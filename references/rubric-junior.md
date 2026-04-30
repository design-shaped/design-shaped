# Rubric — Junior / Early-Career

> No roasting: just collaboration and constructive feedback.
> Voice register: `references/voice.md`. Every flag in this file complies with `voice.md` §3 (pattern templates), §4 (drop list), §6 (anti-roast hard rule).

## When to use this rubric

Apply this rubric when the designer is junior, early-career, or not yet on a promotion track: bootcamp grads, career switchers, 0-2 yrs of design experience, self-taught, HCI Masters grads, students. Job-search contexts: building a first portfolio, actively applying, post-interview-flop, re-entering after a gap.

This rubric is **prescriptive** (per SPEC D-14). Junior portfolios fail in repeating ways, and we push hard on the common failures here. We tell users what to fix.

For mid → senior promotion-track designers, use `references/rubric-senior.md` instead. That rubric is diagnostic — it extracts the user's thesis and grades against it. Don't apply both. Pick one based on the career-stage routing in SKILL.md.

---

## 1. The hiring-manager skim test

The primary diagnostic. Adapted verbatim from Indeed Design + UX Playbook (DOMAIN §2). Most junior portfolios fail at the 0-3s tier, which means everything else is moot.

Walk the portfolio in three timed passes. At each tier, name what gets seen, what should be visible, what fails.

### Tier 1 — 0-3 seconds

**What gets seen:** the homepage above the fold. The first visual. The page-load speed.

**What should be visible:**
- Loads in under 2 seconds
- A positioning statement: who they are, what role they want, what kind of work they ship
- A hero visual that signals business context — a real product surface, not abstract decoration
- No password gate

**What fails this tier:**
- `Element: password-protected portfolio with no password in the email or resume. Cost: hiring manager bounces — they don't chase passwords. Fix: drop the gate for apply-stage portfolios, or paste the password in the resume header and the application email.`
- `Element: the hero. Cost: a generic abstract gradient + "Hi, I'm [name], a passionate designer" reads as bootcamp default — the page is competing with 200 other passionate designers. Fix: replace the hero with one screen of real product work + one sentence of positioning ("I ship onboarding flows for B2B SaaS" beats "I'm passionate about user-centered design").`
- `Element: page-load. Cost: 6-second Webflow load + autoplay video kills the skim before it starts. Fix: compress hero assets, kill autoplay, target sub-2-second first paint.`

If the portfolio fails Tier 1, that's the Top-3 fix. Nothing else matters until the homepage holds attention for 3 seconds.

### Tier 2 — 3-10 seconds

**What gets seen:** the case study list. Project titles. One-line descriptions. The first thumbnail of each project.

**What should be visible:**
- 3-5 case studies (not 10+, not 1)
- Each case study has a one-line outcome or domain visible on the index — "Cut drop-off 38% → 22%" or "B2B onboarding for [N]M-MAU SaaS"
- Project thumbnails show real product surfaces, not decorative covers
- The collection has a through-line — a posture the reader can name

**What fails this tier:**
- `Element: project count. Cost: 10+ case studies signals insecurity about quality — hiring managers assume the strongest two are buried. Fix: cut to 3-5. Curate to "what I want to be hired to do," not "what I've done."` (See: `references/common-flags.md#FLAG-P09`)
- `Element: project count. Cost: 1 case study reads as "I'm not ready yet." Fix: write up coursework, freelance, or unshipped work as additional case studies — three case studies beats one polished one for first-job applications.` (See: `voice.md` Pair 6, `common-flags.md#FLAG-P10`)
- `Element: thumbnails. Cost: four moodboard-style decorative covers don't tell the reader what the projects are about — they look like a Squarespace template. Fix: use a real product screen as the thumbnail. The cover should be a screen of the work, not a poster about the work.`
- `Element: the through-line. Cost: SaaS dashboard + e-comm checkout + fitness app + B2B onboarding reads as "I'll take any role." Fix: pick a posture and put it in the hero — see voice.md Pair 4.`

### Tier 3 — 10-30 seconds (advanced to "maybe" pile)

**What gets seen:** the user clicks into one case study. They scroll. They look for: role clarity, problem framing, outcome.

