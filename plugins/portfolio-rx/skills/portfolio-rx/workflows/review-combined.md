# Workflow: Review combined (resume + portfolio)

## When invoked

Routing dispatches here when the input class includes BOTH a resume AND a portfolio in the same invocation. Per `intake.md` `#multi-input`, that's the default for any of:

- Resume PDF + portfolio URL
- Resume PDF + Figma file (or Figma + screenshots)
- Resume PDF + screenshots of design work
- Pasted resume text + any portfolio class
- Resume + cover letter + portfolio (cover letter folds into the resume input per intake.md)

This is the most common ask. Most users want the holistic read — "do my resume and my portfolio land me the role?" — not an atomic critique of one artifact in isolation.

If the routing layer detected only one class, this workflow is NOT called. `review-resume.md` or `review-portfolio.md` runs instead. See "Forbidden moves" for what to do if we land here with only one class supplied.

## Inputs expected

From `intake.md` `#multi-input` handoff:

- `resume_inputs[]` — one or more structured resume objects (PDF text + heuristic section split, OR pasted text, OR screenshot transcription). Cover letters fold in per `review-resume.md` input contract.
- `portfolio_inputs[]` — one or more portfolio objects, composed into ONE body of work per D-P2-11. URL + Figma + screenshots all collapse here.

From routing:

- `career_stage` — `junior` or `senior`. If absent, default `junior` and emit the auto-clarity confirm in Step 1 (per D-P2-08).
- `role_hint` — `UX` | `UI` | `product`. Optional. Used for the portfolio visual-craft pass (PORT-05). If absent and visual-craft critique would be ambiguous, ask one line.
- `notes` — anything the user said when invoking ("I'm targeting senior product roles," "switching from PM to design," "this is for an internal promotion packet," "NDA-heavy"). Optional but load-bearing when present.

## What to read first

In order. Do not skip.

1. `../references/voice.md` — writing register. Re-read §3 (pattern templates), §4 (drop list), §6 (anti-roast hard rule), §9 (frameworks-by-name), §11 (self-check). Every flag in this workflow's output complies.
2. `../references/rubric-junior.md` OR `../references/rubric-senior.md` — pick one based on `career_stage`. Never load both.
3. `../references/common-flags.md` — load BOTH R01–R10 AND P01–P15. Combined mode is the only review where both halves apply at once.
4. `../references/frameworks-stream.md` AND `../references/frameworks-nate.md` — both files. (`frameworks.md` is the slim index router.) Combined reviews pull resume-shaped frameworks (What/How/Why for bullets, KSAs for ATS keyword match — both in `frameworks-stream.md`) AND portfolio-shaped frameworks (Hook → Proof → Story, Three Target Audiences in `frameworks-stream.md`; Stakeholder Needs Map, Slicing, Brand Drivers in `frameworks-nate.md`) within the same review.
5. `./review-resume.md` — the procedure we run mentally for the resume half.
6. `./review-portfolio.md` — the procedure we run mentally for the portfolio half.

The voice.md ❌/✅ pairs that hit hardest in combined review: Pair 4 (coherence across the body of work — the engine of the COMBO-02 section), Pair 7 (senior strategic narrative), Pair 11 (walking back overconfidence when a body of work is genuinely strong).

## Step-by-step procedure

### Step 1 — Confirm career stage + role hint (single line, single confirm)

If `career_stage` arrived from routing, skip the stage confirm.

If `career_stage` is absent, emit ONE auto-clarity line. Per voice.md §3, single confirm, no hedging:

> Defaulting to the early-career rubric. If you're targeting a senior promotion or a senior IC role, say so and we'll switch.

If `role_hint` is absent AND a visual-craft critique would be ambiguous (UX vs UI have different bars per PORT-05), bundle the role hint into the same one-line confirm:

> Defaulting to early-career, generalist product. Say "senior" if you're on a senior promotion or senior IC track. Say "UX" or "UI" if the role is specialized.

One line, one branch. Do not stack three questions. If the user mentioned stage or role in `notes` ("senior IC at a Series-C," "applying to UI roles"), use that — don't ask again.

