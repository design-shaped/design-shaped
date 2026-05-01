---
title: Frameworks — Resume Rx
plugin: resume-rx
covers: TGT-02, TGT-04, TGT-05, TGT-08
sources:
  - audit/parts/frameworks.md (Phase 1 audit)
  - research/STREAM_MINING_RESUME.md (Bucket 8 mining)
  - research/FEATURES.md §2.3 (named-framework feature spec)
  - research/PITFALLS.md §3.5 (canonical divergence example)
  - SPEC.md D-20 (closed framework set)
  - portfolio-rx/skills/portfolio-rx/references/frameworks.md (What/How/Why carry-over)
---

# Frameworks — Resume Rx

## Framework citation discipline

When a workflow applies a framework, it names that framework verbatim, quotes specifics from the user's bullet, and cites this file's section. Never paraphrase a framework name. Never invent acronyms. Never re-teach a framework inline in a review — the user can read this file if they want the definition. The workflow agent's job is to name the gap, quote the work, and prescribe the fix. The closed set of named resume frameworks is the seven below — STAR, CAR, XYZ, R-A-S, Scope-Impact-Metric, What/How/Why, Skim-test tiers — per SPEC D-20 and FEATURES §2.3. If a review needs a framework not on this list, flag the gap; do not invent.

Per voice.md self-check, every review surfaces at least two of these by name. Zero is generic LLM critique. One is competent. Two or three reads like Tim and Nate. The two-rule scaffold from portfolio-rx applies unchanged: (1) name the framework on first use; (2) quote the user's work, then frame.

---

## STAR

**Definition.** Situation / Task / Action / Result. Full narrative arc — set the scene, name the assignment, describe what you did, state the outcome. Four beats, each contributing a distinct piece of information. The interview-canon framework that designers most often default to when asked "tell me about a time when…" — useful as a structural reference, but rarely the right shape at the bullet level on a resume page.

**When to use.** Cover-letter fragments, summary-statement micro-paragraphs, behavioral-interview prep, and the rare bullet where the situation is genuinely non-obvious to the reader. STAR is verbose by design — it earns its space when the reader can't infer the setup from the role title or company name. On a resume itself, STAR is almost always wrong: the Situation and Task are implied by the role line above the bullet, so the Situation+Task clauses become filler. Use as a thinking tool to recover the full arc behind a bullet, then compress to CAR or XYZ for the page.

**Worked example.** A summary-statement opener for a designer pivoting from agency work into product:
> "At a 12-person design agency serving B2B SaaS clients (Situation), I was assigned the lead role on a stalled checkout-redesign engagement that had already burned two design rounds (Task). I rebuilt the discovery scope around the client's actual cart-abandonment data and ran three rounds of moderated usability testing on the prototype (Action). The redesign shipped six weeks later and reduced checkout-abandonment from 38% to 24% in the first quarter post-launch (Result)."

<!-- INVENTED: STAR-shaped summary opener constructed for illustration. STREAM_MINING_RESUME.md confirms STAR is rarely used at the bullet level on stream — the corpus prefers What/How/Why for bullets and reserves longer arcs for summary or cover-letter contexts. -->

**Failure mode when misapplied.** STAR at the bullet level eats too much line-count. A four-clause STAR bullet pushes other bullets off the page and forces the reader through Situation+Task before the Result lands — colliding with the descending-importance discipline of resume reading (STREAM_MINING_RESUME.md H8, 4tg1bPbOxus L1384–1385: *"we want to express the most important things in order that we want them to read them"*). On a one- or two-page resume, the Situation and Task are usually implied by the role line above the bullet, and STAR collapses into Action+Result — at which point you wanted CAR or XYZ, not STAR. The rule of thumb: if compressing STAR to CAR loses no information the reader needed, you wanted CAR.

---

## CAR

**Definition.** Context / Action / Result. Three beats. Compresses STAR's Situation+Task into a single context clause, then names the action and the result. The default bullet shape when scope context is needed but not load-bearing. Per KudosWall / Resume Whisperer canon (FEATURES §2.3), CAR is the resume-bullet shape that survives the move from interview-storytelling to page-density best.

**When to use.** Bullets where the action requires a one-clause setup to make sense — a constraint (NDA project, ambiguous scope, regulated industry), an unusual team shape, or a non-obvious surface. Use when the reader needs *some* context, but not the full STAR scene-setting. Also useful when the role line above the bullet doesn't carry enough scope to anchor the action — e.g., a designer who sat inside a marketing org but did UX work, where the title alone misleads.

