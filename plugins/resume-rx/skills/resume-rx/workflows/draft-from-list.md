---
title: Draft-from-list — Resume Rx
plugin: resume-rx
covers: MODE-03, MODE-04 (draft-from-list detection branch — closes MODE-04 across P3+P4+P5), OUT-03
sources:
  - ../references/voice.md
  - ../references/frameworks.md
  - ../references/heuristics.md
  - ../references/intake.md
  - ../references/rubric-junior.md
  - ../references/rubric-senior.md
  - ../references/role-families/<family>.md
  - ../references/common-flags.md
  - ../gotchas.md
---

# Workflow: Draft-from-list

> No roasting: just collaboration and constructive feedback. The reviewee is in the call. The user dumped a list of achievements because they don't have a resume yet — meet them there. We parse honestly. We never invent metrics. We never invent education. We never invent a Skills section out of thin air. We end with a four-section markdown resume the user can paste into their tooling, with `<!-- SECTION GAP -->` markers wherever the source list didn't carry the data.

## When invoked

The routing layer (`../SKILL.md`, authored in P6) dispatches here when the input shape is "unstructured list of achievements / brain-dump." This workflow is one of three modes — the other two are `line-edit.md` (P3) and `brainstorm.md` (P4). The router decides; this workflow runs the draft-from-list pass once selected. With P3 (line-edit), P4 (brainstorm), and this workflow (P5) all shipping detection signals, MODE-04 is fully covered for v1 — P6 SKILL.md routing table is the final aggregator.

**Detection signals (draft-from-list fires when any of these are true):**

- Raw bullet-list or notes paste — multiple lines, structural shape of "things I've done" without role-block boundaries (no labeled `Experience` / `Education` / `Skills` headers, no clear role/company/dates rows).
- Brain-dump or stream-of-consciousness paste — *"here's everything I worked on at [company], plus the freelance gigs, plus the bootcamp stuff"* — long-form prose or fragmented lines mixing roles, projects, tools, schooling.
- INTAKE_RESUME emits `mode_routing_hint: "draft_from_list"` from intake.md (raw achievement dump detected).
- Explicit user phrases — *"draft my resume from these notes," "turn this list into a resume," "structure these achievements," "build me a resume from this dump," "I have all this stuff but no resume yet"* — or close variants.
- MODE-05 explicit override — *"use draft-from-list mode," "/draft-from-list."*

**Detection signals that DEFER (route elsewhere):**

- Multi-section resume body present — Experience + Education + Skills detected as labeled headings with ≥3 role blocks → `line-edit.md` (P3). Hand back: *"You've got a draft here that's better suited for line-edit. Want me to switch?"*
- Empty / near-empty input (under ~50 words), single bullet, single paragraph, blank-page signal → `brainstorm.md` (P4). Hand back: *"This is too thin to draft from — we need to surface content first. Want to switch to brainstorm?"*
- A single draft bullet the user wants tightened → `line-edit.md` (P3).

**Explicit override (MODE-05).** When the user says any of *"use draft-from-list mode," "/draft-from-list," "draft my resume from this list,"* draft-from-list runs even if the input shape is ambiguous. Document the override in the output header so the user knows the routing happened by request.

**Detection-checklist quick reference (for SKILL.md authoring in P6):**

| Input shape | Routes to |
|---|---|
| Multi-section resume body, ≥3 role blocks, paste / pdf / linkedin / notion / gdoc | line-edit.md (P3) |
| Empty / near-empty / single paragraph / blank-page signal | brainstorm.md (P4) |
| Raw achievement dump, no resume structure (no role headers, no dates, just dumped lines) | draft-from-list (this workflow) |
| Brain-dump or stream-of-consciousness "here's what I've done" | draft-from-list (this workflow) |
| Explicit phrase: *"draft a resume from this list," "structure these wins," "turn this into a resume"* | draft-from-list (this workflow) |
| Explicit phrase: *"line-edit this," "tighten my bullets"* | line-edit.md (P3) |
| Explicit phrase: *"help me brainstorm," "I'm stuck"* | brainstorm.md (P4) |
| MODE-05 override: *"use draft-from-list mode" / "/draft-from-list"* | draft-from-list (this workflow) regardless of shape |

## Inputs expected

A parsed `INTAKE_RESUME` object emitted by one of the recipes in `../references/intake.md`. The full schema is documented there. For draft-from-list, the load-bearing fields are:

- `raw_text` — the unstructured list / brain-dump itself. Must be non-empty (sparse → brainstorm). Must NOT have multi-section resume body shape (full draft → line-edit).
- `format` — any of the six enum values (`paste` is most common for draft-from-list; LinkedIn / PDF / Notion / GDoc inputs typically arrive resume-shaped and route to line-edit instead).
- `claimed_seniority` — `junior | mid | senior | staff | unknown`. If `unknown`, Step 2 fires a single-line auto-clarity confirm.
- `claimed_role_family` — `product_designer | ux_researcher | design_engineer | design_lead_manager | unknown`. If `unknown`, Step 2 probes once.
- `mode_routing_hint` — should be `"draft_from_list"` if the intake recipe routed here automatically; `"unknown"` if MODE-05 override fired on ambiguous input.
- `sensitive_flags` — if present (`gap`, `layoff`, `nda_mention`, `confidential_metric`, `esl`, `employer_private_project`), apply voice.md §7 carve-out from synthesis.
- `source_provenance` — free-form provenance string (used in output header for traceability).

Draft-from-list consumes — never re-parses — the `INTAKE_RESUME`. The first procedural step validates the schema and requests re-intake if it's malformed (per LD-P3-06 pattern, applied here).

## What to read first

Read in this order. Do not skip.

1. **`../references/voice.md`** — the writing register. Re-read §2 (register / Friday-stream voice-memo direct), §3 (pattern templates), §4 (drop list — banned hedges and AI-default verbs), §6 (anti-roast hard rule), §7 (sensitive-content carve-out — applies to synthesis when `sensitive_flags` present), §9.1 (no-fabricated-metrics rule — load-bearing for synthesis), §11.1 (banned AI-default verb list — never synthesize bullets that contain them), §11.2 (no-fab-metrics again, hard rule), §11.3 (senior-bullet diagnostic — *what changes because of you?*), §11.6 (no-numeric-scores), §11.7 (no-keyword-stuffing — D-21-RR), §11.8 (resume-domain area-of-work labels), §12 (self-check), §14 (footer). Every synthesized bullet, every section, every line of the output complies.

2. **`../references/frameworks.md`** — the seven D-20 frameworks: **STAR**, **CAR**, **XYZ**, **R-A-S**, **Scope-Impact-Metric**, **What/How/Why**, **Skim-test tiers**. Cite by exact name verbatim, never paraphrase. **What/How/Why is the synthesis default** (corpus-load-bearing, 13/23 transcripts) — flip to other frameworks only when the bullet shape calls for it. Skim-test tiers is the section-order diagnostic — apply at output assembly to verify the strongest signal leads.

3. **`../references/heuristics.md`** — the H-S## bias rules. Most relevant for draft-from-list:
   - **H-S19 (probe before draft)** — sparse sections trigger probe-back-to-brainstorm rather than fabrication.
   - **H-S20 (summary line earns its place or gets cut)** — the most-fabricated-prone surface; binary discipline.
   - **H-S04 (honest scope beats fabricated metric)** — synthesis rule.
   - **H-S07 (role-family register lock)** — verb sets per family at synthesis.
   - **H-S10 (reverse-chronological forcing function)** — Experience-section ordering.
   - **H-S11 (tool-list ceiling)** — Skills section caps at ≤8 per group.
   - **H-S13 (education position by seniority)** — junior top-half, senior footer.
   - **H-S15 (section-header conventionality)** — Summary / Experience / Skills / Education only; no cute alternatives.
   Cite sparingly — one or two heuristics per draft at most.

