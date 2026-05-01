---
title: Gotchas — Resume Rx
plugin: resume-rx
covers: operational pitfalls the skill executor must avoid (G01..G14)
sources:
  - .planning/builds/resume-rx/audit/parts/gotchas.md (per-gotcha decisions + net-new list)
  - .planning/builds/resume-rx/audit/foundation-decisions.md (gotchas.md target list, lines 1064–1080)
  - .planning/builds/resume-rx/research/PITFALLS.md (§2.1, §2.2, §4.1, §4.2, §4.3)
  - .planning/builds/resume-rx/SPEC.md (D-16-RR, D-17-RR, D-19-RR, D-21-RR, D-22, D-23, D-24, D-25)
  - portfolio-rx/plugins/portfolio-rx/skills/portfolio-rx/gotchas.md (carry-over shape)
---

# Gotchas — Resume Rx

**Definition.** Gotchas are operational pitfalls the executor must avoid while running a Resume Rx review — pre-committed "do not do this" rules that bind the skill itself, not the reviewee. They are distinct from two neighboring files:

- **Heuristics** (`references/heuristics.md`) bias *how* the review reads the artifact (skim-time tier, dominant-bullet sampling, frame-then-fix). Heuristics shape the lens.
- **Common-flags** (`references/common-flags.md`) name the *reviewee bullet shapes* the lens catches (R01..R12 — filler verbs, fabricated metrics, scope inflation, etc.). Common-flags shape what the lens points at.
- **Gotchas** (this file) are *executor-bound* guardrails — what the skill itself must not do regardless of what the artifact looks like. ATS framing discipline, banned register, deferred features, scope boundaries.

IDs are append-only (G01, G02, …). Never renumber post-ship — workflows and rubrics cite gotchas by ID.

---

## G01 — Modern ATS framing: write for the hiring design manager, ATS follows

**What goes wrong.** The skill treats ATS-keyword optimization and human-readability as competing concerns and produces two-pass advice ("now add keywords for the bot"). This is the false-split refutation per PITFALLS §4.3 — modern enterprise ATSes (Greenhouse, Lever, Workday, iCIMS) use semantic parsing, and a resume written for the hiring design manager performs well in any modern ATS. Splitting the audience produces advice that hurts the human read without helping the bot read.

**Avoid by.** Frame every review around the hiring design manager as the audience. The only ATS-specific advice that belongs is the narrow structural-parse-failure list in G03. If a workflow ever surfaces "what ATS wants" as a separate concern, the framing is wrong — collapse it back into the hiring-manager frame.

**Cite.** Audit appendix `gotchas.md` net-new item 1 (line 109). SPEC D-21-RR. PITFALLS §4.3.

---

## G02 — The "ATS rejects PDFs" myth — debunk it on contact

**What goes wrong.** Designers arrive having been told that PDFs are an ATS death sentence and the skill validates the myth. They strip formatting, abandon their carefully designed PDF, and produce a worse document for the hiring manager who actually reads it. Per PITFALLS §4.1: "Text-based PDFs work fine with most ATS systems."

**Avoid by.** When a designer asks "should I switch to .docx because of ATS?" the answer is no by default — text-based PDFs parse reliably on every modern enterprise ATS. The real risks are narrow and listed in G03. Do not coach designers to abandon PDF as a content format.

**Cite.** Audit appendix `gotchas.md` net-new item 2 (line 110). PITFALLS §4.1. SPEC D-21-RR.

---

## G03 — The narrow real ATS risks — name them, do not generalize

**What goes wrong.** The skill either (a) waves vaguely at "ATS issues" without specifics, or (b) over-broadens the risk list until any designer-shaped resume looks broken. Both fail the user. The actual structural-parse-failure list is short and specific.

**Avoid by.** Limit ATS-format flags to this list, and only this list:

1. Scanned PDFs (image of a resume, no selectable text).
2. Text embedded inside images (a "skills" graphic with no text layer).
3. Merged-cell tables for layout.
4. Non-standard section headers (e.g., "My Story" instead of "Experience").

If a flag isn't on this list, it isn't an ATS-format issue — it's a content issue, and belongs under common-flags / rubrics.

**Cite.** Audit appendix `gotchas.md` net-new item 3 (line 111). PITFALLS §4.1. FEATURES §1.8.

---

## G04 — The keyword-stuffing trap — passes the bot, fails the 7-second human scan

**What goes wrong.** The skill recommends keyword addition in ways that wreck readability — keyword lists buried in bullets, repetition density, "Skills: Figma, Sketch, InVision, Miro, FigJam, Maze, Hotjar, Lookback, FullStory, Dovetail, …". Modern ATSes flag dense repetition as spam (HR.com 2025: 92% of recruiters say ATS is designed to surface qualified candidates, not be gamed). And the hiring manager's 7-second skim fails on cluttered output regardless.

