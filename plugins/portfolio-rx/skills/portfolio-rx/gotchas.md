# Gotchas — Portfolio Rx

Known limitations, out-of-scope cases, and the reasoning behind a few design decisions that aren't obvious from the README.

---

## The rubric is US-shaped

The hiring-manager skim test, the resume conventions, the "why this path" career narrative coaching — all of it is shaped for US tech hiring conventions. Specifically:

- US resumes are 1 page, no photo, no date of birth, no marital status. Many international CV conventions include all three.
- The 0-3s / 3-10s / 10-30s skim hierarchy is a US recruiter-pace convention.
- Career-narrative coaching emphasizes a coherent "why this path" thesis. Some cultures undervalue narrative in favor of credentials.
- "Cover letter" expectations vary widely outside the US.

**What works regardless of geography:** case study structure (Hook → Proof → Story / What/How/Why), framework citation, voice (direct, no roast), bullet-level rewrites, mock interview question generation.

**What doesn't translate cleanly:** resume formatting conventions, the skim-test priorities, the senior-promotion rubric (especially in countries with stronger formal levels frameworks).

If you're applying to a non-US market, treat the structural feedback as universal and the formatting/conventions feedback as US-specific. Use your local network to validate the rest.

---

## Out-of-scope portfolios

The skill won't help with:

- **Graphic design portfolios.** Different evaluation criteria (visual craft is the deliverable; case studies are presentation pieces, not problem-solving narratives). The skill will tell you politely.
- **Photography portfolios.** Same — visual craft is the deliverable, narrative is secondary, and our rubric is wrong for it.
- **Illustration portfolios.** Same.
- **Code / engineering portfolios.** Different domain. The "coherence read" works conceptually but the rubric (esp. visual craft) doesn't.
- **Architecture / industrial design portfolios.** Out of domain.

If you're applying to a hybrid role (e.g., a "design engineer" position), bring the design portfolio side to this skill and use a separate tool for the engineering side.

---

## "Is this your portfolio?" — why we ask

Before producing a review, the skill asks a single line: **"Is this YOUR portfolio?"** Default yes.

This guards against misattribution. People sometimes feed someone else's portfolio into a review tool, then screenshot the output and present it as critique of that person's work. The single-confirmation step:

- Reminds you that the output will be tailored to your situation (career stage, role hint, narrative).
- Surfaces the case where you're reviewing a peer / mentee — the framing shifts to "review of [name]'s portfolio."
- Discourages the pattern of "let me ask Portfolio Rx what's wrong with this person's work."

If the answer is no, the skill still runs, but the framing changes. Be honest with yourself about whose portfolio you're sharing.

---

## Why no `--tim-only` or `--nate-only` modes

Common ask: "I want a Tim review specifically" / "I want a Nate review specifically." The skill ships in joint-voice mode only.

**Why:** the skill mines patterns from public Friday-stream content, where Tim and Nate are speaking together. Speaker attribution from auto-captions is unreliable, and even if we attributed perfectly, the joint review IS the product. Splitting them turns a coherent review into two slightly-different averages — both worse than the joint version.

**`Tim says:` / `Nate says:` callouts** appear when the skill genuinely knows their lenses diverge on a specific call. These are added MANUALLY by Tim and Nate during a markup session, not auto-generated. They're rare on purpose — most of the value is in the joint take.

If you want the actual Tim or actual Nate, the Friday stream is the right tool.

---

## Why placeholders in `references/voice.md`

The 12 ❌/✅ pairs in `references/voice.md` have `[Tim/Nate phrasing TBD]` placeholders for the good versions. The bad versions are real LLM-default phrasings — useful as anti-patterns even before we fill in the real phrasing.

**Why placeholders:** capturing actual Tim+Nate phrasing requires either (1) a markup session where they sit and write the good versions in their own voice, or (2) extraction from Friday-stream transcripts that haven't been mined yet. Both are happening on a longer timeline than v0.1.0 ships.

**What it means for you as a user:** the skill currently uses *example shape* phrasings that match the structural pattern Tim+Nate would use, but the exact words are the model's best approximation. Once Tim and Nate fill in their actual phrasing, the skill's voice gets noticeably closer to theirs.

Track this in the version stamp — v1.0.0 ships when the phrasing slots are filled.

---

## Why the privacy section reads the way it does

The privacy section in the README is intentionally NOT marketing copy. It reads like a legal/technical disclosure because that's what builds trust on a tool that ingests sensitive job materials.

**What it explicitly does NOT say:**
- "100% local" — that's technically untrue. Materials go to Anthropic's API.
- "Encrypted end-to-end" — also not true; standard CC encryption applies, nothing more.
- "Your data is safe" — too vague to be meaningful.

**What it says instead** is the actual data flow: where materials go, what doesn't happen, where the user can verify against Anthropic's policies, and where they should NOT use the skill (sensitive materials they don't want feeding a hosted LLM).

Don't reword this section to be "more punchy." Accuracy is the trust signal.

---

## Why the output footer is non-removable

Every review ends with:

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: https://www.youtube.com/@designshaped/.*

This footer is mandatory and non-removable. **Why:**

- People screenshot LLM output and share it as authoritative quotes. It happens to every popular tool.
- "Portfolio Rx says..." is fine. "Tim said..." or "Nate said..." is not.
- The footer sets attribution expectations directly in the artifact.

If you remove it, you're sharing a review that looks like it came from us when it didn't. That hurts our brand and your credibility — both real costs.

Help us hold the line. If you want a quote from us specifically, come to the stream.

---

## "I think the skill said the wrong thing"

Happens. The skill is mining patterns + applying frameworks + branching on rubrics. It can:
- Flag something that's actually intentional in your work.
- Apply a framework that isn't the right one for your case.
- Miss a stronger flag because the pattern isn't in `common-flags.md` yet.
- Use junior framing on a senior portfolio (or vice versa) if the routing got confused.

**What to do:**
- Ignore the flag. The skill explicitly invites this — flags marked as `nit:` are skippable, and "ignore if you disagree" is a built-in voice move.
- Push back. Tell the skill "this case study is intentionally process-heavy because it's a research project" — it should adjust.
- Bring it to the Friday stream. The hardest cases are exactly where the live review beats the async one.

The skill is a starting point, not a verdict.

---

## Update cadence

Patterns get refined as new Friday-stream transcripts are mined. The plan:

- **Quarterly:** Tim and Nate review `common-flags.md`, `frameworks.md`, `heuristics.md`. Mark stale patterns, add new ones from recent streams. README's "Last reviewed by Tim and Nate" date gets bumped.
- **As-needed:** The voice-capture session that fills `[Tim/Nate phrasing TBD]` slots is one-time-ish, but anti-roast guardrails and ❌/✅ pairs may evolve.

If the README's "last reviewed" date is older than 6 months, the skill will surface a "this content may be stale" notice in output.
