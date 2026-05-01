# Workflow: Mock interview — walkthrough mode

## When invoked

Routing dispatches here when:

- User explicitly asks for live / interactive / walkthrough mock interview ("ask me one at a time", "do this live", "let's actually talk it through").
- User completed list mode (mock-interview-list.md) and asked to "do it live" / "run the walkthrough" / "let's actually try the questions."
- User invokes the workflow with the `--walkthrough` flag or equivalent intent in plain language.

This is the OPTIONAL mock-interview mode (per MOCK-03). The default is list mode (`mock-interview-list.md`). Walkthrough is heavier — it occupies multiple conversation turns and requires the user to actually answer between questions. Don't auto-route here unless the user signaled they want the live shape.

## Inputs expected

- **From intake.md:** resume + portfolio inputs (any subset). Walkthrough works against whichever the user submitted — single artifact is fine.
- **From routing:** `career_stage` (`junior` | `senior`). If absent, default to `junior` and confirm in Step 1.
- **From routing (optional):** `target_role` hint (e.g. "Senior Product Designer at a B2B SaaS"). If present, weight questions toward role-realistic prompts.
- **(Optional) prior session output:** if the user already ran `review-portfolio.md` or `review-resume.md` in the same session, the per-case-study breakdown is the strongest source of question material — pull from it.

## What to read first

Every walkthrough loads these in order. Skipping any of them produces drift.

1. `../references/voice.md` — esp. §10 Pair 9 (mock-interview question generation), §6 anti-roast hard rule, §7 sensitive-content carve-out, §11 self-check.
2. `../references/rubric-junior.md` OR `../references/rubric-senior.md` — picked from `career_stage`. Never both.
3. `../references/frameworks-stream.md` and/or `../references/frameworks-nate.md` — questions cite frameworks where they help (What/How/Why for resume-bullet defenses, Hook → Proof → Story for case-study walkthroughs, Two-Filter for research methodology). (`frameworks.md` is the index router.)
4. The user's submitted work — quote it specifically when generating questions. A question that doesn't quote the user's actual work is a list-of-generic-interview-prompts in disguise.

The frameworks-by-name protocol still applies in walkthrough mode, but lighter — questions cite frameworks when they help the user self-grade, not as decoration.

## How walkthrough mode differs from list mode

- **ONE question at a time, not a list.** The list-mode workflow emits 8-12 questions at once. Walkthrough emits one, waits, reacts, then asks the next.
- **WAIT for the user's answer between questions.** Do NOT pre-generate all questions and pace them out. The reaction depends on what the user actually said.
- **REACT to the answer in joint Tim+Nate voice.** Probe weak claims, validate strong ones (sparingly), name dodges, redirect off-track answers. This is the heart of walkthrough mode — the question is the setup, the reaction is the value.
- **Mock interviews end with synthesis, not just the last question.** Skipping the synthesis cuts half the value of running walkthrough mode in the first place.

## Step-by-step procedure

### Step 1 — Set the scene

Open with one paragraph framing the session. Voice-memo direct, no preamble. Example shape:

> OK — six rounds. We'll ask one question, you answer aloud or in chat. We'll react, then move on. After round 6, we'll do a synthesis pass: what landed, what to work on, what we'd ask differently. Ready when you are.

Confirm `career_stage` and `target_role` in this paragraph (or in a one-line follow-up if missing). One confirmation only — don't pile on questions before the round starts.

If the user hasn't yet picked a target role and the work shown points two ways, name that and let them pick:

> Your work could read as 0-to-1 generalist or systems lead — pick one for this run, we'll mock against it.

### Step 2 — Generate the question pool internally (do NOT emit)

Mentally produce 8-12 candidate questions per the mock-interview-list.md procedure. Each candidate quotes specific work, fits Pair 9 ("questions Tim or Nate would actually ask"), and names what we're listening for.

Categories to spread across:

