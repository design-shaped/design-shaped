# Common flags — Portfolio Rx

## How this file is used

Workflows surface flags from this file when the corresponding pattern appears in user-submitted work. Each flag is small, self-contained, and produces a concrete rewrite. New flags are appended (never rewritten in place); each gets a unique ID and a `last-affirmed` timestamp.

A flag fires when the workflow can quote the user's actual work back to them and map it to one of the patterns below. If we can't quote it, we don't flag it — that's the difference between critique and roast.

## Conventions

- IDs: `P##` for portfolio flags, `R##` for resume flags. (Add `M##` later for mock-interview flags if/when needed.)
- Each flag has: ID, name, pattern (what triggers it), cost (what the user loses), fix (concrete rewrite or move), source.
- New flags are appended to the bottom of the relevant section. Existing IDs are stable — never reuse, never renumber.
- `last-affirmed` is a YYYY-MM date. When transcripts are re-mined, the affirming reviewer (Tim or Nate) updates the date. If older than 6 months, surface a "this flag may be stale" note in the review.
- **High-confidence** flags appeared across ≥4 stream transcripts independently. Treat them as load-bearing — if the user's work hits one of these, it goes in the Top 3 fixes.
- **Single-source** flags appeared in only one stream. Use them, but weight them less heavily until a second stream confirms.

## Portfolio flags