**What should be visible:**
- A problem framing in the first paragraph (not paragraph 6)
- Role clarity — "I" for individual contributions, "we" for team decisions, named team composition for any group project
- A measurable outcome or an honest qualitative one (see §5)
- Process visible but not the hero — process is supporting evidence, not the story
- Reflection — one paragraph on what they'd do differently

**What fails this tier:**
- `Element: the [project name] case study. Cost: outcome lives in paragraph 6. Hiring manager skims, sees process, leaves before the result. Fix: move the outcome to the first paragraph. See voice.md Pair 3.`
- `Element: pronoun usage in the [project name] case study. Cost: "we" everywhere — can't tell what the designer personally contributed. Fix: rewrite using "I" for solo work, "we" for team decisions, with explicit role calls: "This was a 3-person team. I owned IA + interaction; PM owned the brief; visual design was collaborative."` (See: `common-flags.md#FLAG-P02`, `#FLAG-P06`)
- `Element: the reflection section. Cost: case study reads as unexamined success. Recruiters weight self-awareness heavily — its absence reads as "doesn't yet think critically about own work." Fix: one paragraph, "what I'd do differently." Make one regret a real one.` (See: `common-flags.md#FLAG-P14`)

### How to score the skim test

If the portfolio fails Tier 1 → that's the entire Top-3. Fix the homepage. Nothing downstream matters yet.

If the portfolio passes Tier 1 but fails Tier 2 → focus the Top-3 on the case study list and curation.

If the portfolio passes Tier 1 + 2 but fails Tier 3 → focus the Top-3 on case study structure (§2) and outcome specificity (§5).

---

## 2. Case study structure check

Junior case studies should fit one of the named frameworks in `references/frameworks.md`. The rubric checks three things, in order:

1. **Does each case study name a framework?** Not in the prose — in the implicit shape. P→P→O, STAR, or Inverted Pyramid (per `frameworks.md`). If the case study doesn't fit any named framework, the structure is improvised and almost always burying the outcome.

2. **Does it complete the framework's beats?** STAR without the Result is the most common failure. P→P→O with the Outcome reduced to "the redesign improved the experience" is the second.

3. **Does it end with an outcome, not a process diary?** Per `voice.md` Pair 10. A case study that ends with "next steps include further user testing" is a process diary. Reject and rewrite.

### Flags

- `Element: the [project name] case study. Cost: skips the Result in STAR. Reads as a process documentation dump. Fix: add three sentences — what shipped, what changed for users, what you'd do differently. Without those, this isn't a case study, it's a project journal. See: references/frameworks.md#star.`
- `Element: the [project name] case study. Cost: opens with 600 words of secondary research before the problem statement. Hiring manager skims, sees no Problem in P→P→O, leaves. Fix: cut the research preamble. Open with the Problem. Then Process. Then Outcome. See: references/frameworks.md#problem-process-outcome.`
- `Element: the [project name] case study. Cost: every section is the same visual weight — research, sketches, wireframes, final screens, all walls of text + image grids. Inverted Pyramid wants the most-important thing first. Fix: lead with the problem-solution-impact chain in the first 200 words, then expand into process for readers who want depth. See: references/frameworks.md#inverted-pyramid.`

### What to look for

- Each case study fits one of: P→P→O, STAR, Inverted Pyramid (named verbatim per voice.md §9)
- All four beats present in whichever framework is used
- The Outcome / Result is in the first scroll, not the last

### What flags to expect

- Process is the hero, not the problem (`common-flags.md#FLAG-P05`)
- Outcome is missing or vague (`#FLAG-P03`)
- Case study is a wall of text with no hierarchy (`#FLAG-P12`)

---

## 3. "Why this path" career narrative

Critical for career switchers and bootcamp grads. From DOMAIN §3.

The rubric checks: does the body of work + the resume tell **one coherent story** about who this designer is and where they're going? A portfolio is a thesis statement. The thesis can be early, but it has to exist.

Pick the trajectory archetype that fits the user, then apply the matching checks.

### Archetype A — Bootcamp / formal-program grad

Includes: HCI Masters, intensive bootcamps (DesignLab, GA, Springboard), university UX programs.

**What to look for (positive signals):**
- At least one project shaped like a real product, not a curriculum exercise
- Domain expertise from prior life applied to design work — a former nurse designing healthcare tools beats a generic Airbnb redesign every time
- Self-direction visible — a side project, an open-source contribution, a freelance gig the curriculum didn't assign
- Specificity — narrow problem, real users (even if N=5), real constraints

