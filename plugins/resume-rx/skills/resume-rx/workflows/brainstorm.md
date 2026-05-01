---
title: Brainstorm — Resume Rx
plugin: resume-rx
covers: MODE-02, MODE-04 (partial — brainstorm detection branch), OUT-02
sources:
  - ../references/voice.md
  - ../references/frameworks.md
  - ../references/heuristics.md
  - ../references/intake.md
  - ../references/rubric-junior.md
  - ../references/rubric-senior.md
  - ../references/role-families/<family>.md
  - ../gotchas.md
  - .planning/builds/resume-rx/research/STREAM_MINING_RESUME.md (P-RES-01..P-RES-15 verbatim probe text)
---

# Workflow: Brainstorm

> No roasting: just collaboration and constructive feedback. The reviewee is in the call. The user is staring at a blank page or a thin LinkedIn shell — meet them there. We probe before we draft. We never invent metrics. We end with bullets the user can paste, not with more questions.

## When invoked

The routing layer (`../SKILL.md`, authored in P6) dispatches here when the input shape is "nothing concrete." This workflow is one of three modes — the other two are `line-edit.md` (P3) and `draft-from-list.md` (P5). The router decides; this workflow runs the brainstorm pass once selected.

**Detection signals (brainstorm fires when any of these are true):**

- Empty or near-empty INTAKE_RESUME `raw_text` (under ~50 words, or blank).
- Sparse LinkedIn shell — titles + dates + company present, role descriptions empty across most positions.
- User phrasing: *"help me brainstorm," "I don't know what to write," "I'm staring at a blank page," "I'm stuck," "I have nothing yet,"* or close variants.
- A single bullet, single paragraph, or fragment with no role context — no draft to line-edit, just a verbal sketch.
- INTAKE_RESUME emits `mode_routing_hint: "brainstorm"` from intake.md (sparse content detection).
- A user describes a role or project verbally without bullet structure ("I worked on the checkout redesign for two years, pretty senior IC, want to write some bullets about it").

**Detection signals that DEFER (route elsewhere):**

- Multi-section resume body with ≥3 role blocks → `line-edit.md` (P3).
- Raw achievement dump with structure (multiple roles, dated rows, even if fragmented) → `draft-from-list.md` (P5).
- A draft bullet the user wants tightened → `line-edit.md` (P3).

**Explicit override (MODE-05).** When the user says any of *"use brainstorm mode," "/brainstorm," "help me brainstorm," "I don't know what to write,"* brainstorm runs even if the input shape is ambiguous. Document the override in the output header so the user knows the routing happened by request.

## Inputs expected

A parsed `INTAKE_RESUME` object emitted by one of the recipes in `../references/intake.md`. The full schema is documented there. For brainstorm, the load-bearing fields are:

- `raw_text` — typically empty, near-empty, or a verbal sketch. If non-empty and shape is multi-section resume body, hand off to line-edit (Step 1 below).
- `claimed_seniority` — `junior | mid | senior | staff | unknown`. If `unknown`, Step 2 fires a single-line auto-clarity confirm.
- `claimed_role_family` — `product_designer | ux_researcher | design_engineer | design_lead_manager | unknown`. If `unknown`, Step 2 probes once.
- `mode_routing_hint` — should be `"brainstorm"` if the intake recipe routed here automatically; `"unknown"` if MODE-05 override fired on ambiguous input.
- `sensitive_flags` — if present (`gap`, `layoff`, `nda_mention`, `esl`), apply voice.md §7 carve-out from the first turn.

Brainstorm consumes — never re-parses — the `INTAKE_RESUME`. The first procedural step validates the schema and requests re-intake if it's malformed.

## What to read first

Read in this order. Do not skip.

