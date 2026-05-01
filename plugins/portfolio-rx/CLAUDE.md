# CLAUDE.md — Portfolio Rx repo conventions

This is the public-facing Claude Code skill repo for **Portfolio Rx** — an async clone of the Friday-stream portfolio + resume review by Tim and Nate.

## Where the planning artifacts live

This repo is a build product. The planning artifacts (SPEC, REQUIREMENTS, ROADMAP, research, per-phase CONTEXT.md and PLAN.md files) live OUTSIDE this repo, in:

```
/Users/timothygailey/projects/design-shaped/.planning/builds/portfolio-rx/
```

Read those before making non-trivial changes. Especially:

- `SPEC.md` — vision, audience, locked decisions (D-01 through D-21)
- `REQUIREMENTS.md` — REQ-IDs, traceability matrix
- `ROADMAP.md` — phases, success criteria, dependencies
- `research/SUMMARY.md` — synthesized research findings driving the decisions
- `research/PITFALLS.md` — known failure modes; consult before changing privacy or voice copy

## Build conventions (load-bearing)

A few decisions matter enough to enforce here so they don't drift:

- **D-15: Skill `description:` ≤220 chars.** Long-tail triggers go in a `## Trigger Surface` block in SKILL.md body, not in the description. Run `~/.claude/skills/skill-audit/scripts/lint-skill.sh` before commit.
- **D-18: Build voice.md FIRST, SKILL.md body LAST.** Without voice.md as the writing register, every workflow drifts to generic LLM mush.
- **D-19: Frameworks-by-name.** Reviews never paraphrase a framework. They name it verbatim, apply it in one line, and cite the source. dmba's pattern is the model.
- **D-21: README is for humans browsing GitHub. SKILL.md is for Claude.** SKILL.md never references README. Do not pollute SKILL.md context with marketing copy.
- **D-17: `mining-log.md` is in `.gitignore`.** It maps mined patterns back to source transcripts so we can honor takedown requests. NEVER commit it.

## Privacy claims (non-negotiable)

The README's privacy section is locked verbatim from `research/PITFALLS.md` §2.1. Do NOT reword it to be more punchy. The exact wording is the trust signal — accuracy matters more than crispness here. If a reword is requested, route through Tim+Nate, not through Claude.

## Voice (load-bearing)

Once `references/voice.md` exists (Phase 1), every workflow output that reaches a user MUST cite it. The voice is:

- Direct, down-to-earth, actionable, objective
- **No roasting.** "No roasting: just collaboration and constructive feedback" is the verbatim brand line from `design-shaped-site/site/index.html`.
- No hedge words ("you might want to", "perhaps", "consider", "it seems")
- Every flagged bullet gets a concrete rewrite (VOICE-04)
- Frameworks named verbatim, not paraphrased (D-19)

## Phase status

Track in `.planning/builds/portfolio-rx/STATE.md`. As of writing: Phase 0 complete (this commit). Phases 1–5 to follow.
