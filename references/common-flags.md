# Common flags — Portfolio Rx

## How this file is used

Workflows surface flags from this file when the corresponding pattern appears in user-submitted work. Each flag is small, self-contained, and produces a concrete rewrite. New flags are appended (never rewritten in place); each gets a unique ID and a `last-affirmed` timestamp.

A flag fires when the workflow can quote the user's actual work back to them and map it to one of the patterns below. If we can't quote it, we don't flag it — that's the difference between critique and roast.

## Conventions

- IDs: `P##` for portfolio flags, `R##` for resume flags. (Add `M##` later for mock-interview flags if/when needed.)
- Each flag has: ID, name, pattern (what triggers it), cost (what the user loses), fix (concrete rewrite or move), source.
- New flags are appended to the bottom of the relevant section. Existing IDs are stable — never reuse, never renumber.
- `last-affirmed` is a YYYY-MM date. When transcripts are mined (per D-17 Tier 1), the affirming reviewer (Tim or Nate) updates the date. If older than 6 months, surface a "this flag may be stale" note in the review.
- "High-confidence" flags appeared across every DOMAIN source independently. Treat them as load-bearing — if the user's work hits one of these, it goes in the Top 3 fixes.

## Portfolio flags

### P01 — All screenshots, no story (high-confidence) {#P01}
**Pattern:** Case study shows final UI with no problem context, constraints, or decisions. The user shipped pictures of work, not the work itself.
**Cost:** Hiring manager skims, sees pretty UI, can't tell what the designer actually did or whether they understood the problem. Bounces in 10 seconds.
**Fix:** Add a one-paragraph problem framing before every first image. If we can't write the problem in 100 words, we don't understand the problem yet — and the case study isn't ready.
**Source:** DOMAIN.md §5 P01; UX Playbook 11 Red Flags; NNg.
**Last affirmed:** 2026-04 (source: research)

### P02 — "We did this" everywhere (high-confidence) {#P02}
**Pattern:** Case study reads as if a five-person team made every decision together. No "I" anywhere. No role separation. Reviewer can't tell what the designer personally contributed.
**Cost:** Brian Lovin's rule — "it's easy for interviewers to spot undeserved credit." When everything is "we," the reviewer assumes the user is hiding something or didn't do much.
**Fix:** Use "I" for personal contributions, "we" for team decisions. Be specific: "I led the research; the PM wrote the brief; I designed the flows in Figma; the visual designer owned the final UI." One sentence on team composition near the top of every case study.
**Source:** DOMAIN.md §5 P02; Brian Lovin portfolio philosophy; Indeed Design hiring manager interviews.
**Last affirmed:** 2026-04 (source: research)

### P03 — Outcome is missing or vague (high-confidence) {#P03}
**Pattern:** Case study ends with "the redesign improved the experience" or "users loved it." No metric, no user feedback, no before/after, no honest "we couldn't measure this and here's why."
**Cost:** Hiring manager can't tell if the work shipped, worked, or moved a number. Without a result, the case study reads as a process diary.
**Fix:** Name any measurable signal — adoption rate, NPS movement, support tickets, task completion, even qualitative quotes from real users. If we have nothing, say why and what we'd measure next time. Honest "we shipped it but couldn't instrument it" beats fabricated metrics.
**Source:** DOMAIN.md §5 P03; UX Playbook; NNg 204-hiring-manager survey.
**Last affirmed:** 2026-04 (source: research)

### P04 — Bootcamp project visible without differentiation {#P04}
**Pattern:** The Airbnb redesign. The travel app. The recipe app. Hiring managers recognize shared bootcamp curriculum on sight; the case study doesn't show the user did anything self-directed with it.
**Cost:** Matthew Nesbitt's flag — bootcamp portfolios "raising doubts about individual depth." The reviewer assumes the user followed the script and learned what the script taught. No more.
**Fix:** Replace with real work, narrow the scope to a specific interesting problem the user picked themselves, or add domain expertise framing that makes the project distinctly theirs. "I redesigned this Airbnb flow because I noticed the host onboarding skipped X — coming from short-term rental ops, that gap was glaring." Now it's the user's project.
**Source:** DOMAIN.md §5 P04; Indeed Design — Matthew Nesbitt; Course Report 2024.
**Last affirmed:** 2026-04 (source: research)

