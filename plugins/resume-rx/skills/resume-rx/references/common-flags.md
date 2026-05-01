---
title: Common Flags — Resume Rx
plugin: resume-rx
covers: R01–R12 — the closed taxonomy of designer-resume failure modes that resume-rx flags by ID
sources:
  - audit/parts/common-flags.md (Phase 1 audit — mapping table from portfolio-rx R## to FEATURES §1.4 R-IDs)
  - portfolio-rx/plugins/portfolio-rx/skills/portfolio-rx/references/common-flags.md (raw material — re-homed per audit mapping)
  - research/FEATURES.md §1.4 (R01–R12 spine — AUTHORITATIVE numbering, locked by D-14)
  - research/PITFALLS.md (failure-mode prevention strategies)
  - research/STREAM_MINING_RESUME.md (Bucket 8 transcript anchors)
  - references/voice.md (voice rule citations by name)
  - references/frameworks.md (framework citations by name — STAR, CAR, XYZ, R-A-S, Scope-Impact-Metric, What/How/Why, Skim-test tiers)
---

# Common flags — Resume Rx

## R-ID stability is contract; never renumber post-ship

The twelve R-IDs in this file (R01–R12) are bound to FEATURES §1.4 per LD-P2-05 and D-14. Workflows reference flags by ID — a workflow file may instruct the reviewer to "cite R02 by ID," and that contract holds for the life of the plugin. R-IDs are append-only after v1 ship: never renumber, never reuse a deleted ID, never move content between R-IDs once a flag is published. If a future flag is needed, it lands as R13 at the bottom. If a flag becomes obsolete, it stays in place with a deprecation note rather than being deleted.

This file's R-IDs do **not** match portfolio-rx's R## numbering — portfolio-rx ships its own resume-flag set (R01–R10) under different concept-to-ID bindings, and the resume-rx audit (Phase 1) re-homed that content per FEATURES §1.4. Concepts that exist in both files may live under different R-IDs — for example, portfolio-rx R09 (suspicious-round-percentage metrics) is concept-equivalent to resume-rx R02, and portfolio-rx R03 (skills noun salad) is concept-equivalent to resume-rx R05. When in doubt, FEATURES §1.4 is authoritative.

A flag fires when the workflow can quote the user's actual resume back to them and map it to one of the patterns below. If we can't quote it, we don't flag it — that's the difference between critique and roast (voice.md §6 anti-roast hard rule).

---

## R01 — Activity bullet, no outcome

- **ID:** R01
- **Pattern:** Bullet leads with the activity verb. "Designed wireframes for the checkout flow." "Created user personas." "Led end-to-end design for AI questionnaire workflows." The resume reads as a list of what the user *did*, not what *resulted*.
- **Cost:** Activity bullets all flatten to "they did design stuff." No way for a recruiter scanning in 6 seconds to tell whether the wireframes shipped, the flow worked, or anyone used the personas. Reviewers comparing resumes default to the candidate with measurable wins.
- **Fix:** Flip to **What/How/Why** (apply via Why/How/What ordering at output). Lead with the impact, then the method, then the activity. "Improved efficiency 7x by leading end-to-end design for AI questionnaire workflows" beats the activity-first version. If a hard metric doesn't exist, fall back to a soft signal — adoption, scope, team size — per voice.md §9.1 escalation chain (hard / soft / prototyped / scope). Never fabricate a number to fill the slot (voice.md §11.2 No-fabricated-metrics rule).
- **Source:** audit appendix §"Existing R01" → FEATURES §1.4 R01 row (port-replace from portfolio-rx existing R01); STREAM_MINING_RESUME.md §C5 (4tg1bPbOxus L1413–1417) and §C6 (L1424–1425) verbatim Nate.
- **Last affirmed:** 2026-04-30

---

## R02 — Metric fabrication risk, no honest signal

- **ID:** R02
- **Pattern:** Bullet claims a clean round percentage on work that wasn't instrumented. "Increased engagement by 45%." "Improved usability by 80%." Or the inverse — the bullet hedges with a vague platitude ("users loved it," "improved the experience") with no measurable signal of any kind. Junior resumes especially over-index on suspiciously round percentages attached to student or concept work.
- **Cost:** Hiring managers identify fabricated metrics on sight. The user looks like they don't know the difference between real measurement and made-up numbers — which signals worse than no metric at all. Fabricated metrics also poison trust in the metrics on the page that *are* real.
- **Fix:** Three honest options per voice.md §9.1: (1) use real instrumented numbers with sourcing — "38% → 22% drop-off, Mixpanel Q3 2024, n=14k"; (2) use ranges with hedge — "anecdotally 5–10 fewer support tickets per week"; (3) describe what you'd have measured and why you couldn't — "shipped to internal users only, no instrumentation; planned to track adoption and time-to-first-action." Maturity beats round percentages. Apply **XYZ** when an honest hard metric exists; downgrade to **Scope-Impact-Metric** or **CAR** when it doesn't (frameworks.md). The No-fabricated-metrics rule (voice.md §11.2 / D-16-RR) is a hard rule, not a style preference.
- **Source:** audit appendix §"Existing R09" → FEATURES §1.4 R02 row (port-replace from portfolio-rx existing R09); PITFALLS §2.1 (hallucinated metrics); STREAM_MINING_RESUME.md §C1 (4tg1bPbOxus L398–399), §C2 (L437–438), §C10 (L1019–1020).
- **Last affirmed:** 2026-04-30

---

## R03 — Length / format mismatch

- **ID:** R03
- **Pattern:** Mid-or-senior user has cut their resume to one page even though they have 6+ roles to describe — bullets are tight to the point of being uninformative, scope language stripped to fit. Or the inverse: a junior user pads to two or three pages with thin bullets and irrelevant filler. Page count treated as a religion in either direction rather than calibrated to the work.
- **Cost:** The one-page rule originated when resumes were printed and stapled. In a digital-submit-via-portal era, the constraint is irrelevant. A senior who cuts to one page loses the chance to describe scope, ownership, and decision-making — the things that actually win the role. A junior who pads to three pages signals weak prioritization. Either way the page count is doing work the bullets should be doing.
- **Fix:** Two pages is fine for 5+ years of experience. Use the second page only if it's at least mostly full — empty space at the bottom of page two looks worse than ending page one cleanly. Senior resumes especially benefit from the extra room. STREAM_MINING_RESUME.md §H1 (Nate verbatim, 4tg1bPbOxus L1324–1329): *"I'm a firm believer in a two-page resume. As long as both pages are completely filled, the key is no empty space."* For US format, ATS doesn't count pages (§H3) — the constraint is human skim-time, addressed via descending-importance ordering and the **Skim-test tiers** framework (frameworks.md).
- **Source:** audit appendix §"Existing R04" → FEATURES §1.4 R03 row (port-replace from portfolio-rx existing R04); STREAM_MINING_RESUME.md §H1–H3 (4tg1bPbOxus L1324–1338).
- **Last affirmed:** 2026-04-30

---

## R04 — Passive / weak verb

- **ID:** R04 *(net-new — no portfolio-rx analog)*
- **Pattern:** Bullet opens with "Responsible for," "Tasked with," "Helped with," "Worked on," "Assisted in," or any phrase that could appear verbatim in a job posting. The bullet describes a job description, not an accomplishment. Often paired with R01 (activity, no outcome) — the weak verb is what makes the activity itself sound passive. Also surfaces as the inverse failure mode: the user reaches for an AI-default verb (*spearheaded*, *leveraged*, *synergized*, *catalyzed*, *orchestrated*, *championed*) to compensate, which lands as the giveaway pattern PITFALLS §2.2 calls out.
- **Cost:** "Responsible for designing the checkout flow" names a task without naming agency or result. A recruiter reads it as "this candidate doesn't know what they actually contributed." The AI-default-verb compensation is worse — it reads as LLM-generated polish, signals abstraction-regression, and triggers the pattern hiring managers at design-forward companies have been vocal about recognizing instantly since 2024 (PITFALLS §2.2).
- **Fix:** Replace the filler opener with a specific action verb anchored in the actual work, then apply **CAR** (Context / Action / Result) or **What/How/Why** to surface the result. The action verb has to be specific enough that swapping it onto another resume would change the meaning. Per voice.md §11.1 (Banned AI-default verb list), never substitute *spearheaded / leveraged / synergized / catalyzed* — those are roundtrip-fakes for the original weak verb. The abstraction-regression guard from voice.md §4 applies: rewrites are at least as concrete as the original. If the user wrote "Responsible for designing the checkout flow," the rewrite cannot say "Spearheaded checkout transformation" — the rewrite lost. Honest specific verbs: *redesigned, shipped, validated, owned, restructured, cut, built, instrumented*.
- **Source:** FEATURES §1.4 R04 row (net-new for resume-rx); PITFALLS §1.1 (filler verbs) and §2.2 (generic-output convergence); voice.md §4 drop list and §11.1 banned AI-default verb list. <!-- GAP: No single STREAM_MINING_RESUME.md transcript ID anchors a verbatim Tim/Nate flag of "Responsible for" specifically — the corpus addresses this pattern indirectly via the activity-first failure mode (§C5, §H21). v1.1+ deep-pass should mine for verbatim filler-verb call-outs. -->
- **Last affirmed:** 2026-04-30

---

## R05 — Tool-list noun salad in skills section

- **ID:** R05
- **Pattern:** Skills section reads "Figma, Sketch, Adobe XD, Miro, Notion, Jira, Linear, Slack, Trello, FigJam, Maze, UserTesting, Hotjar, Mixpanel, Amplitude, Looker..." formatted as a vertical bullet list, a multi-column block, or a styled grid. Often includes legacy tools (InVision, Zeplin, Abstract) alongside current ones with no recency signal. Tools appear in skills only, never in bullets where they'd carry context.
- **Cost:** Reads as keyword-stuffing for ATS — and modern ATS uses semantic analysis, so repetitive keyword density is now recognized as a spam signal (PITFALLS §4.2). Recruiters who actually read the section discount it. The bullet/column formatting also breaks ATS parsing — the parser may see broken words like "F igma" with literal spaces. Tools-in-list signal less than tools-in-context inside bullets.
- **Fix:** Trim to tools you're genuinely fluent in and used in the last two years. Group by category as a paragraph: "Design: Figma, FigJam. Research: Maze, dscout. Analytics: Amplitude, Mixpanel." Five to eight items max, organized. Skills section goes below experience and education, not above (STREAM_MINING_RESUME.md §H4–H5: Nate verbatim *"I de-emphasize skill sections… you can put that at the bottom so it's a little bit less intrusive"*). Move primary tools into bullets where they're doing semantic work — that's the No-keyword-stuffing rule (voice.md §9.3 / §11.7) operationalized.
- **Source:** audit appendix §"Existing R03" → FEATURES §1.4 R05 row (port-replace from portfolio-rx existing R03); PITFALLS §1.4 (over-tooling) and §4.2 (keyword-stuffing); STREAM_MINING_RESUME.md §H4 (4tg1bPbOxus L1339–1340), §H5 (L1342–1345).
- **Last affirmed:** 2026-04-30

---

## R06 — Missing or broken portfolio link

- **ID:** R06
- **Pattern:** Resume's portfolio URL goes to a 404, a password gate with no password provided, a bit.ly redirect that obscures the destination, a Behance grid when the role wants a standalone portfolio, or — most often — the link is missing entirely or buried in a footer where the ATS can't parse it. URL pasted as text-in-image is invisible to most ATS parsers.
- **Cost:** Unforgivable for portfolio-required roles. Reads as either careless (didn't test the link) or hiding something (the portfolio is bad). Recruiters bounce; the application is dead before any human reads the bullets. The portfolio is the proof — without the link, the resume is an argument without evidence (FEATURES §1.5).
- **Fix:** Test the link before every application. Put it in the header, not the footer (ATS-readable region). Make the URL itself readable — "designs.timgailey.com" beats a shortened tracking link. If the portfolio is password-gated, paste the password right next to the URL on the resume. Per D-25 (resume-rx SPEC), v1 is detect-and-warn only — no live WebFetch validation; the line-edit workflow flags suspicious-shape URLs (bit.ly redirects, missing https://, text-in-image positioning) without claiming the link does or doesn't resolve.
- **Source:** audit appendix §"Existing R10" → FEATURES §1.4 R06 row (port-replace from portfolio-rx existing R10); FEATURES §1.5 (portfolio link check); STREAM_MINING_RESUME.md transcript 11zGHBSfaXc.
- **Last affirmed:** 2026-04-30

---

## R07 — US-format violations

- **ID:** R07 *(net-new — no portfolio-rx analog)*
- **Pattern:** Resume targeting US roles includes a photo / headshot, date of birth, marital status, nationality, full home address, or a "References available upon request" line. Often surfaces on resumes from candidates trained in CV conventions from non-US markets (UK, EU, LATAM, India), where these elements are standard or expected. Sometimes paired with a multi-column "Personal Information" sidebar that compounds R02-format issues.
- **Cost:** US hiring norms treat photo/DOB/marital-status as bias-risk signals — a recruiter at a compliance-aware company may discard the resume rather than process protected-class information. "References available upon request" is filler from a 1990s-era convention; modern recruiters who want references will ask. Either way the user spends their most expensive real estate (top-of-page, header zone) on signals that actively hurt them in the US market — and the photo-and-personal-info layout often forces a multi-column structure that breaks ATS parsing on top of the content cost.
- **Fix:** For US-targeted resumes, drop photo, DOB, marital status, nationality, full street address (city/state is sufficient), and "References available upon request." Personal info compresses to: name, phone (with `tel:` link per STREAM_MINING_RESUME.md §H13), email, city/state, portfolio URL, LinkedIn. Per voice.md §6.1 (naming the limit of expertise), call out the regional asterisk explicitly when flagging — *"For non-US markets our knowledge is limited; this advice applies to US ATS and US recruiter conventions"* — STREAM_MINING_RESUME.md Deferred §International ATS variance. Frame the cut warmly: this isn't about whether the convention is "wrong," it's about which market reads it as standard.
- **Source:** FEATURES §1.4 R07 row (net-new for resume-rx); FEATURES §1.8 (ATS constraint awareness — non-standard headings, header-footer parsing failures); PITFALLS §4.1 (ATS misinformation — selective coaching), §4.3 (false ATS/human split). <!-- GAP: STREAM_MINING_RESUME.md does not contain a verbatim Tim/Nate flag of US-format violations specifically — the corpus mostly reviews US-trained candidates. The non-US ATS landscape disclaimer (Deferred §International ATS variance) is the closest anchor; v1.1+ corpus mining should look for international-candidate review sessions. -->
- **Last affirmed:** 2026-04-30

---

## R08 — "We" overuse, hiding individual contribution

- **ID:** R08
- **Pattern:** Bullets default to "we" or to passive phrasing that obscures who specifically did the work. "We redesigned the onboarding flow." "The team launched the new dashboard." "Drove cross-functional alignment to ship the v2 release." The user's specific contribution is invisible — by the time a recruiter finishes the bullet, they can't tell what this candidate owned versus what the team owned. Often paired with case-study-marketing register that sells the company instead of the candidate.
- **Cost:** A reviewer reads the resume to hire this candidate, not their former team. Without "I" claims that name precise ownership, the reviewer can't tell what the candidate contributed or whether they're worth interviewing. Recurring stream phrasing: *"I came here to buy you, not the company."* The "we" overuse also collides with R12 (claiming team win solo) — the two flags are mirror failures, and the diagnostic is the same: ownership precision is missing.
- **Fix:** Reframe each bullet through specific contribution. "I led the research." "I made the call to cut the personalization spike." "My recommendation was X; the team pushed back; we shipped Y." Use "we" only where it's literally accurate — multi-author work where the user's specific piece is named separately. Per the ownership-audit probe (STREAM_MINING_RESUME.md P-RES-03 / Theme B): if a bullet says *"led [project]"* or *"we [verb]ed,"* the workflow asks "what did you specifically own here?" and surfaces the answer in the rewrite. Apply **CAR** or **R-A-S** to the rewrite (frameworks.md). Voice.md §6.1 cost-framing applies — never frame the flag as the candidate "lying"; frame it as ownership precision missing.
- **Source:** audit appendix §"P04" mapping → FEATURES §1.4 R08 row (concept from portfolio-rx P04 case-study version, reframed for resume bullets); STREAM_MINING_RESUME.md §B1 (4tg1bPbOxus L762–765) verbatim Nate, §B2 (L236–237), §B9 (11zGHBSfaXc L1019–1022).
- **Last affirmed:** 2026-04-30

---

## R09 — Generic summary, wasted top-third

- **ID:** R09
- **Pattern:** Top of resume reads "Passionate UX designer with X years of experience creating user-centered digital experiences." Or "Detail-oriented product designer with a passion for crafting intuitive solutions." The summary could apply to any designer — the copy-paste test (Nate verbatim, STREAM_MINING_RESUME.md §B5) returns "yes, this would work on a different designer's resume without changing a word."
- **Cost:** The summary takes the most expensive real estate on the resume — the top third — and adds nothing the rest of the resume doesn't already say worse. AI-summarizing tools (which many recruiters use for high-volume triage) lock onto this generic line as the user's identity, "prompt-poisoning" the rest of the resume. STREAM_MINING_RESUME.md §H6 (Nate verbatim, 4tg1bPbOxus L1356–1360): *"if we can take your summary, copy, and paste it on somebody else's resume, no longer useful information, and is now just a waste of time."*
- **Fix:** Either make it factual and specific, or cut it. Specific looks like: "Senior product designer, 6 years in B2B SaaS. Shipped 4 v1 surfaces and led the design-system migration at [company]. Targeting design lead roles at Series B–D companies." If the user can't write a specific summary, drop it — the experience section will do the work (STREAM_MINING_RESUME.md §H7, 4tg1bPbOxus L1368–1370). Apply the **summary objectivity test** (P-RES-08 from STREAM_MINING_RESUME.md): could a different designer copy-paste this onto their resume? If yes, rewrite or cut. The fix is a binary — either pivot to objective-and-specific or remove entirely. Don't try to "make it stronger" while keeping the subjective register.
- **Source:** audit appendix §"Existing R06" → FEATURES §1.4 R09 row (port-replace from portfolio-rx existing R06); STREAM_MINING_RESUME.md §B5, §B9 (11zGHBSfaXc L1019–1022), §H6 (4tg1bPbOxus L1356–1360), §H7 (L1368–1370).
- **Last affirmed:** 2026-04-30

---

## R10 — Seniority mismatch, bullet voice wrong for level

- **ID:** R10 *(net-new for resume context — concept from portfolio-rx P14 case-study version, but bullet-voice-vs-level on a resume is materially different)*
- **Pattern:** Two failure shapes, opposite directions. **Junior over-claiming:** 0–3 year designer writes bullets in staff-level register — "defined the design strategy," "owned the 0-to-1 product vision," "drove org-wide alignment" — setting up an interview probe the candidate can't survive. **Senior under-claiming:** Senior or staff designer writes IC-focused bullets — "designed the component library," "conducted 12 user interviews" — that hide leadership scope and read as mid-level execution. Same root failure: the bullet voice is calibrated to the wrong rung.
- **Cost:** Junior over-claiming gets probed hard in interviews. *"You said you 'led' this — walk me through what that meant"* exposes the gap between claimed and actual scope, and the interview ends. Senior under-claiming positions the candidate at mid regardless of years — the recruiter scans IC verbs and assumes IC-level work, then discards the resume from the senior pile. Both failures are positioning-misses, not maturity-misses (voice.md Pair 7). The cost is invisible until interview time for junior, and at first-pass triage for senior.
- **Fix:** Apply the **senior-bullet diagnostic** from voice.md §11.3 — *what changed because of you?* For junior over-claim: re-anchor verbs to the actual contribution scale. *"defined the strategy"* → *"facilitated alignment between X and Y on the strategy" / "co-led the strategy work for the [specific surface]"* (PITFALLS §1.5). For senior under-claim: surface the missing leadership scope — mentorship, hiring contribution, cross-org influence, standards-setting — even briefly (PITFALLS §1.6). Apply **R-A-S** or **Scope-Impact-Metric** at senior tier; apply **What/How/Why** or **CAR** at junior tier (frameworks.md). Frame as calibration, not accusation: *"This reads as full ownership — is that right? If it was collaborative, 'co-led' or 'led the [specific piece] of…' is more accurate and just as strong"* (PITFALLS §1.3 verbatim).
- **Source:** FEATURES §1.4 R10 row (net-new for resume context); PITFALLS §1.3 (claimed-vs-attributed scope), §1.5 (junior over-claiming), §1.6 (senior under-claiming); STREAM_MINING_RESUME.md §B3 (11zGHBSfaXc L418–420), §B4 (P14 cross-ref), §C5, §D1–D6, §D11 (ox8cqMpZbEg L331–332).
- **Last affirmed:** 2026-04-30

---

## R11 — Design process over-narration

- **ID:** R11 *(net-new — no portfolio-rx analog)*
- **Pattern:** Bullets list every research method, every artifact, every step of the design process — *"Conducted user interviews, ran usability testing, created journey maps, synthesized affinity diagrams, facilitated workshops, built personas, drafted wireframes…"* — without ever stating what the methods produced. The bullet is a method inventory, not an accomplishment statement. Most common on UX-researcher and UX-generalist resumes where designers have been trained to list deliverables, and on case-study-derived bullets where the candidate carried portfolio-grade method-listing into the resume context.
- **Cost:** Reviewers skim for outcomes; method inventories don't carry outcomes. The recruiter reads "ran 12 usability tests, synthesized affinity diagrams, built journey maps" and learns nothing about what changed in the product or the team afterward. Worse, listing methods without outputs reads as activity-bullet failure mode (R01 root) compounded — the bullet is doing R01's work three times in a row. Senior reviewers explicitly flag this as a tell that the candidate thinks at method level, not decision level (PITFALLS §1.6 senior under-claiming overlap).
- **Fix:** Compress the method list to the *single output* it produced — *"Identified the 3 highest-friction onboarding steps via 12 moderated usability tests; the team cut step 2 and reordered 4→6, dropping abandonment from 38% to 22%."* The methods become the **How** clause inside **What/How/Why**, not the headline. PITFALLS §1.7 (misaligned voice for the role-family) applies: a UX-researcher bullet legitimately surfaces method names where they're load-bearing (n=, sample composition, methods used), but even then the bullet leads with the *finding* or *decision driven*, not the method roster. The role-family preset for UX Researcher (FEATURES §2.1) defines the verb shape — *Identified, Validated, Influenced, Surfaced, Synthesized* — and explicitly anchors impact on "research drove a decision or prevented a mistake," not on method count.
- **Source:** FEATURES §1.4 R11 row (net-new for resume-rx — explicitly called out by audit task brief); PITFALLS §1.6 (senior under-claiming, craft-dominant bullets) and §1.7 (role-family voice mismatch); FEATURES §2.1 (UX Researcher role-family preset). <!-- GAP: STREAM_MINING_RESUME.md does not have a single transcript ID that anchors process-over-narration as a named flag — the corpus discusses case-study process narration heavily (portfolio-rx P03/P14 territory) but the resume-bullet method-listing inverse failure is implied, not explicit. The cleanest anchor is the contrast between §C5 (activity-first fail) and the role-family verb sets in FEATURES §2.1; v1.1+ deep-pass should mine for verbatim Nate/Tim flags of method-listing on UXR-track resumes. -->
- **Last affirmed:** 2026-04-30

---

## R12 — Claiming team win solo

- **ID:** R12 *(net-new — no portfolio-rx analog)*
- **Pattern:** Bullet uses singular ownership verbs — *led, owned, drove, created, built, redesigned, shipped* — for work that was clearly multi-disciplinary or multi-author. "Led the redesign of the mobile app" when the actual contribution was two screens on a twelve-person team. "Owned the design system" when the role was contributing components to a system someone else architected. "Built the v1 product" when the work was 4 features inside a 40-feature launch with 8 designers and 30 engineers. The mirror-image failure of R08 — instead of "we" hiding the candidate's contribution, "I" inflates the candidate's contribution.
- **Cost:** Scope inflation gets probed hard in interviews — and recruiters who've seen many designer resumes pattern-match the inflation on first read. *"Led the redesign of the mobile app"* on a 0–3 year resume reads as either over-claim or poorly written; either way the bullet is doing damage. Worse, when the inflation gets probed and falls apart, the rest of the resume's bullets become suspect — the recruiter starts re-reading every claim wondering what else is inflated. PITFALLS §1.3 (claimed-vs-attributed scope) catalogs this as the failure mode that "gets probed hard in interviews."
- **Fix:** Surface the precision the bullet is hiding. STREAM_MINING_RESUME.md §B1 verbatim Nate (4tg1bPbOxus L762–765): *"You're not gonna claim sole ownership of [a project that wasn't yours alone]. You're not gonna make a point to talk too much about [the team]."* The fix is named-precision: *"Led the redesign of the mobile app"* → *"Co-led the redesign of the [Auth and Billing] flows on the mobile app — 2 of 8 designers; the broader app redesign shipped collaboratively across the design org."* Or shorter: *"Led the [Auth flow] redesign within the broader mobile-app v3 release."* The candidate keeps the credit they earned — the redesign of the specific surface they actually owned — without claiming credit they didn't. Voice.md Pair 7 frame applies: this is calibration, not accusation. Apply the **ownership audit** probe (P-RES-03 from STREAM_MINING_RESUME.md): *"What did you specifically own here? Where in this bullet does the contribution become precisely yours, vs the team's?"*
- **Source:** FEATURES §1.4 R12 row (net-new for resume-rx — explicitly called out by audit task brief); PITFALLS §1.3 (claimed-vs-attributed scope); STREAM_MINING_RESUME.md §B1 (4tg1bPbOxus L762–765) verbatim Nate, §B2 (L236–237).
- **Last affirmed:** 2026-04-30

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
