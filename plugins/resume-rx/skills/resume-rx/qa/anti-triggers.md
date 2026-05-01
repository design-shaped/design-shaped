---
title: Anti-trigger Battery
plugin: resume-rx
covers: QA-02
---

# Anti-trigger Battery — Resume Rx

This is the anti-trigger battery. These prompts MUST NOT load resume-rx. Run each in a **fresh Claude Code session** with both `resume-rx` AND `portfolio-rx` installed (D-22 collision discipline). 5/5 PASS is the QA-02 floor — any false positive is a trigger-discipline regression and must be addressed before ship. Prompt 1 specifically validates the D-24 portfolio-rx description tweak (anti-collision); prompt 5 validates the v1 cover-letter deferral.

## Prompts

### 1. Portfolio-only (catches D-24 anti-collision)

> "review my portfolio site"

- **Expected:** Does NOT load resume-rx. portfolio-rx loads instead.
- **Why:** Resume-rx must not poach portfolio review prompts. The D-24 portfolio-rx description tweak narrows portfolio-rx's scope wording and resume-rx's trigger surface (D-22) excludes bare *review* + *portfolio*. This prompt validates that both moves landed correctly.

### 2. Unrelated — programming task

> "help me write a Python script for data cleaning"

- **Expected:** Does NOT load resume-rx. Does NOT load portfolio-rx.
- **Why:** No resume-shaped noun anywhere. Anchor words (*resume*, *bullet*, *achievement list*, *blank page*) are absent. This is the "obviously unrelated" floor — failure here means the trigger surface is overfiring on bare verbs.

### 3. Generic feedback (ambiguous)

> "what do you think of this design?"

- **Expected:** Does NOT load resume-rx.
- **Why:** D-22 binds: bare *review* / *feedback* / *critique* must not trigger resume-rx. No resume noun, no bullet noun, no achievement-list noun, no blank-page signal. May or may not trigger portfolio-rx depending on context — the only requirement here is that resume-rx stays silent.

### 4. Design-but-not-resume

> "redesign my landing page hero"

- **Expected:** Does NOT load resume-rx. Does NOT load portfolio-rx.
- **Why:** Design work that's neither portfolio review nor resume writing. Resume-rx must not over-fire on the word *design* alone. Tests that the trigger surface is anchored to the artifact (resume) not the user's profession (designer).

### 5. Cover-letter (v2 deferred per SPEC)

> "help me write a cover letter"

- **Expected:** Does NOT load resume-rx. Does NOT load portfolio-rx.
- **Why:** Cover-letter generation is explicitly deferred per SPEC.md (Deferred Ideas) and gotchas.md scope-doc. Cover letters are a different content type with different conventions — neither plugin handles them in v1. If resume-rx fires here, it's a scope leak.

## Test Results

| # | Prompt | Loaded resume-rx? | Loaded portfolio-rx? | PASS / FAIL | Notes |
|---|---|---|---|---|---|
| 1 | review my portfolio site | No (target) | Yes (target) | __ | __ |
| 2 | help me write a Python script | No (target) | No (target) | __ | __ |
| 3 | what do you think of this design? | No (target) | n/a | __ | __ |
| 4 | redesign my landing page hero | No (target) | No (target) | __ | __ |
| 5 | help me write a cover letter | No (target) | No (target) | __ | __ |

**Total PASS: __ / 5** (QA-02 floor: 5/5)

**Run by:** __________
**Date:** __________
**CC version:** __________
**Plugins installed:** [ ] resume-rx  [ ] portfolio-rx

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
