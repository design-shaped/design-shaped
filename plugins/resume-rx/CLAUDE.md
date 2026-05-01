# CLAUDE.md — Resume Rx plugin conventions

This is the **resume-rx** plugin inside the [Design Shaped marketplace](../../README.md). Marketplace-level conventions live in [the top-level CLAUDE.md](../../CLAUDE.md). This file covers plugin-specific rules only.

## Plugin layout

```
plugins/resume-rx/
├── .claude-plugin/plugin.json    # Manifest
├── README.md                     # Plugin docs (humans)
├── CLAUDE.md                     # ← you are here
└── skills/resume-rx/             # The actual skill (auto-discovered)
    ├── SKILL.md                  # Routing + trigger surface + mode dispatch
    ├── references/               # voice, frameworks, heuristics, intake, common-flags, rubrics, role-families
    ├── workflows/                # 3 workflows: line-edit, brainstorm, draft-from-list
    └── gotchas.md                # G01..G14 — operational pitfalls + scope/limits doc
```

Planning artifacts live outside the repo at `/Users/timothygailey/projects/design-shaped/.planning/builds/resume-rx/` — SPEC.md, REQUIREMENTS.md, ROADMAP.md, per-phase CONTEXT.md and PLAN.md files. Read SPEC.md before making non-trivial content changes.

## Voice canon

Every workflow output that reaches a user MUST cite `skills/resume-rx/references/voice.md`. The voice is:

- **Direct, framework-named, no roasting.** *"No roasting: just collaboration and constructive feedback"* is the load-bearing brand line. The four-clause anti-roast test in voice.md §6 must pass before any output emits.
- **No hedge words.** *"You might want to,"* *"perhaps,"* *"consider,"* *"it would be helpful to"* — banned per voice.md §4 drop list.
- **Every flagged bullet gets a concrete rewrite.** A flag without a rewrite is a roast in disguise.
- **Frameworks named verbatim, not paraphrased** (D-20). The seven frameworks live in `references/frameworks.md`: STAR, CAR, XYZ, R-A-S, Scope-Impact-Metric, What/How/Why, Skim-test tiers. Cite by exact name.

## Load-bearing decisions

These don't drift. Cite by ID in commits and code review.

- **D-15-RR: Line-edit output format.** Per-bullet original + rewrite + 1-sentence rationale (side-by-side), plus top-of-doc 3-issue summary in `[Element]: [problem]. [cost]. [fix].` form. The side-by-side IS the anti-fabrication mechanism — never collapse to a clean rewrite without the original.
- **D-16-RR: No-fab-metrics — HARD rule.** Never invent metrics not in the source. Three-options ladder when metric is absent: probe in rationale → restructure to non-numeric outcome → `<!-- METRIC GAP -->` marker. Never an invented percentage.
- **D-17-RR: Banned AI-default verbs.** *Spearheaded, leveraged, synergized, catalyzed, orchestrated, championed, drove (no object), amplified (no metric)* never appear in any synthesized or rewritten bullet, even if the user used them in conversation. The full list lives in voice.md §11.1; rewrites must be at least as concrete as the original (voice.md §4 abstraction-regression guard).
- **D-21-RR: Write for the hiring design manager.** Modern ATS follows. No keyword-stuffing advice, no two-pass advice, no hidden-text tricks. Keywords are earned via honest bullets that name actual tools and methods used.
- **D-22: Trigger discipline.** resume-rx triggers must NOT collide with portfolio-rx. Bare *"review,"* *"feedback,"* *"critique"* are excluded — they over-trigger on unrelated UI work and collide with portfolio-rx's surface. Resume-rx anchors on *resume*, *bullet*, *achievement list*, *blank page*. The trigger battery (QA-01) runs with both plugins installed; collision scenarios are mandatory.
- **D-23: No numeric scores, grades, or meters.** No "resume score: 72/100," no "ATS-readiness: 4/5," no bullet-strength meter anywhere in any output. Resume.io / Rezi-style grading is the failure mode this rule prevents.
- **D-24: Portfolio-rx description tweak.** Phase 6 lands a minimal one-line scope-narrowing tweak in portfolio-rx's description fields (marketplace.json + plugin.json + SKILL.md frontmatter) to neutralize trigger collision. This is part of the resume-rx ship; it does NOT count as a portfolio-rx build.

## Trigger discipline (D-22)

