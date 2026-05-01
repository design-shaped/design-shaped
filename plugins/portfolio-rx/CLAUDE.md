# CLAUDE.md — Portfolio Rx plugin conventions

This is the **portfolio-rx** plugin inside the [Design Shaped marketplace](../../README.md). Marketplace-level conventions live in [the top-level CLAUDE.md](../../CLAUDE.md). This file covers plugin-specific rules only.

## Plugin layout

```
plugins/portfolio-rx/
├── .claude-plugin/plugin.json    # Manifest
├── README.md                     # Plugin docs (humans)
├── CLAUDE.md                     # ← you are here
└── skills/portfolio-rx/          # The actual skill (auto-discovered)
    ├── SKILL.md                  # Routing + trigger surface
    ├── references/               # voice.md, frameworks.md, rubrics, flags, heuristics
    ├── workflows/                # 5 workflows: resume, portfolio, combined, mock-list, mock-walk
    ├── qa/                       # acceptance-log, detection-checklist
    ├── gotchas.md                # User-facing scope/limits doc
    └── mining-log.md             # gitignored — never published
```

## Where the planning artifacts live

Outside this repo, at:

```
/Users/timothygailey/projects/design-shaped/.planning/builds/portfolio-rx/
```

Read these before making non-trivial changes:

- `SPEC.md` — original M1 vision, audience, locked decisions D-01..D-21
- `MILESTONE-02-SPEC.md` — M2 stream-mining decisions D-M2-01..D-M2-10
- `MILESTONE-03-SPEC.md` — M3 plugin restructure decisions D-M3-01..D-M3-15
- `REQUIREMENTS.md` — REQ-IDs, traceability matrix
- `ROADMAP.md` — phases, success criteria, dependencies
- `research/STREAM_MINING.md` — synthesis of the @designshaped Friday-stream archive (drives content choices)
- `research/PITFALLS.md` — known failure modes; consult before changing privacy or voice copy

## Load-bearing decisions

These don't drift:

- **D-15: Skill `description:` ≤220 chars.** Long-tail triggers go in a `## Trigger Surface` block in `skills/portfolio-rx/SKILL.md` body, not in the description.
- **D-16: Output footer.** Every review the skill produces ends with the verbatim disclaimer footer naming the YouTube channel. The footer is the trust mechanism. Workflows enforce this via their output templates.
- **D-17: `mining-log.md` is in `.gitignore`.** Maps mined patterns back to source transcripts (takedown traceability). Never commit. The marketplace gitignore at repo root has the rule; verify with `git check-ignore -v plugins/portfolio-rx/skills/portfolio-rx/mining-log.md`.
- **D-18: Build voice.md FIRST, SKILL.md body LAST.** Without `references/voice.md` as the writing register, every workflow drifts to generic LLM mush.
- **D-19: Frameworks-by-name.** Reviews never paraphrase a framework. They name it verbatim, apply it in one line, and cite the source. The 25 frameworks in `references/frameworks.md` are the canonical set.
- **D-21: README is for humans browsing GitHub. SKILL.md is for Claude.** SKILL.md never references README. Do not pollute SKILL.md context with marketing copy.

## Privacy claims (non-negotiable)

The plugin README's privacy section is locked verbatim from `.planning/builds/portfolio-rx/research/PITFALLS.md` §2.1. Do NOT reword it to be more punchy. The exact wording is the trust signal — accuracy matters more than crispness. If a reword is requested, route through Tim+Nate.

## Voice (load-bearing)

Every workflow output that reaches a user MUST cite `references/voice.md`. The voice is:

- Direct, down-to-earth, actionable, objective.
- **No roasting.** "No roasting: just collaboration and constructive feedback" is the verbatim brand line.
- No hedge words ("you might want to", "perhaps", "consider", "it seems").
- Every flagged bullet gets a concrete rewrite.
- Frameworks named verbatim, not paraphrased (D-19).

## Acceptance gating

Per [marketplace-level CLAUDE.md](../../CLAUDE.md) and D-M3-13: portfolio-rx ships at v1.0.0 only after both Tim and Nate independently stamp `skills/portfolio-rx/qa/acceptance-log.md`. Until then, version stays at 0.x.y in `.claude-plugin/plugin.json` and the plugin README labels it pre-acceptance.

The acceptance-log path used to live at `qa/acceptance-log.md` relative to the skill repo root. Post-M3 it's at `plugins/portfolio-rx/skills/portfolio-rx/qa/acceptance-log.md`. References inside the skill (workflows, SKILL.md) resolve correctly because the relative path from a workflow file to a sibling qa/ directory is unchanged.

## When plugin-form behavior diverges from standalone-form

The skill was developed and tested as a standalone Claude Code skill at `~/.claude/skills/portfolio-rx`. M3 wraps it in plugin form. If you discover the plugin form does anything the standalone form didn't (different triggers fire, different file resolution, different output), surface as a plugin-form regression — don't silently absorb. The success metric per `MILESTONE-03-SPEC.md` is: zero behavioral regression vs the standalone form.

## Phase status

Track in `.planning/builds/portfolio-rx/STATE.md`. M1 (P0–P5) and M2 (P6–P9) complete. M3 (P10–P12) lands the plugin restructure. v1.0.0 tag gated on Tim+Nate acceptance.
