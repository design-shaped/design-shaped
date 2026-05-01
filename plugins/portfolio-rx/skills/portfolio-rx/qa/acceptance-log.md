# Acceptance log — Portfolio Rx

Tim and Nate independently run the skill on real materials and log their verdict. Two stamps required for v1.0.0.

## How to log an acceptance run

1. Run the skill on a real portfolio + resume + (optionally) a mock interview.
2. Run the 6-check `detection-checklist.md` against the output.
3. Fill in a new entry below with date, materials reviewed, career stage, verdict, and any specific notes.
4. Verdict options: **stamp** (good to ship), **minor revisions** (fixable in <1 hour), **major revisions** (workflow or content needs a meaningful pass).

When both Tim and Nate have stamped, the skill is v1.0.0-ready. Bump the version in README, set the "Last reviewed by Tim and Nate" date, and announce on a Friday stream.

---

## Tim's runs

### Run 1 — TBD

- **Date:** TBD
- **Materials reviewed:** TBD
- **Career stage applied:** TBD
- **Verdict:** TBD
- **Detection checklist results:** TBD (paste 6-line summary)
- **Specific notes:**
  - TBD
- **Rerun required:** TBD

---

## Nate's runs

### Run 1 — TBD

- **Date:** TBD
- **Materials reviewed:** TBD
- **Career stage applied:** TBD
- **Verdict:** TBD
- **Detection checklist results:** TBD (paste 6-line summary)
- **Specific notes:**
  - TBD
- **Rerun required:** TBD

---

## Trigger battery — pre-launch dry run

Run each of these phrases against the skill in a fresh Claude Code session. Each should fire the skill (or fall through to "what would you like to review?" if no inputs).

| # | Phrase | Skill fires? | Notes |
|---|--------|--------------|-------|
| 1 | "review my portfolio" | TBD | |
| 2 | "rip my resume" | TBD | |
| 3 | "Friday review please" | TBD | |
| 4 | "is my portfolio any good" | TBD | |
| 5 | "what would you ask about this?" | TBD | |
| 6 | "Portfolio Rx mock interview" | TBD | |
| 7 | "design portfolio review" | TBD | |
| 8 | "resume feedback for senior promotion" | TBD | |
| 9 | "case study review" | TBD | |
| 10 | "applying for a design role, can you review?" | TBD | |

**Anti-triggers (these should NOT fire the skill):**

| Phrase | Should fire? | Actually fires? |
|--------|--------------|-----------------|
| "review this code" | No | TBD |
| "review this design" *(not job-search context)* | No | TBD |
| "general feedback" | No | TBD |
| "give me a critique" *(not anchored to portfolio)* | No | TBD |

Goal: 10/10 pass on the trigger battery, 0/4 false positives on the anti-triggers.

---

## Final pre-launch checklist

- [ ] All 5 workflow output templates have the verbatim D-16 footer
- [ ] Privacy section in README is the verbatim PITFALLS §2.1 wording
- [ ] voice.md line 3 is the brand line verbatim
- [ ] SKILL.md description ≤220 chars (currently: 202)
- [ ] All P0–P5 commits on `main`
- [ ] GitHub remote pushed to public repo (Tim+Nate decide org)
- [ ] Tim acceptance run logged (above)
- [ ] Nate acceptance run logged (above)
- [ ] Trigger battery 10/10 pass
- [ ] Anti-trigger battery 0/4 false positives
- [ ] README "Last reviewed by Tim and Nate" date stamped
- [ ] README version bumped 0.1.0 → 1.0.0
- [ ] Friday-stream demo + install link in show notes prepared

When every item is checked, the skill is ready for the live launch moment.