4. **`../references/rubric-junior.md` OR `../references/rubric-senior.md`** — pick one based on `claimed_seniority`:
   - `junior` or `mid` → `rubric-junior.md` (mid calibration notes folded inline at each criterion)
   - `senior` or `staff` → `rubric-senior.md` (staff calibration notes folded inline at each criterion)
   - `unknown` → emit ONE auto-clarity confirm (Step 2 below) and proceed on the answer.
   Never load both rubrics. The branch is one-way.

5. **`../references/role-families/<family>.md`** — pick one based on `claimed_role_family`:
   - `product_designer` → `role-families/product-designer.md`
   - `ux_researcher` → `role-families/ux-researcher.md`
   - `design_engineer` → `role-families/design-engineer.md`
   - `design_lead_manager` → `role-families/design-lead-manager.md`
   - `unknown` → defer family-specific signals; probe once before synthesis. Do not invent a fifth preset (gotchas.md G12).

6. **`../references/intake.md`** — for the `INTAKE_RESUME` schema definition and the `mode_routing_hint` semantics. Do not re-parse the input here; if intake misrouted, hand back per Step 1.

7. **`../gotchas.md`** — operational pitfalls. Most load-bearing here: **G05** (no numeric scores), **G06** (no invented metrics — applied at every synthesized bullet), **G07** (banned AI verbs in any synthesized bullet), **G08** (no JD-paste tailoring), **G09** (no .docx export), **G10** (no cover letter), **G11** (out-of-scope resume types — academic / federal / international / non-designer), **G12** (four role-family presets, no fifth), **G13** (missing portfolio link is flag-only).

## Step-by-step procedure

### Step 1 — Validate INTAKE_RESUME and confirm draft-from-list fits

**Schema validation.** Confirm the object has `raw_text` (non-empty), `format` (one of the six enum values), `source_provenance` (any string), `mode_routing_hint` (one of `line_edit | brainstorm | draft_from_list | unknown`), `sensitive_flags` (array). If malformed, request re-intake — do not attempt to recover by re-parsing inside this workflow (per LD-P3-06 pattern).

**Shape check — defer if wrong workflow.**

- If `raw_text` has **multi-section resume body shape** (≥3 role blocks, labeled `Experience` / `Education` / `Skills` headings detectable), hand off to line-edit: *"You've got a draft here that's better suited for a line-edit pass. Want me to switch to line-edit mode and tighten what you've written?"* Do not run draft-from-list on a full draft — that's line-edit's job.
- If `raw_text` is **empty or near-empty** (under ~50 words, single paragraph, blank-page signal), hand off to brainstorm: *"This is too thin to draft from — we'd be making up the resume rather than structuring yours. Want to switch to brainstorm and surface the content first?"* Do not run draft-from-list on sparse input — that's brainstorm's job.

**Sensitive-content branch.** If `sensitive_flags` contains `gap` / `layoff` / `nda_mention` / `confidential_metric` / `esl` / `employer_private_project`, apply voice.md §7 register from synthesis onward. The verbatim Tim warmth-script for layoff disclosure (voice.md §7): *"Our heart hurts with you for layoffs which are extremely tricky and come out of nowhere and are catastrophic in nature."* Then proceed. For NDA-heavy roles specifically, pivot bullets to the **process and decision-making** layer per voice.md §11.5 — process is almost never bound by NDAs.

### Step 2 — Seniority + role-family confirm (single-line auto-clarity)

**Resolve `claimed_seniority`.** If `claimed_seniority` is one of `junior`, `mid`, `senior`, `staff`, route to the matching rubric and continue. If `unknown`, fire a single-line auto-clarity confirm:

> *"Quick check before we draft — what level are you targeting in this round? Junior IC, mid IC, senior IC, staff, or design lead/manager? Closest fit is fine."*

Proceed on the answer. If the user already said something resolving this in `raw_text` (*"I'm 6 years in," "first job out of bootcamp," "applying to staff roles"*), use that — don't ask again.

**Resolve `claimed_role_family`.** If `claimed_role_family == "unknown"`, do not invent a fifth preset (gotchas.md G12). Probe with one line:

> *"Is this Product Designer / UX Researcher / Design Engineer / Design Lead-Manager territory? Closest of those four is fine — hybrid roles route to the closest preset."*

Or proceed without a family preset and flag the absence at synthesis time (*"role family unknown — synthesizing from general rubric only; verb-set check skipped"*).

**Stop condition for Step 2.** Two single-line confirms maximum (one for seniority, one for role-family). Never three. Per voice.md single-confirmation rule.

**Boundary discipline (LD-P3-07).** The senior/junior boundary is **target role**, not years-of-experience. If the user is mid-tenured but applying to senior IC or staff promotion-track roles, route to `rubric-senior.md` even when `claimed_seniority` arrived as `mid`. Surface the call: *"Routing to senior rubric per stated target role."*

### Step 3 — Parse the unstructured input

This is the structural pass. The user dumped a list; we identify what's actually there. Do this before any synthesis.

**Identify role boundaries.** Scan `raw_text` for:
- **Employer mentions** — company names, "at [company]," "for [client]," "while at [company]." Anchor each to a role block.
- **Date ranges** — *"2022-2024," "summer 2024," "for two years," "Jan 2023 – present."* Each anchors a role's timeline. If only relative dates (*"my last job," "before that"*), order by stated sequence.
- **Title mentions** — *"Senior Designer," "Product Design intern," "Design Lead."* Map to the corresponding employer mention.
- **Project names** — *"the checkout redesign," "the Auth flow," "the design system buildout."* Group under the role they belong to (or as standalone if the user describes them without role context).

If the source list has no role boundaries (just a dump of project names with no employer / date anchors), **hand back to brainstorm** for the role-context piece: *"The list has projects but no role context — without employer + dates we can't structure Experience properly. Want to switch to brainstorm to surface the role anchors first?"* Do not invent employers, titles, or dates.

**Identify skill mentions.** Scan for tool names (Figma, Sketch, Maze, Mixpanel, React, Tailwind, Storybook, Notion, Jira, Linear, etc.) and method names (semi-structured interviews, usability testing, journey mapping, A/B testing, accessibility audits, design crits, hiring panels). Hold these for the Skills section synthesis. Do not synthesize a Skills section by inferring tools the user didn't name — only what's in the source list.

**Identify education mentions.** Scan for degree names, institution names, graduation years, bootcamp names (General Assembly, Designlab, BrainStation, Springboard), HCI program names, capstones. Hold these for the Education section. If silent, drop Education with a `<!-- SECTION GAP -->` marker per LD-P5-06 — do not invent.

**Identify sensitive signals.** Mentions of NDA / confidential / can't-share / regulated / government / FAANG-internal — flag for the synthesis register (voice.md §11.5). Mentions of sabbatical / gap / layoff / between roles — flag for voice.md §7 register.

**Output of Step 3.** A structured parse: `{ roles: [{employer, title, dates, projects[]}], skills_mentioned: [...], education_mentioned: [...], sensitive_signals: [...] }`. This is the synthesis input for Steps 4-7.

### Step 4 — Section synthesis order

The 4-section template is fixed (LD-P5-03 / OUT-03), but synthesis order is sequenced for fab-resistance:

1. **Experience first.** The bullets are the load-bearing surface. Synthesize them before the Summary so the Summary doesn't drift into aspirational territory unanchored to the actual bullets.
2. **Skills second.** Group by category from the user's actual skill mentions. ≤8 per group (H-S11). If silent → `<!-- SECTION GAP -->` marker.
3. **Education third.** From the user's actual education mentions. If silent → `<!-- SECTION GAP -->` marker.
4. **Summary last.** Now that the actual bullets exist, the Summary can be honest — 2-3 lines that match the seniority + role-family + 1 differentiator the bullets actually carry. If no honest hook lands, drop with `<!-- SECTION GAP: summary line earned no honest hook — H-S20 binary -->` marker per H-S20.

**Output assembly** then orders Summary → Experience → Skills → Education per Step 7.

### Step 5 — Per-bullet synthesis (LD-P5-04 hard rules)

For each bullet across each role:

1. **Pick the framework.** Default to **What/How/Why** per voice.md §11.3 / frameworks.md (corpus-load-bearing, 13/23 transcripts). Reach for **XYZ** when an honest hard metric exists in the source list. Reach for **CAR** when a one-clause Context is genuinely doing work (NDA constraint, unusual team shape, regulated-industry surface). Reach for **R-A-S** at senior+staff when leading with the result is honest. Reach for **Scope-Impact-Metric** when the headline signal is *what the user owned at the org level*. **STAR** is for summary or cover-letter scale only — never at bullet scale on a one- or two-page resume. **Skim-test tiers** is a section-order diagnostic, not a per-bullet framework — don't cite it on synthesis.

2. **Draft the bullet.** Use a verb from the active role-family preset's licensed verb set (H-S07 register lock). Open with the framework's headline beat (Why for W/H/W; X for XYZ; R for R-A-S; Scope for Scope-Impact-Metric). The bullet is at least as concrete as the user's source description (voice.md §4 abstraction-regression guard).

3. **No-fab-metrics ladder (D-16-RR — HARD rule).** When the user gave no number for a bullet:
   - Use **scope language** instead — *"led seven plus projects" / "shipped to 4M MAU"* is honest scope, not a fake percentage.
   - Use **soft metric / behavior change** if the user described one — *"team adopted the empty-state pattern across two adjacent surfaces."*
   - Use the **`<!-- METRIC GAP: ask N -->`** marker when neither scope nor soft signal is available. The marker is visible to the user and signals: real bullet, real work, but the data isn't here. **Do not paper over with an invented number.**

4. **Banned-AI-verb scrub (D-17-RR / G07 / voice.md §11.1).** Never synthesize *spearheaded, leveraged, synergized, catalyzed, orchestrated, championed, drove (no object), amplified (no metric)* in any bullet. If the user used one in their source list, substitute to a role-family preset verb at synthesis. Cite the banned-AI-default verb list by name in rationale where relevant.

5. **D-21-RR write-for-the-hiring-manager.** No keyword stuffing. The bullet earns its keywords by naming the actual tools and methods the user used — never by tacking them on.

6. **Cite the framework by name** in parentheses next to the bullet in output — *(W/H/W)*, *(Scope-Impact-Metric)*, *(XYZ)*, *(CAR)*, *(R-A-S)*. Per voice.md §12 self-check, every synthesized bullet has at least one framework named verbatim.

7. **Bullet count per role per LD-P5-05.** Junior: 3-4 bullets per role. Senior: 4-6 bullets per role. If the source list provides material for fewer than the floor (e.g., a junior role with only 2 honest bullets), output 2 with a `<!-- BULLET GAP: source list provided 2 honest bullets; junior floor is 3 — surface more in brainstorm if you want -->` marker. Do not pad with weak bullets to hit a count.

### Step 6 — Section completion check (LD-P5-06 probe-before-draft)

Before output assembly, walk each section and check it can be filled honestly:

- **Summary.** Does the source list carry an honest hook (years + role-family + 1 differentiator)? If yes, synthesize 2-3 lines. If no, drop with `<!-- SECTION GAP: summary line earned no honest hook — apply H-S20 binary, either cut entirely or surface more material in brainstorm -->` marker. Do not synthesize a generic "passionate, detail-oriented designer" line — that's the exact R09 anti-pattern. (Per voice.md §11.7: write for the hiring manager. A generic summary writes for no one.)

- **Experience.** Do the role boundaries from Step 3 carry employer + dates + at least 2-3 honest bullets each? If yes, synthesize per Step 5. If not (e.g., a project-name-only mention with no employer/date anchor), either drop the role with `<!-- ROLE GAP: project mentioned but no employer/date — surface in brainstorm -->` or hand back to brainstorm for that role's anchors.

- **Skills.** Did Step 3 surface ≥4 distinct skill mentions across the source list? If yes, group by category (Research methods / Design tools / Front-end stack / etc.) per H-S11; ≤8 per group. If no (the user dumped roles+projects but never named tools or methods), drop the entire Skills section with `<!-- SECTION GAP: no skill mentions in source list — surface tools/methods in brainstorm or omit -->` marker. Do not synthesize a Skills section by inferring tools from the bullets — that's fabrication at the section scale.

- **Education.** Did Step 3 surface degree + institution + dates? If yes, synthesize per H-S13 position rule. If no, drop with `<!-- SECTION GAP: no education info in source list — provide degree/institution/dates or omit -->` marker. Do not invent a degree.

**Hand-off offer for sparse sections.** Single-line offer at the end (LD-P5-07 hand-off + section-specific): *"Sections marked `<!-- SECTION GAP -->` need more source material. Want to switch to brainstorm to surface them?"*

### Step 7 — Output assembly per LD-P5-03

Assemble the output using the template under the "Output template (OUT-03)" section below. Section order is fixed: Summary → Experience → Skills → Education. Per H-S15 (section-header conventionality), use exactly those four header strings — no cute alternatives ("My Story," "Where I've Been," "Tools I Love"). ATS map is non-negotiable.

**Reverse-chronological forcing function (H-S10).** Within Experience, order role blocks newest-first. If the source list provided dates, this is automatic. If only relative ordering, follow the user's stated sequence and surface the assumption in a `<!-- ASSUMPTION: ordered roles by stated sequence — confirm reverse-chronological -->` marker.

**Education position (H-S13).** Junior + mid → top half (above Experience or right after Summary). Senior + staff → footer (after Experience). The position itself is a positioning act per H-S13.

**Skim-test pre-flight.** Run the Skim-test tiers framework against the assembled draft before emit:
- **0–3s — header read.** Does the Summary line carry the seniority + role-family + 1 differentiator? Or did it land as `<!-- SECTION GAP -->` marker?
- **3–10s — most-recent role + top bullet.** Does the lead bullet on the most-recent role carry an honest impact (per W/H/W or Scope-Impact-Metric)?
- **10–30s — bullet pull-through.** Are bullets across older roles compressed to scope+outcome? Are there `<!-- METRIC GAP -->` markers visible where data was missing?
If the Skim-test surfaces a gap the synthesis missed, fix before emit — do not paper over.

**Pre-emit self-check.** Run the voice.md §12 self-check (verbatim list reproduced in "Pre-emit self-check" section below). If any check fails, fix or drop the offending content.

### Step 8 — Hand-off offers (LD-P5-07)

End the output with two single-line offers, in this order:

> *Want to line-edit this draft? Say "line-edit" to refine bullets.*

> *Want to save this to a .md file? Reply with a path.*

If user says "line-edit," the draft becomes INTAKE_RESUME `raw_text` for line-edit (P3). User re-invokes — workflows are not pipelined silently per LD-P3-08 / LD-P4-07 / LD-P5-07.

If user gives a save path, write the file with the full output. If "no" or silence, end with the verbatim D-16-RR footer.