**Worked example.** From the corpus, a CAR-shaped bullet rewrite Tim+Nate workshop on stream:
> "On a stalled ASU campus-services redesign with no live analytics access (Context), led usability passes across seven plus projects and aligned brand standards (Action), increasing user engagement 20% across the cohort (Result)."

The action and result are pulled verbatim from the corpus — Nate workshops the bullet "leading seven plus projects, including the redesign of ASU's Souls website" against a 20% engagement metric (STREAM_MINING_RESUME.md C5–C6, transcript 4tg1bPbOxus L1413–1425). The Context clause is recovered from the surrounding discussion of campus-design constraints. <!-- INVENTED: the "no live analytics access" context fragment is illustrative; the C5/C6 transcript exchange does not pin a specific constraint. -->

**Failure mode when misapplied.** CAR with a generic Context clause ("In a fast-paced startup environment", "As part of a cross-functional team") is worse than no Context — it eats space without telling the reader anything they couldn't infer. Per the copy-paste test (STREAM_MINING_RESUME.md B5/B9, 11zGHBSfaXc L1019–1022: *"You can copy and paste that bullet to my resume, and it would be just as universal"*), a generic Context clause is the single biggest tell. If the Context isn't doing real work — naming a constraint, a scope, or a non-obvious surface that the role line above doesn't already carry — drop to XYZ. The Context clause earns its keep by saying something a different designer's resume couldn't.

---

## XYZ

**Definition.** Accomplished X by doing Y resulting in Z — outcome stated up front, method second, transferable skill or scale signal third. Tight, metric-led, ATS-friendly. Google's hiring rubric popularized this shape; it stuck. Cited across enhancv, KudosWall, and Resume Whisperer canon (FEATURES §2.3) as the default metric-bearing bullet shape for designer resumes.

**When to use.** Mid-to-senior bullets where a hard metric exists and the action is recognizable to a hiring manager in the same role family. The most ATS-effective shape on the page because the keyword density of "by doing Y" tends to surface KSA matches without keyword-stuffing — verbatim Tim on resume keyword density: *"resumes do in fact often need to be stacked with keywords"* (STREAM_MINING_RESUME.md A2, 4tg1bPbOxus L1282–1284). XYZ achieves the stacking honestly because the keywords are doing semantic work in the bullet, not loaded as a separate skills-section pile.

**Worked example.** Pulled directly from Nate's verbatim bullet rewrite on stream (4tg1bPbOxus L1424–1425):
> "Increased user engagement by 20% by improving usability and aligning with brand standards, by leading seven plus projects, including the redesign of ASU's website."

The Accomplished-X (20% engagement) leads, the How-Y (usability + brand-standards work) follows, the Z (project scale, ASU surface) lands at the end. Nate's stream-side gloss: *"do you get the mindset, the motivation that I'm leading there with?"* (L1426). The bullet is the canonical XYZ shape from the corpus.

**Failure mode when misapplied.** XYZ without a real X invites metric fabrication — designers under pressure round up, borrow team-level metrics, or attach percentages to work that wasn't measured. Per SPEC D-16-RR, never invent a metric to fill the X; surface absence as a probe in rationale instead. The corpus is direct on this: *"sometimes these can feel like platitudes where you say reduced bounce rates… you're not providing any concrete numbers or evidence"* (STREAM_MINING_RESUME.md C1, 4tg1bPbOxus L398–399). If no honest hard metric exists, downgrade to a soft-metric or scope-led shape (CAR or Scope-Impact-Metric), not a fabricated XYZ. The framework's strength is exactly its weakness — the metric-first slot is structurally load-bearing, and an empty or fabricated slot hollows the bullet faster than any other shape.

---

## R-A-S

**Definition.** Result / Action / Skill. Three beats — lead with the outcome, name the action that produced it, surface the transferable skill or capability the bullet evidences. Per SPEC D-20 and Briefcase Coach's executive-resume canon. The R-A-S order forces the strongest signal to the front of the bullet.

**When to use.** Senior and staff bullets where the result is the headline and the action is well-understood once the result is named. R-A-S compresses faster than XYZ when the Z (skill or scope) is implicit in the role title above the bullet.

**Worked example.** A senior product-designer bullet rewritten R-A-S:
> "Cut SaaS activation drop-off from 38% to 22% (Result) by restructuring the onboarding sequence from 9 steps to 4 (Action), establishing a reusable Auth-flow pattern adopted by 3 product surfaces (Skill)."

