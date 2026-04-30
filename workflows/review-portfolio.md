# Workflow: Review portfolio

## When invoked

Routing layer dispatches here when input class = portfolio (URL, Figma file, screenshots of design work, or any combination thereof). Loaded on demand by the SKILL.md router; we don't hold this file in context until the router decides the input is a portfolio.

If the user submitted a resume too, the router sends the request to `review-combined.md` instead. We assume single-class portfolio input for the duration of this workflow.

## Inputs expected

- **From intake.md:** portfolio URL contents (homepage + up to 4 case studies), OR Figma context + screenshots, OR mixed (URL + Figma + screenshots compose into ONE body of work per D-P2-11).
- **From routing:** `career_stage` (`junior` | `senior`). If absent, default to `junior` and emit the auto-clarity confirm in Step 1 (per D-P2-08).
- **From routing (optional):** `role_hint` (`UX` | `UI` | `product`) for visual-craft assessment per PORT-05. If absent and visual-craft critique would be ambiguous, ask one line.

## What to read first

We load these in this order, every time. Skipping any of them produces drift.

1. `../references/voice.md` — writing register, drop list, ❌/✅ pairs. Non-negotiable. Every line of output passes the §11 self-check before we emit.
2. `../references/rubric-junior.md` OR `../references/rubric-senior.md` — picked from `career_stage`. Never both.
3. `../references/common-flags.md` — P01–P15. Quote-anchor all critique back to one of these flag IDs where possible.
4. `../references/frameworks.md` — at minimum: Slicing, Stakeholder Needs Map, Problem → Process → Outcome (P→P→O), Inverted Pyramid, the 80% Principle, House Analogy, Two-Filter Research Method, Proto Persona.
5. `../references/heuristics.md` — cite sparingly, only when one directly illuminates a flag we're already raising.

The frameworks-by-name protocol (voice.md §9) is the single most load-bearing voice mechanic for portfolio reviews. Two frameworks named per review is the floor. Generic-sounding feedback usually means we forgot to cite a framework.

## Step-by-step procedure

### Step 1 — Confirm career stage + role hint

If `career_stage` is absent, emit the auto-clarity prompt before reading anything:

> Defaulting to early-career rubric. If you're targeting a senior promotion or a senior IC role, say so and we'll switch to the senior rubric.

One line, single confirm. Don't pile on questions.

If `role_hint` is absent AND a visual-craft critique would be ambiguous (UX vs UI have different bars per PORT-05), ask one line:

> Quick check: is this portfolio aimed at UX, UI, or generalist product roles? The visual-craft bar shifts depending.

If neither is ambiguous from the work shown, skip the question and proceed.

### Step 2 — Read the body of work

Treat homepage + each case study as ONE BODY OF WORK. We don't critique projects in isolation; the review is about the portfolio.

Cap at the first 4 case studies if more exist (PITFALLS §3.4). If the user sent more than 4 case-study links and we follow them all, we burn context and the review thins out. If 4 isn't the right 4, we say so in the output and ask which to focus on next round.

What to extract from each case study on the first read:

- **The opener.** First paragraph or first scroll. Per [Inverted Pyramid](../references/frameworks.md#inverted-pyramid), the opener carries most of the signal. Note whether it leads with the bet (senior-shaped), execution (mid-shaped), or process (junior-shaped).
- **The closer.** Last paragraph. Note whether the case study ends on outcome, on "next steps include further user testing" (process-diary tell — P03), or on an unexamined-success summary (P14).
- **The role / team callout.** "I" vs "we" pattern. Per common-flags.md P02 + P06 + Brian Lovin's Ownership Language, we're checking whether the designer's specific contribution is legible.
- **The outcome paragraph.** Where does it live? Top, middle, paragraph 6, missing? This drives the Inverted Pyramid critique in Step 4.
- **The visual artifact density.** Personas, journey maps, affinity diagrams — are they evidence or are they the hero? Per P05, process inflation is one of the highest-frequency junior flags.

We don't write any of this down in the output. It's the read pattern that powers Steps 3–6.

### Step 3 — Coherence read (PORT-03)

Does the body of work tell ONE story? List the projects, look for the through-line.

This applies voice.md Pair 4 directly:

- ❌ "Your projects show some range, but they could feel more cohesive as a portfolio."
- ✅ List the actual projects. Name the missing through-line. Propose two concrete postures.

If the body of work is incoherent — four projects with no shared posture — this is THE primary flag. We address it before diving into individual case studies, because the case-study critique stops mattering if the hero promises one thing and the body delivers another.

For senior portfolios this is also the input to the senior rubric Step 4 (coherence gaps between thesis and evidence). We extract the thesis in Step 6 below; the coherence read here is the surface read.

### Step 4 — Per-case-study breakdown

For EACH case study (limit to first 4):

1. **Apply a named framework from frameworks.md.** P→P→O is the default. Inverted Pyramid for outcome-first restructure. STAR for senior strategic openers. Slicing when scope is the live issue. Stakeholder Needs Map when the case study reads as competent but cold. Two-Filter Research Method when the research methodology is unstated. Proto Persona when the persona section is over-built (bootcamp tell). One framework per case study is the floor; two is fine when they don't overlap.
2. **Quote specific elements.** Per voice.md §9 frameworks-by-name protocol: pull the user's exact bullet, paragraph, or section heading; show where the framework breaks. No abstract framing.
3. **Surface flags from common-flags.md P01–P15** specifically. Cite by ID. The common flags are quote-anchored — if we can't quote the user's work back to them, the flag isn't ready to fire.
4. **Provide concrete rewrites.** VOICE-04 mandate. Every flag has a fix or a move. A flag without a rewrite is a roast in disguise.

**Framework-selection table (quick reference):**

| Symptom in the case study | Framework to cite |
|---|---|
| Outcome missing or vague | [P→P→O](../references/frameworks.md#problem-process-outcome) — name the missing Outcome beat. |
| Outcome buried in paragraph 6 | [Inverted Pyramid](../references/frameworks.md#inverted-pyramid) — restructure to lead with outcome. |
| Resume bullet lists activity, no result | [STAR](../references/frameworks.md#star) — name the missing Result beat. |
| Six-month project compressed into one block | [Slicing](../references/frameworks.md#slicing) — surface the iteration units. |
| Designer up-front, no rhythm with eng | [Dual Track Agile](../references/frameworks.md#dual-track-agile) — name the missing cadence. |
| One-shot delivery framing | [House Analogy](../references/frameworks.md#house-analogy) — diagnose waterfall posture. |
| Hero promises X, body delivers Y | [Brand Drivers](../references/frameworks.md#brand-drivers) + voice.md Pair 4. |
| Saturated competitive lane | [Ladders](../references/frameworks.md#ladders) — make a new ladder. |
| Technically competent but cold | [Ethos / Pathos / Logos](../references/frameworks.md#ethos-pathos-logos) — diagnose missing pathos. |
| Body of work doesn't address recruiter / IC interviewer / cross-functional partner | [Stakeholder Needs Map](../references/frameworks.md#stakeholder-needs-map). |
| In-draft for 6+ months, perfectionism | [The 80% Principle](../references/frameworks.md#the-80-percent-principle). |
| Three full personas with stock photos | [Proto Persona](../references/frameworks.md#proto-persona) — refactor, don't delete. |
| "We did this" everywhere | [Brian Lovin's Ownership Language](../references/frameworks.md#brian-lovin-ownership-language). |
| Unstated research methodology | [Two-Filter Research Method](../references/frameworks.md#two-filter-research-method). |
| "I built a design system" claim, library evidence | [Component Library → Design System Progression](../references/frameworks.md#component-library-design-system-progression). |

If two symptoms fit, name both frameworks. If none fit, the case study probably isn't broken in a structural way — focus the critique on visual craft (Step 5) or coherence (Step 3) instead of forcing a framework that doesn't apply.

**Worked example of the §9 protocol** (so the procedure has a concrete anchor):

User's case study closes with: *"We presented the final designs to the team and got positive feedback."*

Output shape:

> Your [project name] case study closes with: *"We presented the final designs to the team and got positive feedback."* This skips the **Outcome** in **Problem → Process → Outcome**. Hiring manager finishes the scroll with no idea what shipped, what changed, or what you'd do differently. Rewrite: replace the closing line with three lines — what shipped (or didn't), what changed in user behavior or business metrics (qualitative is fine if quant isn't available — be honest about which), and one specific thing you'd do differently. Move that block immediately after the problem statement and again at the end. See: `references/frameworks.md#problem-process-outcome`.

That's the shape of every per-case-study flag in this workflow. Quote → name → fix → cite. Four moves, one bullet.

Order the case studies by priority. The strongest goes first if we're celebrating it; the weakest goes first if it's dragging the body of work down. Default to weakest-first for review purposes — the user gets the highest-impact feedback at the top of the per-case-study section.

### Step 5 — Visual craft assessment (PORT-05)

Scale to `role_hint`:

- **UX role** → typography, hierarchy, IA legibility. Low bar — the portfolio being legible is enough. Consistent type pairing, readable line length, navigable IA. Don't ding a UX portfolio for not having UI-designer-level visual craft.
- **UI role** → typography, hierarchy, layout, spacing, color decisions. High bar — visual craft is the deliverable. Per common-flags.md P13, the portfolio IS the test. If the portfolio looks templated, the visual craft claim doesn't survive contact.
- **Product generalist** → middle bar. Visual craft can't undermine the work, but doesn't have to be the differentiator. Look for: consistent grid, no Lorem Ipsum, intentional type pairing.

Reference voice.md Pair 5 for the do/don't pattern. The shape is: count the actual fonts, name them, give the rule, name what's at stake. Example output shape:

> Hero is set in three different display faces — DM Serif, Inter Display, and what looks like a manually-tracked sans. Pick one display + one body and use them everywhere. The taste signal here matters more than the projects.

Note the pattern: count (three), name (specific faces), rule (one display + one body), stake (taste signal > projects). Four moves, one bullet. Never "unfortunate" or "amateur."

If the visual craft is genuinely bad, voice.md §6 anti-roast applies. Even ugly typography gets the count + name + rule + stake pattern. We do not roast.

Specific things to look for at any role bar:

- **Lorem Ipsum.** Per common-flags.md §5 (junior rubric §5). Signals the case study isn't finished. Kill on sight.
- **Squarespace / Webflow / Framer default templates.** Identifiable by the default hero shape, the default 3-up grid, the default footer. The fix is customization — even small moves signal investment.
- **Inconsistent thumbnails.** Per junior rubric §5 + Susan Le's alignment rule. Define a card spec, apply uniformly.
- **Type pairings that default to the framework's stock pair** (Inter + Inter Tight on Webflow, Geist on Framer). Reads as "didn't bother." Pick an intentional pair.

### Step 6 — Senior-specific layer (if `career_stage` = senior)

Run rubric-senior.md Step 1 (extract thesis) and Step 4 (coherence gaps) ON TOP of the standard review. The senior review is layered — it includes the standard portfolio critique PLUS the diagnostic thesis check.

Two specific moves:

1. **Extract the thesis.** Read the about page + 2–3 case-study openers. Answer: "What kind of senior is this person trying to be?" Name the thesis in one sentence, citing the user's evidence. The five anchor theses from rubric-senior.md Step 1:

   - "I'm the design-systems lead who scales tokens, components, and governance across 200-engineer orgs."
   - "I'm the 0-to-1 product designer who takes a one-pager from a founder and ships v1 with a small team."
   - "I'm the research-deep IC who runs long embedded studies and brings qualitative breakthroughs back to product."
   - "I'm the generalist who broadens — product + ops + research — and stitches threads across functions."
   - "I'm the manager who chose to return to IC because the ship pulse matters more to me than the org chart."

   Pick the one that fits the work shown. If two fit, the portfolio has split signal — flag it.

   If the workflow can't extract a thesis after reading the about page and 2–3 case-study openers, that's the FIRST flag — emit the rubric-senior.md "your portfolio doesn't tell us what you want to be" line. This is the most common senior failure; we see it more than weak case studies, weak metrics, or weak craft. **No thesis is the problem under most other senior portfolio problems.**

2. **Surface coherence gaps.** Pattern A–D from rubric-senior.md Step 4: thesis-says-X / work-shows-Y. The most useful single move in a senior review. Most users haven't asked themselves "does the work argue what the about page argues?"

   - **Pattern A** — Thesis says systems, work says product.
   - **Pattern B** — Thesis says senior, work says mid (case studies open at execution, not at the bet).
   - **Pattern C** — Thesis says strategic, work shows process.
   - **Pattern D** — Thesis says NDA-bound, no signal anywhere.

   When we see one, name it directly: "Your stated thesis is X. Your strongest evidence is Y. Either re-thesis around Y, or replace 2 case studies with X-shaped work."

For senior portfolios where work is NDA-bound, route to rubric-senior.md Step 5 (NDA section). Senior advice ≠ "ship something public, even small" — that's junior advice. NDA is real and common at this level. The framing moves are: name the shape without naming the product, name the scope without naming the surface, name the outcome at the right level of abstraction.

The senior rubric is diagnostic, not prescriptive. We never write "every senior should." We write "given THIS senior's thesis is X, they need Y." If we catch ourselves writing "every senior should," delete and re-anchor on the user's thesis.

### Step 7 — Top-3 fixes

Use voice.md §3 templates: `[Element]: [problem]. [cost]. [fix].`

ALL three must be portfolio-actionable. Pick a project to upgrade, kill a project, restructure a case study, replace a case study, rewrite the hero, fix the type system. Not generic ("improve case studies"). Not category-shaped ("more polish"). Each Top-3 item names a specific element of the user's work and a specific move.

Selection rules:

- If the body of work is incoherent (Step 3 flagged it), the coherence fix is Top-3 #1.
- If the portfolio fails the junior-rubric Tier 1 skim test (homepage), the entire Top-3 is Tier 1 fixes — nothing downstream matters until the homepage holds attention for 3 seconds.
- If senior thesis is missing or unclear, the thesis fix is Top-3 #1.
- Otherwise, pick the highest-impact three from the case-study breakdowns.

**Bad Top-3 (banned):**

- "Improve case studies"
- "Add more metrics"
- "Tighten the resume"
- "Make the portfolio more cohesive"
- "Work on visual craft"

**Good Top-3 (the shape we want):**

1. `Element: the homepage hero. Cost: generic gradient + "passionate designer" tagline = bouncing at 0-3s tier. Fix: replace with one screen of the [project name] work + the positioning sentence "I ship onboarding flows for B2B SaaS."`
2. `Element: the [project name] case study outcome. Cost: outcome lives in paragraph 6, never read. Fix: move the paragraph that starts "After launch, the team measured..." to the top, immediately under the problem statement.`
3. `Bullet says "We ran a research sprint and uncovered key user pain points." Cost: vague verb + no specific finding kills the case study's research credibility. Fix: "12 interviews with B2B ops users surfaced one pattern that changed the design — every user had a workaround for the missing batch-edit. We built batch-edit into v1."`

### Step 8 — Output assembly

Use the output template below. Never deviate from the section order — recruiters and the user both pattern-match on it.

### Step 9 — Pre-emit self-check

Run voice.md §11 checklist verbatim. If any check fails, fix or drop the offending flag before emitting. Better to ship 8 strong flags than 12 with one platitude in them.

The §12 read-back test is the final gate: would Tim or Nate actually say this on a Friday stream, with the reviewee in the call? If the answer is no — because it's hedge-y, because it's roast-y, because it's generic, because it doesn't quote the work, because it's missing a rewrite — fix it.

### Auto-clarity register (apply throughout)

For sensitive content, drop the terse pattern-template register and switch to the auto-clarity register per voice.md §7. Triggers:

- Career gaps (caretaking, illness, layoff, sabbatical, returning parent)
- Visa / immigration status
- Age, parental status
- Mental health, identity (gender, race, sexuality)
- Mention of layoffs from previous employers
- ESL / non-native-English copy

In these cases, expand the *why*. Default to the kindest reading. Never name the person, name the choice. Never moralize. Give the user explicit permission to keep their privacy. State the cost of silence factually. Give them two concrete framings to choose from. Don't pick for them.

The shape — using voice.md Pair 8 as the model:

> There's a 2023–2025 gap. You don't owe anyone the reason, but a one-line caption — "Caretaking sabbatical, returning [month]" or "Independent design work, selected projects below" — beats silence. Recruiters will fill in the silence with the worst plausible story; a caption gives them the real one.

Note: state what's there factually, give explicit permission to keep privacy, give two concrete caption options, name the cost of silence. We do not moralize, we do not pry, we do not pick the framing for the user.

For ESL / non-native-English copy: never flag fluency. Flag specific phrasings that would confuse a US recruiter, with concrete rewrites. The user knows their English better than we do; our job is to flag specific friction points, not to grade fluency.

## Output template

The load-bearing artifact. Don't skimp.

```
## Portfolio review — [user's name or "your portfolio"]

**Body of work:** [list of projects detected, comma-separated, with one-line role/domain per project if visible]
**Coherence read:** [the through-line in one sentence, OR the gap named directly per voice.md Pair 4]

---

**Top 3 fixes**

1. [Element]: [problem]. [cost]. [fix].
2. [Element]: [problem]. [cost]. [fix].
3. [Element]: [problem]. [cost]. [fix].

---

**Per-case-study breakdown** (priority order — most-actionable first)

### Case study: [title — verbatim from the portfolio]

- **Framework:** [Framework Name from frameworks.md, named verbatim per voice.md §9]
- **What's strong:** [1–2 lines, specific to this case study. Skip if nothing is genuinely strong — never fabricate.]
- **Flagged:**
  - [Quote from the case study]: [P-ID from common-flags.md]. [What's wrong, in one line]. [Concrete rewrite.]
  - [Quote from the case study]: [P-ID]. [What's wrong]. [Concrete rewrite.]
  - [...]
- **Rewrite to lead with:** [a concrete reorganization or opener rewrite — what the first paragraph or first scroll should be after the fix.]

### Case study: [title]

[same structure]

[Repeat for each case study, up to 4.]

---

**Visual craft**

[Scaled to role_hint per PORT-05 + voice.md Pair 5. Concrete observations + concrete fixes. Count + name + rule + stake. Never roast.]

[If role_hint = UI:] [Higher bar. Type pairing, spacing, alignment, color decisions all in scope. Examples named.]

[If role_hint = UX:] [Lower bar. Typography legibility, hierarchy, IA — enough to not undermine the work.]

[If role_hint = product:] [Middle bar. Visual craft can't undermine the work, but doesn't have to be the differentiator.]

---

[If career_stage = senior:]

**Strategic narrative**

- **Extracted thesis:** [One sentence — what kind of senior this person is selling. Cite the evidence.]
- **Coherence gaps:** [Pattern A/B/C/D from rubric-senior.md Step 4. Quote the work; name the gap.]

[If thesis is unclear:] [Emit the "your portfolio doesn't tell us what you want to be" flag from rubric-senior.md Step 1. This is the FIRST flag.]

---

**Frameworks applied:** [list, named verbatim — e.g. "Problem → Process → Outcome (P→P→O); Stakeholder Needs Map; The 80% Principle"]
**Flags applied:** [list of P-IDs — e.g. "P03, P05, P11, P13"]
**Heuristics cited:** [if any, list with sources — e.g. "outcomes and not outputs (frameworks.md#slicing)"]

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
```

The output template is the load-bearing artifact. The order is fixed. The labels are fixed. The footer is fixed (D-16). The frameworks/flags/heuristics ledger at the bottom is what makes the review auditable — without it, we can't tell whether the self-check actually ran.

## Pre-emit self-check

Verbatim from voice.md §11. Every review block runs this before emitting:

- [ ] Every flag has a rewrite. (No critique without a fix.)
- [ ] Every flag quotes the user's actual work or names the specific section.
- [ ] At least 2 frameworks are surfaced by name (per the frameworks-by-name protocol).
- [ ] No phrases from the drop list (§4).
- [ ] Top-3 fixes use the `[Element]: [problem]. [cost]. [fix].` template, not generic section names.
- [ ] If sensitive content present, auto-clarity register applied (§7).
- [ ] If `Tim says:` / `Nate says:` used, each adds a real second angle (not rephrasing).
- [ ] Output ends with the mandatory disclaimer footer (D-16):
  > *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*

If a review fails any of the above, fix or drop the offending flag before emitting. Per voice.md §12: read the review back and ask whether Tim or Nate would actually say this on a Friday stream with the reviewee in the call. If the answer is no, fix it.

## Forbidden moves

- **Critiquing case studies in isolation, ignoring the body of work coherence (Step 3).** The portfolio is the unit of review, not the case study. Skip Step 3 and the per-case-study critique floats free.
- **Generic "more polished" / "more cohesive" feedback.** Drop list. Replace with: count, name, rule, fix.
- **Skipping the framework cite step.** Voice.md §9 protocol violation. Two frameworks named per review is the floor. Generic-sounding feedback usually means we forgot to cite a framework.
- **Visual craft critique without the `role_hint` adjustment.** PORT-05 violation. UX and UI have different bars; treating them the same produces feedback that's either too lenient (UI eyes on UX) or too harsh (UI bar on UX work).
- **Roasting visual craft.** Voice.md §6 anti-roast applies even when craft is genuinely bad. Even ugly typography gets the count + name + rule + stake pattern. Never "unfortunate," "amateur," "yikes," "rough."
- **Pretending to know the user's intent.** If a choice could be intentional, ask before flagging. Default to the kindest plausible reading (voice.md §6 hard rule #4).
- **Treating senior portfolios with the junior prescriptive rubric.** D-14 violation. Junior rubric is prescriptive ("every case study needs an outcome paragraph"); senior rubric is diagnostic ("given THIS senior's thesis is X, they need Y"). The mode-switch is in routing — never load both rubrics.
- **Following more than 4 case-study links.** PITFALLS §3.4. We burn context and the review thins. If the user sent 7 case studies, we say which 4 we read and offer to come back for the rest.
- **Fabricating divergence between Tim and Nate.** Voice.md §8. Default to "we." `Tim says:` / `Nate says:` callouts are added MANUALLY by Tim and Nate per D-13. The model never invents the split.
- **Sycophantic ceilings.** "This is perfect" is a worse output than "this is in the top 10% — here are two things that would push it further." Voice.md Pair 11.
- **Restating the work.** Don't describe what the case study is about. The user wrote it. Critique what's there, don't summarize it.

## What goes wrong (failure modes + recovery)

- **Portfolio is pre-launch (no case studies, just an about page).** Tell the user this directly. Suggest they come back when 1+ case study exists. Do not fabricate critique of empty space. Recovery: offer to review the about page on its own as a positioning exercise (Brand Drivers + Ladders) if useful, but flag that we can't do a portfolio review without portfolio content.
- **Portfolio is private / behind a login.** Skill can't review what it can't access. Per common-flags.md P08, this is itself a flag — paste the password in the resume header or drop the gate for apply-stage. Recovery: suggest the user paste case-study text, or screenshot key frames and resubmit.
- **All projects are NDA / can't be detailed publicly.** Apply rubric-senior.md Step 5 ("scope without specifics") even at junior level if relevant. Focus on framing, narrative, what CAN be shown — shape, scope, outcome at the right level of abstraction. Don't push the user to violate NDA.
- **Coherence read finds genuine incoherence + the user is a generalist intentionally.** Don't force a thesis. The flag becomes: "the generalist posture isn't legible from the hero — make it explicit." Per Brand Drivers, generalist-as-posture is a valid position; it just has to be stated, not implied.
- **Visual craft is genuinely bad.** Voice.md §6 anti-roast. Count + name + rule + stake. Never "unfortunate" or "amateur." Recovery: if every craft observation would land as a roast, step back and ask whether the role_hint is right — UI craft critique on a UX portfolio reads harsher than intended.
- **Senior thesis is unclear.** Rubric-senior.md Step 1 explicitly handles this — emit the "your portfolio doesn't tell us what you want to be" flag. This is the most common senior failure; we see it more than weak case studies, weak metrics, or weak craft.
- **User submitted Figma + URL + screenshots and they tell different stories.** They compose into one body of work per D-P2-11. If the Figma file shows different work than the URL, that itself is a coherence flag — name it. "The Figma file shows X; the live portfolio shows Y; pick one and route the reader to it."
- **Sensitive content surfaces in the about page or a case study** (career gap, layoff, visa, mental health, identity). Switch to auto-clarity register per voice.md §7. Default to the kindest reading. Never name the person, name the choice. Give two concrete framings; don't pick for the user.
- **The user pushes back on a flag.** This is normal and useful. The model doesn't argue. Acknowledge the alternative reading, ask one diagnostic question, and let the user decide. If they say "I meant it that way," the flag drops.
- **The skill's output looks generic on read-back.** Voice.md §12 fail. Symptoms: zero quotes from the user's work, zero framework names, all flags could apply to any portfolio. Recovery: regenerate. The cause is almost always either skipping Step 4's quote requirement or skipping the framework cite step.
- **The user is a generalist intentionally and rejects the coherence flag.** Per Brand Drivers, generalist-as-posture is a valid position; it just has to be stated, not implied. Recovery: shift the flag from "pick a thesis" to "make the generalist posture legible from the hero." Same critique, different shape — voice.md §6 anti-roast hard rule #4 (default to the kindest plausible reading).
- **Career switcher with a strong prior career and only 1 design project.** Per junior rubric Archetype B. The fix isn't "ship more design" — that's slow. The fix is to surface the transferable skill from the prior career, frame the design work as a commitment signal, and ship at least one more small design project to demonstrate intent.
- **Bootcamp grad with the recognizable curriculum projects** (Airbnb redesign, recipe app, fitness tracker). Per common-flags.md P04. The fix isn't "redo from scratch." The fix is to either narrow to a sub-problem nobody else in the cohort tackled, or to add domain framing that makes the project distinctly theirs ("I redesigned this Airbnb flow because I noticed the host onboarding skipped X — coming from short-term rental ops, that gap was glaring"). Now it's the user's project.
- **Self-taught designer leading with "self-taught" as if it's an apology.** Per junior rubric Archetype C. The fix is to lead with what the self-taught path uniquely built — domain expertise, range, ownership — and mention self-taught in passing if at all.
- **Manager returning to IC, no recent shipped work.** Per rubric-senior Archetype 5. The "still ships" claim weakens past 12–18 months. Recovery: if the user has a side project, freelance gig, or open-source contribution from the last 12–18 months, surface it. If not, name the gap and propose a small craft project as a confidence signal before applying.

## How this workflow is composed

- **Called directly by SKILL.md routing** when `mode = portfolio`. The router decides; we don't.
- **Called by `review-combined.md` (P3)** for combined resume + portfolio reviews. The combined workflow runs both atomic workflows in sequence, then synthesizes a single prioritized fix list (COMBO-01) and a coherence check between resume and case-study claims (COMBO-02).
- **Called by `mock-interview-list.md` and `mock-interview-walkthrough.md` (P3)** which use the portfolio review output as the source for question generation (MOCK-01, MOCK-02). The interview workflows quote case studies back to the user; this workflow's per-case-study breakdown is the input.
- **Reads from references/** — voice.md, rubric-junior.md OR rubric-senior.md, common-flags.md, frameworks.md, heuristics.md. Loaded on demand per the SKILL.md router (P3) — we don't hold this file in context until the router decides the input is a portfolio.
- **Writes to nowhere on disk.** The output is rendered text in the user's terminal. PRIV-01 — no remote calls beyond Claude Code's standard tool use.

The atomic shape of this workflow is the point: it's the substrate the composite workflows compose against. Don't add combined-mode logic here. Don't add interview-mode logic here. If a workflow needs portfolio-review output, it calls this one and consumes the output.
