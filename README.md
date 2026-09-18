# slop-design v3.5.0

Design reference contract of 245 AI slop anti-patterns across 18 categories, for AI agents
to read **before** generating UI — paired with a construction workflow, token tables, and a
blocking pre-emit gate.

**Core objective, all domains:** avoid low-effort "AI-generated template" tropes, boilerplate
Bootstrap/SaaS defaults, and unstyled third-party widgets. Every layout must feel deliberate,
bespoke, and tailored to the actual product domain. A pattern that would be correct for one
product is a defect in another — judge fit, not tidiness.

This skill is a **knowledge base only**. It does not scan, track, or fix anything — the
operational counterpart `slop-audit` does that. Loading this one changes what gets
written in the first place.

## Two Surfaces

Seventeen of the eighteen categories describe the **rendered artifact** — every one of them can be judged from a screenshot. The eighteenth, **Engineering (E1-E58)**, describes the **source** that produced it, and none of it is visible in the render.

The failure modes are independent. A page can pass every render-side check and still leak a secret, race a fetch, and carry `any` through its entire boundary — it looks finished. A page with immaculate source can still be visually generic — well-built slop. **A deliverable is not done because the screenshot is good.** Scan both.

## Loading

```bash
/skill slop-design
```

Then read `references/slop-patterns.md` and check each design decision against the catalog
before emitting code.

Then read `references/design-spec.md` — the catalog says what not to build, the spec says
how to build: the 5-stage workflow, motion/colour/type token tables, and the pre-emit gate
that blocks delivery on a failed check. `references/code-slop-guide.md` covers the E category
— grep signatures, per-framework equivalents, and the enforcement checklist.
`references/prompt-library.md` holds copy-paste activation prompts for each stage.

## Role

Act as an elite Creative Director and Lead UI/UX Frontend Architect.

**Core objective, all domains:** avoid low-effort "AI-generated template" tropes, boilerplate
Bootstrap/SaaS defaults, and unstyled third-party widgets. Every layout must feel deliberate,
bespoke, and tailored to the actual product domain.

**Tightened standard for ultra-luxury hospitality, Michelin-grade culinary estates, and
architectural web design:** reject the low-effort grammar of automated website builders, SaaS
dashboards, and food-delivery aggregators.

The domain test for every element is not "does this look designed" but:

> Does this say *"this place exists"*, or *"this place is listed"*?

Anything that reads as a listing is the defect, however polished it is.

## Pattern Catalog

| Category | Patterns | Key Avoidances |
|----------|----------|----------------|
| Visual | V1-V21 | Border accent + radius, glassmorphism, generic icons, extreme radius, mixed icon styles, placeholder images in production, border-as-hierarchy crutch, ungraded embeds, unscrimmed ambient video, geometric mask faking an organic cutout |
| Typography | T1-T18 | Flat hierarchy, oversized headlines, all-caps body, single font, mismatched pairing, "it's not just X it's Y", buzzword stacking, em-dash overuse, fake urgency, rule-of-three, proportional numerals in tables, untracked uppercase, no modular scale |
| Color | C1-C11 | Purple/violet gradients, glowing dark accents, gradient text, gray on colored, cream reflex, WCAG AA failures, pure `#000`/`#fff` planes, zero-chroma neutrals, full-chroma dark fills, unassigned colour roles, the warm-neutral-plus-terracotta palette reflex |
| Layout | L1-L13 | Identical card grids, monotonous spacing, nested cards, line length >80ch, overflow, clipped children, div-soup, default 50/50 split reflex, orphan grid cells, hero below the fold, CTA competition |
| Motion | M1-M18 | Bounce easing, layout-property animation, hover transforms, blanket scroll-fade, uniform 300ms, hover-scale on non-interactive, no `prefers-reduced-motion`, staggered-reveal cliché, `transition: all`, animated high-frequency actions, ease-in entrances, motion-only state, untuned easing curve, `scale(0)` entry, keyframes on a retriggerable surface, origin-blind popover, unbounded stagger, ungated hover motion |
| Copy | P1-P9 | Em-dash overuse, buzzwords, aphoristic cadence, theater framing, "it's not just X it's Y", fake urgency, rule-of-three |
| Imagery | I1-I6 | Broken/placeholder images, stock-photo tells, AI artifacts, mixed icon styles, inconsistent aspect ratios (standardize 1:1 catalog, 16:9 landscape, 4:5 portrait, always `object-fit: cover`) |
| Quality | Q1-Q10 | Cramped padding, viewport-edge text, justified text, low contrast, skipped headings, tight leading, tiny text, wide tracking, **contract-breaking refactor**, unthemed browser surfaces |
| Composition | X1-X10 | Motion saturation, decorative priority inversion, redundant UX writing, modal abuse, page-archetype uniformity, no visual anchor, unbroken zigzag, split-header reflex, unearned production chrome, numbered-pagination chrome |
| Accessibility | A1-A16 | Missing alt text, contrast, no focus state, div-soup, broken keyboard nav, unlabeled inputs, color-only status, missing ARIA, clickable non-interactive elements, positive `tabindex`, modal without a focus trap, unlabeled icon-only controls, decorative SVG not hidden, autofocus on load, `title` as the only label, error state with no `aria-describedby` |
| Design-Token | D1-D6 | Multiple radii for one component, hardcoded hex/px, off-scale spacing, off-scale type, divergent shadows, near-duplicate hex |
| State Coverage | S1-S8 | Empty, loading, skeleton mismatch, error, disabled, partial-data, permission-gated, offline |
| Real-Content Stress | R1-R6 | Long text overflow, list scale, mismatched lengths, number edge cases, image fallback, RTL/special chars |
| Responsive | B1-B5 | Breakpoint drift, touch targets <44/48px, unintended horizontal scroll, disappearing functionality, fixed px widths |
| Interaction Feedback | F1-F7 | Async without loading, destructive without confirm, no success feedback, double-submit, unmapped validation errors, missing hover/focus/active, **hover-locked essential data** |
| Dark Mode Parity | DM1-DM5 | Contrast not re-checked, inverted-only icons, semantic colors not re-tuned, broken elevation, light/dark layout drift |
| **Engineering (source)** | E1-E58 | Derived or duplicated state, effects with no cleanup, fetch in `useEffect` with no abort and no error branch, `'use client'` on the root, god components, prop drilling, index keys, `any`/`@ts-ignore`/`!` at the trust boundary, secrets in client code, `dangerouslySetInnerHTML` on user input, unvalidated boundaries, unsized media, render-blocking font links, no test on a money/auth/parse path, dead code |
| Hospitality / Luxury | H1-H18 | See below |