<!-- INVENTED: senior-bullet illustration. STREAM_MINING_RESUME.md C9 (11zGHBSfaXc L1679) confirms the "adding numbers will bridge that gap [from senior UX into product]" register that R-A-S is built for, but the specific numbers are constructed for illustration. -->

**Failure mode when misapplied.** R-A-S at junior level positions the candidate above their evidence — a junior designer who leads every bullet with a Result-headline reads as inflating contribution, especially when the Action clause is thin or the Skill signal isn't backed by scope words elsewhere in the resume. Per the senior-tag-survives-gap discipline (STREAM_MINING_RESUME.md G9, ox8cqMpZbEg L331–332), R-A-S is for candidates whose career arc has earned the Result-first register; junior candidates should default to What/How/Why or CAR until the bullets carry their own weight.

---

## Scope-Impact-Metric

**Definition.** [Scope context] [action with scope claim] [metric or behavior-change outcome]. A senior- and staff-tier shape where the bullet's scope is the load-bearing signal — team size, customer base, surface area, ARR served — and the metric anchors the impact. Synthesized in FEATURES §2.3 from Resume Worded and Columbia Career Education accomplishment-statement canon.

**When to use.** Senior, staff, and lead bullets where "what changed because of you" requires naming what you owned at the org level. Scope-Impact-Metric surfaces ownership precision (per Theme B of STREAM_MINING_RESUME.md) — it's the shape that distinguishes "led redesign" execution narrative from senior-grade decision-making. Use when the scope claim is real and verifiable.

**Worked example.** A senior product-designer bullet rebuilt Scope-Impact-Metric:
> "Owned the redesign of onboarding for a $200M-ARR SaaS (Scope), drove drop-off from 38% to 22% (Impact), and produced a reusable Auth-flow library adopted across 3 product surfaces (Metric)."

This is the worked example from FEATURES §2.6 ("what changes because of you" senior-bullet diagnostic) — scope ($200M ARR), impact (drop-off delta), and second-order metric (library adoption count). <!-- INVENTED: the $200M ARR figure and 38→22% delta are illustrative scope/metric placeholders; FEATURES §2.6 is the source for the bullet shape, not specific numbers. -->

**Failure mode when misapplied.** Scope-Impact-Metric collapses when the scope claim is inflated. Per Theme B verbatim Nate (4tg1bPbOxus L762–765): *"You're not gonna claim sole ownership of [a project that wasn't yours alone]."* A bullet that opens "Owned the entire design system for a Fortune 500" when the candidate contributed two components reads as senior over-claim and is the failure mode the framework most often surfaces. The fix is precision (`owned` → `contributed`, `entire system` → `the Auth and Billing component sets`), not a different framework.

---

## What/How/Why

**Definition.** What you did → How you did it → Why it mattered, with the explicit instruction to flip the order at output time so the Why leads. The most-cited framework in the @designshaped corpus (13/23 transcripts, per STREAM_MINING_RESUME.md). Verbatim Nate: *"if you follow a what-how-why approach, really hard to write a bad bullet"* (4tg1bPbOxus L1421-onward). Verbatim Tim: *"no one's hiring you for what you did… they're hiring you for the impact."* The single most-portable framework from portfolio-rx — re-anchored here on resume bullets.

**When to use.** Any bullet where the reader needs to hear the impact first. Default scaffold for resume bullet rewrites — replaces STAR for stream-native voice. The flip-the-order step is the actual mechanic: writers naturally draft What-first; the framework's job is to surface that and prescribe the flip.

**Worked example.** The canonical resume-bullet exemplar, quoted verbatim from portfolio-rx frameworks.md and from Nate's stream-side rewrite (4tg1bPbOxus L1413–1425):

The user's submitted bullet leads with What:
> "led seven plus projects, including the redesign of ASU's Souls website"

Nate's verbatim flip to Why/How/What:
> "Increased user engagement by 20% by improving usability and aligning with brand standards, by leading seven plus projects, including the redesign of ASU's website."

The Why (20% engagement) leads, the How (usability + brand-standards work) is in the middle, the What (project count + ASU surface) lands last. This is the load-bearing resume-bullet exemplar across resume-rx — every line-edit-mode rewrite that flips a What-first bullet cites this framework by name.

**Failure mode when misapplied.** The two failure modes are (1) forcing the flip on bullets that are honestly What-first by design — a role-context line, a housekeeping bullet naming the platform or team formation, or a bullet whose Why is genuinely unknown — and (2) skipping the How and producing a Why-only bullet ("Increased engagement 20%") that strips the reader of any way to assess what the designer actually did. The full Why/How/What sentence shape needs all three beats. Per the corpus, also distinct from STAR — STAR is Situation/Task/Action/Result; What/How/Why collapses S+T into context-implicit and replaces R with Why-stated-as-impact.

