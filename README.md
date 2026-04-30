# Portfolio Rx

> No roasting: just collaboration and constructive feedback.

A public Claude Code skill that gives early-career and promotion-track designers a Tim+Nate-flavored portfolio and resume review when they can't make Friday's livestream. An async clone of the live show.

---

## Privacy model

Portfolio Rx runs inside Claude Code on your machine. There is no Portfolio Rx server, no telemetry, and no data is ever sent to Tim or Nate.

Because this is a Claude Code skill, the materials you share with it (resume text, portfolio page contents, Figma frames, screenshots) are sent to Anthropic's Claude API as part of normal Claude Code operation — the same as any other prompt or file you'd share with Claude. Anthropic's data handling is governed by their [usage policies](https://www.anthropic.com/legal/aup) and their [commercial terms](https://www.anthropic.com/legal/commercial-terms) (or consumer terms, depending on your account type). We don't add anything on top of that.

**What this means in practice:**

- We (Tim and Nate) never see your materials.
- There's no Portfolio Rx database, account, or cloud component.
- Anthropic processes the prompts the same way they process any Claude Code session.
- If you're not comfortable feeding sensitive materials to a hosted LLM, this skill (and Claude Code generally) is not the right tool. Friday streams remain an option for live review.

**Portfolio URLs:** When you share a portfolio URL, the skill fetches the page content via Claude Code's WebFetch tool. This makes a normal HTTP request to your portfolio's host (Vercel, Notion, your personal domain, etc.), which will appear in their logs the same as any visitor. The fetched content is then passed to the Claude API for analysis.

**Figma files:** Reading a Figma file uses the official Figma MCP server, which authenticates against your Figma account and fetches file contents through Figma's API. Your file data is governed by Figma's terms of service. Claude (via Anthropic's API) then receives the design context for review.

---

## Who it's for

*TBD — written in Phase 4. See `.planning/builds/portfolio-rx/SPEC.md#who-its-for`.*

## What it does

*TBD — written in Phase 4. See `.planning/builds/portfolio-rx/SPEC.md#core-requirements`.*

## Install

*TBD — written in Phase 4 once SKILL.md triggers exist (Phase 3).*

## How to invoke

*TBD — written in Phase 4 once SKILL.md routing tables exist (Phase 3).*

## Disclaimer

*TBD — written in Phase 4. The mandatory output footer (D-16) makes the disclaimer concrete; this section explains it.*

---

## Status

This repo is in active build (Phase 0 of 5 complete). It is not yet usable as a Claude Code skill — the routing logic and content live in later phases. Track progress in `../design-shaped/.planning/builds/portfolio-rx/ROADMAP.md`.