**Avoid by.** Treat tools-in-context (named inside bullets where they did real work) as the signal; treat tools-in-list (skills section as inventory dump) as the noise. The fix for missing keywords is to move them into bullets in context, not to add more. Role-family presets teach natural vocabulary — they do not authorize keyword injection.

**Cite.** Audit appendix `gotchas.md` net-new item 4 (line 112). PITFALLS §4.2. Common-flags R-IDs (skills section over-tooling pattern).

---

## G05 — No numeric scores, no grades, no meters — ever

**What goes wrong.** The skill produces "Resume score: 72/100" or "ATS-readiness: 4/5" or any meter / gauge / grade. The reference points (Resume.io's "42/100", Rezi's score widgets) are exactly the pattern users find demoralizing and uninformative — a number with no coaching frame. Resume Rx ships zero numeric scoring, full stop.

**Avoid by.** Every output is qualitative — flagged shape + cost + rewrite + framework citation. If a workflow ever computes a numeric score internally (e.g., a count of flags), that count never reaches the user surface. Users will sometimes ask for a score; the answer is the no-score rationale, not a generated number.

**Cite.** Audit appendix `gotchas.md` net-new item 5 (line 113). SPEC D-23.

---

## G06 — No invented metrics — absence becomes a probe, not a number

**What goes wrong.** The skill rewrites a bullet and adds a metric the user never provided. "Improved user satisfaction by 30%" appears in the rewrite; the user's draft had no satisfaction data. This is the highest-trust-failure mode in AI resume tools per PITFALLS §2.1 (Rezi, Resume.io, default ChatGPT prompts all do this). Once a user notices a fabricated number, the entire review is suspect.

**Avoid by.** Hard rule: never add a metric the source content does not contain. If a metric would strengthen the bullet, write a probe into the rationale note instead — "If you have a satisfaction or completion metric here, this is the slot for it. If not, scope (team size, user count, timeline) works." This is non-negotiable correctness, not a style preference.

**Cite.** Audit appendix `gotchas.md` net-new item 6 (line 114). SPEC D-16-RR. PITFALLS §2.1.

---

## G07 — AI-default verbs banned — *spearheaded / leveraged / synergized / catalyzed*

**What goes wrong.** Rewrites converge on the recognizable "AI resume voice" — "Spearheaded cross-functional initiatives to drive strategic outcomes." Hiring managers at design-forward companies have been vocal since 2024 about recognizing this pattern instantly per PITFALLS §2.2. The verbs that read as "polished" to a generic LLM are now active negative signals.

**Avoid by.** The banned list lives in `references/voice.md` and is enforced at rewrite time: *spearheaded, leveraged, synergized, catalyzed* (and close kin — *orchestrated, empowered, unlocked, drove value, optimized cross-functional* in abstract use). Rewrites must be at least as concrete as the original — never swap a specific verb for a buzzword. If a rewrite passes the verb-list check but reads more abstract than the source, it failed the rewrite-discipline rule too.

**Cite.** Audit appendix `gotchas.md` net-new item 7 (line 115). SPEC D-17-RR. PITFALLS §2.2.

---

## G08 — No JD-paste / job-description tailoring in v1

**What goes wrong.** A user pastes a job description alongside their resume and asks the skill to "tailor my resume to this JD." The skill attempts JD-paste matching, hallucinates fit, and the output drifts toward keyword stuffing per G04. JD-paste tailoring is a real future feature, but v1 is not it.

**Avoid by.** When a user provides a JD, surface the v1 deferral explicitly: "JD-paste tailoring is deferred to v1.1+ — for now I'll review your resume on its own merits, and you can use the role-family preset closest to the target." Do not silently absorb the JD as input. Do not pretend to tailor.

**Cite.** Audit appendix `gotchas.md` net-new item 8 (line 116). SPEC Deferred Ideas section.

---

## G09 — No ATS-format export, no .docx templates, no visual-layout output

**What goes wrong.** A user asks the skill to output a "clean ATS-friendly .docx version" or a re-laid-out resume. The skill is content-focused — it does not produce or export visual layouts, templates, or alternate file formats. v1 ships review and rewrites, not artifacts.

**Avoid by.** Surface the v1 deferral on contact: "Resume Rx is content-focused — visual layout and export are deferred. Output ships as side-by-side bullet rewrites against your existing draft." If a workflow is ever tempted to render markdown table layouts as a "resume preview," it crossed the line.

**Cite.** Audit appendix `gotchas.md` net-new item 9 (line 117). SPEC Deferred Ideas + out-of-scope section.

---

## G10 — No cover-letter companion in v1

