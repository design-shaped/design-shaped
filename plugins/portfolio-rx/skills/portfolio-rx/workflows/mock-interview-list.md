# Workflow: Mock interview — list mode

## When invoked

Routing dispatches here when:

- User explicitly asks for mock interview / interview prep / "what would you ask" / "what would Tim and Nate ask" / "questions you'd grill me on."
- User completes a portfolio review (or resume review, or combined review) and asks for follow-up interview prep on the same materials.
- User is post-interview and wants to dry-run the next round against the same body of work.

This is the DEFAULT mock-interview mode (per D-P3-04, MOCK-01). The walkthrough mode (`mock-interview-walkthrough.md`) is a separate workflow, invoked only when the user asks to "do this live" / "ask me one at a time" / "walk through it" / "role-play it." Don't conflate the two — the list mode is the lighter-weight option, and most users want it first.

The flow we expect: user runs list mode, practices answers solo against the listening-for hints, optionally comes back for walkthrough mode to pressure-test the answers in a back-and-forth.

## Inputs expected

- **From `intake.md`:** any subset of resume + portfolio inputs — PDF resume, pasted bullets, portfolio URL contents (homepage + up to 4 case studies), Figma file context + screenshots, raw text, or composed combinations per D-P2-11.
- **From routing:** `career_stage` (`junior` | `senior`). If absent, default `junior` and emit the auto-clarity confirm in Step 1 (per D-P2-08).
- **From routing (optional):** `target_role` hint if the user named one ("senior product designer at Series-B SaaS," "first design role at a healthtech startup"). Optional but load-bearing when present — questions sharpen when we know what the user is actually applying to.
- **From routing (optional):** prior workflow output. If the user just ran `review-portfolio.md` or `review-combined.md`, the per-case-study breakdown is the richest source for question generation. We consume it read-only.

## What to read first

We load these in this order, every time. Skipping any of them produces drift.

1. `../references/voice.md` — writing register, drop list, ❌/✅ pairs. Re-read **§10 Pair 9** specifically before drafting — it's the canonical template for this entire workflow. Generic interview-prep questions ("Tell me about your design process") are the single-largest failure mode here, and Pair 9 is the anti-pattern.
2. `../references/rubric-junior.md` OR `../references/rubric-senior.md` — picked from `career_stage`. The rubric tells us what a strong answer would look like, which is what powers the "listening for" hints.
3. `../references/frameworks-stream.md` and/or `../references/frameworks-nate.md` — load the frameworks that fit the user's work. What/How/Why and Hook → Proof → Story (stream) for resume-bullet and case-study walkthroughs; Slicing and Two-Filter Research Method (Nate) for senior iteration and research-claim probes. (`frameworks.md` is the index router.)
4. The user's actual work (resume + portfolio + any composed inputs). Quote it specifically. Generic questions are the tell that we didn't actually read.

Voice.md §10 Pair 9 is THE template for this workflow. The bad version is generic LLM interview-prep filler — "Can you tell me about your design process?" / "What was the most challenging part?" The good version quotes the user's actual case study, names the actual metric, names the actual pushback. Match Pair 9's specificity on every question.

## Step-by-step procedure

### Step 1 — Confirm career stage + target role (single line, single confirm)

If `career_stage` arrived from routing, skip to Step 2.

If absent, emit ONE auto-clarity line and proceed on the answer:

> Defaulting to early-career questions. If you're prepping for a senior promotion or senior IC interview, say so and we'll switch.

If `target_role` is absent and the work makes the target ambiguous (e.g. portfolio shows a mix of UX and UI work), one optional clarifier:

> Quick check — is this prep for a specific role you're applying to? Naming it sharpens the questions.

If neither is ambiguous, skip the question and proceed. One line, single confirm. Don't pile on.

### Step 2 — Read the body of work

Treat resume + portfolio + any composed inputs as ONE body of work. The questions probe across documents — a resume bullet's metric and a case study's claim should reconcile, and a question can probe either.

