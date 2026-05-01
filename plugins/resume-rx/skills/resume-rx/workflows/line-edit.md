---
title: Line-edit — Resume Rx
plugin: resume-rx
covers: MODE-01, MODE-04 (line-edit detection branch), MODE-05, INPUT-01, INPUT-02, INPUT-03, INPUT-04, OUT-01
sources:
  - ../references/voice.md
  - ../references/frameworks.md
  - ../references/intake.md
  - ../references/common-flags.md
  - ../references/heuristics.md
  - ../references/rubric-junior.md
  - ../references/rubric-senior.md
  - ../gotchas.md
---

# Workflow: Line-edit

> No roasting: just collaboration and constructive feedback. The reviewee is in the call. Read every flag back through that lens — kindest plausible reading first, named choice not named person, cost framed in recruiter / hiring-manager terms, concrete rewrite handed back.

## When invoked

The routing layer (`../SKILL.md`, authored in P6) dispatches here when the input shape is "existing resume draft." This workflow is one of three modes — the other two are `brainstorm.md` (P4) and `draft-from-list.md` (P5). The router decides; this workflow runs the line-edit pass once selected.

**Detection signals (line-edit fires when any of these are true):**

- Multi-section resume body present — Experience + Education + Skills detected as labeled headings or clearly structured blocks.
- Bullet-list shape with **3 or more role blocks** — recognizable role/company/dates lines each followed by bullets.
- Explicit user phrase — *"review my resume," "edit this resume," "tighten my bullets," "line-edit this," "give me a marked-up version,"* or close variants.
- Resume-shaped paste / PDF / LinkedIn profile / Notion-or-GDoc resume — full-draft inputs route here by default per intake.md `mode_routing_hint == "line_edit"`.

**Detection signals that DEFER (route elsewhere):**

- Single bullet, single paragraph, or fragment with no role context → brainstorm or draft-from-list. Hand back to router with note: *"Sparse input — line-edit needs ≥3 role blocks. Routing to brainstorm/draft-from-list."*
- Raw achievement dump, no resume structure (no role headers, no dates) → draft-from-list (P5).
- User asks for a fresh resume from nothing → brainstorm (P4) or draft-from-list (P5).

**Explicit override (MODE-05).** When the user says any of *"use line-edit mode," "/line-edit," "line-edit this," "treat this as a line edit,"* line-edit runs even if the input shape is ambiguous. Document the override in the output header so the user knows the routing happened by request.

**Detection-checklist quick reference (for SKILL.md authoring in P6):**

| Input shape | Routes to |
|---|---|
| Multi-section resume body, ≥3 role blocks, paste / pdf / linkedin / notion / gdoc | line-edit (this workflow) |
| Single bullet OR single paragraph, no role context | brainstorm.md (P4) |
| Raw achievement dump, no resume structure (no role headers, no dates) | draft-from-list.md (P5) |
| Sparse LinkedIn profile (titles only, no descriptions) | brainstorm.md (P4) by default |
| Explicit phrase: *"line-edit this," "tighten my bullets," "review my resume"* | line-edit (this workflow) |
| Explicit phrase: *"help me brainstorm," "I'm stuck," "blank page"* | brainstorm.md (P4) |
| Explicit phrase: *"draft a resume from this list," "structure these wins"* | draft-from-list.md (P5) |
| MODE-05 override: *"use line-edit mode" / "/line-edit"* | line-edit (this workflow) regardless of shape |

## Inputs expected

A parsed `INTAKE_RESUME` object emitted by one of the recipes in `../references/intake.md`. The full schema is documented there. Line-edit consumes — never re-parses — the `INTAKE_RESUME`. The first procedural step validates the schema and requests re-intake if it's malformed.

The `INTAKE_RESUME.format` enum has six values, all supported here:

- `paste` — plain-text paste (INPUT-01)
- `pdf` — PDF read via the `Read` tool (INPUT-02)
- `linkedin_url` — LinkedIn public profile URL via `WebFetch` (INPUT-03)
- `linkedin_json` — LinkedIn JSON export, parsed directly (INPUT-03)
- `notion_url` — Notion published page via `WebFetch` (INPUT-04)
- `gdoc_url` — Google Doc public-view URL via `WebFetch` (INPUT-04)

Format-specific extraction is the intake recipe's job. Line-edit operates on the normalized `raw_text` field plus the metadata fields (`claimed_seniority`, `claimed_role_family`, `has_link`, `link_url`, `sensitive_flags`, `source_provenance`, `mode_routing_hint`).

## What to read first

Read in this order. Do not skip.

1. **`../references/voice.md`** — the writing register. Re-read §2 (register), §3 (pattern templates), §4 (drop list, including banned AI-default verbs), §6 (anti-roast hard rule + the four observable moves), §7 (sensitive-content carve-out), §9 (frameworks-by-name protocol — including §9.1 no-fab metrics, §9.2 side-by-side, §9.3 no-keyword-stuffing), §11 (net-new resume-domain rules — banned AI verbs, no-fab metrics, senior-bullet diagnostic, side-by-side, NDA carve-out, no-numeric-scores, no-keyword-stuffing, area-of-work labels), §12 (self-check), §14 (footer). Every flag in this workflow's output complies.

