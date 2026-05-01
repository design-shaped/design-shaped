# Frameworks (Nate Bauer) — Portfolio Rx

The 13 frameworks Nate teaches and publishes on nabauer.com. Sourced verbatim from his articles. **Sister file:** [`frameworks-stream.md`](frameworks-stream.md) holds the 13 stream-mined portfolio review frameworks. **Index:** [`frameworks.md`](frameworks.md).

The frameworks-by-name protocol from `voice.md` §9 applies to everything in this file. NEVER paraphrase. Quote the user's work, name the framework verbatim, hand off to the rewrite, cite the source line.

---

## Index (this file)

- [Slicing](#slicing) — Nate's iteration-sized deliverable system; ports cleanly to case-study scope
- [Stakeholder Needs Map](#stakeholder-needs-map) — six roles, six "needs to know" prompts; portfolio audit lens
- [The 80% Principle](#the-80-percent-principle) — ship at 80% satisfaction; portfolio "perfection paralysis" cure
- [Dual Track Agile](#dual-track-agile) — designer one or two slices ahead, never more
- [Brand Drivers](#brand-drivers) — Functional / Economic / Emotional / Self-Expressive 4-column method
- [Ethos / Pathos / Logos](#ethos-pathos-logos) — Aristotle's three pillars as a sales/UX diagnostic
- [Ladders](#ladders) — your rung dictates your strategy; reframe portfolio "positioning". **Distinct from Trust Ladder.**
- [Two-Filter Research Method](#two-filter-research-method) — qual/quant + attitudinal/behavioral
- [Proto Persona](#proto-persona) — assumption-built persona; prioritize speed over accuracy
- [Component Library → Design System Progression](#component-library-design-system-progression) — don't build a system until the library holds you back
- [House Analogy](#house-analogy) — Waterfall vs. Agile in one image
- [Lean / Agile / Scrum](#lean-agile-scrum) — three terms people conflate, separated cleanly
- [Three Pillar System](#three-pillar-system) — accessibility's three pillars; AI collapses two

> Cross-references to stream-native frameworks (Hook → Proof → Story, Three Target Audiences, etc.) point at [`frameworks-stream.md`](frameworks-stream.md).

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

This is the lens we reach for first when asked "review my whole portfolio holistically" at the product-team-artifact level. For portfolio-only audits, see [Three Target Audiences](frameworks-stream.md#three-target-audiences) — the streams-native 3-audience compression. Both are valid; pick by review surface.

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

The "decentralized product environment" framing is the second senior signal. Nate's verbatim: "the UX designer ends up being a team leader… You are the person that builds team alignment. You facilitate how these processes should function, and you are the person that ends up re-encouraging that mindset of getting things right eventually and not on the first try." For senior portfolio review, this is the "leadership without authority" frame — the case study should show the designer shaping the team's posture, not just the product's. This connects directly to [Centralized vs Decentralized Environments](frameworks-stream.md#centralized-decentralized) — Dual Track Agile assumes the decentralized environment; surface the prerequisite first.

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

> **CRITICAL: Distinct from [Trust Ladder](frameworks-stream.md#trust-ladder).** Ladders is rung-based competitive positioning. Trust Ladder is within-page conversion sequencing. They share a metaphor but answer different questions. Cite by full name to avoid confusion.

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

The Ladders move pairs with [Brand Drivers](#brand-drivers) and [Designer Niche Scales](frameworks-stream.md#niche-scales): Brand Drivers gives you the language for the niche; Niche Scales tells you which axes to position on; Ladders tells you whether to make the niche your whole positioning. For senior portfolio reviews, "make a new ladder" is one of the most common reframes we offer. It pairs especially well for career-switcher portfolios — the prior career almost always defines a niche ladder where the switcher is rung 1 or 2 (e.g., ex-teachers in EdTech, ex-nurses in healthcare, ex-engineers in dev tools). The Ladders move says: lead with that niche; the generalist roles open up later.

**Common pitfalls when applying Ladders to portfolio review:**

- **Confusing with Trust Ladder.** They're different frameworks. Cite "Ladders" or "Nate's Ladders" when the topic is positioning; "[Trust Ladder](frameworks-stream.md#trust-ladder)" when the topic is within-page conversion.
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

Pair this with Nate's interview heuristics from `references/heuristics.md` — "open-ended questions only," "focus on the customer not the product," "free coffee > paid incentives." Those are the inside-the-method moves; Two-Filter is the choose-the-method move.

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
