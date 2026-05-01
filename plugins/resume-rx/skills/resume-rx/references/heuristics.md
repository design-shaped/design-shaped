---
title: Heuristics — Resume Rx
plugin: resume-rx
covers: bullet-shape, scope-claims, section-structure, voice-register
sources:
  - audit/parts/heuristics.md (Phase 1 audit appendix)
  - audit/foundation-decisions.md §heuristics.md (target list, lines 1041–1062)
  - research/STREAM_MINING_RESUME.md (Bucket 8 — per-heuristic transcript IDs)
  - research/FEATURES.md (net-new heuristic surfacing)
  - research/PITFALLS.md (net-new heuristic surfacing)
  - portfolio-rx/skills/portfolio-rx/references/heuristics.md (carry-over shape reference)
  - SPEC.md D-15-RR, D-16-RR, D-17-RR, D-19-RR, D-20, D-21-RR
---

# Heuristics — Resume Rx

Heuristics are stream-mined gut-rules that bias the review — they're how a Tim+Nate review *leans*, not what it must do. They sit beside two other reference layers and earn their place by being distinct from both: **common-flags** name reviewee bullet shapes that recur across resumes (R01, R02, R09 …) and prescribe the fix per pattern, while **gotchas** name executor pitfalls (the model's failure modes — fabricated metrics, ATS theater, generic LLM verbs). Heuristics are smaller-grain than common-flags and operate at the phrase or section level. Cite by name, never paraphrase (D-19), and only when the rule adds a real second angle. One or two heuristics per review at most — over-citing degrades the voice. Append-only after ship per the portfolio-rx procedure: never rewrite an existing heuristic in place; if framing genuinely changes, add a new one and mark the old as superseded so anchor IDs stay stable.

---

## Bullet shape & impact

These heuristics govern what a single resume bullet must do — the order of clauses, the verb choice, the side-by-side rewrite contract, and the licensed shapes for senior signal.

### H-S01 — Scope-noun-before-verb (senior signal)
**Rule:** At senior+ tier, lead the bullet with the scope noun (team / ARR / product surface / customer base), then the verb, then the metric. Verb-only bullets read mid regardless of header title.
**Cite:** audit/parts/heuristics.md "Scope-noun-before-verb (senior signal)" net-new list; STREAM_MINING_RESUME.md §B3, §B4 (4tg1bPbOxus L762–765 — *"You're not gonna claim sole ownership of [a project that wasn't yours alone]"*); FEATURES §2.6 senior-bullet diagnostic; framework: Scope-Impact-Metric (frameworks.md).

### H-S02 — Why-how-what bullet ordering
**Rule:** Resume experience bullets read strongest in why-how-what order. Lead with the impact (the why or the metric), then the method (how), then the artifact (what). Most-impressive thing first because that's all the recruiter skims.
**Cite:** audit/parts/heuristics.md §Stream-mined H-S04 (port verbatim); STREAM_MINING_RESUME.md §C5–C7 (4tg1bPbOxus L1413–1426 — *"if you follow a what-how-why approach, really hard to write a bad bullet"*); framework: What/How/Why (frameworks.md).

### H-S03 — Banned-AI-default-verb list
**Rule:** Never emit *spearheaded, leveraged, synergized, catalyzed* (and same-family *orchestrated, championed, drove, amplified*) on the rewrite side. If the user wrote one, flag it and rewrite to a more specific verb anchored in the actual work.
**Cite:** audit/parts/heuristics.md "Banned-AI-default-verb list" net-new list; SPEC D-17-RR; PITFALLS §2.2 (verbatim *"Rewrites more abstract than the original"*); voice.md §11.1.