---

## Skim-test tiers

**Definition.** A timed-attention model with three tiers: 0–3 seconds (header read — name, role, company, dates), 3–10 seconds (most-recent role and top bullet), 10–30 seconds (bullet pull-through across the rest of the page). Each tier has a specific question the document must answer in that window. Replaces portfolio-rx's "Read-the-Titles-Only Test" with a resume-native equivalent per FEATURES §1.3 and SPEC D-20. The 7.4-second hiring-manager scan figure (LinkedIn, 2024) is the empirical anchor for the 0–3s and 3–10s tiers.

**When to use.** Before any bullet-level work. Run the skim-test pass on the whole document first — the most-leveraged fixes almost always surface at the 0–3s tier (header) and 3–10s tier (recent-role bullets), and bullet rewrites buried in older roles can't compensate for a 0–3s failure. Also: section-order coherence checks (FEATURES §1.6) anchor on this framework.

**Worked example.** Applied to a hypothetical senior-product-designer resume that opens with an "Education" section and a generic summary:
- **0–3s test (header):** Reader sees "Senior Product Designer" but the most-recent role is buried below "Bachelor of Fine Arts, 2014." Fail — the strongest signal isn't leading. Fix: pull most-recent role to the top.
- **3–10s test (recent role and top bullet):** Top bullet reads "Worked on redesign of checkout flow." Fail — activity-first, no outcome. Fix: flip via What/How/Why.
- **10–30s test (bullet pull-through):** Bullets across older roles are uniformly task-narrative. Fail — no scope words, no metrics. Fix: surface 1–2 metric-bearing bullets per role; cut the rest.

The 0–3s/3–10s/10–30s sequencing is the rubric-junior.md timed-tier model from portfolio-rx, ported to resume scope per the audit appendix decision (frameworks.md row, divergent rewrite). <!-- INVENTED: the senior-PD example is illustrative — not pulled from a specific transcript — but the failure modes (education-leads-senior, activity-first top bullet, no scope words across older roles) are corpus-attested patterns from STREAM_MINING_RESUME.md Themes B, C, and H. -->

**Failure mode when misapplied.** The skim-test is a diagnostic, not a content rule. Misapplied, it becomes a license for keyword-stuffing the top of the resume to "win" the 0–3s test, which collides with FEATURES §3.4 (no generic keyword-stuffing). The framework's job is to surface where attention dies on the page, not to demand that every tier "pass" a fixed score. Some sections (older roles, education for senior candidates) are *meant* to fail the 10–30s tier — that's the design.

---

## Choosing between frameworks

The seven frameworks aren't interchangeable; each fits a specific bullet shape and seniority register. Default to **What/How/Why** for any bullet rewrite — it's the corpus-load-bearing scaffold (13/23 stream transcripts). Reach for **XYZ** when a hard honest metric exists and the bullet wants the tightest ATS-friendly shape. Reach for **CAR** when the bullet needs a one-clause Context to make sense (NDA constraint, unusual team shape, regulated-industry surface). Reach for **R-A-S** at senior/staff level when leading with the result is honest and the action clause earns its place. Reach for **Scope-Impact-Metric** when the bullet's headline signal is *what you owned at the org level* — team size, ARR, surface area, customer base — and the metric anchors that scope. Reach for **STAR** only at summary or cover-letter scale, never at bullet scale on a one- or two-page resume. Run **Skim-test tiers** before any bullet-level work, on the whole document — it tells you where the bullet-level work is most leveraged.

A quick decision heuristic by bullet-shape signal:

| If the bullet has… | Lead with… |
|---|---|
| A hard metric and a recognizable action | XYZ |
| A real one-clause context that the role line doesn't carry | CAR |
| A senior-grade scope claim (team / ARR / surface) and a metric | Scope-Impact-Metric |
| A senior-grade result that earns leading the bullet | R-A-S |
| Activity-first draft with impact buried at the end | What/How/Why (flip to Why/How/What) |
| Genuinely non-obvious situation (cover letter, summary, NDA) | STAR |
| A whole-document attention-failure question | Skim-test tiers (run first, before any of the above) |

When in doubt, name two frameworks rather than zero, per voice.md self-check. A review with no framework names reads as generic LLM critique; a review with two reads like Tim and Nate.

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
