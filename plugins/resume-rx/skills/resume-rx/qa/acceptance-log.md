---
title: Acceptance Log
plugin: resume-rx
covers: QA-04, QA-05, QA-06, QA-07
---

# Acceptance Log — Resume Rx

## What this file is

This is the append-only log of plugin-form acceptance stamps for resume-rx. Both **Tim** and **Nate** must independently stamp PASS after running the plugin against a real designer resume. Two PASS stamps are the gate to the v1.0.0 version stamp (QA-06) and the `v1.0.0` git tag (QA-07). FAIL stamps surface specific gaps and route the build back to the relevant earlier phase before re-running acceptance. This log is append-only — older entries stay; new entries land underneath.

## Pre-acceptance checklist

Each reviewer completes this **before** stamping. All three boxes must be checked.

- [ ] **Plugin installed.** Run `/plugin install resume-rx@design-shaped` in a fresh Claude Code session and confirm install succeeded.
- [ ] **Trigger battery passed.** Run `qa/trigger-battery.md` end-to-end in a fresh CC session with both `resume-rx` AND `portfolio-rx` installed. Score ≥10/12 PASS (QA-01 floor).
- [ ] **Anti-trigger battery passed.** Run `qa/anti-triggers.md` end-to-end in the same session. Score 5/5 PASS (QA-02 floor — any false positive blocks acceptance).

## Acceptance protocol

Run the plugin against a real designer resume of your own choosing. Exercise the four modes below. Confirm the output discipline rubric in the next section before stamping.

1. **Line-edit mode.** Submit a paragraph of an existing resume draft, or a full draft. Confirm the workflow returns per-bullet original + rewrite + 1-sentence rationale, plus a top-of-doc 3-issue summary (D-15-RR side-by-side format).
2. **Brainstorm mode.** Start from blank. Confirm the workflow probes scope/impact conversationally, then synthesizes ≥1 draft bullet from your answers.
3. **Draft-from-list mode.** Provide an unstructured list of achievements. Confirm the workflow returns a 4-section markdown resume (Summary / Experience / Skills / Education) with `<!-- GAP -->` markers where source data was missing.
4. **Footer verification.** Confirm every output (line-edit, brainstorm, draft-from-list) ends with the verbatim D-16-RR Tim+Nate footer (OUT-04). Missing or edited footer is an automatic FAIL.

## Rubric — 6 criteria, each PASS or FAIL

Score each criterion independently. All 6 must PASS for an overall PASS verdict.

1. **Voice register matches Friday-stream Tim+Nate.** Direct, framework-named, no roasting, no AI-cheerleader puffery, no hedge words. Per `references/voice.md` §4 (drop list) and §6 (anti-roast test).
2. **No fabricated metrics (D-16-RR).** Every number on a synthesized or rewritten bullet traces back to the user's input. Three-options ladder fired when metric was absent (probe → restructure → `<!-- METRIC GAP -->`). Never an invented percentage.
3. **No invented frameworks (D-20 closed set).** Workflow names frameworks verbatim from the seven canonical names only: **STAR, CAR, XYZ, R-A-S, Scope-Impact-Metric, What/How/Why, Skim-test tiers**. No paraphrasing, no invented eighth framework.
4. **R-IDs match `references/common-flags.md` numbering (LD-P2-05 stability).** Every line-edit flag cites an exact R-ID from R01–R12. R-IDs are append-only after ship — no renumbering, no repurposing, no silent retirement of an existing ID.
5. **Side-by-side format on every line-edit flag (D-15-RR).** Original + Rewrite + Rationale, three labeled rows or columns per bullet. The side-by-side IS the anti-fabrication mechanism — a clean rewrite without the original is a FAIL.
6. **Verbatim D-16-RR footer on every output (OUT-04).** Footer text matches `SKILL.md` line 122 verbatim (URL form, not the `[Friday stream link]` placeholder form). Missing footer or edited footer is a FAIL.

## Stamp slots

### Tim's stamp

- **Date:** __________
- **Resume tested:** __________
- **Modes invoked:** [ ] line-edit  [ ] brainstorm  [ ] draft-from-list
- **Trigger battery:** __ / 12 PASS
- **Anti-trigger battery:** __ / 5 PASS
- **Rubric:** __ / 6 PASS
- **Verdict:** PASS | FAIL
- **Notes:** __________
- **Signoff:** __________

### Nate's stamp

- **Date:** __________
- **Resume tested:** __________
- **Modes invoked:** [ ] line-edit  [ ] brainstorm  [ ] draft-from-list
- **Trigger battery:** __ / 12 PASS
- **Anti-trigger battery:** __ / 5 PASS
- **Rubric:** __ / 6 PASS
- **Verdict:** PASS | FAIL
- **Notes:** __________
- **Signoff:** __________

## Post-acceptance steps — Tim's manual checklist

Run only when **both** Tim's stamp and Nate's stamp record `Verdict: PASS`. These steps are the human gate that auto mode cannot execute (LD-P7-05, LD-P7-06).

### QA-06 — Version stamp (0.1.0 → 1.0.0)

Bump the version in all three locations and commit:

- [ ] `portfolio-rx/plugins/resume-rx/.claude-plugin/plugin.json` — bump `"version"` from `0.1.0` to `1.0.0`.
- [ ] `portfolio-rx/.claude-plugin/marketplace.json` — bump the resume-rx plugin entry's `"version"` from `0.1.0` to `1.0.0`.
- [ ] `portfolio-rx/plugins/resume-rx/README.md` — update version reference if the README mentions `0.1.0` or carries a "pre-acceptance" label.

Commit message:

```
chore(resume-rx): stamp v1.0.0 (acceptance Tim + Nate)
```

### QA-07 — Git tag

After the QA-06 commit lands on the working branch:

```
git tag v1.0.0 -m "Resume Rx v1.0.0 (acceptance Tim + Nate)"
git push --tags
```

### Post-tag

- [ ] Update `.planning/builds/resume-rx/STATE.md` to `v1.0.0 ship-ready`.
- [ ] Announce on the next Friday stream with install link.

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