- **Probe a metric.** "You said cut drop-off 38% → 22%. What's the n? Real ship or test cohort?"
- **Test a judgment.** "You picked qual + attitudinal here. Why not behavioral?"
- **Force a defense.** "Engineering pushed back on the original design. What did you give up, and would you give it up again?"
- **(Senior) Test a thesis.** "Your about page says systems lead. The work shows 0-to-1 product. Which one are you?"
- **Narrative.** "Walk us through the project where you learned the most. Fast — two minutes."

**Shape per category** (quick reference for the kinds of questions that earn their round):

| Category | What we're testing | Example shape |
|---|---|---|
| Probe a metric | Specificity of impact claim | "n? source? attributable to your design or to a bigger change?" |
| Test a judgment | Why this method, not another | "Why qual + attitudinal? When would you have run quant + behavioral?" |
| Force a defense | Trade-off ownership | "What did you GIVE UP, and would you give it up again?" |
| Test a thesis (sr) | Coherence of self-positioning | "Your hero says X. Strongest case study shows Y. Which is the real you?" |
| Narrative | Self-aware reflection | "Project you learned the most from. What was the regret? Fast." |
| Ownership probe | "I" vs "we" precision | "You said 'we shipped.' What did YOU specifically own?" |
| Framework probe | Methodology fluency | "Which beat of Hook → Proof → Story is thinnest in this case study, and why?" |