2. **`../references/rubric-junior.md` OR `../references/rubric-senior.md`** — pick one based on `claimed_seniority`:
   - `junior` or `mid` → `rubric-junior.md` (the mid calibration notes are folded inline at each criterion)
   - `senior` or `staff` → `rubric-senior.md` (the staff calibration notes are folded inline at each criterion)
   - `unknown` → emit ONE auto-clarity confirm (Step 1 below) and proceed on the answer
   Never load both rubrics. The branch is one-way.

3. **`../references/role-families/<family>.md`** — pick one based on `claimed_role_family`:
   - `product_designer` → `role-families/product-designer.md`
   - `ux_researcher` → `role-families/ux-researcher.md`
   - `design_engineer` → `role-families/design-engineer.md`
   - `design_lead_manager` → `role-families/design-lead-manager.md`
   - `unknown` → defer family-specific signals; flag absence as observable in rationale (*"role family unknown — using general rubric only"*). Do not invent a fifth preset (gotchas.md G12).

4. **`../references/common-flags.md`** — load R01 through R12. The full closed taxonomy. R-IDs are stable per LD-P2-05 / D-14; cite by exact ID.

5. **`../references/frameworks.md`** — the seven D-20 frameworks: **STAR**, **CAR**, **XYZ**, **R-A-S**, **Scope-Impact-Metric**, **What/How/Why**, **Skim-test tiers**. Cite by exact name verbatim, never paraphrase. Per voice.md §12 self-check, every review surfaces at least two by name.

6. **`../references/heuristics.md`** — the H-S## bias rules. Most relevant for line-edit: H-S01 (scope-noun-before-verb at senior), H-S02 (Why-How-What ordering), H-S03 (banned AI-default verbs), H-S04 (honest-scope beats fabricated-metric), H-S05 (side-by-side rationale required), H-S07 (role-family register lock), H-S09 (calibration-not-accusation), H-S10 (reverse-chronological at senior), H-S11 (tool-list ceiling), H-S15 (section-header conventionality), H-S17 (text-based PDF is fine), H-S18 (write-for-the-hiring-manager), H-S20 (summary line earns its place or gets cut). Cite sparingly — one or two per review at most.

7. **`../gotchas.md`** — the operational pitfalls G01..G14. Most load-bearing here: G05 (no numeric scores), G06 (no invented metrics), G07 (banned AI verbs), G08 (no JD-paste in v1), G09 (no .docx / visual export), G10 (no cover letter in v1), G11 (out-of-scope resume types), G12 (four role-family presets, no fifth), G13 (missing portfolio link is flag-only).

## Step-by-step procedure

### Step 1 — Validate `INTAKE_RESUME` and resolve missing seniority / role-family

**Schema validation.** Confirm the object has `raw_text` (non-empty), `format` (one of the six enum values), `source_provenance` (any string), `has_link` (boolean), `link_url` (string or null), `sensitive_flags` (array), `mode_routing_hint` (one of `line_edit`, `brainstorm`, `draft_from_list`, `unknown`). If any required field is missing or malformed, request re-intake: *"`INTAKE_RESUME` looks malformed — `<field>` is missing/wrong-shape. Re-run the intake recipe for `format: <X>` and hand back."* Do not attempt to recover by re-parsing inside this workflow (per LD-P3-06).

**Resolve `claimed_seniority`.** If `claimed_seniority` is one of `junior`, `mid`, `senior`, `staff`, route to the matching rubric (junior+mid → `rubric-junior.md`; senior+staff → `rubric-senior.md`) and continue to Step 2. If `claimed_seniority == "unknown"`, emit one auto-clarity confirm — single line, no multi-part question — per voice.md §3 and the rubric-junior / rubric-senior boundary discipline:

> Defaulting to the early-career rubric. If you're targeting a senior promotion or senior IC role, say so and we'll switch.

Proceed on the answer. If the user said something in `notes` or `raw_text` that resolves the question (*"I'm 6 years in, applying to senior roles" / "first job out of bootcamp"*), use that — don't ask again.

**Resolve `claimed_role_family`.** If `claimed_role_family` is one of the four enum values, load the matching `role-families/<family>.md` preset. If `claimed_role_family == "unknown"`, do not invent a fifth preset (gotchas.md G12). Either:

- Probe with one line: *"Is this resume targeting Product Designer / UX Researcher / Design Engineer / Design Lead-Manager? Closest fit is fine."*
- Or proceed without a family preset and flag the absence in the per-bullet rationale where relevant (*"role family unknown — using general rubric only; verb-set check skipped"*).

**Sensitive-content branch.** If `sensitive_flags` contains entries (`nda_mention`, `confidential_metric`, `gap`, `layoff`, `esl`, `employer_private_project` — or close variants), switch the register per voice.md §7 (sensitive-content carve-out) and §11.5 (NDA carve-out extension). For NDA-heavy work specifically, pivot bullets to the **process and decision-making** layer per the verbatim Tim+Nate framing — process is almost never bound by NDAs.

