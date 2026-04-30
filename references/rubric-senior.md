# Rubric — Senior (mid → senior IC promotion track)

> Diagnostic, not prescriptive. Extract the user's thesis. Grade the work against THAT, not against a universal checklist.

## When to use this rubric

Use this rubric when the user is:
- Going for IC senior at a company that has staff/principal levels above
- Mid-level designer building a portfolio for a senior application
- Senior designer prepping promotion materials (often NDA-bound)
- Manager returning to IC who needs to re-establish ship-shaped evidence

For first-job applicants, bootcamp grads, career switchers, and anyone in their first or second design role: use `rubric-junior.md` instead. Junior portfolios fail in repeating ways and the rubric is prescriptive ("every case study needs an outcome paragraph"). Senior portfolios fail in individual ways. A prescriptive checklist gives senior designers generic feedback, which is a worse failure than no feedback. This rubric extracts the user's thesis and grades the work against that thesis.

The mode-switch in `SKILL.md` routing decides which rubric loads. They never load together.

---

## Why this rubric is diagnostic

A junior portfolio with no metrics is broken in a known way and the fix is known: add metrics. A senior portfolio with no metrics could be deliberate (research-deep IC, NDA-bound work, qualitative-breakthrough story) or it could be the actual problem. We can't tell without first reading the work and answering: *what kind of senior is this person trying to be?*

The rubric reads: "given the user's thesis is X, do they have evidence on axis Y?" — never "every senior should have evidence on axis Y." If we ever catch ourselves writing "every senior should," delete it and re-anchor on the user's thesis.

The five steps:

1. Extract the user's thesis from their work.
2. Map to one of five trajectory archetypes.
3. Apply the ADPList 6-axis senior framework against the thesis.
4. Surface coherence gaps between thesis and evidence.
5. Surface promotion-track-specific signals (NDA, scope, leadership without authority).

Then a Top-3 fixes block, anchored on the thesis.

---

## Step 1 — Extract the user's thesis

Before applying any criteria, read the body of work and answer: **"What kind of senior designer is this person trying to be?"**

The thesis is rarely stated. It's hidden in:

- **The about page.** What gets named first — domain, scope, posture, role evolution? What's missing?
- **The case-study openers.** Do they open at the bet ("we had a 40% drop-off and no one knew why"), at execution ("I was assigned the checkout flow"), or at process ("we ran a research sprint")? Senior thesis lives at the bet. Mid thesis lives at execution. Junior thesis lives at process.
- **Project selection.** Six projects on the portfolio — what's the through-line? "I ship 0-to-1 in fintech" is a thesis. "I scale design systems across N teams" is a thesis. "Here are six unrelated projects" is the absence of a thesis, which is itself the finding.
- **Role progression on the resume.** Did the user climb at one company (depth thesis) or breadth across many (range thesis)? Did they promote into management and back to IC (manager-returning thesis)?
- **What's NOT shown.** Sometimes the thesis is signaled by what's absent. A research-heavy portfolio with no shipped product is a research-deep IC thesis. A systems-heavy portfolio with no flow work is a design-systems-lead thesis.

### Five-to-seven example theses (so the workflow has anchors)

A senior thesis is one sentence. It names the *posture* the user is selling, not the *role title*.

- *"I'm the design-systems lead who scales tokens, components, and governance across 200-engineer orgs."*
- *"I'm the 0-to-1 product designer who takes a one-pager from a founder and ships v1 with a small team."*
- *"I'm the research-deep IC who runs long embedded studies and brings qualitative breakthroughs back to product."*
- *"I'm the generalist who broadens — product + ops + research — and stitches threads across functions."*
- *"I'm the manager who chose to return to IC because the ship pulse matters more to me than the org chart."*
- *"I'm the domain specialist in [healthtech / fintech / dev tools] — my edge is the domain, not the methodology."*
- *"I'm the senior-of-juniors — I lead without title, mentor a pod of 4-6, ship through them."*

Pick the one that fits the work shown. If two fit, the portfolio has split signal — flag it.

### When the thesis is unclear

If the workflow can't extract a thesis after reading the about page and 2-3 case-study openers, the FIRST flag is:

> Your portfolio doesn't tell us what you want to be. Six projects, all execution, no posture. Pick a thesis — "I ship complex flows in B2B" or "I scale systems across teams" or "I take 0-to-1 from sketch to v1" — and rebuild the hero, the about page, and at least one case-study opener around it. Right now this reads as: "I'll take any senior role." Recruiters fill that silence with the worst plausible story.

