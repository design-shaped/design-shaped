# Frameworks — Portfolio Rx (index)

> **v0.2 split:** the framework bodies moved into two sister files to fit under the 25k-token Read ceiling. Anchors moved with the bodies — citations that used to read `frameworks.md#hook-proof-story` now read `frameworks-stream.md#hook-proof-story`. This file is the slim router.

## How this file is used

The voice.md §9 frameworks-by-name protocol mandates: when a workflow applies a framework, it names the framework verbatim, quotes specifics from the user's work, and cites the source file's section. NEVER paraphrase. NEVER re-teach inline.

Workflow agents read only the section they need. Each framework is self-contained in one of the two split files:

- **[`frameworks-stream.md`](frameworks-stream.md)** — 13 stream-native portfolio review frameworks (mined from 23 @designshaped Friday-stream transcripts).
- **[`frameworks-nate.md`](frameworks-nate.md)** — 13 frameworks Nate publishes on nabauer.com.

Two voice rules to honor when surfacing a framework:

1. **Name it on first use.** "This bullet leads with **What** in **What/How/Why**." Never "this bullet's W/H/W is off" without spelling out What/How/Why once.
2. **Quote the user's work, then frame.** Pull the user's exact bullet or paragraph, then name the framework step it skips, then provide the rewrite. Never frame in the abstract.

### Worked example of the protocol

A user submits a resume bullet: "Led seven plus projects, including the redesign of ASU's Souls website." A workflow agent applies the protocol:

1. **Quote the user's work:** "Your bullet reads: *'Led seven plus projects, including the redesign of ASU's Souls website.'*"
2. **Name the framework verbatim:** "This leads with **What** in **What/How/Why**. Most impressive thing is last."
3. **Hand off to the rewrite without re-teaching:** "Flip to Why/How/What: *'Increased engagement 20% by improving usability and aligning brand standards across seven plus projects, including ASU's Souls redesign.'*"
4. **Cite the source line:** "See: `references/frameworks-stream.md#what-how-why`."

That four-step loop is the entire mechanic. The workflow agent does NOT explain what What/How/Why is in the review output — the user can read the framework section if they want. The workflow agent's job is to name the gap, quote the work, and prescribe the fix.

When in doubt: name two frameworks, not zero. Per voice.md self-check: "At least 2 frameworks are surfaced by name." A review with no framework names reads as generic LLM critique; one with two or three reads like Tim and Nate.

---

## Index — which framework lives where

### Stream-native (in [`frameworks-stream.md`](frameworks-stream.md))