1. **`../references/voice.md`** — the writing register. Re-read §2 (register / Friday-stream voice-memo direct), §3 (pattern templates — the *check-in pivot* lands at every probe turn), §4 (drop list — banned hedges and AI-default verbs), §6 (anti-roast hard rule + the four observable moves), §7 (sensitive-content carve-out — applies inline as we probe), §9.1 (no-fabricated-metrics rule — load-bearing for synthesis), §11.1 (banned AI-default verb list — we don't synthesize bullets that contain them), §11.2 (no-fab-metrics again, hard rule), §11.3 (senior-bullet diagnostic — *what changes because of you?*), §12 (self-check), §14 (footer). Every probe and every synthesized bullet complies.

2. **`../references/frameworks.md`** — the seven D-20 frameworks: **STAR**, **CAR**, **XYZ**, **R-A-S**, **Scope-Impact-Metric**, **What/How/Why**, **Skim-test tiers**. Cite by exact name verbatim, never paraphrase. **What/How/Why is the synthesis default** (corpus-load-bearing, 13/23 transcripts) — flip to other frameworks only when the bullet shape calls for it.

3. **`../references/heuristics.md`** — the H-S## bias rules. Most relevant for brainstorm: **H-S19 (probe before draft)** is the entry rule for this workflow — never draft a bullet before the probes have surfaced the content. **H-S04 (honest scope beats fabricated metric)** — when the probe surfaces no number, the synthesized bullet uses scope language, not a fake percentage. **H-S07 (role-family register lock)** — verb sets per family, locked at synthesis. **H-S09 (calibration-not-accusation)** — frame seniority probes as positioning, not maturity. Cite sparingly — one or two heuristics per session at most.

4. **`../references/rubric-junior.md` OR `../references/rubric-senior.md`** — pick one based on `claimed_seniority`:
   - `junior` or `mid` → `rubric-junior.md` (mid calibration notes folded inline at each criterion)
   - `senior` or `staff` → `rubric-senior.md` (staff calibration notes folded inline at each criterion)
   - `unknown` → emit ONE auto-clarity confirm (Step 2 below) and proceed on the answer
   Never load both rubrics. The branch is one-way.

5. **`../references/role-families/<family>.md`** — pick one based on `claimed_role_family`:
   - `product_designer` → `role-families/product-designer.md`
   - `ux_researcher` → `role-families/ux-researcher.md`
   - `design_engineer` → `role-families/design-engineer.md`
   - `design_lead_manager` → `role-families/design-lead-manager.md`
   - `unknown` → defer family-specific signals; probe once before synthesis. Do not invent a fifth preset (gotchas.md G12).

6. **`../gotchas.md`** — operational pitfalls. Most load-bearing here: **G05** (no numeric scores), **G06** (no invented metrics — applied at synthesis), **G07** (banned AI verbs in any synthesized bullet), **G12** (four role-family presets, no fifth).

## Probe set — P-RES-01..P-RES-15 (from STREAM_MINING_RESUME.md Bucket 6 distillation)

These are the 15 probes the workflow runs, in conversational order. Each probe is cited by exact `P-RES-##` ID per LD-P4-03. Probe text is quoted verbatim from STREAM_MINING_RESUME.md (Bucket 6 distillation, lines 262–346). Do not paraphrase the probe in output — use the exact wording so the IDs trace back.

The 15 probes cluster into four areas. Selection order leads with whichever cluster has the biggest unknown — typically scope first, then impact, then process, then seniority — but if `claimed_seniority == "unknown"`, lead with seniority disambiguation (P-RES-01 + P-RES-12) before any other cluster.

### Scope cluster — what was the work, who used it, how big

**P-RES-01** — *"Tell us a little about who you are, the kind of design work you do, and the level / role title you're targeting in this round of applications. What part of the resume do you want us to focus on?"*
- Surfaces: target role string, career stage, candidate-stated focus area.
- When to fire: **always first** — sets seniority + role-family + the section/role we'll brainstorm bullets for. If `claimed_seniority` and `claimed_role_family` already arrived from intake, compress to a single confirm: *"Targeting Senior Product Designer roles, focusing on your most recent role at [company] — that right?"*

**P-RES-02** — *"Read me your top bullet from your most recent role. What in that bullet would actually make a hiring manager hire you — the activity, or the outcome? If the outcome is buried, what's it actually moving for the business?"*
- Surfaces: activity-first vs outcome-first bullet shape, readiness for a W/H/W flip.
- When to fire: brainstorm-mode adaptation — if there's no top bullet yet, reframe as: *"What's the most recent project you'd want a recruiter to ping you for? Tell us what you did and who used it."*

**P-RES-03** — *"Your bullet says 'led [project]' or 'we [verb]ed.' What did you specifically own here? Where in this bullet does the contribution become precisely yours, vs the team's?"*
- Surfaces: ownership precision, scope inflation risk, team-vs-solo contribution split.
- When to fire: after P-RES-02 if the user described "we" / "the team" / "led" without naming what was specifically theirs.

### Impact cluster — what changed because of you (the senior diagnostic)

**P-RES-04** — *"You wrote '20% increased engagement.' What's the n? Was it your specific design change or a broader release? What was the timeline? And is that pre/post the bullet's described work, or correlated with it?"*
- Surfaces: whether a metric the user has survives a senior-recruiter audit, or whether it's a borrowed number.
- When to fire: when the user volunteers a metric in P-RES-02 / P-RES-03 answers.

**P-RES-05** — *"This bullet has no number. What's the soft metric — the behavior change, the team-adoption signal, the support-ticket reduction? If even that's not available, can you prototype a number from a comparable shipped product?"*
- Surfaces: F-NEW-12 (Hard / Soft / Prototyped Metrics) escalation chain.
- When to fire: when the user says they have no metric. **Critical for D-16-RR compliance** — this is the probe that prevents fabrication.

**P-RES-06** — *"On this bullet, what did you give up to get the result you're claiming? What didn't ship that you wanted to? Would you make the same trade again?"*
- Surfaces: senior-grade self-awareness; the trade-off layer that distinguishes mid-bullet from senior-bullet voice.
- When to fire: senior+staff brainstorms; one of the highest-leverage probes for surfacing under-claimed leadership scope (rubric-senior.md Criterion 3).

**P-RES-07** — *"Your previous title was [X]. Does that title mean the same thing in a centralized environment vs decentralized? At the company you're targeting, will their recruiter read this title the way your previous company meant it?"*
- Surfaces: title translation gap (R05 / F-NEW-07 centralized-vs-decentralized).
- When to fire: when the user names a title that's environment-dependent (Design Lead, Senior Designer at orgs with non-standard leveling).

### Process cluster — how you got to the outcome

**P-RES-08** — *"Read me your summary section. Could a different designer copy and paste it onto their own resume without changing a word? If yes, what's specific to you that should replace it?"*
- Surfaces: subjective-summary anti-pattern (R09); the "copy-paste test" Nate runs verbatim.
- When to fire: only if the user is brainstorming a summary line. Otherwise defer.

**P-RES-09** — *"Pull up the job description for the role you most want. Which KSAs from that JD show up verbatim in your resume? Where they don't, is it because you don't have that knowledge/skill/ability, or because you didn't write it down?"*
- Surfaces: ATS-match gap; opportunity to seed KSAs from JD into bullets and skills section.
- When to fire: cautiously — gotchas.md G08 says no JD-paste tailoring in v1. Reframe as: *"What KSAs from the target JD do you have but haven't written down yet?"* without absorbing the JD as input.

**P-RES-10** — *"Did you build this in Figma or in a one-column doc? Have you run it through any ATS checker — Resi, Jobscan, anything? If a column or sidebar is in here, what's keeping it from being a parse failure?"*
- Surfaces: two-column anti-pattern (R02 portfolio-rx / R03 resume-rx); two-version strategy awareness.
- When to fire: only if the user has a partial draft and is asking about format. Otherwise defer to line-edit (this isn't really a brainstorm probe — keep it for late-session housekeeping).

### Seniority / positioning cluster — what level signal sits in this work

**P-RES-11** — *"Your resume shows a gap from [date] to [date]. Is that a gap that needs explaining? If yes, where on the resume have you owned and framed it?"*
- Surfaces: sabbatical / layoff framing (voice.md §7 sensitive-content carve-out); whether candidate is hiding it (worse) or owning it.
- When to fire: when `sensitive_flags` includes `gap` or `layoff`. Apply voice.md §7 register from the first turn.

**P-RES-12** — *"If a recruiter reads your title at the top and your most recent bullet, what level do they think you are? Now compare that to the level you're targeting. Where's the gap — title, bullet voice, scope words, or metrics?"*
- Surfaces: thesis coherence; resume-as-positioning-vehicle vs resume-as-history-record.
- When to fire: if `claimed_seniority == "unknown"` lead with this + P-RES-01 in the seniority-disambiguation opener. Otherwise mid-session calibration.

**P-RES-13** — *"If we made you cut one bullet from your most recent role, which one and why? What would you put in its place?"*
- Surfaces: candidate self-awareness; surfaces dead-weight bullets and the user's own ranking.
- When to fire: late-session, when the user has 4+ candidate bullets emerging from the conversation. Helps narrow to the 3–7 bullets we synthesize.

**P-RES-14** — *"Of the three audiences — ATS, recruiter, hiring manager — which one did you optimize this version for? Which one would actually open this PDF first?"*
- Surfaces: dual-audience awareness (Theme A); whether candidate has a "two version" strategy.
- When to fire: cautiously — drift toward line-edit territory. Use only if the user is asking about format trade-offs mid-brainstorm.

**P-RES-15** — *"How are you feeling about the direction we're heading on this bullet? Does the rewrite land for you, or do you want to pull on a different thread?"*
- Surfaces: buy-in; permission to redirect mid-conversation.
- When to fire: **after every probe block** — load-bearing for the no-roast register per voice.md Pair 13. Same function as the check-in pivot in line-edit. Single most-repeated phrase in the corpus.

## Step-by-step procedure

### Step 1 — Validate INTAKE_RESUME and confirm brainstorm fits

**Schema validation.** Confirm the object has the expected fields per intake.md schema. If malformed, request re-intake (don't try to recover by re-parsing here).

**Shape check.** If `raw_text` is non-empty AND has multi-section resume body shape (≥3 role blocks, Experience + Education + Skills detectable), hand off to line-edit instead: *"You've got a draft here that's better suited for a line-edit pass. Want me to switch to line-edit mode and tighten what you've written?"* Do not run brainstorm on a full draft — that's line-edit's job.

**Sensitive-content branch.** If `sensitive_flags` contains `gap` / `layoff` / `nda_mention` / `esl`, apply voice.md §7 register from the first turn. The verbatim Tim warmth-script for layoff disclosure (voice.md §7 / STREAM_MINING_RESUME.md §G2): *"Our heart hurts with you for layoffs which are extremely tricky and come out of nowhere and are catastrophic in nature."* Then proceed with the probes.

### Step 2 — Seniority + role-family confirm (single-line auto-clarity)

**Resolve `claimed_seniority`.** If `claimed_seniority` is one of `junior`, `mid`, `senior`, `staff`, route to the matching rubric and continue. If `unknown`, fire P-RES-01 inflected for seniority disambiguation:

> P-RES-01 reframed: *"Quick check before we dig in — what level / role title are you targeting in this round? Junior IC, mid IC, senior IC, staff, or design lead/manager? Closest fit is fine."*

Proceed on the answer. If the user already said something resolving this (*"I'm 6 years in, applying to senior promotion roles"*), use that — don't ask again.

**Resolve `claimed_role_family`.** If `claimed_role_family == "unknown"`, do not invent a fifth preset (gotchas.md G12). Probe with one line:

> *"Is this Product Designer / UX Researcher / Design Engineer / Design Lead-Manager territory? Closest of those four is fine — hybrid roles route to the closest preset."*

Or proceed without a family preset and flag the absence at synthesis time (*"role family unknown — synthesizing from general rubric only; verb-set check skipped"*).

**Stop condition for Step 2.** Two single-line confirms maximum (one for seniority, one for role-family). Never three. Per voice.md single-confirmation rule.

### Step 3 — Probe selection (lead with the biggest unknown)

**Conversational not survey.** Run **≤4 probes per turn** per LD-P4-04. The probes are NOT a checklist — they're a tool for surfacing content the user has but hasn't written down (per H-S19 probe-before-draft).

**Selection order:**

1. **If seniority is still unknown after Step 2:** lead with P-RES-12 (seniority gap probe) bundled with P-RES-01 confirms.
2. **Otherwise — default order:** scope (P-RES-02, P-RES-03) → impact (P-RES-04, P-RES-05, P-RES-06) → process (P-RES-08, P-RES-09 reframed) → seniority/positioning (P-RES-07, P-RES-12, P-RES-13).
3. **Sensitive-content branches:** if `sensitive_flags` includes `gap`/`layoff`, fire P-RES-11 early (voice.md §7 register applied).
4. **Format probes (P-RES-10, P-RES-14):** defer or skip — these drift toward line-edit territory and aren't load-bearing for a brainstorm.

**Per-turn discipline.** Each turn:
- Pick 2–4 probes that share a cluster or naturally chain.
- Open with a one-line context note that names the cluster (*"Let's pull on scope first — three quick probes."*).
- Cite each probe by exact P-RES-## ID inline.
- Close every turn with **P-RES-15** (the check-in pivot) verbatim or close paraphrase: *"How are you feeling about the direction? Want to pull on a different thread, or keep going?"* Per voice.md Pair 13.

### Step 4 — Listen. Synthesize partial bullets as you go.

**User answers drive synthesis.** As the user answers probes, note the material that lands:
- A scope number (team size, surface area, customer base) → goes in the synthesized bullet's scope clause.
- A metric (with sourcing) → goes in the bullet's metric slot. **Verify the user actually said the number** — never round up, never extrapolate.
- A second-order effect (pattern adopted, library used elsewhere, team standard set) → goes at the senior-bullet tail per voice.md §11.3.
- A trade-off / killed-by reason → reserves the slot for an honest non-outcome bullet (rubric-junior.md §8 / rubric-senior.md Criterion 5).

**Real-time framing.** When the user lands a strong answer, name the framework that fits the bullet emerging from it: *"That's a Scope-Impact-Metric shape — scope (3 product squads), impact (cut review-cycle time in half), metric (12 designers adopted the rubric in the next quarter). Want me to draft it now or pull on more?"*

**Short-circuit later probes** when scope and impact land hard. If the user gives a complete answer to P-RES-02 + P-RES-03 + P-RES-05 in one breath, skip to synthesis — don't run process probes for completeness's sake.

### Step 5 — Stop conditions

Synthesize when any of:

1. **Enough material** — 3–7 bullets are visible from the conversation. Each candidate bullet has a verb + scope or method + outcome (even if the outcome is honest non-outcome).
2. **User says "synthesize"** / "that's enough" / "let's draft" / "ok give me bullets."
3. **All 15 probes have run** — rare. If we're still probing after 15, the user doesn't have the content yet, and the move is honest: *"We've pulled hard on this — sounds like the work is genuinely too early for resume bullets yet. Want to come back when there's more to point at?"*

If under 3 candidate bullets surface, the workflow ends with a single-bullet draft + a probe-back-soon note. Do not pad with weak bullets to hit a count.

### Step 6 — Synthesis (3–7 draft bullets)

For each candidate bullet:

1. **Pick the framework.** Default to **What/How/Why** per voice.md §11.3 / frameworks.md (corpus-load-bearing, 13/23 transcripts). Reach for **XYZ** when an honest hard metric exists. Reach for **CAR** when a one-clause Context is genuinely doing work (NDA constraint, unusual team shape, regulated-industry surface). Reach for **R-A-S** at senior+staff when leading with the result is honest. Reach for **Scope-Impact-Metric** when the headline signal is *what you owned at the org level*. Reach for **STAR** only at summary or cover-letter scale, never at bullet scale on a one- or two-page resume. **Skim-test tiers** is a section-order diagnostic, not a per-bullet framework — don't cite it on synthesis.

2. **Draft the bullet.** Use a verb from the active role-family preset's licensed verb set (H-S07 register lock). Open with the framework's headline beat (Why for W/H/W; X for XYZ; R for R-A-S; Scope for Scope-Impact-Metric). Honor D-16-RR — only metrics the user provided in answers. The bullet is at least as concrete as the user's spoken description (voice.md §4 abstraction-regression guard).

3. **No-fab-metrics ladder (D-16-RR — HARD rule).** When the user gave no number for a bullet:
   - Use **scope language** instead of fabricated metrics — *"led seven plus projects"* / *"shipped to 4M MAU"* is honest scope, not a fake percentage.
   - Use **soft metric / behavior change** if the user described one — *"team adopted the empty-state pattern across two adjacent surfaces."*
   - Use the **`<!-- METRIC GAP: ask N -->`** marker when neither scope nor soft signal is available. The marker is visible to the user and signals: real bullet, real work, but the data isn't here. **Do not paper over with an invented number.**

4. **Banned-AI-verb scrub.** Never synthesize *spearheaded, leveraged, synergized, catalyzed, orchestrated, championed, drove (no object), amplified (no metric)* in any bullet (voice.md §11.1 / D-17-RR / gotchas.md G07). If the user used one in conversation, substitute to a role-family preset verb at synthesis.

5. **Cite the framework by name** in parentheses next to the bullet in output — *(W/H/W)*, *(Scope-Impact-Metric)*, *(XYZ)*, etc.

### Step 7 — Save offer

After synthesis, offer to save the transcript per OUT-02 / LD-P4-06:

> *Save this transcript? Reply with a path (e.g. `~/resume-brainstorm.md`) or say "no."*

If the user gives a path, write the file with the full output template content. If "no," end without writing. If user gives a path that's clearly wrong (no extension, system path), one clarifying line: *"Want a `.md` file? Suggest a path like `~/Documents/resume-brainstorm.md`."*

### Step 8 — Hand-off offer to line-edit (LD-P4-07)

Single-line offer at the very end:

> *Want to line-edit these now? Say "line-edit" to switch — the bullets become input for a tightening pass.*

If the user says "line-edit," the bullets become INTAKE_RESUME `raw_text` for line-edit (P3). The user re-invokes — workflows are not pipelined silently per line-edit.md "How this workflow is composed" / LD-P4-07.

If "no," end with the verbatim D-16-RR footer.

## Three worked examples

These illustrate the probe sequence + synthesis discipline. Each: probe / user answer / final bullet + framework cite + voice rule cite.

### Example 1 — Junior brainstorming first job bullet (W/H/W)

**Context.** `claimed_seniority: junior`, `claimed_role_family: product_designer`. The user is a 1-year-out designer with one internship and is starting from a blank page.

**Probe sequence:**

- **P-RES-01:** *"Quick check — junior Product Designer roles, focusing on your internship at [company]?"*
- User: *"Yeah, I was a Product Design intern at a fintech startup, summer 2024. Worked on the password reset flow."*
- **P-RES-02 (reframed):** *"What was the most recent project you'd want a recruiter to ping you for? Tell us what you did and who used it."*
- User: *"The password reset redesign. The old flow had three screens and confused users — I redesigned it to a single screen with inline validation. The lead designer reviewed my work, the eng team built it, it shipped to production for our 50K users."*
- **P-RES-03:** *"What did you specifically own here vs the team's?"*
- User: *"I did all the wireframes and the high-fidelity mocks. The lead designer pushed back on my error states and we co-designed those. I didn't run usability tests — the lead handled that part."*
- **P-RES-05:** *"Any number you've got for it — drop-off, support tickets, anything?"*
- User: *"Honestly no. We didn't track success/failure of the password reset. I know the team was happy with it because they shipped my version basically as-is."*
- **P-RES-15:** *"Sounds like a real first-job-shaped bullet. Want me to draft, or pull on more?"*
- User: *"Draft it."*

**Synthesized bullet:**

> "Co-designed the v1 password-reset flow as a Product Design intern at [company]; the lead designer reviewed and we shipped my single-screen design with inline validation to ~50K users. *(W/H/W)*"

**Framework cite.** **What/How/Why** — flips the user's spoken What-first description. The Why (single-screen design shipped to ~50K users) leads, the How (lead reviewed, co-designed error states) is implicit in *"co-designed,"* the What (the password-reset flow at [company]) anchors. No fabricated metric — the 50K user count is what the user gave; we never invented a drop-off percentage.

**Voice rule cite.** voice.md §11.1 banned-AI-verb register (rejected *spearheaded* / *led* — used *co-designed* per role-family preset and rubric-junior.md §1 junior-baseline verb set). voice.md §9.1 no-fab-metrics rule (no number invented; the 50K is sourced from user answer). Honest non-outcome framing per rubric-junior.md §8.

### Example 2 — Senior brainstorming strategic-influence bullet (Scope-Impact-Metric)

**Context.** `claimed_seniority: senior`, `claimed_role_family: design_lead_manager`. The user is 7 years in, embedded as a design lead on a SaaS product, starting a brainstorm because they haven't written a resume in 4 years and want to surface leadership scope they keep forgetting to claim.

**Probe sequence:**

- **P-RES-01:** *"Senior design lead role, targeting senior+ promotion-track or staff roles?"*
- User: *"Senior design lead role at a 200-person SaaS, targeting staff or principal IC roles at FAANG."*
- **P-RES-12:** *"If a recruiter reads your title and your most recent bullet, what level do they think you are vs the level you're targeting?"*
- User: *"That's why I'm here. My title is Senior Designer, my work is staff-shaped — I run design systems, mentor 4 designers, partner with eng leads on architecture. But I keep writing bullets that sound IC."*
- **P-RES-02 (reframed):** *"Tell us about the leadership-scope work you'd want a staff hiring manager to see — even if you've never written it down."*
- User: *"I built our design system from scratch over 18 months. 14 components in production. The 4 designers on my team adopted it; the broader design org of 24 picked it up by Q3 last year. I wrote the contribution rubric. I run the design-eng partnership cadence with two staff engineers."*
- **P-RES-06:** *"On that work, what did you give up to get the result? What didn't ship?"*
- User: *"I gave up shipping the new search UI for two quarters — I made the call to deprioritize it because the design system was the higher leverage bet. Eng lead was annoyed at first; product caught up six months later when the system unblocked the next two roadmap items."*
- **P-RES-05:** *"Any hard numbers tied to the design system adoption — adoption rate, time-saved, anything?"*
- User: *"Adoption count yes — 14 components, 24 designers using it. Time-saved I don't have measured. The two-quarter search-UI delay I have on Slack."*
- **P-RES-15:** *"That's classic senior under-claim — staff-shaped work narrated IC. Want a draft?"*
- User: *"Yeah, let's see it."*

**Synthesized bullet:**

> "Owned the design system buildout for a 200-person SaaS over 18 months (Scope) — 14 components shipped to production, adopted by my 4-designer team and the broader design org of 24 (Impact); deprioritized a competing search-UI roadmap item to ship the system, which unblocked two subsequent product launches (Metric, second-order). *(Scope-Impact-Metric)*"

**Framework cite.** **Scope-Impact-Metric** — the user's headline signal is *what they owned at the org level* (200-person SaaS, 18-month timeline, 4-designer team, design org of 24). The metric slot carries the second-order effect (unblocked two subsequent launches) per voice.md §11.3 / rubric-senior.md Criterion 5 second-order effect probe.

**Voice rule cite.** voice.md §11.3 senior-bullet diagnostic (*what changed because of you?* — answered: design org of 24 adopted, two roadmap items unblocked). voice.md §11.2 no-fab-metrics (the 14 / 24 / 4 numbers are sourced; the time-saved metric the user didn't have is omitted, not invented). H-S07 role-family register (Lead/Manager preset verbs — *owned, shipped, deprioritized*).

### Example 3 — Design-engineer brainstorming stack-specific shipping bullet (XYZ)

**Context.** `claimed_seniority: mid`, `claimed_role_family: design_engineer`. The user is 4 years in as a design engineer at a Series-B startup, brainstorming a bullet about the migration of their design tokens to a new stack.

**Probe sequence:**

- **P-RES-01:** *"Mid Design Engineer roles at startup-to-Series-B-scale companies?"*
- User: *"Yes, plus design systems lead at slightly larger orgs."*
- **P-RES-02 (reframed):** *"Most recent shipping work you'd want a hiring manager to see?"*
- User: *"I migrated our design tokens off legacy CSS variables onto Tailwind plus Storybook with Figma tokens as the source of truth. Took about 4 months."*
- **P-RES-03:** *"What did you specifically own vs the team's?"*
- User: *"I owned the migration end-to-end. Partnered with 4 frontend engineers and 1 PM. I wrote the token mapping spec; they did the React component refactors with my pair-programming support. Shipped behind a feature flag."*
- **P-RES-04:** *"Any number tied to the migration?"*
- User: *"Three product surfaces moved off legacy CSS vars after the migration. Token-drift incidents in our error log dropped from ~12/month to 0 once everything was on Figma tokens."*
- **P-RES-15:** *"That's a clean XYZ — hard metric (token-drift to zero), action (the migration), skill-signal (Tailwind + Storybook stack). Draft?"*
- User: *"Yes."*

**Synthesized bullet:**

> "Cut design-token drift from ~12 incidents/month to 0 (Accomplished X) by migrating legacy CSS variables to a Tailwind + Storybook stack with Figma tokens as the source of truth (by doing Y); partnered with 4 frontend engineers and 1 PM, shipped behind a feature flag, replaced legacy CSS vars across 3 product surfaces (resulting in Z). *(XYZ)*"

**Framework cite.** **XYZ** — Accomplished-X (token-drift zeroed) leads, How-Y (Tailwind + Storybook + Figma tokens stack) carries the keyword density honestly, Z (3 product surfaces, partnered scope) anchors. Stack specificity per H-S08 (stack-specificity-over-category for design-engineer).

**Voice rule cite.** voice.md §11.1 banned-AI-verb scrub (rejected *spearheaded* / *leveraged* — used *migrated, partnered, shipped, replaced* per design-engineer role-family preset). voice.md §11.2 no-fab-metrics (the 12-to-0 drift number, 4 engineers, 1 PM, 3 surfaces all sourced from user answers — never extrapolated). H-S08 stack-specificity (*Tailwind + Storybook with Figma tokens* beats *"design systems work"*).

## Output template (OUT-02)

```
## Brainstorm — <date>
<claimed_seniority + claimed_role_family> · <1-line scope summary>
<one-line note if MODE-05 override fired or seniority/role-family was unknown>

### Conversation

1. **P-RES-##:** <verbatim probe text>
   *User:* <answer>
2. **P-RES-##:** <verbatim probe text>
   *User:* <answer>
...
N. **P-RES-15:** *"How are you feeling about the direction? Pull on a different thread or keep going?"*
   *User:* <answer / "synthesize">

### Draft bullets

- <bullet 1> *(<framework name>)*
- <bullet 2> *(<framework name>)*
- <bullet 3> *(<framework name>)*
... (3–7 bullets)

### Frameworks applied

<comma-separated list of frameworks named verbatim — minimum 1 per bullet>

### Save transcript?

Reply with a path (e.g. `~/resume-brainstorm.md`) or say "no."

### Want to line-edit these?

Say "line-edit" to refine — the bullets become input for a tightening pass.

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
```

### Output template notes

- The `<claimed_seniority + claimed_role_family>` line uses the resolved values from Step 2.
- Conversation transcript is **numbered** with **P-RES-## IDs visible** so the user (and any downstream line-edit pass) can trace the source of each synthesized bullet back to a probe.
- Draft bullets are 3–7 (LD-P4-05 / LD-P4-06). Each cites its framework verbatim in parentheses.
- Frameworks-applied trailer: minimum 1 framework named per bullet; per voice.md §12 self-check, surface frameworks by name.
- Save offer + line-edit handoff offer are **single-line** each — no multi-question stacks (voice.md auto-clarity discipline).
- Footer is verbatim D-16-RR. Non-removable, no rewording.
- `<!-- METRIC GAP: ask N -->` markers are **inline in the bullet** where they apply, visible in the saved transcript so the user knows where to fill in real numbers.

## Pre-emit self-check (verbatim from voice.md §12, brainstorm-adapted)

Run before emit. Fix or drop offending content.

- [ ] Every probe is cited by exact P-RES-## ID per LD-P4-03.
- [ ] Probe text is quoted verbatim from STREAM_MINING_RESUME.md, not paraphrased.
- [ ] ≤4 probes per turn (LD-P4-04). No survey stack.
- [ ] At least 1 framework named per synthesized bullet.
- [ ] No phrases from voice.md §4 drop list, including the banned AI-default verbs (§4 / §11.1).
- [ ] **No fabricated metrics** — every number on a synthesized bullet traces back to a user answer (§9.1, §11.2). When metric is absent, scope language or `<!-- METRIC GAP: ask N -->` marker fired.
- [ ] Synthesized bullets are at least as concrete as the user's spoken description — no abstraction regression (§4, §11.1).
- [ ] Long flag blocks end with the check-in pivot (Pair 13 / P-RES-15): *"How are you feeling about that direction?"*
- [ ] No numeric scores, grades, or meters anywhere in the output (§4, §11.6 / D-23 / gotchas.md G05).
- [ ] If sensitive content present (gaps, layoffs, ESL, NDA), auto-clarity register applied (§7, §11.5).
- [ ] If `Tim says:` / `Nate says:` used, each adds a real second angle (not rephrasing). Callouts authored MANUALLY per D-M2-02 — never generated.
- [ ] Output ends with the verbatim D-16-RR footer.

## What this workflow does NOT do

Set expectations. People will ask for these and brainstorm doesn't handle them.

- **Does not invent metrics** (D-16-RR / voice.md §9.1 / §11.2 / gotchas.md G06). Hard rule. The probe-before-draft heuristic (H-S19) is the entry rule for this workflow precisely so that synthesis never has to fabricate. When the user has no number, scope language or `<!-- METRIC GAP: ask N -->` marker carries the slot — never an invented percentage.
- **Does not draft a full resume** — that's draft-from-list mode (P5). Brainstorm produces 3–7 bullets, not Summary / Experience / Skills / Education sections.
- **Does not edit existing draft text** — that's line-edit mode (P3). If the user shows up with a draft to tighten, hand off to line-edit at Step 1.
- **Does not run as a survey / multi-question stack** (LD-P4-04 / voice.md auto-clarity discipline). ≤4 probes per turn, conversational pacing, user answers can short-circuit later probes.
- **Does not assign numeric scores, grades, or meters** (D-23 / voice.md §11.6 / gotchas.md G05). No "bullet strength: 4/5," no "ATS-readiness score." Brainstorm output is bullets + framework cites + voice register.
- **Does not paste-tailor to a JD** (gotchas.md G08, deferred to v1.1+). P-RES-09 is reframed to surface KSAs the user has but hasn't written down — the JD is not absorbed as input.
- **Does not invent a fifth role-family preset** (D-19-RR / gotchas.md G12). Hybrid roles route to the closest of the four presets with one inline note acknowledging the call.
- **Does not generate `Tim says:` / `Nate says:` callouts** (voice.md §8 / D-M2-02). Default to "we." Callouts are authored MANUALLY by Tim and Nate; never fabricated by the model.
- **Does not synthesize bullets containing banned AI-default verbs** (voice.md §11.1 / D-17-RR / gotchas.md G07). Never *spearheaded, leveraged, synergized, catalyzed* in any output bullet — even if the user spoke them in conversation, substitute at synthesis.
- **Does not pad with weak bullets to hit a count.** If the conversation surfaces only 2 strong bullets, output 2. If only 1, output 1 + a probe-back-soon note. The 3–7 range is a ceiling, not a quota.

## Forbidden moves (specific to brainstorm sessions)

- **Drafting before probing** (H-S19 violation). The probe IS the draft scaffold. Drafting before content has been surfaced produces generic bullets and risks fabricated metrics.
- **Multi-question stacks per turn.** Voice.md auto-clarity rule. Even when probes naturally chain, ≤4 per turn — and end every turn with P-RES-15 (the check-in pivot).
- **Synthesizing a bullet without citing its framework.** Per voice.md §12 self-check; frameworks named verbatim is the load-bearing voice mechanic.
- **Inventing a metric the user did not provide.** D-16-RR is hard rule. The whole point of the probe-before-draft sequence is that synthesis never has to fabricate.
- **Synthesizing a bullet that contains a banned AI-default verb** (voice.md §11.1).
- **Restating what the user said as the synthesized bullet.** Synthesis adds the framework structure, the role-family verb, and the scope/impact ordering — not just markdown formatting on the user's verbal sketch.
- **Sycophantic openers / closers.** *"Great brainstorm!"* / *"Hope this helps!"* — never. Lead with the next move; close with the line-edit hand-off offer.

## Edge cases the workflow handles inline

- **User has zero shipped work yet.** Common for bootcamp grads, students, career switchers. Lean on rubric-junior.md §6 (projects-as-experience licensing) — coursework, capstones, freelance, side projects roll into the bullets at the same shape as employed work. Probe for the most-recent project regardless of whether it shipped.

- **NDA-heavy work, no nameable metrics.** Apply voice.md §11.5 NDA carve-out from the first probe. Pivot to the **process and decision-making** layer per Tim+Nate verbatim: *"Process and decision-making are almost never bound by NDAs."* The synthesized bullet form: scope description + role + decision + observable behavior change, with the confidential metric explicitly held back. Frame as a feature, not a constraint.

- **User describes work in third-person ("the team did X").** Fire P-RES-03 immediately to surface ownership precision. The synthesis bullet must name the user's specific contribution — not the team's collective output. Per H-S06 single-author-vs-team-win disclosure.

- **User insists on a metric they're not sure about.** Fire P-RES-04 (metric audit). If the user can't say what the n was, what the timeline was, or whether it's pre/post — flag the audit risk: *"That number won't survive a senior recruiter audit. Honest scope (team size, surface, timeline) is stronger than a borrowed metric."* Synthesize without the suspicious number.

- **Layoff / sabbatical / gap signal in `sensitive_flags`.** Apply voice.md §7 carve-out. Lead with the verbatim Tim warmth-script when a layoff is disclosed. Then proceed with probes normally — do not dwell. Fire P-RES-11 for gap framing per voice.md Pair 8 (own the sabbatical, don't fake freelance).

- **User wants to brainstorm a summary line, not bullets.** Fire P-RES-08 (copy-paste test) early. Per H-S20: a summary either earns its place (factual + specific — years + role-family + 1 differentiator) or it gets cut. Don't try to "make it stronger" while keeping the subjective register; the fix is binary. Synthesize a summary line OR explicitly recommend cutting it.

- **User is brainstorming for a hybrid / non-listed role family** (content designer, design technologist, service designer). Per gotchas.md G12: pick the closest of the four presets — do not invent a fifth — and surface the call: *"Routing to design-engineer.md preset; the design-systems lead role you describe leans IC-technical at this seniority."*

- **`claimed_seniority == "mid"` with target-role signal indicating senior promotion.** Per the rubric-junior boundary discipline (LD-P3-07 / D-18): the boundary is target role, not years-of-experience. If the user says they're applying to senior IC or staff promotion-track roles, route to rubric-senior.md probes (P-RES-06 trade-off, P-RES-12 seniority gap) even though `claimed_seniority` arrived as `mid`.

## Heuristics in play (cite sparingly, one or two per session)

Per voice.md §12 self-check the synthesis surfaces at least 1 framework per bullet. Heuristics are the second layer — they bias the probe selection and synthesis lens. Cite by name only when the rule adds a real second angle. Most load-bearing for brainstorm:

- **H-S19 (probe before draft).** Entry rule for this workflow. The probes ARE the draft scaffold. Never draft before content has been surfaced.
- **H-S04 (honest scope beats fabricated metric).** Synthesis rule. When no number lands, scope language carries the slot.
- **H-S07 (role-family register lock).** Verb sets per family at synthesis.
- **H-S09 (calibration-not-accusation).** Frame seniority probes (P-RES-12) as positioning, not maturity.
- **H-S20 (summary line earns its place or gets cut).** When synthesizing a summary line per P-RES-08.

Over-citing heuristics degrades the voice. One or two per session is the rule.

## How this workflow is composed

Called directly by `../SKILL.md` routing (P6) when:

- `mode == brainstorm`, OR
- `mode == auto` AND `mode_routing_hint == "brainstorm"` from intake.md, AND no explicit override to line-edit or draft-from-list.

Cross-mode handoff: line-edit.md (P3) and draft-from-list.md (P5) consume `INTAKE_RESUME` from the same intake recipes. They do not call brainstorm; they're peers in the routing layer. If a brainstorm session ends in draft bullets that the user wants line-edited, the user re-invokes — the workflows are not pipelined silently per LD-P4-07.

The footer is appended once per emit at the end of this workflow's output. No multi-workflow composition in v1.

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