This is the most common senior failure. We see it more than weak case studies, weak metrics, or weak craft. **No thesis is the problem under most other senior portfolio problems.**

---

## Step 2 — Map to a trajectory archetype

Once we have the thesis, match it to one of these five (verbatim from `research/PITFALLS.md` §5.1). Each archetype has its own "what good looks like" — the rubric grades against the archetype, not against a universal senior bar.

### Archetype 1 — Research-deep IC

**The trajectory:** Long-running embedded research, qualitative breakthroughs, owns the research practice on the team, often the person product comes to when the question is "what don't we know yet?"

**What makes it legible:**
- Case studies that open with the question, not the design
- Research artifacts that are decision artifacts, not deliverable artifacts (a synthesis that changed the roadmap, not a research-readout deck)
- Evidence of methodology choice, not just methodology execution ("we used diary studies because the behavior was rare and contextual" — not "we ran 12 interviews")
- Long tenure on a problem space (years, not weeks)
- Outcomes framed as understanding shifts, not conversion lifts

**Don't confuse with:** a generalist who occasionally runs research. The research-deep IC owns the practice; the generalist participates in it.

### Archetype 2 — Design-systems lead

**The trajectory:** Scaled tokens, components, governance, and adoption across N teams. Often promoted from product designer into systems lead. Influence is measured in adoption, not in product launches.

**What makes it legible:**
- Adoption metrics (teams using, components deployed, design-debt-removed PRs)
- Governance evidence (RFC processes, working groups, contribution models)
- Cross-org collaboration documented (engineering partners, design org partners)
- Migration case studies (deprecating old, rolling out new, with timelines)
- A through-line about *system* and *legibility*, not individual screen polish

**Don't confuse with:** a designer who built a Figma library. Library ≠ design system. Adoption + governance is the difference.

### Archetype 3 — 0-to-1 founder-shaped

**The trajectory:** Early-stage product designers, ambiguity-tolerant, scope-broad. Often the first design hire at multiple companies. Comfortable with "no PM, here's a one-pager, ship v1 in six weeks."

**What makes it legible:**
- Case studies that show the problem-finding, not just the problem-solving
- Evidence of scope expansion (not just design — also product, brand, ops)
- Founder/CEO collaboration documented (named, with the specific bet)
- Output diversity (a v1 product flow + a landing page + an onboarding sequence + a brand foundation, all shipped by the same person)
- Failure case studies (because 0-to-1 ships fail more often than scale ships, and senior 0-to-1 designers know this)

**Don't confuse with:** a junior at a startup. Both touch many things. The 0-to-1 senior shows decisions about what to build and what to NOT build; the startup junior shows execution across many surfaces.

### Archetype 4 — Generalist-broadening

**The trajectory:** IC who's broadening into product + ops + research. Often a designer who's three years into a role and has started owning things adjacent to design — running standups, writing PRDs, scoping research, doing competitive analysis.

**What makes it legible:**
- Case studies that document cross-functional ownership ("I owned the PRD" / "I ran the research synthesis" / "I scoped the engineering spike")
- A range thesis explicitly named ("I do design + product + research" — the user names this)
- Mentions of work that isn't strictly design output (decks, strategy docs, competitive matrices)
- Evidence of the user being the connector across functions

**Don't confuse with:** a generalist who hasn't differentiated. A senior generalist names the broadening explicitly. A junior generalist looks like they're doing too many things because they don't know where to focus.

### Archetype 5 — Manager-returning-to-IC

**The trajectory:** Has led teams (4-12 designers), managed performance, run hiring, built design org structure. Choosing to go back to IC because the ship pulse matters more than the org chart. Needs to demonstrate they can still ship.

**What makes it legible:**
- A clear, named pivot in the about page ("After three years managing, I'm choosing IC again because…")
- Recent shipped work, not just managed work (within the last 12-18 months — older than that and the "still ships" claim weakens)
- Both managerial signals (mentorship, hiring, org-building) AND craft signals (recent screens, recent flows, recent prototypes) — both visible
- A clear scope-down posture ("I'm not looking for a Staff IC; I want senior IC")
- Honesty about why — not defensive, not over-explained

**Don't confuse with:** a manager job-searching for a manager role. The returning-to-IC archetype is specifically a craft-and-pulse story; the manager job search is an org-building story.

---

## Step 3 — Apply the ADPList 6-axis (against the user's thesis)

From `research/DOMAIN.md` §4: ADPList's senior framework names six axes. The mid → senior shift is not a craft upgrade; it's a scope and influence upgrade. Drawing and coding skills don't differentiate senior from mid — people and strategic skills do.