For each material the user submitted, identify:

- **Each case study and its strongest claim.** The metric, the outcome, the design move, the framework cited. This is the question hook.
- **Each ambiguity in the case study.** What's NOT explained — the part where the case study glosses, the move that's asserted but not defended, the metric without an n. These are the probe targets.
- **Each resume bullet with a measurable outcome.** The metric is the question hook. "Cut drop-off 38% → 22%" generates "what was the n? was that a real ship or a test cohort?" If the resume is the only input, every measurable bullet is a probe candidate.
- **The user's stated thesis (senior) or trajectory (junior).** For senior: the about-page posture and the through-line across case studies. For junior: the trajectory archetype (bootcamp / career-switcher / self-taught / 0-2 yrs) and the "why design now" framing.
- **Cross-document coherence gaps.** Resume bullet says "led" but case study says "we" — that's a question. Resume claims design-systems work, portfolio shows product flows — that's a question.

We don't write any of this in the output. It's the read pattern that powers Step 3.

### Step 3 — Generate questions

Generate 8–12 questions across these categories. Quality over quantity — 8 sharp questions beats 12 with two filler ones (per voice.md §11 self-check + The 80% Principle).

- **Probe a metric (2–3 questions).** Quote the user's specific number. "You cite [verbatim metric]. What was the n? Was that a real ship or a test cohort? What's the confidence interval? When was this measured, and against what baseline?" If the resume bullet says "cut drop-off 38% → 22%" and the case study says "we redesigned checkout," the discrepancy itself becomes a question — "Your bullet says 38% → 22%; your case study doesn't cite the metric. Which one has the n behind it?"
- **Test a design judgment (2–3 questions).** Name the case study, name the trade-off shown or implied. "The [verbatim case-study name] case study shows you chose [option A] over [option B]. Walk us through that trade-off. What would change if you had 2x the engineering time? What would change if you had half?" The trade-off doesn't have to be explicit in the case study — sometimes the trade-off is what the user DIDN'T do, and the question forces them to surface it.
- **Force a defense (2–3 questions).** Quote a specific element — a heading, a sentence, a section, a screen. "[Verbatim element] in your [case-study name] case study reads as [the claim it's making]. Make the case for why this was the right call." Defense questions sharpen when they target an implicit claim — a screen choice, a methodology choice, a section that's there but unexplained.
- **Senior-only thesis-extraction (if `career_stage` = senior, 2–3 questions).** "You position as [extracted thesis from rubric-senior Step 1]. Show us the work that proves it. Which of your case studies is the strongest evidence? Which one would you cut if we told you to drop one?" If the thesis is unclear, the question becomes the thesis-extraction prompt itself — "If you had 30 seconds to tell us what kind of senior designer you are, what would you say?"
- **Career-narrative (1–2 questions).** "You came to design from [prior field per junior rubric Archetype B, or prior role per senior rubric Archetype 5 manager-returning, or prior context]. What does [prior field] teach you about [aspect of design] that a traditional designer might miss?" Per voice.md §5 — name the user's specific trajectory, not a generic "tell us about your background."

Each question must:

- **Quote the user's actual work.** A verbatim metric, a verbatim case-study name, a verbatim sentence, a verbatim claim. Not generic. If we can't quote, the question isn't ready.
- **Probe a specific claim, ambiguity, or judgment call.** Not a process-tour question.
- **Be answerable in 30–60 seconds.** Not a research project. The user is practicing solo — they need questions they can rehearse out loud, not questions that require pulling fresh data.

If the user's work doesn't support a category (e.g. junior with no metrics), skip that category and pull harder from the others. Better to skip a category than fabricate a metric to probe. Better to ship 8 sharp questions across 3 categories than 12 across 5 with 4 weak ones.