### H-S04 — Honest-scope beats fabricated-metric
**Rule:** Scope words (team size, project count, stakeholders navigated, customer surface) are honest signal even without a number. *"Led seven plus projects"* is scope, not metric, and that beats *"Increased user satisfaction by 30%"* when the 30% wasn't measured. Never fabricate a metric to fill the X in XYZ.
**Cite:** audit/parts/heuristics.md "Honest-scope beats fabricated-metric (R02 positive rule)" net-new list; SPEC D-16-RR; PITFALLS §2.1 (hallucinated metrics); STREAM_MINING_RESUME.md §C2–C3, §C10 (4tg1bPbOxus L437–450, L1019–1020); framework: XYZ failure mode (frameworks.md).

### H-S05 — Side-by-side rationale required
**Rule:** Every bullet rewrite shows original / rewrite / 1-sentence rationale. Never collapse to a clean rewrite with no original — the user can't audit the change, can't catch a fabricated metric, can't learn the move. The side-by-side IS the anti-fabrication mechanism.
**Cite:** audit/parts/heuristics.md "Side-by-side rationale required (no blind rewrites)" net-new list; SPEC D-15-RR; PITFALLS §2.4, §2.5; voice.md §9.2, §11.4.

---

## Scope claims & seniority calibration

These heuristics govern how much credit a bullet may claim, how role-family vocabulary locks in, and how the review reframes over- or under-claiming without accusation.

### H-S06 — Single-author-vs-team-win disclosure
**Rule:** When a bullet describes shipped work that was a team effort, name the contribution precisely. *"Owned the Auth and Billing component sets"* beats *"Owned the entire design system."* The fix is precision, not a different framework.
**Cite:** audit/parts/heuristics.md "Single-author-vs-team-win disclosure" net-new list; STREAM_MINING_RESUME.md §B1 (4tg1bPbOxus L762–765 verbatim Nate); FEATURES §1.7 ownership-precision; framework: Scope-Impact-Metric failure mode (frameworks.md).

### H-S07 — Role-family register lock (verb set per family)
**Rule:** Each role family licenses a different verb set. Product Designer leans toward *shipped, owned, drove, decided*; UX Researcher leans toward *recruited, ran, synthesized, recommended*; Design Engineer leans toward *built, integrated, refactored, deployed*; Lead/Manager leans toward *facilitated, hired, mentored, set standards*. Mixing families across bullets reads as positioning incoherence.
**Cite:** audit/parts/heuristics.md "Role-family register lock (verb set per family)" net-new list; SPEC D-19-RR (role-families presets); FEATURES §1.7 career-stage routing; STREAM_MINING_RESUME.md §E1–E8 (Theme E role-family-specific resume language).

### H-S08 — Stack-specificity over category (design-engineer)
**Rule:** For design-engineer and similar hybrid roles, name the stack — *React + Tailwind + Storybook with Figma tokens* — not the category *"design systems."* Category-only positioning is a copy-paste-test failure for technical roles.
**Cite:** audit/parts/heuristics.md "Stack-specificity over category (design-engineer)" net-new list; SPEC D-19-RR design-engineer.md preset; framework: copy-paste test failure (cross-ref H-S15); STREAM_MINING_RESUME.md §E3 (11zGHBSfaXc L1149–1151 — Tim on his own bullet density for technical-space roles).

### H-S09 — Calibration-not-accusation framing
**Rule:** Junior over-claim and senior under-claim are positioning misses, not character flaws. Frame as *"this bullet currently positions you at mid; if your target is senior, here's the move"* — never as *"you're inflating"* or *"you're underselling."* The candidate can act on positioning; they can't act on a character call.
**Cite:** audit/parts/heuristics.md "Calibration-not-accusation framing (junior over-claim / senior under-claim)" net-new list; PITFALLS §1.5 (verbatim calibration frame); STREAM_MINING_RESUME.md §D4–D7 (Dfmfpi82qAk L735–736, L773–774); voice.md §6 anti-roast hard rule.

