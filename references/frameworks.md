# Frameworks — Portfolio Rx

## How this file is used

The voice.md §9 frameworks-by-name protocol mandates: when a workflow applies a framework, it names the framework verbatim, quotes specifics from the user's work, and cites this file's section. NEVER paraphrase a framework. NEVER re-teach it inline.

Workflow agents read only the section they need. Each framework here is self-contained: name, when to use, structure (in the source's words), how to apply to a portfolio review, and source citation. The section anchor is the citation target — `See: references/frameworks.md#slicing` is a valid hand-off.

Two voice rules to honor when surfacing a framework:

1. **Name it on first use.** "This bullet leads with **What** in **What/How/Why**." Never "this bullet's W/H/W is off" without spelling out What/How/Why once.
2. **Quote the user's work, then frame.** The pattern is: pull the user's exact bullet or paragraph, then name the framework step it skips, then provide the rewrite. Never frame in the abstract.

### Worked example of the protocol

A user submits a resume bullet: "Led seven plus projects, including the redesign of ASU's Souls website." A workflow agent applies the protocol:

1. **Quote the user's work:** "Your bullet reads: *'Led seven plus projects, including the redesign of ASU's Souls website.'*"
2. **Name the framework verbatim:** "This leads with **What** in **What/How/Why**. Most impressive thing is last."
3. **Hand off to the rewrite without re-teaching:** "Flip to Why/How/What: *'Increased engagement 20% by improving usability and aligning brand standards across seven plus projects, including ASU's Souls redesign.'*"
4. **Cite the source line:** "See: `references/frameworks.md#what-how-why`."

That four-step loop is the entire mechanic. The workflow agent does NOT explain what What/How/Why is in the review output — the user can read the framework section if they want. The workflow agent's job is to name the gap, quote the work, and prescribe the fix.

When in doubt: name two frameworks, not zero. Per voice.md self-check: "At least 2 frameworks are surfaced by name." A review with no framework names reads as generic LLM critique; a review with one framework name reads as competent; a review with two or three reads like Tim and Nate.

---

## Index

> **M2 update — 5 public-domain frameworks removed (zero corpus citations); 13 streams-mined frameworks added. See STREAM_MINING.md §2 for sourcing.**

**Stream-native portfolio review frameworks** (the moat — mined from 23 @designshaped Friday-stream transcripts; every workflow touches at least one)

- [What/How/Why ↔ Why/How/What](#what-how-why) — bullet-writing scaffold; the most-cited stream framework (13/23). Replaces STAR.
- [Three Target Audiences](#three-target-audiences) — Recruiter / Hiring Manager / Future Peers. Augments Nate's Stakeholder Needs Map (does NOT replace).
- [Housekeeping](#housekeeping) — case-study top-of-page factual block (role, timeline, industry, team, tools)
- [Trust Ladder](#trust-ladder) — within-page conversion sequencing: hook → credibility → story → ask. **Distinct from Nate's Ladders.**
- [Centralized vs Decentralized Environments](#centralized-decentralized) — org-shape question; prerequisite for cadence frameworks
- [Read-the-Titles-Only Test](#titles-only-test) — skim-test diagnostic for case-study section titles
- [Children's Picture Book Rhetoric](#picture-book) — convert paragraphs into annotated images
- [JJJ (Jolt / Journey / Jackpot)](#jjj) — 3-beat storytelling mechanic for openings
- [KSAs (Knowledge / Skills / Abilities)](#ksas) — ATS keyword-match diagnostic
- [Hook → Proof → Story](#hook-proof-story) — case-study sequencing. Replaces Inverted Pyramid.
- [Hard Metrics vs Soft Metrics (Behavior Change)](#hard-soft-metrics) — outcome-evidence diagnostic
- [Prototyping with Numbers](#prototyping-with-numbers) — third escalation when hard/soft metrics aren't available
- [Designer Niche Scales](#niche-scales) — multi-axis positioning model

**Design + product frameworks Nate teaches** (the moat — these are why this skill exists; from nabauer.com)

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

---

## What/How/Why ↔ Why/How/What {#what-how-why}

**Use when:** Reviewing any resume bullet, case-study TLDR, or hero/value-prop sentence. The single most-cited framework in the corpus (13/23 transcripts). The default scaffold for bullet-rewrite slots — replaces STAR for stream-native voice.

**The structure (verbatim from streams):**

- **What** — what you did (the activity)
- **How** — how you did it (the method/tactic)
- **Why** — why you did it (the impact/outcome)

The optimization: flip the order to **Why → How → What**, putting impact first. Headline rule (recurring verbatim): *"if you follow a what-how-why approach, really hard to write a bad bullet."* Optimization rationale: *"no one's hiring you for what you did… they're hiring you for the impact."* Caveat (recurring): *"you don't have to do the why-how-what approach at all times… don't take it as a hard rule."*

**Apply to a portfolio:** This is the bullet-rewrite default. Walk every resume bullet and ask: does it lead with the why? If a bullet starts with "Designed X," "Created Y," or "Led Z," it's What-first — flip it. Apply also at case-study scope: the TLDR/hero sentence of a case study should lead with impact, then how, then what shipped.

*This bullet leads with **What** in **What/How/Why**. Bullet says: "Led seven plus projects, including the redesign of ASU's Souls website." Most impressive thing is last. Per the framework, flip to **Why/How/What**: "Increased engagement 20% by improving usability and aligning brand standards across seven plus projects, including ASU's Souls redesign." Why first, how middle, what last.*

A second application — case-study hero copy. A hero that opens with "I redesigned the onboarding flow for a SaaS product" is What-first. Per Why/How/What: "Cut SaaS activation drop-off from 31% to 47% by restructuring onboarding from 9 steps to 4." Same project, hero now leads with impact, and the reader has a reason to scroll.

The caveat matters. Don't force every bullet into rigid Why/How/What — some bullets (especially housekeeping / role-context lines) are What-first by design. The framework's job is to flag bullets that bury impact. When the bullet is honest about activity-only context, leave it alone.

**Common pitfalls when applying What/How/Why:**

- **Inflating Why.** If the user has no measured impact, don't manufacture one. Reach for [Hard Metrics vs Soft Metrics](#hard-soft-metrics) and use a behavior-change claim instead.
- **Skipping How.** "Increased engagement 20%" is Why-only; without the How, the reader can't tell what the designer actually did. The full Why/How/What sentence shape needs all three.
- **Treating it as STAR.** It isn't. STAR is Situation/Task/Action/Result; What/How/Why collapses S+T into context-implicit and replaces R with Why-stated-as-impact.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. Most-frequent framework across 13/23 transcripts.

---

## Three Target Audiences {#three-target-audiences}

**Use when:** Auditing a whole portfolio holistically. The streams-native compression of Nate's published Stakeholder Needs Map (6 roles) into 3 portfolio-specific audiences. Augments — does NOT replace — [Stakeholder Needs Map](#stakeholder-needs-map).

**The structure (verbatim from streams):**

- **Recruiter** — Doesn't have deep design understanding. Skims for KSA keyword match. Looks at the value prop on the homepage and the **Housekeeping** at top of case studies. Goal: SEO/keyword match, not storytelling.
- **Hiring Manager** — Cares how you delineate and solve business problems. Skims case studies, looking for problem breakdown, decision-making, prioritization, process narrative.
- **Future Peers** — *"if I share an office with you for eight hours a day, are you going to make my life miserable?"* Cares about the about page. *"About pages are probably closer to dating pieces than they are business pieces."*

**Apply to a portfolio:** Walk the portfolio against each audience and ask: does this audience's question get answered? Most portfolios answer 1 or 2 of the 3. The missing audience is the audit gap.

*This portfolio answers the **hiring manager** in **Three Target Audiences** but skips the **future peer**. The about page is a stock-photo headshot and one paragraph; nothing tells me what kind of teammate you'd be. Rewrite the about page as a dating piece in a professional register — what you read, what you're learning, what kind of teams you do well in. Referrals look at this page; it's load-bearing for the strongest hiring channel.*

A second example: most career-switcher portfolios skip the **recruiter**. The case studies are well-written narrative but there's no [Housekeeping](#housekeeping) block at the top, so the recruiter — who scans for [KSAs](#ksas) — has nothing to triage on. The fix is mechanical: add a 5-line housekeeping block to the top of every case study. Recruiter now passes; the rest of the portfolio reaches the hiring manager.

**Cross-reference with Nate's Stakeholder Needs Map:** Both are valid. The Stakeholder Needs Map is the 6-role product-team version (Product Manager, Product Owner, Developers, Stakeholder, Other UX Designers, User). Three Target Audiences is the 3-audience portfolio-review compression. **Use Three Target Audiences when reviewing portfolios; use [Stakeholder Needs Map](#stakeholder-needs-map) when reviewing product-team artifacts.** They augment each other; do not pick one as canonical.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 10/23 transcripts.

---

## Housekeeping {#housekeeping}

**Use when:** Reviewing every case study. The factual SEO-targeted block at the top, separate from the narrative. The recruiter audience consumes this; the hiring manager skips past it.

**The structure (verbatim from streams):**

- **Role** on the project
- **Timeline**
- **Industry**
- **Team composition**
- **Tools used**
- Optionally: **skills**, **platform** (web/mobile)

Verbatim purpose: *"some real factual things, with a goal of SEO, not necessarily storytelling."* Pairs with [KSAs](#ksas) — housekeeping is where you seed the KSA keywords from the job description.

**Apply to a portfolio:** Open every case study with a housekeeping block. Missing housekeeping fails the recruiter audience even when the case study otherwise works. The block reads in 5 seconds; lets the recruiter triage; signals to the hiring manager that the candidate understands the audiences.

*This case study is missing **Housekeeping**. The case study opens directly on a problem statement. Add a housekeeping block: role (sole product designer), timeline (Q3 2024, 4 months), industry (B2B SaaS — fintech), team (1 PM, 3 engineers, 1 researcher), tools (Figma, Maze, Mixpanel). Reads in 5 seconds; lets the recruiter triage.*

A second application — when the user is targeting multiple role types, the Housekeeping block is where the [KSAs](#ksas) get seeded per-target. Different jobs have different keyword sets; the housekeeping block is the cheap place to swap them. Two versions of the same case study, with different housekeeping blocks tuned for "design systems lead" vs "product designer," is a legitimate move — the narrative below stays the same; the housekeeping carries the keyword load.

**Common pitfalls when applying Housekeeping:**

- **Inflating role.** "Lead Product Designer" when the candidate was the only designer is dishonest by upgrade. Use "sole product designer" — it's more honest and reads more senior than the inflated title.
- **Vague team composition.** "Cross-functional team" is non-information. Name the count and roles: "1 PM, 3 engineers, 1 researcher."
- **Tool-padding.** Listing every tool you've ever opened ("Figma, Sketch, Adobe XD, InVision, Marvel, Principle, Origami") signals insecurity. List the tools used on this project.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 11/23 transcripts.

---

## Trust Ladder {#trust-ladder}

**Use when:** Homepage / hero reviews, freelance portfolios with "hire me" CTAs, low-conversion diagnostics. The within-page conversion sequencing framework.

> **CRITICAL: Distinct from [Nate's Ladders](#ladders).** Nate's Ladders is rung-based competitive positioning ("which list of designers does the hiring manager mentally rank you on?"). Trust Ladder is within-page conversion sequencing. They share a metaphor but answer different questions. Do not merge.

**The structure (sequence-based, verbatim from streams):**

1. **Hook** — give them a reason to look further
2. **Build credibility** — evidence of competence
3. **Tell the story** — deepen the relationship
4. **THEN ask for the action** — CTA, contact, hire, interview

Verbatim: *"a trust ladder is your funnel for how effectively you are able to convince someone to take an action. And if you give them an action to take too early on in that trust ladder, they're gonna say no."*

**Apply to a portfolio:** Walk every page, especially the home and about pages. If a CTA appears before trust is built (e.g., "Book a discovery call" button in the hero before any work is shown), the trust ladder is broken.

*This homepage breaks the **Trust Ladder**. The first thing above the fold is a "Book a discovery call" CTA. Per the framework, you've asked for the action before the hook, the credibility, or the story. Cut the CTA from the hero. Move it below the case studies, after the recruiter has trusted you enough to want to take the next step.*

A second portfolio application: contact pages. A contact page that opens with a multi-field form and no context is asking for the action without earning it. Per Trust Ladder, the contact page should still give a hook (one line on what kinds of work you take), build credibility (links back to the strongest case study or two), tell a small story (why you're reachable here vs LinkedIn), then present the form. The form converts better when the page above it has done the trust work.

For freelance portfolios, the Trust Ladder failure is the most common conversion bug: hero says "Hire me," followed immediately by the form. Per the framework, that's asking for marriage before the first date. Restructure: hero hook → 2–3 case studies as credibility → 1 testimonial paragraph as story → THEN the contact CTA.

**Cross-reference with Nate's Ladders:** **DO NOT MERGE.** When citing in a review, name them precisely: "Trust Ladder" (within-page conversion) vs "Ladders" (competitive positioning). They co-occur often (Trust Ladder addresses page-level sequencing; Ladders addresses overall-positioning lane), but they are independent diagnostics.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 9/23 transcripts.

---

## Centralized vs Decentralized Environments {#centralized-decentralized}

**Use when:** Career-direction conversations, where the candidate needs to choose what kind of role to target before fixing the portfolio. The org-shape question that the cadence frameworks ([Slicing](#slicing) / [Dual Track Agile](#dual-track-agile) / [House Analogy](#house-analogy)) answer downstream.

**The structure (verbatim from streams):**

- **Centralized environment** — designer reports up to a UX manager who assigns a backlog. Common in design agencies and smaller orgs. Advantages: peer-designer growth, design-craft mentorship. Disadvantages: button-pushing risk, working across many unfamiliar projects.
- **Decentralized environment** — designer is embedded on a product team alongside PMs/devs/business stakeholders. Common in enterprise agile. Advantages: deep ownership of one initiative, end-to-end zero-to-one. Disadvantages: no peer-designer feedback, broader required skill range.

Stream rule: *"centralized environments prefer specialists. Decentralized environments prefer generalists."* Hybrid environments exist; some designers hold hybrid roles.

**Apply to a portfolio:** Use as the prerequisite question before applying any cadence framework. *"Are you in a decentralized environment? Then we can talk Dual Track Agile / Slicing / Slices ahead."* If the user's case study reads as one-environment work but they're targeting the other, surface the mismatch.

*This portfolio's case studies read as **Centralized** work per **Centralized vs Decentralized Environments** — multiple short projects across unrelated domains, one Figma file per project, no embedded-team detail. The user is targeting decentralized enterprise roles. The mismatch is the audit gap. Either retarget the application list to centralized-fit roles (agencies, smaller orgs), or rework the strongest case study to surface the embedded-team detail (PM/eng partners named, product-team rhythm visible) and treat that one case study as the decentralized-fit anchor.*

**Common pitfalls when applying Centralized vs Decentralized:**

- **Treating it as a hierarchy.** Decentralized isn't "better" — it's a different shape. Some senior designers prefer centralized work for the craft mentorship.
- **Forcing the binary.** Hybrid environments are real; if the user worked at a 200-person org with embedded designers but a UX guild, name the hybrid honestly.
- **Skipping it entirely.** Without naming the environment, the cadence frameworks don't land. Slicing assumes decentralized; House Analogy reads centralized work as waterfall by default. Surface the environment first.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 8/23 transcripts.

---

## Read-the-Titles-Only Test {#titles-only-test}

**Use when:** Case-study rewrites where the designer has all the right content but readers aren't getting through. The skim diagnostic.

**The structure (a passes/fails barometer, verbatim from streams):**

- Strip out all body content.
- Read **only the section titles** of the case study, top to bottom.
- If the titles alone tell the story (problem → process → outcome), the case study passes.
- If the titles are checkbox words ("Intro", "Challenges", "Solution") that don't carry narrative, the case study fails.

Verbatim: *"the barometer for success here is if you take your case study and you only read the titles, one should still have an understanding of the process that you utilized."* Companion: case study should read closer to a [Children's Picture Book](#picture-book) than an essay.

**Generative move:** rewrite each section title as a story-bearing sentence. "Intro" → "Who is Cratillo?", "Challenges" → "Why this process doesn't work", "Solution" → "What we shipped that finally moved the number."

**Apply to a portfolio:** Run the test on every case study. If a reader scrolling fast (most of them) only sees the titles, the titles need to carry the narrative. The body content is for the deep readers.

*This case study fails the **Read-the-Titles-Only Test**. The section titles are: "Intro," "Research," "Process," "Solution," "Reflection." Read top to bottom, those tell no story. Rewrite as story-bearing titles: "Why analysts couldn't find what they needed," "What 8 user interviews changed in the brief," "The two prototypes — and why we killed the second," "What shipped, what moved, what we got wrong." Same case study, now legible at skim.*

**Common pitfalls:**

- **Confusing titles with headlines.** Titles still need to be terse. "Why analysts couldn't find what they needed" works; "After conducting comprehensive ethnographic research, we discovered that the analyst persona experienced significant friction…" is a paragraph, not a title.
- **Over-cleverness.** Titles should be honest about what's in the section, not metaphors that require the body to decode.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 8/23 transcripts.

---

## Children's Picture Book Rhetoric {#picture-book}

**Use when:** Long, content-rich case studies that aren't consumable. Junior portfolios that fear cutting words.

**The structure (guiding metaphor, verbatim from streams):**

*"Your case study should be closer to that of a children's picture book than that of an essay."*

Caveat (also verbatim): *"I think what people receive from that is, oh, I should just not include text in my case study. And that's really not what I mean… I'm a big fan of long case studies, lots of content case studies."*

The mechanic: write all the content first, then convert as much of it as possible into imagery. Most readers skim; images and titles do the heavy lifting. Deep readers find the section they want and pause there.

**Apply to a portfolio:** Pair with [Read-the-Titles-Only Test](#titles-only-test). If a case study fails the titles test, the picture-book treatment is the rewrite — convert paragraphs into annotated images, captioned diagrams, before/after screenshots.

*This case study is essay-shaped per **Children's Picture Book Rhetoric** — six paragraphs of process narrative with no images between them. Don't cut the words; convert them. Each paragraph should anchor on an image: an annotated wireframe, a before/after pair, a flow diagram, a screenshot with callouts. The deep reader still gets the prose; the skimmer gets the visual story.*

**Common pitfalls:**

- **Reading it as "delete text."** It isn't. The full text stays — it just gets surrounded by imagery that lets skimmers consume the case study at image-speed.
- **Decorative images.** Images need to carry information. A stock photo of "people collaborating" doesn't help the reader; an annotated screenshot of the broken state with red callouts does.
- **Missing captions.** Per stream pattern: every image earns a caption. The caption is what the skimmer reads.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 4+ transcripts.

---

## JJJ (Jolt / Journey / Jackpot) {#jjj}

**Use when:** Case-study opening sections, hero/landing copy, narrative-flow diagnostics.

**The structure (3-beat storytelling mechanic, verbatim from streams):**

- **Jolt** — the hook; something that grabs attention (visual or verbal)
- **Journey** — the story; *"tell them something that feels complete but prompts them to want to engage more"*
- **Jackpot** — the reward; *"tell them why it matters and give them some kind of reward at the end"*

Verbatim disclosure: *"I didn't invent this, by the way."* Companion acronym: **AIDA** (Attention, Interest, Desire, Action) from sales/marketing — JJJ and AIDA are roughly interchangeable, JJJ for storytelling, AIDA for sales.

**Apply to a portfolio:** Use as a hero/case-study-opening diagnostic. If the hero has no jolt (nothing grabs the reader), the rest of the page won't get read. If the case study has no jackpot (no payoff at the end), the reader leaves unsatisfied.

*This case study has the **Journey** in **JJJ** — the middle 70% reads well — but skips the **Jolt** and the **Jackpot**. Opens on "Background and methodology" (no jolt), closes on "We presented final designs to the team" (no jackpot). Rewrite the opening as a one-line jolt: "We had a 38% cart-abandonment rate. Here's what we did about it." Rewrite the close as a jackpot: "Drop-off cut from 38% to 22% in 6 weeks. The address-confirmation rewrite was the main lever; what surprised us was that the inline-validation pattern broke for 11% of EU users — we'll fork that next."*

**Common pitfalls:**

- **Confusing Jolt with shock.** The jolt is attention-grabbing, not jarring. A surprising number, a specific scene, a problem named concretely — all qualify. A loud animation does not.
- **Inflating Jackpot.** If the project didn't move a number, don't fake one. Reach for [Hard Metrics vs Soft Metrics](#hard-soft-metrics) — a behavior-change claim is a legitimate jackpot.
- **Treating it as a template.** JJJ is a diagnostic, not a section structure. The jolt-journey-jackpot beats can live across multiple sections; what matters is that the reader experiences all three.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 5/23 transcripts.

---

## KSAs (Knowledge / Skills / Abilities) {#ksas}

**Use when:** Resume reviews, case-study housekeeping, ATS-rejection diagnostics. Borrowed from HR canon, operationalized for designers.

**The structure (verbatim from streams):**

- **Knowledge** — what you know (domain, tools, methodologies named verbatim from the job description)
- **Skills** — what you can do (executional capabilities)
- **Abilities** — broader capacities (cross-functional, leadership, communication)

The mechanic: ATSs measure resumes by KSA-match against the job description. The candidate's job is to extract KSAs from each job description and seed them into the resume + case-study [Housekeeping](#housekeeping) sections. Verbatim: *"KSAs are the currency by which one measures the candidates that apply for these jobs."*

**Apply to a portfolio:** Pair with [Housekeeping](#housekeeping). When a resume isn't getting through ATS, check whether the JD's named knowledge (e.g., "Figma", "fintech", "B2B SaaS"), skills (e.g., "user research", "prototyping", "wireframing"), and abilities (e.g., "stakeholder management", "facilitation") appear in the resume + housekeeping. Missing KSAs = missing keyword match = ATS rejection.

*This resume isn't surfacing **KSAs** per the JD it's targeting. The JD names "B2B SaaS, fintech, design systems, stakeholder management" as required. The resume names "product design, UX research, Figma." Per the framework, those are non-overlapping KSA sets — the ATS rejects this resume, and the recruiter doesn't see it. Rewrite: pull the JD's exact KSAs into the resume's housekeeping line and seed them into the bullet structure. "Designed B2B SaaS fintech flows in Figma; stakeholder management with PM + 4 engineers" — same project, KSA-aligned.*

A second application: case studies. When the case study's [Housekeeping](#housekeeping) block lists tools but not the JD's named methodologies, the keyword match fails. Add the JD's methodologies (e.g., "qualitative + quantitative research," "Lean UX," "Design Systems") to the housekeeping if they were used. Don't fabricate — but if you ran user interviews, "qualitative research" belongs in housekeeping when the JD asks for it.

**Common pitfalls:**

- **Stuffing.** Listing every KSA from every JD turns the resume into noise. Tune per-application; rewrite housekeeping per-target.
- **Translating verbatim words.** If the JD says "ethnographic research" and you ran "user interviews," use the JD's exact phrase if your work qualifies. If it doesn't qualify, don't.
- **Treating KSAs as the whole resume.** KSAs are the keyword-match layer. The bullets still need [What/How/Why](#what-how-why) shape.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 5/23 transcripts.

---

## Hook → Proof → Story {#hook-proof-story}

**Use when:** Case-study sequencing reviews, hero rewrites, "outcome-buried" diagnostics. The streams-native framework for case-study order — used in place of Inverted Pyramid in stream reviews.

**The structure (3-beat sequence, verbatim from streams):**

1. **Hook** — TLDR-shaped opening (problem + outcome stated up front)
2. **Proof** — visual/empirical evidence the claim is true (UI design, screenshots, numbers)
3. **Story** — the narrative explaining the journey, decisions, alternatives

Verbatim: *"You're essentially giving me the hook, giving me the proof, now you're giving me the story."* Pairs with the **TLDR Hero** test (the hero of any page should read as a TLDR — reader can decide in 5–10 seconds whether to keep going).

**Apply to a portfolio:** Walk every case study. If the outcome lives in paragraph 6, the case study leads with story instead of hook. Move the hook (problem + outcome) to the top, then proof, then expand into story.

*This case study buries the outcome per **Hook → Proof → Story**. The outcome paragraph is in scroll 6 of the [project name] case study. Per the framework, lead with the hook: one line on problem + outcome at the top. Then proof: the before/after screenshots and the number. Then story: the six paragraphs of process narrative for the deep reader. Right now the order is Story → Proof → Hook, which is backwards.*

A second application: hero rewrite. Most case-study heroes lead with the project title and a stock visual. Per Hook → Proof → Story, the hero should read as a TLDR — problem + outcome in one line, proof visual right below. The story expands below the fold.

**Common pitfalls:**

- **Reading "lead with hook" as "skip the story."** It isn't. The story still belongs in the case study — it just doesn't open it. Senior reviewers want the story; they'll scroll for it once the hook earns the scroll.
- **Confusing Proof with hero image.** A stock photo isn't proof. Proof is a screenshot of the shipped UI, a number, an annotated before/after — concrete evidence the claim in the hook is real.
- **Skipping the Hook because the project is "obvious."** No project is obvious to a reader who's never seen it. The hook makes the problem and outcome legible in one sentence; without it, even strong proof and story fail.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 5/23 transcripts.

---

## Hard Metrics vs Soft Metrics (Behavior Change) {#hard-soft-metrics}

**Use when:** Case studies missing impact numbers, NDA'd projects, side projects, internal tools. The "I can't share / didn't measure" diagnostic.

**The structure (verbatim from streams):**

- **Hard metric** — quantifiable business or product number (conversion +X%, drop-off −Y%, retention +Z%, NPS, revenue)
- **Soft metric (Behavior Change)** — qualitative validated outcome ("analysts no longer have to use this software to find what they're looking for"; "users now complete this task without contacting support")

Verbatim: *"that's a soft metric and is still a validation of success and building momentum in the correct direction."* Tim's accompanying citation: book *Designing for Behavior Change*. Operating rule: hard > soft when available; soft is honest when hard isn't accessible. The two are NOT interchangeable — hard outranks soft, but soft beats silence.

**Apply to a portfolio:** Walk every case study's outcome paragraph. If there's no hard metric, ask whether a behavior change can be claimed concretely. Pair with [Prototyping with Numbers](#prototyping-with-numbers) for the third escalation when neither hard nor soft is available.

*This case study has no **Hard Metric** and no **Soft Metric (Behavior Change)** per the framework. Outcome paragraph reads: "We presented the final designs to the team and got positive feedback." That's neither hard nor soft — it's silence dressed as outcome. If the project shipped, name the behavior change concretely: "Analysts no longer have to open three tools to compile the weekly report — the consolidated view replaces all three." That's a soft metric and it's honest. If the project didn't ship, see [Prototyping with Numbers](#prototyping-with-numbers).*

The escalation order is the rule. Hard metric first (best). If unavailable, behavior change (good). If neither, prototyped numbers (creative). Never skip up the ladder by claiming a stronger metric than you have. Hiring managers clock inflated hard metrics instantly; an honest soft metric reads more senior than a fabricated hard one.

**Common pitfalls:**

- **Calling team feedback a metric.** "The team loved it" is neither hard nor soft. It's not a metric.
- **Inventing percentages.** "Improved engagement 25%" with no measurement attached gets clocked. If the number isn't real, drop to behavior change.
- **NDA hiding all evidence.** Behavior change can be claimed without revealing proprietary numbers. "Reduced average task completion time by approximately half" is shareable; the underlying timing data isn't.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 6/23 transcripts.

---

## Prototyping with Numbers {#prototyping-with-numbers}

**Use when:** Personal projects, side projects, conceptual work, NDA'd work where the actual metrics can't be shared. The senior-track narrative move for demonstrating business literacy.

**The structure (Tim's framing, verbatim):**

1. Pick a comparable real product (e.g., Headspace).
2. Find its public business or behavior numbers (revenue, retention, satisfaction).
3. State: *"if there was an app similar to mine, here's what the business outcome would have been at this scale."*
4. Then: scale that prediction down to the size of the project you actually shipped.

Verbatim: *"you're attaching measurable things to your predicted outcomes, which again reflects the way you talk about your value and your business acumen."* Disclosure: *"it's a thing I call prototyping with numbers, and when I say I call it prototyping with numbers, it's actually someone else who coined that phrase that I now use as well."*

Broader argument: *"designers are late to the party because everyone else already does this. If you look at any project proposal, any investment proposal, those are the things they include."*

**Apply to a portfolio:** Three escalating moves for the no-metric problem: Hard metric (best) → Behavior Change (good) → Prototyped numbers (creative). Use this for case studies that are conceptual, side-project, NDA'd, or otherwise number-less.

*This side-project case study has no **Hard Metric** and no **Soft Metric**. Per **Prototyping with Numbers**, name a comparable: "Headspace's free-to-paid conversion is around 5% per published reports. If this concept reached 10K daily active users at that conversion, the equivalent business outcome would be ~500 paying subscribers — at Headspace's reported $70/year, that's ~$35K/year revenue at this scale." Now the case study has a business-literate frame, and the disclosure that this is a prediction (not a shipped result) makes it honest.*

**Common pitfalls:**

- **Treating it as a hard metric.** Prototyped numbers are predictions, not results. Always disclose: "if this had shipped at scale" or "comparable benchmark."
- **Picking implausible comparables.** "If my todo app reached Apple's revenue scale" isn't useful. Pick a comparable in the same category and stage.
- **Skipping the senior-track move.** This framework is the move designers hesitate on. Stream pattern: most designers don't reach for prototyped numbers because it feels like cheating. It's not cheating — it's the standard move in product proposals and investment decks. Designers who use it read more senior than those who don't.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 3+ transcripts.

---

## Designer Niche Scales {#niche-scales}

**Use when:** Career-direction conversations, positioning audits, generalist portfolios with no clear angle. The diagnostic for "I don't want to niche down because I'll lose opportunities."

**The structure (multi-axis "shape of designer," verbatim from streams):**

Niche is not one-dimensional (industry-only). Niche = the designer's *shape* across multiple scales:

- **Domain familiarity** — agnostic ↔ embedded in one industry (healthcare, fintech, etc.)
- **Elevation** — tactical ↔ strategic (UI output ↔ team leadership)
- **Product stage** — zero-to-one ↔ scaling enterprise
- **Organization stage** — startup ↔ enterprise

Verbatim: *"niche doesn't mean you go into one specific spot and stay there. It means you've got opinions on all of these other things, and then you hone in what organizations you apply for because they also meet your criteria of your shape as a designer."*

Counter to common designer rhetoric: *"you'll have other people say niching down will kill you and it will get you stuck… we are in agreement that niching does not mean you can only do one trick."*

**Apply to a portfolio:** Pairs with [Ladders](#ladders). Ladders says "find a competitive lane where you can win"; Niche Scales says "your win-condition is the *shape* you take across these axes." Use together when a designer is generalist-positioned and needs to find their angle.

*This portfolio is generalist-positioned per **Designer Niche Scales** — the about page says "product designer with experience across SaaS, e-commerce, and consumer apps." Per the framework, walk the four axes: domain familiarity (agnostic), elevation (tactical, no leadership claims visible), product stage (mixed — both 0-to-1 and scaling work shown), org stage (mixed — startups and one enterprise role). The shape that emerges: agnostic-tactical generalist who has touched both stages. That's a real shape, and it's hireable in some markets — but the about page doesn't name it. Rewrite as: "Tactical product designer; comfortable in both 0-to-1 and scaling work; domain-agnostic. Best fit for teams that want a designer who ships fast across surfaces, not one who specializes in one industry." Now the shape is legible.*

A second application: career-switcher portfolios. The prior career almost always defines a domain-familiarity axis where the switcher is rung 1 or 2 (e.g., ex-RN in healthcare, ex-teacher in EdTech). Per Niche Scales + [Ladders](#ladders), lead with that axis as the spine of positioning. The other three axes — elevation, product stage, org stage — refine the shape.

**Common pitfalls:**

- **Treating niche as industry-only.** This is the most common mistake. Niche has four axes; industry is one of them. A "design systems specialist who works across industries" is just as niched as a "healthcare-only product designer."
- **Picking axes you can't defend.** If the user has 8 months of healthcare experience, "domain-embedded in healthcare" doesn't yet hold. Pick the axis position you can prove.
- **Forcing a single shape.** Some designers legitimately operate at multiple shapes (e.g., consultant pattern). The framework still works — just name the multiple shapes explicitly rather than letting the portfolio read as undifferentiated.

**Source:** @designshaped Friday-stream corpus, see `mining-log.md`. 4+ transcripts.

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

This is the lens we reach for first when asked "review my whole portfolio holistically" at the product-team-artifact level. For portfolio-only audits, see [Three Target Audiences](#three-target-audiences) — the streams-native 3-audience compression. Both are valid; pick by review surface.

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

The "decentralized product environment" framing is the second senior signal. Nate's verbatim: "the UX designer ends up being a team leader… You are the person that builds team alignment. You facilitate how these processes should function, and you are the person that ends up re-encouraging that mindset of getting things right eventually and not on the first try." For senior portfolio review, this is the "leadership without authority" frame — the case study should show the designer shaping the team's posture, not just the product's. This connects directly to [Centralized vs Decentralized Environments](#centralized-decentralized) — Dual Track Agile assumes the decentralized environment; surface the prerequisite first.

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

> **CRITICAL: Distinct from [Trust Ladder](#trust-ladder).** Ladders is rung-based competitive positioning. Trust Ladder is within-page conversion sequencing. They share a metaphor but answer different questions. Cite by full name to avoid confusion.

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

The Ladders move pairs with [Brand Drivers](#brand-drivers) and [Designer Niche Scales](#niche-scales): Brand Drivers gives you the language for the niche; Niche Scales tells you which axes to position on; Ladders tells you whether to make the niche your whole positioning. For senior portfolio reviews, "make a new ladder" is one of the most common reframes we offer. It pairs especially well for career-switcher portfolios — the prior career almost always defines a niche ladder where the switcher is rung 1 or 2 (e.g., ex-teachers in EdTech, ex-nurses in healthcare, ex-engineers in dev tools). The Ladders move says: lead with that niche; the generalist roles open up later.

**Common pitfalls when applying Ladders to portfolio review:**

- **Confusing with Trust Ladder.** They're different frameworks. Cite "Ladders" or "Nate's Ladders" when the topic is positioning; "[Trust Ladder](#trust-ladder)" when the topic is within-page conversion.
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

---

## Cross-framework patterns

Several patterns show up across multiple frameworks here. Workflow agents should recognize them.

**The honest-claim pattern.** [The 80% Principle](#the-80-percent-principle), [Component Library → Design System Progression](#component-library-design-system-progression), [Proto Persona](#proto-persona), and [Hard Metrics vs Soft Metrics](#hard-soft-metrics) all share the same underlying move: prefer the smaller honest claim over the bigger fabricated one. When reviewing a portfolio that over-claims, reach for whichever of these four frameworks fits the specific over-claim. The verbatim pattern: name what was actually built, label it precisely, and don't apologize for the smaller scope. Hiring managers reward precision; they punish inflation.

**The cadence-and-rhythm pattern.** [Slicing](#slicing), [Dual Track Agile](#dual-track-agile), [House Analogy](#house-analogy), and [Centralized vs Decentralized Environments](#centralized-decentralized) all diagnose the same gap: case studies that compress iteration into a single block. The frameworks attack the gap from four angles — Slicing names the iteration unit, Dual Track Agile names the designer-to-engineering rhythm, House Analogy names the posture (waterfall vs. agile), Centralized vs Decentralized names the prerequisite environment. For most senior reviews, citing one or two of the four by name is enough. For a particularly process-thin case study, all four can apply.

**The positioning-and-narrative pattern.** [Brand Drivers](#brand-drivers), [Ladders](#ladders), [Designer Niche Scales](#niche-scales), [Ethos / Pathos / Logos](#ethos-pathos-logos), [Stakeholder Needs Map](#stakeholder-needs-map), and [Three Target Audiences](#three-target-audiences) are the cluster for "this portfolio is technically fine but not landing." Brand Drivers gives the language. Ladders tells you which competitive lane you're in. Niche Scales tells you the multi-axis shape that defines the lane. Ethos/Pathos/Logos diagnoses which audience response is missing. Stakeholder Needs Map and Three Target Audiences audit which readers the portfolio talks to. When asked "review my whole portfolio holistically" or "I'm not getting interviews," start in this cluster.

**The case-study-shape pattern.** [What/How/Why](#what-how-why), [Hook → Proof → Story](#hook-proof-story), [JJJ](#jjj), [Read-the-Titles-Only Test](#titles-only-test), [Children's Picture Book Rhetoric](#picture-book), and [Housekeeping](#housekeeping) all attack case-study consumability. What/How/Why operates at the bullet level; Hook → Proof → Story at the case-study sequence; JJJ at the opening beat; Read-the-Titles-Only Test at the section-title level; Picture Book at the prose-vs-imagery balance; Housekeeping at the recruiter-readable factual block. Combined, they cover every layer of how a case study gets consumed.

**The metric-evidence pattern.** [Hard Metrics vs Soft Metrics](#hard-soft-metrics) and [Prototyping with Numbers](#prototyping-with-numbers) form the escalation: hard metric → behavior change → prototyped numbers. Use the order verbatim. Never claim higher on the ladder than the evidence supports.

**The Ladders distinction (cross-framework critical note).** [Ladders](#ladders) (Nate's competitive positioning) and [Trust Ladder](#trust-ladder) (within-page conversion sequencing) share a metaphor but answer different questions. They co-occur often in reviews. Always cite by full name. Do not merge.

---

## Adding new frameworks

This file is additive (per CONTENT-05). New frameworks land here as Tim+Nate mine them from Friday-stream transcripts on the @designshaped YouTube channel, or as Nate publishes new articles on nabauer.com.

When adding a framework:

- **Pull text verbatim from the source.** Don't paraphrase — the voice's authenticity comes from quoting Nate's (or Tim's) actual words. If a quote is missing, mark it `[verbatim source TBD]` and ship; don't invent.
- **Match the existing section template.** Name (anchor), Use when, The structure, Apply to a portfolio, Source. The template's order is the workflow agent's read order — don't reorder.
- **Append, don't rewrite.** Add the new framework to the bottom of its group in the Index, then add the section to the bottom of the file. Workflows already cite existing anchors — don't break those citations.
- **Cite the transcript or article.** New patterns from streams cite the transcript line in the private `mining-log.md` (per D-17 — Tier 1 mining doesn't require re-contact, but the audit trail does). New articles cite the URL.
- **Earn the section.** Not every observation Nate or Tim makes on stream is a framework. A framework has structure (named beats, a stop rule, a sequence, or a diagnostic). One-line heuristics belong in `references/heuristics.md`, not here. Test: can a workflow agent quote the structure verbatim and apply it without paraphrasing? If yes, it's a framework. If no, it's a heuristic.

The ceiling on this file is roughly 25 frameworks. We're at 25 now (12 Nate + 13 stream-mined). Past that, the workflow agent's "load only what you need" pattern starts breaking down. If we approach the ceiling, split into framework-card files (the dmba pattern) — one file per framework, with this file becoming the index.

When in doubt about whether a candidate framework crosses the bar, route to Tim+Nate. The voice depends on these being right, not on these being many.
