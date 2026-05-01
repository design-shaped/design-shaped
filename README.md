# Design Shaped — plugin marketplace

> No roasting: just collaboration and constructive feedback.

A Claude Code plugin marketplace for designers. Async clones of the [Design Shaped](https://www.youtube.com/@designshaped/) Friday review stream — coaching tools shaped by Tim Gailey and Nate Bauer.

---

## What's in here

| Plugin | Status | What it does |
|--------|--------|--------------|
| [`portfolio-rx`](./plugins/portfolio-rx/README.md) | v0.1.0 (pre-acceptance) | Tim+Nate-flavored review for designer portfolios and resumes. |

More plugins to come — resume mock-interview as a standalone, Figma case-study reviewer, stream-mining quarterly refresh, and the Design Shaped reading list have all been scoped. They land here when they're built.

---

## Install

Add this marketplace to Claude Code, then install the plugin you want.

```bash
# In any Claude Code session:
/plugin marketplace add <github-url-tbd>

# Then:
/plugin install portfolio-rx@design-shaped
```

> The GitHub URL is TBD — Tim and Nate are choosing the org/account. Once published, the install command above is the canonical path.

To install **locally** (during dev or before the public push):

```bash
# Clone the marketplace repo
git clone <repo-url> ~/projects/design-shaped

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
├── plugins/
│   └── portfolio-rx/        # Plugin 1
│       ├── .claude-plugin/
│       │   └── plugin.json  # Plugin manifest
│       ├── README.md        # Plugin docs (humans)
│       ├── CLAUDE.md        # Plugin conventions (Claude)
│       └── skills/
│           └── portfolio-rx/
│               ├── SKILL.md
│               ├── references/
│               ├── workflows/
│               ├── qa/
│               ├── gotchas.md
│               └── mining-log.md  # gitignored — never published
├── LICENSE                  # MIT, Tim Gailey + Nate Bauer
├── README.md                # ← you are here
└── CLAUDE.md                # marketplace-level conventions
```

Each plugin is a self-contained directory under `plugins/`. Adding a new plugin = scaffold its directory, register it in `marketplace.json`, write its own README + CLAUDE.md.

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

Open a GitHub issue (URL TBD) with:
- A plugin run that produced bad output (with sanitized inputs if possible).
- A pattern you've seen on the Friday stream that we missed.

PRs welcome from designers who watch the stream and have evidence of patterns we haven't captured.

---

## Disclaimer

The plugins here are approximations built from publicly shared review patterns. **Tim and Nate did not personally review your work.** For a direct review, join the Friday stream: [https://www.youtube.com/@designshaped/](https://www.youtube.com/@designshaped/).

If you screenshot plugin output, please don't present it as a direct quote from Tim or Nate. Attribution that works: *"Portfolio Rx (a Tim+Nate-shaped Claude Code plugin) suggested..."* — never *"Tim said..."* or *"Nate told me..."*.

If we wouldn't say it on Friday stream with the reviewee in the call, we don't want it shared as if we did.