### H-S10 — Reverse-chronological forcing function (senior)
**Rule:** Senior resumes default reverse-chronological with most-recent role bulleted fullest. A senior resume that buries a recent senior role beneath education or projects fails the 0–3s skim test. Education and projects sections move *down* as seniority climbs.
**Cite:** audit/parts/heuristics.md "Reverse-chronological forcing function (senior)" net-new list; STREAM_MINING_RESUME.md §H10–H11 (4tg1bPbOxus L1394–1400 — *"the immediate first thing I usually look at on resumes is the dates"*); FEATURES §1.6 section-order; framework: Skim-test tiers (frameworks.md).

---

## Section structure & ATS sanity

These heuristics govern the architecture of the resume page — section ordering, skills-section discipline, page-count defaults, and the ATS-vs-human framing that decides what goes where.

### H-S11 — Tool-list ceiling (skills section)
**Rule:** The skills section caps at roughly 8–12 named tools/methods, organized by relevance to the target role. A 30-tool skills section dilutes the keyword-density signal and reads as résumé-padding, not capability.
**Cite:** audit/parts/heuristics.md "Tool-list ceiling (skills section)" net-new list; STREAM_MINING_RESUME.md §H5 (4tg1bPbOxus L1342–1345 — Nate on de-emphasizing skills sections); SPEC D-21-RR (no keyword-stuffing); cross-ref portfolio-rx "One to five drivers, never more."

### H-S12 — Recent-tools-only (skills section recency cut)
**Rule:** Tools listed in the skills section must be tools the candidate has used in the last 2–3 years. Listing Photoshop alongside Figma and Framer dilutes recency signal and tells the recruiter the candidate either hasn't updated or is padding the list.
**Cite:** audit/parts/heuristics.md "Recent-tools-only (skills section recency cut)" net-new list; FEATURES §1.7 career-stage routing (recency calibration); cross-ref H-S11 tool-list ceiling.