## Generic Anti-Patterns (all domains)

Six patterns carry the core objective. Each has a hospitality counterpart — report at the
scope of the target, never both.

| ID | Defect | Correction | Hospitality |
|----|--------|-----------|-------------|
| **V18** | Border-as-hierarchy crutch — a border drawn around every text block to separate it | Hierarchy is typographic: size, weight, letter-spacing, and muted opacity (`0.6`–`0.8`) | H8 (inverse) |
| **V19** | Ungraded third-party embed — map, calendar, calculator left in its vendor palette | CSS filter stack, custom color overlay, or the vendor's own theme | H17, H4 |
| **V20** | Unscrimmed ambient video — no calibrated scrim, or text legible on frame 1 only | Calibrated linear **and** radial gradient scrims; AAA contrast on every frame | H11 |
| **L10** | Default 50/50 split reflex — every section text-left / media-right in an unvarying half-and-half box | Full-width banners, asymmetric 40/60, tabular rows, or an interactive multi-panel viewport | H18 |
| **F7** | Hover-locked essential data — price, spec, or primary action only in a hover drawer | Static presence; hover may add, never gate. Essential info must work on touch | H7 |
| **Q9** | Contract-breaking refactor — classes, IDs, or `data-*` attributes renamed or removed while JS, data fetching, or event listeners still reference them | Diff the selectors the JS uses against the markup before clearing a style refactor. **Blocker, Stage 1** | none — both scopes |

Also generic and binding at both scopes:

- **No fake browser/app chrome** unless the product genuinely is an OS or browser simulator.
- **No unstyled third-party widgets** — maps, calendar widgets, calculators.
- **No icon-in-a-circle stack** as the default way to present key-value facts.
- **Preserve domain truth** — never invent physical, architectural, or logistical features.

### Font pairing — match the typeface to the identity

Mixing a geometric/bubbly sans with a classic or formal face is the defect.

- *Clean / technical:* neutral, balanced sans-serifs — Plus Jakarta Sans, Manrope, Inter
- *Editorial / refined:* a high-contrast serif with a restrained humanist sans — Cormorant Garamond with Tenor Sans or Plus Jakarta Sans

**Inter is not banned.** T8 flags it as an *identity default*; H6 flags it as a *pairing*
against a display serif. Inter is correct for a clean/technical product identity with brand
justification. Report only where it is an unjustified default or a mismatched pairing.

## Hospitality / Luxury Domain (H1-H18)

Scope: ultra-luxury hospitality, Michelin-grade restaurants, architectural destination
venues only. SaaS, dashboards, dev tools, and aggregators do not trigger these.

**ID blocks:** forbidden patterns are H1-H7 and H13-H15 (detected by presence); mandatory
codes are H8-H12 and H16-H18 (detected by absence of the required treatment). IDs are
stable — new patterns append, they never renumber.