Apply each axis as: "given the user's thesis is X, do they have evidence on axis Y?" Never "you should have evidence on axis Y."

The six axes:

### Axis 1 — Product Thinking

Understanding business opportunity, not just user needs. The case study opens at the bet (the business question), not the design (the screen).

- Given the user's thesis, do the case studies open at the bet?
- Is there evidence the user understood the business model — pricing, growth loop, unit economics, retention curve — at the level their thesis claims?

For a research-deep IC, this looks like research questions tied to business decisions. For a design-systems lead, it looks like adoption framed as engineering velocity, not as design consistency. Different shapes per thesis.

### Axis 2 — Intentionality

Consistent process and communication. Does the user's process repeat across case studies (signaling a deliberate practice), or does each case study look improvised?

- Does the user name their process or method? Is it consistent enough across cases to read as a real practice?
- For their thesis, is the level of process visibility right? (A 0-to-1 thesis with heavy process documentation reads as wrong. A research-deep thesis with no process documentation reads as wrong.)

### Axis 3 — Drive

Leadership, mentorship, community. Sphere of influence beyond the immediate team.

- Does the user show evidence of leading without title? Mentoring? Community contribution?
- For their thesis, is this the right kind of leadership? (Design-systems lead → cross-org RFCs and governance. 0-to-1 → founder collaboration and team-shaping. Manager-returning → past management evidence still visible.)

### Axis 4 — Craft

(Implicit in ADPList; explicit in most company rubrics.) Visual, interaction, prototype, and detail craft at the level the thesis demands.

- Given the user's thesis, is the craft floor met? (A research-deep thesis has a lower visual-craft floor than a 0-to-1 thesis. A systems thesis has a higher detail-and-consistency floor than either.)
- Is the craft *shown* in the right place? A senior portfolio doesn't open with craft — it opens with the bet — but craft has to be visible somewhere or the case study reads as a decision-doc with no design.

### Axis 5 — Collaboration

Cross-functional partnership — engineering, product, research, marketing, leadership. The senior signal is influence without authority.

- Does the user document who they collaborated with, by role and by named decision (not by name)?
- For their thesis, is the collaboration story coherent? (A design-systems lead with no engineering partner story is incoherent. A research-deep IC with no PM-and-engineer translation story is incoherent.)

### Axis 6 — Outcome ownership

Post-launch. What happened 3-6 months after the work shipped? What metrics moved? What failed?

- Does at least one case study extend past launch?
- For their thesis, is the right kind of outcome shown? (Research-deep → understanding shifts and decision changes, not conversion. Systems → adoption curves. 0-to-1 → MAU, retention, or honest "the company pivoted" framing.)

---

## Step 4 — Surface coherence gaps

This is where most senior portfolios actually fail. Not "missing axis Y" — *coherence*. The user states one thesis and the work argues another.

Common patterns:

**Pattern A — Thesis says systems, work says product.**

> Your stated thesis is design-systems lead — your about page names tokens, governance, adoption. But four of your six case studies are 0-to-1 product flows. Either re-thesis around the product work ("0-to-1 product designer who's also done systems work"), or replace two case studies with systems-shaped work — adoption rollout, deprecation case study, RFC-driven token migration. Right now the hero promises one thing and the body delivers another.

**Pattern B — Thesis says senior, work says mid.**

> Your case studies open at execution — "I was assigned…" / "the PM gave me…" / "we needed to redesign…". For your thesis (senior IC), they should open at the bet — what was unclear, who decided to invest in it, why this was the strategic move. Right now the case studies argue for a mid promotion, not a senior one.

**Pattern C — Thesis says strategic, work shows process.**

> The about page names strategic impact and cross-org influence. The case studies are heavy on research methodology and design iteration steps. For your thesis, the strategic context — what the company was betting on, what got de-prioritized, what you decided NOT to build — should be the loudest layer. Process is the second layer.

**Pattern D — Thesis says NDA-bound, no signal anywhere.**