### Step 2 — Run resume review (mentally, do NOT emit)

Apply `review-resume.md` procedure Steps 2–5 against `resume_inputs[]`:

- Step 2 — Hiring-manager skim test (junior tiers OR senior 10-second senior-signal test).
- Step 3 — Bullet-level pass against R01–R10 + What/How/Why.
- Step 4 — Section coherence (header / summary / experience / education / skills / projects).
- Step 5 — Top-3 fixes for the resume in isolation.

Hold the output internally. We do not emit a full resume review here. Combined mode is a synthesis, not a concatenation. The atomic resume review's frameworks-applied list and flagged-bullets list are inputs to Step 5 below.

### Step 3 — Run portfolio review (mentally, do NOT emit)

Apply `review-portfolio.md` procedure Steps 2–7 against `portfolio_inputs[]` (composed into ONE body of work per D-P2-11):

- Step 2 — Read the body of work (opener, closer, role callout, outcome paragraph location, visual-artifact density per case study; cap at first 4 case studies per PITFALLS §3.4).
- Step 3 — Coherence read across the body of work (PORT-03).
- Step 4 — Per-case-study breakdown with frameworks named verbatim and P-IDs cited.
- Step 5 — Visual craft pass scaled to `role_hint`.
- Step 6 — Senior layer if `career_stage = senior` (extract thesis, surface coherence gaps Pattern A/B/C/D from rubric-senior.md Step 4).
- Step 7 — Top-3 fixes for the portfolio in isolation.

Hold the output internally. Same rule — synthesis, not concatenation.

### Step 4 — Coherence check (the COMBO-02 distinguishing feature)

This is the load-bearing step of combined mode. If a reviewer reads only one paragraph of the output, it should be the coherence read.

Read both internal outputs together. Ask:

- **Do the resume bullets and the case-study openers tell the same story?** Resume bullet says "Led design for 4M-MAU SaaS"; case study opens with a personal side project. The reader can't tell what work the user actually wants to be hired for.
- **Does the resume's role progression match the portfolio's project selection?** Three roles climbing in B2B SaaS, but the four featured case studies are all consumer mobile apps. The hero promises one thing; the body delivers another.
- **If the user has a stated thesis (senior — extracted in Step 3 per `rubric-senior.md` Step 1), does the resume support it?** Thesis says design-systems lead; resume bullets all describe shipping product flows with no governance, adoption, or RFC evidence. Pattern A from `rubric-senior.md` Step 4 — but cross-document.
- **Does the register match across artifacts?** Resume bullets quantify outcomes; case studies end on "the team got positive feedback." Or the inverse — case studies are rigorous; the resume reads as a job description. Pick one register and use it everywhere.
- **Does the cover letter (if present) align with the portfolio's first three projects?** Cover letter pitches consumer apps; portfolio leads with B2B SaaS. The hiring manager will be confused about what the user wants.
- **Where else do resume and portfolio diverge?** Anywhere the two artifacts argue for different roles, different scopes, or different postures, that's a coherence gap.

