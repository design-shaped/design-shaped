---
title: Role family preset — Design Engineer (Resume Rx)
plugin: resume-rx
covers: TGT-07
sources:
  - research/FEATURES.md §1.4 (R-IDs), §2.1 (role-family bullet patterns — Design Engineer row)
  - research/STREAM_MINING_RESUME.md §E3 (Tim verbatim on technical-space bullet density), §E7 (KSA-vocabulary list)
  - research/PITFALLS.md §1.4 (over-tooling — stack-specificity prescription), §1.7 (role-family voice mismatch)
  - references/voice.md (banned AI verbs §11.1, no-fab metrics §11.2, area-of-work labels §11.8)
  - references/frameworks.md (What/How/Why, XYZ, Scope-Impact-Metric)
  - references/common-flags.md (R01, R02, R04, R05, R10, R11, R12)
  - references/heuristics.md H-S08 (stack-specificity over category)
  - references/rubric-junior.md, references/rubric-senior.md
---

# Role family preset — Design Engineer (Resume Rx)

> No roasting: just collaboration and constructive feedback. Joint Tim+Nate voice.

This preset covers the **Design Engineer** role family — the hybrid practitioner who lives at the seam between design and front-end engineering. In v1 scope this means designers who code (build production-grade UI from their own design work) and engineers who design (front-end specialists with strong taste, design-system stewardship, or prototyping ownership). Title variants in the wild: *Design Engineer, Design Technologist, UX Engineer, Design Systems Engineer, Prototyper, Creative Technologist, Front-end Designer.* The preset's job is to keep bullets honest about what shipped, where it shipped (the stack), and what changed because the candidate was the one in the seat — without letting tool-list noun salad or category-only positioning drown the signal.

---

## Section 1 — Verb set

The licensed verb set for Design Engineer bullets, anchored in shipped-code reality:

- **shipped** — code landed in production, observable by users
- **prototyped-in-code** — built a working artifact in the actual stack (not Figma) that informed the decision
- **instrumented** — wired analytics, telemetry, or measurement into the surface
- **owned** — accountable for the surface, the component, or the system across releases
- **automated** — replaced a manual design-eng handoff or pipeline step with code
- **refactored** — restructured a component, system, or codebase with a measurable craft outcome
- **integrated** — wired design tokens, design-system primitives, or component sets into the application stack
- **built** — composed, assembled, or authored — anchored in a named artifact (component, plugin, pipeline, page)

**Anti-set (banned-AI-verb list per voice.md §11.1).** Never emit *spearheaded, leveraged, synergized, catalyzed, orchestrated, championed, drove (without object), amplified (without metric)* on the rewrite side. These are the giveaway pattern hiring managers at design-forward and engineering-forward orgs pattern-match instantly since 2024 (PITFALLS §2.2). For Design Engineer specifically: *leveraged* is the most common offender — candidates reach for it to sound technical and produce abstraction-regression instead. The fix is the specific named action: *"used React Server Components to..."* beats *"leveraged modern frameworks to..."* every time.

The abstraction-regression guard (voice.md §4) sits next to the verb set: rewrites are at least as concrete as the original. If the user wrote *"built a Figma plugin for design-token sync"*, the rewrite cannot regress to *"orchestrated design-engineering tooling initiatives"* — that rewrite lost.

---

## Section 2 — Scope vocabulary (stack-specificity emphasized)

