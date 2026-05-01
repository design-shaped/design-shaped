# Portfolio Rx

> No roasting: just collaboration and constructive feedback.

A public Claude Code skill that gives early-career and promotion-track designers a Tim+Nate-flavored portfolio and resume review when they can't make Friday's livestream. An async clone of the [Design Shaped](https://www.youtube.com/@designshaped/) live show.

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

Designers building or upgrading a portfolio + resume for a US-shaped job market. Specifically:

- **Bootcamp grads / 0 yrs experience** — building a first portfolio.
- **Career switchers** — pivoting from dev, marketing, research, ops, education, etc. into design.
- **0–2 yrs experience** — first or second design job, leveling up to mid-level.
- **Self-taught designers** — no formal program, often the hardest portfolio to position.
- **HCI Masters grads** and **UX students** on track for industry roles.
- **Mid → Senior promotion candidates** — a different rubric branch (diagnostic, not prescriptive).

Job-search contexts the skill handles:
- Building a first portfolio (no specific role target yet)
- Actively applying — getting silence or rejections, need to fix
- Got interviews but didn't convert (case-study walkthrough flopped)
- Re-entering after a gap (caretaking, layoff, burnout, sabbatical)
- Promotion-hunting (mid → sr)

The rubric is shaped for US tech hiring conventions. Storytelling norms differ globally — see `gotchas.md` for what the skill does and doesn't translate.

**Roles targeted:** Product designer (generalist), UX designer, UI / visual designer.

**NOT for:** Graphic designers, photographers, illustrators, code/engineering portfolios. Different conventions, different rubrics. See `gotchas.md`.

---

## What it does

Portfolio Rx is an async clone of the Friday review stream. You drop in your materials, the skill produces a Tim+Nate-flavored review.

**Five input types:**
- Resume PDF
- Portfolio URL (Vercel, Notion, Read.cv, personal domain, etc.)
- Figma file URL or fileKey (case study or portfolio in Figma)
- Pasted text (resume bullets, case study draft, cover letter)
- Screenshots (one-page docs, design frames, portfolio pages)

**Four review modes:**
- **Resume review** — Top-3 fixes, hiring-manager skim test, bullet-level rewrites.
- **Portfolio review** — Top-3 fixes, body-of-work coherence read, per-case-study breakdown with named frameworks, visual-craft assessment scaled to your role.
- **Combined review** — when you supply both, the skill produces ONE prioritized fix list spanning both, plus an explicit resume↔portfolio coherence check (the distinguishing feature — "do the bullets and case studies tell the same story?").
- **Mock interview** — list mode produces 8–12 questions Tim+Nate would actually ask of YOUR specific work; walkthrough mode role-plays a one-question-at-a-time conversation in joint Tim+Nate voice.

**Voice:** direct, framework-named, no roasting. The skill cites 25 named frameworks — 12 from [Nate Bauer's](https://nabauer.com/articles) published writing plus 13 mined from the @designshaped Friday-stream archive — by name and applies them to your specific work. The brand line is the load-bearing rule: *no roasting, just collaboration and constructive feedback.*

**Junior vs. senior modes:** the skill branches on career stage. Junior gets a prescriptive rubric (junior portfolios fail in repeating ways). Senior gets a diagnostic rubric (extract your thesis, grade against that — senior portfolios fail individually).

**The mandatory output footer:** every review ends with a non-removable disclaimer making clear the output is an approximation, not Tim or Nate themselves. See the Disclaimer section below.

---

## Install

```bash
git clone https://github.com/[USER]/portfolio-rx.git ~/.claude/skills/portfolio-rx
```

> **GitHub URL:** TBD. Tim+Nate's account / org is being decided. The clone destination is `~/.claude/skills/portfolio-rx/` regardless.

**Verify:** open Claude Code in any directory and type `review my portfolio` (or any phrase from the [How to invoke](#how-to-invoke) section). The skill should fire and ask you for inputs.

If the skill doesn't trigger, check that:
- The repo cloned to exactly `~/.claude/skills/portfolio-rx/` (not a nested folder).
- `~/.claude/skills/portfolio-rx/SKILL.md` exists with valid YAML frontmatter.
- You're on a recent Claude Code build that supports user-level skills.

---

## How to invoke

The skill auto-fires on natural-speech triggers. No slash command required.

Examples:
- "Review my portfolio"
- "Resume feedback"
- "Rip my resume"
- "Friday review"
- "Portfolio Rx"
- "Review my case study"
- "Mock interview"
- "What would you ask me about this work?"
- "Is my portfolio any good?"

You can also drop materials directly:
- Drag a resume PDF into the chat and say "review this"
- Paste a portfolio URL and say "what do you think"
- Share a Figma URL and ask "would this case study land?"

**The skill will ask:**
1. Is this YOUR portfolio / resume? (Single confirmation, default yes — guards against misattribution.)
2. Career stage? (junior / mid / senior — affects which rubric branch fires.)
3. For portfolio reviews: UX / UI / product? (Affects how visual craft is weighted.)

Single-line confirmations, not three sequential prompts. If you've already said "I'm prepping for a senior promotion" in the same conversation, the skill won't re-ask.

---

## What this skill does NOT do

- Coach salary negotiation, offer evaluation, or interview logistics. (We're a review tool, not a career coach.)
- Write portfolios from scratch. (We review what you've made.)
- Process audio or video portfolios. (Loom links don't currently work.)
- Follow paywalled or auth-gated portfolio links.
- Generate fictional personas or example portfolios.
- Review for non-US markets. (The rubric is US-shaped — storytelling norms differ. See `gotchas.md`.)
- Review graphic design / photography / illustration / code portfolios. (Different conventions.)

If you want any of the above, redirect to a more specialized tool — or join the Friday stream where Tim and Nate can take a wider range of asks live.

---

## Disclaimer

Every review the skill produces ends with this footer:

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [https://www.youtube.com/@designshaped/](https://www.youtube.com/@designshaped/).*

We mean it. The skill is built from publicly shared content — Nate's published writing, Friday-stream pattern extraction, our own design-review experience codified into a rubric. **Tim and Nate did not personally review your work.** The skill is an approximation, not a stand-in.

**If you screenshot the output:**
- Don't present it as a direct quote from Tim or Nate.
- Attribution that works: *"Portfolio Rx (a Tim+Nate-shaped Claude Code skill) suggested..."*
- Attribution that doesn't: *"Tim said..."* / *"Nate told me..."*

If we wouldn't say it on Friday stream with the reviewee in the call, we don't want it shared as if we did. Help us hold the brand line.

---

## Status

- **Version:** 0.1.0 (pre-launch — M2 stream-mined content installed; v1.0.0 ships once Tim and Nate stamp acceptance per `qa/acceptance-log.md`).
- **Last reviewed by Tim and Nate:** *Pending acceptance run. M2 mining of all 24 @designshaped Friday streams completed 2026-04-30.*

Content the skill currently ships:

- **`references/common-flags.md`** — 26 critique patterns (16 portfolio + 10 resume) mined from 23 Friday-stream transcripts.
- **`references/frameworks.md`** — 25 named frameworks: 12 from [nabauer.com](https://nabauer.com/articles) plus 13 joint Tim+Nate frameworks mined from the streams (What/How/Why bullets, Three Target Audiences, Housekeeping, Trust Ladder, Centralized vs Decentralized Environments, Read-the-Titles-Only Test, Children's Picture Book Rhetoric, JJJ, KSAs, Hook→Proof→Story, Hard vs Soft Metrics, Prototyping with Numbers, Designer Niche Scales).
- **`references/heuristics.md`** — 37 heuristics: 17 verbatim from [nabauer.com](https://nabauer.com/articles) plus 20 stream-mined.
- **`references/voice.md`** — 14 ❌/✅ pair examples + the anti-roast 4-clause rule + the joint Tim+Nate voice register, all sourced from the stream archive.
- **`references/rubric-junior.md`** — prescriptive rubric anchored to positioning, housekeeping, why-how-what bullets, the three audiences, and Tim's "apply up" rhetoric.
- **`references/rubric-senior.md`** — diagnostic rubric anchored to target environment (centralized vs decentralized), the bet at the top of case studies, and scope language as senior tell.

Pattern refresh happens on a quarterly cadence as new streams air.

**Issues / contributions:** open a GitHub issue (URL TBD) with a portfolio-rx run that produced bad output, or a transcript-mining find we missed. PRs welcome from designers who watch the stream and have evidence of patterns we haven't captured.

---

## Authors

- **Tim Gailey** — co-host, Design Shaped Friday review stream.
- **Nate Bauer** — co-host, Design Shaped Friday review stream. Author of the 12 frameworks + 17 heuristics on [nabauer.com/articles](https://nabauer.com/articles) that anchor the skill.

The skill is the joint Friday-review voice. Both authors review pattern updates before they ship.

---

## Build artifacts

The planning artifacts (SPEC, REQUIREMENTS, ROADMAP, research, per-phase CONTEXT.md and PLAN.md files) live OUTSIDE this repo, in `../.planning/builds/portfolio-rx/`. They're maintained for build continuity and are not user-facing documentation.