### Step 2 — Skim-test pass (anchor the Top-3)

Before any bullet-level work, run the **Skim-test tiers** framework against the whole resume. The framework (frameworks.md) defines three timed tiers:

- **0–3s — header read.** Name, role-targeting, current company / title, dates, portfolio URL visible? Per H-S15, section headers map to ATS-recognized labels (Experience / Education / Skills). Per `has_link` flag (intake.md / D-25): if `has_link == false`, flag R06 (missing or broken portfolio link) at this tier — do not WebFetch the URL (gotchas.md G13).
- **3–10s — most-recent role + top bullet.** Does the strongest signal live here? At senior+staff, this is where the `what changed because of you` diagnostic (voice.md §11.3, rubric-senior.md Criterion 1) gets applied to the lead bullet.
- **10–30s — bullet pull-through across the rest of the page.** Are there scope words, metrics, named outcomes, or is the resume a method inventory?

Surface what passes and fails at each tier. The tier results **anchor the Top-3** — if the resume fails 0–3s (header or section-order), the Top-3 weights toward header/summary/section-order fixes. If it passes 0–3s but fails 3–10s (recent-role bullets), the Top-3 weights toward the most-recent role's lead bullet. Bullet rewrites buried in older roles cannot compensate for a 0–3s failure.

Note observable structural problems here too: page-count mismatch (R03), tool-list noun salad in the skills section (R05), US-format violations like photo / DOB (R07).

### Step 3 — Bullet-level pass

For every bullet across every role:

1. **Quote verbatim.** Paste the bullet exactly as the user wrote it. Per voice.md §5 keep-list: quote the user's own copy. We do not paraphrase.
2. **Check against R01–R12** in `common-flags.md`. Multiple R-IDs can fire on one bullet — list all that apply. Quick reference for the closed taxonomy:
   - **R01** — activity bullet, no outcome
   - **R02** — metric fabrication risk, no honest signal
   - **R03** — length / format mismatch (page count, US-format)
   - **R04** — passive / weak verb (including AI-default-verb compensation)
   - **R05** — tool-list noun salad in skills section
   - **R06** — missing or broken portfolio link
   - **R07** — US-format violations (photo, DOB, marital status, references-line)
   - **R08** — "we" overuse, hiding individual contribution
   - **R09** — generic summary, wasted top-third
   - **R10** — seniority mismatch (junior over-claim or senior under-claim)
   - **R11** — design process over-narration (method inventory, no output)
   - **R12** — claiming team win solo (mirror of R08; "I" inflates contribution)
3. **Check against the seven frameworks** in `frameworks.md`:
   - **What/How/Why** — primary scaffold for resume bullets. Does the bullet lead with Why (impact), or is it What-first / activity-only? Flip to Why/How/What when impact is buried (Pair 10 in voice.md). Per Nate verbatim: *"if you follow a what-how-why approach, really hard to write a bad bullet."*
   - **STAR** — flag as misapplied if a four-clause STAR sits at bullet scope (Situation+Task usually implied by the role line). Useful as a thinking tool to recover the full arc, then compress.
   - **CAR** — when one-clause Context is genuinely doing work (NDA constraint, unusual team shape, regulated-industry surface). Generic Context clauses ("In a fast-paced startup environment") are worse than no Context — flag per the copy-paste test (voice.md Pair 2).
   - **XYZ** — when an honest hard metric exists. Never fabricate the X (D-16-RR / voice.md §9.1 / §11.2).
   - **R-A-S** — senior+staff bullets where leading with the result is honest.
   - **Scope-Impact-Metric** — senior+staff bullets where the scope is the headline signal (team size, ARR, surface area, customer base).
   - **Skim-test tiers** — ran in Step 2; do not re-run per bullet.
4. **Check role-family verb-set + scope vocabulary** (per H-S07). The active role-family preset licenses a specific verb set (Product Designer leans `shipped, owned, drove, decided`; UX Researcher leans `recruited, ran, synthesized, recommended`; Design Engineer leans `built, integrated, refactored, deployed`; Design Lead/Manager leans `facilitated, hired, mentored, set standards`). Verbs from a different family on this bullet read as positioning incoherence.
5. **Banned-AI-verb scrub (D-17-RR per LD-P3-10).** If the bullet contains *spearheaded, leveraged, synergized, catalyzed, orchestrated, championed, drove (no object), amplified (no metric)*, flag R04 (passive/weak verb — AI-default-verb compensation variant) and prepare to substitute. The rewrite must (a) swap to a verb from the active role-family preset's verb set, and (b) be at least as concrete as the original (voice.md §4 abstraction-regression guard). Cite *banned-AI-default verb list* by name in the rationale per voice.md §11.1.

If the bullet passes all checks, do not list it. The output is a flag list, not an exhaustive audit. A passing bullet is silence.

A bullet without a rewrite is a roast in disguise (voice.md §6). If a concrete rewrite cannot be produced, either drop the flag or mark the bullet *"needs more context — what was the result?"* and surface it as a probe.