**Heuristic anchor: H-S08 (stack-specificity over category).** Per `references/heuristics.md` H-S08 verbatim: *"For design-engineer and similar hybrid roles, name the stack — React + Tailwind + Storybook with Figma tokens — not the category 'design systems.' Category-only positioning is a copy-paste-test failure for technical roles."* The stream-mining anchor is STREAM_MINING_RESUME.md §E3 (Tim verbatim, 11zGHBSfaXc L1149–1151): *"I'm a more technical space. The type of roles I'm looking for — that's just how I communicate. So that's how I've chosen to do that."* Bullet density and stack-specificity correlate at this role family — vague *"frontend"* / *"full-stack"* positioning fails the copy-paste test (any front-end designer's resume can claim "frontend") and surrenders the KSA-match advantage that named stacks earn (FEATURES §2.1 Design Engineer row, STREAM_MINING_RESUME.md §E7 verbatim Nate KSA-vocabulary list).

**Concrete stack vocabulary licensed for Design Engineer bullets:**

- **Component frameworks:** React, Vue, Svelte, SwiftUI, Compose, Web Components, Solid, Qwik
- **Styling systems:** Tailwind, CSS Modules, vanilla-extract, styled-components, Stitches, Linaria, Emotion
- **Design-system-as-code surfaces:** Storybook, Ladle, Histoire, design-tokens-as-code (Style Dictionary, Tokens Studio), CSS custom properties, Theo
- **Build / framework layer:** Next.js, Remix, Astro, Vite, Turbopack, Nuxt, SvelteKit
- **Bridging surfaces:** Figma plugins, Figma REST API integrations, Tokens Studio sync, Code Connect, Storybook–Figma integration
- **Prototyping stacks:** Framer (code), React Three Fiber, Lottie, Rive, Web Animations API, GSAP, Framer Motion
- **Testing & a11y:** axe-core, jest-axe, Playwright, Storybook a11y addon, Chromatic, Percy

**Anti-pattern: vague category-only positioning.** Per H-S08 and PITFALLS §1.4 (over-tooling — stack-specificity prescription verbatim: *"design engineer role-family preset specifies: stack specificity signals more than category — 'React + TypeScript + Figma tokens' beats 'front-end development.'"*), the failure mode looks like:

- *"Front-end development experience"* — fails copy-paste test; could apply to any front-end designer
- *"Modern web technologies"* — category-only; KSA-match-zero
- *"Built design systems"* — without naming the framework, token pipeline, or consumption surface
- *"Full-stack design"* — vague; suggests the candidate hasn't decided what part of the stack they actually own

**Scope phrases that earn their place (concrete, KSA-bearing):**

- *"Shipped 14 components in a React + TypeScript + Storybook design system consumed by 8 product teams"*
- *"Built a Figma plugin in TypeScript that synced 220+ tokens from Tokens Studio to a Style Dictionary pipeline"*
- *"Owned the Tailwind theme + design-token bridge across the Next.js marketing site and the React app"*
- *"Refactored 38 styled-components into a vanilla-extract recipe pattern; cut bundle size 18%"*
- *"Prototyped-in-code with Framer Motion to validate the gesture-driven onboarding before engineering scoped the build"*

The bullet earns its keep when swapping it onto another design engineer's resume would change the meaning. If the bullet survives the copy-paste test verbatim, the stack-specificity is missing.

---

## Section 3 — Common over-claims

Three patterns where Design Engineer candidates over-state contribution and set up an interview probe they can't survive.

**Over-claim 1 — "Built the design system" inflation.** Bullet says *"Built the design system from scratch"* when the actual contribution was 6 components added to a system someone else architected, or a token pipeline grafted onto an existing Storybook. **R-IDs:** R12 (claiming team win solo), R10 (seniority mismatch). The fix per common-flags.md R12 verbatim Nate (STREAM_MINING_RESUME.md §B1, 4tg1bPbOxus L762–765): *"You're not gonna claim sole ownership of [a project that wasn't yours alone]."* Surface the precision the bullet is hiding: *"Contributed 6 components and the icon-set token pipeline to the React + Storybook design system; total system maintained collaboratively by 3 design engineers + 2 staff designers."* The candidate keeps the credit they earned — the specific surface they actually owned — without claiming credit they didn't.

**Over-claim 2 — Production-engineering claim on prototype-only work.** Bullet says *"Shipped X feature"* when the artifact was a Framer prototype that informed the decision but never landed in production. The verb *shipped* is reserved for code in production — used loosely it sets up a hard interview probe (*"walk me through the deploy"* / *"what's your role in the on-call rotation for this surface?"*). **R-IDs:** R10 (seniority mismatch — bullet voice wrong for level), R02 (metric fabrication risk — when the candidate attaches production metrics to prototype work). The fix is verb precision per Section 1: *"Prototyped-in-code with Framer + React Three Fiber to validate the gesture-driven onboarding; engineering shipped the Production-React build the following quarter, retaining 80% of the prototype's interaction model."* The candidate gets credit for the prototype (real, valuable work) without claiming the production deploy.

**Over-claim 3 — Stack inflation on a thin surface.** Bullet name-checks 8 technologies (*"Built React + TypeScript + Tailwind + Storybook + Figma plugin + GraphQL + Vercel + design tokens"*) on what was actually a single landing page. The reviewer pattern-matches the inflation — recruiters who've seen many Design Engineer resumes recognize the resume-padding-via-stack-roster move on first read. **R-IDs:** R05 (tool-list noun salad), R11 (design process over-narration — inverse failure where method/tool listing replaces outcome), R02 (metric-fabrication-adjacent when stack inflation pairs with un-instrumented claims). The fix per common-flags.md R05 and voice.md §11.7 (no-keyword-stuffing): trim to the stack pieces actually load-bearing for the bullet's outcome. *"Shipped the marketing landing page in Next.js; integrated the existing design-token pipeline so brand updates propagate without engineering deploys."* The relevant stack pieces (Next.js, design-token pipeline) earn their mention; the unrelated stack pieces don't.

**Over-claim 4 — "Owned" as default verb without scope evidence.** Bullet leads with *"Owned"* on every line of the most-recent role: *"Owned the design system, owned the component library, owned the Figma plugin, owned the token pipeline."* The verb has stopped doing work — at scale, it reads as a claim the candidate doesn't have evidence for, and pairs with R10 senior over-claim direction. **R-IDs:** R10 (seniority mismatch), R12 (claiming team win solo). The fix is verb diversity anchored in actual scope: *"Owned the Auth-flow component set across the design system; contributed icon-pipeline tooling; co-led the design-token migration alongside the staff design engineer."*

---

## Section 4 — Common under-claims

Four patterns where Design Engineer candidates bury the signal that would actually win the role.

**Under-claim 1 — Burying the actual stack.** Candidate has a Senior Front-end Designer title and a list of bullets that read *"Designed and built features for the web app"* — without naming React, Vue, the design-system surface, or the token pipeline. The recruiter scans the resume and can't tell which front-end ecosystem the candidate operates in, and the resume gets discarded from the React-shop pile (or the Vue-shop pile, or the SwiftUI-shop pile) because there's no stack signal to match against. **R-IDs:** R09 (generic summary, wasted top-third — when the bury extends to the summary/header), R01 (activity bullet, no outcome — when the bury is paired with verb-only opener). The fix per H-S08 and Section 2 above: surface the stack at the bullet level. *"Designed and built 12 components in the Vue 3 + Pinia + Storybook design system; the components shipped to 4 product surfaces over 3 quarters."*

**Under-claim 2 — Hiding code-ownership scope.** Candidate authored or co-authored real production code, owns review on a real codebase, and is on-call for a real surface — but the resume reads like they sit beside engineering, not inside it. Bullets say *"Worked closely with engineers on..."* or *"Collaborated with the front-end team to..."* when the honest framing is *"Reviewed and shipped front-end PRs for the [surface]; on-call rotation alongside 3 engineers."* **R-IDs:** R08 ("we" overuse — hiding individual contribution), R10 (seniority mismatch — under-claim direction). The fix per common-flags.md R08 (STREAM_MINING_RESUME.md §B1, §B2): name the precise contribution. *"Authored 40+ PRs to the React component library over 18 months, including the popover and combobox primitives; reviewed code from 5 design engineers and 2 staff engineers as part of the design-system review rotation."*

**Under-claim 3 — Treating Figma-plugin / tooling work as side-project.** Candidate built a Figma plugin, a token-sync pipeline, a design-engineering Slack-bot, or a CI integration that real teams now depend on — and either (a) buries it in a side-projects section at the bottom of the resume, or (b) drops it entirely. **R-IDs:** R10 (under-claim variant — the senior who built infrastructure but framed it as IC craft), R11 (design process over-narration when the tooling work gets buried under method narration about how it was built rather than what changed because it was built). The fix per voice.md §11.3 *what changes because of you?*: surface the tooling work at proper scope. *"Built the Figma plugin (TypeScript + Figma REST API) that syncs 220+ design tokens from Tokens Studio into the Style Dictionary pipeline. Adopted by the design-systems team as the canonical sync mechanism; cut manual token-update time from ~2hr/release to <5 min."*

**Under-claim 4 — Quantifying craft work but not ownership.** Bullet says *"Built 14 components"* (a craft metric) but doesn't name the consumption surface (which products use them?), the team scope (who depended on you?), or the second-order effect (what changed because the components shipped?). At Design Engineer specifically, the consumption-surface count is the load-bearing scope signal — a component shipped to 1 internal tool reads differently than the same component shipped to 6 product surfaces with 4M MAU. **R-IDs:** R11 (process/method over-narration), R10 (seniority mismatch — under-claim direction). The fix per frameworks.md Scope-Impact-Metric and FEATURES §2.1 Design Engineer row (verbatim metric set: *"% a11y pass rate, component usage count, sprint velocity"*): *"Shipped 14 components in the React + Storybook design system; consumed across 6 product surfaces (combined ~4M MAU); a11y pass rate moved from 78% → 96% across the consumed surfaces post-adoption."*

---

## Section 5 — Voice-mismatch examples

Three ❌/✅ pairs targeting Design Engineer voice register failures.

**Pair DE-1 — Generic "front-end" positioning (Section 2 anti-pattern in action)**

❌ *"Experienced front-end developer with a passion for design systems and modern web technologies. Skilled in React, JavaScript, HTML, CSS, and various frameworks."*

✅ *"Senior Design Engineer, 5 years shipping React + TypeScript design systems at B2B SaaS scale. Owned the design-token pipeline (Style Dictionary + Tokens Studio + Figma plugin) at [company]; the system consumed across 8 product teams. Targeting Staff Design Engineer roles where the design-engineering seam is owned by one practitioner."*

*Failure mode:* category-only positioning, copy-paste test failure (R09), no stack-specificity. Replace with: named stack (React + TypeScript), named ownership surface (design-token pipeline + Style Dictionary + Tokens Studio + Figma plugin), named scope (8 product teams), named target (Staff Design Engineer, single-practitioner seam). Cite: H-S08 stack-specificity heuristic, voice.md §11.8 area-of-work labels.

**Pair DE-2 — "Built the design system" inflation (Section 3 over-claim 1 in action)**

❌ *"Spearheaded the company's design system from the ground up, leveraging modern web technologies to drive cross-functional alignment and elevate product quality."*

✅ *"Co-led the v2 React + vanilla-extract design system rebuild alongside 1 staff design engineer + 2 designers; authored the icon-pipeline tooling and the Auth + Billing component sets (12 of 38 system components). The system replaced the v1 styled-components implementation across 4 product surfaces; bundle size dropped 22% and Storybook a11y pass rate moved from 81% → 97%."*

*Failure mode:* banned AI verbs (*spearheaded, leveraging, drive, elevate*), R12 sole-ownership inflation, R02 missing-evidence metric-claim ("elevated product quality"). Replace with: precision verbs (*co-led, authored*), specific contribution scope (12 of 38 components, named ones), team composition (1 staff + 2 designers), stack-specific (React + vanilla-extract), real metrics (bundle size 22%, a11y 81→97%). Cite: voice.md §11.1 banned AI verbs, common-flags.md R12, frameworks.md Scope-Impact-Metric.

**Pair DE-3 — Hiding code-ownership scope (Section 4 under-claim 2 in action)**

❌ *"Worked closely with the engineering team to implement design solutions and ensure pixel-perfect handoffs."*

✅ *"Authored 60+ PRs to the Vue 3 + Pinia component library over 14 months, including the dialog, listbox, and date-picker primitives; reviewed front-end PRs from 4 engineers as part of the design-system review rotation. On-call rotation for the component-library Storybook + Chromatic CI."*

*Failure mode:* R08 "we" overuse / passive collaboration framing, R01 activity-only, no stack signal, no contribution count. Replace with: named primitives shipped (dialog, listbox, date-picker), authorship count (60+ PRs), review-loop participation (4 engineers, design-system rotation), on-call ownership (Storybook + Chromatic CI). The bullet now demonstrates code-ownership scope rather than collaboration-adjacent framing. Cite: common-flags.md R08, R01; voice.md §5 (quote the user's own copy + name the user's specific work).

---

## Section 6 — ATS keyword cluster

Per voice.md §11.7 (no-keyword-stuffing) and SPEC D-21-RR: write for the hiring design manager; modern ATS follows. Keyword inclusion at Design Engineer happens **inside bullets via honest action — not as a separate skills-section pile**. The cluster below is the vocabulary that earns its place when it appears in context. Per D-21-RR / voice.md §11.8: **specific stacks beat category names**. Always.

**Component frameworks (specific, not category).** *React, React Server Components, Vue 3, Svelte, SvelteKit, SolidJS, Qwik, Astro, Web Components, Lit, SwiftUI, Jetpack Compose.* Anti-pattern: *"front-end frameworks"* / *"modern JavaScript frameworks."*

**Styling and tokens (named, not category).** *Tailwind CSS, CSS Modules, vanilla-extract, styled-components, Stitches, Emotion, Linaria, CSS custom properties, Style Dictionary, Tokens Studio, Theo, design tokens, theming.* Anti-pattern: *"CSS"* / *"styling systems."*

**Design-system surfaces (named, not category).** *Storybook, Ladle, Histoire, Chromatic, Percy, Code Connect, design-system-as-code, component library, design-tokens-as-code, monorepo (Turborepo, Nx), pnpm workspaces.*

**Build, framework, deploy (named, not category).** *Next.js (App Router, Pages Router, Server Components), Remix, Vite, Turbopack, esbuild, Vercel, Netlify, Cloudflare Pages, edge runtime, ISR, SSG, SSR.* Anti-pattern: *"deployment pipelines"* / *"modern build tools."*

**Figma + design-engineering bridge.** *Figma plugin, Figma REST API, Figma Variables, Code Connect, Tokens Studio sync, design-token pipeline, Figma-to-code workflow, Storybook–Figma integration.* This cluster is high-signal at Design Engineer specifically — recruiters scan for it because it indicates the candidate operates at the seam, not adjacent to it.

**Prototyping (named, not category).** *Framer (code), React Three Fiber, Three.js, Lottie, Rive, GSAP, Framer Motion, Web Animations API, anime.js, View Transitions API, motion design.*

**Testing + accessibility (named, not category).** *axe-core, jest-axe, Storybook a11y addon, Playwright, Cypress, Vitest, Jest, ARIA, WCAG 2.1 AA, screen reader testing (VoiceOver, NVDA), keyboard navigation, focus management.*

**Languages and adjacent.** *TypeScript, JavaScript (ES2022+), HTML5, CSS3, GraphQL, REST APIs, JSON, Node.js, Bun, Deno.*

The keyword cluster is **not a copy-paste skills section.** Per common-flags.md R05 (tool-list noun salad) and voice.md §11.7: tools land inside bullets where they're doing semantic work. A skills section that lists every tool above unsorted is a downgrade signal. The cluster's job is to seed bullet-level vocabulary; the bullet's job is to demonstrate the tool in honest action.

<!-- GAP: STREAM_MINING_RESUME.md does not contain a Design-Engineer-specific reviewee transcript that anchors a verbatim Tim/Nate flag of stack-specificity vs category positioning. The closest anchor is §E3 (Tim verbatim on technical-space bullet density) and §E7 (Nate KSA-vocabulary list), which establish the principle but not a Design-Engineer-bullet-shape worked example. v1.1+ corpus mining should look for Design-Engineer-track resume reviews that surface stack-specificity as a named flag. -->

---

> *This is not Tim or Nate speaking — it's an approximation built from publicly shared review patterns. For a direct review, join the Friday stream: [Friday stream link].*