**What flags to expect:**
- `Element: the Airbnb / TripPlanner / RecipeApp redesign. Cost: hiring managers recognize bootcamp curriculum projects on sight — Matthew Nesbitt (Indeed Design) flags this explicitly. Fix: either replace with a real shipped thing (freelance, open-source, side project), narrow to a sub-problem nobody else in the cohort tackled, or add domain framing that makes it distinctly yours. See: common-flags.md#FLAG-P04.`
- `Element: fabricated metrics ("45% engagement lift"). Cost: round-number outcomes on student projects with no real data — hiring managers spot this and discount the whole portfolio. Fix: replace with what you'd have measured and why, or use honest qualitative outcomes ("5/5 testers completed the task without prompting; n=5"). Honesty signals more maturity than fake numbers. See: common-flags.md#FLAG-P07.`
- `Element: process-section bloat. Cost: bootcamp curricula reward documenting every double-diamond step, which produces case studies where research takes 40% of the scroll. Fix: cut research to the decisions it informed. If a research activity didn't change a design decision, it doesn't belong in the case study.`

### Archetype B — Career switcher

From dev, marketing, research, ops, education, healthcare, anything.

**What to look for (positive signals):**
- The "why design now" moment is concrete — a specific observation from prior work that made design thinking legible ("while building compliance workflows, I kept noticing users were confused at step 3 — and I was the only one curious about that")
- Prior career framed as transferable, not apologized for — a former PM has product judgment a bootcamp grad doesn't
- At least one design project that demonstrates commitment to the new field, not just curiosity

**What flags to expect:**
- `Element: the "About" page. Cost: opens with "After 8 years in marketing, I decided to follow my passion for design" — passive, no concrete moment, reads as bored-not-driven. Fix: name the moment. "Building 30-page email funnels at [Company], I kept rewriting the user flow on whiteboards — that's when I realized the design layer was where I was already working." Concrete beats abstract.`
- `Element: prior-career bullets on the resume. Cost: the bullets describe non-design responsibilities with no transferable framing — reads as two unrelated careers stapled together. Fix: rewrite each bullet to surface the transferable skill. "Managed 3-person research team" → "Led 3-person research team interviewing 50+ enterprise users — methods I now apply to UX research." See: voice.md Pair 2.`
- `Element: the design project count. Cost: only one design project after a multi-year career switch reads as tentative — has the user actually committed? Fix: ship a second project even if small. A redesigned freelance landing page or an open-source contribution beats a polished single project for demonstrating commitment.`

### Archetype C — Self-taught / independent

No formal program. Learned on the job, on the internet, on the weekends.

**What to look for (positive signals):**
- A "why design" thesis — not "I love creativity" but a specific lens (accessibility, dev tools, healthcare ops, a domain)
- Range visible — interaction design, visual craft, research, system thinking — without claiming senior-level depth in all of them
- Evidence of deliberate practice — case studies that show iteration, decisions, and learning, not just polished outputs

**What flags to expect:**
- `Element: the body of work. Cost: 4 case studies, no through-line, no thesis — reads as "I designed whatever came up." For self-taught designers this is the hardest archetype to position because the formal credential isn't doing any work. Fix: pick a posture and reorganize the portfolio around it. "I make B2B feel less hostile" or "I ship small tools, fast" — anything specific beats the unstated everything-shape. See: voice.md Pair 4.`
- `Element: visual craft inconsistency across projects. Cost: case studies look like they were made by 4 different people — typography, spacing, layout language all different. Self-taught is the archetype where craft floor matters most because there's no school to vouch for it. Fix: pick one type system and one layout grid. Apply across all case studies. See: §6 + common-flags.md#FLAG-P13.`
- `Element: the "About" framing. Cost: leads with "self-taught" as if it's an apology. Fix: lead with what the self-taught path uniquely built — domain expertise, range, ownership. Then mention self-taught in passing if at all.`

### Archetype D — 0-2 yrs experience

First or second job. Has shipped something. Looking to level up.

