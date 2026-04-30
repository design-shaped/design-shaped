# Detection checklist — Portfolio Rx

A 6-point harness for catching the "feels like generic LLM" failure mode. Run this against any review the skill produces. Source: `../../.planning/builds/portfolio-rx/research/PITFALLS.md` §8.5.

## How to use

1. Generate a review by running the skill against a real portfolio / resume / case study.
2. Read the review.
3. Run all 6 checks below. Each produces PASS / FAIL + a 1-line rationale.
4. If any check fails, the review needs to be regenerated with stricter voice discipline. Update `references/voice.md` if the failure mode is novel.

This is a manual harness in v0.1.0. A future automated version may script Checks 1, 4, and 6.

---

## Check 1 — Hedge-word grep

**Question:** Does the review contain any phrases from the `references/voice.md` §4 drop list, in the SKILL'S voice (not in quoted user copy)?

**How to run:**
- Open the review output.
- Skim for these flagged phrases (verbatim in skill voice):
  - "I noticed", "It seems like", "It would be helpful to"
  - "You might want to consider", "Perhaps consider", "You may want to"
  - "I think", "I believe", "From my perspective"
  - "delve", "leverage", "navigate the landscape"
  - "actionable insights", "synergy", "robust", "seamless", "elegant solution"
  - "Great work overall!", "with a few tweaks…"
  - "yikes", "lol", "disaster", "rough", "unfortunate"
  - "Hope this helps!", "Best of luck!"
- If found in skill voice → FAIL. (Quoted user copy that includes these phrases is OK — voice.md keep list says "quote the user's own copy.")

**Pass example:**
> "Bullet says 'designed checkout flow.' Designed how, for whom, with what result?"

**Fail example:**
> "I noticed your bullet could be more impactful. Consider adding metrics."

**Rationale line:** PASS — no drop-list phrases in skill voice. (or)  FAIL — review used "I noticed" in section X, "consider" in section Y.

---

## Check 2 — Rewrite-ratio (≥0.8)

**Question:** Does every flag have a concrete rewrite or next move?

**How to run:**
- Count: total flags surfaced (numbered or bulleted critique items).
- Count: total rewrites or concrete next moves attached to those flags.
- Compute: rewrites / flags. Target: ≥0.8.

**Pass example:**
> Flagged: bullet "designed checkout flow"  
> Rewrite: "Redesigned checkout for [N]M-MAU SaaS — cut drop-off from 38% → 22% in the test cohort."

**Fail example:**
> "Your case studies could use more specificity."  *(no rewrite; ratio gets dragged down)*

**Rationale line:** PASS — 12 flags, 11 rewrites, ratio 0.92. (or)  FAIL — 8 flags, 4 rewrites, ratio 0.50.

---

## Check 3 — Framework-name surfacing (≥2 per review)

**Question:** Does the review cite at least 2 named frameworks from `references/frameworks.md`?

**How to run:**
- Skim the review for any of these framework names (or any others in `frameworks.md`):
  - STAR, Problem → Process → Outcome (P→P→O), Inverted Pyramid, Brian Lovin's Ownership Language
  - Slicing, Stakeholder Needs Map, The 80% Principle, Dual Track Agile
  - Brand Drivers, Ethos / Pathos / Logos, Ladders
  - Two-Filter Research Method, Proto Persona
  - Component Library → Design System Progression, House Analogy, Lean / Agile / Scrum, Three Pillar System
- Count distinct frameworks named. Target: ≥2.

**Pass example:**
> "This case study skips the *outcome* in Problem → Process → Outcome." (1)
> "Your hero hits Slicing's mid-point but doesn't show the customer-facing change." (2) → PASS

**Fail example:**
> No framework cited; review uses generic "case study structure" language. → FAIL

**Why it matters:** frameworks-by-name is the load-bearing voice mechanic per D-19. Skipping it is the fastest path to generic-LLM output.

**Rationale line:** PASS — 3 frameworks named (P→P→O, Slicing, Brand Drivers). (or)  FAIL — 0 frameworks named; review reads as "improve case study structure."

---

## Check 4 — Top-3 format

**Question:** Does the review's Top-3 fixes section use the `[Element]: [problem]. [cost]. [fix].` template, NOT section names?

**How to run:**
- Find the Top-3 section (usually at the top of the output).
- Each item should be a specific element + concrete problem + concrete cost + concrete fix. NOT "Improve experience section" or "Strengthen case studies."

**Pass example:**
> 1. Hero outcome: case study buries the metric in paragraph 6. Hiring manager skims past it. Move "38% → 22% drop-off" to paragraph 1.

**Fail example:**
> 1. Improve case studies. (section name, no specifics) → FAIL
> 2. Strengthen resume bullets. (section name) → FAIL

**Rationale line:** PASS — all 3 Top-3 items use the template. (or)  FAIL — items 1 and 2 are section names.

---

## Check 5 — Sensitive-content auto-clarity

**Question:** If the review touches sensitive content (career gap, layoff mention, identity disclosure, ESL copy, caretaking), does the skill use the auto-clarity register from voice.md §7?

**How to run:**
- Skim the user's submitted materials for sensitive content signals (gap dates, layoff language, identity markers, ESL phrasing, caretaking mention).
- If sensitive content is present, the review should:
  - Use longer, more explanatory framing (not terse mode).
  - Default to the kindest plausible reading.
  - Never name the person; name the choice.
  - Give explicit permission to keep privacy.
  - Provide concrete framing options the user can pick from.
- If no sensitive content is present, this check is N/A (PASS by default).

**Pass example (sensitive content present):**
> "There's a 2023-2025 gap. You don't owe anyone the reason, but a one-line caption — 'Caretaking sabbatical, returning [month]' or 'Independent design work, selected projects below' — beats silence."

**Fail example (sensitive content present):**
> "Your resume has a gap from 2023-2025 that you may want to address." (terse mode applied to sensitive content; passive judgmental phrasing)

**Rationale line:** N/A — no sensitive content detected. (or)  PASS — auto-clarity register applied to gap mention. (or)  FAIL — terse mode on sensitive content; "may want to address" is passive judgmental.

---

## Check 6 — Footer presence

**Question:** Does the review end with the verbatim D-16 footer?

**How to run:**
- Open the review output.
- Tail of the output should be (verbatim, character-for-character):
  > *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
- If the footer is missing, paraphrased, or in a different position → FAIL.

**Pass example:** Footer present at the end of the review, verbatim wording.

**Fail example:** Footer missing; or "P.S. join us on the Friday stream" instead of the verbatim D-16 wording.

**Rationale line:** PASS — footer verbatim. (or)  FAIL — footer was reworded to "join us on the Friday stream."

---

## How to score

- **All 6 PASS:** review is shippable. Generic-LLM signal undetected.
- **1-2 FAIL:** patch the review or regenerate with tighter voice prompts. Update `references/voice.md` if the failure pattern is novel.
- **3+ FAIL:** the workflow itself drifted. Re-read voice.md before next invocation.

## Logging

Run-level logs go in `acceptance-log.md`. Pattern-level findings (e.g., "the skill consistently misses Check 3 on senior portfolios") get appended to `../../.planning/builds/portfolio-rx/research/PITFALLS.md` as new failure modes.