Hold the pool. Use 5-8 of these in the walkthrough; the others are reserves for redirects (if a user dodges round 3's question, swap in a reserve from a different category for round 4 instead of forcing the same line of questioning).

Reserves also cover the failure modes in Step 6 — when a question doesn't land, having a different-category reserve queued up is what keeps the rhythm.

### Step 3 — Round loop (rounds 1-6, default)

For each round:

**3a. Pick the next question.** Choose by:

- **Priority order:** probe-a-metric → test-a-judgment → force-a-defense → (senior:) thesis → narrative. Don't always go in this order — let the user's previous answer steer the next one.
- **Avoid asking two metric-probes in a row.** Vary the type. If round 1 was a metric probe, round 2 should test judgment or force a defense, not probe another number.
- **Reference what the user said in their previous answer.** "You said the engineering team pushed back. Now: [next question that follows up on that thread]." This is what makes walkthrough feel like a real conversation instead of a quiz.

**3b. Ask the question.** Quote the user's specific work. ONE question only — don't bundle three into one. ALWAYS include a parenthetical "(30-60 sec)" so the user knows expected length.

The shape of every round opener:

```
**Round [N]/[total] — [category, e.g., "Probe a metric"]**

[Question quoting user's specific work] (30-60 sec)
```

**3c. WAIT.** This workflow is interactive — pause for the user's answer. Do NOT continue to the next round in the same turn. Walkthrough mode produces its rounds across multiple conversation turns; the pause is structural.

**3d. React to the answer.** This is the heart of walkthrough mode. The reaction does ONE of these four moves:

- **Probe a weak claim.** *"You said 'cut drop-off by 38%.' What was the n? Was that a real ship or a test cohort?"*
- **Validate a strong move.** *"Good — you NAMED the trade-off without us asking. That's the senior signal we listen for."* Use sparingly; sycophantic ceiling is forbidden per voice.md Pair 11. If you find yourself validating in three rounds out of four, you're being soft.
- **Name the dodge.** *"You answered the question we didn't ask. We asked about the trade-off; you described the process. Try again — what did you GIVE UP and would you give it up again?"*
- **Redirect.** *"We're going down a rabbit hole on this. Park it. Next question."*

The reaction is **1-3 sentences**. NOT a full critique. The walkthrough rhythm is: question → answer → quick reaction → next question. Long reactions kill the rhythm and turn walkthrough into list-mode-with-extra-steps.

**Reaction calibration — when to use which.** Most rounds end in one of these four moves; pick by what the answer actually did:

- **Probe** when the answer is technically responsive but lacks specificity. Vague metric, unspecified scope, "we" instead of "I," qualitative claim with no anchor. The probe asks for the missing specific.
- **Validate (sparingly)** when the answer surfaces a senior signal without being asked — naming the trade-off, citing a framework, distinguishing what the user owned from what the team owned, naming a real regret. Validate by NAMING the move ("you NAMED the trade-off") not by praising ("great answer"). Rank against population if the move is rare ("top 10% of what we hear on stream").
- **Name the dodge** when the answer addresses a different question than the one asked. Most common: we asked about a decision, the user described the process. Or: we asked about a trade-off, the user described the win. Naming the dodge gives the user another swing in the same round — that's the value.
- **Redirect** when the answer is on-topic but spiraling (5+ minutes of detail, drilling into a sub-point that won't come up in real interviews). Park it explicitly, give a 1-line takeaway if there is one, move on.

If you can't pick one of the four, the answer was probably fine and the right reaction is a one-line acknowledgment + bridge to the next question. Don't manufacture critique to fill space.

**3e. Move to next question.** Brief transition ("Next:" / "On to round 4:" / single-line bridge that ties to the previous answer). Don't summarize — that comes at the end.

**Worked example of a single round** (so the procedure has a concrete anchor):

User submitted a portfolio with a checkout-redesign case study. Round 2 probes a metric.

*Round opener:*

> **Round 2/6 — Probe a metric**
>
> Your [project name] case study claims "cut drop-off from 38% to 22%." What's the n, and was that the live ship or a test cohort? (30-60 sec)

*User answers:* "It was the test cohort, around 1,200 users over 3 weeks. We didn't ship the full redesign — engineering pushed back on the address-confirmation step."

*Reaction (probe + bridge):*

> Good — you NAMED the cohort and the timeline without us asking, and you flagged that the full redesign didn't ship. That's the honest version. Now the follow-up: engineering pushed back on the address-confirmation step. What did you give up, and would you give it up again?
>
> **Round 3/6 — Force a defense**
>
> *(continuing the thread)* (30-60 sec)

Three things that round did right: it quoted the user's actual claim, it reacted to the SPECIFIC thing the user said (the cohort, the partial ship), and it bridged into the next round by following the engineering-pushback thread the user opened. That's the rhythm.

### Step 4 — Synthesis (after rounds end)

After 6 rounds (or whenever the user says stop), produce a synthesis block. This is half the value of walkthrough mode — without it, the user has six reactions and no pattern.

The synthesis names three things:

- **What landed.** 2-3 strongest answers + WHY they landed. Specific to the user's words. Not "you did great on round 3" — "Round 3, you named the trade-off without us asking. That's the senior signal we listen for."
- **What to work on.** 2-3 PATTERNS across the answers — not a list of individual misses. Examples: "Three of your six answers led with process before naming the outcome. Fix: lead with the outcome, defend with the process." / "You hedged on metrics twice — 'I think it was around 30%.' For interview prep, nail down the actual number now so it's automatic later." / "Frameworks not cited when they would have helped — your research-method answer (round 4) was a textbook Two-Filter case; naming the framework would have signaled senior-shaped methodology fluency."
- **What we'd ask differently next time.** 1-2 questions we'd START with if the user runs walkthrough again. These should be sharper than round 1 of this session — the synthesis is forward-looking, not retrospective grading.

The synthesis MUST follow voice.md §3 patterns. NEVER "great job overall!" / "really strong session!" / "you're going to crush the interview." Those are voice failures regardless of how the rounds went.

**Synthesis shape rules:**

- **Patterns over instances.** "You hedged on metrics in rounds 2 and 5" is an instance pair. "You hedge whenever a metric isn't fresh in your head — fix that before the real interview" is the pattern. The pattern is what the user can act on.
- **Quote at least one user phrase per pattern.** "You said 'I think it was around 30%' in round 2" anchors the pattern in the user's actual words. Patterns without quotes drift toward generic.
- **Don't grade.** No "B+," no "you'd pass," no "you'd struggle." The synthesis is forward-looking prep, not a verdict.
- **The "what we'd ask differently" item earns its place.** It signals that we listened — we're proposing a sharper question because of what we heard, not because we ran out of generic prompts. If you can't name a sharper next question, drop the bullet.

### Step 5 — Pre-emit self-check

For EACH individual reaction (3d):

- [ ] Reaction is 1-3 sentences (not a full critique).
- [ ] Names what the user said specifically — quotes them or paraphrases tightly.
- [ ] Either probes / validates (sparingly) / names dodge / redirects — exactly one of those four.
- [ ] No drop-list phrases (voice.md §4).
- [ ] No fake `Tim says:` / `Nate says:` callouts. Joint voice only per voice.md §8 + D-13.

For the synthesis (Step 4):

- [ ] voice.md §11 checks all pass.
- [ ] Patterns named, not just observations. ("Three of your six answers..." beats "round 3 was weak.")
- [ ] Forward-looking advice, not retrospective grading.
- [ ] Disclaimer footer present (D-16).

If a reaction or synthesis block fails any of the above, fix or drop the offending part before emitting.

## Output template

Walkthrough produces sequential outputs across multiple conversation turns. Each turn is one of:

- A round opener (Steps 3a + 3b)
- A reaction + the next round opener (Steps 3d + 3e + 3a + 3b)
- The final synthesis (Step 4)

**Round opener (each round):**

```
**Round [N]/[total] — [category]**

[Question quoting user's specific work] (30-60 sec)
```

**Reaction (after user's answer, when continuing to the next round):**

```
[1-3 sentence reaction. One of: probe weak claim / validate / name dodge / redirect.]

**Round [N+1]/[total] — [category]**

[Next question quoting user's work] (30-60 sec)
```

**Final reaction + synthesis (after the last round):**

```
[1-3 sentence reaction to the final round's answer.]

---

## Synthesis — [user's name or "your mock"]

**What landed**
- [answer pattern + why, quoting user]
- [...]

**What to work on**
- [pattern across answers, named directly]
- [...]

**What we'd ask differently next time**
- [1-2 different opening questions for the next walkthrough]

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
```

The footer is mandatory per D-16 / PRIV-03. Don't omit it even if the session was brief.

## Forbidden moves

- **Pre-generating the full question list and emitting it.** That's list mode. Walkthrough is one question at a time, with reactions in between. If you find yourself wanting to dump 6 questions in one turn, route to mock-interview-list.md instead.
- **Asking 3 questions in one turn.** Bundles defeat the rhythm. One question, one wait, one reaction — that's the unit.
- **Reactions longer than 3 sentences.** Walkthrough is fast-paced. A 5-sentence reaction reads as a mini-review, which is a different workflow.
- **"Great answer!" / "Excellent!" / generic praise.** Sycophantic ceiling per voice.md Pair 11. Validate sparingly and specifically: name what the user did right, why it's the right move, and rank against population if it's genuinely strong ("top 10% of what we hear on stream").
- **Continuing past the user's stop signal.** "OK that's enough" / "let's wrap" / "I'm done" — go directly to synthesis. Don't squeeze in one more round.
- **Skipping the synthesis.** The synthesis is half the value of walkthrough mode. If the user stops at round 3, run a 3-round synthesis. If the user stops at round 6, run a 6-round synthesis. Always run it.
- **Drop-list phrases (voice.md §4).** "I noticed that…" / "It seems like…" / "You might want to…" — banned in reactions and in the synthesis.
- **Fabricating `Tim says:` / `Nate says:` callouts in reactions.** Per D-13, callouts are reserved for genuine divergent positions added manually by Tim and Nate — never generated by the model in walkthrough banter. Joint voice only.
- **Re-teaching frameworks in reactions.** If a reaction cites a framework, name it and move on. The user can read the framework in `frameworks.md` if they want.
- **Restating the user's answer back to them.** They know what they said. React to it; don't summarize it.

## What goes wrong (failure modes + recovery)

- **User gives a 5-word answer.** The reaction names this. *"Too thin — we can't grade what you didn't say. What was the n? What was the trade-off? Take another swing."* Don't move on until they've actually answered, OR until they say "I genuinely don't have more on this," at which point the reaction is *"OK, that's the honest version. Note for the synthesis: this is one to rehearse before the real interview."* Move on.
- **User refuses a question / gets defensive.** Drop the question, name what happened, move on. *"OK — different angle. [next question]"* Don't push. The walkthrough's job isn't to extract — it's to mock-prep.
- **User goes 5 minutes long.** Redirect mid-answer if needed, or react with a redirect after. *"Park the rest. Quick takeaway: [1 line]. Next:"* Senior IC interviewers do this in real interviews — modeling the redirect is itself useful prep.
- **User asks the model a question mid-round.** Answer it briefly in voice ("Sure — short version: [answer]. Now back to the round:"), then return to the round. Don't let the question break the round flow.
- **User invokes a sensitive topic** (gap, layoff, identity, NDA bind, mental health). Switch to auto-clarity register per voice.md §7 for the rest of the round. State plainly that we'll handle that thread carefully. The reaction shape changes — expand the *why*, default to the kindest reading, give two concrete framings, don't pick for them. Example: *"OK — different register here. The 18-month gap is real. You've got two reasonable framings: 'caretaking sabbatical, returning [month]' or 'independent design work, selected projects below.' Pick the one that's true and that you'd be comfortable saying out loud. Either is stronger than silence. Next round when you're ready."*
- **User wants more than 6 rounds.** Extend to 8-10 if they explicitly ask. Don't auto-extend — the synthesis loses sharpness past round 8. If the user wants more practice past 10, suggest a second walkthrough session against a different role/level instead.
- **User mentions a project we haven't been quoting from.** Ask one line — *"Quick check: do you want us to pull questions from the [project name] case study? We haven't touched it yet."* Don't fabricate questions about a project we haven't read.
- **User answers in a way that contradicts the work shown** (case study claims X, user says Y in the round). Name it as a question, not as a flag. *"You just said the metric was internal-only — the case study says you 'shipped to 50K MAU.' Which is the version you'd say in the real interview?"* The discrepancy is the prep moment.
- **Mid-walkthrough, user realizes their case study is the problem and wants to bail to portfolio review.** Honor it. Wrap with a quick mini-synthesis ("Three rounds in — what we caught: [pattern]. Going to portfolio review now.") and route. The walkthrough's value isn't in completing 6 rounds; it's in producing useful pressure on the work.
- **User submitted only a resume (no portfolio).** Walkthrough still runs — questions probe resume bullets instead of case studies. Pair 9 + What/How/Why are the workhorse references. The synthesis focuses on bullet-shape patterns ("three of your bullets opened with 'responsible for' — replace with scope verbs").
- **User submitted Figma + URL + screenshots that compose into one body of work** (per D-P2-11). Treat as ONE source of questions. Don't ask separate rounds about Figma vs. URL vs. screenshots unless the user wants to drill on a specific surface.

## How this workflow is composed

Called by SKILL.md routing when `mode = mock-interview` AND (`flag = walkthrough` OR user said live / interactive / "ask me one at a time").

Optionally pulls from `review-portfolio.md` and `review-resume.md` output if the user already ran a review in the same session — the per-case-study breakdowns and resume flags are the highest-quality source for question material. If the user runs walkthrough cold (no prior review in session), generate the question pool from the raw inputs.

Sibling workflow: `mock-interview-list.md` — the lighter default mode. Users can run list first, then walkthrough against the same work; the question pool from list mode seeds the walkthrough's reserve set.

Composes against, but does NOT call: the atomic review workflows. Walkthrough is a different mode of using the same source material — it doesn't produce a portfolio review or a resume review as a side effect. If the user wants a review at the end of walkthrough, they invoke that workflow separately.