> Your thesis (senior at a company you can't show work from) is real and common. But the portfolio shows two pre-current-job case studies and zero current-job signal. Even NDA-bound work can show: scope ("led design for a 12-engineer team across two product surfaces"), system ("owned the design-review process for 8 designers"), outcome at the org level ("reduced eng-design back-and-forth by 40%, measured via PR-revision count"). Right now the portfolio is silent on the most recent two years.

When you see a coherence gap, name it directly:

> Your stated thesis is X. Your strongest evidence is Y. Either re-thesis around Y, or replace 2 case studies with X-shaped work.

This is the most useful single move in a senior review. Most users haven't asked themselves "does the work argue what the about page argues?"

---

## Step 5 — Promotion-track-specific signals

Senior promotion materials have a unique problem set the senior job-search materials don't have. Cover them explicitly when they apply.

### NDA work (current employer, can't show details)

Senior portfolios are often promotion-track or recently-departed-from-employer. The strongest work is usually NDA-bound. Junior advice ("ship something public, even small") doesn't apply at this level — the user has shipped real things, just not publicly.

How to talk about NDA work without violating it:

- Name the **shape** of the work without naming the product. ("Led the redesign of a B2B sales-tooling flow at a Series-C SaaS company.")
- Name the **scope** without naming the surface. ("Owned IA, interaction design, and rollout across 3 product surfaces, partnering with 12 engineers and 2 PMs.")
- Name the **outcome** at the right level of abstraction. ("Reduced sales-cycle drop-off by 22% in the test cohort" — without naming the company, the product, or the specific feature.)
- Use **before/after framing without screens.** A flow diagram, a process diagram, or a structural sketch can carry the story without leaking the UI.
- When asked, **walk-through framing**: "the portfolio sets the stage; the interview conversation is where the depth lives."

### Scope-signaling without humble-bragging

The senior signal is scope. The trap is sounding like a LinkedIn post.

- **Bad:** "Led design for a high-impact, high-visibility initiative spanning multiple cross-functional teams."
- **Good:** "Led design for a 12-engineer 2-PM team migrating 4M users from v1 to v2 over 7 months."

Use specific numbers. Specific numbers don't read as bragging — they read as scope evidence. Vague superlatives ("high-impact," "transformative," "cross-functional") read as filler.

### Leadership without authority

The senior IC sells leadership without title. Without "Manager" in the title, the user has to show it through the work.

Evidence to look for:
- Mentorship documented by named relationship (not by name): "Onboarded 3 designers in the last 18 months, two of whom were promoted within the year."
- RFCs or design proposals authored that other teams adopted.
- A design-review or critique practice the user owns.
- A working group, guild, or community-of-practice the user runs.
- Decisions named where the user influenced engineering or product without being the decider.

### The "promotion-track portfolio" problem

Often the user can't make their portfolio public — promotion review is internal, the materials reference internal product details, and external publication risks the relationship. Frame this for the user:

> If this portfolio is for an internal promotion review, the audience is your manager and your skip-level — not a recruiter. The structure flips: you can name the company, the team, the metric. You don't need NDA-shaped framing. The risk inverts — too much abstraction reads as evasion. State the work plainly.

If the same portfolio has to do double duty (promotion review *and* future external job search), the user has a real problem. Recommend two versions: one internal, one external.

---

## Senior resume rubric

Senior resumes are simpler structurally than junior ones (fewer sections, less to prove) but harder to write. The bar is scope language, not outcome verbs.

### Scope verbs (use these)

Led, owned, shipped, scaled, drove, partnered, established, restructured, defined.

Avoid:
- "Designed" without modifier (every designer designed)
- "Worked on" / "Contributed to" (low-agency)
- "Responsible for" (passive, junior register)
- "Helped" (anywhere)

### Measurable scope (specific numbers, not superlatives)

- Team size led — "Led design for a 4-designer pod" / "Mentored 6 designers"
- Engineering partner ratio — "Partnered with 12 engineers across 3 squads"
- Customer base / scale — "4M MAU" / "$200M ARR" / "200-engineer org"
- Time horizon — "18-month migration" / "Q3 2024 launch through Q2 2025 stability"
- Cross-org reach — "Adopted by 8 product teams" / "Influenced 3 quarterly OKRs"

If a bullet has no number, ask whether it's load-bearing. Most senior bullets without numbers can be cut.

### Reverse-chronological forcing function

The most senior signal — biggest scope, broadest influence — should be at the top. If the user's most senior work is 3 years old and their last 18 months are weaker, the resume undermines itself.

Fix: either lead with the older work explicitly framed ("Most recent senior IC role; current role is a managerial pivot") or restructure the bullets within the recent role to surface the senior signal that's there.

### "What changed because of you" language, not "what I did" language

- **Bad:** "Designed a new onboarding flow."
- **Mid:** "Designed a new onboarding flow that reduced drop-off by 18%."
- **Senior:** "Owned the redesign of onboarding for a $200M-ARR SaaS — drop-off fell from 38% → 22%, the new pattern was adopted across 3 product surfaces, and the engineering partnership produced a reusable Auth flow library."

The senior bullet shows: scope (you owned it, didn't just designed it), measurable change (drop-off), org-level adoption (other surfaces), and second-order outcome (a library that outlived the project).

### Length

- 5-10 years experience: 1-2 pages.
- 10+ years: 2 pages, max.
- One page is fine if the work is dense enough; two pages is fine if every bullet earns its line.

If the resume is longer than 2 pages and the user isn't applying for a CV-format role (academic, research, principal at a research institution), cut.

### Common senior resume flags

- **Manager-shaped bullets in an IC application** — "Hired 4 designers, ran performance reviews" reads as a manager applying for IC. Reframe or cut.
- **Tool list dominates the skills section** — Senior resumes don't sell on tools. Trim the tool noun salad and add scope language.
- **Recent role is thin** — If the last 18 months has 2 bullets, the resume reads as "I'm coasting." Either flesh out (find scope language for the work that was done) or address the thinness directly.
- **Title inflation visible in role progression** — Going from "Senior Designer" at a Series-A to "Designer II" at a Series-C reads as a downgrade. Frame the move ("joined for the staff trajectory" / "domain pivot").

---

## The Top-3 fixes pattern (senior shape)

Senior Top-3 is more prescriptive than the rest of the rubric — the user has earned bluntness. Each fix follows the voice.md §3 templates.

The Top-3 should call out:

1. **Thesis** (if missing or weak). The thesis fix is always position #1 if it applies. Without thesis, the rest of the review is sand.
2. **One case study to replace or upgrade.** Specific case study, named. The fix is concrete: "Cut the e-comm checkout case study; replace with the Series-C systems work — scope it, name the partners, show one diagram." Or: "Upgrade the [project name] case study by moving the bet to the top and adding a 6-month-after section."
3. **One resume bullet pattern to fix.** Specific bullet, quoted verbatim. The fix is the rewrite, in scope-verb + measurable-scope + outcome shape.

### Template

```
Top 3 fixes:

1. Thesis: [problem statement]. [cost]. [fix].
   Quote example: "Right now the hero says 'product designer with strategic range' — that doesn't tell us what kind of senior. Pick: 'I'm the [archetype] who [scope]' and rebuild the about page around it."

2. Case study to [replace / upgrade]: [project name]. [why it's the weakest or the wrong-shape one]. [the move].
   Quote example: "Replace the [project name] case study. It opens at execution and reads as mid-level work — for your thesis (research-deep IC), it should open at the question that drove the bet. Either rebuild the opener or cut it and write up the [other project] research instead."

3. Resume bullet to fix: "[verbatim bullet]." [diagnostic question]. [rewrite with scope verb + scope number + outcome].
   Quote example: "Bullet says 'Designed checkout flow for Series-C SaaS.' Designed how, for whom, with what result, and at what scope? Rewrite: 'Owned redesign of checkout for a 4M-MAU Series-C SaaS — partnered with 6 engineers across 2 squads, drop-off fell from 38% → 22% in Q3 2024, the pattern was adopted across 3 surfaces.'"
```

Senior reviews can be MORE direct in the Top-3 — the audience has earned bluntness. But "no roasting" still holds (voice.md §6, anti-roast hard rule). Bluntness ≠ roasting. Bluntness names the choice and the cost; roasting names the person.

If a Top-3 item would land as a roast, it's wrong, not the rule.

---

## Diagnostic vs. prescriptive — the key difference

Junior rubric (`rubric-junior.md`): *"every case study needs an outcome paragraph."*

This rubric: *"your case studies open at execution; for your thesis, they should open at the bet."*

The senior rubric never says "every senior should." It always says "given THIS senior's thesis is X, they need Y."

When in doubt, re-anchor on the user's thesis. If the workflow is producing senior-feedback that would apply to any senior, the workflow is doing junior-shaped feedback in senior clothing — back up and re-extract the thesis.

---

## How a workflow uses this rubric

`workflows/review-portfolio.md` and `workflows/review-resume.md` consume this file when the user has selected the senior career-stage branch. The workflow's first move is to apply Step 1 (extract thesis) before any flagging or rewriting. Step 2-5 produce the body of the review. The Top-3 pattern produces the priority section. `common-flags.md` is consulted for repeating patterns the user might also have, but flags from there only fire if they're consistent with the user's thesis. The combined-review workflow runs both the resume and portfolio passes, then surfaces coherence gaps between resume bullets and case-study claims.