### H-S13 — Education position by seniority
**Rule:** Recent grad → education near the top (it's the strongest signal). Mid → education below the most-recent role. Senior+ → education at the bottom or single-line. The position itself is a positioning act.
**Cite:** audit/parts/heuristics.md "Education position by seniority" net-new list; STREAM_MINING_RESUME.md §D10 (4tg1bPbOxus L1390 — *"if you are a recent graduate, then oftentimes the most impressive thing you have on your resume is the education"*); FEATURES §1.6 section-order.

### H-S14 — No-projects-section at senior (scope-coasting flag)
**Rule:** A standalone "Projects" section at senior+ tier reads as scope-coasting — surfacing side-projects to compensate for thin senior-role bullets. At senior, projects fold into the role bullet that produced them or get cut. Junior/early-mid: projects section fine.
**Cite:** audit/parts/heuristics.md "No-projects-section at senior (scope-coasting flag)" net-new list; FEATURES §1.7 career-stage routing; PITFALLS §1.6 senior under-claiming pattern.

### H-S15 — Section-header conventionality (ATS map)
**Rule:** Section headers map to ATS-recognized labels: *Experience* (or *Work Experience*), *Education*, *Skills*. Cute alternatives — *"Where I've Been," "Tools I Love," "My Story"* — break ATS parsing and don't earn a human upgrade either. Conventionality at the header level is non-negotiable; creativity goes in the bullet content.
**Cite:** audit/parts/heuristics.md "Section-header conventionality (ATS map: Experience / Education / Skills)" net-new list; PITFALLS §4.1 (narrow real ATS risks); STREAM_MINING_RESUME.md §F3 (11zGHBSfaXc L1237–1239 — Nate's ATS-definition spiel).

### H-S16 — One-page default at junior; two-page ceiling at senior
**Rule:** Junior → one page. Senior → up to two pages, both fully filled (no big empty chunks). Length is a function of evidence weight, not aspiration. A two-page junior resume reads as padding; a one-page senior resume reads as undersold.
**Cite:** audit/parts/heuristics.md "One-page default at junior; two-page ceiling at senior" net-new list; STREAM_MINING_RESUME.md §H1–H3 (4tg1bPbOxus L1324–1338 — *"I'm a firm believer in a two-page resume. As long as both pages are completely filled"*).

---

## Voice register & process discipline

These heuristics govern how the review behaves — what gets said, what gets cut, when the review pauses for input, and the ATS-theater traps that look like advice but aren't.

### H-S17 — Text-based PDF is fine (anti-ATS-theater)
**Rule:** A text-based PDF (exported from Figma, Docs, Pages — selectable text, not flattened-to-image) parses fine in modern ATS. The "ATS rejects all PDFs" myth is theater. Real ATS risks are scanned PDFs, text-in-images, merged-cell tables, and non-standard section headers — not PDFs as a format.
**Cite:** audit/parts/heuristics.md "Text-based PDF is fine (anti-ATS-theater)" net-new list; PITFALLS §4.1 (narrow real ATS risks); STREAM_MINING_RESUME.md §F7–F10 (4tg1bPbOxus L1297–1499 — Tim+Nate ATS uncertainty + tolerance discussion); SPEC D-21-RR.

### H-S18 — Write-for-the-hiring-manager (ATS follows)
**Rule:** Write the resume for the hiring design manager who'll read it; modern ATS follows naturally when bullets name actual tools, methods, and outcomes. Treating ATS as a separate optimization layer produces keyword-stuffed garbage that fails the human read.
**Cite:** audit/parts/heuristics.md "Write-for-the-hiring-manager (ATS follows)" net-new list; SPEC D-21-RR locked; PITFALLS §4.2–§4.3; STREAM_MINING_RESUME.md F11 (11zGHBSfaXc L1044–1047 — Nate on density without keyword-loading).

### H-S19 — Probe before draft
**Rule:** In brainstorm mode, ask before drafting. The probes (target role, scope, ownership, n) surface content the candidate has but hasn't written down. Drafting before probing produces generic bullets and risks fabricated metrics. The probe IS the draft scaffold.
**Cite:** audit/parts/heuristics.md "Probe before draft (brainstorm mode entry rule)" net-new list; STREAM_MINING_RESUME.md P-RES-01 through P-RES-15 (Bucket 6 distillation — resume-applicable probes); FEATURES §2.6 brainstorm-mode entry; voice.md §9 frameworks-by-name protocol.

### H-S20 — Summary line earns its place or gets cut
**Rule:** A summary section is either factual and specific (years + role-family + 1 differentiator) or it gets cut. If the summary survives the copy-paste test (could be pasted onto another designer's resume and still read as true), the line isn't earning its place — it's positioning anyone, which means it's positioning no one.
**Cite:** audit/parts/heuristics.md §Stream-mined H-S06 (copy-paste test, port); STREAM_MINING_RESUME.md §B5, §B9, §H6 (4tg1bPbOxus L1356–1370, 11zGHBSfaXc L1019–1022 — verbatim Nate copy-paste test); cross-ref portfolio-rx "Copy-paste test for genericness."

---

## Adding new heuristics (procedure)

Append-only. New heuristics arrive from two sources: (1) FEATURES / PITFALLS additions surfaced through ongoing stream review, and (2) Tim+Nate transcript mining where a phrase recurs across multiple streams. For (2), the mining-log.md (private, gitignored per D-17-RR) tracks recurrence; three independent appearances minimum before promotion. Each new heuristic gets an H-S## ID in next-available sequence (next is H-S21), a short noun-phrase name, a 1-line rule, and a citation that points at the audit appendix anchor and (where attributable) the STREAM_MINING_RESUME transcript ID. Never rewrite an existing heuristic in place — if framing genuinely changes, add a new heuristic and mark the old one with a "superseded by" note rather than deleting it. The IDs stay stable so cross-references from common-flags.md, frameworks.md, rubrics, and workflows don't shift.

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