**Forbidden:**
- **H1** card-grid aggregation — rows of identical rounded cards, cropped image headers, plain text bodies. Second tell: box-in-a-box thumbnail (a photo with its own radius inside a card that already has border + radius)
- **H2** generic status pills — pulsing green/red dot, "Open Today • 12:00 PM – 11:30 PM". Reads as an automated server health monitor
- **H3** fake chrome around media — mock window headers, tab strips, `Sky Hi Dining • Live Map` bars. Exempt only when the product genuinely is an OS or browser simulator
- **H4** raw embedded maps — pastel roads, yellow highways, cyan water in a dark palette
- **H5** circular icon lists — pin, telephone, clock, car in tinted circles beside contact rows
- **H6** fintech sans pairing — Outfit/Poppins/Inter/DM Sans/Montserrat against a luxury serif. A *pairing* rule, not a ban on Inter (that is T8)
- **H7** hover-gated core content — dish photos, ingredients, tasting notes, pricing behind a hover reveal. Unreachable on touch. Generic case: F7
- **H13** commerce price and tag pills — a price (`₹200`), tag, or category trapped in a rounded pill, chip, or grey button box
- **H14** retail menu chrome — search toolbar, pill filter chips, "Expand All" on a dining menu
- **H15** spatial/factual hallucination — "rooftop venue", "high-rise", "skyline balcony" claimed for a ground-level estate; invented floors, views, capacity. **Blocker, no exemption**

**Mandatory codes (absence is the defect):**
- **H8** canvas over card — full-bleed planes, `1px solid rgba(223, 191, 108, 0.18)` hairlines, asymmetric split viewports
- **H9** editorial typographic scale — Roman/serif numerals ("01"), tracking `0.2em`, small caps
- **H10** discreet dietary indicators — 4-6px glowing jewel dot in a glass disc, not a VEG badge or an FSSAI bordered square
- **H11** cinematic media integration — linear + vignette scrims bleeding into the palette; footage slow, atmospheric, low-contrast
- **H12** tabular concierge hierarchy — key left in tracked uppercase sans, Cormorant Garamond value right
- **H16** architectural signature footer — masthead, direct telephone booking line (`tel:`), tabular nav, low-opacity watermark brand stamp
- **H17** curated third-party grading — every embed graded to the palette and asymmetrically framed, never a 50/50 box split. `filter: invert(92%) hue-rotate(185deg) saturate(35%) brightness(78%) contrast(125%);`
- **H18** page-archetype uniformity — one generic template site-wide; each page owns its venue-logic architecture. Tell: every section a 50/50 split (generic case: L10)

**Application order when generating:** truth (H15) → canvas (H8) → page archetype (H18) →
media (H3/H4/H11/H17) → structure (H1/H5/H12/H16) → type (H6/H9) → indicators
(H2/H10/H13/H14) → content presence (H7). Skipping truth produces a beautiful site that
lies about the building — the one defect no redesign recovers from.

**Before any style refactor, apply Q9:** never rename, remove, or modify existing classes,
IDs, or `data-*` attributes when JS, data fetching, or event listeners depend on them.
Stage 1 blocker at both scopes.

Full contract — section-by-section archetype ledger for menu, dish, experience, location,
footer, menu page, events, and gallery; pre-emit checklist; exemption rules; supersession
table; generic ↔ hospitality mapping: `references/luxury-hospitality-protocol.md`.

## Reference Files

- `references/slop-patterns.md` — full 245-pattern catalog across 18 categories, including the E1-E58 source-code block and the H1-H18 hospitality block, convergence pairs, fix order, and the generic ↔ hospitality mapping
- `references/design-spec.md` — construction-side counterpart: Stage 1 brief (design read + three dials), motion/colour/type token tables, build rules, polish passes, Stage 5 pre-emit gate, evidence labels, and the completion rule. Byte-identical in both skills
- `references/code-slop-guide.md` — E-category detection method: grep signatures, per-framework equivalents, lint rules, pre-commit checklist, and the scope/honesty limits. Byte-identical in both skills
- `references/prompt-library.md` — 10 copy-paste activation prompts (strategy pass, landing, dashboard, typography, bento, motion, colour, redesign audit, hero, final gate) plus the rejected prompt sets and why
- `references/luxury-hospitality-protocol.md` — H1-H18 design contract: forbidden patterns, mandatory codes, section ledger, pre-emit checklist, exemptions, supersession, mapping
- `references/content-quality-guidelines.md` — quality standards for content evaluation
- `references/regex-debugging.md` — regex debugging notes for the operational scan script

## What v3.5.0 added

78 patterns, append-only; no ID renumbered, H-IDs untouched.

