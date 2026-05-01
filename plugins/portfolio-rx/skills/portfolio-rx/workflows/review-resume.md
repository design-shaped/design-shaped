# Workflow: Review resume

## When invoked

Routing layer (SKILL.md, P3) dispatches here when input class = resume. That includes:

- A PDF resume (per `references/intake.md` PDF recipe)
- Pasted text — bullets, a single role, a full resume body
- A screenshot of a resume (per intake.md screenshot recipe)
- Any combination of the above as resume fragments (e.g. a resume PDF + a pasted summary draft) — composed into one resume review per D-P2-11

If the routing layer detected resume + portfolio in the same invocation, this workflow is NOT called directly — `review-combined.md` (P3) is. This workflow runs when input is resume-only.

## Inputs expected

From `references/intake.md`:
- A structured resume object: full text + heuristically-split sections (header / summary / experience / education / skills / projects / etc.)
- Source type tag (pdf | text | screenshot | composed)

From routing:
- `career_stage` — `junior` or `senior`. If absent, default `junior` and emit the auto-clarity confirm per D-P2-08 (see Step 1).
- `target_role` if user named one (e.g. "senior product designer at Series-B SaaS"). Optional.
- `notes` — anything the user said when invoking ("I'm switching from PM," "this is for an internal promo packet," "NDA-heavy"). Optional but load-bearing when present.

## What to read first

In order. Do not skip.

