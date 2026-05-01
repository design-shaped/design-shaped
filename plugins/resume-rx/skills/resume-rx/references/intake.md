---
title: Intake — Resume Rx
plugin: resume-rx
covers: INPUT-01, INPUT-02, INPUT-03, INPUT-04, MODE-04
sources:
  - .planning/builds/resume-rx/audit/parts/intake.md
  - .planning/builds/resume-rx/SPEC.md (D-01, D-02, D-04, D-25)
  - .planning/builds/resume-rx/REQUIREMENTS.md (INPUT-01..04)
  - .planning/builds/resume-rx/research/FEATURES.md §2.7 (multi-format normalization)
  - portfolio-rx/skills/portfolio-rx/references/intake.md (structural pattern only)
---

# Intake — Resume Rx

## How this file is used

The skill's routing layer (`../SKILL.md` body, written in P6) detects what the user provided and dispatches to the matching recipe in this file. The recipe runs first; its output is then handed to the mode router (line-edit / brainstorm / draft-from-list per D-01). This file does NOT contain mode logic, rewrite logic, or rubric logic — only ingestion. The four recipes here cover the four locked input formats per SPEC D-02. All recipes normalize to the same `INTAKE_RESUME` schema before handoff per FEATURES §2.7.

## Conventions

- Each recipe is self-contained: detection signal, extraction approach, output shape, handoff to mode router. Failure-mode strings follow voice.md — direct, no hedge, name what's wrong + the next move.
- We speak as "we" throughout. Failure messages to the user follow voice.md register.
- All recipes produce the same `INTAKE_RESUME` object shape (defined below). The mode router consumes one schema, not four.
- Privacy: every recipe sends text to Anthropic's Claude API as part of the normal Claude Code prompt. WebFetch recipes additionally hit the user's chosen host (LinkedIn / Notion / Google Docs) — that fetch shows up in those hosts' server logs the same as any visitor. The README's privacy section covers this in full; we do not re-state it inside the recipe bodies.
- Per D-25: missing-portfolio-link in the resume is **flag-only in v1** — we detect absence and warn, we do not run a live link verification. Live-check deferred to v1.1+.

## Index of input formats