resume-rx fires on resume-specific phrases listed in SKILL.md `## Trigger Surface`. The exclusion rule is binding: bare *review* / *feedback* / *critique* must NOT trigger this skill, because they over-trigger on unrelated UI work and collide with portfolio-rx. Anchor every example trigger phrase to a resume-specific noun (*resume*, *bullet*, *achievement list*, *blank page*, *role history*).

If a new trigger phrase is added in the future, validate it against both plugins' trigger surfaces in a fresh Claude Code session before commit. The QA-01 trigger battery (P7) runs with both plugins installed and includes ≥10 resume-shaped prompts and 4 anti-trigger prompts.

## Mode routing

`SKILL.md` is the dispatcher. It reads the input shape (via `references/intake.md`) and the user's phrasing, then dispatches to one of three workflows:

- `workflows/line-edit.md` — existing-draft input.
- `workflows/brainstorm.md` — blank-page input.
- `workflows/draft-from-list.md` — unstructured-list input.

MODE-05 explicit override syntax (*"use line-edit mode"* / *"/line-edit"* / etc.) is recognized in SKILL.md and forces the dispatch regardless of input shape. The dispatched workflow documents the override in its output header.

Workflows do NOT call each other. Cross-mode handoff (line-edit → brainstorm to surface more bullets, brainstorm → line-edit to tighten the synthesized draft) is mediated by single-line offers at the end of each workflow's output, and the user re-invokes — workflows are never pipelined silently.

## R-ID stability (D-14 / R01–R12)

`references/common-flags.md` defines the closed failure-mode taxonomy R01–R12. **R-IDs are append-only after ship.** Never renumber R01–R12; never repurpose an existing ID; never silently retire one. New patterns surfaced post-ship get appended (R13, R14, ...) — the existing IDs are stable references in every line-edit rationale and every workflow's flag list.

## Framework citation (D-20 closed set)

The seven frameworks in `references/frameworks.md` are the canonical set:

- **STAR** — Situation / Task / Action / Result. Summary or cover-letter scale only — never bullet scale on a one- or two-page resume.
- **CAR** — Context / Action / Result. One-clause context where it's genuinely doing work (NDA constraint, unusual team shape, regulated-industry surface).
- **XYZ** — Accomplished X by doing Y, resulting in Z. Honest hard-metric bullets only — never fabricate the X.
- **R-A-S** — Result / Action / Skill. Senior+staff bullets where leading with the result is honest.
- **Scope-Impact-Metric** — Senior+staff bullets where the headline signal is what was owned at the org level.
- **What/How/Why** — The corpus-load-bearing default scaffold (13/23 transcripts). Most bullets land in this shape.
- **Skim-test tiers** — 0-3s / 3-10s / 10-30s. Section-order diagnostic, not a per-bullet framework.

Cite by exact name verbatim. Never paraphrase. Per voice.md §12 self-check: at least 2 frameworks surface by name in every line-edit and draft-from-list output; at least 1 framework per synthesized brainstorm bullet.

## No fabrication (D-16-RR / D-21-RR / no-invented-anything)

Every claim cites a source. The discipline cascades:

- **No fabricated metrics** (D-16-RR). Numbers trace back to the user's input or carry a `<!-- METRIC GAP -->` marker.
- **No invented employers, dates, titles, or education.** If the source list / draft / brainstorm conversation didn't surface the role anchor or the degree, the section drops with a `<!-- ROLE GAP -->` or `<!-- SECTION GAP -->` marker — never a synthesized employer or fabricated degree.
- **No inferred Skills section.** If the source list never named tools, the Skills section drops with `<!-- SECTION GAP -->`. Inference at the section scale is fabrication at the section scale.
- **No invented `Tim says:` / `Nate says:` callouts.** Default to "we." Callouts are authored manually by Tim and Nate; never fabricated by the model.
- **No invented fifth role-family preset.** Hybrid roles route to the closest of the four; do not invent a fifth (gotchas.md G12).

## Acceptance gating

Per [marketplace-level CLAUDE.md](../../CLAUDE.md): resume-rx ships at v1.0.0 only after both Tim and Nate independently stamp `skills/resume-rx/qa/acceptance-log.md` (or wherever the plugin keeps its acceptance log). Until then, version stays at 0.x.y in `.claude-plugin/plugin.json` and the plugin README labels it pre-acceptance.

## Mining log

`mining-log.md` (gitignored at plugin root per D-17 / D-M2-07 pattern carried from portfolio-rx) maps mined patterns from the Design Shaped stream archive back to their source transcripts. Never commit. The marketplace `.gitignore` rule covers this; verify with `git check-ignore -v plugins/resume-rx/mining-log.md`.