### P05 — Process is the hero, not the problem (high-confidence) {#P05}
**Pattern:** Case study walks through every research activity in chronological order. Personas in section 2. Affinity diagrams in section 3. Wireframes in section 4. The actual decisions and outcomes are buried at the end.
**Cost:** UXFolio's data — 54% of hiring managers spend 5–10 minutes; 35% spend only 5. If the core logic chain (problem → decision → outcome) is buried under three scrolls of research artifacts, the case study has failed the structure test.
**Fix:** Reorder using inverted pyramid. Problem → decision → outcome first, in the first card. Then evidence. The research artifacts go below the fold or in a "process detail" section the reader can dig into if they want.
**Source:** DOMAIN.md §5 P05; UXFolio inverted pyramid; van Schneider anti-template.
**Last affirmed:** 2026-04 (source: research)

### P06 — No role clarity on team projects {#P06}
**Pattern:** Case study from a 4-person team reads as if one person did everything. Or the opposite — it's so vague about who did what that nothing is claimed.
**Cost:** Reviewer can't tell what the user is qualified to do solo. Asking "what was your role" in an interview should not be the first time the user answers it.
**Fix:** Call out team composition explicitly near the top: "This was a 3-person team (PM, eng lead, me). I owned the IA and interaction design; the visual design was a collaborative output with the brand designer." One paragraph, factual, near the start.
**Source:** DOMAIN.md §5 P06; Brian Lovin; Glassdoor Design portfolio review advice.
**Last affirmed:** 2026-04 (source: research)

### P07 — Fabricated or speculative metrics {#P07}
**Pattern:** Outcomes claimed with suspiciously round numbers — "45% improvement in engagement," "80% increase in usability" — on student or concept projects with no real data, no source, no n.
**Cost:** Seasoned hiring managers identify this immediately. The user looks like they don't know the difference between real measurement and made-up numbers — which is worse than no metric at all.
**Fix:** Either name real data with source ("38% → 22% drop-off, measured via Mixpanel, Q3 2024, n=14k"), use ranges honestly ("anecdotally 5–10 fewer support tickets per week"), or describe what we'd have measured and why we couldn't. Maturity beats made-up numbers.
**Source:** DOMAIN.md §5 P07; Course Report 2024 bootcamp portfolio analysis; UX Playbook.
**Last affirmed:** 2026-04 (source: research)

### P08 — Password-protected portfolio with no password provided {#P08}
**Pattern:** Portfolio link in resume goes to a password gate. No password in the resume. No password in the email. Hiring manager bounces.
**Cost:** Corey Chandler's rule — "password-protected portfolios cause immediate friction and lost ground." Recruiters won't chase passwords. The application is dead before anyone reads it.
**Fix:** Either remove the password gate for the apply-stage version, or paste the password prominently in the resume header right next to the URL. NDA work that has to stay protected gets a separate "available on request" line.
**Source:** DOMAIN.md §5 P08; Indeed Design — Corey Chandler.
**Last affirmed:** 2026-04 (source: research)

### P09 — Ten-plus case studies listed {#P09}
**Pattern:** Portfolio homepage shows 10+ projects. Or 7. Or 12. Quantity signals insecurity about quality.
**Cost:** Reviewer can't tell which projects to weight. Ends up on the weakest one first because there's no curation. The portfolio reads as "here's everything I've ever touched."
**Fix:** Curate to 3–5. The question is not "what did I do?" but "what best demonstrates what I want to be hired to do?" Cut everything that doesn't pull weight toward the target role. The cut projects can stay as 1-paragraph teasers if they're too good to drop entirely.
**Source:** DOMAIN.md §5 P09; van Schneider; UX Playbook senior guide.
**Last affirmed:** 2026-04 (source: research)

### P10 — Concept-only work, no shipped product {#P10}
**Pattern:** Portfolio has zero shipped, real-world products. Every project is a concept exercise, a redesign, a hypothetical app.
**Cost:** Corey Chandler's rule — "a smaller product that actually shipped" beats polished concept work every time. Reviewer can't tell if the user has ever survived a real release cycle.
**Fix:** Add at least one real shipped thing — client work, side project, open-source contribution, even a landing page that's actually live. If none exists, be honest about it and frame what we learned from the exercise. "I haven't shipped to real users yet" + a specific plan to is more honest than dressing concept work up as production work.
**Source:** DOMAIN.md §5 P10; Indeed Design hiring manager interviews; UX Playbook.
**Last affirmed:** 2026-04 (source: research)