**Section-level checks fired during the bullet pass.** Two R-IDs commonly surface at section scope rather than per-bullet — flag them here and roll into the per-bullet markup section under the relevant role / section block:

- **R09 (generic summary, wasted top-third)** — apply the **copy-paste test** (voice.md Pair 2, STREAM_MINING_RESUME.md §B5/§B9 verbatim Nate): could a different designer copy-paste this summary onto their resume and have it still read as true? If yes, the line is positioning anyone, which means it's positioning no one. Per H-S20: a summary either earns its place (factual + specific — years + role-family + 1 differentiator) or it gets cut. Don't try to "make it stronger" while keeping the subjective register; the fix is binary.
- **R08 ("we" overuse, hiding individual contribution)** — fires on bullets that default to *"we redesigned"* / *"the team launched"* / passive ownership phrasing. Mirror failure of R12 (claiming team win solo); the diagnostic is the same — ownership precision is missing. Apply the **ownership audit** probe (P-RES-03, voice.md): *"What did you specifically own here? Where in this bullet does the contribution become precisely yours, vs the team's?"* Use *"we"* only where it's literally accurate — multi-author work where the user's specific piece is named separately.

### Step 4 — Concrete rewrite per flagged bullet (D-15-RR side-by-side)

For each flagged bullet, produce a rewrite that lands in the **side-by-side format** per LD-P3-05 / D-15-RR / voice.md §9.2. Original quoted verbatim → Rewrite (concrete) → Rationale (1 sentence). Never collapse to a clean rewrite without the original — the side-by-side IS the anti-fabrication mechanism (voice.md §11.4, PITFALLS §2.4–§2.5).

**No-fabricated-metrics ladder (D-16-RR per LD-P3-09 — HARD rule, not style preference).** When a bullet is metric-absent, the rewrite must follow the three-options ladder, in order of preference:

1. **Probe in rationale** — surface the absence honestly: *"Bullet has no measurable signal. If you have a metric (drop-off %, n=, time-to-ship, adoption count), this is the slot for it. If not, scope (team size, surface area, timeline) is honest signal."* This is the default move per voice.md §9.1 escalation chain.
2. **Restructure to a non-numeric outcome** — pivot the rewrite onto a process / artifact / decision honestly. *"Killed by leadership pivot — what we learned: should have stress-tested executive alignment before sketching."* Or *"Pattern adopted by two adjacent teams as the default for new flows."* Process and decision-making are almost never bound by NDAs (voice.md §11.5 NDA carve-out).
3. **`<!-- METRIC GAP: needs source data -->` marker** — only if neither probe nor restructure works. The marker is visible to the user and signals: real bullet, real work, but the data to write the rewrite isn't here. Do not paper over with an invented number.

**Banned AI-verb substitution per LD-P3-10.** When the original contained a banned verb, the rewrite swaps to a verb from the active role-family preset's licensed verb set (H-S07). Rationale cites the banned-AI-default verb list by name (voice.md §11.1). Example: original *"Spearheaded the design system rollout"* → rewrite (Product Designer family) *"Shipped the design system across 3 product teams; 14 components adopted in the first quarter."* The rewrite is at least as concrete as the original (voice.md §4 abstraction-regression guard).

**Sensitive-content rewrite register.** If `sensitive_flags` includes `nda_mention` / `confidential_metric` / employer-private project signal, pivot to the process-and-decision-making layer per voice.md §11.5. Bullet form: scope description + role + decision + observable behavior change, with the confidential metric explicitly held back. Frame as a feature, not a constraint. Layoff / gap / ESL flags trigger voice.md §7 register — name the choice not the person, give explicit permission around privacy, give two concrete framings.

### Step 5 — Top-3 selection

Synthesize the **Top-3 highest-leverage** issues from Steps 2–4. Highest-leverage means **biggest skim-test improvement, not biggest critique pile**. Bias hard toward header / summary / section-order fixes when those fail the 0–3s tier. Bias toward the most-recent-role lead bullet when the resume fails 3–10s.

**Top-3 selection rules:**

