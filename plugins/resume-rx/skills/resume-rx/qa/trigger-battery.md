---
title: Trigger Battery
plugin: resume-rx
covers: QA-01
---

# Trigger Battery — Resume Rx

This is the trigger battery for resume-rx. Run each prompt in a **fresh Claude Code session** with both `resume-rx` AND `portfolio-rx` installed (D-22 collision discipline). Expected behavior is that resume-rx SKILL.md loads — not portfolio-rx, not any other skill, not no-skill. ≥10/12 PASS is the QA-01 floor; 12/12 is the target. Score each prompt PASS or FAIL and log the run at the bottom.

## Prompts

### 1. Explicit invocation

> "review my resume"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 2. Direct ask — line-edit territory

> "help me fix my resume bullets"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 3. Mode-specific — line-edit (tighten phrasing)

> "tighten the bullets in this resume"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 4. Mode-specific — line-edit (edit a draft)

> "edit my resume draft"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 5. Mode-specific — brainstorm (blank page)

> "I'm staring at a blank page for my resume — help me brainstorm"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 6. Mode-specific — brainstorm (stuck)

> "I don't know what to write for my resume"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 7. Mode-specific — draft-from-list (turn list)

> "turn this list of accomplishments into a resume"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 8. Mode-specific — draft-from-list (structure)

> "structure these achievements"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 9. Input-format-specific — LinkedIn URL

> "here's my LinkedIn URL — draft me a resume"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 10. Input-format-specific — Notion notes

> "here's my Notion notes about jobs — turn into resume"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 11. Seniority-specific — senior

> "senior product designer resume help"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

### 12. Seniority-specific — junior

> "junior designer resume review"

- **Expected:** Loads resume-rx
- **Anti-expected:** Does not load portfolio-rx, does not load any other skill

## Test Results

| # | Prompt (short) | PASS / FAIL | Skill that loaded (if not resume-rx) | Notes |
|---|---|---|---|---|
| 1 | review my resume | __ | __ | __ |
| 2 | help me fix my resume bullets | __ | __ | __ |
| 3 | tighten the bullets in this resume | __ | __ | __ |
| 4 | edit my resume draft | __ | __ | __ |
| 5 | I'm staring at a blank page for my resume | __ | __ | __ |
| 6 | I don't know what to write for my resume | __ | __ | __ |
| 7 | turn this list of accomplishments into a resume | __ | __ | __ |
| 8 | structure these achievements | __ | __ | __ |
| 9 | here's my LinkedIn URL — draft me a resume | __ | __ | __ |
| 10 | here's my Notion notes — turn into resume | __ | __ | __ |
| 11 | senior product designer resume help | __ | __ | __ |
| 12 | junior designer resume review | __ | __ | __ |

**Total PASS: __ / 12** (QA-01 floor: ≥10)

**Run by:** __________
**Date:** __________
**CC version:** __________
**Plugins installed:** [ ] resume-rx  [ ] portfolio-rx

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
