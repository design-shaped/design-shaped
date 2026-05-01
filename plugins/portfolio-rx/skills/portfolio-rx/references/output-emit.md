# Output emit — Portfolio Rx

## Why this file exists

Reviews are long. Tim's first end-to-end test produced 20k+ characters of dense markdown. Reading that in the terminal is not fun. v0.2 adds a **file-out emit step** to every review workflow: after the review prints to the terminal, the workflow writes the same content to disk as `.md` AND a styled `.html`, then opens the HTML in the user's default browser. The user can read it like a document and Cmd+P → "Save as PDF" if they want a portable copy.

This file is the shared recipe. Every review workflow's "Step 8 — Output assembly" calls into it after generating the review block.

## When to emit

- ALWAYS emit for `review-portfolio`, `review-resume`, and `review-combined`. These are long-form reviews.
- DON'T emit for `mock-interview-list` and `mock-interview-walkthrough` by default — those are conversational and live in the terminal naturally. (Optional: if the question list is long, offer to emit as a courtesy. User opt-in only.)

## Where to write

Default directory: `~/portfolio-rx-output/`. Create if it doesn't exist (`mkdir -p`).

Filename pattern:

```
~/portfolio-rx-output/YYYY-MM-DD-<slug>-<mode>-review.md
~/portfolio-rx-output/YYYY-MM-DD-<slug>-<mode>-review.html
```

- `YYYY-MM-DD` = today's date in ISO.
- `<slug>` = lowercase, dash-separated. From the user's name if known (`tim-gailey`), or the portfolio domain if not (`timgailey-com`), or `anonymous` if neither.
- `<mode>` = `portfolio` | `resume` | `combined`.

If a file at the target path already exists, append `-2`, `-3`, etc. Don't overwrite.

## How to emit

Three tool calls. Run sequentially, not in parallel.

### Step A — Write the markdown

`Write` tool. Content = the verbatim review block produced by Step 7 of the calling workflow (NOT including any conversational scaffolding the model added in chat — the file should be the review only, with the mandatory footer per D-16).

### Step B — Write the styled HTML

`Write` tool. Wrap the markdown in the HTML template below, after rendering the markdown to HTML inline. The model itself does the markdown→HTML conversion — no external tools needed.

The HTML template (use verbatim; minimal print-friendly CSS):

```html
<!doctype html>
<html lang="en">
<head>
<meta charset="utf-8">
<title>Portfolio Rx — <slug></title>
<style>
  :root {
    --ink: #14181f;
    --paper: #fafafa;
    --rule: #e4e4e7;
    --accent: #0b6e3a;
    --measure: 68ch;
  }
  @media print {
    :root { --paper: #ffffff; }
    body { padding: 0; }
    main { margin: 0; max-width: none; }
  }
  * { box-sizing: border-box; }
  body {
    margin: 0;
    padding: 2rem 1rem 4rem;
    background: var(--paper);
    color: var(--ink);
    font: 16px/1.55 -apple-system, BlinkMacSystemFont, "Segoe UI", system-ui, sans-serif;
  }
  main {
    max-width: var(--measure);
    margin: 0 auto;
  }
  h1, h2, h3, h4 {
    font-family: ui-serif, Georgia, "Times New Roman", serif;
    line-height: 1.25;
    margin-top: 2rem;
    margin-bottom: 0.5rem;
  }
  h1 { font-size: 2rem; border-bottom: 2px solid var(--ink); padding-bottom: 0.5rem; }
  h2 { font-size: 1.5rem; margin-top: 2.5rem; }
  h3 { font-size: 1.2rem; color: var(--accent); }
  hr { border: none; border-top: 1px solid var(--rule); margin: 2.5rem 0; }
  p, li { font-size: 1rem; }
  ul, ol { padding-left: 1.4rem; }
  li { margin-bottom: 0.4rem; }
  blockquote {
    border-left: 3px solid var(--accent);
    margin: 1rem 0;
    padding: 0.25rem 0 0.25rem 1rem;
    color: #3f4756;
    font-style: italic;
  }
  code {
    font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
    font-size: 0.9em;
    background: #f0f1f3;
    padding: 0.1em 0.3em;
    border-radius: 3px;
  }
  pre {
    background: #f0f1f3;
    padding: 1rem;
    overflow-x: auto;
    border-radius: 4px;
  }
  pre code { background: none; padding: 0; }
  strong { color: #000; }
  em { color: #2a2f3a; }
  table { border-collapse: collapse; margin: 1rem 0; }
  th, td { padding: 0.4rem 0.8rem; border: 1px solid var(--rule); text-align: left; }
  th { background: #f0f1f3; }
  footer {
    margin-top: 3rem;
    padding-top: 1rem;
    border-top: 1px solid var(--rule);
    font-size: 0.85rem;
    color: #5a6275;
    font-style: italic;
  }
  .print-hint {
    position: fixed;
    top: 1rem;
    right: 1rem;
    background: #fffbe6;
    border: 1px solid #f0c36d;
    padding: 0.5rem 0.8rem;
    border-radius: 4px;
    font-size: 0.85rem;
  }
  @media print { .print-hint { display: none; } }
</style>
</head>
<body>
  <div class="print-hint">⌘P → Save as PDF for a portable copy.</div>
  <main>
    <!-- RENDERED_MARKDOWN_GOES_HERE -->
  </main>
</body>
</html>
```