| Framework | Anchor |
|---|---|
| What/How/Why ↔ Why/How/What | [`frameworks-stream.md#what-how-why`](frameworks-stream.md#what-how-why) |
| Three Target Audiences | [`frameworks-stream.md#three-target-audiences`](frameworks-stream.md#three-target-audiences) |
| Housekeeping | [`frameworks-stream.md#housekeeping`](frameworks-stream.md#housekeeping) |
| Trust Ladder | [`frameworks-stream.md#trust-ladder`](frameworks-stream.md#trust-ladder) |
| Centralized vs Decentralized Environments | [`frameworks-stream.md#centralized-decentralized`](frameworks-stream.md#centralized-decentralized) |
| Read-the-Titles-Only Test | [`frameworks-stream.md#titles-only-test`](frameworks-stream.md#titles-only-test) |
| Children's Picture Book Rhetoric | [`frameworks-stream.md#picture-book`](frameworks-stream.md#picture-book) |
| JJJ (Jolt / Journey / Jackpot) | [`frameworks-stream.md#jjj`](frameworks-stream.md#jjj) |
| KSAs (Knowledge / Skills / Abilities) | [`frameworks-stream.md#ksas`](frameworks-stream.md#ksas) |
| Hook → Proof → Story | [`frameworks-stream.md#hook-proof-story`](frameworks-stream.md#hook-proof-story) |
| Hard Metrics vs Soft Metrics | [`frameworks-stream.md#hard-soft-metrics`](frameworks-stream.md#hard-soft-metrics) |
| Prototyping with Numbers | [`frameworks-stream.md#prototyping-with-numbers`](frameworks-stream.md#prototyping-with-numbers) |
| Designer Niche Scales | [`frameworks-stream.md#niche-scales`](frameworks-stream.md#niche-scales) |

### Nate Bauer (in [`frameworks-nate.md`](frameworks-nate.md))

| Framework | Anchor |
|---|---|
| Slicing | [`frameworks-nate.md#slicing`](frameworks-nate.md#slicing) |
| Stakeholder Needs Map | [`frameworks-nate.md#stakeholder-needs-map`](frameworks-nate.md#stakeholder-needs-map) |
| The 80% Principle | [`frameworks-nate.md#the-80-percent-principle`](frameworks-nate.md#the-80-percent-principle) |
| Dual Track Agile | [`frameworks-nate.md#dual-track-agile`](frameworks-nate.md#dual-track-agile) |
| Brand Drivers | [`frameworks-nate.md#brand-drivers`](frameworks-nate.md#brand-drivers) |
| Ethos / Pathos / Logos | [`frameworks-nate.md#ethos-pathos-logos`](frameworks-nate.md#ethos-pathos-logos) |
| Ladders | [`frameworks-nate.md#ladders`](frameworks-nate.md#ladders) |
| Two-Filter Research Method | [`frameworks-nate.md#two-filter-research-method`](frameworks-nate.md#two-filter-research-method) |
| Proto Persona | [`frameworks-nate.md#proto-persona`](frameworks-nate.md#proto-persona) |
| Component Library → Design System Progression | [`frameworks-nate.md#component-library-design-system-progression`](frameworks-nate.md#component-library-design-system-progression) |
| House Analogy | [`frameworks-nate.md#house-analogy`](frameworks-nate.md#house-analogy) |
| Lean / Agile / Scrum | [`frameworks-nate.md#lean-agile-scrum`](frameworks-nate.md#lean-agile-scrum) |
| Three Pillar System | [`frameworks-nate.md#three-pillar-system`](frameworks-nate.md#three-pillar-system) |

---

## Loading guidance for workflows

Workflows should load frameworks selectively, not eagerly. Three patterns:

- **Bullet/resume-shaped reviews** — load `frameworks-stream.md` only (What/How/Why, KSAs, Housekeeping carry most resume work). Pull `frameworks-nate.md` for Lean/Agile/Scrum if the user buzzword-stacks.
- **Portfolio reviews** — load both. Most portfolio reviews cite at least one stream framework (Hook → Proof → Story, Three Target Audiences) and at least one Nate framework (Slicing, Stakeholder Needs Map, Brand Drivers).
- **Senior diagnostic reviews** — both files; Niche Scales + Ladders + Brand Drivers cluster always loads together.

The Read tool's 25k-token ceiling is the reason for the split. Each split file fits well under the cap. If a workflow tries to load `frameworks.md` and expects framework bodies, it will get the index — read the appropriate split file instead.

---

## Cross-framework patterns

Several patterns recur across multiple frameworks. Workflow agents should recognize them.

**The honest-claim pattern.** [The 80% Principle](frameworks-nate.md#the-80-percent-principle), [Component Library → Design System Progression](frameworks-nate.md#component-library-design-system-progression), [Proto Persona](frameworks-nate.md#proto-persona), and [Hard Metrics vs Soft Metrics](frameworks-stream.md#hard-soft-metrics) all share the same underlying move: prefer the smaller honest claim over the bigger fabricated one. When reviewing a portfolio that over-claims, reach for whichever fits the specific over-claim. Hiring managers reward precision; they punish inflation.

**The cadence-and-rhythm pattern.** [Slicing](frameworks-nate.md#slicing), [Dual Track Agile](frameworks-nate.md#dual-track-agile), [House Analogy](frameworks-nate.md#house-analogy), and [Centralized vs Decentralized Environments](frameworks-stream.md#centralized-decentralized) all diagnose the same gap: case studies that compress iteration into a single block. The frameworks attack the gap from four angles — Slicing names the iteration unit, Dual Track Agile names the designer-to-engineering rhythm, House Analogy names the posture (waterfall vs. agile), Centralized vs Decentralized names the prerequisite environment.

**The positioning-and-narrative pattern.** [Brand Drivers](frameworks-nate.md#brand-drivers), [Ladders](frameworks-nate.md#ladders), [Designer Niche Scales](frameworks-stream.md#niche-scales), [Ethos / Pathos / Logos](frameworks-nate.md#ethos-pathos-logos), [Stakeholder Needs Map](frameworks-nate.md#stakeholder-needs-map), and [Three Target Audiences](frameworks-stream.md#three-target-audiences) are the cluster for "this portfolio is technically fine but not landing." When asked "review my whole portfolio holistically" or "I'm not getting interviews," start in this cluster.

**The case-study-shape pattern.** [What/How/Why](frameworks-stream.md#what-how-why), [Hook → Proof → Story](frameworks-stream.md#hook-proof-story), [JJJ](frameworks-stream.md#jjj), [Read-the-Titles-Only Test](frameworks-stream.md#titles-only-test), [Children's Picture Book Rhetoric](frameworks-stream.md#picture-book), and [Housekeeping](frameworks-stream.md#housekeeping) all attack case-study consumability. What/How/Why operates at the bullet level; Hook → Proof → Story at the case-study sequence; JJJ at the opening beat; Read-the-Titles-Only Test at the section-title level; Picture Book at the prose-vs-imagery balance; Housekeeping at the recruiter-readable factual block.

**The metric-evidence pattern.** [Hard Metrics vs Soft Metrics](frameworks-stream.md#hard-soft-metrics) and [Prototyping with Numbers](frameworks-stream.md#prototyping-with-numbers) form the escalation: hard metric → behavior change → prototyped numbers. Use the order verbatim. Never claim higher on the ladder than the evidence supports.

**The Ladders distinction (cross-framework critical note).** [Ladders](frameworks-nate.md#ladders) (Nate's competitive positioning) and [Trust Ladder](frameworks-stream.md#trust-ladder) (within-page conversion sequencing) share a metaphor but answer different questions. They co-occur often in reviews. Always cite by full name. Do not merge.

---

## Adding new frameworks

Both split files are additive (per CONTENT-05). New frameworks land in whichever sister file they belong to as Tim+Nate mine them from Friday-stream transcripts on the @designshaped YouTube channel, or as Nate publishes new articles on nabauer.com.

When adding a framework:

- **Pick the right file.** Stream-mined → `frameworks-stream.md`. Nate's published articles → `frameworks-nate.md`.
- **Pull text verbatim from the source.** Don't paraphrase — the voice's authenticity comes from quoting Nate's (or Tim's) actual words. If a quote is missing, mark it `[verbatim source TBD]` and ship; don't invent.
- **Match the existing section template.** Name (anchor), Use when, The structure, Apply to a portfolio, Source. The template's order is the workflow agent's read order — don't reorder.
- **Append, don't rewrite.** Add the new framework to the bottom of its file's Index, then add the section to the bottom of the file. Workflows already cite existing anchors — don't break those citations.
- **Update this index.** Add the framework to the table for the appropriate file.
- **Cite the transcript or article.** New patterns from streams cite the transcript line in the private `mining-log.md` (per D-17 — Tier 1 mining doesn't require re-contact, but the audit trail does). New articles cite the URL.
- **Earn the section.** Not every observation Nate or Tim makes on stream is a framework. A framework has structure (named beats, a stop rule, a sequence, or a diagnostic). One-line heuristics belong in `references/heuristics.md`, not here. Test: can a workflow agent quote the structure verbatim and apply it without paraphrasing? If yes, it's a framework. If no, it's a heuristic.

The ceiling on each split file is roughly 15 frameworks. We're at 13 in each now. Past 15 per file, split further (e.g., `frameworks-stream-rhetoric.md`, `frameworks-stream-research.md`).

When in doubt about whether a candidate framework crosses the bar, route to Tim+Nate. The voice depends on these being right, not on these being many.