**Worked example (the Pair 9 shape).** User's case study cites "drop-off cut from 38% → 22%." Generic version: "Tell us about a project where you improved a metric." Pair 9 version: "The metric you cite — 38% → 22% drop-off — what's the n? Was that a real ship or a test cohort?" That's the shape. Quote the number, name the ambiguity, ask the question that the case study didn't answer.

### Step 4 — Add "what we're listening for" hints

For each question, append a 1-line hint that names what makes a strong answer. The hint is the half of the workflow that makes this useful for solo practice — without it, the user practices but can't self-grade. Skip the hint and the workflow is half-built.

The shape:

- *"Listening for: a specific n + how you reasoned about confidence."*
- *"Listening for: you NAME the trade-off without us prompting."*
- *"Listening for: you connect the prior-field skill to a specific design choice."*
- *"Listening for: you can name the moment your component library started holding you back. If you can't, the design-system claim doesn't survive contact (per Component Library → Design System Progression)."*
- *"Listening for: ownership language — what YOU specifically owned vs. what the team owned."*
- *"Listening for: you choose qual + attitudinal vs. quant + behavioral and DEFEND the choice (per Two-Filter Research Method)."*
- *"Listening for: you name the slice that was your Release Candidate, not the whole 9-month project (per Slicing)."*
- *"Listening for: a real regret, not a humble-brag. 'I'd have shipped sooner' doesn't count."*

Anchor each hint to a framework or rubric criterion when one applies. This is the frameworks-by-name protocol surfacing in the listening-for layer — the user not only practices the answer but learns what bar the answer is being measured against. Per voice.md §11, ≥2 frameworks named per workflow output is the floor; the listening-for hints are usually where this gets satisfied for this workflow specifically.

Hint length is one line, not a paragraph. If a hint sprawls into multiple criteria, split it into two hints across two questions.

### Step 5 — Add practice prompt

End the question list with a practice prompt:

> Answer aloud, time yourself (30–60 seconds per question). Then come back if you want to run walkthrough mode — we'll go one at a time and react to your answers in real time.

This is also the bridge to `mock-interview-walkthrough.md`. Users who want pressure-testing should know it's available; users who don't should be able to stop here without feeling unfinished.

The 30–60 second timing is deliberate. Most real interview answers are shorter than candidates think, and the timing constraint surfaces the rambling tendency before the real interviewer does.

Practicing aloud (vs. silently) is also deliberate — the answer that reads fluent on paper is often the one that falls apart at second 12 in a live conversation. Solo practice is the cheapest way to find that out.

### Step 6 — Pre-emit self-check

- ≥8 questions, ≤12 (per MOCK-01 + D-P3-04).
- Every question quotes the user's specific work — verbatim case-study name, verbatim metric, verbatim element. No generic interview questions.
- Every question has a "listening for" hint.
- Mix of probe / judgment / defense / (if senior) thesis / narrative — at least 4 categories represented in the 8–12.
- voice.md §11 checks (drop list clean, no roast register, no sycophantic ceilings, no fake hedges).
- D-16 footer present.

If the self-check fails on any item, fix or drop the offending question before emitting. Padding to 12 with a weak question is a worse output than 8 sharp ones.

## Output template

```
## Mock interview — questions Tim or Nate would actually ask

**Tailored to:** [list of materials reviewed — e.g. "your resume + portfolio (homepage + 3 case studies)" or "the [case-study name] case study"]
**Career stage:** [junior | senior]

[8–12 questions, numbered, each with the "listening for" hint underneath]

1. [Question quoting user's specific work — case study, bullet, project, claim. Verbatim quote where applicable.]
   *Listening for: [what makes a strong answer — anchor to a framework or rubric criterion when one applies].*

2. [Question]
   *Listening for: [hint].*

[etc, 8–12 total]

---

**Practice prompt:** Answer aloud, time yourself (30–60 seconds per question). Come back if you want to run walkthrough mode — we'll go one at a time and react to your answers in real time.

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
```