### P11 — Homepage doesn't say what you do {#P11}
**Pattern:** Visitor lands on the portfolio. Five seconds in, they can't tell what role the user is targeting, what they specialize in, or what experience level they're at. The hero is "Hi, I'm [name]" and a vibe.
**Cost:** UX Playbook's 30-second test — "show portfolio to a non-designer for 10 seconds. Ask: what seniority level? What impact? What problems do they solve?" If the answers are vague, the portfolio fails. Recruiters don't infer.
**Fix:** One sentence above the fold. Who we are, what we do, what kind of work we're looking for. "Senior product designer specializing in B2B SaaS — I ship complex flows for non-technical users. Looking for design lead roles at Series B–D companies."
**Source:** DOMAIN.md §5 P11; UX Playbook 6 Rules; UXFolio.
**Last affirmed:** 2026-04 (source: research)

### P12 — Case study is a wall of text {#P12}
**Pattern:** Long paragraphs throughout, no visual breaks, no headers, no hierarchy. Reads like a report submitted for a grade.
**Cost:** Hiring managers skim first. If skimming finds no entry points — no headlines, no callouts, no diagrammed decisions — the case study doesn't get read. The work could be brilliant; nobody will know.
**Fix:** Break into scannable sections with descriptive headers ("The bet we made," "Why we cut the personalization spike," "What shipped vs. what we wanted"). Bullets and callouts where they earn their place. One image per major decision, captioned to stand alone.
**Source:** DOMAIN.md §5 P12; Designlab 14 Mistakes; UX Playbook senior guide.
**Last affirmed:** 2026-04 (source: research)

### P13 — Visual craft inconsistent with stated specialty {#P13}
**Pattern:** Applying for a UI/visual designer role but the portfolio itself has poor typography, inconsistent spacing, misaligned components, three competing display fonts. The portfolio is a portfolio of evidence against the claim.
**Cost:** If visual craft is the selling point, the portfolio is the test. Susan Le's rule — recruiters check for typos and alignment issues immediately. The portfolio fails the test before the case studies get read.
**Fix:** Audit the portfolio itself against the same standards we'd apply to a client project. Pick one display + one body face. Set a vertical rhythm and stick to it. Align everything to a grid. Treat the portfolio as the most important case study in the portfolio.
**Source:** DOMAIN.md §5 P13; Indeed Design — Susan Le; Glassdoor Design.
**Last affirmed:** 2026-04 (source: research)

### P14 — Missing "what I'd do differently" {#P14}
**Pattern:** Case study reads as an unexamined success story. Everything went great, the team aligned, the metrics moved, the launch was smooth. No reflection, no regret, no honest "here's what we missed."
**Cost:** Reviewers weight self-awareness heavily — especially at mid+ levels. A case study with no "what I'd change" reads as either dishonest or junior. Both kill the senior signal.
**Fix:** One paragraph at the end on what we'd change, what we'd have measured earlier, what the team missed. Make at least one regret a real one — "I let the eng team talk me out of the empty state polish; six months later it was the #2 support ticket source." The honesty IS the senior signal.
**Source:** DOMAIN.md §5 P14; ADPList senior framework; UX Playbook senior guide.
**Last affirmed:** 2026-04 (source: research)

### P15 — Dribbble/Behance as primary portfolio {#P15}
**Pattern:** Resume points to a Dribbble or Behance grid as the primary portfolio. No standalone site.
**Cost:** Brian Lovin's rule — "standalone portfolio site strongly preferred over Dribbble/Behance hosting — signals craft investment." A grid of shots signals a designer who chases likes; a standalone site signals one who builds.
**Fix:** Build a standalone site, even a simple one. Framer, Webflow, or a well-structured Notion page beats a Dribbble grid. Keep Dribbble/Behance as a secondary "selected shots" link if useful, but the primary URL on the resume points to the standalone site.
**Source:** DOMAIN.md §5 P15; Brian Lovin portfolio philosophy.
**Last affirmed:** 2026-04 (source: research)

## Resume flags