If sections are marked `<!-- SECTION GAP -->`, also offer:

> *Sections marked `<!-- SECTION GAP -->` need more source material. Want to switch to brainstorm to surface them?*

## Three worked examples

These illustrate the parse + synthesis discipline. Each: input list verbatim → parsed structure (Step 3 output) → final 4-section output.

### Example 1 — Junior pivot resume from bootcamp + freelance list

**Context.** `claimed_seniority: junior`, `claimed_role_family: product_designer`. The user is a 1-year-out career switcher — finished a bootcamp 14 months ago, did some freelance work, never had a full-time design title.

**Input list (verbatim user paste):**

> "Ok so I did General Assembly's UX Design Immersive in 2024 (graduated Aug 2024). Capstone was a redesign of the Phoenix Public Library's mobile app — usability testing with 8 students, redesigned the search and hold-request flows, hi-fi mockups in Figma, validated through 2 rounds of moderated tests. After bootcamp I did freelance for: a local coffee roaster (logo refresh + landing page, May–Jul 2024), a nonprofit (donation flow redesign, Sep–Nov 2024 — they tracked donation completion before/after, went from ~52% to ~68%), and a friend's e-commerce side hustle (product page redesign, Jan 2025, no measurement). Tools: Figma, Maze, FigJam, Notion, light HTML/CSS. Targeting junior product design roles."

**Parsed structure (Step 3 output):**

```
{
  roles: [
    {
      employer: "self / freelance — friend's e-commerce side hustle",
      title: "Freelance Product Designer (project-based)",
      dates: "Jan 2025",
      projects: ["product page redesign — no measurement"]
    },
    {
      employer: "self / freelance — local nonprofit",
      title: "Freelance Product Designer (project-based)",
      dates: "Sep–Nov 2024",
      projects: ["donation flow redesign — completion 52% → 68%"]
    },
    {
      employer: "self / freelance — local coffee roaster",
      title: "Freelance Product Designer (project-based)",
      dates: "May–Jul 2024",
      projects: ["logo refresh + landing page"]
    }
  ],
  capstone: {
    project: "Phoenix Public Library mobile app redesign",
    detail: "8 student usability tests, 2 moderated rounds, redesigned search + hold-request flows, hi-fi in Figma",
    program: "General Assembly UX Design Immersive, grad Aug 2024"
  },
  skills_mentioned: ["Figma", "Maze", "FigJam", "Notion", "HTML/CSS (light)"],
  education_mentioned: ["General Assembly UX Design Immersive — Aug 2024"],
  sensitive_signals: []
}
```

**Final output (4-section markdown):**

```
## Summary

Career-switcher product designer 14 months out of General Assembly's UX Immersive,
targeting junior product design roles. Three freelance engagements shipped, one
with a measurable conversion lift (52% → 68% donation completion). Comfortable
in Figma + Maze + FigJam, light HTML/CSS for handoff fluency.

## Education

**General Assembly · UX Design Immersive · Aug 2024**
Capstone: Phoenix Public Library mobile app redesign — redesigned the search and
hold-request flows, validated through 2 rounds of moderated usability testing
(n=8 students), shipped hi-fi in Figma.

## Experience

### Freelance Product Designer · Local nonprofit · Sep–Nov 2024
- Lifted donation completion from 52% to 68% by redesigning the donation flow
  end-to-end, validated through pre/post tracking the nonprofit ran. *(XYZ)*
- Shipped the new flow as the donation page's default; the nonprofit kept the
  redesign in production through year-end. *(W/H/W)*
- Owned the project solo: discovery, hi-fi, handoff to their site builder. *(CAR)*

### Freelance Product Designer · Local coffee roaster · May–Jul 2024
- Refreshed the logo and shipped a single-page marketing site for the roaster's
  storefront opening. *(W/H/W)*
- Designed the landing page in Figma, handed off to the owner who built it
  on Squarespace; the page launched on the storefront opening date. *(CAR)*
- Owned the project solo: brand direction, copy collaboration, hi-fi handoff.
  <!-- METRIC GAP: roaster did not track site analytics; honest scope only. --> *(W/H/W)*

### Freelance Product Designer · Friend's e-commerce side hustle · Jan 2025
- Redesigned the product page for the side hustle's storefront — focused on
  hierarchy and the add-to-cart placement. *(W/H/W)*
- Shipped the redesign behind the friend's existing storefront tooling.
  <!-- METRIC GAP: no measurement on this project — honest non-outcome. --> *(W/H/W)*
- Owned the project solo. *(CAR)*

## Skills

**Design tools:** Figma, FigJam, Maze
**Documentation:** Notion
**Front-end fluency:** HTML/CSS (light, handoff-level)

---

Want to line-edit this draft? Say "line-edit" to refine bullets.

Want to save this to a .md file? Reply with a path.

---

*This is not Tim or Nate speaking — it's an approximation built from publicly
shared review patterns. For a direct review, join the Friday stream:
[Friday stream link].*
```

**Synthesis notes.** Education sits **above Experience** per H-S13 junior-tier position rule (the bootcamp + capstone are the strongest signal on the page). Three freelance roles run reverse-chronological within Experience. Bullet count: 3 per role per LD-P5-05 junior floor. Two `<!-- METRIC GAP -->` markers visible where the user explicitly said "no measurement" — honest non-outcome bullets per rubric-junior.md §8. Frameworks cited: XYZ (one bullet with the 52%→68% real metric), W/H/W (default scaffold), CAR (one-clause context where solo ownership earned its place). The Summary earns its place per H-S20 — career-switcher framing + 14-months-out + measurable lift on one project + tool fluency. Banned-AI-verb scrub: no *spearheaded / leveraged / catalyzed* anywhere; verbs (*lifted, refreshed, redesigned, owned*) drawn from product-designer role-family preset.

### Example 2 — Senior IC strategic-narrative resume from role-history dump

**Context.** `claimed_seniority: senior`, `claimed_role_family: product_designer`. The user is 8 years in, embedded as a senior IC at a 200-person SaaS, targeting staff IC promotion-track roles at FAANG. Hasn't written a resume in 4 years; dumped the role history.

**Input list (verbatim user paste):**

> "Senior Product Designer at [SaaS-co], April 2021–present. Own the Billing surface end-to-end (admins, end-users, internal eng). Shipped the billing-page redesign Q3 2022 — drop-off on the upgrade flow went from 41% to 23%, sustained through 2024. Built the design-system Auth + Billing component sets — adopted by 4 product teams (12 designers using them as of last quarter). Mentored 2 mid designers to senior level over 2023. Partnered with 3 staff engineers on the architecture for the Q4 2023 multi-tenancy migration — design surface stayed coherent across the migration; no UX regressions reported. Wrote the design-eng partnership rubric in 2024; the broader design org adopted it for the design-eng cadence. Before [SaaS-co]: Product Designer at [B2B-co], 2018–2021, three years on the workflow-builder surface, shipped two major releases (V2 and V3). Design Intern at [agency], summer 2017. Education: BFA Visual Communication, Cal Poly, 2017. Tools: Figma, Tokens Studio, Storybook, Linear, Notion, Mixpanel. Methods: design crit facilitation, usability testing, design-eng pair programming, hiring panels."

**Parsed structure (Step 3 output):**