**What to look for (positive signals):**
- Growth visible between projects — the second project shows decisions the first didn't
- At least one case study features a constraint the designer pushed back on (engineering pushback, scope cut, deadline crunch) — signals collaboration maturity
- Self-aware reflection — "what I'd do differently" with a real regret, not humble-bragging

**What flags to expect:**
- `Element: project sequence. Cost: 3 case studies, all the same depth, no visible growth — reads as flat skill ceiling, not learning trajectory. Fix: order projects chronologically and let the most recent one show explicit growth — "Compared to the [earlier project], here I learned to pre-validate scope with engineering before sketching."`
- `Element: collaboration framing. Cost: case studies describe design as solo work — no mention of PM, eng, research partners. At 0-2 yrs the collaboration signal matters more than the craft signal. Fix: add a "team + my role" callout to each case study. Per Brian Lovin: "great designers understand software development is a team sport."`
- `Element: the reflection section. Cost: "what I'd do differently" reads as humble-bragging ("I'd have shipped sooner"). Fix: make one regret a real one — "I should have pushed back on the PM's success metric before sketching; we measured the wrong thing for the first month." See: voice.md Pair 11.`

---

## 4. Outcome / metric specificity

Per DOMAIN §5 R01-R02 + voice.md Pair 2.

Every bullet, every case study should land one of three outcomes:

1. **Measurable outcome** — a real number with a real source. "Cut checkout drop-off 38% → 22%, measured Mixpanel Q3 2024, n=12K sessions."
2. **Honest qualitative outcome** — a shipped artifact, a user signal, a real consequence. "Shipped Q3 2024 to ~50K MAU; support tickets on the affected flow dropped from ~30/wk to ~5/wk."
3. **Honest non-outcome** — for projects that didn't ship, didn't get measured, or are too early. "Killed by leadership pivot in October — what I learned: should have stress-tested executive alignment before sketching." Or: "Still in beta — current signals: 5/5 internal testers completed the task without prompting; public launch Q1 2026."

Reject vague verbs. The drop list (per `voice.md` §4):

- "improved the experience"
- "delighted users"
- "drove engagement"
- "elevated the product"
- "delivered impact"
- "moved the needle"
- "transformed the workflow"

These verbs commit to nothing. They're filler.

### Flags

- `Bullet says "Designed checkout flow that improved the experience." Diagnostic: improved how, for whom, measured how? Rewrite: "Redesigned checkout for [N]M-MAU SaaS — cut drop-off 38% → 22% in test cohort (Mixpanel, Q3 2024)."` (Per `voice.md` Pair 2.)
- `Bullet says "Drove engagement on the redesigned dashboard." Diagnostic: what's "engagement"? DAU? session length? task completion? what was the baseline? Rewrite: "Redesigned dashboard — DAU/MAU ratio moved from 0.18 to 0.27 over 6 weeks post-launch (n=12K, internal analytics)."`
- `Element: the [project name] case study. Cost: the outcome paragraph claims a "45% engagement lift" on a student project with no real users. This is FLAG-P07 and seasoned hiring managers spot it instantly. Fix: replace with what you'd have measured ("primary signal: task completion rate; secondary: time-on-task; n target: 30 over 2 weeks") + honest reflection on why the project didn't generate real data.`
- `Element: the [project name] case study. Cost: project shipped but no post-launch signal cited — reads as "we built it and walked away." Fix: even one qualitative signal helps — "shipped Q2 2024; the support team flagged a 60% drop in checkout-related tickets that quarter." Honest qualitative beats no signal.`

### What to look for

- Every resume bullet has either a number or a concrete shipped artifact
- Every case study ends with one of the three outcome shapes (measurable / qualitative / honest non-outcome)
- No vague verbs from the drop list

---

## 5. Visual craft floor

From `common-flags.md#FLAG-P15` + `voice.md` Pair 5.

At least one case study should NOT look like a tutorial output. The portfolio is itself a design artifact — for visual / UI / product designer roles, the portfolio's craft is part of the test.

### Flags

