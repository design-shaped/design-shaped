# Design Shaped — plugin marketplace

> No roasting: just collaboration and constructive feedback.

A Claude Code plugin marketplace for designers. Async clones of the [Design Shaped](https://www.youtube.com/@designshaped/) Friday review stream — coaching tools shaped by Tim Gailey and Nate Bauer.

---

## What's in here

| Plugin | Status | What it does |
|--------|--------|--------------|
| [`portfolio-rx`](./plugins/portfolio-rx/README.md) | v0.2.0 · pre-acceptance | Review designer portfolios + Figma case studies in the Friday-stream voice — direct, framework-named, no roasting. |
| [`resume-rx`](./plugins/resume-rx/README.md) | v0.1.0 · pre-acceptance | Resume writing + line-editing in the Design Shaped voice. Junior to staff designers. |
| `get-stuff-done` | external | Structured build pipeline — interview → spec → roadmap → plan/execute → verify. Sourced from [`tim-gsd`](https://github.com/artisticmedic/tim-gsd). |

**Pre-acceptance:** Tim+Nate are still refining patterns before stamping any plugin v1.0.0. Also scoped but not yet built: a Figma case-study reviewer, a stream-mining quarterly refresh, and the Design Shaped reading list.

---

## Install

Add this marketplace to Claude Code, then install the plugin you want.

```bash
# In any Claude Code session:
/plugin marketplace add design-shaped/design-shaped
/plugin install portfolio-rx@design-shaped   # portfolio + Figma case-study review
/plugin install resume-rx@design-shaped       # resume writing + line-edit
```

> The marketplace repo is currently private (pre-acceptance). Collaborators added to the `design-shaped` GitHub org can install via the command above. After Tim+Nate stamp acceptance, the repo flips public and anyone can install.

To install **locally** during plugin development (skip GitHub round-trip):

```bash
git clone https://github.com/design-shaped/design-shaped ~/projects/design-shaped

# In Claude Code:
/plugin marketplace add ~/projects/design-shaped
/plugin install portfolio-rx@design-shaped
```

For per-plugin install verification (does the trigger fire? does the review look right?), see each plugin's README.

---

## Privacy model (marketplace level)

Plugins in this marketplace run inside Claude Code on your machine. There is no Design Shaped server, no telemetry, and nothing is sent back to Tim or Nate.

Each plugin is a Claude Code skill — the materials you share with it are sent to Anthropic's Claude API as part of normal Claude Code operation, the same as any other Claude Code prompt. Anthropic's data handling is governed by their [usage policies](https://www.anthropic.com/legal/aup) and their commercial or consumer terms (depending on your account type).

Per-plugin privacy notes (e.g. portfolio-rx fetching portfolio URLs via WebFetch, or reading Figma files via the Figma MCP server) live in each plugin's README.

---

## How this marketplace is organized

```
design-shaped/
├── .claude-plugin/
│   └── marketplace.json     # Catalog (lists portfolio-rx today, more later)
├── plugins/                 # local plugins — one self-contained dir each
│   ├── portfolio-rx/        # v0.2.0
│   │   ├── .claude-plugin/
│   │   │   └── plugin.json  # Plugin manifest
│   │   ├── README.md        # Plugin docs (humans)
│   │   ├── CLAUDE.md        # Plugin conventions (Claude)
│   │   └── skills/portfolio-rx/
│   │       ├── SKILL.md
│   │       ├── references/  workflows/  qa/
│   │       ├── gotchas.md
│   │       └── mining-log.md  # gitignored — never published
│   └── resume-rx/           # v0.1.0 — same shape
├── LICENSE                  # MIT, Tim Gailey + Nate Bauer
├── README.md                # ← you are here
└── CLAUDE.md                # marketplace-level conventions
```

`get-stuff-done` is an **external** source (`artisticmedic/tim-gsd`) — registered in `marketplace.json` but not vendored as a directory here.

Each local plugin is a self-contained directory under `plugins/`. Adding a new plugin = scaffold its directory, register it in `marketplace.json`, write its own README + CLAUDE.md.

---

## Authors

- **Tim Gailey** — co-host, Design Shaped Friday review stream.
- **Nate Bauer** ([nabauer.com](https://nabauer.com/articles)) — co-host, Design Shaped Friday review stream.

The plugins here are the joint Friday-review voice. Both authors review pattern updates before they ship.

---

## License

MIT. See [LICENSE](./LICENSE). One license covers the marketplace and all plugins inside.

---

## Issues / contributions

Open a [GitHub issue](https://github.com/design-shaped/design-shaped/issues) with:
- A plugin run that produced bad output (with sanitized inputs if possible).
- A pattern you've seen on the Friday stream that we missed.

PRs welcome from designers who watch the stream and have evidence of patterns we haven't captured.

---

## Disclaimer

The plugins here are approximations built from publicly shared review patterns. **Tim and Nate did not personally review your work.** For a direct review, join the Friday stream: [https://www.youtube.com/@designshaped/](https://www.youtube.com/@designshaped/).

If you screenshot plugin output, please don't present it as a direct quote from Tim or Nate. Attribution that works: *"Portfolio Rx (a Tim+Nate-shaped Claude Code plugin) suggested..."* — never *"Tim said..."* or *"Nate told me..."*.

If we wouldn't say it on Friday stream with the reviewee in the call, we don't want it shared as if we did.