1. If the skim-test failed at 0–3s (header / section-order / portfolio link), the Top-3 weights heavily toward header fixes. Nothing downstream matters until the recruiter stays past the first scan.
2. If two flags want the same Top-3 slot — common case: a header skim-test fix (#1) and the strongest-bullet R01 rewrite (#1) both want position 1 — the header / skim-test fix wins for junior; the seniority-calibration / scope-language fix wins for senior+staff (rubric-senior.md Top-3 priority order).
3. Each Top-3 entry uses the **area-of-work label** template per voice.md §3 / §11.8. Resume-domain labels: *bullet impact, scope claims, role-family alignment, seniority calibration, summary line, ATS-readability, positioning, housekeeping*. Drop *layout* and *visual craft* — resume-rx is content-only per D-15-RR. Keep *storytelling* only when it actually applies (rare on resumes).
4. Variable count: 1–3, not always 3 (voice.md §3 / Pattern C). If only two priorities dominate, list two. If a single priority dominates everything (often ATS-parseability), list one and say so explicitly. Do not manufacture a third.
5. Each Top-3 entry: area-of-work label + 1-line problem + the single bullet rewrite (or move) that captures it. Quote verbatim where possible.

### Step 6 — Output assembly

Use the output template below (LD-P3-05). Fill only sections that have content; do not emit empty headers. Order is fixed; section content is not.

Append the verbatim D-16-RR Tim+Nate footer at the end. Verbatim, no rewording, no softening (voice.md §14, gotchas.md footer).

Run the voice.md §12 self-check before emitting (verbatim list reproduced under "Pre-emit self-check" below). If any check fails, fix or drop the offending content.

## Three worked examples

These illustrate the rewrite discipline. Each: original verbatim + rewrite + rationale (1 sentence) + R-ID + framework cite + voice rule cite.

### Example 1 — Junior over-claim bullet

**Context.** `claimed_seniority: junior`, `claimed_role_family: product_designer`. The resume is from a 1-year-out designer applying to early-career roles.

**Original (verbatim quote):**
> "Defined the design strategy for our 0-to-1 product, increasing user satisfaction by 45%."

**Rewrite:**
> "Co-designed the v1 onboarding for our 0-to-1 product alongside the lead designer; the team killed the multi-step variant after the first usability round and shipped the single-screen flow that's still in production."

**Rationale (1 sentence).** Flagged R02 (metric fabrication risk — round 45% on un-instrumented student-stage work) and R10 (seniority mismatch — *defined the strategy* is staff-register on a junior resume); rewrite applies **What/How/Why** with the Why as honest non-outcome (the team killed the variant) and substitutes *defined* with *co-designed* per voice.md §11.1 banned-AI-default verb register and the calibration-not-accusation framing in voice.md Pair 7.

### Example 2 — Senior under-claim bullet

**Context.** `claimed_seniority: senior`, `claimed_role_family: design_lead_manager`. The resume is from a 7-year designer in a tech-lead role; the bullet hides leadership scope behind craft-verb register.

**Original (verbatim quote):**
> "Led the design system rollout across three product teams."

**Rewrite:**
> "Cut design-token drift across 3 product teams (12 designers, 4 PMs) by standing up the design system; 14 components shipped to prod and the team's review-cadence rubric was adopted by the broader design org."

**Rationale (1 sentence).** Flagged R12 (claiming team win solo — *led* without naming the contribution boundary against the broader design org) and R11 (process over-narration — *the design system rollout* is method label, not outcome); rewrite applies **Scope-Impact-Metric** with senior-grade scope (3 teams + 12 designers + 4 PMs), surfaces the second-order effect (review-cadence rubric adopted org-wide) per voice.md §11.3 *what changes because of you* idiom, and uses calibration-not-accusation framing per H-S09.

### Example 3 — Banned-AI-verb scrub

**Context.** `claimed_seniority: mid`, `claimed_role_family: design_engineer`. The bullet uses *spearheaded* and *leveraged* — the LLM-rewrite tells.

**Original (verbatim quote):**
> "Spearheaded the migration of legacy design tokens, leveraging cross-functional partnerships to deliver a robust scalable solution."

**Rewrite:**
> "Migrated the legacy design tokens to the new Tailwind + Storybook stack; partnered with 4 frontend engineers and 1 PM, shipped behind a feature flag, and the new tokens replaced the legacy CSS vars across 3 product surfaces."

**Rationale (1 sentence).** Flagged R04 (passive/weak verb — AI-default-verb compensation: *spearheaded* + *leveraged* + *robust scalable*) per the banned-AI-default verb list named verbatim in voice.md §11.1; rewrite substitutes Design Engineer family verbs (*migrated, partnered, shipped*) per H-S07 role-family register lock and applies **What/How/Why** with the How clause carrying stack specificity (Tailwind + Storybook) per H-S08 stack-specificity-over-category — the rewrite is at least as concrete as the original per voice.md §4 abstraction-regression guard.

## Output template (OUT-01 / D-15-RR)

```
## <Candidate name or "your resume"> — Line-edit review
<date> · <claimed_seniority + claimed_role_family> · <1-line scope summary>
<one-line note if MODE-05 override fired or if seniority / role-family was unknown>

### Top 3 issues

1. **<area-of-work label>** — <1-line problem>. Rewrite: <single bullet, or "Move <X> to <Y>" for section-order fixes>.
2. **<area-of-work label>** — <1-line problem>. Rewrite: <single bullet>.
3. **<area-of-work label>** — <1-line problem>. Rewrite: <single bullet>.

(Variable count 1–3 per voice.md §3 / Pattern C — list 2 if two priorities dominate; list 1 if a single priority dominates everything. Do not manufacture a third.)

### Per-bullet markup

#### <Role title — Company, dates>

**Original:** "<verbatim quote of the user's bullet>"
**Rewrite:** "<concrete rewrite using the right framework, honoring D-16-RR no-fab-metrics>"
**Rationale:** <1 sentence citing R-ID(s) + framework name + voice rule by name>

(repeat per flagged bullet across all roles. Skip bullets that pass all checks. If a role's bullets all pass, note "<Role>: bullets hold — no flags." once and move on.)

### Skim-test verdict

- **0–3s — header read:** PASS | FAIL — <what lands or doesn't, naming the failing element>
- **3–10s — most-recent role + top bullet:** PASS | FAIL — <...>
- **10–30s — bullet pull-through:** PASS | FAIL — <...>

### Frameworks applied

<comma-separated list of frameworks named verbatim in this review — minimum 2 per voice.md §12 self-check>

### Flags applied

<comma-separated R-IDs surfaced — junior reviews typically hit 4–7 R-IDs; senior reviews fewer>

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
```

### Output template notes

- The `<Candidate name>` slot uses the name from the resume header if present in `raw_text`. If anonymous, use *"your resume"* — do not ask for the name; it's not load-bearing.
- The `<claimed_seniority + claimed_role_family>` line uses the resolved values from Step 1. If either was unknown and resolved by auto-clarity confirm, surface that ("Defaulted to junior rubric per single-line confirm").
- The Top-3 list is mandatory but variable-count (1–3, not always 3). Each item uses the area-of-work label template, never section names like *"Improve experience section."*
- Per-bullet markup blocks are skipped for passing bullets. Silence is the pass signal.
- Skim-test verdict is mandatory — three lines, pass/fail at each tier with the failing element named.
- Frameworks-applied and flags-applied trailers are voice-discipline anchors per voice.md §12 — at least 2 frameworks, R-IDs by exact ID.
- Footer is verbatim D-16-RR. Non-removable, no rewording.

## Pre-emit self-check (verbatim from voice.md §12)

Run before emit. Fix or drop offending content.

- [ ] Every flag has a rewrite. (No critique without a fix.)
- [ ] Every flag quotes the user's actual bullet or names the specific section.
- [ ] At least 2 frameworks are surfaced by name (per the frameworks-by-name protocol).
- [ ] No phrases from the drop list (voice.md §4), including the banned AI-default verbs (§4 / §11.1).
- [ ] No fabricated metrics — every number on the rewrite side traces back to the user's input or is explicitly marked as a probe / scope / prototyped (§9.1, §11.2). When metric is absent, the three-options ladder fired (probe / restructure / `<!-- METRIC GAP -->`).
- [ ] Rewrites are at least as concrete as the original — no abstraction regression (§4, §11.1).
- [ ] Side-by-side format: Original / Rewrite / 1-sentence Rationale per bullet (§9.2, §11.4). Never collapsed to a clean rewrite without the original.
- [ ] Top-3 fixes use the resume-domain area-of-work template (§3 / §11.8). Variable count 1–3 — no manufactured third.
- [ ] Long flag blocks end with the check-in pivot (Pair 13): *"How are you feeling about that direction? Push back if it's off."*
- [ ] Any verdict-word ("wrong," "bad," "ugly," "gross") that slips in gets walked back on the page (Pair 14) — not silently smoothed.
- [ ] No numeric scores, grades, or meters anywhere in the output (§4, §11.6 / D-23 / gotchas.md G05).
- [ ] No keyword-stuffing advice — write for the hiring design manager; modern ATS follows (§9.3, §11.7 / D-21-RR).
- [ ] If sensitive content present (gaps, layoffs, ESL, NDA), auto-clarity register applied (§7, §11.5).
- [ ] If `Tim says:` / `Nate says:` used, each adds a real second angle (not rephrasing). Callouts authored MANUALLY per D-M2-02 — never generated.
- [ ] Output ends with the verbatim D-16-RR footer.

If a review fails any check, fix or drop the offending flag before emitting.

## What this workflow does NOT do

Set expectations. People will ask for these and v1 doesn't handle them.

- **Does not invent metrics** (D-16-RR / voice.md §9.1 / §11.2 / gotchas.md G06). Hard rule. Three-options ladder per LD-P3-09: probe / restructure / `<!-- METRIC GAP -->`. Never a fabricated number.
- **Does not assign numeric scores, grades, or meters** (D-23 / voice.md §11.6 / gotchas.md G05). No "resume score: 72/100," no "ATS-readiness: 4/5," no bullet-strength meter. Resume.io / Rezi-style grading is the failure mode this rule prevents.
- **Does not stuff ATS keywords** (D-21-RR / voice.md §9.3 / §11.7 / gotchas.md G04). Write for the hiring design manager; modern ATS follows. Keyword inclusion only via honest bullet rewrites that name actual tools and methods used. No "add these words" list at the bottom, no hidden-text trick.
- **Does not paste-tailor to a JD** (gotchas.md G08, deferred to v1.1+). If a user provides a JD, surface the deferral: *"JD-paste tailoring is v2 — for now I'll review the resume on its own merits, and you can use the role-family preset closest to the target."* Do not silently absorb the JD.
- **Does not export .docx or render visual layouts** (gotchas.md G09, deferred to v2). Output ships as side-by-side bullet rewrites against the existing draft. Visual layout is the user's design tooling's job.
- **Does not write cover letters** (gotchas.md G10, deferred). Cover-letter generation is a different content type with different conventions; resume-rx covers the resume artifact only.
- **Does not WebFetch portfolio links** (D-25 / gotchas.md G13, deferred to v1.1+). v1 is detect-and-warn only — `has_link == false` from intake fires R06 as a flag without live verification.
- **Does not invent a fifth role-family preset** (D-19-RR / gotchas.md G12). Hybrid roles (content designer, design technologist, service designer) route to the closest of the four presets with one inline note acknowledging the call.
- **Does not apply the rubric to out-of-scope resume types** (gotchas.md G11). Academic CVs, federal/government resumes, international CVs requiring photo/DOB, non-designer resumes (PM, eng, marketing) — surface the scope mismatch and decline rather than forcing a fit.
- **Does not generate `Tim says:` / `Nate says:` callouts** (voice.md §8 / D-M2-02). Default to "we." Callouts are authored MANUALLY by Tim and Nate; never fabricated by the model.

## Forbidden moves (specific to line-edit reviews)

- **Generic "your bullets could be stronger" feedback.** Every flag is bullet-specific. If we can't quote the bullet, we can't flag it (voice.md Pair 1).
- **Drop-list phrases.** *"I noticed," "you might want to," "consider," "perhaps," "it would be helpful to."* Banned per voice.md §4. None appear in the output.
- **Any flag without a rewrite.** A flag without a rewrite is a roast in disguise (voice.md §6). VOICE-04 mandates rewrites.
- **Skipping the bullet-level pass and going straight to section-level critique.** Section-level is the supporting layer; bullet-level is load-bearing.
- **Loading both rubrics.** rubric-junior.md and rubric-senior.md never load together. The career-stage branch is one-way (rubric-senior.md scope discipline).
- **Restating what the resume says.** Critique what's there; don't summarize it (voice.md §4).
- **Sycophantic openers.** *"Great resume overall," "There's a lot of strong stuff here."* Never. Lead with the most useful thing (voice.md Pair 1).

## What goes wrong (failure modes + recovery)

- **Bullet-pass produces 30+ rewrites.** Curate to the 8–12 highest-leverage — bullets that bury the most signal, bullets in the most-recent role, bullets that fire multiple R-IDs. Document in output: *"This was a curation pass — flagging the highest-leverage bullets. The rest of the resume has similar opportunities; we surfaced the patterns to apply across the rest."*

- **Resume is excellent and there's not much to flag.** Apply voice.md Pair 11 — rank against population: *"This resume is in the top 10% of what we see on stream. Two-three notes that would push it further:"* Mark them as nits. Give permission to ignore. Do not pad with weak flags to hit a quota.

- **User has no measurable outcomes for any role.** Common in NDA-heavy senior, government, regulated industries. Apply the senior rubric "scope without metrics" guidance — focus on scope verbs, scope nouns (team size, eng partner ratio, customer base), time horizon, cross-org reach. Honest scope language beats fake numbers (R02 + voice.md §9.1 logic).

- **User submitted an out-of-scope artifact** — academic CV, federal resume, international CV with photo/DOB, non-designer resume. Per gotchas.md G11: surface the scope mismatch and decline rather than forcing the rubric onto the wrong artifact. Do not run the line-edit on a forced fit.

- **`INTAKE_RESUME` arrived without `claimed_seniority` AND without `claimed_role_family`.** Single-line auto-clarity confirm covers seniority (Step 1). For role-family unknown: probe with one line OR proceed without family preset and flag the absence in rationale. Two questions in two single-line confirms is acceptable; never three (voice.md single-confirmation rule).

- **Two flags want the same Top-3 slot.** Pick the one with higher skim-test leverage. Header / skim-test fix wins for junior. Seniority-calibration / scope-language fix wins for senior+staff. The bullet rewrite drops to position 2 or 3.

- **The user pasted a JD alongside the resume.** Per gotchas.md G08: surface the v1 deferral. Do not silently absorb the JD. Run line-edit on the resume; if the user names a target role, route to the closest role-family preset and proceed without keyword-matching.

- **`has_link == false`** (no portfolio link detected). Fire R06 at the 0–3s skim-test tier. Do NOT WebFetch the URL — v1 is flag-only per D-25 / gotchas.md G13.

## Heuristics in play (cite sparingly, one or two per review)

Per voice.md §12 self-check the review surfaces at least 2 frameworks by name. Heuristics are the second layer — they bias the lens. Cite by name only when the rule adds a real second angle (heuristics.md introduction). The most load-bearing for line-edit:

- **H-S01 (scope-noun-before-verb at senior+).** Lead the bullet with the scope noun, then the verb, then the metric. Verb-only bullets read mid regardless of header title.
- **H-S02 (Why-How-What ordering).** The corpus-load-bearing scaffold. Most-impressive-thing first because that's all the recruiter skims.
- **H-S05 (side-by-side rationale required).** The side-by-side IS the anti-fabrication mechanism — never collapse to a clean rewrite without the original.
- **H-S07 (role-family register lock).** Verb sets per family; mixing families across bullets reads as positioning incoherence.
- **H-S09 (calibration-not-accusation).** Junior over-claim and senior under-claim are positioning misses, not character flaws.
- **H-S11 (tool-list ceiling).** Skills section caps at roughly 8–12 tools. R05 fires at higher counts.
- **H-S15 (section-header conventionality).** Headers map to ATS-recognized labels: Experience / Education / Skills. Cute alternatives break ATS parsing without earning a human upgrade.
- **H-S17 (text-based PDF is fine, anti-ATS-theater).** Do not coach designers to abandon PDF as a content format.
- **H-S18 (write-for-the-hiring-manager, ATS follows).** No two-pass advice. The hiring manager is the audience; modern ATS follows.
- **H-S20 (summary line earns its place or gets cut).** Apply the copy-paste test from voice.md Pair 2.

Over-citing heuristics degrades the voice. One or two per review is the rule.

## Edge cases the workflow handles inline

These shapes recur. Handle them inside the line-edit pass rather than punting back to the router.

- **`format == "linkedin_url"` or `"linkedin_json"` with sparse profile.** LinkedIn profiles often have role titles + dates + company but no descriptions — the candidate filled out the structural shell and stopped. Per intake.md the recipe sets `mode_routing_hint: "brainstorm"` in this case, but if the user explicitly requested line-edit (MODE-05 override) and the profile is sparse, run line-edit on what's there and surface the absence as a Top-3 priority: *"role descriptions empty across most positions — line-edit can sharpen what's written, but the highest-leverage move is to fill in two to three bullets per role first. Want to brainstorm those?"* Do not invent role descriptions.

- **`format == "pdf"` with a scanned (image-only) PDF.** The intake recipe should have caught this and asked for the source doc. If somehow a `raw_text` lands here that's empty or near-empty (under ~50 words), abort the line-edit and request re-intake: *"`INTAKE_RESUME.raw_text` is empty / near-empty — likely a scanned-image PDF that the intake recipe couldn't extract text from. Ask the user to share the source doc or paste the text directly."*

- **`format == "paste"` with mixed content (resume + portfolio case study + cover letter draft).** Per gotchas.md G10 / G11: line-edit on the resume content only. Surface the scope: *"Pasted content includes a case study and what looks like a cover letter draft — line-edit covers the resume portion only. Cover letters are out of scope in v1; case studies route to portfolio-rx."* Run line-edit on whatever resume-shape content is present.

- **Layoff / sabbatical / gap signal in `sensitive_flags`.** Apply voice.md §7 carve-out. Lead with the verbatim Tim warmth-script when a layoff is disclosed: *"Our heart hurts with you for layoffs which are extremely tricky and come out of nowhere and are catastrophic in nature."* Then proceed normally. Do not dwell. For gap framing: voice.md Pair 8 verbatim — own the sabbatical as a sabbatical; do not fake freelance.

- **Career switcher with no prior design titles.** Per rubric-junior.md Archetype B: the bullets need transferable-skill framing. Don't critique the prior career as "off-topic" — apply What/How/Why to the prior bullets (lead with Why/impact, not What/activity) and surface the transferable signal. Voice.md Pair 2 application to non-design bullets carries.

- **Bullets pasted with no role context.** The user pasted bullets only — no company, no dates, no title. Run the bullet-level pass on what's there, skip the section-coherence pass, note the missing context: *"Reviewing bullets in isolation. Once role context is in, run the section coherence pass — recent-role thinness and reverse-chronological signal can't be checked here."* Do not invent context.

- **`claimed_seniority == "mid"` with target-role signal indicating senior promotion.** Per the rubric-junior boundary discipline (LD-P3-07 / D-18): the boundary is target role, not years-of-experience. If the user says they're applying to senior IC or staff promotion-track roles, route to rubric-senior.md even though `claimed_seniority` arrived as `mid`. Surface the routing call: *"Routing to senior rubric per stated target role."*

- **Two role-families plausible.** The user is a hybrid (design technologist with research methods, design lead with hands-on IC craft). Per gotchas.md G12: pick the closest of the four presets — do not invent a fifth — and surface the call: *"Routing to design-engineer.md preset; the design-systems lead role you describe leans IC-technical at this seniority. If your target is more people-track, switch to design-lead-manager.md."*

## How this workflow is composed

Called directly by `../SKILL.md` routing (P6) when:

- `mode == line_edit`, OR
- `mode == auto` AND `mode_routing_hint == "line_edit"` from intake.md, AND no explicit override to brainstorm or draft-from-list

Cross-mode handoff: brainstorm.md (P4) and draft-from-list.md (P5) consume `INTAKE_RESUME` from the same intake recipes. They do not call line-edit; they're peers in the routing layer. If a brainstorm session ends in draft bullets that the user then wants line-edited, the user re-invokes — the workflows are not pipelined silently.

The footer is appended once per emit at the end of this workflow's output. No multi-workflow composition in v1.

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