- `Element: the portfolio template. Cost: hero + 3-up grid + footer — exact Squarespace default layout. Reads as "I picked a template and dropped my work in." Fix: customize the layout. Even small choices — full-width hero replaced with split-column, custom case-study cover instead of stock thumbnail — signal investment.`
- `Element: typography. Cost: hero is set in three different display faces — DM Serif + Inter Display + a manually-tracked sans. Pick one display + one body and use them everywhere. The taste signal here matters more than the projects. See: voice.md Pair 5.`
- `Element: leftover Lorem Ipsum in the [project name] case study. Cost: signals the case study isn't actually finished — and if the portfolio isn't proofread, the work-product won't be either. Fix: kill all Lorem Ipsum. If a section isn't ready, cut the section.`
- `Element: type pairing on the index. Cost: defaults to the framework's stock pairing (Webflow's default Inter + Inter Tight, Framer's default Geist) — works fine but reads as "didn't bother." Fix: pick an intentional pair. Even a small move — Söhne + Söhne Mono, GT America + Tiempos — shows craft. See: common-flags.md#FLAG-P13.`
- `Element: alignment + spacing across the case study grid. Cost: thumbnail sizes inconsistent, padding varies, hero images cropped differently per project. Susan Le (Indeed Design) flags alignment issues immediately. Fix: define a grid + a card spec, apply uniformly. The grid is the test.`

### What to look for

