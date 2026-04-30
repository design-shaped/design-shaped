# Frameworks — Portfolio Rx

## How this file is used

The voice.md §9 frameworks-by-name protocol mandates: when a workflow applies a framework, it names the framework verbatim, quotes specifics from the user's work, and cites this file's section. NEVER paraphrase a framework. NEVER re-teach it inline.

Workflow agents read only the section they need. Each framework here is self-contained: name, when to use, structure (in the source's words), how to apply to a portfolio review, and source citation. The section anchor is the citation target — `See: references/frameworks.md#slicing` is a valid hand-off.

Two voice rules to honor when surfacing a framework:

1. **Name it on first use.** "This case study skips the *outcome* in **Problem → Process → Outcome**." Never "this lacks a P→P→O outcome" without spelling out P→P→O once.
2. **Quote the user's work, then frame.** The pattern is: pull the user's exact bullet or paragraph, then name the framework step it skips, then provide the rewrite. Never frame in the abstract.

### Worked example of the protocol

A user submits a case study where the closing line is: "We presented the final designs to the team and got positive feedback." A workflow agent applies the protocol:

1. **Quote the user's work:** "Your case study closes with: *'We presented the final designs to the team and got positive feedback.'*"
2. **Name the framework verbatim:** "This skips the **Outcome** in **Problem → Process → Outcome**."
3. **Hand off to the rewrite without re-teaching:** "Replace the closing line with three lines — what shipped, what changed, what you'd do differently."
4. **Cite the source line:** "See: `references/frameworks.md#problem-process-outcome`."

That four-step loop is the entire mechanic. The workflow agent does NOT explain what P→P→O is in the review output — the user can read the framework section if they want. The workflow agent's job is to name the gap, quote the work, and prescribe the fix.

When in doubt: name two frameworks, not zero. Per voice.md self-check: "At least 2 frameworks are surfaced by name." A review with no framework names reads as generic LLM critique; a review with one framework names reads as competent; a review with two or three reads like Tim and Nate.

---

## Index

**Case study + portfolio narrative frameworks** (the spine — every workflow touches at least one)

- [STAR](#star) — Situation, Task, Action, Result; the resume + interview baseline
- [Problem → Process → Outcome (P→P→O)](#problem-process-outcome) — the dominant case-study structure; NNg standard
- [Inverted Pyramid](#inverted-pyramid) — outcome-first; corrects process-heavy case studies
- [van Schneider's 300-Character Summary Constraint](#vanschneider-300-character-summary) — anti-template; force the punchline first
- [Brian Lovin's Ownership Language](#brian-lovin-ownership-language) — direct vs. team contributions; honesty as senior signal

**Design + product frameworks Nate teaches** (the moat — these are why this skill exists)

- [Slicing](#slicing) — Nate's iteration-sized deliverable system; ports cleanly to case-study scope
- [Stakeholder Needs Map](#stakeholder-needs-map) — six roles, six "needs to know" prompts; portfolio audit lens
- [The 80% Principle](#the-80-percent-principle) — ship at 80% satisfaction; portfolio "perfection paralysis" cure
- [Dual Track Agile](#dual-track-agile) — designer one or two slices ahead, never more
- [Brand Drivers](#brand-drivers) — Functional / Economic / Emotional / Self-Expressive 4-column method
- [Ethos / Pathos / Logos](#ethos-pathos-logos) — Aristotle's three pillars as a sales/UX diagnostic
- [Ladders](#ladders) — your rung dictates your strategy; reframe portfolio "positioning"
- [Two-Filter Research Method](#two-filter-research-method) — qual/quant + attitudinal/behavioral
- [Proto Persona](#proto-persona) — assumption-built persona; prioritize speed over accuracy
- [Component Library → Design System Progression](#component-library-design-system-progression) — don't build a system until the library holds you back
- [House Analogy](#house-analogy) — Waterfall vs. Agile in one image
- [Lean / Agile / Scrum](#lean-agile-scrum) — three terms people conflate, separated cleanly
- [Three Pillar System](#three-pillar-system) — accessibility's three pillars; AI collapses two

---

## STAR {#star}

**Use when:** Reviewing a resume bullet or an interview-style case-study walkthrough that lacks a clear outcome. STAR is the lowest-common-denominator structure every recruiter recognizes — if a bullet can't survive a STAR rewrite, it's hiding.

**The structure:**

- **Situation** — what was the context and problem
- **Task** — your specific role and objective
- **Action** — what you did (design process, decisions made)
- **Result** — measurable outcomes

**Apply to a portfolio:** STAR is the resume rewrite tool. When a bullet reads as activity-only ("Designed checkout flow"), reach for STAR and ask which beat is missing. The "Action" beat is usually present; "Situation" and "Result" are usually missing. Force both back in.

*This bullet skips the **Result** in **STAR**. Bullet says: "Designed checkout flow for SaaS product." Hiring manager sees activity, no impact — bounces. Rewrite: "Redesigned checkout for [N]M-MAU SaaS to fix 38% drop-off (Situation/Task). Restructured the address-confirmation step and added inline validation (Action). Drop-off cut from 38% → 22% in the test cohort over 6 weeks (Result)."*

A second example for the **Situation/Task** beat. A bullet that says "Led design for the new mobile onboarding" skips Situation. The reader doesn't know why the redesign was needed — was the old onboarding broken? Was this a new product? Was this a competitive response? Per **STAR**, name the Situation in the bullet itself: "Led design for new mobile onboarding after activation dropped 18% post-redesign." Now the bullet has stakes.

For case-study walkthroughs, STAR works best as a sanity-check skeleton, not a final structure — see [Problem → Process → Outcome](#problem-process-outcome) for case-study-shaped storytelling. STAR's failure mode at scale is formulaic-ness: ten bootcamp portfolios all written to STAR start to read identically. We use STAR to fix bullets, not to template a full case study.

For mock-interview prep, STAR is also the structure to default to when answering behavioral questions. "Tell me about a time you disagreed with a stakeholder" → walk it through STAR. The Action beat is where most candidates get long; trim it to two sentences and protect the Result beat.

**Source:** General interview coaching canon. Codified for design by community writers — e.g., [Carl Wheatley, "Structuring Your Product Design Case Studies Using The STAR Method"](https://carlwheatley.medium.com/structuring-your-product-design-case-studies-using-the-star-method-34eaae5c2de0). Public-domain rubric.

---

## Problem → Process → Outcome (P→P→O) {#problem-process-outcome}

**Use when:** Reviewing any case study. P→P→O is the default rubric we walk every case study against. If a case study is missing one of the three, this is the first flag.

**The structure (NNg / IxDF codification):**

1. Problem statement (user + business framing)
2. Your role and collaborators
3. How you developed solutions (research methods, iterations, what you rejected and why)
4. Challenges and constraints
5. Results — user impact + business impact
6. Lessons learned

NNg surveyed 204 UX hiring professionals. Their finding, verbatim: hiring managers want to see "how you started with an opportunity and produced real value for a user and the organization" — not just the final output. Final screenshots only tell part of the story.

**Apply to a portfolio:** Walk every case study against the three beats — name which one is thin or missing. The most common failure is **outcome thinness**: pages of process, two sentences of result. The second most common is **problem framing absent**: the case study opens on the Figma file, not the user-or-business problem. The third is **process inflation**: every research artifact dumped in chronological order with no decisions visible.

*This case study skips the **Outcome** in **Problem → Process → Outcome**. The "Spotify-for-podcasts redesign" case study has six scrolls of personas, journey maps, and wireframes, then ends: "We presented final designs to the team." Hiring manager finishes the scroll with no idea what shipped, what changed, or what you'd do differently. Rewrite: replace the closing line with three lines — what shipped (or didn't), what changed in user behavior or business metrics (qualitative is fine if quant isn't available — be honest about which), and one specific thing you'd do differently. Move that block to immediately after the problem statement and again at the end.*

For senior portfolios, the P→P→O frame extends — see [Inverted Pyramid](#inverted-pyramid) for the senior-shaped variant where outcome leads.

**Common pitfalls when applying this framework:**

- **Treating P→P→O as a template, not a rubric.** Every case study needs the three beats; the order, weight, and shape can vary. Don't enforce a six-section template.
- **Confusing "process" with "documentation dump."** Process is decisions made, alternatives rejected, what you learned. Process is NOT a chronological list of every research artifact you created.
- **Treating "outcome" as "the metric."** Outcome can be qualitative (user behavior changed in this specific way) or qualitative-with-metric (user behavior changed AND we measured X). What it can't be is "the team liked it."

**Source:** [Nielsen Norman Group, "UX Design Portfolios"](https://www.nngroup.com/articles/ux-design-portfolios/) and [IxDF, "How To Write Great Case Studies for Your UX Design Portfolio"](https://ixdf.org/literature/article/how-to-write-great-case-studies-for-your-ux-design-portfolio). Public-domain rubric.

---

## Inverted Pyramid {#inverted-pyramid}

**Use when:** A case study has all the ingredients but reads in the wrong order. Outcome buried, problem buried, "lessons learned" tucked at the bottom where no one scrolls. Inverted Pyramid is P→P→O re-stacked for skim behavior.

**The structure (UXFolio's framing):**

Lead with the most important thing. Put problem-solution-impact chain first and immediately visible. Then expand into process below. The shape is journalism's: top of the pyramid = the news (what happened, who, impact). Below that = context, evidence, supporting detail. At the bottom = nice-to-haves a deep reader will reach.

UXFolio's stat: 54% of hiring managers spend 5–10 minutes on a portfolio; 35% spend only 5 minutes. If your core logic chain is buried under three scrolls of research artifacts, you've failed the structure test.

**Apply to a portfolio:** This is the "skim test" rewrite. Walk every case study against the first-screen test — within the first scroll (or first slide), does the reader see problem + outcome? If not, restructure. The fix is rarely "delete the process" — it's "lead with the punchline, then expand into the process for the deep readers."

*This case study buries the **outcome** per **Inverted Pyramid**. The outcome paragraph is in scroll 6 of the [project name] case study. Move it to scroll 1, right under the problem framing. Hiring managers skim — if they don't see a result in 15 seconds, they're gone. Standard rewrite shape: hero image / problem one-liner / outcome one-liner / role + team / then drop into process below the fold.*

The frequent misread: "lead with outcome" gets confused with "skip the process entirely." It doesn't. The process still belongs in the case study — it just doesn't open the case study. This pairs with [Problem → Process → Outcome](#problem-process-outcome) — same content, different order of presentation.

**Source:** [UXFolio Blog, "UX Case Study Structure"](https://blog.uxfol.io/ux-case-study-structure/). Public-domain framing — "inverted pyramid" itself is journalism canon (lede first, supporting detail below).

---

## van Schneider's 300-Character Summary Constraint {#vanschneider-300-character-summary}

**Use when:** A case study sprawls and the user can't tell what the case study is *about*. van Schneider's anti-template critique gives a forcing function: write the 300-character summary first, before drafting the case study itself. If you can't write 300 characters that hook a reader, the case study isn't ready yet.

**The structure (Tobias van Schneider's recommendations, verbatim from "The Old Case Study Is Not Working"):**

His core argument: the "challenge, user journey, sketches, result" template has expired. "Nobody's reading them." Recruiters spend under 10 seconds scanning; rigid templates produce homogeneous portfolios.

His recommendations:

1. Draft a 300-character summary first — forces you to identify the single most compelling aspect.
2. Lead with visuals — "your visuals will do 90% of the heavy lifting."
3. Write captions that tell the story on their own — if someone only reads captions, they should understand the project.
4. Design each case study like a magazine feature — custom color, compelling hook, distinctive layout.
5. Emphasize personal strengths, not process — "everyone's process is somewhat the same."

**Apply to a portfolio:** Use the 300-character summary as a cross-check before any case-study rewrite. If the user can't write 300 characters that capture the project's hook, the case study itself won't land. This is the diagnostic version of [Inverted Pyramid](#inverted-pyramid) — same intent (lead with the punchline) but with a hard character constraint that exposes vagueness fast.

*This case study fails the **300-character summary constraint** per **van Schneider's** anti-template critique. We asked: "What's this case study about, in 300 characters?" The user said: "It's about how I redesigned the onboarding flow for a SaaS product to improve activation." That's 90 characters of summary and 210 characters of room left over — but the summary itself is generic ("improve activation" could apply to any project). Rewrite the summary first. "Cut SaaS onboarding from 9 steps to 4. Activation rate moved from 31% to 47% in 6 weeks. Engineering pushed back on cutting the address-confirmation step; I argued for the cut and was wrong — it cost us EU compliance review later." That's 290 characters and the case study now has a hook (the productive failure).*

van Schneider's "magazine feature" recommendation is more relevant for senior portfolios where visual identity is part of the differentiation. For early-career portfolios, the 300-character constraint is the part to lean on.

**Source:** [Tobias van Schneider, "The Old Case Study Is Not Working"](https://vanschneider.com/blog/portfolio-tips/the-old-case-study-is-not-working/) and [DESK Magazine, "Write Project Case Studies"](https://vanschneider.com/blog/portfolio-tips/write-project-case-studies-portfolio/).

---

## Brian Lovin's Ownership Language {#brian-lovin-ownership-language}

**Use when:** A case study uses "we" throughout and we can't tell what the user specifically did. Brian Lovin's portfolio philosophy is the corrective: be explicit about direct vs. team contributions. "It's easy for interviewers to spot undeserved credit."

**The structure (Brian Lovin's principles, from "Product Design Portfolios"):**

- Standalone portfolio site strongly preferred over Dribbble/Behance hosting — signals craft investment.
- Be explicit about direct vs. team contributions — "it's easy for interviewers to spot undeserved credit."
- Be forthcoming about where smaller contributions fit within larger team effort — humility plus honesty signals maturity.
- Simple visual language; portfolio should be accessible, useful, and inspiring to interact with.
- Cross-functional collaboration evidence matters — "great designers understand software development is a team sport."

**Apply to a portfolio:** The ownership-language test is one of the most-applied frameworks in our review reps. Walk every "we" in a case study and ask: did this person actually do this, or are they riding on a team contribution? The fix isn't to scrub "we" — it's to be precise. "I led the X. The team owned Y. I contributed Z to the broader effort." That sentence shape signals seniority — humble about scope, honest about contribution, clear about ownership.

*This case study uses "we" exclusively per **Brian Lovin's Ownership Language**. The redesign-of-checkout case study says: "We researched, we designed, we shipped, we measured." We can't tell what the user specifically did — and per Brian Lovin, "it's easy for interviewers to spot undeserved credit." Rewrite by separating the three contributions cleanly: "I owned the address-confirmation step (sole designer). The team (PM, two engineers, one researcher) owned the broader flow. I contributed to the kickoff strategy and the post-launch retro on cart-abandonment." That's three sentences and the ownership map is now legible.*

A second example — the "smaller contribution to a larger team effort" framing. When a designer worked on a recognizable big-name product but only owned a small slice, the temptation is to over-claim. Per Brian Lovin, the move is to be forthcoming: name the slice precisely and contextualize it. "I worked on the [Big Product] team for 18 months. Owned the empty-state system across mobile (the 14 screens shown). The team of 30+ designers owned the app overall. I influenced the larger empty-state pattern that was adopted across web after my mobile work shipped." That paragraph signals maturity; the alternative — "I designed [Big Product]" — gets clocked as undeserved credit and tanks the rest of the portfolio's trust.

For mock-interview prep, expect the test question: "Walk me through what you specifically did on this project." The candidate who has practiced ownership-language framing handles it cleanly; the candidate who relied on "we" gets caught in vague backpedaling. The fix is to rehearse it during portfolio prep, not during the interview.

This pairs with the senior rubric's "Leadership sway documented" beat (DOMAIN §4) — being precise about ownership is the foundation that lets leadership claims land. A senior portfolio with no ownership clarity reads as a mid-level portfolio with a senior title, even if every project is real. Conversely, a mid-level portfolio with crisp ownership language often reads more senior than its title suggests, because the precision itself is a maturity signal.

**Source:** [Brian Lovin, "Product Design Portfolios"](https://brianlovin.com/writing/product-design-portfolios) and ["How to Give a Great Product Design Portfolio Presentation"](https://brianlovin.com/writing/how-to-give-a-great-product-design-portfolio-presentation).

---

## Slicing {#slicing}

**Use when:** Reviewing a senior or promotion-track portfolio where case studies read as monolithic "I did this whole project" walls. Slicing is the tool to reframe scope into iterations — and the iteration framing is what separates execution-only senior portfolios from strategic-narrative ones.

**The structure (Nate's words, verbatim from "An Introduction To Slicing"):**

Each slice is a single Figma deliverable that contains:

- **Visibility of designs** + **Documentation** (numbered, labeled inline on the design)
- **Slice Description** (intro paragraph stating the iteration's objective)
- **Approvals/Sign-offs**
- **Multiple Slices** (each as a separate Figma page, numbered)

Color-coding system for features within a slice: new / pre-existing / under review / slated for removal. Verbatim: "Slice 1: Document and label new features. Slice 2: Change existing features from green to black to label them as already existing. Add new features as green. Slice 3: Same as slice 2."

Slice approval state shows on the page title:

- **Green:** "approved by all stakeholders and is ready for the next steps — traditionally breaking the slice into stories."
- **Yellow:** "doesn't have approvals but is ready for review."
- **Red:** "in design and doesn't have approvals."

The final slice is the **Release Candidate**. Verbatim: "every iteration and slice should be viewed as a minimum viable product" until you decide to ship.

Headline rule, also verbatim: "our main objective should be tackling outcomes and not outputs."

**Apply to a portfolio:** Slicing is the lens for any case study where the designer says "I worked on this for nine months." Ask: what was Slice 1? What did Slice 1 ship? What did Slice 1 *learn* that changed Slice 2? If the answer is "we ran one big handoff at the end," that's a process flag — and it's a senior-signal flag, because senior designers ship and learn in iterations, not in a single drop.

*This case study compresses six months into one block — no **slices** visible per **Slicing**. The "internal CMS redesign" reads as: research, design, ship. We can't tell what shipped first, what you learned from it, or what you cut between iterations. Rewrite: structure the case study as 2–3 named slices. "Slice 1: replaced the editor for power users; learned the inline-preview pattern broke for our QA team. Slice 2: forked the editor for QA mode; killed the inline-preview path." This shows iteration thinking, which is what senior portfolios miss most.*

A second portfolio application: Slicing's **Release Candidate** framing. Nate's verbatim: "every iteration and slice should be viewed as a minimum viable product" until you decide to ship. For portfolio review, this means a senior case study should be able to answer: which slice was the Release Candidate? What made that slice the one we shipped, vs. the prior iterations we ran past it? If a designer can't name their Release Candidate, they were doing waterfall, not iteration — see also [House Analogy](#house-analogy).

Slicing pairs with [Stakeholder Needs Map](#stakeholder-needs-map) (the table that powers it) and [Dual Track Agile](#dual-track-agile) (Nate's slicing rhythm rule). For portfolio review, the Stakeholder Needs Map version is more often actionable; we apply Slicing itself when scope is the live issue.

Headline rule worth quoting back in any senior review, verbatim from Nate: "our main objective should be tackling outcomes and not outputs." If the case study lists outputs (Figma files, decks, mocks) without naming the outcomes those outputs created, that's the gap. The fix isn't more outputs in the case study — it's surfacing the outcomes the existing outputs produced.

**Common pitfalls when applying Slicing to portfolio review:**

- **Forcing slices retroactively.** If the actual project was waterfall, don't dress it up as Slicing. The honest move is to note the project was waterfall and discuss what the user would do differently — that itself is a senior reflection.
- **Confusing "slices" with "sections of a Figma file."** Slicing is about iteration units that ship and learn. A slice that never shipped is a draft, not a slice.
- **Skipping the Release Candidate naming.** Without naming which slice was the RC, the case study reads as parallel work with no convergence point.

**Source:** Nate Bauer, ["An Introduction To Slicing"](https://nabauer.com/articles/slicing). Slicing is Centene-proprietary ("our proprietary methodology") but Nate publishes the full method on his site, so it's safe to cite verbatim. "And that's Slicing in a nutshell." (his close)

---

## Stakeholder Needs Map {#stakeholder-needs-map}

**Use when:** Auditing whether a portfolio (the whole site, not just one case study) communicates to the *full* set of readers it needs to. The single most directly portfolio-applicable framework Nate teaches — translates one-to-one to "who reads a portfolio and what do they each need."

**The structure (verbatim "Needs to know" prompts from "An Introduction To Slicing"):**

| Stakeholder role | Needs to know |
|---|---|
| Product Manager | "Which features are completed or being worked on?" |
| Product Owner | "Are the correct problems being solved?" |
| Developers | "What should I work on?" |
| Stakeholder | "What's the momentum?" |
| Other UX Designers | "What should I work on?" |
| User | "Are my problems getting solved?" |

**Apply to a portfolio:** Re-cast the six roles for portfolio review. The portfolio's stakeholders are: recruiter, hiring manager, IC interviewer, future teammate, future cross-functional partner (PM/eng), the user of the work shown. Each has a different "needs to know":

- **Recruiter:** can I tell what level this person is in 10 seconds?
- **Hiring manager:** is there shipped work, and what was the impact?
- **IC interviewer:** can I see how they make decisions under constraint?
- **Future teammate:** would I want to work with this person?
- **PM/eng partner:** do they understand non-design tradeoffs?
- **User of the shipped work:** is there evidence the user's problem actually got solved?

Walk the portfolio against the six. Most portfolios answer 2 or 3 of the six. The unanswered ones are the audit gaps.

*This portfolio answers the **hiring manager** and the **future teammate** in the **Stakeholder Needs Map**, but skips the **IC interviewer**. We can see what shipped and we can see you'd be pleasant to work with, but no case study shows a tradeoff you owned — no "we had two options, here's why I picked the one we picked, here's what we gave up." For the IC-interviewer signal, add one paragraph per case study on a decision you owned and the alternative you rejected.*

A second example: most career-switcher portfolios skip the **future cross-functional partner**. The case studies show user research and design work, but no evidence the designer can talk to engineering or product on their own terms. Per **Stakeholder Needs Map**, the PM/eng partner asks: "Do they understand non-design tradeoffs?" Rewrite by adding one sentence per case study about a tradeoff you discussed with engineering or PM — what they pushed back on, what you adjusted, what you held the line on. That sentence answers the cross-functional partner's question and is the senior signal that's almost always missing in switcher portfolios.

This is the lens we reach for first when asked "review my whole portfolio holistically." Individual case studies use [Problem → Process → Outcome](#problem-process-outcome); the body of work uses Stakeholder Needs Map.

The "What's the momentum?" prompt (the Stakeholder role's needs-to-know question) deserves its own application: hiring managers reading a portfolio at a senior level want to see momentum across the body of work — case studies dated, growth visible, recent work as strong as older work. A portfolio where the strongest case study is from 2019 and the recent work is thinner reads as declining momentum, regardless of how good the 2019 piece was. We surface this as: "Per **Stakeholder Needs Map**, the Stakeholder reader wants to see momentum. Your strongest case study is dated 2019. Either freshen the 2024–2026 work to match, or remove the dates and lead with the 2019 piece as your anchor."

**Source:** Nate Bauer, ["An Introduction To Slicing"](https://nabauer.com/articles/slicing) — the table that powers Slicing. Same article as Slicing; same citation rules.

---

## The 80% Principle {#the-80-percent-principle}

**Use when:** A user says "I want to launch but it's not done yet" or has had a portfolio in draft for 6+ months without shipping. The 80% Principle is Nate's most quotable original heuristic — and the cure for portfolio perfection paralysis.

**The structure (Nate's words, verbatim):**

"if I'm working on a project and I get to 80% satisfaction with the output of that project, that's when I should stop working on it and get feedback and validate effort… 80% was good enough, usually almost always is."

The framework is: stop polishing at 80% satisfaction; ship for feedback because the last 20% costs as much as the first 80%. Treat your portfolio (or each case study) the same way — 80% is the publish threshold, not 100%.

**Apply to a portfolio:** Two common situations. (1) Portfolio in private draft for months — the 80% Principle is the permission slip. (2) One case study polished to a sheen, three case studies in 60% draft — the 80% Principle says: stop polishing the polished one, get the other three to 80%, ship all four.

*This portfolio is one polished case study, three half-finished ones. Per **The 80% Principle**, four case studies at 80% beat one at 99% for first-job applications. The cost of the missing 20% on each draft is small; the cost of three missing case studies is large. Pick the strongest of the three drafts, push it to 80%, publish, and let recruiter feedback tell you which one to push further.*

A second application — resume vs. portfolio prioritization. Designers often agonize over the resume while the portfolio sits in 60% draft. Per **The 80% Principle**, push the portfolio to 80% first. The portfolio carries more weight in the hiring decision; the resume is the gate to get the portfolio looked at. A 90% resume linked to a 60% portfolio loses to an 80% resume linked to an 80% portfolio. Apply the threshold to the heavier-weight artifact first, then circle back.

A third: case-study video walkthroughs. Many designers record a Loom of their case study, then re-record it five times trying to get it perfect. Per **The 80% Principle**, ship the second take. Send it to a designer friend for feedback before ever sending it to a recruiter. The validation loop matters more than the fifth take.

The 80% Principle is a heuristic, not a multi-step framework, but we treat it as one because it has structure (a threshold, a stop rule, and a follow-up action — get feedback). Cite it by name. It's one of the cleanest things Nate has published and it shows up on stream often. Worth quoting back to anyone who says "I'll publish it when it's ready" — Nate's verbatim is the disarming line: "80% was good enough, usually almost always is."

**Source:** Nate Bauer, ["UX, Agile, and Healthcare Innovation Projects"](https://nabauer.com/articles/ux-agile-and-healthcare-innovation-projects). Public on Nate's site; cite verbatim.

---

## Dual Track Agile {#dual-track-agile}

**Use when:** Reviewing a senior portfolio where the case studies read as "I designed it, then they built it" — no rhythm of designer-ahead-of-dev visible. Dual Track Agile (Nate's slicing variant) is the diagnostic for whether the designer worked in a real iteration cadence with engineering.

**The structure (Nate's words, verbatim from "UX, Agile, and Healthcare"):**

The UX designer works on Slice N+1 or N+2 while devs build Slice N. The designer stays one or two slices ahead — never more.

Verbatim rule: "I would argue that's too much. I typically find comfort in being one slice or two slices ahead." Worst case if you have to throw a slice away: "you only lose two weeks of effort."

Verbatim on the designer's role inside this rhythm: "in a decentralized product environment… the UX designer ends up being a team leader… You are the person that builds team alignment. You facilitate how these processes should function, and you are the person that ends up re-encouraging that mindset of getting things right eventually and not on the first try."

**Apply to a portfolio:** Use this as a senior-rubric prompt. Ask: in your case study, where were you relative to engineering? If the answer is "we did design first, then I handed off, then they built," that's not Dual Track — that's waterfall in agile-sprint clothing. The senior signal is the cadence: designing one slice ahead, validating with engineering on the slice currently in build, and feeding what you learn back into the next slice's design.

*This case study describes designing for nine months, then a handoff. Per **Dual Track Agile**, that's not the senior cadence — there's no rhythm of designer-ahead-by-one-or-two-slices visible. Rewrite: pick one slice in the case study and show the dual-track rhythm. "While engineering shipped Slice 2 (the editor), I was in design on Slice 3 (the QA preview). Engineering's findings on Slice 2 — the inline-preview pattern broke for QA — fed directly into the Slice 3 redesign." That single paragraph unlocks the senior-cadence signal.*

The "never more than one or two slices ahead" rule is also useful in mock-interview prep. The IC interviewer's question — "How did you stay aligned with engineering?" — has a strong answer using Nate's verbatim cap: "I stayed one slice ahead at most, two if engineering was running fast on a known pattern. Past two, I'd lose touch with what was real in build, and the slice I was designing would drift." That answer signals the senior posture: the designer's value isn't in being far ahead; it's in staying close enough that the design and the build co-evolve.

The "decentralized product environment" framing is the second senior signal. Nate's verbatim: "the UX designer ends up being a team leader… You are the person that builds team alignment. You facilitate how these processes should function, and you are the person that ends up re-encouraging that mindset of getting things right eventually and not on the first try." For senior portfolio review, this is the "leadership without authority" frame — the case study should show the designer shaping the team's posture, not just the product's.

Dual Track Agile is the rhythm rule that sits inside [Slicing](#slicing). Slicing is the deliverable system; Dual Track Agile is the cadence the designer holds across slices. For most senior portfolios, citing Dual Track Agile by name is the move that lifts a "process diary" case study into a "shipping cadence" case study.

**Source:** Nate Bauer, ["UX, Agile, and Healthcare Innovation Projects"](https://nabauer.com/articles/ux-agile-and-healthcare-innovation-projects) and ["An Introduction To Slicing"](https://nabauer.com/articles/slicing).

---

## Brand Drivers {#brand-drivers}

**Use when:** Reviewing a portfolio's positioning — the hero, the about page, the "what kind of designer am I" copy. Brand Drivers is the workshop tool Nate teaches for getting from "we sort of do everything" to a sharp message. Ports cleanly to portfolio positioning.

**The structure (verbatim 4 columns from "Capturing Brand Drivers"):**

1. **Functional** — "The purpose and result of the product."
2. **Economic** — "How it benefits the user financially."
3. **Emotional** — "How it affects them emotionally."
4. **Self-Expressive** — "What they're emoting to the world about themselves."

**Process (verbatim):** "ideally done with 3-5 people with one person acting as moderator." Moderator pushes past generics by asking "Why is that important?" Then "go through each column and remove any redundancy… Don't, however, combine benefits between columns." Final step: narrow to "between one and five" core drivers. "More than that and your messaging risks becoming muddied and diluted."

**Apply to a portfolio:** Re-cast the four columns for designer positioning. Functional = what kind of work you ship (B2B SaaS flows, design systems, 0-to-1 product). Economic = the business value you bring (cycle time, conversion, retention). Emotional = how working with you feels (calm, decisive, bias-to-ship). Self-Expressive = what hiring you signals about the team's values (we hire people who push back on PMs; we hire people who can sit with ambiguity).

Most early-career portfolios fill column 1 only — what they did. Most senior portfolios still fill only 1 and 2 — what they did and the metric. Columns 3 and 4 are where positioning lives, and they're where most portfolios have nothing.

*This portfolio fills the **Functional** column in **Brand Drivers** but skips **Self-Expressive**. The hero says: "Product designer with 6 years' experience in SaaS." That's column 1 only. What does hiring you signal about the team that hires you? Rewrite the hero to lead with column 4 — pick a posture: "I ship complex flows in regulated B2B" or "I make consumer apps feel inevitable" — and put it in your hero. Right now the portfolio reads as: "I'll take any role." (See voice.md ❌/✅ Pair 4 for the same observation.)*

A second portfolio example: cover-letter copy. **Brand Drivers** also works as a cover-letter audit. Most cover letters are 100% Functional column — what the candidate has done, in what role, with what tools. The four-column re-cast: add one sentence each on Economic ("the work I'm proudest of moved retention from X to Y"), Emotional ("teams I've been on say I'm the one who slows the room down before we commit"), and Self-Expressive ("hire me if you want a designer who'll push back on the brief, not run it"). Three sentences across three columns is enough — Nate's 1-to-5 rule applies here too.

The 1-to-5 driver rule is non-negotiable. If a portfolio's positioning sprawls across 7+ angles, it's not differentiated. Per Nate's verbatim: "More than that and your messaging risks becoming muddied and diluted." We've seen this pattern often enough on stream that we've named it: "I'll take any role" is the failure mode of unfocused positioning. Brand Drivers is the cure.

The moderator move from the workshop process — pushing past generics by asking "Why is that important?" — is also worth porting to portfolio review. When a designer says "I want to focus on healthcare," ask "Why is that important?" until they get past "because I have experience there" and arrive at something specific and personal. The answer to the third "why" is usually the Self-Expressive driver.

**Common pitfalls when applying Brand Drivers to portfolio review:**

- **Combining benefits across columns.** Nate's verbatim guard: "Don't, however, combine benefits between columns." If a driver shows up in two columns, leave it in both — they're different angles on the same value.
- **Sprawl past five drivers.** Nate's hard cap: 1–5. More than 5 = muddied positioning.
- **Letting the Functional column do all the work.** If columns 2, 3, 4 are empty, the portfolio is positioned by what the designer *does*, not why it matters. That's column 1 only — the weakest of the four.

**Source:** Nate Bauer, ["Capturing Brand Drivers"](https://nabauer.com/articles/capturing-brand-drivers). Nate references "Brand Foundations on LinkedIn Learning (formerly Lynda.com)" as the original course source — but he teaches the full 4-column method himself in the article, so we cite the article, not the course.

---

## Ethos / Pathos / Logos {#ethos-pathos-logos}

**Use when:** A portfolio "looks fine" but isn't getting interviews — and the user can't figure out why. Ethos / Pathos / Logos (Aristotle's three pillars, with Nate's sales/UX application) is the diagnostic. One of the three is missing, and you can identify which.

**The structure (Nate's framing from "Three Principles Of Persuasion"):**

- **Ethos** = "credibility & character" / brand trust. Built via "Meet Our Team pages, testimonials, Partners pages."
- **Pathos** = "emotion & connection." Built via "benefits of a product rather than… features."
- **Logos** = "logic & reason." Built via "diagrams describing how a product actually functions… comparison charts."

**Diagnostic test (verbatim):** "Next time you go to the store and decide not to buy something, consider which one of these three things were not fulfilled in you."

**Ordering rule (verbatim):** "logos should be last… Logos should be used only after the audience has already been inspired to buy the category of product."

**Failure modes (verbatim):** "If a company lacks ethos, they don't trust them enough to buy from them. If the company lacks pathos, they haven't met the needs or wants of the customer or may be targeting the wrong audience. If a company lacks logos, the customer will simply buy the product from someone else."

**Apply to a portfolio:** Translate the failure modes:

- **Lacks Ethos** = the portfolio gives no reason to trust the designer. No about page, no testimonials, no shipped-work evidence, no team context. The recruiter can't tell if this is a real practitioner.
- **Lacks Pathos** = the portfolio is all features (case studies, screenshots, methods) but no story about who the work is for or why it matters. The hiring manager doesn't feel anything.
- **Lacks Logos** = there's narrative and trust signal, but no evidence of structured thinking. The IC interviewer can't see how decisions got made.

Apply Nate's ordering rule: a portfolio that opens with logos (process diagrams, methodology) before pathos (the human reason this matters) is selling features before building desire. Lead with pathos — why this work matters, who it served — then back into logos.

*This portfolio lacks **Pathos** in **Ethos / Pathos / Logos**. Three case studies open with "Background and methodology" sections — that's logos before pathos. By Nate's ordering rule, "logos should be last." Rewrite each case study opening: lead with the user-or-business reason this work mattered (one paragraph, concrete), then show the methodology. Right now the case studies read as competent but cold — recruiters bounce because nothing makes them care.*

A second application — the failure-mode diagnostic. When a user says "I'm not getting interviews and I don't know why," walk the three failure modes:

- **No interviews at all (Ethos failure):** the portfolio gives no reason to trust the designer. Add an about page, list shipped products, name companies, name teammates, surface testimonials if you have any. Even a one-line note — "shipped to 2M users at [Company]" — moves the trust needle.
- **Some interviews, none convert past first round (Pathos failure):** the portfolio is technically competent but not memorable. The designer doesn't have an opinion about the work. Surface the opinions: what did you push back on, what would you do differently, what do you believe about good design that other designers don't.
- **Interviews go well, lose at offer (Logos failure):** the IC interviewers can't see decisions made under constraint. Add the tradeoff paragraphs to the case studies. "We had two options. I picked X. We gave up Y. With more time I'd have re-tested Z."

For senior portfolios, the diagnostic is sharper: lacking ethos = no leadership story. Lacking pathos = no opinion about the work. Lacking logos = no decisions made under constraint. Most senior portfolios fail on pathos. The senior portfolio that's "fine but boring" is almost always a pathos gap.

Nate's verbatim sales-tactic mapping is also useful for cover-letter and outreach copy. Ethos in outreach = lead with where you've shipped, who you've worked with. Pathos = name a specific reason this company's work moves you (concrete, not generic). Logos = explain how you'd solve a specific problem they have. In that order. Logos last.

**Common pitfalls when applying Ethos / Pathos / Logos to portfolio review:**

- **Skipping the failure-mode diagnostic.** Just naming the three pillars without diagnosing which is missing is generic. The diagnostic — which one is missing for *this* user? — is the move.
- **Inverting the order.** If a portfolio reviewer leads with logos ("the methodology is rigorous"), they're inverting Nate's rule. Lead with pathos in the review, the same way the portfolio should lead with pathos for its readers.
- **Treating ethos as just credentials.** Ethos is character and credibility, not just where you went to school. Shipped work, named teammates, testimonials, transparent ownership — all build ethos.

**Source:** Nate Bauer, ["Three Principles Of Persuasion"](https://nabauer.com/articles/three-principles-of-persuasion) and ["What Aristotle Can Teach Us About Marketing"](https://nabauer.com/articles/what-aristotle-can-teach-us-about-marketing). Aristotle's framework is public-domain canon; Nate's *application* (failure-mode diagnostic + ordering rule + sales-tactic mapping) is original framing — that's the part to lean on.

---

## Ladders {#ladders}

**Use when:** A portfolio is competing in a saturated category — bootcamp grad in product design, senior IC in design systems — and "more polish" isn't the answer. Ladders reframes positioning: your strategy depends on which rung you currently occupy, not how good the work is.

**The structure (Nate's words, verbatim from "How Ladders Alter Your Marketing Strategies"):**

A ladder is a ranked list of brands a customer holds in their head for a given category. Your strategy by rung:

- **Rung 1:** "all they have to do is market the industry that they're in." (Already trusted; sell the category.)
- **Rung 2:** "Canon's got this target audience, we're going to go after this other target audience instead… potentially an opposite list of benefits."
- **Rung 3+:** "focus on a differentiation that puts you on a new ladder, one on which you're the top rung, one you can comfortably and confidently dominate."

**Audit move (verbatim):** "if you have different segments and target audiences, explore where you are on segment one's ladder, compare that to segment two."

**Apply to a portfolio:** Translate ladder = "the list of designers a hiring manager mentally ranks for the role." If you're a bootcamp grad applying to senior product designer roles, you're rung 12, not rung 1 — no marketing tactic for rung 1 will work. The Ladders move is to find a ladder where the user is closer to rung 1 (or the only one on it) and compete there.

For most early-career and mid-career designers, the right move is **make a new ladder**. "Senior product designer" is a saturated ladder. "Senior product designer for healthcare-compliance flows" might be a ladder you're rung 1 or 2 on, especially if you came from healthcare. The portfolio's job is then to make that ladder visible — to *be* the ladder for that role.

*This portfolio competes on the saturated ladder per **Ladders**: "Senior product designer." Hundreds of equally-qualified candidates already on it. The user has nursing background plus 4 years designing for healthcare-startups — that's a niche ladder where they're a top-2 candidate, not a generic one where they're rung 30. Rewrite the portfolio's positioning to lead with the niche: "Product designer for clinical workflows — ex-RN." The ladder you compete on is now the one you can win.*

The audit move — "explore where you are on segment one's ladder, compare that to segment two" — works directly for designers targeting more than one role type. Walk both ladders. If you're rung 5 on "senior product designer" but rung 1 on "design systems lead," the portfolio's positioning answer is design systems lead, even if the role you wish you could land is generalist. Compete where you can win; the generalist role becomes more reachable once you're known on the niche ladder.

The Ladders move pairs with [Brand Drivers](#brand-drivers): Brand Drivers gives you the language for the niche; Ladders tells you whether to make the niche your whole positioning. For senior portfolio reviews, "make a new ladder" is one of the most common reframes we offer. It pairs especially well for career-switcher portfolios — the prior career almost always defines a niche ladder where the switcher is rung 1 or 2 (e.g., ex-teachers in EdTech, ex-nurses in healthcare, ex-engineers in dev tools). The Ladders move says: lead with that niche; the generalist roles open up later.

**Common pitfalls when applying Ladders to portfolio review:**

- **Picking a niche the user can't actually defend.** If the user has 6 months of healthcare experience, "Senior product designer for clinical workflows" doesn't yet hold. Pick the niche where the evidence supports rung 1 or 2, not where the user wishes they were.
- **Confusing "make a new ladder" with "narrow into oblivion."** "Senior product designer for fintech mobile onboarding flows in pre-Series-A startups" is too narrow — no roles match. The ladder needs to be defensible *and* big enough to have demand.
- **Not auditing across segments.** Most designers target multiple roles. The ladder analysis should run for each — where you stand on each, and which is the right one to lead with.

**Source:** Nate Bauer, ["How Ladders Alter Your Marketing Strategies"](https://nabauer.com/articles/how-ladders-alter-your-marketing-strategies). Public on Nate's site.

---

## Two-Filter Research Method {#two-filter-research-method}

**Use when:** Reviewing a case study that says "we did research" without specifying what kind. The Two-Filter Research Method is Nate's diagnostic for whether the right method was used — and it's a senior-portfolio test, because senior designers pick methods deliberately.

**The structure (Nate's words, verbatim from "Attitudinal and Behavioral Research"):**

Two yes/no questions narrow down which research method to run:

1. "am I looking to test this with one user or many users?" (qual vs quant)
2. "do I want to know how they feel about this button or what actions they take?" (attitudinal vs behavioral)

**Definitions (verbatim):**

- **Attitudinal** = "what people think."
- **Behavioral** = "what people do."
- "very often the two are quite different."

**Apply to a portfolio:** When a case study says "we ran research," the Two-Filter test asks: which quadrant? Most portfolio case studies sit in qualitative + attitudinal (interviews about feelings) without naming it. That's fine — but the senior signal is being able to defend why qual + attitudinal was the right choice, vs quant + behavioral, for the question at hand.

*This case study skips the **Two-Filter** check from **The Two-Filter Research Method**. It says: "We interviewed 8 users to understand their pain points." That's qual + attitudinal — fine, but unstated. The senior question is: why qual + attitudinal here, and not quant + behavioral (e.g., session-replay or analytics on the live flow)? Rewrite: add one sentence after the methodology line — "Chose qual + attitudinal over quant + behavioral because we needed to understand *why* drop-off was happening, not measure *that* it was. Analytics already showed the where." That sentence is the senior signal.*

The "very often the two are quite different" line is also worth pulling forward in mock-interview prep. The IC interviewer's question — "Have you ever had research findings contradict each other?" — is a Two-Filter question in disguise. The strong answer: "Yes — attitudinal said users wanted X; behavioral showed they used Y. We designed for what they did, not what they said." That's the senior research-judgment signal.

Pair this with Nate's interview heuristics from `references/heuristics.md` (when one exists) — "open-ended questions only," "focus on the customer not the product," "free coffee > paid incentives." Those are the inside-the-method moves; Two-Filter is the choose-the-method move.

**Source:** Nate Bauer, ["Attitudinal and Behavioral Research"](https://nabauer.com/articles/attitudinal-and-behavioral-research). Public on Nate's site.

---

## Proto Persona {#proto-persona}

**Use when:** Reviewing a junior or career-switcher case study where the persona section is over-built — three full personas with names, photos, fabricated quotes, fictional demographics. Proto Persona is Nate's fix: lean version, assumption-built, prioritize speed.

**The structure (Nate's words from "Proto Personas"):**

A Proto Persona is a lean version of a persona built from assumptions, not research. Captures only basic demographics, needs, obstacles, desires.

**Rule (verbatim):** "Personas are ever-changing documents that evolve over time." Prioritize "speed over accuracy."

**Apply to a portfolio:** When a case study has fabricated persona detail (the bootcamp tell), reach for Proto Persona to refactor it. The fix isn't "delete the persona" — it's "convert the over-built persona into a Proto Persona, then label it as such." This is more honest and reads better to hiring managers who recognize bootcamp persona patterns.

*This case study presents three full personas with stock photos and fabricated quotes — recognizable as a bootcamp persona pattern per **Proto Persona**. Rewrite as: one Proto Persona block per primary user — basic demographics, needs, obstacles, desires, and a one-line note: "Built from assumptions; we'd validate with research in the next iteration." That's more honest and reads better to seasoned hiring managers, who clock fabricated personas instantly.*

Proto Persona is also the right move when a designer is showing **process for a real shipped product but the actual personas are NDA'd**. Convert to Proto Persona structure (demographics + needs only, no proprietary detail) and the case study becomes shareable. The "evolves over time" rule is the cover — Proto Personas are explicitly placeholder, so showing one in a case study isn't a claim that it was the final user model, it's a claim that it was the starting one.

For mock-interview prep, the IC interviewer's follow-up on personas is usually: "How did the persona change once you got to research?" The strong answer uses Proto Persona vocabulary: "We started with a Proto Persona built from stakeholder interviews. After 6 user interviews in week 2, we updated three of the four 'needs' and discovered an obstacle we hadn't seen — security review fatigue. The persona kept evolving through the project." That answer signals process maturity AND the verbatim Proto Persona principle ("ever-changing documents that evolve over time").

**Source:** Nate Bauer, ["Proto Personas"](https://nabauer.com/articles/proto-personas). Public on Nate's site.

---

## Component Library → Design System Progression {#component-library-design-system-progression}

**Use when:** Reviewing a portfolio that claims "I built a design system" — common over-claim, especially mid-career. The progression rule is the test: did they build a real system, or a component library that they're calling a system?

**The structure (Nate's words, verbatim from "Why Build Design Systems?"):**

"design systems are commitments. There is absolutely no need to build out an entire system that an application doesn't currently use or need… stay away from a design system until your component library starts holding you back. When that occurs, start building systems only in places you currently need them."

The progression: component library first. Build a system **only in the places it's currently needed**. The system grows out of the library when the library starts to fail at scale.

**Apply to a portfolio:** "I built a design system" is a senior-level claim and should map to senior-level evidence — versioning, governance, documentation, adoption metrics, contribution model. If a case study claims "design system" but the evidence is a Figma file with shared components, the framework name to apply is **Component Library**, not Design System.

*This case study claims "I built a design system" but the evidence is a shared Figma library with 40 components. Per **Component Library → Design System Progression**, that's a component library, not a system — no governance, no contribution model, no adoption metric. The fix isn't to fabricate system evidence; it's to rename. Rewrite the case study as: "Built a component library that grew into [system aspects, if any]. Did NOT build a design system — the application didn't need one yet." Nate's rule, cited verbatim: "stay away from a design system until your component library starts holding you back." That's a more honest claim and a better senior signal — designers who can tell the difference between library and system are rarer than designers who claim systems work.*

For mock-interview prep, the killer follow-up on design-system claims is: "What was the moment your component library started holding you back?" If the candidate can name that moment — "we hit it when our third product team needed to fork our Button component because their density was different, and we realized we didn't have token-level control" — they understand the progression. If they can't, they were doing component-library work and calling it a system, which the IC interviewer will clock.

This pairs with [The 80% Principle](#the-80-percent-principle) — both are Nate's "don't over-build" instincts. The portfolio version is "don't over-claim." Both heuristics share a posture: prefer the smaller honest claim over the bigger fabricated one. That posture is, on its own, a senior signal.

**Source:** Nate Bauer, ["Why Build Design Systems?"](https://nabauer.com/articles/why-build-design-systems). Public on Nate's site.

---

## House Analogy {#house-analogy}

**Use when:** Explaining (in mock interviews especially) the difference between Waterfall and Agile process posture — and clocking which posture a case study reads as. The House Analogy is Nate's signature explainer; it shows up in multiple articles and on stream.

**The structure (Nate's words, verbatim from "How UX Fits in an Agile Framework"):**

The analogy: Waterfall builds the whole house in one go. Agile builds the office first, validates, then builds the next room.

**Punchline (verbatim, repeated multiple articles):** "waterfall tries to get things right on the first try while agile tries to get things right eventually."

**Apply to a portfolio:** Use the House Analogy as a diagnostic on case studies that read as one-shot deliveries. If the case study reads as "we designed the whole thing, then it shipped," that's a waterfall-shaped case study — even if the team called it agile. The senior signal is an agile-shaped case study: "we shipped the [office room] first, learned [X], then built the [kitchen] differently."

*This case study reads as waterfall per the **House Analogy** — designed the whole product, then shipped. Per Nate's punchline, "waterfall tries to get things right on the first try while agile tries to get things right eventually." For mock-interview prep, expect the question: "Walk me through what you shipped first and what you learned that changed what you shipped second." Rewrite the case study to answer that question without being asked.*

The House Analogy is also a useful explainer when a junior designer doesn't yet have the vocabulary for waterfall vs agile. In mock interviews, we use it to teach the distinction in 30 seconds — it lands faster than abstract definitions. See also [Lean / Agile / Scrum](#lean-agile-scrum) for the precise vocabulary.

A second portfolio application: the analogy works backwards too. When a portfolio has too *many* small case studies that all look like room-additions to a non-existent house, the diagnostic is "build the office first" — pick the one case study that's the foundational room (the one that establishes the designer's POV) and lead with it. Then the others become rooms added to that foundation. The opposite failure of waterfall portfolios is "all rooms, no house" — and the House Analogy diagnoses both.

**Source:** Nate Bauer, ["How UX Fits in an Agile Framework"](https://nabauer.com/articles/how-ux-fits-in-an-agile-framework). Public on Nate's site.

---

## Lean / Agile / Scrum {#lean-agile-scrum}

**Use when:** A case study or resume bullet uses these terms loosely — "I worked in Agile," "we ran Lean Scrum sprints" — and we need to test whether the user actually knows the difference. Three terms people conflate; Nate separates them cleanly.

**The structure (Nate's definitions, verbatim from "Lean, Agile, and Scrum"):**

- **Lean** = "the methodology of building a product using the minimum amount of effort possible."
- **Agile** = "a methodology that allows a team the opportunity to pivot a product at any given time."
- **Scrum** = "simply a communication strategy" — stand-ups, grooming, retrospectives.

**Apply to a portfolio:** Use this as a vocabulary-precision test on resumes and case studies. A resume bullet that says "Designed in an Agile/Scrum environment" is fine. A bullet that says "Drove Lean methodology to ship Agile features in Scrum sprints" is word-salad — the writer is buzzword-stacking.

*This bullet word-stacks per **Lean / Agile / Scrum**. Bullet says: "Drove Lean methodology to ship Agile features in Scrum sprints." Per Nate's definitions, those are three different things — Lean is about minimum effort, Agile is about pivoting, Scrum is about communication. Hiring manager reads this as buzzword soup. Rewrite: pick the one that's true and be specific. "Shipped in 2-week Scrum cycles; cut design-to-dev handoff time from 5 days to 2 by colocating the design crit with sprint grooming." That bullet shows Scrum AND a real outcome.*

For mock interviews, expect: "What's the difference between Agile and Scrum?" The answer using Nate's framing: Agile is the posture (we can pivot); Scrum is the communication ritual (stand-ups, grooming, retrospectives). Lean is a separate axis (minimum effort). A candidate who can give that three-line answer outperforms a candidate who waves at "we're Agile and Scrum" generically.

A second resume-bullet pattern this catches: false specificity. "Led 14 Lean UX sprints in a Scaled Agile Framework (SAFe) environment with a Kanban backlog." Zero of those terms add information about the work. Rewrite by stripping the methodology stack and naming the work outcome: "Designed across 14 two-week sprints — shipped 9 features, killed 3 in design crit, deferred 2." That bullet survives scrutiny; the previous one folds at the first follow-up question.

**Source:** Nate Bauer, ["Lean, Agile, and Scrum"](https://nabauer.com/articles/lean-agile-and-scrum). Public on Nate's site.

---

## Three Pillar System {#three-pillar-system}

**Use when:** Reviewing a portfolio that claims accessibility expertise — common claim, often thin evidence. The Three Pillar System (Nate's framing on accessibility) is the diagnostic for whether the user understands accessibility as a system, not a checklist.

**The structure (Nate's words, verbatim from "AI Will Revolutionize Accessibility"):**

Accessibility today rests on three pillars:

1. "Products need to be designed for accessibility."
2. "Those with impairments need access to accessibility technology."
3. "Legislation to enforce progress."

Nate's headline argument: AI collapses two of the three (the "designed for accessibility" pillar and the "access to assistive technology" pillar can both be augmented or replaced by AI). Legislation remains.

**Apply to a portfolio:** When a case study says "I designed for accessibility," the test is: which pillar(s)? Most case studies show pillar 1 evidence only — color-contrast checks, screen-reader testing, focus order. That's the design pillar. Senior accessibility evidence touches at least pillar 2 (built or specified assistive-tech behaviors) or pillar 3 (compliance-driven decisions: WCAG AA vs AAA, ADA, EAA, Section 508).

*This case study claims accessibility work but per the **Three Pillar System**, only pillar 1 is shown — color contrast and screen-reader testing. For senior portfolios in regulated domains, surface pillar 3 evidence: name the standard you designed against (WCAG 2.1 AA, ADA, EAA), and one decision you made specifically because of compliance. "Chose a 4.5:1 contrast minimum for body copy because the product had to ship to EU clients under EAA." That sentence shows you understand accessibility as a system, not a checklist.*

For junior portfolios, pillar-1 evidence is appropriate — we don't expect compliance literacy at junior. But name it as pillar 1, don't over-claim it as the whole system.

For mock-interview prep on accessibility-claimed portfolios, expect the IC-interviewer follow-up: "What's a tradeoff you made between visual design and accessibility?" The strong answer is a real one — "Wanted to use a 3:1 contrast on a card subtitle for visual hierarchy; couldn't because the design system bound that color token to body copy elsewhere. We forked the token and used the higher-contrast pair on the card." The weak answer is "Accessibility never has to compromise design." Per the Three Pillar System framing, real pillar-1 work has tradeoffs all the time; senior signal is being able to name one.

**Source:** Nate Bauer, ["AI Will Revolutionize Accessibility"](https://nabauer.com/articles/ai-will-revolutionize-accessibility). Public on Nate's site.

---

## Cross-framework patterns

Three patterns show up across multiple frameworks here. Workflow agents should recognize them.

**The honest-claim pattern.** [The 80% Principle](#the-80-percent-principle), [Component Library → Design System Progression](#component-library-design-system-progression), [Proto Persona](#proto-persona), and [Brian Lovin's Ownership Language](#brian-lovin-ownership-language) all share the same underlying move: prefer the smaller honest claim over the bigger fabricated one. When reviewing a portfolio that over-claims, reach for whichever of these four frameworks fits the specific over-claim. The verbatim pattern: name what was actually built, label it precisely, and don't apologize for the smaller scope. Hiring managers reward precision; they punish inflation.

**The cadence-and-rhythm pattern.** [Slicing](#slicing), [Dual Track Agile](#dual-track-agile), and [House Analogy](#house-analogy) all diagnose the same gap: case studies that compress iteration into a single block. The frameworks attack the gap from three angles — Slicing names the iteration unit, Dual Track Agile names the designer-to-engineering rhythm, House Analogy names the posture (waterfall vs. agile). For most senior reviews, citing one of the three by name is enough. For a particularly process-thin case study, cite all three.

**The positioning-and-narrative pattern.** [Brand Drivers](#brand-drivers), [Ladders](#ladders), [Ethos / Pathos / Logos](#ethos-pathos-logos), and [Stakeholder Needs Map](#stakeholder-needs-map) are the cluster for "this portfolio is technically fine but not landing." Brand Drivers gives the language. Ladders tells you which competitive lane you're in. Ethos/Pathos/Logos diagnoses which audience response is missing. Stakeholder Needs Map audits which readers the portfolio talks to. When asked "review my whole portfolio holistically" or "I'm not getting interviews," start in this cluster.

---

## Adding new frameworks

This file is additive (per CONTENT-05). New frameworks land here as Tim+Nate mine them from Friday-stream transcripts on the @designshaped YouTube channel, or as Nate publishes new articles on nabauer.com.

When adding a framework:

- **Pull text verbatim from the source.** Don't paraphrase — the voice's authenticity comes from quoting Nate's (or the source's) actual words. If a quote is missing, mark it `[verbatim source TBD]` and ship; don't invent.
- **Match the existing section template.** Name (anchor), Use when, The structure, Apply to a portfolio, Source. The template's order is the workflow agent's read order — don't reorder.
- **Append, don't rewrite.** Add the new framework to the bottom of its group in the Index, then add the section to the bottom of the file. Workflows already cite existing anchors — don't break those citations.
- **Cite the transcript or article.** New patterns from streams cite the transcript line in the private `mining-log.md` (per D-17 — Tier 1 mining doesn't require re-contact, but the audit trail does). New articles cite the URL.
- **Earn the section.** Not every observation Nate or Tim makes on stream is a framework. A framework has structure (named beats, a stop rule, a sequence, or a diagnostic). One-line heuristics belong in `references/heuristics.md`, not here. Test: can a workflow agent quote the structure verbatim and apply it without paraphrasing? If yes, it's a framework. If no, it's a heuristic.

The ceiling on this file is roughly 25 frameworks. Past that, the workflow agent's "load only what you need" pattern starts breaking down. If we approach the ceiling, split into framework-card files (the dmba pattern) — one file per framework, with this file becoming the index.

When in doubt about whether a candidate framework crosses the bar, route to Tim+Nate. The voice depends on these being right, not on these being many.