Render the review markdown to HTML using the standard mappings: `# Heading` → `<h1>`, `## Heading` → `<h2>`, `**bold**` → `<strong>`, `*italic*` → `<em>`, `>` blockquotes, `-` and `1.` lists, code fences, horizontal rules, tables. Replace the `<!-- RENDERED_MARKDOWN_GOES_HERE -->` comment with the rendered fragment.

The mandatory footer (per D-16) is part of the review markdown itself — don't strip it. It will render inside the `<main>`.

### Step C — Open in default browser

`Bash` tool: `open ~/portfolio-rx-output/<filename>.html`.

On macOS, `open` resolves to the user's default `.html` handler (Safari, Chrome, Arc, Dia). If the user is on Linux/WSL, fall back to `xdg-open`. (Detect with: `if [[ "$(uname)" == "Darwin" ]]; then open ...; else xdg-open ...; fi`. Single command, no extra round-trip.)

### Step D — Tell the user (one line, after the review block)

After the in-terminal review, append one line:

> 📄 Saved to `~/portfolio-rx-output/<filename>.md` (markdown) and `<filename>.html` (opened in browser — ⌘P to save as PDF).

That's it. The user gets the review on screen + a reading-friendly file open in their browser + a markdown copy for editing.

## Failure modes

- **Disk write fails** (read-only home, full disk). Bail gracefully — log the error to the terminal in one line, don't error-loop. The terminal still has the review.
- **`open` exits non-zero** (no GUI, headless session, missing default handler). Print the file path so the user can open it manually: "Saved to `~/portfolio-rx-output/<file>.html` — open it in your browser to read."
- **Pre-existing same-named file.** Append `-2`, `-3`, etc. Never overwrite.
- **User explicitly opts out** ("just print to terminal," "skip the file"). Skip Steps A-D. Print only.

## Privacy

Files are written to the user's local disk only. Nothing leaves the machine. The `open` call hands the local file URL to the OS; the browser opens a local-disk file (no network round-trip). Per PITFALLS §2 — this changes the data flow only by **adding a local-disk artifact**. The Anthropic API has already received the review content as part of the chat; emitting to disk doesn't add a new external recipient.

If the user's portfolio contains sensitive content (career-gap details, layoff context, identity disclosures), the on-disk file inherits that sensitivity. The user is responsible for the file's local handling — same model as any other Claude Code-generated file. Don't add a special privacy callout for this; it's the same baseline.

## Why HTML, not direct PDF

PDF generation requires `pandoc` / `wkhtmltopdf` / `weasyprint` — none of which ship with macOS by default. Bundling a PDF toolchain inside the skill is brittle (Python deps, shell quirks, font discovery). HTML + browser print covers 100% of users with zero install cost. The tradeoff is one extra Cmd+P for the user — fine.

If a future user has `pandoc` installed and wants direct PDF, the workflow can detect that (`command -v pandoc`) and skip the HTML step. Until then, HTML is the universal substrate.