**The new source surface.** Categories V/T/C/L/M/P/I/Q/X/A/D/S/R/B/F/DM/H all describe a rendered artifact. The new **E category (E1-E58)** describes the source, across ten sub-blocks: state and effects (E1-E6), data fetching (E7-E13), lifecycle and leaks (E14-E18), component architecture (E19-E25), TypeScript (E26-E31), markup and styling (E32-E37), security and privacy hygiene (E38-E43), performance and framework (E44-E50), testing and project structure (E51-E55), form handling (E56-E58). Companion: `references/code-slop-guide.md`.

**Blockers.** E38, E39, and E41-E43 join Q9 and H15 in the Stage 1 tier. Where the input is user-controlled they outrank every aesthetic finding — a leak or an unvalidated boundary is not a polish item.

**Extended categories:**

| New | Pattern | Distinct from |
|-----|---------|---------------|
| M14 | `scale(0)` entry | M1 (overshoot curve) — this is the start value |
| M15 | Keyframes on a retriggerable surface | No prior ID — restart vs retarget |
| M16 | Origin-blind popover | No prior ID — transform origin |
| M17 | Unbounded stagger | M8 (reveal on non-list) — this is the delay budget |
| M18 | Hover motion ungated by pointer type | No prior ID — input capability |
| C11 | Warm-neutral-plus-terracotta palette reflex | C5 (surface only) — this is the whole scheme arriving without a reason |
| V21 | Geometric mask faking an organic cutout | No prior ID — mask provenance |
| Q10 | Unthemed browser surfaces | No prior ID — selection, caret, scrollbar, focus ring |
| X7 | Unbroken zigzag alternation | X5 (page-level uniformity) — this is the split reflex repeating |
| X8 | Split-header reflex | X5 — header shape not decided by content |
| X9 | Unearned production chrome | No prior ID — furniture carrying no information |
| X10 | Numbered-pagination chrome | L5 (numbering that is real information) |
| A9-A16 | Clickable non-interactive element; positive `tabindex`; modal without a focus trap; icon-only control with no name; decorative SVG not hidden; autofocus on load; `title` as the only label; error state with no `aria-describedby` | Keyboard, focus management, and the programmatic half of the state model |
| E1-E58 | Source-code slop | The source surface, separate from the render |

**New discipline.** Every material statement carries an evidence class — **Observed**, **Measured**, **Inferred**, or **Unknown**. Never promote inferred or unknown material into a factual claim, and never infer authorship from style alone. The **completion rule** bounds the pruning instinct: stop removing when the next removal would reduce task completion, comprehension, evidence, identity, component or interaction behavior, action discoverability, migration safety, or accessibility.

Also: `references/design-spec.md` gained the design read, the three dials (variance 8 / motion 6 / density 4 baseline), the motion-physicality rules, the browser-surface theming floor, the source-discipline bullets in Stage 3, and the evidence/completion blocks in Stage 5.

## What v3.4.0 added

17 patterns, append-only; no ID renumbered, H-IDs untouched.

| New | Pattern | Distinct from |
|-----|---------|---------------|
| M9 | Blanket `transition: all` | M2 (layout properties) — this is *unnamed* properties |
| M10 | Motion on a high-frequency action | No prior ID |
| M11 | Entrance on ease-in or >300ms | M5 (duration uniform) — this is direction and length |
| M12 | Motion-only state indication | A7 (colour-only) — inverse medium |
| M13 | Untuned default easing curve | M5 — curve axis vs duration axis |
| C7 | Pure black/white surfaces | C2 (glow) — this is the surface floor |
| C8 | Zero-chroma neutrals | No prior ID |
| C9 | Full-chroma accent fill on dark | C2 (glow) — this is fill saturation |
| C10 | Palette with no role assignment | Only in replacement prose before |
| T16 | Proportional numerals in tabular context | No prior ID |
| T17 | Uppercase label without tracking | Q8 — inverse axis |
| T18 | No modular type scale | D4 — absence vs drift |
| L11 | Orphan or decorative grid cell | L2 — count mismatch vs identical siblings |
| L12 | Above-the-fold hero overflow | No prior ID |
| L13 | CTA competition | No prior ID |
| X5 | Page-level archetype uniformity | H18 — generic scope |
| X6 | No visual anchor | No prior ID |

Also: the X1-X6 detail block was missing from this skill's `pattern_catalog_detail` and is now present, and the construction references (`design-spec.md`, `prompt-library.md`) were added.

## Related Skills

- `slop-audit` — operational counterpart: scans, tracks, and fixes slop in existing code
- `content-pipeline` — AI UGC video production (may generate slop)
- `capture` — note capture workflow
- `gsd:progress` — GSD progress checking and routing