### R01 — Bullets describe activities, not outcomes (high-confidence) {#R01}
**Pattern:** "Designed wireframes for the checkout flow." "Created user personas." "Developed style guide." Resume reads as a job description copy-pasted from the listing, not an achievement record.
**Cost:** The bullet says nothing about impact. Reviewer can't tell if the wireframes shipped, if the flow worked, if anyone used the personas. Every "designed X" without a result line is dead weight.
**Fix:** Add the result. "Designed wireframes for the checkout flow" → "Redesigned checkout flow that reduced drop-off from 38% → 22% (Mixpanel, Q3 2024)." If no metric exists, use a soft signal: "Redesigned checkout flow; team adopted as the default pattern across the SaaS suite."
**Source:** DOMAIN.md §5 R01; Resume Worded; MentorCruise.
**Last affirmed:** 2026-04 (source: research)

### R02 — No metrics in any bullet {#R02}
**Pattern:** Resume has zero quantified bullets. Reads as a list of responsibilities. No numbers, no percentages, no scope, no timelines.
**Cost:** Recruiter skim test fails. The XYZ formula ("accomplished X as measured by Y, by doing Z") is the resume reviewer's default — without it, every bullet flattens to "they did design stuff."
**Fix:** Quantify at least one signal per role. Hard metrics where possible (drop-off, conversion, NPS). Soft signals where not (team size, project count, timeline, stakeholder count, scope of system). "Owned design across 3 product surfaces with 4 engineers and 1 PM" beats "responsible for product design."
**Source:** DOMAIN.md §5 R02; MentorCruise XYZ formula; Resume Worded.
**Last affirmed:** 2026-04 (source: research)

### R03 — Resume is longer than 2 pages for under 5 years experience {#R03}
**Pattern:** 0–5 years of experience. Resume is 2.5 or 3 pages. Often padded with side projects, every coursework piece, every freelance gig.
**Cost:** US convention — 1 page for 0–5 years, 2 pages max for 5+. Recruiters know the convention. A 3-page junior resume signals someone who can't edit their own work.
**Fix:** Cut projects section, consolidate early roles, trim to highest-signal bullets only. The portfolio carries project depth; the resume is the index. If we can't get to one page, the bullets aren't tight enough — not the page count.
**Source:** DOMAIN.md §5 R03; MentorCruise; Mentorix ATS-Proof Templates.
**Last affirmed:** 2026-04 (source: research)

### R04 — "Responsible for" language {#R04}
**Pattern:** Bullets that start with "Responsible for…" "Tasked with…" "Duties included…" Passive, low-agency framing.
**Cost:** Reads as a job description, not work the user owned. "Responsible for the design system" doesn't tell the reviewer if we built it, maintained it, broke it, or shipped one component.
**Fix:** Replace every "responsible for X" with a verb that shows ownership: Led, Designed, Shipped, Reduced, Grew, Defined, Built, Launched, Restructured, Prototyped, Validated, Partnered, Owned. "Responsible for the design system" → "Built and shipped the v1 design system across 3 product teams."
**Source:** DOMAIN.md §5 R04; Resume Worded action-verb canon.
**Last affirmed:** 2026-04 (source: research)

### R05 — Skills section is a noun salad {#R05}
**Pattern:** "Figma, Sketch, Adobe XD, Miro, Notion, Jira, Linear, Slack, Trello, FigJam, Maze, UserTesting, Hotjar, Mixpanel, Amplitude, Looker…" Twenty tools, no context, no depth signal.
**Cost:** Reads as insecurity. The user is hoping a recruiter ATS scan catches the right keyword. Recruiters who actually read it discount the whole section.
**Fix:** Trim to tools genuinely fluent in and relevant to target roles. Group by category: "Design: Figma, FigJam. Research: Maze, dscout. Analytics: Amplitude, Mixpanel." Five to eight items max, organized.
**Source:** DOMAIN.md §5 R05; MentorCruise; Mentorix.
**Last affirmed:** 2026-04 (source: research)