```
{
  roles: [
    {
      employer: "[SaaS-co]",
      title: "Senior Product Designer",
      dates: "April 2021–present",
      projects: [
        "Billing surface ownership end-to-end",
        "Billing-page redesign Q3 2022 — drop-off 41% → 23%, sustained",
        "Design-system Auth + Billing component sets — adopted by 4 product teams (12 designers)",
        "Mentored 2 mid → senior over 2023",
        "Multi-tenancy migration partnership Q4 2023 (3 staff eng) — no UX regressions",
        "Design-eng partnership rubric — adopted by broader design org 2024"
      ]
    },
    {
      employer: "[B2B-co]",
      title: "Product Designer",
      dates: "2018–2021",
      projects: ["Workflow-builder surface, 3 years", "Shipped V2 + V3 major releases"]
    },
    {
      employer: "[agency]",
      title: "Design Intern",
      dates: "Summer 2017",
      projects: []
    }
  ],
  skills_mentioned: ["Figma", "Tokens Studio", "Storybook", "Linear", "Notion", "Mixpanel",
                     "design crit facilitation", "usability testing",
                     "design-eng pair programming", "hiring panels"],
  education_mentioned: ["BFA Visual Communication, Cal Poly, 2017"],
  sensitive_signals: []
}
```

**Final output (4-section markdown):**

```
## Summary

Senior product designer, 8 years in, targeting staff IC promotion-track roles.
Own the Billing surface at a 200-person SaaS — drove drop-off from 41% to 23% on
the upgrade flow (sustained through 2024), stood up the design-system Auth +
Billing component sets adopted by 4 product teams, and authored the design-eng
partnership rubric the broader design org standardized on in 2024.

## Experience

### Senior Product Designer · [SaaS-co] · April 2021–present
- Owned the Billing surface end-to-end (admin, end-user, internal eng) for a
  200-person SaaS — cut upgrade-flow drop-off from 41% to 23% in Q3 2022 and
  sustained through 2024. *(Scope-Impact-Metric)*
- Stood up the design-system Auth + Billing component sets — adopted by 4
  product teams, 12 designers using them as of last quarter. *(XYZ)*
- Partnered with 3 staff engineers on the Q4 2023 multi-tenancy migration; the
  design surface stayed coherent across the migration with no UX regressions
  reported post-launch. *(Scope-Impact-Metric)*
- Wrote the design-eng partnership rubric in 2024; the broader design org
  adopted it as the standard cadence. *(R-A-S)*
- Mentored 2 mid designers to senior level over 2023 — both promoted with the
  rubric I drafted as the leveling reference. *(W/H/W)*

### Product Designer · [B2B-co] · 2018–2021
- Shipped two major releases (V2 and V3) on the workflow-builder surface across
  3 years — design ownership end-to-end, partnered with PM + eng leads.
  <!-- METRIC GAP: source list named V2/V3 ships but no metric — surface in
  brainstorm if there's adoption / activation data. --> *(W/H/W)*
- Designed the workflow-builder surface as the IC owner across 3 years; the
  surface remained the product's primary user-touchpoint through the
  V3 launch. *(W/H/W)*
- Partnered with PM + eng on roadmap sequencing for V2 → V3; design-led
  pattern decisions carried forward into V3 without rework. *(CAR)*
- Owned design crits and pair sessions with the next-gen IC hire ramping
  during V2. *(W/H/W)*

### Design Intern · [agency] · Summer 2017
- Single-summer agency internship; supported senior designers on client work
  across 3 brand engagements. *(W/H/W)*
<!-- BULLET GAP: senior floor is 4-6 bullets per role; this internship doesn't
have material for senior-tier bullet density. Recommend cutting this role
entirely on the senior resume — it's pre-2018 and dilutes the 8-years-in
positioning. -->

## Skills

**Design tools:** Figma, Tokens Studio, Storybook
**Documentation + Eng partnership:** Linear, Notion
**Analytics:** Mixpanel
**Methods:** design crit facilitation, usability testing, design-eng pair
programming, hiring panels

## Education

**BFA Visual Communication · Cal Poly · 2017**

---

Want to line-edit this draft? Say "line-edit" to refine bullets.

Want to save this to a .md file? Reply with a path.

---

*This is not Tim or Nate speaking — it's an approximation built from publicly
shared review patterns. For a direct review, join the Friday stream:
[Friday stream link].*
```

**Synthesis notes.** Education sits **at the footer** per H-S13 senior-tier position rule. Three roles run reverse-chronological per H-S10. Bullet count: 5 on the most-recent role (within 4-6 senior range), 4 on the prior B2B-co role, 1 on the internship with a `<!-- BULLET GAP -->` marker recommending the role be cut entirely (the internship-on-a-senior-resume is the rubric-senior.md reverse-chronological forcing function in action). Frameworks cited: Scope-Impact-Metric (twice — load-bearing for senior bullets per Criterion 2), XYZ (component adoption count), R-A-S (rubric authored, adopted org-wide — result-led), W/H/W (default), CAR (partnership context). One `<!-- METRIC GAP -->` on the prior role's V2/V3 ships where the user didn't provide metrics. Senior under-claiming probe set (Criterion 3) covered: mentorship (the 2-mid-to-senior bullet), cross-org influence (the design-eng partnership rubric adopted org-wide), process standards-setting (the design-eng cadence standard). Banned-AI-verb scrub: no *spearheaded / leveraged / orchestrated* anywhere; verbs (*owned, stood up, partnered, wrote, mentored*) drawn from product-designer + lead-manager role-family preset registers.

### Example 3 — Design-engineer resume from project-list with stack mentions

**Context.** `claimed_seniority: mid`, `claimed_role_family: design_engineer`. The user is 4 years in as a design engineer at a Series-B startup, dumped a project list with stack mentions but no single role summary.

**Input list (verbatim user paste):**

> "[Series-B startup] Apr 2022–present, Design Engineer. Migrated our design tokens off legacy CSS variables onto Tailwind + Storybook with Figma tokens as source of truth — 4 months, partnered with 4 frontend engineers and 1 PM, shipped behind a feature flag, replaced legacy CSS vars across 3 product surfaces, token-drift incidents in our error log dropped from ~12/month to 0. Built the React component library used by the broader product — 23 components shipped to npm, used by 8 product teams across the company, a11y test pass rate went from 71% to 96% over a year. Refactored the dashboard's sidebar nav using new tokens — completed in one sprint, used as the template for the marketing site refactor by the next quarter. Before [Series-B startup]: Frontend Engineer at [agency], 2020–2022, two years on client work — built marketing sites in Next.js + Tailwind for 5 different B2B clients. CS minor at [State University], 2020 (BFA Graphic Design primary). Stack: React, Tailwind, Storybook, Figma + Tokens Studio, Vite, Storybook, npm, GitHub Actions. Methods: a11y audits, component a11y testing, design-eng pair programming, design system governance."

**Parsed structure (Step 3 output):**

```
{
  roles: [
    {
      employer: "[Series-B startup]",
      title: "Design Engineer",
      dates: "Apr 2022–present",
      projects: [
        "Token migration: legacy CSS → Tailwind + Storybook + Figma tokens, 4mo, 4 FE + 1 PM, feature-flagged, 3 surfaces, drift 12/mo → 0",
        "React component library: 23 components, npm-shipped, 8 product teams, a11y 71% → 96% over a year",
        "Dashboard sidebar refactor — 1 sprint, template for marketing-site refactor next quarter"
      ]
    },
    {
      employer: "[agency]",
      title: "Frontend Engineer",
      dates: "2020–2022",
      projects: ["Next.js + Tailwind marketing sites, 5 B2B clients, 2 years"]
    }
  ],
  skills_mentioned: [
    "React", "Tailwind", "Storybook", "Figma", "Tokens Studio", "Vite", "npm",
    "GitHub Actions", "a11y audits", "component a11y testing",
    "design-eng pair programming", "design system governance"
  ],
  education_mentioned: ["BFA Graphic Design + CS minor, [State University], 2020"],
  sensitive_signals: []
}
```

