# Intake — Portfolio Rx

## How this file is used

The skill's routing layer (`../SKILL.md` body, written in P3) detects what the user provided and dispatches to the matching recipe in this file. The recipe runs first; its output is then handed to the matching review workflow. This file does NOT contain review logic — only ingestion.

## Conventions

- Each recipe is self-contained: trigger detection, tool call sequence, data shape passed to workflow, failure modes, and explicit privacy callout.
- Keep recipes short. The workflow does the thinking — intake just gets the bits in.
- Privacy callouts are MANDATORY for each recipe per PITFALLS §2. The user's trust model is built one recipe at a time.
- We speak as "we" throughout. Failure-mode messages to the user follow voice.md: direct, no hedge, name what's wrong + the next move.

## Index of input types

- [PDF (resume / cover letter / case study export)](#pdf)
- [Portfolio URL](#portfolio-url)
- [Figma file](#figma)
- [Pasted text](#pasted-text)
- [Screenshot](#screenshot)
- [Multi-input combinations](#multi-input)

## Recipes

### PDF {#pdf}

**Trigger:** User attaches a PDF, OR explicitly references a PDF path on disk (anything ending `.pdf`).

**Tool sequence:**
1. `Read` the file — Claude Code's PDF reader extracts text natively.
2. Inspect first paragraph + filename. Heuristic classification:
   - Filename contains `resume` / `cv` → resume.
   - Filename contains `cover` → cover letter.
   - First paragraph contains role title + dates → resume.
   - First paragraph contains case study title + project intro paragraph → case study export.
   - Default if ambiguous: ask "is this a resume or a case study?" — single confirmation, not three questions (per ROUTE-03 + PITFALLS §1.5).

**Output to workflow:**
```
{
  input_type: "resume" | "cover_letter" | "case_study",
  raw_text: <full extracted text>,
  sections: {
    // resume:
    header, experience, education, skills
    // OR case study:
    problem, process, outcome
  },
  source_path: <original PDF path>
}
```
Sections are heuristically split — best-effort. The workflow re-validates structure; intake doesn't need to be perfect.

**Failure modes:**
- PDF is image-only (scanned, no embedded text). Tell the user: "This PDF looks like a scanned image — no extractable text. Share the source doc, or paste the text directly."
- PDF is over 20 pages. Cap at first 10 pages. Resumes shouldn't be over 2; longer files are likely portfolios — say: "This PDF is over 20 pages. Reading the first 10. If this is a portfolio, share the URL instead — we follow case-study links from there."
- Read returns empty. Tell the user: "That path didn't return any text. Verify the file exists at the path you gave us."

**Privacy:**
The PDF text is sent to Anthropic's Claude API as part of the prompt (per PITFALLS §2.1, §2.5). This is normal Claude Code behavior — the skill adds nothing on top. The README's privacy section covers this verbatim; we do not re-state it inside the routing prompt.

---

### Portfolio URL {#portfolio-url}

**Trigger:** User shares a URL in chat, OR references one explicitly. Recognize as a portfolio if:
- TLD or path matches `notion.site`, `read.cv`, `framer.website`, `bento.me`, `super.site`, `webflow.io`, `vercel.app`, or a personal domain ending `.com` / `.dev` / `.io` / `.co` / `.me` / `.design`.
- Path contains `/portfolio`, `/work`, `/projects`, `/case-studies`.
- NOT a `figma.com` URL (that routes to the Figma recipe).

**Tool sequence:**
1. `WebFetch` the homepage URL with a prompt asking for: page text, list of internal links to case studies / project pages, hero copy.
2. From the homepage response, identify up to 4 case-study links. Prioritize:
   - Links labeled with project names (not nav items like "About" / "Contact").
   - Links the user explicitly named ("review the Stripe case study").
3. `WebFetch` each of those up to 4 case-study URLs in parallel. One prompt per fetch: extract case study text, structure (intro / process / outcome if visible), and any visible metric.
4. Stop. Don't crawl deeper (per PITFALLS §3.4).

**Output to workflow:**
```
{
  input_type: "portfolio",
  homepage: { url, hero_copy, raw_text, case_study_links: [...] },
  case_studies: [
    { url, title, raw_text, structure_hint }
  ],
  source_url: <original URL>
}
```

**Failure modes:**
- Homepage returns 4xx/5xx or empty. Tell the user: "We couldn't fetch [URL]. Check the URL, or paste the case study text directly."
- **WebFetch returns 403 / blocked by anti-bot (Cloudflare, Vercel firewall, etc).** Many personal-portfolio hosts block Anthropic's WebFetch user-agent. **BEFORE giving up, fall back to curl with a browser UA.** Tool sequence: `Bash` → `curl -sL -A "Mozilla/5.0 (Macintosh; Intel Mac OS X 10_15_7) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/120.0.0.0 Safari/537.36" "<url>"`. Strip HTML to text inline (`| sed 's/<[^>]*>//g' | tr -s ' \n'` or pipe through a quick parser) and feed the result into the workflow as if WebFetch had returned it. This reaches every portfolio that just has UA-based bot blocking. The privacy callout below still applies — the user's host still sees the request, just from us instead of Anthropic. If `curl` returns a Cloudflare challenge page (not the real content), THEN escalate to "share screenshots, paste the copy."
- Homepage is a JS-only SPA with no server-rendered content. WebFetch will return shell HTML. Say: "This site is rendered client-side — WebFetch only sees the shell. Share screenshots of the case studies, or paste the copy." **Partial-SPA case:** some sites (custom OS-metaphor portfolios, sites with JS-overlay case studies) server-render the homepage tile copy but load case-study internals via JS. In that case, run a tile-only review and emit the partial-portfolio caveat in the output (see `workflows/review-portfolio.md` Step 8 output template). Don't hard-fail when partial review is possible.
- Homepage is behind auth (Notion private, password-gated). Say: "This URL needs auth we don't have. Make it public, share screenshots, or paste the text."
- Fewer than 4 case-study links found. Use what's there. No fabricated links.
- Site is paywalled / behind a hard JS-challenge (not just UA-block). After curl fallback fails: name what's wrong, name the move (screenshots / paste).

**Privacy:**
WebFetch hits the user's portfolio host. The URL — including IP, user-agent, and timestamp — appears in that host's server logs (Vercel, Notion, personal domain) the same as any visitor (per PITFALLS §2.3 verbatim). The fetched page contents are then passed to the Claude API for analysis. The README's privacy section covers this in full.

---

### Figma file {#figma}

**Trigger:** User shares a `figma.com/design/...` or `figma.com/file/...` URL, OR provides a fileKey + nodeId pair explicitly.

**Tool sequence:**
1. Parse `fileKey` and `nodeId` from the URL. URL pattern: `figma.com/design/:fileKey/:fileName?node-id=:nodeId` — convert `-` to `:` in the nodeId. If `figma.com/design/:fileKey/branch/:branchKey/...`, use `branchKey` as the fileKey.
2. `mcp__plugin_figma_figma__get_metadata` first. This is the cheap structural pass — frames, names, hierarchy. We use this to locate which frame to deep-read.
3. From the metadata, pick the target frame:
   - If the user pointed at a specific node (URL had `node-id`), use that.
   - Otherwise pick the largest top-level frame, OR the first one whose name suggests a portfolio piece (`hero`, `case study`, `project`, `cover`).
4. `mcp__plugin_figma_figma__get_design_context` on the target frame. This returns reference code + a screenshot + design tokens.
5. If the file has multiple frames the user wants reviewed, repeat step 4 — but cap at 4 frames to protect context budget (per PITFALLS §3.4).

**Output to workflow:**
```
{
  input_type: "figma",
  file_key: <fileKey>,
  frames_reviewed: [
    { node_id, name, design_context, screenshot_url, tokens }
  ],
  metadata_summary: <high-level structure of the file>
}
```

**Failure modes:**
- Figma MCP returns auth error. Tell the user: "Figma MCP needs auth we don't have. Sign in to the Figma integration in Claude Code, or share screenshots instead."
- File is too large; metadata returns hundreds of frames. Don't enumerate — pick the largest top-level frame and review that. Say: "This file has [N] frames. We're reviewing the largest top-level frame — point at a specific frame if you want a different one."
- nodeId in URL doesn't resolve. Say: "That nodeId didn't resolve. Share the URL of the frame you want reviewed, or just the file URL and we'll pick."

**Privacy:**
The Figma MCP server authenticates against the user's Figma account and fetches file contents through Figma's API (per PITFALLS §2.4 verbatim). The user's file data is governed by Figma's terms of service. Claude (via Anthropic's API) then receives the design context for review. The README's privacy section covers this in full.

---

### Pasted text {#pasted-text}

**Trigger:** User pastes a block of text in chat. Recognize as paste-input if:
- Block is over ~5 lines AND not wrapped in a URL or file path.
- User says "here's my [resume / case study / cover letter / draft]" before or after the paste.
- Block contains structural markers (bullets, dashes, dated rows, headings).

**Tool sequence:**
None. Direct ingestion — no extraction tool runs.

Heuristic classification by structural signal:
- Many short bullets, role+dates, sections like `Experience` / `Education` / `Skills` → resume bullets.
- Multi-paragraph prose, opens with "Dear hiring manager" / "I'm writing to apply" / "I'm excited about" → cover letter.
- Multi-paragraph prose with `Problem` / `Process` / `Outcome` (or similar) headings → case study draft.
- If ambiguous between two of the above, ask once: "is this a resume, a cover letter, or a case study draft?" — one question, not three.

**Output to workflow:**
```
{
  input_type: "resume" | "cover_letter" | "case_study",
  raw_text: <user paste verbatim>,
  source: "paste"
}
```
Sections aren't pre-split for paste — the text is short enough that the workflow does its own structural pass.

**Failure modes:**
- Paste is under ~3 lines. Say: "That's a short paste — share more of the resume / case study so there's something to review."
- Paste is a URL, not text. Route to the Portfolio URL recipe.
- Paste is something the skill doesn't handle (engineering README, marketing landing copy that isn't job-search). Say: "This doesn't look like resume or portfolio copy. Portfolio Rx reviews job-search materials — resumes, cover letters, case studies, portfolio pages."

**Privacy:**
Pasted text is sent to Anthropic's Claude API as part of the normal Claude Code prompt (per PITFALLS §2.1). No extraction tool runs, so this is the simplest data flow of all the recipes — the text the user typed goes straight into the prompt context. The README's privacy section covers this.

---

### Screenshot {#screenshot}

**Trigger:** User attaches an image (PNG / JPG / WebP / HEIC), OR points at an image path on disk.

**Tool sequence:**
1. `Read` with the image path — Claude Code's native multimodal vision handles this.
2. Heuristic classification by visual structure:
   - One-page document with horizontal text rows, name banner, dated rows → resume scan.
   - Design frame (UI mockup, marketing layout, app screen) → portfolio piece.
   - Long screenshot of a case-study page (homepage / Notion page / Read.cv page) → portfolio fragment.
   - Photo of a printed page → resume scan (rare, but route the same way).
3. If multiple screenshots are attached, classify each one. They may all be portfolio pieces; they may be a resume + a case study; treat each on its own.

**Output to workflow:**
```
{
  input_type: "resume" | "portfolio_piece" | "portfolio_page",
  image_path: <path>,
  visual_description: <what's in the image, structural>,
  extracted_text: <visible copy, if legible>
}
```

**Failure modes:**
- Image is too low-res to read. Say: "This screenshot is too low-res for us to read the copy. Share a higher-res version or paste the text."
- Image is a meme / unrelated photo. Say: "That image doesn't look like a portfolio piece or a resume. Share the actual screen you want reviewed."
- Multiple screenshots and they're inconsistent (e.g. a resume + a meme). Process the relevant ones; flag the irrelevant ones in one line.

**Privacy:**
The image is sent to Anthropic's Claude API as an image input (per PITFALLS §2.1, §2.5). It is processed by Claude's hosted multimodal vision, not by a local model. The README's privacy section covers this — specifically the line that we do not carve out a "but images stay local" claim, because they don't.

---

### Multi-input combinations {#multi-input}

**Trigger:** Two or more inputs of different classes detected in the same invocation. Common combinations:
- Resume PDF + portfolio URL.
- Resume PDF + Figma file + screenshots.
- Pasted resume + portfolio URL.
- Cover letter PDF + resume PDF (both resume-class — handled inside review-resume.md, not here).

**This section is a handoff doc, not a recipe.** Atomic workflows in P2 (`review-resume.md`, `review-portfolio.md`) handle one input class at a time. Multi-class combinations route to the combined workflow built in P3 (`review-combined.md`).

**Procedure (executed by the routing layer in P3):**
1. Detect all inputs in the user's invocation. Classify each by which recipe matches (PDF / URL / Figma / paste / screenshot).
2. For each input, run its recipe in this file. Recipes can run in parallel — they don't depend on each other.
3. Collect each recipe's output object.
4. Group outputs by class:
   - `resume_inputs[]` — anything where `input_type` ∈ `{resume, cover_letter}`.
   - `portfolio_inputs[]` — anything where `input_type` ∈ `{portfolio, figma, portfolio_piece, portfolio_page, case_study}`.
5. Hand the grouped outputs to `review-combined.md` (P3). Combined mode is the default for multi-class inputs (per D-P2-12 + COMBO-01).
6. Show the inferred plan back to the user in one line: "We've got [resume PDF + portfolio URL + 2 screenshots] — running combined review with Top 3 fixes first. Right?" Single confirmation, not three questions.

**Why this section exists:** without it, the routing layer would have to re-derive the grouping rules from each recipe's `input_type`. Centralizing the handoff here keeps the recipes simple and the routing logic thin.

**Privacy:** each input flows per its own recipe's privacy callout. Multi-input doesn't add a new data flow — it just means more of them happen in one invocation.

---

## What this file does NOT do

Set expectations. People will ask for these and we don't handle them in v1:

- **Transcribe video / audio.** Loom, Vimeo, YouTube case-study walkthroughs, voice memos — out of scope. We can review a written case study, not a video walkthrough. (PITFALLS §3.2 known gap.)
- **OCR scanned PDFs to high quality.** If a PDF is image-only (scan of a printed resume), Read returns empty text. We tell the user to share the source doc — we don't run OCR.
- **Follow paywalled or auth-gated portfolio links.** Notion private pages, password-gated Webflow sites, anything behind a login wall — WebFetch can't reach them. The user makes the page public, shares screenshots, or pastes the text.
- **Crawl an entire portfolio site.** We follow up to 4 case-study links from the homepage. Beyond that we ask the user to point at the specific pieces they want reviewed.
- **Parse a Figma prototype's interaction flow.** We read static frames via `get_design_context`. Animated transitions, hover states, prototype connections — those need a screencap or a description from the user.
- **Review code or engineering portfolios.** Out of scope per SPEC "Out of Scope" — different domain, different rubric.
- **Compare two portfolios side by side.** Out of scope for v1 (deferred — would be a separate workflow).
- **Read an Adobe XD / Sketch / InVision file.** Figma only via MCP. Other design files → export to PDF or screenshot.

## Adding a new input type

When a new input class enters scope (e.g. Loom transcripts, Adobe XD exports), do all three:

- **Add the recipe in this file.** Use the same five-section template the existing recipes use: Trigger, Tool sequence, Output to workflow, Failure modes, Privacy. Same H3 + anchor pattern. Same voice — direct failure messages, no hedge.
- **Required output fields:** `input_type`, `raw_text` (or equivalent media reference), `source` (path / URL / "paste"), and any structural hints the workflow needs. The `input_type` value must map cleanly to either `resume_inputs` or `portfolio_inputs` per the multi-input handoff above.
- **Plumb into routing.** Update the SKILL.md routing table (P3) to detect the new input class and dispatch to this recipe. Update the multi-input grouping rules in this file's `#multi-input` section if the new class doesn't fit the existing two groups.