**What goes wrong.** A user asks the skill to "also write a cover letter for this role" or "draft a paragraph for the application form." The skill obliges, drifts into a different content type with different conventions, and produces a generic cover letter on top of an inconsistent register.

**Avoid by.** Cover-letter generation is deferred to a future skill. Surface the deferral when asked: "Cover letters are out of scope in v1 — Resume Rx covers the resume artifact only. The voice and bullet rewrites here are useful raw material if you draft one yourself."

**Cite.** Audit appendix `gotchas.md` net-new item 10 (line 118). SPEC Deferred Ideas section.

---

## G11 — Out-of-scope resume types — name them politely, do not bend the rubric

**What goes wrong.** Someone pastes an academic CV (publications-list-driven, multi-page, no career narrative), a federal/government resume (USAJOBS-conformant, structurally different), an international CV requiring photo / DOB / marital status, or a non-designer resume (PM, engineering, marketing, exec). The skill applies the designer-resume rubric anyway and gives advice that's wrong for the actual artifact.

**Avoid by.** Detect at intake. Resume Rx's rubric is shaped for US-market designer resumes (1 page, no photo, no DOB, no marital status, narrative-driven). For artifacts outside that envelope, surface the scope mismatch explicitly and decline to apply the rubric: "This looks like an academic CV / federal resume / international CV / non-designer resume — Resume Rx's rubric is calibrated for US-market designer resumes and would give you wrong advice here. Use a tool calibrated for that artifact." Do not run the review on a forced fit.

**Cite.** Audit appendix `gotchas.md` net-new item 11 (line 119). Audit appendix `gotchas.md` per-gotcha decision §1 ("rubric is US-shaped") and §2 ("out-of-scope portfolios").

---

## G12 — Role-family presets are exactly four — hybrid roles get the closest preset, not a custom one

**What goes wrong.** A user identifies as a "design technologist / content designer / design ops lead / service designer / strategist" and the skill invents a fifth preset on the fly, hallucinating verb sets and scope vocabulary that aren't in any reference file. Or worse, the workflow paraphrases two presets together into a Frankenpreset.

**Avoid by.** The four presets are fixed at `references/role-families/`: `product-designer.md`, `ux-researcher.md`, `design-engineer.md`, `design-lead-manager.md`. Hybrid and adjacent roles get routed to the closest preset (content designer → product-designer; design-systems lead → design-engineer or design-lead-manager depending on IC vs. people scope), with one inline note acknowledging the routing call. Do not invent a fifth preset. Custom presets are deferred to v1.1+.

**Cite.** Audit appendix `gotchas.md` net-new item 12 (line 120). SPEC D-19-RR.

---

## G13 — Missing portfolio-link is flag-only in v1 — do NOT WebFetch

**What goes wrong.** The skill detects a portfolio URL in the resume header, decides to be helpful, and WebFetches it to validate that it loads. v1 does not include the live-check capability, and WebFetching arbitrary user-supplied URLs introduces privacy and reliability surface that v1 has not signed off on.

**Avoid by.** v1 is detect-and-warn only. If a portfolio link appears in the resume, surface a flag — "Test this link from a fresh browser before you send the resume out; bit.ly redirects, password gates, and 404s are common silent failures" — but do not actually load the URL. Live link-check is deferred to v1.1+.

**Cite.** Audit appendix `gotchas.md` net-new item 13 (line 121). SPEC D-25. Common-flags R06 (missing/broken portfolio link).

---

## G14 — Trigger collision with portfolio-rx — both plugins installed, route correctly

**What goes wrong.** A user has both `portfolio-rx` and `resume-rx` installed. They paste a resume. Portfolio-rx still ships a `review-resume.md` workflow internally, so the trigger fires there too — and the user gets portfolio-rx's lighter resume review instead of Resume Rx's dedicated line-edit / brainstorm / draft-from-list modes. The user has no idea which skill responded; the review is generically worse.

**Avoid by.** Resume-rx's SKILL.md description is scope-narrowed at write time per D-22 to win the resume-paste trigger over portfolio-rx. Per D-24, portfolio-rx's SKILL.md description gets a one-line scope-narrowing tweak in the same monorepo PR before resume-rx ships, so portfolio-rx no longer claims resume artifacts as a primary trigger. The QA-01 trigger battery runs with both plugins installed and includes resume-paste collision scenarios. If a user reports landing in portfolio-rx for a resume artifact, the SKILL.md descriptions need the next round of tightening — not a workaround inside this skill.

**Cite.** Audit appendix `gotchas.md` net-new item 14 (line 122). SPEC D-22, D-24. PITFALLS §3.3.

---

## Footer (verbatim, mandatory — D-16-RR)

Every output the skill produces ends with:

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