**Final output (4-section markdown):**

```
## Summary

Design engineer, 4 years in, comfortable across Tailwind + Storybook + Figma
tokens with Tokens Studio in the design-system pipeline. Shipped a 23-component
React library used by 8 product teams (a11y pass rate 71% → 96%), and led the
token-system migration that cut design-token-drift incidents from ~12/month to 0.

## Experience

### Design Engineer · [Series-B startup] · Apr 2022–present
- Cut design-token drift from ~12 incidents/month to 0 by migrating legacy CSS
  variables to a Tailwind + Storybook stack with Figma tokens as the source of
  truth (4-month migration); partnered with 4 frontend engineers and 1 PM,
  shipped behind a feature flag, replaced legacy CSS vars across 3 product
  surfaces. *(XYZ)*
- Shipped a 23-component React library to npm — adopted by 8 product teams
  across the company; a11y test pass rate climbed from 71% to 96% over the
  first year of adoption. *(Scope-Impact-Metric)*
- Refactored the dashboard's sidebar navigation using the new tokens in one
  sprint; the refactor was adopted as the template for the marketing-site
  refactor the following quarter. *(W/H/W)*
- Owned the design-system governance cadence — design-eng pair programming
  with the FE leads, component a11y testing on every release.
  <!-- METRIC GAP: governance cadence has no specific quantified outcome
  beyond the a11y delta above — honest scope only. --> *(W/H/W)*

### Frontend Engineer · [agency] · 2020–2022
- Built and shipped marketing sites in Next.js + Tailwind for 5 B2B clients
  across 2 years. *(W/H/W)*
- Owned the FE work end-to-end on each engagement; partnered with the agency's
  design leads on handoff fidelity. *(CAR)*
- Set up the agency's first shared Tailwind config across 3 of the 5 client
  builds — reduced setup time on subsequent client kickoffs. *(W/H/W)*
- Pair-programmed with junior FE hires on 2 of the 5 client engagements
  during their ramp. *(W/H/W)*

## Skills

**Front-end stack:** React, Tailwind, Storybook, Vite
**Design-system tooling:** Figma, Tokens Studio, npm, GitHub Actions
**Methods:** a11y audits, component a11y testing, design-eng pair programming,
design system governance

## Education

**BFA Graphic Design (CS minor) · [State University] · 2020**

---

Want to line-edit this draft? Say "line-edit" to refine bullets.

Want to save this to a .md file? Reply with a path.

---

*This is not Tim or Nate speaking — it's an approximation built from publicly
shared review patterns. For a direct review, join the Friday stream:
[Friday stream link].*
```