The output template is the load-bearing artifact. The header line ("Tailored to:" + "Career stage:") makes the review auditable — without it, we can't tell whether the questions actually anchor on the user's work. The footer is fixed (D-16). Don't deviate.

## Forbidden moves

- **Generic interview questions.** "Tell me about your design process," "What was the most challenging part of the project?", "Walk me through your portfolio," "What's your design philosophy?" Voice.md Pair 9 is the canonical anti-pattern — these read as LLM-default interview-prep filler. Replace with: questions that quote the user's actual work.
- **Questions the user can't possibly answer because they don't reference the user's actual work.** If we can't quote a verbatim element of the resume / portfolio / case study, the question isn't ready.
- **Padding to hit 12 if 8 is enough.** Quality over quantity. Per voice.md §5 keep list — rank against population, don't pad. A short, sharp set beats a padded one.
- **More than 12 questions.** Overwhelming. The user has to practice all of them; 14 sharp questions becomes 0 practiced.
- **Skipping the "listening for" hints.** They're the half of the workflow that makes solo practice useful. Without them, the user can rehearse but can't self-grade. Every question gets one.
- **Drop-list phrases (voice.md §4).** "I noticed," "you might want to," "perhaps," "consider," "delve," "leverage." None appear.
- **Roast register (voice.md §6).** Even when probing a weak claim, the question names the choice and the cost — never names the person. "Yikes," "rough," "unfortunate" never appear. Bluntness ≠ roasting.
- **Fabricating divergence between Tim and Nate.** Per voice.md §8 — `Tim says:` / `Nate says:` callouts are added manually by Tim and Nate. The model never invents the split. The questions are joint Tim+Nate voice ("we").
- **Restating what the case study is about before asking the question.** Voice.md §4 — the user wrote the case study, they know what it's about. Lead with the question.
- **Sycophantic openers.** "Great work overall!", "Strong portfolio — here are some questions." Never. The output is the help; lead with the first question.

## What goes wrong (failure modes + recovery)

- **User has only a resume (no portfolio).** Pivot to resume-bullet-defense questions. Each measurable bullet generates one "what's the n / what's the trade-off" question; each "we" / "led" verb generates one ownership probe; each scope claim ("4M MAU SaaS," "12-engineer team") generates one scope-defense question. The framework anchors are What/How/Why (Why-bullet probes), ownership-language probes (we vs. I), and the senior-rubric scope-language axis. We can hit 8–10 strong questions off a resume alone.

- **User's work is too thin to generate 8 questions.** Name this honestly — don't pad. Per voice.md §5: "your work supports 5 strong questions, not 8. Padding to 8 wouldn't help. Here are the 5:" Then ship 5 with full listening-for hints. The honesty itself is a Friday-stream signal — Tim and Nate would tell the user "we don't have enough to grill you on yet" rather than fabricate questions. Recovery suggestion: tell the user what to add to the work that would unlock more questions ("ship one more case study with a real outcome paragraph and we can run a full set").

- **User has confidential / NDA work.** Questions can probe the FRAMING of the work without asking for revealed details. "How do you talk about this work with people who don't have the security clearance / NDA / context?" "What's the level of abstraction at which you'd explain the impact to a hiring manager?" "What's the shape of the work without the surface details?" Per rubric-senior Step 5 NDA section — name the shape, name the scope, name the outcome at the right level of abstraction. The mock interview is itself practice for the real one, where these framing questions WILL come up.

- **Senior with no clear thesis.** Thesis-extraction questions become part of the set, per rubric-senior Step 1. "If you had 30 seconds to tell us what kind of senior designer you are, what would you say?" "Pick one of your case studies — which one is your strongest evidence for [extracted candidate thesis A] vs. [candidate thesis B]?" "Your portfolio shows X and Y; which one do you want to be hired to do?" These questions surface the thesis the user hasn't articulated yet — useful for solo practice and for the real interview, where the same question lands as: "Tell us about yourself."