### P01 — Hero doesn't say what kind of designer you are (high-confidence) {#P01}
**Pattern:** Hero reads "Hi, I'm [name]" or generic "designer creating user-centered experiences" — no specialty, no industry, no level. The user could be anyone.
**Cost:** Recruiter lands here, can't tell in five seconds what role they're being asked to consider you for. They bounce. The site has done the work of marketing the platform, not the person.
**Fix:** Write a value-prop sentence that names who you are, what you do, the target audience, and the benefit you deliver. "Senior product designer. I ship complex flows in B2B SaaS. Looking for design lead roles at Series B-D." If the line could be copy-pasted onto someone else's portfolio and still fit, it's too generic.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=AVyzs8UBzmo; https://www.youtube.com/watch?v=EYgmghBYdbE; https://www.youtube.com/watch?v=U_fXJRoUv5U; https://www.youtube.com/watch?v=Q-De5H259hQ
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P02 — Generalist positioning across competing titles (high-confidence) {#P02}
**Pattern:** Portfolio claims UX/UI/product designer all at once, or graphic-and-UX-and-research, or industries listed as "SaaS, healthcare, fintech, ed-tech." Three or more titles or industries get equal weight.
**Cost:** When the market is tight, generalists get outbid by specialists every time. A reviewer who needs a fintech designer reads "I do everything" as "she's not focused on this" and moves on. Every category you claim, you lose authority on.
**Fix:** Pick one title and one or two adjacent industries. Build the whole portfolio around that posture. The cut categories don't disappear — they get demoted to the about page or a "selected work" footnote, not the hero.
**Source:** https://www.youtube.com/watch?v=EYgmghBYdbE; https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=Q-De5H259hQ; https://www.youtube.com/watch?v=AVyzs8UBzmo
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P03 — Case study skips process, jumps from problem to solution (high-confidence) {#P03}
**Pattern:** Case study has a problem statement, then immediately shows the final UI. Missing the middle — the discovery, the framing, the trade-offs, the why behind the design choices.
**Cost:** A hiring manager doesn't care about the output as much as how you got there. With no process, the case study positions you as a UI executor, not a UX or product designer. If you're targeting senior or product, you've just disqualified yourself.
**Fix:** Add the middle section. Show how you broke down the business problem, who you talked to, what you tried, what you cut, what you'd do differently. The output is the smallest part of the case study; the decision trail is the work.
**Source:** https://www.youtube.com/watch?v=UXCAoN-FSFo; https://www.youtube.com/watch?v=EYgmghBYdbE; https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=Fe4Md-UR1EE; https://www.youtube.com/watch?v=vRxJGuJdk6k
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P04 — Case study sells the company instead of the candidate (high-confidence) {#P04}
**Pattern:** Case study reads as marketing for the product or client — "Carvana wanted to..." "Sun Life's mission is..." — with the designer absent. The user's name barely appears. Everything is "we" or the brand.
**Cost:** A reviewer comes here to hire you, not to learn about your former employer. With no "I" in the story, the reviewer can't tell what you contributed or whether you're worth interviewing. The recurring stream phrasing: "I came here to buy you, not the company."
**Fix:** Reframe every section through your work. "I led the research." "I made the call to cut the personalization spike." "My recommendation was X; the team pushed back; we shipped Y." Use "we" only where it's literally accurate. One short paragraph near the top names the team composition and what you specifically owned.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=AVyzs8UBzmo; https://www.youtube.com/watch?v=Q-De5H259hQ; https://www.youtube.com/watch?v=oZqAPmWsDHU; https://www.youtube.com/watch?v=EYgmghBYdbE
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P05 — Section titles are checkbox labels, not the story (high-confidence) {#P05}
**Pattern:** Section headers read "Overview," "Research," "Process," "Wireframes," "Final Design," "Impact." The titles describe formats, not findings.
**Cost:** Hiring managers skim. They read titles, not paragraphs. If the titles are generic format names, the skimmer learns nothing — the case study reads as a template the user filled in. If the work is good, no one will know.
**Fix:** Rewrite each title to summarize the section's argument. "Building blocks" becomes "Why we picked opinionated primitives over a federated kit." "Research" becomes "Eight drivers told us the same thing about handoffs." Barometer test: if a reader only reads the titles, can they still follow the story? If not, the titles aren't doing their job.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=UXCAoN-FSFo; https://www.youtube.com/watch?v=EYgmghBYdbE; https://www.youtube.com/watch?v=4tg1bPbOxus
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P06 — Outcome buried, generic, or missing entirely (high-confidence) {#P06}
**Pattern:** Case study ends with "users loved it" or "improved the experience." No metric, no behavioral signal, no honest "we couldn't measure this and here's why." Or the outcome lives in paragraph six instead of the top.
**Cost:** Without an outcome, the case study reads as a process diary. The reviewer can't tell whether the work shipped or moved a number. At mid-and-up levels, no outcome = no signal that the user makes decisions that matter. Recurring stream verb: "buried."
**Fix:** Tease the outcome at the top of the case study, then expand it at the bottom. Use real metrics where they exist ("38% → 22% drop-off, n=14k, Mixpanel Q3"). Use behavioral signals when metrics don't exist ("the team adopted this as the default pattern across three surfaces"). Honest "we shipped it but couldn't instrument it, here's what I'd measure next time" beats fabricated numbers.
**Source:** https://www.youtube.com/watch?v=UXCAoN-FSFo; https://www.youtube.com/watch?v=Fe4Md-UR1EE; https://www.youtube.com/watch?v=AVyzs8UBzmo; https://www.youtube.com/watch?v=EYgmghBYdbE
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P07 — Wall of text, no image-to-text balance (high-confidence) {#P07}
**Pattern:** Case study is mostly long paragraphs with few visuals, or visuals are tiny, decorative, or shoved at the bottom. Text leaks past 1000+ pixels wide so even the body copy is hard to track.
**Cost:** People skim. If the case study has no entry points — no headers, no annotated images, no callouts that earn their place — the reader bounces before the work registers. A picture book that tells the story will outperform an essay every time.
**Fix:** Treat case studies like a children's picture book with sophisticated content underneath. Every major decision gets one image, captioned to stand alone. Constrain body copy to ~600-800px wide for readability. Annotate screenshots — point at the change, label the parts. The image carries 80% of the load; the text supports.
**Source:** https://www.youtube.com/watch?v=SPxfv9ZnOjg; https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=AVyzs8UBzmo; https://www.youtube.com/watch?v=EYgmghBYdbE
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P08 — AI-written copy that sounds like Claude {#P08}
**Pattern:** Case study uses "this isn't X, it's Y" rhythm over and over. Dramatic dichotomies. "Speed isn't the value, alignment is." "Data was everywhere, priorities nowhere." Often pretty, rarely the user's voice.
**Cost:** The case study is supposed to be evidence of your judgment and voice. AI prose all sounds the same and a reviewer who reads a lot of portfolios will clock it on the second paragraph. It also makes a hiring manager wonder what else was AI: the research, the decisions, the metrics?
**Fix:** Use AI for outlining, not writing. Brain-dump the project in your own words first, then ask AI to help you organize, not to phrase. When AI gives you a "this not that" line, rewrite it as a normal sentence. The voice that gets you hired is yours.
**Source:** https://www.youtube.com/watch?v=SPxfv9ZnOjg; https://www.youtube.com/watch?v=D0BG1wPj4WM
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P09 — Visual-craft inconsistencies that signal the taste level (high-confidence) {#P09}
**Pattern:** Mixed font weights for the same hierarchy. Cards with different border-radius rules. Margin breaks across sections. Hover states on things that aren't clickable, no hover state on things that are. Color used inconsistently to group sections.
**Cost:** If you're applying for product or UI roles, the portfolio itself is the test. A reviewer who sees these gaps assumes the same gaps exist in your client work. Typos and alignment errors get noticed before the case studies are read.
**Fix:** Audit the portfolio against the same standards you'd apply to a client project. One display + one body face. Set a vertical rhythm. Match border radii internal-to-external by the right ratio (external = internal + padding). Reserve hover/animation for things that are actually interactive. The portfolio is the most important case study in the portfolio.
**Source:** https://www.youtube.com/watch?v=SPxfv9ZnOjg; https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=Q-De5H259hQ; https://www.youtube.com/watch?v=EYgmghBYdbE
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P10 — Behance/Dribbble as primary portfolio {#P10}
**Pattern:** Resume points to a Behance grid as the primary portfolio. No standalone site.
**Cost:** Behance serves Behance. The platform pushes Adobe sign-up modals, advertises other designers below your work, and gates contact through their auth flow. Behance wants to win, not for you to win. Anyone serious about hiring you has to fight the platform to do it.
**Fix:** Build a standalone site, even a simple Framer or Webflow page, even a Notion site if that's all you have time for. Keep Behance as a secondary "selected shots" link if useful, but the primary URL points to a page you control. Building the site is also a UX deliverable — recruiters who see "I can ship a real product surface" weight that more than a Behance grid.
**Source:** https://www.youtube.com/watch?v=D0BG1wPj4WM; https://www.youtube.com/watch?v=AVyzs8UBzmo
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P11 — Animation noise and scroll-jacking distract from the story (high-confidence) {#P11}
**Pattern:** Multiple animations firing at the same time on the hero — pulsing "open to work" indicator, animated greeting, ambient motion graphics, plus zoom-on-hover on each project card. Scroll-jacking page that intercepts the scroll wheel.
**Cost:** Animation is supposed to direct attention, not split it. When everything moves, nothing reads as the priority — the user can't tell what to look at and bounces. Scroll-jacking outright betrays user expectations: the page scrolls slower than the user wants, the content jumps past where they wanted to land. They leave.
**Fix:** Cut motion to one or two intentional moments per page that direct the eye where you want it. Hover states only on things that are actually clickable. Stop scroll-jacking. Animations should consistently use the same easing, the same hover treatment — if a card scales on hover, every card scales on hover, and the rule is documented in your own head.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=SPxfv9ZnOjg; https://www.youtube.com/watch?v=UXCAoN-FSFo; https://www.youtube.com/watch?v=VLNRqtqHIp0
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P12 — Case study tile teaser doesn't differentiate (high-confidence) {#P12}
**Pattern:** Project tiles on the home page show identical-looking screenshots and titles like "Acme Redesign," "Thing App," "Project 3." Nothing tells the reviewer which to click. Mouse hover required to see what each is about.
**Cost:** A reviewer with two minutes will click the first one, find it weak, and leave. With no opinionated framing on the tile, there's no way to put your strongest project where they'll see it. Every tile says enough, even unclicked, that the reviewer knows what they'd be reading.
**Fix:** Each tile gets an outcome-first title and a one-line teaser. "Reduced fleet-monitor cognitive load 28% — B2B SaaS, sole designer, 2024." Show one strong screen, not a generic mockup. Strongest project goes first; rank deliberately.
**Source:** https://www.youtube.com/watch?v=SPxfv9ZnOjg; https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=oZqAPmWsDHU; https://www.youtube.com/watch?v=Q-De5H259hQ
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P13 — Conceptual redesign of a giant company (Netflix/Airbnb) (single-source) {#P13}
**Pattern:** Case study redesigns Netflix or Airbnb wholesale. The framing implies the user's solo work outperforms the millions invested by the actual product team.
**Cost:** Reads as ego or naivety. A reviewer immediately knows it's conceptual and can't help comparing it (unfavorably) to what shipped. The case study undersells the user — same effort directed at a feature *gap* lands much better.
**Fix:** Pivot from "I redesigned Netflix" to "I added a feature Netflix doesn't ship — discovery via mood." Now you're solving a problem the actual team had reasons not to ship, and the framing invites the reviewer to evaluate your judgment, not your audacity.
**Source:** https://www.youtube.com/watch?v=oZqAPmWsDHU
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P14 — Senior portfolio reading as execution, not strategy (high-confidence) {#P14}
**Pattern:** Case studies on a senior or staff portfolio walk through tactical UI work — wireframes, screens, components — without showing how the user broke down business problems, navigated stakeholders, or made the call about *what* to build.
**Cost:** Senior is a level of decision-making, not pixel quality. If the case study can't show the user's thinking at the bet level — what was unclear, who decided to invest in it, why this work and not other work — the user is positioned at mid, not senior, regardless of years of experience.
**Fix:** Open every senior-track case study on the bet. Then move into the strategy: stakeholder negotiation, scope decisions, what was cut and why, cross-functional leadership moments. The output gets smaller; the decision trail gets bigger. At staff level, sometimes the case study doesn't even need final screens.
**Source:** https://www.youtube.com/watch?v=AVyzs8UBzmo; https://www.youtube.com/watch?v=Fe4Md-UR1EE; https://www.youtube.com/watch?v=vRxJGuJdk6k; https://www.youtube.com/watch?v=UXCAoN-FSFo
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P15 — NDA work hides the entire case study (single-source) {#P15}
**Pattern:** User worked on confidential B2B/finance/healthcare projects, can't show screens, defaults to either zero case study or a vague description that says nothing.
**Cost:** Without anything to show, the case study can't validate the user's judgment for hiring managers. But naming the actual brand and process publicly may breach the NDA — and reviewing strangers can't tell which side of that line you're on.
**Fix:** First check the actual NDA — many users haven't re-read theirs and assume restrictions that aren't there. Then: process and decision-making are almost never bound by NDAs. Talk about how you broke down the problem, the negotiation moves, the trade-offs — using synthetic data for screens. Frame the limitations honestly: "Specific data and screens are protected, here's what I can show about the thinking." That's a stronger story than fake screens.
**Source:** https://www.youtube.com/watch?v=D0BG1wPj4WM
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### P16 — About page either missing or generic (high-confidence) {#P16}
**Pattern:** No about page. Or an about page that's a stock-photo headshot and a paragraph that could be on any designer's site. No personality, no through-line, no reason to like working with this person.
**Cost:** The about page targets the third audience — future peers and referral sources. They're asking "would I share a cubicle wall with this person for eight hours?" A generic about page can't answer that, and referrals are the strongest hiring channel; missing this channel is a real cost.
**Fix:** Make the about page lengthy and specific. Personality, what you read, what you're learning, what kind of teams you do well in. Mash professional history into it (referrals look at both at once). Treat it like a dating profile in a professional register — give the reader enough to decide whether to refer you.
**Source:** https://www.youtube.com/watch?v=SPxfv9ZnOjg; https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=vRxJGuJdk6k
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

## Resume flags

### R01 — Bullets describe activities, not outcomes (high-confidence) {#R01}
**Pattern:** "Designed wireframes for the checkout flow." "Created user personas." "Led end-to-end design for AI questionnaire workflows." Resume reads as a list of what the user *did*, not what *resulted*.
**Cost:** Activity bullets all flatten to "they did design stuff." No way to tell whether the wireframes shipped, the flow worked, or anyone used the personas. Reviewers comparing resumes default to the one with measurable wins.
**Fix:** Reorder every bullet to lead with impact using **why-how-what** (see frameworks.md). "Improved efficiency 7x by leading end-to-end design for AI questionnaire workflows" beats the activity-first version. If a hard metric doesn't exist, use a soft signal — adoption, scope, team size. "Reduced support tickets ~10/week (anecdotal)" beats silent claim.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=UXCAoN-FSFo; https://www.youtube.com/watch?v=Fe4Md-UR1EE; https://www.youtube.com/watch?v=4tg1bPbOxus
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R02 — Two-column resume formatting breaks ATS (high-confidence) {#R02}
**Pattern:** Resume is a beautifully designed two-column layout, often built in Figma, with skills in a side rail and timeline on the right. Looks great to humans.
**Cost:** Most ATS systems strip layout and feed plain text to the parser. Two-column layouts get scrambled — words from the side rail get inserted into the middle of work bullets, dates get cut from titles, the parser sees garbage. Resume gets auto-rejected before any human reads it.
**Fix:** Single column, left-aligned, ATS-safe fonts. Skills as a comma-separated paragraph, not a styled grid. Maintain a designed PDF for direct outreach to humans (recruiters, hiring managers, referrals); keep the ATS version for portal submissions. Two versions, same content.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=EYgmghBYdbE
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R03 — Skills section as a noun salad (high-confidence) {#R03}
**Pattern:** "Figma, Sketch, Adobe XD, Miro, Notion, Jira, Linear, Slack, Trello, FigJam, Maze, UserTesting, Hotjar, Mixpanel, Amplitude, Looker..." formatted as a vertical bullet list or a multi-column block.
**Cost:** Reads as keyword-stuffing for ATS. Recruiters who actually read it discount the section. The bullet/column formatting also breaks ATS parsing — the parser may see broken words like "F igma" with literal spaces.
**Fix:** Trim to tools you're genuinely fluent in. Group by category as a paragraph: "Design: Figma, FigJam. Research: Maze, dscout. Analytics: Amplitude, Mixpanel." Five to eight items max, organized. Skills section goes below experience and education, not above.
**Source:** https://www.youtube.com/watch?v=EYgmghBYdbE; https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=UXCAoN-FSFo
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R04 — One-page rule applied as a religion {#R04}
**Pattern:** Mid-or-senior user has cut their resume to one page even though they have 6+ roles to describe. Bullets are tight to the point of being uninformative. Skills section squeezed into one line.
**Cost:** The one-page rule originated when resumes were printed and stapled. In a digital-submit-via-portal era, the constraint is irrelevant. A senior who cuts to one page loses the chance to describe scope, ownership, and decision-making — the things that actually win the role.
**Fix:** Two pages is fine for 5+ years of experience. Use the second page only if it's at least mostly full — empty space at the bottom of page two looks worse than ending page one cleanly. Senior resumes especially benefit from the extra room to describe scope.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=UXCAoN-FSFo
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R05 — Job titles don't match target role (high-confidence) {#R05}
**Pattern:** User applies for "Senior Product Designer" with titles like "UX/UI Contractor," "Digital Experience Creator," internal-only titles, or "Designer" alone with no level. ATS keyword scan misses the match.
**Cost:** Recruiters and ATS systems pattern-match on title strings. A non-standard or internal title gets filtered out at the first pass even when the work was identical. The user disqualifies themselves before the bullets get read.
**Fix:** Where truthful, translate the internal title to industry-standard. "Digital Experience Creator" becomes "Senior UX Designer (internal title: Digital Experience Creator)" — keeps honesty, surfaces the keyword. Lead the resume with the title you're applying for ("Senior Product Designer") so the ATS and the recruiter both see it within two seconds.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=EYgmghBYdbE
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R06 — Generic professional summary (single-source) {#R06}
**Pattern:** Top of resume reads "Passionate UX designer with X years of experience creating user-centered digital experiences." Could apply to any designer.
**Cost:** The summary takes the most expensive real estate on the resume — the top third — and adds nothing the rest of the resume doesn't already say worse. AI-summarizing tools (which many recruiters use) will lock onto this generic line as the user's identity, "prompt-poisoning" the rest of the resume.
**Fix:** Either make it factual and specific, or cut it. Specific looks like: "Senior product designer, 6 years in B2B SaaS. Shipped 4 v1 surfaces and led the design-system migration at [company]. Targeting design lead roles at Series B-D companies." If you can't write a specific one, drop it — the experience section will do the work.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R07 — Standalone projects section instead of integrating into experience (single-source) {#R07}
**Pattern:** Junior or pivot-track user lists personal projects in a separate "Projects" section below experience, treating freelance/coursework/personal as a different kind of work. Each project gets one bullet.
**Cost:** The separation signals that the user themselves doesn't think the projects count as real work. A reviewer reads the first signal: "she's discounting this." If projects are real work — built, shipped to anyone, taught the user something — they belong in the experience section, dated and bulleted like any other role.
**Fix:** Roll personal/freelance/coursework projects into the experience section, chronologically, with the same bullet format as employed roles. Treat each as a real role you led — even if the role was solo founder of "yourself, design office of one." The maturity in the framing matters more than the contract status.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R08 — Education or extracurriculars before experience (single-source) {#R08}
**Pattern:** Resume opens with education at the top, then certifications, then experience. Or includes "Student club: Designer (2 years)" as an extracurricular section.
**Cost:** "Student" and "club" code as junior to a recruiter scanning. Education-first works for a current student; for anyone past graduation, leading with education subtracts authority. The resume is supposed to argue for the user as a professional, not as a recent grad.
**Fix:** Experience first, always, except for currently-enrolled students with no internship. Roll meaningful student leadership into experience, not extracurriculars — "Designer, [Org]" rather than "extracurricular activity." Drop the years you attended college (US-region note: this prevents age inference, which is a real bias risk).
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R09 — Bullets rely on metrics that don't exist, or use suspiciously round percentages {#R09}
**Pattern:** Junior resume claims "Increased engagement by 45%" or "Improved usability by 80%" on student/concept work that was never instrumented or never shipped. Numbers feel made up.
**Cost:** Hiring managers identify fabricated metrics on sight. The user looks like they don't know the difference between real measurement and made-up numbers — which signals worse than no metric at all. It also poisons the trust on metrics that are real.
**Fix:** Three honest options: (1) use real instrumented numbers with sourcing — "38% → 22% drop-off, Mixpanel Q3 2024, n=14k"; (2) use ranges with hedge — "anecdotally 5-10 fewer support tickets per week"; (3) describe what you'd have measured and why you couldn't — "shipped to internal users only, no instrumentation; planned to track adoption and time-to-first-action." Maturity beats round percentages. See: `frameworks.md#prototyping-with-numbers` for the personal-project alternative.
**Source:** https://www.youtube.com/watch?v=Dfmfpi82qAk; https://www.youtube.com/watch?v=4tg1bPbOxus
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

### R10 — Resume submitted with portfolio URL that's broken, gated, or unreadable (single-source) {#R10}
**Pattern:** Resume's portfolio link goes to a 404, a password gate with no password provided, a bit.ly redirect, or a Behance grid when the role wants a standalone portfolio.
**Cost:** Unforgivable for portfolio-required roles. Reads as either careless (didn't test the link) or hiding something (the portfolio is bad). Recruiters bounce; the application is dead before any human reads the bullets.
**Fix:** Test the link before every application. Put it in the header, not the footer. Make the URL itself readable — "designs.timgailey.com" beats a shortened tracking link. If the portfolio is password-gated, paste the password right next to the URL on the resume.
**Source:** https://www.youtube.com/watch?v=11zGHBSfaXc
**Last affirmed:** 2026-04 (source: stream mining, 23 transcripts)

## Adding new flags (procedure for Tim+Nate)

When transcript mining surfaces a recurring pattern that isn't covered above, append it — don't rewrite. The skill ships with a stable v0; growth is additive (per CONTENT-05).

- **Confirm the pattern is recurring**, not a one-off. The mining-log.md (private, gitignored per D-17) tracks how many separate streams the pattern appeared in. Three independent appearances minimum before promotion to a flag; ≥4 streams earns the `(high-confidence)` suffix.
- **Pick the next ID in sequence** — P17, R11, etc. Never reuse a deleted ID; never renumber existing flags. Workflows reference IDs by anchor.
- **Match the structure exactly:** ID + name (+ `(high-confidence)` if appeared in ≥4 stream transcripts independently; + `(single-source)` if only one stream) + Pattern + Cost + Fix + Source (one or more YouTube URLs from the transcript) + Last affirmed (YYYY-MM, plus source tag — "stream mining, N transcripts" or "Tim/Nate manual add").
- **Test the fix line against voice.md §9** voice-content density (what / cost / frame / fix) before committing. If the fix doesn't pass, the flag isn't ready — back to mining.
- **Anti-roast 4-clause check** (voice.md §6): every flag must (1) name the choice not the person, (2) state the cost in concrete recruiter/hiring-manager terms, (3) provide the rewrite, (4) default to the kindest plausible reading. If a flag fails any of the four, rewrite or drop.

The mining-log.md links each appended flag back to the transcript timestamps that justified it. That log is private (D-17) so we can honor takedown requests without breaking the public skill.