**Synthesis notes.** Education sits **at the footer** per H-S13 — at mid, education drops below experience full stop. Two roles, reverse-chronological per H-S10. Bullet count: 4 on most-recent role (within mid range — junior floor 3, senior floor 4; mid sits at the 3-5 boundary), 4 on the prior agency role. **Stack-specificity heuristic (H-S08) cited explicitly** — Tailwind + Storybook + Figma tokens beats *"design systems work"* (the design-engineer-preset stack-specificity rule). Skills section grouped by category: Front-end stack / Design-system tooling / Methods (≤8 per group per H-S11). Frameworks cited: XYZ (the token migration's clean accomplished-X / by-doing-Y / resulting-in-Z shape), Scope-Impact-Metric (component library adoption count + a11y delta), W/H/W (default), CAR (one-clause context on agency client work). Banned-AI-verb scrub: no *spearheaded / leveraged* anywhere; verbs (*cut, shipped, refactored, owned, built, set up, pair-programmed*) drawn from design-engineer role-family preset register.

## Output template (OUT-03)

```
## Summary

<2-3 line summary statement, factual + specific: years + role-family + 1-2
differentiators that the bullets actually carry. Earned per H-S20 binary, or
dropped with `<!-- SECTION GAP: summary line earned no honest hook -->`.>

## <Education here if junior or mid — H-S13 top-half position>

(Junior + mid only — for senior + staff, Education moves to the footer.)

**<Degree> · <Institution> · <Dates>**
<Optional 1-line capstone / coursework / GPA-if-3.7+ / honors-if-relevant.>

## Experience

### <Role title> · <Company> · <Dates>
- <Bullet, framework headline beat first> *(<framework name>)*
- <Bullet> *(<framework name>)*
- <Bullet> *(<framework name>)*
... (3-4 bullets junior, 4-6 bullets senior — LD-P5-05)

### <Prior role title> · <Company> · <Dates>
- ...

(Reverse-chronological per H-S10. <!-- ROLE GAP --> markers where source list
mentioned project but not employer/dates. <!-- BULLET GAP --> markers where
source list provided fewer bullets than rubric floor.)

## Skills

**<Category 1>:** <comma-separated list, ≤8 entries per H-S11>
**<Category 2>:** <comma-separated list, ≤8 entries>
**<Category 3>:** <comma-separated list, ≤8 entries>

(Or `<!-- SECTION GAP: no skill mentions in source list — surface tools/methods
in brainstorm or omit -->` if Step 6 found no skill mentions.)

## <Education here if senior or staff — H-S13 footer position>

**<Degree> · <Institution> · <Dates>**

---

Want to line-edit this draft? Say "line-edit" to refine bullets.

Want to save this to a .md file? Reply with a path.

(If sections are marked `<!-- SECTION GAP -->`:)
Sections marked `<!-- SECTION GAP -->` need more source material. Want to
switch to brainstorm to surface them?

---

*This is not Tim or Nate speaking — it's an approximation built from publicly
shared review patterns. For a direct review, join the Friday stream:
[Friday stream link].*
```

### Output template notes

- **Section header strings are exactly:** `## Summary`, `## Experience`, `## Skills`, `## Education`. No cute alternatives per H-S15 (section-header conventionality — ATS map). Cute headers break ATS parsing without earning a human upgrade.
- **Section order is fixed:** Summary → Experience → Skills → Education for senior+staff. For junior+mid, Education slides above Experience per H-S13.
- **Bullet framework cite** in parentheses next to each bullet — *(W/H/W)*, *(XYZ)*, *(Scope-Impact-Metric)*, *(CAR)*, *(R-A-S)*. Per voice.md §12 self-check, every synthesized bullet carries at least one framework named verbatim.
- **Bullet count per role** per LD-P5-05: junior 3-4, senior 4-6. Mid sits at the boundary; typical 3-5.
- **`<!-- GAP -->` markers are visible in the output** — they tell the user exactly where the source list didn't carry the data and where to fill in if they want. Three marker types: `<!-- SECTION GAP -->` (whole section), `<!-- ROLE GAP -->` (role anchor missing), `<!-- BULLET GAP -->` (bullet count below rubric floor), `<!-- METRIC GAP -->` (no number for the bullet).
- **Hand-off offers are single-line each** — no multi-question stacks (voice.md auto-clarity discipline).
- **Footer is verbatim D-16-RR.** Non-removable, no rewording.

## Section structural rules (LD-P5-05 / FEATURES §2.5)

These are the load-bearing rules for output assembly. Cite by name.

- **Bullets per role.** Junior: 3-4 bullets. Senior: 4-6 bullets. Mid sits at the boundary (3-5). If the source list provides material for fewer, output what's there with a `<!-- BULLET GAP -->` marker — never pad with weak bullets.

- **Skills section.** Grouped by category, NOT alphabetical noun salad. Categories vary by role-family — Product Designer leans `Design tools / Research methods / Documentation`; UX Researcher leans `Research methods / Synthesis tools / Stakeholder craft`; Design Engineer leans `Front-end stack / Design-system tooling / Methods`; Lead/Manager leans `Methods / Tools / Practices`. Per H-S11 tool-list ceiling: ≤8 entries per group. A 30-tool skills section dilutes the keyword-density signal and reads as résumé-padding (R05 tool-list noun salad).

- **Education position.** Junior + mid → top half (above Experience or right after Summary). Senior + staff → footer (after Experience). Per H-S13 verbatim Nate (4tg1bPbOxus L1390): *"if you are a recent graduate, then oftentimes the most impressive thing you have on your resume is the education."* And inversely (4tg1bPbOxus L1398-1400): *"My perception coming into this resume is that you've already been working on this for five years. And that's a more impressive stance than that of starting with, I just graduated six months ago."*

- **Reverse-chronological forcing function.** Within Experience, role blocks run newest-first per H-S10. Burying a recent senior role beneath education or projects fails the 0-3s skim test.

- **No standalone Projects section at senior+** per H-S14 (no-projects-section at senior — scope-coasting flag). Junior + early-mid: Projects section fine; in this workflow, capstones and side-projects roll into Experience as freelance / coursework role blocks, not as a separate section.

- **Page-count default per H-S16.** Junior → one page worth of content. Senior → up to two pages, both filled. If the synthesized output overruns one page for a junior, surface the call: *"This is running long for a junior resume — H-S16 says one page; want to cut the weakest bullet per role?"* Length is a function of evidence weight, not aspiration.

## What this workflow does NOT do

Set expectations. People will ask for these and v1 doesn't handle them.

- **Does not invent metrics** (D-16-RR / voice.md §9.1 / §11.2 / gotchas.md G06). Hard rule. The probe-before-draft heuristic (H-S19) is the entry rule for sparse sections, and the no-fab-metrics ladder (scope language → soft metric → `<!-- METRIC GAP -->` marker) carries every metric-absent bullet. Never an invented number.

- **Does not invent education, employers, dates, or titles.** If the source list doesn't carry the role anchor, the role drops with a `<!-- ROLE GAP -->` marker or hands back to brainstorm. Education-section invention is the highest-trust-failure surface — never synthesize a degree.

- **Does not synthesize a Skills section by inferring tools from bullets.** If the source list never named tools, the Skills section drops with `<!-- SECTION GAP -->`. Inference at the section scale is fabrication at the section scale.

- **Does not output a generic Summary line.** Per H-S20 binary: a summary either earns its place (factual + specific — years + role-family + 1 differentiator) or it gets cut. Don't try to "make it stronger" while keeping the subjective register; the fix is binary. *"Passionate, detail-oriented designer with 5 years of experience"* is the exact R09 anti-pattern this workflow is built to prevent.

- **Does not output non-standard section headers** (R07 / H-S15 ATS map). The four section headers are exactly *Summary / Experience / Skills / Education*. Cute alternatives — *"My Story," "Where I've Been," "Tools I Love," "What I Do"* — break ATS parsing and don't earn a human upgrade. Conventionality at the header level is non-negotiable; creativity goes in the bullet content.

- **Does not assign numeric scores, grades, or meters** (D-23 / voice.md §11.6 / gotchas.md G05). No "resume score," no "ATS-readiness," no bullet-strength meter.

- **Does not stuff ATS keywords** (D-21-RR / voice.md §9.3 / §11.7 / gotchas.md G04). Write for the hiring design manager; modern ATS follows. Keyword inclusion only via honest bullet rewrites that name actual tools and methods used. No "add these words" list, no hidden-text trick.

- **Does not paste-tailor to a JD** (gotchas.md G08, deferred to v1.1+). If a user provides a JD alongside the list, surface the deferral: *"JD-paste tailoring is v2 — for now I'll structure your list against the role-family preset closest to the target."* Do not silently absorb the JD.

- **Does not export .docx or render visual layouts** (gotchas.md G09, deferred to v2). Output ships as markdown only — Summary / Experience / Skills / Education — with the user's design tooling handling visual layout. No tables, no two-column layouts, no skill bars.

- **Does not write cover letters** (gotchas.md G10, deferred). Cover-letter generation is a different content type with different conventions; resume-rx covers the resume artifact only.

- **Does not WebFetch portfolio links** (D-25 / gotchas.md G13, deferred to v1.1+). v1 is detect-and-warn only — if the source list mentions a portfolio URL, include it in the resume header (the user-provided contact line is upstream of this workflow), but do not live-verify the link.

- **Does not invent a fifth role-family preset** (D-19-RR / gotchas.md G12). Hybrid roles (content designer, design technologist, service designer, design ops lead) route to the closest of the four presets with one inline note acknowledging the call.

- **Does not apply the rubric to out-of-scope resume types** (gotchas.md G11). Academic CVs, federal/government resumes, international CVs requiring photo / DOB, non-designer resumes (PM, eng, marketing) — surface the scope mismatch and decline rather than forcing a fit.

- **Does not generate `Tim says:` / `Nate says:` callouts** (voice.md §8 / D-M2-02). Default to "we." Callouts are authored MANUALLY by Tim and Nate; never fabricated by the model.

- **Does not synthesize bullets containing banned AI-default verbs** (voice.md §11.1 / D-17-RR / gotchas.md G07). Never *spearheaded, leveraged, synergized, catalyzed, orchestrated, championed, drove (no object), amplified (no metric)* in any output bullet — even if the user used one in their source list, substitute at synthesis.

## Forbidden moves (specific to draft-from-list)

- **Synthesizing a Summary that survives the copy-paste test** (R09 / H-S20). If the same line could be pasted onto another designer's resume and read as true, the line is positioning anyone, which means it's positioning no one. Either earn it or cut it.
- **Synthesizing a bullet without citing its framework** (voice.md §12 self-check violation). At least one framework name in parens per bullet.
- **Inventing a metric the user did not provide** in the source list. D-16-RR is hard rule.
- **Synthesizing a bullet that contains a banned AI-default verb.**
- **Restating the user's source-list bullet verbatim** as the synthesized bullet — synthesis adds the framework structure, the role-family verb, the scope/impact ordering, NOT just markdown formatting on the user's verbal sketch. (Voice.md §4 abstraction-regression guard runs the other way too: rewrites must be at least as concrete, but never just repackaging.)
- **Outputting a Skills section inferred from bullet content** when the source list never named tools.
- **Outputting an Education section inferred from "the user must have gone to school somewhere"** when the source list never named a degree.
- **Padding bullets to hit the rubric floor** when the source list doesn't carry the material — surface a `<!-- BULLET GAP -->` marker instead.
- **Sycophantic openers / closers.** *"Great list to work from!"* / *"Hope this helps!"* — never. Lead with the draft; close with the hand-off offers.
- **Loading both rubrics.** rubric-junior.md and rubric-senior.md never load together. The career-stage branch is one-way.

## Edge cases the workflow handles inline

- **Source list with one role only.** Single-role drafts are valid for first-job applicants and very-recent-pivots. Synthesize the role with bullets per LD-P5-05; Education sits prominently for juniors per H-S13. If the role has fewer than 3 honest bullets, surface a `<!-- BULLET GAP -->` and offer brainstorm: *"Only 2 honest bullets surfaced from the source list — junior floor is 3. Want to switch to brainstorm to surface more before drafting?"*

- **Source list with NDA-heavy work.** Apply voice.md §11.5 NDA carve-out at synthesis. Pivot bullets to the **process and decision-making** layer per Tim+Nate verbatim: *"Process and decision-making are almost never bound by NDAs."* Bullet form: scope description + role + decision + observable behavior change, with the confidential metric explicitly held back. Frame as a feature, not a constraint.

- **Source list with a layoff / sabbatical / gap mention.** Apply voice.md §7 register from synthesis. Lead with the verbatim Tim warmth-script when a layoff is disclosed: *"Our heart hurts with you for layoffs which are extremely tricky and come out of nowhere and are catastrophic in nature."* In the Experience section, label the gap honestly — own a sabbatical as a sabbatical (Pair 8: don't fake freelance). Per H-S10 reverse-chronological forcing function with the rubric-senior.md Criterion 6 calibration: it's pretty smart to put your most-recent role at the top rather than sabbatical even though the years don't line up linearly.

- **Source list mixes role history with a JD paste.** Per gotchas.md G08: surface the v1 deferral. Synthesize from the role history only; do not absorb the JD. *"You pasted a JD with the list — JD-paste tailoring is v2. I'll draft against the role-family preset closest to the target role you named."*

- **Source list has a portfolio URL embedded.** Include the URL in the header / Summary line area (the user-provided contact line is upstream). Per D-25 / G13: do NOT WebFetch the URL to verify. Surface a single-line note in the output: *"Portfolio link included from your source list. Test it from a fresh browser before sending the resume out — bit.ly redirects, password gates, and 404s are common silent failures."*

- **Source list is a hybrid role family** (content designer with research methods + design ops lead with hands-on IC craft). Per gotchas.md G12: pick the closest of the four presets — do not invent a fifth — and surface the call: *"Routing to design-engineer.md preset; the design-systems lead role you describe leans IC-technical at this seniority. If your target is more people-track, switch to design-lead-manager.md."*

- **`claimed_seniority == "mid"` with target-role signal indicating senior promotion.** Per the rubric-junior boundary discipline (LD-P3-07 / D-18): the boundary is target role, not years-of-experience. If the user's source list says they're applying to senior IC or staff promotion-track roles, route to `rubric-senior.md` even though `claimed_seniority` arrived as `mid`. Surface the routing call: *"Routing to senior rubric per stated target role."*

- **Source list contains education only, no work history.** Common for bootcamp grads pre-first-job, returning students, career switchers mid-program. Hand back to brainstorm for the projects-as-experience licensing per rubric-junior.md §6: *"This is education + no shipped work yet. Want to switch to brainstorm to surface coursework, capstones, freelance, or side-projects as experience-section material?"* Do not draft an Experience section from "things implied by the program."

- **Source list contains skill mentions only, no roles.** Pure tool-dump with no employer/project context. Hand back to brainstorm: *"You've got tools but no role context — without project anchors we can't structure Experience. Want to switch to brainstorm to surface the projects?"* Do not synthesize a Skills-only resume.

- **Out-of-scope artifact** — academic CV (publications-list-driven), federal resume (USAJOBS-conformant), international CV requiring photo/DOB, non-designer resume (PM, eng, marketing). Per gotchas.md G11: surface the scope mismatch and decline. *"This looks like an academic CV / federal resume / international CV / non-designer resume — Resume Rx's rubric is calibrated for US-market designer resumes and would give you wrong advice. Use a tool calibrated for that artifact."*

## Heuristics in play (cite sparingly, one or two per draft)

Per voice.md §12 self-check, the synthesis surfaces at least 1 framework per bullet. Heuristics are the second layer — they bias the synthesis lens. Cite by name only when the rule adds a real second angle. Most load-bearing for draft-from-list:

- **H-S19 (probe before draft).** Sparse sections trigger probe-back-to-brainstorm rather than fabrication.
- **H-S20 (summary line earns its place or gets cut).** The most-fabricated-prone surface; binary discipline.
- **H-S04 (honest scope beats fabricated metric).** Synthesis rule.
- **H-S07 (role-family register lock).** Verb sets per family at synthesis.
- **H-S10 (reverse-chronological forcing function).** Experience-section ordering.
- **H-S11 (tool-list ceiling).** Skills section caps.
- **H-S13 (education position by seniority).** Junior top-half, senior footer.
- **H-S15 (section-header conventionality).** Summary / Experience / Skills / Education only.
- **H-S08 (stack-specificity over category for design-engineer).** Cited explicitly in Example 3.
- **H-S16 (page-count default — one page junior, two-page senior ceiling).** Length-discipline guard.

Over-citing heuristics degrades the voice. One or two per draft is the rule.

## Pre-emit self-check (verbatim from voice.md §12, draft-from-list-adapted)

Run before emit. Fix or drop offending content.

- [ ] Every synthesized bullet has a framework cited by name in parens (W/H/W / XYZ / Scope-Impact-Metric / CAR / R-A-S).
- [ ] At least 2 frameworks surface across the whole draft (per voice.md §12 self-check).
- [ ] No phrases from voice.md §4 drop list, including the banned AI-default verbs (§4 / §11.1 / D-17-RR).
- [ ] **No fabricated metrics** — every number on a synthesized bullet traces back to the source list (§9.1, §11.2 / D-16-RR). When metric is absent, scope language or `<!-- METRIC GAP: ask N -->` marker fired.
- [ ] **No invented education, employers, dates, or titles** — the role anchors all came from the source list.
- [ ] **Skills section** either grouped by category with ≤8 per group, OR dropped with `<!-- SECTION GAP -->` marker. Not inferred from bullet content.
- [ ] **Education section** either present with the user's actual degree info, OR dropped with `<!-- SECTION GAP -->` marker. Not invented.
- [ ] **Summary line** either earns its place (years + role-family + 1 specific differentiator that the bullets carry) OR dropped with `<!-- SECTION GAP: H-S20 binary -->` marker. Not generic R09 filler.
- [ ] Synthesized bullets are at least as concrete as the user's source-list description — no abstraction regression (§4, §11.1).
- [ ] Section headers are exactly *Summary / Experience / Skills / Education* (no cute alternatives — H-S15).
- [ ] Experience section is reverse-chronological (H-S10).
- [ ] Education position matches seniority (H-S13: junior top-half, senior footer).
- [ ] Bullet count per role hits the rubric floor (LD-P5-05: 3-4 junior, 4-6 senior) OR carries a `<!-- BULLET GAP -->` marker.
- [ ] Skim-test pre-flight passed (0-3s header / 3-10s recent-role lead bullet / 10-30s pull-through).
- [ ] No numeric scores, grades, or meters anywhere in the output (§4, §11.6 / D-23 / G05).
- [ ] No keyword-stuffing — write for the hiring design manager (§9.3, §11.7 / D-21-RR).
- [ ] If sensitive content present (gaps, layoffs, ESL, NDA), auto-clarity register applied (§7, §11.5).
- [ ] If `Tim says:` / `Nate says:` used, each adds a real second angle (not rephrasing). Callouts authored MANUALLY per D-M2-02 — never generated.
- [ ] Hand-off offers present at end (line-edit + save + brainstorm-for-gaps if applicable).
- [ ] Output ends with the verbatim D-16-RR footer.

## How this workflow is composed

Called directly by `../SKILL.md` routing (P6) when:

- `mode == draft_from_list`, OR
- `mode == auto` AND `mode_routing_hint == "draft_from_list"` from intake.md, AND no explicit override to line-edit or brainstorm.

Cross-mode handoff: line-edit.md (P3) and brainstorm.md (P4) consume `INTAKE_RESUME` from the same intake recipes. They do not call draft-from-list; they're peers in the routing layer. If a draft-from-list session ends in a draft the user wants line-edited, the user re-invokes — the workflows are not pipelined silently per LD-P3-08 / LD-P4-07 / LD-P5-07.

The footer is appended once per emit at the end of this workflow's output. No multi-workflow composition in v1.

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
