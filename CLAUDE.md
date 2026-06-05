# CLAUDE.md — Design Shaped marketplace conventions

This is the **Design Shaped** Claude Code plugin marketplace. It hosts plugins co-authored by Tim Gailey and Nate Bauer, shaped by their Friday review stream.

## Layout

```
design-shaped/
├── .claude-plugin/marketplace.json   # Marketplace catalog
├── plugins/<plugin-name>/            # One subdirectory per plugin
│   ├── .claude-plugin/plugin.json    # Plugin manifest
│   ├── README.md                     # Plugin docs (humans)
│   ├── CLAUDE.md                     # Plugin-level conventions (Claude)
│   └── skills/<skill-name>/SKILL.md  # The actual skill (auto-discovered)
├── LICENSE                           # MIT, top-level
├── README.md                         # Marketplace overview
└── CLAUDE.md                         # ← you are here
```

Plugin-level `CLAUDE.md` files cover plugin-specific conventions (voice, content rules, framework citations). This top-level file covers marketplace-level concerns only.

## Where the planning artifacts live

The build artifacts (SPECs, REQUIREMENTS, ROADMAPs, research, per-phase CONTEXT.md and PLAN.md files) live OUTSIDE this repo, in the maintainers' local planning workspace:

```
<local projects dir>/design-shaped/.planning/builds/<plugin-name>/
```

For portfolio-rx specifically:

```
.planning/builds/portfolio-rx/
├── SPEC.md                  # Original M1 vision + decisions D-01..D-21
├── MILESTONE-02-SPEC.md     # M2 stream-mining decisions D-M2-01..D-M2-10
├── MILESTONE-03-SPEC.md     # M3 plugin restructure decisions D-M3-01..D-M3-15
├── MILESTONE-03-ROADMAP.md
├── REQUIREMENTS.md
├── ROADMAP.md
├── research/                # Stream transcripts, mining buckets, synthesis
└── phases/                  # P0..P12 per-phase artifacts
```

Read the relevant SPECs before making non-trivial changes to any plugin.

## Adding a new plugin

1. Scope it: write `MILESTONE-NN-SPEC.md` and `MILESTONE-NN-ROADMAP.md` under `.planning/builds/<plugin-name>/`.
2. Scaffold the directory: `plugins/<plugin-name>/{.claude-plugin/plugin.json, README.md, CLAUDE.md, skills/<skill-name>/SKILL.md}`.
3. Register in `.claude-plugin/marketplace.json` under `plugins[]`.
4. Each plugin gets its own SPEC, its own acceptance log under its `qa/` directory, its own version line.
5. License is MIT, owners are Tim Gailey and Nate Bauer (unless explicitly stated otherwise per plugin).

## Manifest schemas

Per [code.claude.com/docs/en/plugins-reference](https://code.claude.com/docs/en/plugins-reference):

- `marketplace.json` minimum fields: `name`, `owner.name`, `plugins[]` (each with `name` + `source`).
- `plugin.json` minimum fields: `name`. Optional but used in this marketplace: `version`, `description`, `author`, `license`, `homepage`, `keywords`.
- Skills auto-discovered from `skills/<skill-name>/SKILL.md` — no `skills` field required in `plugin.json` if you use the convention.

## Versioning

- Semver per plugin in its `plugin.json`. Bump on user-visible behavior changes.
- Marketplace itself is unversioned — plugins version independently.
- The marketplace catalog (`marketplace.json`) duplicates each plugin's `version` so the manager UI can show it without reading every plugin manifest.
- Pre-acceptance plugins ship at `0.x.y`. Post-acceptance + Tim+Nate stamp = `1.0.0`.

## License

MIT. Single LICENSE at marketplace root covers everything inside. Per-plugin LICENSE duplication is not added — if a future plugin needs different licensing, surface that decision before merging it.

## Privacy

The marketplace and plugins do not run a server. All data flows through standard Claude Code → Anthropic API channels. Per-plugin privacy notes (URL fetches, MCP server access, etc.) live in each plugin's README. The portfolio-rx plugin in particular fetches portfolio URLs via WebFetch and reads Figma files via the Figma MCP server — see its README for specifics.

## Acceptance gating

Plugins ship at v1.0.0 only after Tim and Nate independently stamp the acceptance log under `plugins/<plugin-name>/skills/<skill-name>/qa/acceptance-log.md` (or wherever the plugin keeps its acceptance log). Plugin-form acceptance verifies that:

1. Triggers fire as expected (per the plugin's trigger battery).
2. Output passes the plugin's detection-checklist.
3. Behavior under `/plugin install` is identical to standalone-form testing (if the plugin had a standalone-form precursor).

Until both stamps land, the plugin stays at 0.x.y and the README labels it pre-acceptance.

## Cross-references

- Plugin-specific conventions live in each plugin's `plugins/<plugin-name>/CLAUDE.md` — read those before making content changes inside a plugin.
- For portfolio-rx specifically, the load-bearing decisions are D-15 (description ≤220 chars), D-16 (output footer), D-17 (mining-log.md gitignored), D-18 (voice first), D-19 (frameworks-by-name), D-21 (README is humans, SKILL.md is Claude). See `plugins/portfolio-rx/CLAUDE.md`.