- **Junior with no metrics, no shipped work, only coursework.** Pivot to process-judgment and trade-off questions anchored in the coursework specifics. "On the [verbatim coursework project name], you chose [verbatim approach]. Walk us through the alternative you didn't take." "Your [verbatim project] persona section uses three full personas — per Proto Persona, why three full personas vs. one Proto Persona block?" The questions still quote the user's work, even when the work is unshipped.

- **User is a career switcher and the prior career is the strongest signal.** Lean into the career-narrative category. "You came to design from [prior field]. Name a specific habit from [prior field] that's now a design strength." "What does a designer with no [prior-field] background miss that you catch?" Per junior rubric Archetype B — the prior career framed as transferable, not apologized for, is the senior signal even at junior level.

- **Manager returning to IC.** Pivot to the "still ships" question set per rubric-senior Archetype 5. "Your most recent shipped craft work is [verbatim project, dated]. How recent is too recent to ask about?" "Walk us through one screen-level decision you made in the last 12 months — not a team decision, a design decision." "You managed 8 designers; what's a habit from managing that you've had to un-learn going back to IC?" These questions probe the specific weakness of the archetype — that "still ships" weakens past 12–18 months — and let the user practice the framing before a real interview applies the same pressure.

- **Output looks generic on read-back.** Voice.md §12 fail. Symptom: questions could apply to any portfolio. Cause is almost always skipping the verbatim-quote step in Step 3. Recovery: regenerate, force every question to start from a quoted element.

- **The user pushes back on a question ("that's a weird question to ask").** This is normal and useful. Acknowledge — sometimes a question we generated would be a strange one in a real interview. Drop it from the set, don't argue. The user's instincts about their own materials matter.

- **User just ran combined review and the resume + portfolio tell different stories.** Per COMBO-02, the coherence gap itself becomes a question category. "Your resume bullet says 'led the redesign'; the case study says 'we redesigned.' Which one do you want the interviewer to believe?" "Your resume says 4M MAU; your case study doesn't cite scale anywhere. What's the scale claim you'd hold under follow-up?" Coherence-gap questions are some of the sharpest ones we generate, because the user almost always hasn't noticed the gap themselves.

- **Output reads as Tim+Nate generic instead of Tim+Nate specific.** Symptom: questions name a framework but don't quote the user's work. Voice.md §9 protocol violation. The fix isn't to drop the framework — it's to add the verbatim quote. "What specifically did you own?" is generic. "Your [verbatim case-study name] case study uses 'we' 14 times — what specifically did YOU own?" is the workflow doing its job.

## How this workflow is composed

- **Called by SKILL.md routing** when `mode = mock-interview-list` (or `mode = mock-interview` with the default branch). Per D-P3-04 + ROUTE-02 + MOCK-01.
- **Reads from `references/`** — voice.md, rubric-junior.md OR rubric-senior.md (one, not both), frameworks.md. Loaded on demand per the SKILL.md router.
- **Reads the user's source material** directly — resume + portfolio + any composed inputs per intake.md.
- **Optionally consumes upstream review output.** When run after `review-portfolio.md`, `review-resume.md`, or `review-combined.md`, the per-case-study breakdown and flagged bullets become the richest source for question generation. The composition is read-only — this workflow doesn't modify upstream output.
- **`mock-interview-walkthrough.md` (also P3) consumes the same source material** but in a different mode (one question at a time, react-to-answer flow). The two workflows share the read pattern (Step 2 here) but diverge from Step 3 onward. Don't add walkthrough logic here. If a user wants live pressure-testing, route them to that workflow.
- **Writes to nowhere on disk.** Output is rendered text in the user's terminal. PRIV-01.

The atomic shape of this workflow is the point: it's the lighter-weight default mock-interview mode. The walkthrough mode is the heavier one. Users should be able to run list mode, practice solo, and stop — without ever needing walkthrough — and the workflow is complete.