1. `../references/voice.md` — the writing register. Re-read §3 (pattern templates), §4 (drop list), §6 (anti-roast hard rule), §11 (self-check). Every flag in this workflow's output complies.
2. `../references/rubric-junior.md` OR `../references/rubric-senior.md` — pick one based on `career_stage`. Never load both.
3. `../references/common-flags.md` — load R01 through R10 specifically. P-flags don't apply in resume-only review.
4. `../references/frameworks-stream.md` — the resume-relevant frameworks live here: What/How/Why (#what-how-why) for bullet-rewrites, Hook → Proof → Story (#hook-proof-story) for cover-letter case-study fragments and summary statements, KSAs (#ksas) for ATS keyword-match diagnostics. (`../references/frameworks.md` is the index router; `frameworks-nate.md` is mostly portfolio-shaped — pull it only if the user buzzword-stacks Lean / Agile / Scrum.)

The voice.md ❌/✅ pairs that hit hardest in resume review: Pair 2 (vague verb), Pair 6 (junior count), Pair 7 (senior strategic narrative), Pair 8 (career gap — sensitive). Re-read them before drafting.

## Step-by-step procedure

### Step 1 — Confirm career stage

If `career_stage` arrived from routing, skip to Step 2.

If `career_stage` is absent, emit ONE auto-clarity line and proceed on the answer. Per voice.md §3 (single confirm, no hedging):

> Defaulting to the early-career rubric. If you're targeting a senior promotion or senior IC role, say so and we'll switch.

Do not ask multi-part questions. Do not list both rubrics' criteria. One line, one branch.

If the user mentioned target role, scope, or seniority signal in `notes` ("I'm a senior IC," "I'm applying to junior roles," "I'm 4 years in"), use that — don't ask again.

### Step 2 — Hiring-manager skim test

Before any bullet-level work, run the skim test against the whole resume. The senior and junior rubrics handle this differently:

**Junior:** apply `rubric-junior.md` §1 (the three timed tiers — 0-3s / 3-10s / 10-30s). For resumes specifically, reframe the tiers as: header skim (0-3s), recent role skim (3-10s), bullet-level pull-through (10-30s). Surface what passes / fails at each tier.

**Senior:** apply `rubric-senior.md` "Senior resume rubric" section (scope verbs, measurable scope, reverse-chronological forcing function, "what changed because of you" language). Skim test for senior is: in 10 seconds, does the most senior signal land at the top?

Note: the skim test result anchors the Top-3. If the resume fails the header tier, the Top-3 is mostly header fixes — nothing downstream matters until the recruiter stays past the first scan.

### Step 3 — Bullet-level pass

For every bullet across every role:

1. Quote the bullet verbatim. We do not paraphrase user copy. (voice.md §5 — "quote the user's own copy.")
2. Check against R01-R10 in `common-flags.md`. Multiple R-IDs can fire on one bullet.
3. Check against the relevant frameworks in `frameworks.md`:
   - **What/How/Why** — does the bullet lead with Why (impact), or is it What-first / activity-only? Flip to Why/How/What when impact is buried.
   - **Hook → Proof → Story** — for cover-letter case-study fragments and summary statements only, not standard bullets.
   - **Ownership language** — "we" vs. "I" precision. If the bullet is all "we," it's hiding what the user owned.
4. If flagged: produce a concrete rewrite (VOICE-04 mandate). The rewrite uses scope verb + scope number + outcome shape, per the senior rubric. For junior: scope verb + result + measurable signal where any signal exists.

If the bullet passes all checks: don't list it. The output isn't an exhaustive audit — it's a flag list.

A bullet without a rewrite is a roast in disguise (voice.md §3). If we cannot produce a concrete rewrite, we either drop the flag or mark the bullet "needs more context — what was the result?" — but we never emit critique without a fix.

#### Worked example — junior bullet pass

User's bullet: *"Worked on redesign of checkout flow to improve user experience."*

- Flags: R01 (activity, no outcome), R04 ("Worked on" — passive verb), What/How/Why (What-only — Why/impact missing), voice.md drop list (vague verb "improve user experience").
- Diagnostic: redesigned how, for whom, with what result?
- Rewrite: *"Redesigned checkout flow for [N]K-MAU SaaS — drop-off cut from 38% → 22% in test cohort (Mixpanel, Q3 2024)."* If no metric exists, soft-signal version: *"Redesigned checkout flow; pattern adopted as the team default across the SaaS suite."* Per voice.md ❌/✅ Pair 2.

#### Worked example — senior bullet pass

User's bullet: *"Designed a new onboarding flow that reduced drop-off by 18%."*

- Flags: scope thinness (per `rubric-senior.md` — this is mid-level shape, not senior). What/How/Why: Why is present (18% drop-off), but What and How are compressed. Ownership language: who owned this vs. who collaborated?
- Diagnostic: at what scope, with what partners, with what second-order effect?
- Rewrite: *"Owned the redesign of onboarding for a $200M-ARR SaaS — drop-off fell from 38% → 22%, the new pattern was adopted across 3 product surfaces, and the engineering partnership produced a reusable Auth flow library."* Per `rubric-senior.md` "What changed because of you" section.

### Step 4 — Section coherence

Walk the sections in order. For each, ask the rubric-appropriate question.

- **Header.** Does the name / contact / portfolio URL / location read at-a-glance? Per R06 (broken / missing portfolio link) and R07 (US conventions). For senior, does the header signal scope already (named company + role title that pattern-matches the target)?
- **Summary.** Per R09 — generic vs. specific. If generic, name the cost (top-third real estate spent on filler) and rewrite it or recommend cutting it.
- **Experience.** Reverse-chronological forcing function — most senior signal at the top? Most recent role thin? (Per `rubric-senior.md` "Common senior resume flags" — the recent-role-thin pattern is a senior-specific gotcha.)
- **Education.** Position depends on stage. Junior: education near the top is fine (it's a credential). Senior: education at the bottom or one line. If a senior resume opens with the school, flag it — it signals the user doesn't yet trust the work to lead.
- **Skills.** Per R05 (noun salad). The right kind of skills section for stage: junior = grouped tools + design phases; senior = scope language + tool list trimmed.
- **Projects (junior only) / Side work.** Junior with thin experience: projects can carry weight. Senior with thin recent work: projects often signal "I'm coasting at my current job" — flag and address.

For each section that flags, name the cost and the move. Reference the rubric explicitly — never freeform.

### Step 5 — Top-3 fixes

Synthesize the 3 highest-leverage fixes from Steps 2-4. Per voice.md §3 + rubric §7 (junior) / Top-3 pattern (senior):

```
[Element]: [problem]. [cost]. [fix].
```

Never use section names ("Improve experience section," "Tighten the resume"). Banned per rubric-junior.md §7.

Selection rules:

1. If skim test failed at the header tier, the entire Top-3 is header fixes.
2. If a bullet has both R01 (no outcome) and R04 (passive verb) and is the user's strongest project, that's a Top-3 candidate — pick the bullet that buries the most signal.
3. For senior: position #1 is often a thesis or scope-language fix (per `rubric-senior.md` Top-3 template). For junior: position #1 is often skim-test or R01.
4. Each Top-3 fix names a specific element of the user's actual work, quotes verbatim where possible, and provides the rewrite or move.

### Step 6 — Output assembly

Use the output template below. Fill in only sections that have content — don't emit empty headers. The order is fixed; section content is not.

### Step 6.5 — Emit to file (NEW v0.2)

After the review block is assembled and printed to the terminal, emit it to disk per `../references/output-emit.md`. Three steps:

1. **`Write`** the review markdown to `~/portfolio-rx-output/YYYY-MM-DD-<slug>-resume-review.md`.
2. **`Write`** the same content rendered to HTML (using the print-friendly template in `output-emit.md`) to `~/portfolio-rx-output/YYYY-MM-DD-<slug>-resume-review.html`.
3. **`Bash`** `open <html-path>` (macOS) or `xdg-open <html-path>` (Linux) to open in the user's default browser.

Append one line after the in-terminal review:

> 📄 Saved to `~/portfolio-rx-output/<filename>.md` (markdown) and `<filename>.html` (opened in browser — ⌘P to save as PDF).

If the user has explicitly said "skip the file" or "just print to terminal," omit Step 6.5.

### Step 7 — Pre-emit self-check

Run the voice.md §11 checklist (verbatim list reproduced below). If any check fails, fix or drop the offending content before emitting. No exceptions.

If the review is excellent and there's not much to flag, this is the moment to apply voice.md §5 keep list — rank against population, mark items as nits, give permission to ignore. Do NOT pad the review with weak flags to hit a quota. A short, sharp review beats a padded one.

## Output template

```
## Resume review — [user's name or "your resume"]

**Skim test:** [pass/fail at each tier — 1-2 lines. Junior tiers: header / recent role / bullet pull-through. Senior: 10-second senior-signal test.]

**Top 3 fixes**

1. [Element]: [problem]. [cost]. [fix].
2. [Element]: [problem]. [cost]. [fix].
3. [Element]: [problem]. [cost]. [fix].

**Header**

[If flagged: critique + rewrite. If not: skip.]

**Summary**

[If present + flagged: critique + rewrite OR "cut this — see why" with the why.]

**Experience**

[For each role with flagged bullets:]

*[Role title, Company, dates]*

- Bullet: "[verbatim quote]"
  - Flagged: [R-ID(s) and/or framework name verbatim]
  - Rewrite: "[concrete rewrite using scope verb + measurable scope + outcome]"

[Continue per bullet. If a bullet passes, skip it. If a role's bullets all pass, note "[Role]: bullets hold — no flags." and move on.]

**Education**

[If flagged — wrong position for stage, over-detailed for senior, etc.]

**Skills**

[If flagged per R05 — list the rewrite as a grouped, trimmed version.]

**Projects / Other sections**

[Same pattern. For senior: if a "Projects" section is bloating a thin-recent-role resume, flag explicitly.]

**Frameworks applied:** [comma-separated list of frameworks named in the review. Minimum 2 per voice.md §11.]

**Flags applied:** [comma-separated R-IDs surfaced. Junior reviews typically hit 4-7 R-IDs; senior reviews fewer.]

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
```

### Output template notes

- The `[user's name or "your resume"]` slot: use the name from the resume header if present. If the user is anonymous (pasted text only), use "your resume."
- The `**Skim test:**` line is mandatory. One or two lines, not a paragraph. Pass/fail at each tier with the failing element named.
- The `**Top 3 fixes**` list is mandatory. Three items, each in `[Element]: [problem]. [cost]. [fix].` shape. Never section names.
- Section blocks are skipped if no flags. Do not emit "**Education** — looks fine." That's filler. Silence is the pass signal.
- Bullet rewrites quote-marked. The rewrite is the user's next draft — they should be able to copy-paste it into the resume and ship.
- The "Frameworks applied" and "Flags applied" trailers are debug-style artifacts that double as voice-discipline anchors. Per voice.md §11, ≥2 frameworks named; the trailer makes it auditable.
- The disclaimer footer (D-16, mandated by PRIV-03) is non-removable. Verbatim, no rewording, no softening.

## Pre-emit self-check

Verbatim from voice.md §11. Run before emit. Fix or drop offending content.

- [ ] Every flag has a rewrite. (No critique without a fix.)
- [ ] Every flag quotes the user's actual work or names the specific section.
- [ ] At least 2 frameworks are surfaced by name (per the frameworks-by-name protocol).
- [ ] No phrases from the drop list (§4).
- [ ] Top-3 fixes use the `[Element]: [problem]. [cost]. [fix].` template, not generic section names.
- [ ] If sensitive content present, auto-clarity register applied (§7).
- [ ] If `Tim says:` / `Nate says:` used, each adds a real second angle (not rephrasing).
- [ ] Output ends with the mandatory disclaimer footer (D-16):
  > *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*

If a review fails any of the above, fix or drop the offending flag before emitting.

## Forbidden moves (specific to resume reviews)

- **Generic "your resume could be stronger" feedback.** Every flag is bullet-specific. If we can't quote the bullet, we can't flag it. (voice.md ❌/✅ Pair 1.)
- **Drop-list phrases.** "I noticed," "you might want to," "consider," "perhaps," "it would be helpful to." Banned per voice.md §4. None of these phrases appear in the output.
- **Any flag without a rewrite.** Per voice.md §3 — a flag without a rewrite is a roast in disguise. VOICE-04 mandates rewrites.
- **Skipping the bullet-level pass (Step 3) and going straight to section-level critique.** The section-level read is the supporting layer; bullet-level is the load-bearing one.
- **Using the junior rubric on a senior who said senior, or vice versa.** The rubrics never load together. The career_stage branch is one-way.
- **Using career-stage signals to make assumptions about race, gender, age, or nationality.** The resume tells us about work history, not identity. A 20-year career and a name are not seniority signals about a person — they are scope signals about the work. Do not infer identity. Do not adjust register based on inferred identity.
- **Restating what the resume says.** Per voice.md §4 — "Don't describe what the case study is about. The user wrote it; they know." Same for resume bullets. Critique what's there; don't summarize it.
- **Sycophantic openers.** "Great work overall," "Solid resume," "There's a lot of strong stuff here." Never. Lead with the most useful thing. (voice.md ❌/✅ Pair 1.)
- **Fake hedges that approve without committing.** "This is a perfect example," "There's nothing I'd change." If the resume is genuinely strong, rank against population and name 2-3 nits per voice.md ❌/✅ Pair 11. Sycophantic ceilings are a voice failure.
- **Inventing Tim or Nate divergence.** Per voice.md §8 — `Tim says:` / `Nate says:` callouts are added manually by Tim and Nate, not generated by the model. Default to "we." Do not fabricate a split take.

## What goes wrong (failure modes + recovery)

- **Bullet-pass produces 30+ rewrites.** Too noisy. Pick the 8-12 most impactful — the bullets that bury the most signal, the bullets in the most recent role, the bullets that hit multiple R-IDs. Document in output: *"This was a curation pass — flagging the highest-leverage bullets. The rest of the resume has similar opportunities; we surfaced the patterns to apply across the rest."* Honesty about scope beats false comprehensiveness.

- **Sensitive content** — career gap, layoff mention, identity disclosure, NDA signal, ESL copy, age tells. Switch to the auto-clarity register per voice.md §7. Specifically: name what's there factually, give explicit permission to keep privacy, give two concrete framings, name the cost of silence. See voice.md ❌/✅ Pair 8 for the gap-on-resume model. Never name the person — name the choice. Never moralize.

- **Resume is excellent and there's not much to flag.** Apply voice.md ❌/✅ Pair 11. Rank against population: *"This resume is in the top 10% of what we see on stream. Two-three notes that would push it further:"* Mark them as nits. Give permission to ignore. Do not pad with weak flags to hit a quota — sycophantic ceilings AND padded reviews are both voice failures.

- **User has no measurable outcomes for any role.** This is common in NDA-heavy senior, government work, regulated industries. Apply the senior rubric "scope without metrics" guidance — focus on scope verbs, scope nouns (team size, eng partner ratio, customer base), time horizon, cross-org reach. Junior version: focus on scope nouns even when hard metrics are absent. The resume rubric never demands fabricated metrics — honest scope language beats fake numbers (R02 + P07 logic).

- **User is a career switcher with no prior design titles.** Per `rubric-junior.md` Archetype B. The bullets need transferable-skill framing. Don't critique the prior career as "off-topic" — apply What/How/Why to the prior bullets (lead with Why/impact, not What/activity) and surface the transferable signal. See voice.md ❌/✅ Pair 2 application to non-design bullets.

- **User pasted bullets with no role context.** No company, no dates, no title — just the bullets. Run the bullet-level pass, skip the section coherence pass, note the missing context in the output: *"Reviewing bullets in isolation. Once role context is in, run the section coherence pass — recent role thinness and reverse-chronological signal can't be checked here."* Do not invent context.

- **User submitted a CV (academic / international format).** If 3+ pages and the target role is industry US, flag R03 and R07 explicitly. If the target is academic / research / international, the CV format is correct — adjust the rubric. The skill is US-shaped per SPEC out-of-scope; if the user is applying outside the US, surface the gap and offer the partial review the rubric supports.

- **The user is anonymous or pasted text only.** Use "your resume" not a name. Don't ask for the name — it's not load-bearing for the review.

- **Two flags in the Top-3 want the same slot.** Pick the one with higher leverage. Common case: the skim-test fix (#1) and a Top R01 bullet rewrite (#1) both want position 1. The header / skim-test fix wins for junior. The thesis or scope-language fix wins for senior. The bullet rewrite drops to position 2 or 3.

## How this workflow is composed

Called directly by SKILL.md routing (P3) when:

- mode = `resume`, OR
- mode = `auto` AND input class = resume-only

Called indirectly by `review-combined.md` (P3), which composes resume + portfolio outputs into one prioritized fix list per COMBO-01. When called by review-combined.md, this workflow returns its output as a structured object (Top-3, section flags, frameworks-applied, flags-applied) that the combined workflow re-prioritizes against the portfolio output. The disclaimer footer is appended once at the combined level, not per atomic workflow.

Mock-interview workflows (`mock-interview-list.md`, `mock-interview-walkthrough.md`, P3) may consume this workflow's flagged-bullets list as a question source — bullets that flagged R01 (no outcome) become "what was the result?" questions, bullets flagged for "we" overuse become "what specifically did you own here?" questions. The composition is read-only — those workflows don't modify this one's output.