- [Plain text paste](#paste)
- [PDF](#pdf)
- [LinkedIn URL or JSON export](#linkedin)
- [Notion / Google Doc URL](#notion-gdoc)

## Recipes

### Plain text paste {#paste}

**Detection signal:**
- Multi-line text in the user message (over ~5 lines) AND not wrapped in a URL or file path.
- User says "here's my resume" / "here's a draft" / "here's a list of things I've done" before or after the paste.
- Block contains structural markers (bullets, dashes, dated rows, headings like `Experience` / `Skills` / `Education`).

**Extraction approach:**
None — direct ingestion. The pasted text is the `raw_text`. No tool runs. Set `format: "paste"` and `source_provenance: "user paste"`.

**Mode-routing hint detection** (sets `mode_routing_hint` on the schema; the mode router has final say):
- Many short bullets, role+dates, full sections (Experience / Skills / Education) → `line_edit` (full draft present, user wants it sharper).
- Raw list of achievements / projects, no resume structure (no role headers, no dates, just dumped lines) → `draft_from_list`.
- Sparse content (under ~3 bullets, or a single role with no detail) or user explicitly says "I'm stuck" / "blank page" / "help me think" → `brainstorm`.
- Ambiguous between two of the above → `unknown`. The mode router asks one question (per voice.md single-confirmation rule) — never three.

**Handoff:**
Emit `INTAKE_RESUME` with `format: "paste"`, `raw_text: <user paste verbatim>`, `mode_routing_hint: <as detected>`. Hand to mode router. The mode router decides the working mode using `mode_routing_hint` plus any explicit override (`/resume-rx brainstorm` etc. per MODE-05).

**Failure modes:**
- Paste is under ~3 lines. Say: "That's a short paste — share more of the resume, or a list of what you've done, so there's something to work with."
- Paste is a URL, not text. Route to the LinkedIn or Notion/GDoc recipe based on the host.
- Paste is something the skill doesn't handle (engineering README, marketing landing copy, an essay). Say: "This doesn't look like resume content. Resume Rx works on resume drafts, raw achievement lists, or interview-stage content for designers."

---

### PDF {#pdf}

**Detection signal:**
- User attaches a PDF, OR explicitly references a path on disk ending in `.pdf`.
- Filename containing `resume` / `cv` is a stronger signal but not required — resume-rx is a single-class intake (resume only), so any PDF in scope is treated as a resume per FEATURES.md §4 ("Content-only scope").

**Extraction approach:**
1. `Read` the file — Claude Code's PDF reader extracts text natively (per INPUT-02).
2. The full extracted text is the `raw_text`. We do not pre-split sections — the workflow does its own structural pass when needed.
3. Set `format: "pdf"` and `source_provenance: <original PDF path>`.
4. Run the same mode-routing-hint detection as the paste recipe (PDF resumes are usually full drafts → `line_edit`, but a designer may dump a "things I've done" PDF — handle both).

**Handoff:**
Emit `INTAKE_RESUME` with `format: "pdf"`, `raw_text: <full extracted text>`, `source_provenance: <path>`, `mode_routing_hint: <as detected>`. Hand to mode router.

**Failure modes:**
- PDF is image-only (scanned, no embedded text). `Read` returns empty. Tell the user: "This PDF looks like a scanned image — no extractable text. Share the source doc, or paste the text directly."
- PDF is over 20 pages. Cap at first 10 pages. Resumes shouldn't be over 2; longer files are likely portfolios. Say: "This PDF is over 20 pages. Reading the first 10. If this is a portfolio, Resume Rx is content-only — Portfolio Rx handles portfolio reviews."
- `Read` returns empty on a non-image PDF. Say: "That path didn't return any text. Verify the file exists at the path you gave us, or paste the text directly."

---

### LinkedIn URL or JSON export {#linkedin}

**Detection signal:**
- URL matches `linkedin.com/in/<handle>` (public profile URL).
- OR pasted JSON with the LinkedIn export shape — top-level keys including some of: `firstName`, `lastName`, `headline`, `summary`, `positions`, `educations`, `skills`. (The user has explicitly exported their LinkedIn data; we accept the JSON as-is.)
- NOT a `linkedin.com/jobs/...` URL (out of scope — no JD-targeting v1 per D-11).

**Extraction approach:**
1. **If URL:** `WebFetch` the profile URL with a prompt asking for: headline, summary / about section, experience entries (title / company / dates / description per role), education entries, skills list. The `WebFetch` model parses LinkedIn's rendered HTML and returns a structured summary.
2. **If JSON:** parse the JSON directly. Extract the same fields: headline, summary, positions[], educations[], skills[].
3. Concatenate into resume-shaped `raw_text` — header (name + headline), summary, experience (one block per role), skills, education. This is the normalization step per FEATURES §2.7.
4. **Per D-25** — scan the assembled text for portfolio link presence. If a URL pattern matching a portfolio host (TLD or path matches `notion.site`, `read.cv`, `framer.website`, `bento.me`, `super.site`, `webflow.io`, `vercel.app`, or a personal domain ending `.com` / `.dev` / `.io` / `.co` / `.me` / `.design` with portfolio-shaped path) is present, set `has_link: true` and `link_url: <url>`. Otherwise `has_link: false` and `link_url: null`. **Flag-only — we do NOT run a live `WebFetch` on the link to verify it resolves.** Live-check is deferred to v1.1+ per D-25.
5. Set `format: "linkedin_url"` or `format: "linkedin_json"` and `source_provenance: <profile URL or "linkedin json export">`.

**Handoff:**
Emit `INTAKE_RESUME` with `format: "linkedin_url" | "linkedin_json"`, `raw_text: <normalized resume-shaped text>`, `source_provenance`, `has_link`, `link_url`, `mode_routing_hint`. LinkedIn input is almost always `line_edit` (a profile is a draft) — but if the profile is sparse (no role descriptions, just titles), set `mode_routing_hint: "brainstorm"`. Hand to mode router.

**Failure modes:**
- `WebFetch` returns 4xx, empty, or "this profile is private" content. Say: "We couldn't fetch that LinkedIn profile — it may be private or login-gated. Make the profile public, paste the text, or export the LinkedIn JSON and share that."
- LinkedIn profile is a JS-only render that `WebFetch` only sees as shell HTML. Same script: name what's wrong, name the move (paste / JSON export).
- Pasted JSON doesn't match the LinkedIn export shape. Say: "This JSON doesn't look like a LinkedIn export. Share the profile URL, paste the resume text, or check the export format."
- `has_link: false` is **not a failure** — it's a flag the workflow can probe ("we didn't see a portfolio link in your profile — adding one is a Top 3 fix at any seniority"). Per D-25.

---

### Notion / Google Doc URL {#notion-gdoc}

**Detection signal:**
- URL matches `notion.so/...` or `<workspace>.notion.site/...` for Notion.
- URL matches `docs.google.com/document/...` for Google Docs.
- The URL is the resume itself (a designer's Notion-resume page or a Google Doc resume), not a portfolio site (portfolio sites route nowhere — Resume Rx doesn't accept them; redirect to Portfolio Rx).

**Extraction approach:**
1. `WebFetch` the URL with a format-aware prompt:
   - **Notion:** ask for the page text in reading order, preserving section headings (Experience / Skills / Education), bullets, and dated rows. Notion published pages render server-side enough that `WebFetch` gets usable text.
   - **Google Doc:** ask for the document text in reading order. Public-link Google Docs (`?usp=sharing` with view permission) return text; private docs return the login wall.
2. Normalize to resume-shaped `raw_text` per FEATURES §2.7 — same shape as the LinkedIn recipe output (header, summary if present, experience, skills, education). Whatever sections are present.
3. Run the same portfolio-link presence scan as the LinkedIn recipe per D-25 — set `has_link` / `link_url` flags. No live verification.
4. Set `format: "notion_url"` or `format: "gdoc_url"` and `source_provenance: <original URL>`.
5. Run mode-routing-hint detection as in the paste recipe (Notion / GDoc resumes are typically full drafts → `line_edit`).

**Handoff:**
Emit `INTAKE_RESUME` with `format`, `raw_text`, `source_provenance`, `has_link`, `link_url`, `mode_routing_hint`. Hand to mode router.

**Failure modes:**
- URL is private / behind auth / requires login. `WebFetch` returns the login wall. Say: "This URL needs auth we don't have. Make the page public (Notion → Share → Publish; Docs → Share → Anyone with the link can view), paste the text, or export to PDF and share that."
- Notion URL is a workspace page (not published). Same script.
- Google Doc returns the share-request page. Same script.
- URL is a Notion or Docs page that isn't a resume (a portfolio piece, a case study, an internal doc). Say: "This page doesn't look like a resume. Resume Rx works on resume content; Portfolio Rx handles portfolio pages and case studies."

---

## INTAKE_RESUME schema (output to mode router)

Every recipe normalizes to this single typed object. The mode router consumes one shape, not four — per FEATURES §2.7.

```
INTAKE_RESUME {
  raw_text: string                                                    // full resume text, normalized to resume-shape (header / summary / experience / skills / education present where available)
  format: "paste" | "pdf" | "linkedin_url" | "linkedin_json"
        | "notion_url" | "gdoc_url"                                   // which recipe ran (D-02 enum)
  claimed_seniority: "junior" | "mid" | "senior" | "staff" | "unknown"  // user-self-identified, optional, "unknown" until the workflow asks
  claimed_role_family: "product_designer" | "ux_researcher"
                     | "design_engineer" | "design_lead_manager"
                     | "unknown"                                       // per D-04, four presets; "unknown" until workflow asks
  source_provenance: string                                            // free-form: where the text came from — "user paste" / "<PDF path>" / "<LinkedIn URL>" / "linkedin json export" / "<Notion URL>" / "<GDoc URL>"
  has_link: boolean                                                    // portfolio link present in the resume text — per D-25, detect-only, no live verification
  link_url: string | null                                              // the portfolio URL we found, or null if has_link is false
  sensitive_flags: string[]                                            // detected sensitive-content markers — entries like "nda_mention" / "confidential_metric" / "employer_private_project" — points the workflow to voice.md sensitive-content register (per FEATURES §2.4)
  mode_routing_hint: "line_edit" | "brainstorm"
                   | "draft_from_list" | "unknown"                     // recipe's best guess from input shape; mode router has final say (per D-01 + MODE-04)
}
```

**Field notes:**
- `claimed_seniority` and `claimed_role_family` are not required from intake — most users won't volunteer them in the first message. The recipe sets them to `"unknown"` if not stated; the mode router or the workflow asks one calibration question (per voice.md single-confirmation rule) before applying the rubric and the role-family preset.
- `sensitive_flags` is an open-ended array. Detection patterns covered: literal "NDA" / "confidential" / "internal" / "can't share" mentions in the text; round-number metrics that read as fabricated (the workflow's job, not intake's, but intake flags obvious cases per D-16-RR); employer-private project names. The flag tells the workflow to switch into the sensitive-content register from voice.md — it does not redact text.
- `mode_routing_hint` is a hint, not a decision. The mode router (P3 SKILL.md) reconciles it with explicit user override per MODE-05.

## Mode routing handoff

The intake recipe's job ends at `INTAKE_RESUME`. The mode router (specified in P3 / authored in P6 SKILL.md body) reads the schema and dispatches to one of three modes per D-01:

- **Line-edit** — `mode_routing_hint == "line_edit"` AND the user did not explicitly request another mode. Full-draft inputs (paste with sections, PDF resume, LinkedIn profile, Notion/GDoc resume) route here by default.
- **Brainstorm** — `mode_routing_hint == "brainstorm"` (sparse input or explicit blank-page signal), OR the user explicitly invoked `/resume-rx brainstorm`. Conversational mode — the workflow asks scope/impact probes, then drafts.
- **Draft-from-list** — `mode_routing_hint == "draft_from_list"` (raw achievement dump, no resume structure), OR explicit invocation. The workflow structures the dump into resume sections.
- **Unknown / ambiguous** — the router asks one calibration question (single confirmation, not three — per voice.md): "Want me to line-edit what's there, brainstorm new bullets together, or draft a resume from your list?"

Full router decision logic (signal weights, override precedence per MODE-05, multi-input handling) is deferred to P3 / P6. Intake's contract is: emit a clean `INTAKE_RESUME` and let the router decide.

## What this file does NOT do

Set expectations. People will ask for these and we don't handle them in v1:

- **Live-verify portfolio links.** Per D-25, missing-link is flag-only in v1. We detect the presence/absence of a portfolio URL in the resume text; we do not `WebFetch` it. Live-check deferred to v1.1+.
- **Read screenshots / images of resumes.** Resume Rx is content-only (FEATURES §4). If the user attaches a screenshot of a printed resume, we ask them to share the source doc or paste the text.
- **Crawl portfolio sites linked from the resume.** That's Portfolio Rx's job. Resume Rx works on the resume text only.
- **Read JD URLs / paste-in job descriptions.** No JD-targeting in v1 per D-11. Deferred.
- **Multi-class combined intake (resume + portfolio).** That's the cross-plugin pair-mode deferred per SPEC. Resume Rx accepts resume content; if a designer also wants their portfolio reviewed, they invoke Portfolio Rx separately.
- **OCR scanned PDFs.** If `Read` returns empty on an image-only PDF, we tell the user to share the source doc — no OCR.
- **Auth-walled / private Notion or GDoc URLs.** `WebFetch` can't reach login walls. The user makes the page public, exports to PDF, or pastes the text.
- **LinkedIn profiles set to private.** Same — `WebFetch` only sees what the public web sees.

## Adding a new input format

When a new input format enters scope (e.g. Markdown export from a resume builder, Pages doc, Word doc), do all three:

- **Add the recipe in this file.** Use the same four-section template the existing recipes use: Detection signal, Extraction approach, Handoff, Failure modes. Same H3 + anchor pattern. Same voice.
- **Required output fields:** every recipe must emit a complete `INTAKE_RESUME` object. Add a new value to the `format` enum if the new input doesn't fit `paste | pdf | linkedin_url | linkedin_json | notion_url | gdoc_url`. Update this file's schema definition + the SKILL.md routing table (P6) in the same change.
- **Plumb into routing.** Update the SKILL.md routing table to detect the new input class and dispatch to this recipe. Update the index at the top of this file.

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