### R06 — No portfolio link, or link is broken {#R06}
**Pattern:** Resume submitted for a portfolio-dependent role. Portfolio URL is missing, mistyped, or returns a 404.
**Cost:** Unforgivable. The role explicitly asks for a portfolio. A missing or broken link reads as either careless (didn't test) or hiding something (the portfolio is bad).
**Fix:** Test the link before every application. Include the URL in the header, not buried in the footer. Make the URL itself readable — "designs.timgailey.com" beats "bit.ly/3xK9z2a." If the portfolio is password-gated, paste the password right next to the URL.
**Source:** DOMAIN.md §5 R06; Indeed Design hiring manager rules.
**Last affirmed:** 2026-04 (source: research)

### R07 — Photo, age, or address on US resume {#R07}
**Pattern:** Resume includes a headshot, date of birth, full home address, marital status, or nationality. International CV format applied to a US application.
**Cost:** Triggers unconscious-bias concerns at US employers — many will discard the resume rather than risk a discrimination claim. Also signals the user doesn't know US conventions, which is a problem for any role at a US company.
**Fix:** Remove all personal identifiers except: name, city (state optional), email, phone, LinkedIn URL, portfolio URL. Photo, DOB, address, nationality, marital status — all out. Keep city + country only if applying from abroad to set timezone expectations.
**Source:** DOMAIN.md §5 R07; AI ResumeGuru international format guide; Enhancv.
**Last affirmed:** 2026-04 (source: research)

### R08 — Resume is a designed PDF that is unreadable by ATS {#R08}
**Pattern:** Resume is a beautifully designed two-column PDF with icons, text in image boxes, fancy graphics. Visually striking, ATS-invisible.
**Cost:** For apply-via-portal submissions, the ATS strips the layout and feeds plain text to the parser. If text is in image boxes, the parser sees nothing. The resume gets auto-rejected before any human reads it.
**Fix:** Maintain two versions. The ATS version: single-column, left-aligned, ATS-safe fonts (Arial, Calibri, Georgia, Helvetica, Times New Roman), plain-text-compatible PDF, no tables/icons/text-boxes. The designed version: send directly to humans (recruiters, hiring managers, referrals). Same content, two formats.
**Source:** DOMAIN.md §5 R08; Mentorix ATS-Proof; Resume Worded.
**Last affirmed:** 2026-04 (source: research)

### R09 — Summary statement is generic {#R09}
**Pattern:** "Passionate UX designer with 3 years of experience creating user-centered digital experiences." Filler. Could be anyone.
**Cost:** The summary takes up the most expensive real estate on the resume — the top third — and says nothing the rest of the resume doesn't already say worse. It subtracts value.
**Fix:** Either make it specific or cut it entirely. Specific looks like: "Senior product designer, 6 years in B2B SaaS. Shipped 4 v1 surfaces and led the design-system migration at [company]. Looking for design lead roles at Series B–D companies." If we can't write a specific one, cut it; the experience section will do the work.
**Source:** DOMAIN.md §5 R09; Resume Worded; MentorCruise.
**Last affirmed:** 2026-04 (source: research)

### R10 — Job titles don't match target role (high-confidence) {#R10}
**Pattern:** Applying for "Senior Product Designer" with titles like "UX/UI Contractor," "Digital Experience Creator," "Product Specialist," "Design Lead [internal title]." Recruiter ATS keyword scan misses the match.
**Cost:** Recruiters and ATS systems pattern-match on title keywords. Non-standard or internal-only titles get filtered out at the first pass — even when the work was identical to the target role.
**Fix:** Where truthful, align job title language to industry standard terminology. "UX/UI Contractor" → "Contract Product Designer" (if the work was product design). "Digital Experience Creator" → "Senior UX Designer (internal title: Digital Experience Creator)" — keeps honesty, surfaces the keyword. Don't lie about title; do translate it.
**Source:** DOMAIN.md §5 R10; MentorCruise; Resume Worded; ATS-formatting research.
**Last affirmed:** 2026-04 (source: research)

## Adding new flags (procedure for Tim+Nate)

When transcript mining surfaces a recurring pattern that isn't covered above, append it — don't rewrite. The skill ships with a stable v0; growth is additive (per CONTENT-05).

- **Confirm the pattern is recurring**, not a one-off. The mining-log.md (private, gitignored per D-17) tracks how many separate streams the pattern appeared in. Three independent appearances minimum before promotion to a flag.
- **Pick the next ID in sequence** — P16, R11, etc. Never reuse a deleted ID; never renumber existing flags. Workflows reference IDs by anchor.
- **Match the structure exactly:** ID + name (+ "high-confidence" if it appeared in every DOMAIN-tier source independently) + Pattern + Cost + Fix + Source + Last affirmed (YYYY-MM, plus source tag — "research", "transcript: YYYY-MM-DD stream", or "Tim/Nate manual add").
- **Test the fix line against voice.md §9** voice-content density (what / cost / frame / fix) before committing. If the fix doesn't pass, the flag isn't ready — back to mining.

The mining-log.md links each appended flag back to the transcript timestamps that justified it. That log is private (D-17) so we can honor takedown requests without breaking the public skill.
