# Resume Rx

> No roasting: just collaboration and constructive feedback.

An async resume-writing partner in the joint Friday-review voice of Tim Gailey and Nate Bauer. Three working modes that meet you where you are: tighten an existing draft, brainstorm bullets from a blank page, or draft a structured resume from a list of achievements.

Sister plugin to [`portfolio-rx`](../portfolio-rx/) in the [Design Shaped marketplace](../../README.md).

---

## Install

Add the marketplace to Claude Code, then install:

```bash
# In any Claude Code session:
/plugin marketplace add design-shaped/design-shaped
/plugin install resume-rx@design-shaped
```

The marketplace repo is currently private (pre-acceptance). Collaborators added to the `design-shaped` GitHub org can install via the command above. After Tim+Nate stamp acceptance, the repo flips public and anyone can install.

To install **locally** during plugin development:

```bash
git clone https://github.com/design-shaped/design-shaped ~/projects/design-shaped

# In Claude Code:
/plugin marketplace add ~/projects/design-shaped
/plugin install resume-rx@design-shaped
```

---

## Modes

Resume Rx routes automatically based on what you bring. You can also override with an explicit invocation.

### Line-edit

You have a resume draft (paste, PDF, LinkedIn URL, LinkedIn JSON export, Notion URL, or Google Doc URL) and want it sharper. Resume Rx returns a marked-up version: original + rewrite side-by-side per bullet, with a 1-sentence rationale citing the failure mode (R01–R12) and the framework applied (What/How/Why, XYZ, Scope-Impact-Metric, etc.). Top-of-doc surfaces the 3 highest-leverage issues.

Trigger phrases: *"review my resume,"* *"line-edit this,"* *"tighten my bullets,"* *"give me a marked-up version."*

### Brainstorm

You're staring at a blank page or a thin LinkedIn shell. Resume Rx asks scope-and-impact probes (15 conversational probes from Bucket 6 of the Design Shaped stream archive — *what changed because of you?*, *what did you specifically own here?*, *any number tied to this work?*) and synthesizes 3–7 draft bullets from your answers. Probes lead; drafting follows.

Trigger phrases: *"help me brainstorm,"* *"I'm staring at a blank page,"* *"I'm stuck on my resume,"* *"I don't know what to write."*

### Draft-from-list

You have raw notes — projects, achievements, role history dumped from memory — but no resume yet. Resume Rx parses the dump (employer mentions, date ranges, titles, project names, skill mentions, education mentions), then synthesizes a four-section markdown resume: Summary / Experience / Skills / Education. Every bullet cites its framework. `<!-- GAP -->` markers appear inline wherever the source list didn't carry the data — Resume Rx never invents employers, dates, education, or metrics to fill the holes.

Trigger phrases: *"draft my resume from these notes,"* *"turn this list into a resume,"* *"structure these wins,"* *"build me a resume from this dump."*

---

## Voice register

Every Resume Rx output follows the writing register documented in [`skills/resume-rx/references/voice.md`](./skills/resume-rx/references/voice.md). The voice is direct, framework-named, and load-bearing on a single hard rule: **no roasting**. *"No roasting: just collaboration and constructive feedback"* is the brand line, and the four-clause anti-roast test in voice.md §6 must pass before any output emits. Hedge words — *"you might want to,"* *"perhaps,"* *"consider,"* *"it would be helpful to"* — are banned. Banned AI-default verbs (*spearheaded, leveraged, synergized, catalyzed, orchestrated, championed*) never appear in any synthesized or rewritten bullet, even if the user used them in conversation.

---

## What this plugin does NOT do

Set expectations. v1 keeps a tight scope.