- The portfolio doesn't read as "a Squarespace default" or "a Webflow template with the brand name swapped"
- No Lorem Ipsum, no placeholder copy
- Type pairing is intentional — one display, one body, used consistently
- At least one case study has custom layout treatment (not the framework's default case-study template)

---

## 6. Resume — junior R-flags

The 10 R-flags from DOMAIN §5. Each: how to detect, what the rewrite looks like.

### R01 — Bullets describe activities, not outcomes

**Detect:** bullet starts with "Designed wireframes for X" or "Worked on Y." No result.

**Flag:** `Bullet says "Designed wireframes for the checkout flow." Diagnostic: what was the result? Rewrite: "Designed checkout flow that cut drop-off 38% → 22% (Mixpanel, Q3 2024, n=12K sessions)." See: voice.md Pair 2.`

### R02 — No metrics anywhere

**Detect:** zero numbers in the entire resume. Reads as a job description, not an achievement record.

**Flag:** `Element: the resume. Cost: no metric in any bullet — reads as a JD. Recruiter scans for impact signals and bounces. Fix: quantify at least one signal per role. If no hard metrics, use soft ones — team size, project count, timeline, stakeholder count, scope ("Designed for ~30K MAU SaaS team", "Worked across 4 product lines + 8 engineers").`

### R03 — Resume runs longer than 2 pages

**Detect:** under 5 yrs experience + 2+ pages. Or 5+ yrs + 3+ pages.

**Flag:** `Element: page count. Cost: 3 pages with 2 yrs of experience — recruiter's first thought is "doesn't know what matters." Fix: cut to 1 page. Drop projects section, consolidate early roles to one line each, trim bullets to highest-signal only. The constraint is the test.`

### R04 — "Responsible for" language

**Detect:** any bullet starting with "Responsible for" or "Helped with" or "Assisted in."

**Flag:** `Bullet says "Responsible for redesigning the onboarding flow." Diagnostic: did you lead it or follow? Rewrite: "Led onboarding redesign across 3 product lines; reduced time-to-first-action from 12 min to 4 min." Replace every "responsible for" with: Led / Designed / Shipped / Reduced / Built / Defined / Owned.`

### R05 — Skills section is a noun salad

**Detect:** lists of 15-20 tools (Figma, Sketch, Adobe XD, Miro, Notion, Jira, Linear, Slack, ...) with no grouping or depth indicator.

**Flag:** `Element: the skills section. Cost: 18 tools listed — reads as "checked every box on a job description." Recruiters discount long lists. Fix: cut to 6-8 tools you'd be comfortable being interviewed on. Group by category — Design (Figma, Framer), Research (Maze, Dovetail), Collaboration (Linear, Notion).`

### R06 — Portfolio link missing or broken

**Detect:** no URL in the header, or the URL 404s, or it's a Dropbox folder.

**Flag:** `Element: the portfolio link. Cost: link goes to a Dropbox folder that requires a login. Recruiter doesn't request access — they move on. Fix: standalone URL in the header, tested before every application. Dropbox links signal "I haven't built a portfolio yet."`

### R07 — Photo, age, or address on US resume

**Detect:** profile photo, date of birth, full street address, marital status, nationality.

**Flag:** `Element: the resume header. Cost: profile photo + DOB + full address — triggers unconscious-bias avoidance, also flags the resume as international format applied to a US role. Fix: keep name, city + state, email, phone, LinkedIn, portfolio URL. Drop everything else. See: DOMAIN §7 for international → US conversion.`

### R08 — Resume PDF unreadable by ATS

**Detect:** text rendered as images, multi-column layout, icons replacing text labels.

**Flag:** `Element: the resume layout. Cost: two-column layout + icon labels for "Skills" and "Experience" — ATS strips icons and merges columns into garbage text. Resume gets parsed as nonsense, never reaches the recruiter. Fix: for apply-via-portal submissions, use single-column plain-text-compatible PDF. Save the designed version for direct send.`

### R09 — Generic summary statement

**Detect:** opening summary that could describe any designer. "Passionate UX designer with X years of experience creating user-centered digital experiences."

**Flag:** `Element: the summary. Cost: "passionate UX designer..." reads as filler — recruiter's eye skips it. Fix: either make it specific (name your specialty, your domain, your outcome posture: "Product designer focused on B2B onboarding — last role cut activation time 3x") or cut it entirely. Generic is worse than absent.`

### R10 — Job titles don't match target role

**Detect:** applying for "Senior Product Designer" but the resume titles say "UX/UI Contractor" or "Digital Experience Creator."

**Flag:** `Element: the job titles. Cost: "Digital Experience Creator" doesn't pattern-match for ATS keyword scans on "Product Designer" or "UX Designer" roles. Fix: where truthful, align titles to industry standard ("Product Designer" / "UX Designer" / "UI Designer"). If your formal title was non-standard, parenthetical-clarify: "Digital Experience Creator (Product Designer)."`

---

## 7. Producing the Top-3 fixes

End every review with a Top-3 fixes block. Per `voice.md` §11 self-check.

**Format — non-negotiable, from `voice.md` §3:**

```
[Element]: [problem]. [cost]. [fix].
```

**Never use section names as fixes.** "Improve case studies" is not a Top-3 fix — it's a category.

### Bad Top-3 (banned)

- ❌ "Improve case studies"
- ❌ "Add more metrics"
- ❌ "Tighten the resume"
- ❌ "Make the portfolio more cohesive"
- ❌ "Work on visual craft"

### Good Top-3 (the shape we want)

1. `Element: the homepage hero. Cost: generic gradient + "passionate designer" tagline = bouncing at 0-3s tier. Fix: replace with one screen of the [project name] work + the positioning sentence "I ship onboarding flows for B2B SaaS."`
2. `Element: the [project name] case study outcome. Cost: outcome lives in paragraph 6, never read. Fix: move the paragraph that starts "After launch, the team measured..." to the top, immediately under the problem statement.`
3. `Bullet says "Responsible for designing checkout flow." Cost: passive verb + no result kills the resume's strongest project. Fix: "Led checkout redesign for [N]M-MAU SaaS — cut drop-off 38% → 22% (Mixpanel, Q3 2024)."`

### Top-3 selection rules

1. Pick the highest-leverage fixes — the ones that move the most when done.
2. If the portfolio fails Tier 1 of the skim test, the entire Top-3 should be Tier 1 fixes.
3. Each fix names a specific element of the user's work — quote it verbatim where possible.
4. Each fix has a concrete rewrite or move. No "consider X." No "think about Y."
5. Reference frameworks by name (per `voice.md` §9) when relevant: "See: references/frameworks.md#problem-process-outcome."

---

## How a workflow uses this rubric

Resume + portfolio review workflows (in `workflows/`) consume this file as follows:

1. The career-stage router in SKILL.md detects junior / early-career / 0-2 yrs and loads `rubric-junior.md` (this file) — never alongside `rubric-senior.md`.
2. The workflow walks §1 (skim test) first, in order, gating each tier. Failures at Tier 1 short-circuit the rest.
3. The workflow then applies §2-5 (case study structure, narrative, outcomes, craft) as supporting detail — the Top-3 fixes are pulled from whichever section flagged hardest.
4. For combined resume+portfolio review, §6 (R-flags) runs in parallel; coherence between resume bullets and case study outcomes is checked explicitly.
5. Output ends with the §7 Top-3 block + the mandatory disclaimer footer (D-16) from `voice.md` §11.