Surface the coherence gap as a NAMED flag. The shape — quote both sides, name the gap, name the fix. Examples (these are output shapes, not canned copy — fit them to the user's actual work):

- *"Resume header says 'Design Systems Lead' but the four featured case studies are all 0-to-1 product flows — zero adoption metrics, zero governance, zero contribution-model evidence. Pattern A from `rubric-senior.md` Step 4. The hero promises systems; the body delivers product. Either re-thesis around product (the resume header becomes 'Senior Product Designer who's also done systems work'), or replace two case studies with systems-shaped work — one adoption rollout, one deprecation case study."*
- *"Resume bullets quantify outcomes (38% → 22% drop-off, 4M MAU, 3 product surfaces). Case studies end on 'the team got positive feedback' and 'next steps include further user testing.' Per voice.md Pair 4 + P03, pick one register. The resume's outcome shape is the right one — port it to the case studies. Each case study closes with what shipped, what changed, what you'd do differently."*
- *"Cover letter pitches 'consumer apps that feel inevitable.' Portfolio leads with three B2B SaaS dashboards. The hiring manager reads the cover letter, opens the portfolio, sees a different designer. Pick one and align — either rewrite the cover letter to lead with the B2B work, or replace the lead case studies with consumer work."*

If the resume and portfolio genuinely tell the same story, **say so explicitly**. That's a strong signal, not a bug. Per voice.md Pair 11 (walking back overconfidence), rank against population: *"The resume and the portfolio argue the same thing — same level, same domain, same posture. This is the top 10% of what we see on stream for cross-document coherence. Two notes that would push it further: ..."* Do NOT fabricate a gap to fill the section. Fake coherence flags read worse than no flag.

The cost language matters. State the gap in concrete recruiter / hiring-manager terms per voice.md §6 hard rule #2:

- ❌ "Your resume and portfolio feel a bit inconsistent."
- ✅ "Recruiter reads the resume, sees a Senior Product Designer at a Series-C SaaS. Opens the portfolio, sees three concept redesigns of consumer apps. Spends 8 seconds trying to reconcile, gives up, moves on."

### Step 5 — Synthesize cross-document Top-3

Combine the resume Top-3 (from Step 2) + the portfolio Top-3 (from Step 3) + any coherence flags (from Step 4) into ONE prioritized list of THREE. This is COMBO-01.

Order by impact on landing the role:

1. **A coherence gap usually outranks a single resume bullet rewrite.** A misaligned thesis + evidence axis costs more than one weak verb. If the recruiter bounces on "this designer doesn't know what they want," nothing downstream matters.
2. **A weak case study (the body-of-work weakest link) usually outranks a typography flag.** PORT-05 is real, but P03 (missing outcome) is bigger than P13 (visual-craft inconsistency) on the impact axis.
3. **A senior thesis gap usually outranks any individual flag.** Per rubric-senior.md Step 1, "no thesis is the problem under most other senior portfolio problems." If we extracted no thesis in Step 3, the thesis fix is Top-3 #1, full stop.
4. **A failed Tier-1 skim test (junior portfolio homepage) usually outranks any bullet-level resume flag.** If the homepage doesn't hold attention for 3 seconds, the hiring manager never reaches the resume bullets.
5. **A broken portfolio link on the resume (R06) trumps almost everything else.** It's the cheapest fix and the most expensive miss. If R06 fires, it's Top-3 #1 — full stop.

Use voice.md §3 templates verbatim. NEVER use section names. The shape:

```
[Element]: [problem]. [cost]. [fix]. *(source: resume / portfolio / coherence)*
```

The `*(source: ...)*` tag is mandatory in combined mode — it's how the user knows which document each fix lives in. Without the tag, the Top-3 reads as if it floats free of either artifact.

The Top-3 must mix sources. If all three Top-3 items come from the resume OR all three come from the portfolio, the combined-mode synthesis isn't doing its job — back up and re-prioritize. Coherence flags count as their own source.

Selection example (junior, both artifacts have weaknesses):

1. *Element: the homepage hero. Problem: generic gradient + "passionate designer" tagline. Cost: bouncing at 0-3s tier; the resume bullets never get read because the portfolio link gets clicked first. Fix: replace with one screen of the [project name] work + the positioning sentence "I ship onboarding flows for B2B SaaS." (source: portfolio)*
2. *Element: resume ↔ portfolio coherence. Problem: resume header says "UX Designer focused on B2B SaaS" but three of four case studies are consumer mobile concepts. Cost: hiring manager opens both, can't tell what the user wants to be hired for, defaults to "I'll take any role." Fix: either pick one B2B case study and lead with it on the portfolio, or rewrite the resume header to match what the portfolio actually argues. (source: coherence)*
3. *Element: resume bullet "Responsible for redesigning the onboarding flow." Problem: passive verb + no result kills the strongest resume project. Cost: the bullet is in the most senior role and the recruiter skims past it. Fix: "Led onboarding redesign across 3 product lines; reduced time-to-first-action from 12 min to 4 min." (source: resume — R04, R01)*

### Step 6 — Output assembly

Use the output template below. Order is fixed. The coherence section sits ABOVE both compressed reviews because it's the distinctive output. The compressed reviews are summaries — synthesized, not concatenated; ~10–15 lines for the resume side and ~15–20 lines for the portfolio side.

The frameworks-applied and flags-applied trailers run across both halves of the review. Combined mode often fires 4–7 frameworks total (resume + portfolio sometimes overlap on What/How/Why and Hook → Proof → Story, but otherwise they're separate sets). Combined mode fires a wider P-ID + R-ID surface than either atomic review.

### Step 6.5 — Emit to file (NEW v0.2)

After the review block is assembled and printed to the terminal, emit it to disk per `../references/output-emit.md`. Three steps:

1. **`Write`** the review markdown to `~/portfolio-rx-output/YYYY-MM-DD-<slug>-combined-review.md`.
2. **`Write`** the same content rendered to HTML (using the print-friendly template in `output-emit.md`) to `~/portfolio-rx-output/YYYY-MM-DD-<slug>-combined-review.html`.
3. **`Bash`** `open <html-path>` (macOS) or `xdg-open <html-path>` (Linux) to open in the user's default browser.

Append one line after the in-terminal review:

> 📄 Saved to `~/portfolio-rx-output/<filename>.md` (markdown) and `<filename>.html` (opened in browser — ⌘P to save as PDF).

Combined reviews benefit most from file emit — they're the longest of the three formats and dense to read in terminal. If the user has explicitly said "skip the file" or "just print to terminal," omit Step 6.5.

### Step 7 — Pre-emit self-check

Run the voice.md §11 checklist verbatim. Plus combined-specific checks below. If any check fails, fix or drop the offending content.

Combined-specific self-checks:

- [ ] The Top-3 mixes sources (resume + portfolio + coherence) — not all 3 from one document.
- [ ] The coherence section is genuine — flags real gaps, not made-up ones. If the artifacts genuinely agree, the section says so explicitly per voice.md Pair 11, not silently or with a fabricated flag.
- [ ] No double-counting. If a coherence gap and an underlying portfolio flag are the same thing, surface ONCE — pick the framing with the higher impact (usually the coherence framing) and reference the underlying flag in the compressed portfolio section without re-flagging it in the Top-3.
- [ ] The compressed reviews don't reproduce the full atomic-workflow output. They synthesize — top flags only, ~10–15 lines (resume) and ~15–20 lines (portfolio).
- [ ] The disclaimer footer (D-16) appears once at the bottom — not duplicated from the compressed reviews.

The voice.md §12 read-back test is the final gate: would Tim or Nate actually say this on a Friday stream, with the reviewee in the call? If the answer is no — because it's hedge-y, because it's roast-y, because it's generic, because the coherence section is platitude-shaped — fix it.

## Output template

```
## Combined review — [user's name or "your materials"]

**The materials:** [list — e.g., "1-page resume PDF + portfolio at example.com (3 case studies) + 2 Figma frames"]
**Career stage:** [junior | senior — from routing]

---

**Top 3 fixes (cross-document, by impact)**

1. [Element]: [problem]. [cost]. [fix]. *(source: resume / portfolio / coherence)*
2. [Element]: [problem]. [cost]. [fix]. *(source: ...)*
3. [Element]: [problem]. [cost]. [fix]. *(source: ...)*

---

**Resume ↔ portfolio coherence**

[2–5 sentences. The through-line, OR the named gap. The most distinctive output of this workflow. Quote both sides; name the gap in voice.md what/cost/frame/fix shape. If the artifacts genuinely agree, say so per voice.md Pair 11 — rank against population, name 1–2 nits that would push it further.]

---

**Resume — compressed review**

[Skim test result, 1 line. Top resume-specific flags + rewrites — quote the user's bullets verbatim. ~10–15 lines total. Do NOT reproduce the full review-resume.md output. Synthesize.]

---

**Portfolio — compressed review**

[Coherence read, 1 line. Top portfolio-specific flags + rewrites — quote the user's case-study copy verbatim, name frameworks. Visual craft pass if relevant. Senior strategic-narrative layer if `career_stage = senior`. ~15–20 lines total. Do NOT reproduce the full review-portfolio.md output. Synthesize.]

---

**Frameworks applied:** [comma-separated list — at least 2 per voice.md §11; combined mode usually fires 4–7]
**Flags applied:** [comma-separated R-IDs and P-IDs — e.g., "R01, R04, P03, P05, P11"]
**Coherence flag:** [the named coherence gap, if any — e.g., "Pattern A (thesis says systems, work shows product)" OR "no gap detected — register and posture aligned across both artifacts"]

---

*This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*
```

### Output template notes

- The `**The materials:**` line is mandatory. It anchors the review against what was actually submitted and lets the user spot if we missed an artifact.
- The `**Top 3 fixes**` block is mandatory. Three items, each with `*(source: ...)*` tag. Mixed sources — never all three from one document.
- The `**Resume ↔ portfolio coherence**` section is the distinguishing feature. 2–5 sentences. If we cannot fill it with a real observation, the workflow has failed — back up to Step 4 and re-read the artifacts together.
- The compressed reviews are SUMMARIES. Resume: ~10–15 lines. Portfolio: ~15–20 lines. Lifted directly from the atomic-workflow Top-3 outputs and the highest-leverage section flags. Drop bullets the Top-3 already covered — no double-counting.
- The footer is appended ONCE at the bottom of the combined review per D-16. The atomic workflows return their output without footers when called from combined mode (per `review-resume.md` "How this workflow is composed" + `review-portfolio.md` "How this workflow is composed"). The combined review owns the footer.

## Pre-emit self-check

Verbatim from voice.md §11, plus the combined-specific checks added in Step 7.

- [ ] Every flag has a rewrite. (No critique without a fix.)
- [ ] Every flag quotes the user's actual work or names the specific section.
- [ ] At least 2 frameworks are surfaced by name (per the frameworks-by-name protocol).
- [ ] No phrases from the drop list (§4).
- [ ] Top-3 fixes use the `[Element]: [problem]. [cost]. [fix].` template, not generic section names.
- [ ] If sensitive content present, auto-clarity register applied (§7).
- [ ] If `Tim says:` / `Nate says:` used, each adds a real second angle (not rephrasing).
- [ ] Output ends with the mandatory disclaimer footer (D-16):
  > *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*

Combined-specific:

- [ ] Top-3 mixes resume + portfolio + coherence sources, not all from one document.
- [ ] Coherence section is genuine — flags real gaps, OR explicitly says the artifacts agree per voice.md Pair 11.
- [ ] No double-counting between the coherence section and the compressed reviews.
- [ ] Compressed reviews are synthesized, not concatenated full atomic outputs.
- [ ] Footer appears once, at the bottom.

If a review fails any check, fix or drop the offending content before emitting.

## Forbidden moves

- **Producing only a resume review or only a portfolio review when both inputs were supplied.** Defeats the purpose of combined mode. Re-route into combined synthesis. If we genuinely have no portfolio (the URL 404'd, the Figma file is private), see "What goes wrong" recovery — fall back to the atomic resume review and tell the user.
- **Reproducing the full review-resume.md output verbatim.** Combined mode is a SYNTHESIS, not a concatenation. The compressed resume section is ~10–15 lines, not the 60+ lines a standalone resume review produces.
- **Reproducing the full review-portfolio.md output verbatim.** Same rule. Compressed portfolio section is ~15–20 lines.
- **Skipping the coherence check (Step 4).** The coherence section is the distinguishing feature of combined mode. Without it, we shipped two independent reviews stapled together.
- **Cross-document Top-3 that pulls all 3 items from one document.** If the resume has three crushing flags and the portfolio is fine, surface the resume flags in the resume compressed section — but the Top-3 still has to draw from at least two sources (resume + portfolio + coherence) per COMBO-01's "ordered by impact" mandate.
- **Fabricating coherence gaps that don't exist.** If the resume and portfolio genuinely tell the same story, say so explicitly per voice.md Pair 11. Fake coherence flags are a worse failure than no flag.
- **Drop-list phrases per voice.md §4.** "I noticed," "consider," "perhaps," "it would be helpful to," "you may want to" — none appear in the output.
- **Sycophantic ceilings on the coherence section.** "Everything looks great" is a worse output than "this is in the top 10% — here are two nits that would push it further." Per voice.md Pair 11.
- **Skipping career stage / role hint confirmation (Step 1).** The atomic workflows assume the routing layer handed them a stage; combined mode is the first place we confirm if missing. Skipping leaves both downstream halves unanchored.
- **Inventing Tim or Nate divergence.** Per voice.md §8, callouts are added manually. Default to "we." Combined mode doesn't unlock split takes that the atomic workflows wouldn't have.
- **Restating either artifact.** Don't summarize the resume; don't describe what the portfolio is about. Critique what's there. Per voice.md §4.

## What goes wrong (failure modes + recovery)

- **User supplied only resume OR only portfolio (not both), but routing landed here.** Routing-layer error. Recovery: tell the user directly — *"We see only [resume / portfolio] in this invocation — running review-[resume / portfolio] instead. Share the [missing one] and we'll re-run with the combined coherence check, which is the real value of combined mode."* Then route to the matching atomic workflow.

- **Resume and portfolio are wildly inconsistent and the user is intentionally mid-pivot.** Don't force coherence. Surface the gap as a feature, not a bug — name the pivot, name what bridges the two artifacts, and offer two concrete framings. Voice.md §7 auto-clarity register may apply (career switching is a sensitive context if disclosed). Example shape: *"Your resume reads as B2B SaaS; the portfolio leads with consumer mobile concept work. If this is a deliberate pivot, name it — one line in the resume summary or the portfolio about page that says 'mid-pivot from B2B to consumer; recent work reflects the direction I'm heading.' Either framing beats the silent gap."*

- **Either review on its own would have produced 30+ flags.** Combined mode FORCES curation. We pick the top items only — the bullets that bury the most signal, the case studies that drag the body of work down, the coherence gaps that cost the most. Document this in the output: *"This was a curation pass — flagging the highest-leverage cross-document items. Each compressed section has more underneath; ask for a deep-dive review of just the resume or just the portfolio if you want the full ledger."* Honesty about scope beats false comprehensiveness.

- **User has multiple portfolio inputs (URL + Figma + screenshots).** Treat them as ONE portfolio per D-P2-11 and run `review-portfolio.md` Step 2 once across all of them. If the URL and the Figma file show different work, that itself is a coherence flag inside the portfolio (handled in `review-portfolio.md` Step 3), separate from the resume↔portfolio coherence check this workflow owns. Both can fire in the same review.

- **Resume is excellent and portfolio is weak (or vice versa).** Common pattern. The Top-3 will weight toward the weaker artifact, but the coherence section still earns its place — explicitly name the gap. *"The resume is in the top 10% of what we see on stream; the portfolio is at the median. The gap is itself the flag — recruiters reading both will mark you as 'strong on paper, soft in evidence,' which kills offers at the IC interview stage. The fix is to bring the portfolio up to the resume's level (the more leveraged direction), not down."*

- **Both artifacts are excellent and there's not much to flag.** Apply voice.md Pair 11. Rank against population: *"This combined package is in the top 5% of what we see on stream. The coherence is real — resume and portfolio argue the same posture, same level, same domain. Two-three notes that would push it further:"* Mark them as nits. Give permission to ignore. Do NOT pad with weak flags to hit a quota. Sycophantic ceilings AND padded reviews are both voice failures.

- **Sensitive content surfaces in either artifact** (career gap, layoff, visa, mental health, identity, ESL copy). Apply voice.md §7 auto-clarity register throughout — both halves of the review and the coherence section. Default to the kindest reading. Never name the person, name the choice. Never moralize. Give two concrete framings; don't pick for the user. The cross-artifact coherence rules still apply, but the register softens.

- **NDA-bound senior with thin recent work in both artifacts.** Run `rubric-senior.md` Step 5 (NDA section). The combined coherence check becomes especially valuable here — the resume scope-language and the portfolio shape-without-specifics need to align. If the resume names a 4M-MAU SaaS and the portfolio shows pre-current-job concept work, the gap is loud. Frame: *"Your resume names the scope of the current role (4M MAU, $200M ARR, 12 engineers). The portfolio is silent on the most recent two years. Even NDA-bound work can show shape without surface — add one slice with the structural sketch + outcome at the org level. Right now the portfolio undermines the resume's senior signal."*

- **Career switcher with strong prior career and one design project + a transferable-skills resume.** Per `rubric-junior.md` Archetype B. The combined coherence check asks: does the resume's prior-career framing match the portfolio's "why design now" moment? If the resume has surfaced the transferable-skill bullets but the portfolio's about page reads as generic, that's the coherence fix — port the resume's specificity to the portfolio.

- **Output reads as two atomic reviews stapled together, with a thin coherence section.** Combined-mode failure. Symptom: the coherence section is one platitude sentence; the compressed reviews are 40 lines each. Recovery: regenerate. Almost always means we skipped Step 4's quote-anchored synthesis and went straight to Step 6 output assembly.

- **Cover letter is included alongside resume + portfolio.** The cover letter folds into the resume input per intake.md `#multi-input` and `review-resume.md` input contract. The combined coherence check then has THREE artifacts in scope: cover letter, resume bullets, portfolio case studies. The cover-letter ↔ portfolio gap is often the loudest of the three (cover letter pitches X; portfolio leads with Y). Surface that explicitly when it fires.

- **The user pushes back on the coherence flag.** Normal and useful. The model doesn't argue. Acknowledge the alternative reading, ask one diagnostic question ("if both artifacts are aimed at the same role, what's the through-line a hiring manager would name in 10 seconds?"), and let the user decide. If they say "I meant it that way," the flag drops to a nit or moves out of the Top-3.

## How this workflow is composed

- **Called by SKILL.md routing (P3)** when input class includes BOTH resume AND portfolio. Per ROUTE-03 + intake.md `#multi-input`, this is the default for any multi-class invocation.
- **Reuses procedural steps from `review-resume.md` and `review-portfolio.md`** — Steps 2–3 of this workflow run those procedures internally (Steps 2–5 of resume; Steps 2–7 of portfolio). The atomic workflows return structured outputs (Top-3, section/case-study flags, frameworks-applied, flags-applied) that this workflow synthesizes — they do NOT emit their own footer when called from combined mode.
- **Produces a synthesized output, not concatenated outputs.** The Top-3 is cross-document and prioritized by role-impact (COMBO-01). The coherence section is the distinctive output (COMBO-02). The compressed reviews are summaries — never the full atomic-workflow ledger.
- **Owns the disclaimer footer (D-16).** Atomic workflows skip the footer when called by this one; combined appends it once at the bottom.
- **May be consumed by mock-interview workflows (`mock-interview-list.md`, `mock-interview-walkthrough.md`, P3)**. The combined Top-3, coherence flag, and per-artifact compressed reviews feed question generation. Read-only — those workflows don't modify this one's output.
- **Reads from `references/`** — voice.md (always), rubric-junior.md OR rubric-senior.md (one, never both), common-flags.md (BOTH halves — R01–R10 AND P01–P15), frameworks.md (full file), heuristics.md (sparingly).
- **Writes to nowhere on disk.** Output renders in the user's terminal. PRIV-01 — no remote calls beyond Claude Code's standard tool use during intake; combined mode itself adds no I/O.

The atomic shape of combined mode is: synthesize, don't concatenate. The coherence section is the differentiator. If a future workflow needs cross-document review output, it composes against this one — the same way mock-interview workflows compose against `review-portfolio.md`.