- **Does not review portfolios.** Portfolio URLs, Figma case studies, design mock-interview prep — that's [portfolio-rx](../portfolio-rx/), the sister plugin.
- **Does not paste-tailor to a job description.** JD-paste tailoring is deferred to v1.1+. Bring the role-family preset closest to your target role; the bullets get sharper without keyword-matching tricks.
- **Does not export .docx or render visual layouts.** Output is markdown. Bring your own layout tooling (Figma, Notion, a Google Doc, a one-column markdown-to-PDF pipeline).
- **Does not write cover letters.** Cover letters are a different content type with different conventions. A cover-letter plugin is scoped for a future build.
- **Does not invent metrics, employers, dates, titles, or education.** When the data isn't there, you'll see a `<!-- METRIC GAP -->`, `<!-- ROLE GAP -->`, `<!-- BULLET GAP -->`, or `<!-- SECTION GAP -->` marker in the output — never a fabricated number or fact.
- **Does not assign numeric scores, grades, or meters.** No "resume score," no "ATS-readiness percentage," no bullet-strength rating. Resume.io / Rezi-style grading is the failure mode this rule prevents.
- **Does not stuff ATS keywords.** Resume Rx writes for the hiring design manager; modern ATS follows. No "add these words" list at the bottom of the output.
- **Does not WebFetch portfolio links.** v1 detects missing-portfolio-link as a flag (R06) without live verification. Live link-checking is deferred.
- **Does not handle out-of-scope resume types.** Academic CVs (publications-list-driven), federal resumes (USAJOBS-conformant), international CVs requiring photo/DOB, non-designer resumes (PM, eng, marketing) — Resume Rx surfaces the scope mismatch and declines rather than forcing the rubric onto the wrong artifact.
- **Does not invent a fifth role-family preset.** Hybrid roles (content designer, design technologist, service designer, design ops lead) route to the closest of the four existing presets with one inline note acknowledging the call.

---

## Audience

Resume Rx is built for **working designers, all levels — junior through staff**. The rubrics calibrate:

- **Junior + mid** → `rubric-junior.md`. Prescriptive checklist. Mid calibration notes folded inline at each criterion.
- **Senior + staff** → `rubric-senior.md`. Diagnostic flow. Staff calibration notes folded inline.

The boundary between rubrics is **target role**, not years-of-experience. A 4-year designer applying to staff promotion-track roles routes to the senior rubric. A 10-year designer pivoting from a senior IC job back to a hands-on junior IC role routes to the junior rubric.

Four role-family presets carry verb sets, scope language, and worked rewrites:

- **Product Designer** — `references/role-families/product-designer.md`
- **UX Researcher** — `references/role-families/ux-researcher.md`
- **Design Engineer** — `references/role-families/design-engineer.md`
- **Design Lead / Manager** — `references/role-families/design-lead-manager.md`

Hybrid roles (content designer, design technologist, service designer, design ops lead) route to the closest of the four — Resume Rx will surface the call and show the routing call inline.

---

## Privacy

This plugin runs inside Claude Code on your machine. There is no Resume Rx server, no telemetry, and nothing is sent back to Tim or Nate. The materials you share with the skill flow through Claude Code's normal tool surface (Read for paste/PDF, WebFetch for LinkedIn / Notion / GDoc URLs) and are processed by Anthropic's Claude API the same way as any other Claude Code prompt. Anthropic's data handling is governed by their [usage policies](https://www.anthropic.com/legal/aup) and your account terms.

The marketplace-level privacy model is documented in [the marketplace README](../../README.md#privacy-model-marketplace-level).

---

## Issues / contributions

Open a [GitHub issue](https://github.com/design-shaped/design-shaped/issues) with:

- A Resume Rx run that produced bad output (sanitize sensitive details first).
- A pattern you've seen on the Friday stream that we missed.

PRs welcome from designers who watch the stream and have evidence of patterns we haven't captured.

---

## Disclaimer

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [https://www.youtube.com/@designshaped/](https://www.youtube.com/@designshaped/).*

If you screenshot Resume Rx output, please don't present it as a direct quote from Tim or Nate. Attribution that works: *"Resume Rx (a Tim+Nate-shaped Claude Code plugin) suggested..."* — never *"Tim said..."* or *"Nate told me..."*. If we wouldn't say it on Friday stream with the reviewee in the call, we don't want it shared as if we did.
