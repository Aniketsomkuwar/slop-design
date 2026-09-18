---
name: slop-design
description: Design reference contract of 245 AI slop anti-patterns across 18 categories (V/T/C/L/M/P/I/Q/X/A/D/S/R/B/F/DM/H/E) for AI agents to read BEFORE generating UI, paired with a construction workflow, motion/colour/type token tables, and a blocking pre-emit gate. Core objective — avoid low-effort AI-template tropes, boilerplate Bootstrap/SaaS defaults, and unstyled third-party widgets; every layout must feel deliberate, bespoke, and tailored to the actual product domain. Contains forbidden-pattern catalogs, a 5-stage design workflow, OKLCH colour rules, a motion budget table, replacement principles, a pre-emit checklist, a copy-paste activation prompt library, the H1-H18 luxury hospitality contract (canvas over card, editorial numerals and dot-leader price ledgers, jewel-dot dietary marks, video scrims, concierge dossier, architectural signature footer, graded third-party embeds, per-page archetypes, spatial-truth verification), and the E1-E58 source-code contract (React state and effects, data fetching, lifecycle and leaks, component architecture, TypeScript quality, markup and styling, security and privacy hygiene, performance, testing, and form ownership). Use before building or redesigning any UI, when writing React/Next.js/TypeScript source that should not read as generated, and always for luxury hospitality, Michelin-grade restaurant, or destination-venue work.
version: "3.5.0"
argument-hint: "[--scan] [--list] [--clear]"
allowed-tools:
  - Read
  - Write
  - Grep
  - Glob
  - AskUserQuestion
---

<objective>
Provide comprehensive design reference for AI-assisted UI generation, documenting 245 AI slop patterns across 18 categories (Visual, Typography, Color/Contrast, Layout/Space, Motion, Copy, Imagery, Quality, Composition, Accessibility, Design-Token, State Coverage, Real-Content Stress Test, Responsive Consistency, Interaction Feedback, Dark Mode/Theme Parity, Hospitality/Luxury, Engineering/Source-Code). This skill serves as the design knowledge base that AI agents read before generating UI, while slop-audit serves as the operational skill that detects and tracks slop in existing codebases. Extends v3.2.0 with six generic patterns that apply to every product domain — V18 border-as-hierarchy crutch, V19 ungraded third-party embed, V20 unscrimmed ambient video, L10 default 50/50 split reflex, F7 hover-locked essential data, and Q9 contract-breaking refactor (blocker) — plus the H13-H18 hospitality block and a generic↔hospitality mapping so the same defect reports at the right scope. v3.4.0 adds 17 patterns (motion M9-M13, colour C7-C10, typography T16-T18, layout L11-L13, composition X5-X6), the previously missing X1-X6 detail block, and pairs the catalog with two construction-side references: `references/design-spec.md` (5-stage workflow, motion/colour/type token tables, blocking pre-emit gate) and `references/prompt-library.md` (copy-paste activation prompts). v3.5.0 adds 78 patterns: the **Engineering category E1-E58** for source-code slop — React state and effects, data fetching, lifecycle and leaks, component architecture, TypeScript quality, markup and styling, security and privacy hygiene, performance and framework handling, testing and project structure, form ownership — plus A9-A16 (code-level accessibility), C11 (premium-consumer palette reflex), M14-M18 (physical motion), V21 (geometric mask faking an organic cutout), Q10 (unthemed browser surfaces), and X7-X10 (zigzag cap, split-header reflex, unearned production chrome, pagination chrome). Paired with `references/code-slop-guide.md` and a design-read plus three-dial brief in `references/design-spec.md`.
</objective>

<role>
Act as an elite Creative Director and Lead UI/UX Frontend Architect.

**Core objective, all domains:** avoid low-effort "AI-generated template" tropes,
boilerplate Bootstrap/SaaS defaults, and unstyled third-party widgets. Every layout must
feel deliberate, bespoke, and tailored to the actual product domain. A pattern that would
be correct for one product is a defect in another — judge fit, not tidiness.

**Tightened standard for ultra-luxury hospitality, Michelin-grade culinary estates, and
architectural web design:** reject the low-effort grammar of automated website builders,
SaaS dashboards, and food-delivery aggregators outright. Every component answers to
bespoke, editorial haute-hospitality standards. The domain question for every element is
**"does this say *this place exists*, or *this place is listed*"** — anything that reads
as a listing is the defect, however polished.
</role>

<routing>

| Flag | Action | Description |
|------|--------|-------------|
| (none) | Scan mode | Scan files for slop indicators (operational skill) |
| --list | List tracked slop items | Show all previously identified slop with status, grouped by category |
| --clear | Clear resolved slop entries | Remove tracked slop items from storage |
| --scan PATH | Scan specific path | Run operational scan (slop-audit) |

</routing>

<process>

<step name="init_context">
Ensure directories exist in the project being scanned (current working directory):
```bash
# All data stored in the current working directory — never in a global/home path
mkdir -p ./.slop-tracker
mkdir -p ./.slop-tracker/references
mkdir -p ./.slop-tracker/notes
```
</step>

<step name="reference">
Provide design reference for AI-assisted UI generation. Show pattern catalog with all 245 patterns across 18 categories. Every finding uses evidence model (Source/Render/Judgment/Confidence) plus severity (blocker/major/nit) and auto_fix boolean tag, logged to slop-log.json under D-category (Design-Token/Drift).
</step>

<step name="workflow">
This skill is the *reference* half. The *construction* half is `references/design-spec.md`, and the catalog only works when the two run together — the catalog says what not to build, the spec says how to build instead.

Run the spec's stages in order:

1. **Brief** — state the one-line Design Read, then decide mode, audience, mood, density, variance, motion intensity, banned list, and the single visual idea, before any markup exists. Record in `.slop-tracker/design-brief.md`.
2. **Constraints** — define motion, colour, and type tokens before components. Components built first inherit ad-hoc values, which is D1-D6 drift by construction.
3. **Build** — structure follows content; one anchor per section; grid composed from content; states and feedback are part of the component. Build the source with the same discipline: derive rather than synchronise state, declare every effect's cleanup, ship all four fetch branches, validate at the boundary, and keep secrets out of the client.
4. **Polish** — type pass, colour pass, motion pass, copy pass, in that order.
5. **Gate** — run the Stage 5 checklist. A failure blocks delivery; it is not a note.

The E-category (E1-E58) is the source-side half of the same contract. The render can pass
every visual check while the source leaks a secret, races a fetch, or carries `any` through
its boundary. Read `references/code-slop-guide.md` before writing React, Next.js, or
TypeScript source — it carries the grep signatures and the per-framework equivalents.

For copy-paste activation prompts per stage, see `references/prompt-library.md`. For hospitality targets, the H1-H18 step order supersedes and the truth step runs first.
</step>

</process>

<pattern_catalog_summary>
Total patterns: 245

Visual: V1-V21 (21 patterns)
Typography: T1-T18 (18 patterns)
Color and Contrast: C1-C11 (11 patterns)
Layout and Space: L1-L13 (13 patterns)
Motion: M1-M18 (18 patterns)
Copy: P1-P9 (9 patterns)
Imagery: I1-I6 (6 patterns)
General Quality: Q1-Q10 (10 patterns)
Composition: X1-X10 (10 patterns)
Accessibility: A1-A16 (16 patterns)
Design-Token / Drift Detection: D1-D6 (6 patterns)
State Coverage: S1-S8 (8 patterns)
Real-Content Stress Test: R1-R6 (6 patterns)
Responsive/Breakpoint Consistency: B1-B5 (5 patterns)
Interaction Feedback Audit: F1-F7 (7 patterns)
Dark Mode / Theme Parity: DM1-DM5 (5 patterns)
Hospitality / Luxury: H1-H18 (18 patterns)
Engineering / Source-Code: E1-E58 (58 patterns)

Render-side total (V/T/C/L/M/P/I/Q/X/A/D/S/R/B/F/DM/H): 187
Source-side total (E): 58

</pattern_catalog_summary>

<pattern_catalog_detail>

### Visual Details (V1-V21)
- V1: Border accent on rounded element (>=2px border + >=12px radius)
- V2: Glassmorphism everywhere (translucent cards + backdrop-filter: blur)
- V3: Side-tab accent border (colored border >=3px on card side)
- V4: Hairline border with wide shadow (1px border + >=20px shadow blur)
- V5: Repeating-gradient stripes on surfaces
- V6: Extreme border radius (>=24px turns cards into blobs)
- V7: Amateurish hand-drawn SVG (complex inline SVG with rough geometry)
- V8: Generic AI icons (sparkle, star, magic, lightning, diamond, robot, AI orb)
- V9: Lucide icons (every icon from same thin-stroke library)
- V10: Colored left stripe (thin vertical bar on card/section edges)
- V11: Small arrows (→/↗) on almost every button as decoration
- V12: AI capsule badges (pill shape, thin border, glow, uppercase "AI Powered", etc.)
- V13: Generic AI typography (large monospace headings, HOW IT WORKS uppercase with wide tracking)
- V14: Typeface chosen without reason (font picked as AI default, not brand fit)
- V15: Generic illustrations (Undraw, Storyset, 3D blob with no product connection)
- V16: Mixed icon styles in one view (outline + filled + duotone)
- V17: Leftover placeholder images (lorem-picsum, unsplash-random) in production build
- V18: Border-as-hierarchy crutch (a border or outline drawn around every text block, card, and label instead of establishing hierarchy typographically). Fix: font size, weight, letter-spacing, muted opacity `0.6`–`0.8`. Reserve borders for structural separation
- V19: Ungraded third-party embed (raw default-styled map, calendar, calculator, booking or chat widget dropped into a custom palette with no filter stack, overlay, or vendor theme)
- V20: Unscrimmed ambient video (video as section underlay with no gradient overlay, so foreground text contrast varies frame to frame). Fix: calibrated linear **and** radial scrims, verified for AAA contrast across every frame
- V21: Geometric mask faking an organic cutout (a circle, polygon, or radial-gradient cutout approximating a photographic subject's edge, so the subject appears cropped by a shape it does not match). Fix: derive an alpha matte from the actual image, or produce a real cut-out asset — the geometric approximation reads worse than omitting the effect

### Typography (T1-T18)
- T1: Flat type hierarchy (adjacent roles differ <1.25x, lack contrast)
- T2: Icon tile stacked above heading (repeated feature cards)
- T3: Italic serif display headline (serif italic >=32px in generic startup hero)
- T4: Hero eyebrow or pill chip (tracked uppercase text above hero heading)
- T5: Repeated section kickers (3+ sections with same uppercase tracked label)
- T6: Oversized hero headline (8+ words with >=48px or text-5xl styling)
- T7: Crushed letter spacing (display tracking < -0.05em, body with negative tracking)
- T8: Overused font (Inter, Geist, Space Grotesk, Instrument Serif as default identity)
- T9: Single font for everything (one family with identical weight/width/spacing across roles)
- T10: All-caps body text (paragraphs/long blocks >=20 words in uppercase)
- T11: "It's not just X, it's Y" / "more than just a Z" construction
- T12: Buzzword stacking (seamless, leverage, unlock, elevate, robust, cutting-edge)
- T13: Em-dash overuse as a sentence-structure crutch (3+ em-dashes in body block)
- T14: Inflated fake urgency/stats with no source ("only 3 spots left", "10,000+ happy customers")
- T15: Rule-of-three headline tic ("Fast. Reliable. Secure.")
- T16: Proportional numerals in tabular context (metrics, prices, dates, or table columns rendering with default proportional figures, so digit widths vary and the column jitters as values update). Fix: `font-variant-numeric: tabular-nums` on any figure read in a column or refreshed in place
- T17: Uppercase label without compensating tracking (uppercase micro-labels — eyebrows, table headers, badges — at default or negative tracking, so letters crowd). Fix: 0.05em–0.12em. Q8 is the inverse defect — wide tracking on running body copy
- T18: No modular type scale (sizes chosen ad hoc per component, no ratio relating adjacent roles, so hierarchy is accidental). Fix: roles (display/heading/body/label/data) on one ratio, commonly 1.2–1.333. D4 is the *drift* case — a defined scale that components ignore. Report T18 only when no scale exists to drift from

**Font pairing — match the typeface to the identity.** Mixing a geometric/bubbly sans with a classic or formal face is the defect.
- *Clean / technical:* neutral, balanced sans-serifs — Plus Jakarta Sans, Manrope, Inter
- *Editorial / refined:* a high-contrast serif with a restrained humanist sans — Cormorant Garamond with Tenor Sans or Plus Jakarta Sans

**Inter is not banned.** T8 flags it as an *identity default*; H6 flags it as a *pairing* against a display serif. Inter is correct for a clean/technical product identity with brand justification. Report only where it is an unjustified default or a mismatched pairing.

### Color and Contrast (C1-C11)
- C1: AI color palette (purple/violet gradients or cyan-on-dark without brand evidence)
- C2: Dark mode with glowing accents (dark surfaces with colored box shadows/neon text)
- C3: Gradient text (background-clip: text + transparent fill on headings/metrics)
- C4: Gray text on colored background (neutral gray on chromatic surface, loses contrast)
- C5: Cream/beige reflex (warm off-white as whole page's generic surface without palette)
- C6: Contrast failing WCAG AA (<4.5:1 normal text, <3:1 large text)
- C7: Pure black/white surfaces (`#000` background or `#fff` surface used as-is — no tint, no lifted floor). Pure `#fff` on pure `#000` produces halation and destroys perceived depth. Fix: tint neutrals toward the brand hue and lift the dark floor, e.g. `oklch(0.18 0.012 250)`
- C8: Zero-chroma neutrals against a chromatic brand (the neutral ramp sits at 0 chroma while the brand hue is saturated, so greys read as a second, unrelated system). Fix: a small chroma at the brand hue, generally well under half the brand's chroma
- C9: Full-chroma accent fill on a dark surface (brand accent at maximum saturation as a large fill, so it vibrates against the surface). Fix: lower chroma and lift lightness for dark-mode fills; keep full chroma for small indicators only. C2 is *glow* (shadow, neon text); C9 is *fill saturation*
- C10: Palette with no role assignment (colours exist as a flat hex list; nothing distinguishes brand, action, status, emphasis, and surface). Detected by absence. Fix: give every colour a job and name the token after the job, not the hue. Report when one chromatic colour serves two jobs, or when status and action share a colour
- C11: Premium-consumer palette reflex (the page lands on the same "tasteful" warm-neutral-plus-terracotta scheme with no brand evidence — backgrounds in the `#f5f1ea`/`#f7f5f1`/`#fbf8f1`/`#efeae0`/`#ece6db`/`#e8dfcb` family, accents in the `#b08947`/`#b6553a`/`#9a2436`/`#9c6e2a`/`#bc7c3a`/`#7d5621` family, ink in the `#1a1714` family). Fix: pick a named, committed world. C5 is the *surface-only* cream reflex; C11 is the full three-role scheme appearing together — report one, never both

### Layout and Space (L1-L13)
- L1: Hero metric layout (centers large number, tiny label, supporting stats with generic treatment)
- L2: Identical card grids (4+ siblings with identical icon/heading/paragraph sizing)
- L3: Monotonous spacing (same gap/padding token for item/group/component/section boundaries)
- L4: Nested cards (3+ nested levels repeating borders/fills/radii/shadows)
- L5: Numbered section markers (01/02/03 labels for independent sections)
- L6: Line length too long (>80 chars per line running text)
- L7: Content overflowing its container (text/media spills, clips, accidental horizontal scroll)
- L8: Positioned child clipped by overflow container (tooltip/menu/popover cut by overflow:hidden/clip)
- L9: Non-semantic markup (div-soup instead of button/nav/main/header)
- L10: Default 50/50 split reflex (section after section resolves to a predictable 50% text / 50% media split). Fix: vary the rhythm — full-width banner, asymmetric 40/60, tabular data rows, interactive multi-panel viewport
- L11: Orphan or decorative grid cell (grid cell count does not match item count — an empty cell remains, or a filler cell was inserted to square the layout). Fix: let content choose the grid; redistribute the item span or change structure. A bento is composed *from* content, never filled *to fit*
- L12: Above-the-fold hero overflow (at 1440×900 the hero headline or primary CTA falls below the fold, or the header exceeds ~80px or wraps to a second row). Fix: header one row under ~80px, headline held to two lines, CTA above the fold
- L13: CTA competition (two or more calls to action at equal visual weight, or two expressing the same intent — "Get started" beside "Start free trial"). Fix: one primary action per view; secondaries take subordinate treatment and a genuinely different intent

### Motion (M1-M18)
- M1: Bounce or elastic easing (dialogs/cards/routine controls with overshoot/spring effects)
- M2: Layout-property animation (width/height/padding/margin/top/left causing reflow)
- M3: Image hover transform (generic cards repeatedly scale/rotate on hover)
- M4: Blanket scroll-fade-in applied to every section indiscriminately
- M5: Uniform 300ms ease-in-out duration regardless of element size/distance
- M6: Reflexive hover:scale-105 / lift-shadow on non-interactive cards
- M7: No respect for prefers-reduced-motion
- M8: Staggered-list-reveal cliché applied to non-list content
- M9: Blanket `transition: all` (transition declared on every property rather than the properties meant to animate). Fix: name them — `transition: transform 160ms, opacity 160ms`. Blanket transitions animate unintended properties and make timing unpredictable
- M10: Motion on a high-frequency action (keyboard shortcut, search, filter, tab switch, row hover, or menu open animating long enough to be felt as lag). Fix: resolve in roughly 100–150ms, or immediately. Reserve deliberate motion for occasional and rare interactions
- M11: Entrance on ease-in or over 300ms (entering elements should decelerate and stay short; ease-in belongs on exits)
- M12: Motion-only state indication (a state change carried solely by animation, with no persistent static difference once the motion ends). Fix: pair motion with a static affordance that survives `prefers-reduced-motion`. A7 is the colour-only case; M12 is the motion-only case
- M13: Untuned default easing curve (every state transition using the browser default `ease` or `linear`, no curve chosen per interaction class). Fix: choose a curve per class and keep it in a token. M5 covers the duration axis, M13 the curve axis — a page can fail either one alone
- M14: Entrance from `scale(0)` (element appearing from nothing, or a pure opacity pop with no scale offset). Fix: start from `scale(0.9–0.97)` plus `opacity: 0` — the small non-zero start is what makes the entrance read as physical rather than as a toggle. M1 is the overshoot *curve*; M14 is the *start value*
- M15: Keyframes where a transition belongs (a rapidly-retriggered element — toast, toggle, dynamic list — animating via `@keyframes`, so an interrupted run restarts from zero instead of retargeting). Fix: transitions interrupt and retarget; reserve keyframes for predetermined, one-shot motion
- M16: Popover scaling from its own center (dropdown, menu, or popover growing from the element's center rather than from the trigger that opened it). Fix: set `transform-origin` to the trigger. Modals are the one exemption — centered in the viewport, they keep `transform-origin: center`
- M17: Compositor-breaking animation technique (child transforms driven by a CSS variable on the parent, `will-change` left on permanently, or a rAF loop writing into React state). Fix: set `transform` directly on the animating element, scope `will-change` to the animating window, keep rAF out of React state
- M18: Ungated hover motion (hover-triggered transform that also fires on touch, where the tap produces a false hover and the element moves under the finger). Fix: gate behind `@media (hover: hover) and (pointer: fine)`

### Copy (P1-P9)
- P1: Em-dash overuse (3+ em-dash characters in body block)
- P2: Marketing buzzword (supercharge, streamline, empower, world-class, enterprise-grade, seamlessly, unlock)
- P3: Aphoristic cadence (Multiple sections repeat Not X. Y. or Less X. More Y. patterns)
- P4: Theater framing copy (Marketing dismisses category as theater without explaining practical failure)
- P5: "It's not just X, it's Y" / "more than just a Z" construction
- P6: Buzzword stacking (supercharge, leverage, unlock, elevate, robust, cutting-edge)
- P7: Em-dash overuse as a sentence-structure crutch
- P8: Inflated fake urgency/stats with no source ("only 3 spots left", "10,000+ happy customers")
- P9: Rule-of-three headline tic ("Fast. Reliable. Secure.")

### Imagery (I1-I6)
- I1: Broken or placeholder image (missing/empty src, #, known placeholder services, placeholder API paths)
- I2: Generic stock-photo tells (diverse-team-laughing-at-laptop, handshake close-up, lightbulb-idea shot)
- I3: AI-image generation artifacts (garbled embedded text, malformed hands, uncanny facial symmetry, inconsistent lighting/shadows)
- I4: Mixed icon styles in one view (outline + filled + duotone)
- I5: Inconsistent aspect ratios/crops across a grid or gallery; images not using `object-fit: cover`. Fix: standardize ratios by role — 1:1 catalog items, 16:9 landscape showcases, 4:5 vertical portraits
- I6: Leftover placeholder images (lorem-picsum, unsplash-random) in production build

### General Quality (Q1-Q10)
- Q1: Cramped padding (text/controls within ~8px of bordered/colored edge)
- Q2: Body text touching viewport edge (especially on mobile)
- Q3: Justified text without effective hyphenation/language support
- Q4: Low contrast text (misses WCAG AA: 4.5:1 normal, 3:1 large text)
- Q5: Skipped heading level (rendered outline jumps h1 to h3 or similar)
- Q6: Tight line height (body text below 1.3, display headings role-based exceptions)
- Q7: Tiny body text (below 12px, 12-13px readability risk)
- Q8: Wide letter spacing on body (tracking above 0.05em)
- Q9: Contract-breaking refactor (existing HTML classes, IDs, or data-attributes renamed, removed, or restructured while JS, data fetching, or event listeners depend on them). **Blocker.** Preserve every technical hook — diff the selectors the JS references against the markup before changing styles; if a rename is genuinely required, update both sides in the same change
- Q10: Unthemed browser surfaces (text selection, caret, scrollbar, focus ring, underline offset, and tabular numerals still carrying browser defaults, so the parts the designer did not draw belong to no design system). Fix: theme them from the palette — this is the cheapest signal that a page was built rather than assembled, and the one most reliably skipped

### Composition (X1-X10)
Composition-level checks. These sit above single-component defects: a page can pass every V/T/C/L check and still fail here.
- X1: Motion saturation (many elements enter, float, pulse, wiggle, or bounce). Fix: keep motion tied to a single state change or spatial relationship
- X2: Decorative priority inversion (icon containers, badges, ornaments occupying more visual weight than the message they introduce)
- X3: Redundant UX writing (label, sublabel, helper, placeholder, hint all repeating the same fact)
- X4: Modal abuse (a scrolling multi-column, multi-section workflow living in a modal)
- X5: Page-level archetype uniformity (the same section skeleton repeating down the page and across routes — identical 50/50 splits, identical card rows, identical section heights). Generic scope; H18 is the hospitality-scoped form of this defect — report X5 elsewhere, never both. Fix: each route owns the structure its content implies
- X6: No visual anchor (every element in a section carries equal weight; nothing is memorable and no element reads as the point of the section). Fix: give one element dominance, chosen by content priority rather than by size alone
- X7: Unbroken zigzag alternation (every media/text section flips side in strict alternation, so the third consecutive zigzag makes the page read as a template rather than a sequence). Fix: cap consecutive zigzags at two — the third section in a row must take a different shape (full-bleed, tabular, stacked, multi-panel)
- X8: Split-header reflex (heading left, supporting paragraph right, repeated as the opening of section after section). Fix: let the header take the shape its content implies — a split header on every section is a layout the page never decided on
- X9: Unearned production chrome (interface furniture that signals "shipped product" without carrying information: version labels in the hero, scroll cues, decorative status dots, locale/time/weather strips, decoration text strips, floating top-right sub-text, photo-credit captions, version footers, micro-meta-sentences, generic step labels). Fix: delete anything on this list unless it carries real, decision-relevant information — this chrome is what makes a page read as a demo rather than a product
- X10: Numbered-pagination chrome (`01 / 4` counters, scoring bars with filled tracks, and step indicators attached to content that is not a real sequence). Fix: keep numbering only where order itself is information the reader needs (see L5)

### Accessibility (A1-A16) NEW
- A1: Missing/generic alt text ("image", "photo1.png")
- A2: Contrast failing WCAG AA (<4.5:1 normal text, <3:1 large text)
- A3: No visible focus state / outline removed with no replacement
- A4: Non-semantic markup (div-soup instead of button/nav/main/header)
- A5: Broken keyboard nav (unreachable interactive elements, no skip-to-content)
- A6: Form inputs with no associated label
- A7: Color-only status indication (no icon/text fallback)
- A8: Missing ARIA roles/live regions on dynamic content
- A9: Clickable non-interactive element (`<div onClick>` or `<span onClick>` where a `<button>` belongs — not focusable, not keyboard-operable, no role announced). Fix: use the element whose semantics match the behavior; styling is not a reason to avoid `<button>`
- A10: Positive `tabindex` (`tabindex="1"` or higher reorders focus away from document order). Fix: `0` to join the natural order, `-1` for programmatic focus only
- A11: Modal without a focus trap (focus escapes to the page behind an open dialog, or is never moved in on open and never returned to the trigger on close). Fix: move focus in, trap it while open, restore it on close — use `<dialog>` or the platform's focus management
- A12: Icon-only control with no accessible name (a close, menu, or search button rendering an SVG with no label). Fix: visible text, `aria-label`, or a visually-hidden span — the icon alone names nothing
- A13: Decorative SVG not hidden from assistive tech (purely decorative icons and ornaments announced, adding noise to every read). Fix: `aria-hidden="true"` and `focusable="false"`; meaningful graphics get a `<title>`
- A14: Autofocus on page load (a field steals focus, scrolling past content and disorienting screen-reader and keyboard users). Fix: autofocus only inside a surface the user just opened
- A15: `title` attribute as the only label (tooltip-as-label on a control or an image, unreachable by keyboard and touch). Fix: a real `<label>`, a visible caption, or `aria-label` — `title` is never the sole carrier of a name
- A16: Error state with no programmatic association (a validation message renders visually but is not tied to its field, so assistive tech never announces it). Fix: `aria-describedby` on the message, `aria-invalid` on the field. F5 is the visual mapping; A16 is the programmatic one

### Design-Token / Drift Detection (D1-D6) NEW
- D1: Multiple border-radius values for the same component type across files
- D2: Hardcoded hex/px instead of referencing defined tokens
- D3: Spacing off the defined scale (random 13px/22px instead of 8/16/24)
- D4: Font-size/weight combos outside the type scale
- D5: Divergent shadow/elevation values for equivalent components
- D6: Near-duplicate hex values that should collapse into one token

### State Coverage (S1-S8) NEW
- S1: Empty state (zero items/no data) — must be intentional design, not bare blank container
- S2: Loading state — skeleton or spinner present; flag if missing entirely
- S3: Skeleton/loading layout mismatch — skeleton shape doesn't match real content's final layout (causes visible layout shift on load)
- S4: Error state — a failed fetch/action has a visible, human-readable error, not a silent failure or raw stack trace
- S5: Disabled state — actions requiring precondition are visibly disabled, not just non-functional
- S6: Partial-data state — some fields present, others null/undefined — doesn't break layout or show "undefined"/"null" as text
- S7: Permission-gated state — role-restricted UI shows appropriate message, not broken/empty view
- S8: Offline/network-loss state, where relevant

### Real-Content Stress Test (R1-R6) NEW
- R1: Long text overflow (long name, long email, long title) — check truncation/wrap behavior exists
- R2: List with 0 items, 1 item, and 100+ items — check for layout breaking or missing pagination/virtualization at scale
- R3: Mismatched string lengths in a set that's supposed to align (e.g. table columns, card titles)
- R4: Number edge cases — zero, negative, very large numbers, decimals where integers were assumed
- R5: Missing/broken image fallback (alt text and a placeholder graphic, not a broken-image icon)
- R6: Special characters / RTL text / emoji not breaking layout

### Responsive / Breakpoint Consistency (B1-B5) NEW
- B1: Same component's spacing/type-scale token usage checked at each breakpoint (mobile/tablet/desktop) — flag drift introduced only at certain sizes
- B2: Touch targets below 44x44px (iOS) / 48x48px (Android) on mobile breakpoints
- B3: Horizontal scroll appearing unintentionally at any breakpoint
- B4: Content/functionality that silently disappears on smaller breakpoints instead of adapting
- B5: Fixed pixel widths that don't scale, causing overflow or excess whitespace

### Interaction Feedback Audit (F1-F7) NEW
- F1: Async actions (save/submit/delete) with no loading indicator during the wait
- F2: Destructive actions (delete, remove, cancel subscription) with no confirmation step
- F3: Successful actions with no success feedback (toast, inline message, visual state change)
- F4: Double-submit not prevented (button stays clickable during a pending request)
- F5: Form validation errors that don't map to the specific field they belong to
- F6: Hover/focus/active states missing on any clickable element
- F7: Hover-locked essential data (names, prices, or specs reachable only via a hover drawer or hover-only tooltip, so touch devices cannot reach them at all). Core data must be immediately visible and operable — hover may *add*, it must never *gate*

### Dark Mode / Theme Parity (DM1-DM5) NEW
- DM1: Contrast ratio re-checked independently in dark mode (good light-mode ratio doesn't guarantee good dark-mode one)
- DM2: Icons/illustrations that are literally just inverted rather than purpose-built for dark backgrounds (halos, wrong shadows)
- DM3: Semantic colors (error red, success green) not re-tuned for dark backgrounds and failing contrast there
- DM4: Elevation/shadow system that relied on light-mode shadows now invisible or wrong on dark backgrounds
- DM5: Spacing/layout drift between light and dark versions of the same component

### Engineering — Source-Code Slop (E1-E58)
Scope: React / Next.js / TypeScript / Tailwind codebases. Everything above describes the **rendered artifact**; this category describes the **source** that produced it, and none of it is visible in the render. A deliverable can pass every render-side check and still fail E. Full rows, per-framework equivalents, grep signatures, and the enforcement checklist: `references/slop-patterns.md` and `references/code-slop-guide.md`.

State and effects:
- E1: Derived state in `useState` + `useEffect` (a value stored in state then kept in sync by an effect, when it was always computable). Fix: compute during render, `useMemo` if expensive — never state plus an effect
- E2: Duplicated state (the same fact in two places, updated in both, so they can disagree). Fix: one owner, derive the rest
- E3: `useCallback`/`useMemo` cargo cult (memoization around trivial values, or handlers passed to a component that is not memoized). Fix: memoize against a measured re-render
- E4: `useEffect` as an event handler (an effect watching a state flag to perform an action the user already triggered). Fix: do the work in the handler
- E5: Continuous input value in React state (drag, scroll, mousemove, or pointer position in `useState`, re-rendering every frame). Fix: a ref, a motion value, or a directly-set transform
- E6: Undivided context (one context holding unrelated values, re-rendering every consumer on any change). Fix: split by change frequency

Data fetching:
- E7: Fetch in `useEffect` with no guard (an async request resolving after unmount or a dependency change, writing into a dead tree). Fix: an `ignore` flag or `AbortController`
- E8: No `AbortController` (in-flight requests continuing after navigation, wasting the response and racing the next one). Fix: abort on cleanup, pass the signal through
- E9: Happy-path-only fetch (no loading, error, or empty branch). Fix: all three are part of the component (S1, S2, S4)
- E10: No cache or dedup (two components mount and request the same endpoint; a remount refetches everything). Fix: the framework cache or a query library with a key
- E11: `'use client'` on everything (the directive on the route, layout, or most components, so the whole tree ships as client JavaScript). Fix: keep the boundary at the leaf
- E12: `async` passed directly to `useEffect` (the effect returns a Promise, so cleanup is not a function). Fix: an inner async function called from a synchronous outer one
- E13: Sequential awaits where parallel is available (independent requests awaited in sequence, so latency adds up). Fix: `Promise.all` for independent work

Lifecycle and leaks:
- E14: Uncleaned timer or interval (no clear call in the effect cleanup)
- E15: Uncleaned event listener or subscription (no corresponding removal)
- E16: Unrevoked object URL or blob (`URL.createObjectURL` with no `revokeObjectURL`)
- E17: Module-level mutable state holding request or user data (shared across every user of the module, surviving navigation)
- E18: Unawaited promise with no error path (rejection becomes an unhandled rejection, never surfaced)

Component architecture:
- E19: God component (one component owning layout, data, state, handlers, and rendering, well past 300 lines). Fix: split by responsibility
- E20: Prop drilling through three or more layers. Fix: composition (`children`), context, or colocate the state
- E21: Array index as key on a list that can reorder, insert, or delete. Fix: key on a stable identity
- E22: Missing key entirely. Fix: a stable key; also applies to fragments in a list
- E23: Boolean-prop configuration (`isLarge`, `isPrimary`, `isIcon` accumulating into a matrix of flags). Fix: variants, composition, or separate components
- E24: Inline handler recreated per row in a hot list. Fix: hoist it, or use a data attribute
- E25: No module boundaries (data access, business logic, and presentation with no separation)

TypeScript:
- E26: `any` (explicit, or implicit from an untyped source). Fix: type it, or use `unknown` and narrow
- E27: Suppression comment without a reason (`@ts-ignore`/`@ts-expect-error` and no explanation). Fix: the type, or the reason; prefer `@ts-expect-error`
- E28: Absent or empty prop types (props typed `any`, `object`, or not at all). Fix: declare them explicitly
- E29: `as` cast to silence a mismatch. Fix: narrow or validate — a cast moves the failure to runtime
- E30: Non-null assertion as a substitute for a check (`value!` on something that can genuinely be null). Fix: check it, or encode the guarantee in the type
- E31: Permissive types (`string` where a union belongs; every field optional; `object` for a shape). Fix: model the domain

Markup and styling:
- E32: Utility class soup (twenty or more utilities on one element, no extraction, repeated app-wide). Fix: extract the component or the class
- E33: Arbitrary values everywhere (`w-[437px]`, `mt-[13px]`, `text-[15px]`). Fix: snap to the scale — the Tailwind form of D3/D4 drift
- E34: Specificity escalation (`!important`, Tailwind's `!` prefix, ever-deeper selectors). Fix: the source of the conflict
- E35: Inline `style` for values that belong in tokens. Fix: a token or a class — inline style is D2 hardcoding wearing a different hat
- E36: Duplicated utility clusters (the same eight-class string in twelve places). Fix: extract once
- E37: No responsive strategy (desktop-first classes with no breakpoints). Fix: define the collapse per section (B1-B5)

Security and privacy hygiene — blocker-class where the input is user-controlled:
- E38: `dangerouslySetInnerHTML` with unsanitized input. Fix: render as text, or sanitize through a maintained library at the boundary
- E39: Secret in the client bundle (a key, token, or signing secret behind `NEXT_PUBLIC_*`, `VITE_*`, or in client code). Fix: move it server-side — anything shipped to the client is public
- E40: Intermediate values and user data left in `console.log` (tokens, response bodies, form values). Fix: remove before delivery
- E41: No validation at the trust boundary (client-supplied values used server-side unchecked). Fix: validate server-side regardless of the client
- E42: Sensitive data in the URL, query string, or `localStorage`. Fix: keep credentials out of URLs; prefer httpOnly cookies
- E43: Unvalidated redirect or fetch target (a URL taken from a parameter with no allowlist). Fix: restrict to known origins or paths

Performance and framework:
- E44: Client boundary at the root (the whole page is a client component, so nothing streams and everything hydrates). Fix: push the boundary to the interactive leaves
- E45: Raw `<img>` for large assets (no framework image component, no dimensions, no modern format, no `loading`). Fix: the framework image component, or explicit dimensions plus `loading="lazy"`
- E46: Unsized media causing layout shift. Fix: reserve the space — the largest single contributor to a failing CLS
- E47: Heavy import with no dynamic boundary (a charting, editor, or 3D library at module top level in a route needing it conditionally). Fix: import dynamically at the point of use
- E48: Render blocked on non-critical data (the page waits on a request one section needs). Fix: stream or suspend the slow section
- E49: Google Fonts via `<link>` (render-blocking third-party request, no `preconnect`, no `display=swap`, consequent shift). Fix: self-host via the framework font loader
- E50: Bundle growth with no accounting (dependencies added per feature, no check on cost). Fix: verify against `package.json`; dead dependencies are pure payload

Testing and project structure:
- E51: No test on a correctness-critical path (money, auth, parsing, permissions, dates). Fix: one test that fails if the logic breaks
- E52: Snapshot-only tests (coverage that breaks on every styling edit and catches no bug). Fix: assert on behavior
- E53: Tests asserting implementation detail (internal state, private methods, call counts). Fix: assert on observable behavior
- E54: Dead code and unused exports (commented-out blocks, unreachable branches, forgotten feature flags). Fix: delete — version control is the archive
- E55: Duplicated logic (the same helper or validation copy-pasted with small drift). Fix: one implementation, one owner

Form handling:
- E56: Controlled/uncontrolled switch (an input changing ownership model mid-life, so React warns and the value resets). Fix: choose one model at first render — `undefined` is what triggers the switch
- E57: File input value held in state (a `FileList` copied into React state, where it cannot be set back). Fix: read it on submit, or use a ref
- E58: Form state not reset after submit (fields keep their values, so the user cannot tell whether it worked and may submit twice). Fix: reset on success; pair with F3

**Meta-tell.** Four or more of these together means the tree was generated without a human review pass: component file doubling as its own data layer, `any` at every boundary, fetch inside `useEffect`, `console.log` still present, unused exports, index keys, `'use client'` on the root, no test on a path that matters. Use it to set severity and justify a rewrite over a patch — report the individual E-IDs, not the gestalt.

### Hospitality / Luxury Domain (H1-H18)
Scope: ultra-luxury hospitality, Michelin-grade restaurants, architectural destination venues only. Do not apply to SaaS, dashboards, dev tools, or aggregators.

ID blocks: forbidden patterns are H1-H7 and H13-H15; mandatory codes (violations of absence) are H8-H12 and H16-H18. IDs are stable — new patterns append, they never renumber.

Forbidden patterns:
- H1: Card-grid aggregation (rows of identical rounded cards: cropped image header + plain text body). Two tells: the uniform rounded-container reflex (`border-radius: 12-16px` + generic shadow + flat grey fill applied to halls, gardens, gazebos, dishes alike) and box-in-a-box thumbnail syndrome (a photo nested in its own rounded container inside an already bordered card)
- H2: Generic status pills (pill with pulsing green/red dot: "Open Today • 12:00 PM – 11:30 PM", "Live", "Active Now") — reads as an automated server health monitor
- H3: Fake chrome around media (mock window headers, tab strips with close buttons, "LIVE MAP" bars around embedded media). Exempt only when the product genuinely is an OS or browser simulator
- H4: Raw embedded maps (unstyled Google Maps — pastel roads, yellow highways, cyan water — in a dark-themed luxury interface)
- H5: Circular icon lists (icon-in-circle stacked beside address/contact/hours rows: pin, telephone, clock, car)
- H6: Fintech sans pairing (Outfit, Poppins, Inter, DM Sans, Montserrat against a classical luxury serif — geometric circularity beside Cormorant Garamond reads fintech/crypto, not heritage). **This is a *pairing* rule, not a ban on Inter** — Inter is legitimate for a clean/technical identity (see T8)
- H7: Hover-gated core content (dish photos, ingredients, tasting notes, pricing hidden entirely inside hover reveals — also unreachable on touch, where no hover state exists)
- H13: Commerce price and tag pills (a price `₹200`, tag, or category trapped in a rounded pill, chip, or grey button box — checkout-counter grammar; the generic case is V12). Replacement: lightweight text labels, subtle dots, or an integrated typographic scale — or, in the dining context, an editorial ledger: Cormorant Garamond title, hairline dot-leader, standalone gold serif price
- H14: Retail menu chrome (search toolbar with magnifier, pill filter chips, "Expand All" toggle on a dining menu — makes a restaurant read as a pharmacy or retail catalog). Replacement: editorial category index, chapter curtain, or video chapter transition
- H15: Spatial/factual hallucination (describing a ground-level botanical estate as "rooftop venue", "high-rise", or "skyline balcony"; inventing floors, views, amenities, awards, capacity). **Severity: blocker** — the only pattern a guest can falsify by arriving. Verify every claim against the brief; where the brief is silent, omit the claim rather than defaulting to the aspirational one

Mandatory design codes (violation = the required treatment is absent):
- H8: Canvas over card (full-bleed backgrounds, architectural hairline borders `1px solid rgba(223, 191, 108, 0.18)`, asymmetrical split viewports — not boxed containers)
- H9: Editorial typographic scale (numbers, coordinates, labels treated as design elements: Roman or serif numerals "01"/"02", wide tracking 0.2em, small caps — `01 — Rogan Josh`, not `1. Rogan Josh`)
- H10: Discreet dietary indicators (4-6px glowing jewel dots framed in glass discs, not heavy VEG/NON-VEG badges — the FSSAI bordered square with green/red dot is the specific forbidden form; it is a packaging mark and signals cloud kitchen or delivery aggregator)
- H11: Cinematic media integration (background video carries calibrated linear + vignette gradient scrims bleeding into the dark palette, no hard edges; footage stays atmospheric, slow-motion, low-contrast — tandoor embers, a simmering rogan, never a stock whoosh or hard cut)
- H12: Tabular concierge hierarchy (arrival, contact, venue data as a five-star concierge dossier: category key left in letter-spaced uppercase sans, refined Cormorant Garamond serif values right)
- H16: Architectural signature footer (grand brand masthead, direct telephone booking line as primary action via real `tel:` link, tabular navigation, large low-opacity background watermark brand stamp). Violation tell: generic 3-column template with tiny corner logo, plain link lists, and floating circular SVG social icons
- H17: Curated third-party grading (every embed — map, review strip, booking widget, social feed — graded back into the house palette and framed asymmetrically, never a raw embed beside a contact card in an uninspired 50/50 box split). Grading equation, tune per palette: `filter: invert(92%) hue-rotate(185deg) saturate(35%) brightness(78%) contrast(125%);`
- H18: Page-archetype uniformity (one generic template reused site-wide: 3 feature boxes on events, 3×3 grid on gallery, static paragraphs plus three icon bullets on experience, every section a 50/50 split). Each page has its own venue-logic architecture — see the section-by-section ledger in `references/luxury-hospitality-protocol.md`

Supersession: in this domain the H-ID replaces its base-catalog equivalent — H1>L2/V6/I5/L4, H2>V12/M4/M6, H4>C1/C4, H5>A4/L9, H6>T8/V14, H10>V12, H8>L4, H9 inverse of T5/L5, H13>V12, H18>L2/L3/L4/L10/X5. Report one, never both. H3, H7, H11, H14, H15, H16, and H17 have no base equivalent.

**Generic-pair splits** (adjacent IDs that describe different axes of one symptom — report one per defect, at the scope of the target):

| Pair | Axis A | Axis B |
|------|--------|--------|
| M13 / M5 | Curve (default `ease`) | Duration (uniform 300ms) |
| M12 / A7 | Motion-only state | Colour-only state |
| C9 / C2 | Fill saturation on dark | Glow (shadow, neon text) |
| T18 / D4 | No scale defined (absence) | Drift from a defined scale |
| X5 / H18 | Generic page archetype | Hospitality page archetype |
| L13 / H2, H13 | Generic CTA competition | Venue-status and price forms |

**Generic ↔ hospitality mapping.** The H-patterns are the hospitality-scoped case of generic defects. Outside that domain, report the generic ID; inside it, the H-ID — never both.

| Generic | Hospitality | Relationship |
|---------|-------------|--------------|
| V19 Ungraded third-party embed | H17 (any embed), H4 (maps) | Same defect, house-palette severity |
| V20 Unscrimmed ambient video | H11 | H11 adds the slow/atmospheric footage rule |
| F7 Hover-locked essential data | H7 | H7 names dish photos, ingredients, tasting notes |
| V18 Border-as-hierarchy crutch | H8 (inverse) | H8 is the positive framing: canvas over card |
| L10 Default 50/50 split reflex | H18 | H18 is page-level; L10 is the section-level symptom |
| X5 Page-level archetype uniformity | H18 | Same defect; X5 is the generic scope, H18 the hospitality one |
| L13 CTA competition | H2, H13 | The venue-status and price forms of one-action-per-view |
| L9 Non-semantic markup | H5 | H5 when the icon list encodes contact/venue data |

Full design contract, section-by-section archetype ledger, pre-emit checklist, and exemption rules: `references/luxury-hospitality-protocol.md`.

</pattern_catalog_detail>

<references>
- references/slop-patterns.md — 245 AI slop phrase and design patterns across 18 categories with risk levels, corrections, convergence pairs, and fix order
- references/design-spec.md — Construction-side counterpart: Stage 1 brief, motion/colour/type token tables, build rules, polish passes, and the Stage 5 pre-emit gate that blocks delivery
- references/code-slop-guide.md — Detection method, per-framework equivalents, grep signatures, and enforcement for the E category (E1-E58). Byte-identical in both skills
- references/prompt-library.md — Copy-paste activation prompts (strategy pass, landing, dashboard, typography, bento, motion, colour, redesign audit, hero, final gate) plus the rejected prompt sets and why
- references/content-quality-guidelines.md — Quality standards for content evaluation
- references/luxury-hospitality-protocol.md — H1-H18 luxury hospitality design contract: forbidden patterns, mandatory codes, section-by-section archetype ledger, pre-emit checklist, exemption rules
</references>

<related_skills>
- slop-audit — Operational skill: detects and tracks slop in codebases via --scan, --list, --clear
- content-pipeline — AI UGC video production (may generate slop)
- capture — Note capture workflow
- gsd:progress — GSD progress checking and routing
</related_skills>

<how_to_use>
This skill is a **design reference only** — AI agents load it before generating UI. It documents 245 anti-patterns across 18 categories and the design principles to avoid, plus the construction workflow that keeps most of them from being emitted in the first place.

Seventeen of the eighteen categories read the **rendered artifact**. The eighteenth — Engineering (E1-E58) — reads the **source** that produced it. A deliverable can pass every render-side check and still fail E. Scan both.

### Loading the Skill
```bash
/skill slop-design
```

### Reference Workflow for AI Agent:
1. Run the Stage 1 brief from `references/design-spec.md` — mode, audience, mood, density, variance, motion intensity, banned list, and the single visual idea. No code until it exists
2. Load the skill via `/skill slop-design`
3. Read the pattern catalog from `references/slop-patterns.md`
3. Check each design decision against all 245 patterns (V1-V21, T1-T18, C1-C11, L1-L13, M1-M18, P1-P9, I1-I6, Q1-Q10, X1-X10, A1-A16, D1-D6, S1-S8, R1-R6, B1-B5, F1-F7, DM1-DM5, H1-H18, E1-E58)
4. Apply replacement principles where patterns are detected
5. Ensure hierarchy uses a proper font system (single family with strong hierarchy through size/weight/width/spacing; second family earns place through clear role)
6. Verify colors carry defined jobs (brand, action, status, emphasis, surfaces); repeated decorative gradients/glows dilute those jobs
7. Check spacing communicates relationship (related items sit close; sections receive larger separation; repeated spacing tokens remain useful when semantic roles differ visibly)
8. If motion used, it communicates state, continuity, or causality (default surfaces stay still; one meaningful transition carries more value than many ornamental effects)
9. If decoration used, it carries meaning (domain artifacts, real product UI, data, photography, diagrams, and brand motifs provide specificity; generic icons and blobs disappear when carrying no information)
10. Asymmetry follows priority (give more space to more important content; avoid arbitrary card-size variation created solely to appear designed)
11. For each component, check state coverage (S1-S8): empty, loading, error, disabled, partial-data, permission-gated, offline states designed intentionally
12. For each component, run real-content stress test (R1-R6): long text, list scales, mismatched lengths, number edge cases, image fallbacks, RTL/special chars/emoji
13. For each component, check responsive consistency (B1-B5): spacing/type-scale across breakpoints, touch targets, unintended horizontal scroll, disappearing functionality, fixed pixel widths
14. For each interactive element, check interaction feedback audit (F1-F7): async actions with loading, destructive actions with confirmation, success feedback, double-submit prevention, form validation mapping, hover/focus/active states, essential data never hover-gated
15. If dark mode detected, check dark mode parity (DM1-DM5): contrast re-checked independently, icons purpose-built not just inverted, semantic colors re-tuned, elevation/shadow system working, spacing/layout drift resolved
16. Run the composition checks (X1-X10): motion saturation, decorative priority inversion, redundant writing, modal abuse, page-archetype uniformity, confirm each section has one visual anchor, split-symmetry default, blur-as-priority, depth cues on flat surfaces, numbered pagination chrome
17. Motion tokens: name every transition (M9), scale duration to interaction frequency (M10), ease-out entrances (M11), static affordance alongside motion (M12), authored curves (M13), never `scale(0)` on entry (M14), transitions over keyframes for retriggerable surfaces (M15), origin-aware popovers (M16), bounded stagger (M17), hover motion gated to fine pointers (M18). Token table in `references/design-spec.md`
18. Colour tokens: no pure `#000`/`#fff` planes (C7), neutrals tinted to the brand hue (C8), de-saturated dark-mode fills (C9), every colour carrying a job (C10), and no unexamined warm-neutral-plus-terracotta "tasteful" default palette (C11). OKLCH recipe in `references/design-spec.md`
19. Type tokens: roles on one ratio (T18), tabular numerals where digits align (T16), tracked uppercase labels (T17), measure and line height bounded (L6, Q6), display capped around 6rem (T6), tight tracking floored around -0.04em (T7)
20. Layout checks: no orphan or filler grid cell (L11), hero CTA above the fold with header under 80px (L12), one primary CTA per view (L13)
21. If the target is luxury hospitality, fine dining, or a destination venue, apply the H1-H18 domain contract. Resolve in order — **truth** (H15: verify every spatial/factual claim against the brief before laying anything out), **canvas** (H8), **page archetype** (H18), **media** (H3/H4/H11/H17), **structure** (H1/H5/H12/H16), **type** (H6/H9), **indicators** (H2/H10/H13/H14), **content presence** (H7). Skipping the truth step produces a beautiful site that lies about the building, which is the one defect no redesign recovers from. Skip this whole step for non-hospitality targets
22. Track exempted patterns if applicable (patterns that communicate real meaning or follow established brand)
23. Before emitting, run the pre-emit gate in `references/design-spec.md` (Stage 5). It includes the contract check: existing classes, IDs, and data-attributes the JS, data fetching, or event listeners reference are preserved (Q9). This is the one pattern in the catalog that ships a silent regression rather than a visual one. A failing check blocks delivery
24. **Source pass (E1-E58).** Read the code, not the render. Effects declare their cleanup (E14-E17); every fetch ships loading, error, and empty branches (E9); one owner per fact (E1, E2, E25); types at the boundaries (E26, E29, E30); no secret reachable from the client (E39); no `dangerouslySetInnerHTML` on user input (E38); server-side validation (E41); stable list keys (E21, E22); client boundary at the interactive leaf (E11, E44); browser surfaces themed (Q10); one correctness test on money, auth, parse, or permission paths (E51). Method, grep signatures, and per-framework equivalents in `references/code-slop-guide.md`. Report individual E-IDs, never the gestalt
25. Generate UI that consciously avoids all 245 anti-patterns

### When NOT to Use This Skill
- Do NOT run `--scan` or `--fix` commands — this is a reference guide only
- Do NOT expect auto-fix suggestions — those belong in slop-audit operational skill
- Do NOT use for runtime detection — use slop-audit for that

### Integration with slop-audit
- Load slop-design first for design patterns
- Invoke the slop-audit skill for operational detection and tracking
- Findings from operational skill can reference pattern IDs from this design guide
- Exemptions tracked in slop-log.json can reference patterns from both skills

## Pattern Reference Quick Lookup Table

| Category | Patterns | Key Avoidances |
|----------|----------|----------------|
| Visual | V1-V21 | Borders >=2px+radius >=12px, glassmorphism, generic icons, extreme radius, mixed icon styles, placeholder images in production, border-as-hierarchy crutch, ungraded third-party embeds, unscrimmed ambient video, geometric mask faking an organic cutout |
| Typography | T1-T18 | Flat hierarchy, oversized headlines, all-caps body, single font, "it's not just X it's Y", buzzword stacking, em-dash overuse, fake urgency, rule-of-three headline, proportional numerals in tables, untracked uppercase, no scale |
| Color | C1-C11 | Purple/violet gradients, dark mode glowing accents, gradient text, gray on colored, cream reflex, WCAG AA contrast failures, pure black/white planes, zero-chroma neutrals, full-chroma dark fills, unassigned colour roles, the warm-neutral-plus-terracotta "tasteful" palette reflex |
| Layout | L1-L13 | Identical card grids, monotonous spacing, nested cards, line length >80 chars, content overflow, positioned child clipped, non-semantic markup, default 50/50 split reflex, orphan grid cells, hero below fold, CTA competition |
| Motion | M1-M18 | Bounce easing, layout-property animation, image hover transform, blanket scroll-fade-in, uniform 300ms ease, hover-scale on non-interactive, no prefers-reduced-motion, staggered-list-reveal on non-list, `transition: all`, animated high-frequency actions, ease-in entrances, motion-only state, default easing curve, `scale(0)` entry, keyframes on a retriggerable surface, origin-blind popover, unbounded stagger, hover motion ungated by pointer type |
| Copy | P1-P9 | Em-dash overuse, marketing buzzwords, aphoristic cadence, theater framing, "it's not just X it's Y", buzzword stacking, fake urgency, rule-of-three headline |
| Imagery | I1-I6 | Broken/placeholder images, stock-photo tells, AI-image artifacts, mixed icon styles, inconsistent aspect ratios, leftover placeholder images in production |
| Quality | Q1-Q10 | Cramped padding, viewport edge text, justified text, low contrast, skipped headings, tight line height, tiny body text, wide letter spacing, contract-breaking refactor (renamed classes/IDs the JS depends on), unthemed browser surfaces (selection, caret, scrollbar, focus ring) |
| Composition | X1-X10 | Motion saturation, decorative priority inversion, redundant UX writing, modal abuse, page-archetype uniformity, no visual anchor, unbroken zigzag alternation, split-header reflex, unearned production chrome, numbered-pagination chrome |
| Accessibility | A1-A16 | Missing alt text, WCAG contrast failures, no focus state, div-soup markup, broken keyboard nav, unlabeled form inputs, color-only status, missing ARIA roles/live regions, clickable non-interactive elements, positive `tabindex`, modal without a focus trap, unlabeled icon-only controls, decorative SVG not hidden, autofocus on load, `title` as the only label, error state with no `aria-describedby` |
| Design-Token | D1-D6 | Multiple border-radius values, hardcoded hex/px, spacing off scale, font combos outside type scale, divergent shadow values, near-duplicate hex values |
| State Coverage | S1-S8 | Missing empty state, missing loading state, skeleton/layout mismatch, missing error state, non-disabled non-functional actions, missing permission-gated state, missing offline state |
| Real-Content Stress Test | R1-R6 | Long text overflow, list scale breakage, mismatched string lengths, number edge cases, broken image fallback, RTL/special chars/emoji breaking layout |
| Responsive Consistency | B1-B5 | Drift at certain breakpoints, touch targets <44/48px, unintended horizontal scroll, disappearing functionality, fixed pixel widths causing overflow/whitespace |
| Interaction Feedback | F1-F7 | Async actions without loading, destructive actions without confirmation, success feedback missing, double-submit not prevented, form validation not mapped to field, missing hover/focus/active states, hover-locked essential data unreachable on touch |
| Dark Mode / Theme Parity | DM1-DM5 | Contrast not re-checked in dark mode, inverted-only icons, semantic colors not re-tuned, elevation/shadow system wrong on dark, spacing/layout drift between light/dark |
| Hospitality / Luxury | H1-H18 | Identical rounded cards with image headers and box-in-a-box thumbnails, pulsing status pills, fake window chrome, raw pastel maps, circular icon lists, fintech sans against serif, hover-gated dishes/prices, prices in pills, search/filter chrome on the menu, invented rooftop/floor/view claims; missing full-bleed canvas, editorial numerals and dot-leader price ledgers, jewel-dot dietary marks, video scrims, concierge dossier, signature footer, graded embeds, per-page archetypes |
| **Engineering (source)** | E1-E58 | Derived or duplicated state, effects without cleanup, fetch in `useEffect` with no abort and no error branch, `'use client'` on the root, god components, index keys, `any`/`@ts-ignore`/`!` at the trust boundary, secrets in client code, `dangerouslySetInnerHTML` on user input, unvalidated boundaries, unsized media, Google Fonts via `<link>`, no test on a money/auth/parse path, dead code |

## For AI Agent Integration

This skill is designed to be loaded as a **knowledge base** - the AI agent reads the pattern catalog and design principles, then applies them when generating UI. It does NOT need to run `--scan` or `--fix` commands.

The agent should:
1. Run the Stage 1 brief from `references/design-spec.md` before writing any UI
2. Load the skill via `/skill slop-design`
3. Read the pattern catalog from `references/slop-patterns.md`
4. Define motion, colour, and type tokens before components (Stage 2)
5. Reference the replacement principles when making design decisions
6. Track exempted patterns if applicable
7. Run the Stage 5 pre-emit gate; a failing check blocks delivery, not annotates it
8. Generate UI that consciously avoids all 245 anti-patterns

This is a reference guide only - no scan tracking, no slop-log.json, no remediation actions. Pure design guidance for AI-assisted UI generation.

## Integration Notes

v3.5.0 appends 78 patterns across one new category and four extended ones, opens the source-code surface, and adds the third shared reference file. ID stability holds: nothing renumbered, H-IDs untouched.

**The new surface.** Categories V/T/C/L/M/P/I/Q/X/A/D/S/R/B/F/DM/H all describe a **rendered artifact** — every one of them can be judged from a screenshot. The new **E category (E1-E58)** describes the **source** that produced it, and none of it is visible in the render. The two failure modes are independent: a page can pass every render-side check and still leak a secret, race a fetch, and carry `any` through its entire boundary; and a page with immaculate source can still be visually generic. A deliverable is not done because the screenshot is good. Detection method, grep signatures, per-framework equivalents, and the enforcement checklist live in `references/code-slop-guide.md`.

**New patterns**

| ID | Pattern | Axis |
|---|---|---|
| M9 | Blanket `transition: all` | Unnamed properties (M2 is layout properties) |
| M10 | Motion on a high-frequency action | Interaction frequency budget |
| M11 | Entrance on ease-in or >300ms | Direction and length of entrances |
| M12 | Motion-only state indication | Inverse medium of A7 |
| M13 | Untuned default easing curve | Curve axis (M5 is the duration axis) |
| M14 | `scale(0)` entry | Start value (M1 is the overshoot curve) |
| M15 | Keyframes on a retriggerable surface | Restart vs retarget |
| M16 | Origin-blind popover | Transform origin |
| M17 | Unbounded stagger | Delay budget across a list |
| M18 | Hover motion ungated by pointer type | Input-capability media query |
| C7 | Pure black/white surfaces | Surface floor and tint |
| C8 | Zero-chroma neutrals | Neutral-to-brand relationship |
| C9 | Full-chroma accent fill on dark | Fill saturation (C2 is glow) |
| C10 | Palette with no role assignment | Absence of colour roles |
| C11 | Warm-neutral-plus-terracotta palette reflex | Scheme arrived without a reason (C5 is surface-only) |
| T16 | Proportional numerals in tabular context | Figure alignment |
| T17 | Uppercase label without tracking | Inverse axis of Q8 |
| T18 | No modular type scale | Absence of a scale (D4 is drift) |
| L11 | Orphan or decorative grid cell | Cell count vs item count |
| L12 | Above-the-fold hero overflow | Fold reachability |
| L13 | CTA competition | Action hierarchy |
| V21 | Geometric mask faking an organic cutout | Mask provenance |
| Q10 | Unthemed browser surfaces | Ownership of the parts the designer did not draw |
| X5 | Page-level archetype uniformity | Generic twin of H18 |
| X6 | No visual anchor | Section-level dominance |
| X7 | Unbroken zigzag alternation | Repetition of the split reflex |
| X8 | Split-header reflex | Header shape not decided by content |
| X9 | Unearned production chrome | Furniture carrying no information |
| X10 | Numbered-pagination chrome | Numbering on a non-sequence |
| A9-A16 | Clickable non-interactive element; positive `tabindex`; modal without a focus trap; icon-only control with no name; decorative SVG not hidden; autofocus on load; `title` as the only label; error state with no `aria-describedby` | Keyboard, focus management, and the programmatic half of the state model |
| E1-E58 | Source-code slop across state and effects, data fetching, lifecycle and leaks, component architecture, TypeScript, markup and styling, security and privacy hygiene, performance and framework, testing and project structure, form handling | The source surface, separate from the render |

**New references**
- `references/design-spec.md` — Stage 1 brief, motion/colour/type token tables, build rules, polish passes, Stage 5 pre-emit gate. Byte-identical in both skills
- `references/code-slop-guide.md` — E-category detection method, grep signatures, per-framework equivalents, enforcement checklist. Byte-identical in both skills
- `references/prompt-library.md` — 10 activation prompts plus the rejected prompt sets

**Blockers.** E38, E39, and E41-E43 join Q9 and H15 in the Stage 1 tier. Where the input is user-controlled they outrank every aesthetic finding on the page: a leak or an unvalidated boundary is not a polish item.

**Evidence labels.** Every material statement in a report carries exactly one of **Observed**, **Measured**, **Inferred**, or **Unknown**. Never promote inferred or unknown material into a factual claim, and never infer authorship from style alone.

**Completion rule.** Removal is the default fix in this catalog and it is right most of the time. Stop pruning when the next removal would reduce task completion, comprehension, evidence, identity, component or interaction behavior, action discoverability, migration safety, or accessibility.

**Pairing rule.** The catalog is detection; `design-spec.md` is construction. Running detection without construction catches the same defect every cycle. Running construction without detection ships the ones that slipped the brief. Reading the artifact without reading the source ships the ones no screenshot can show.

Prior update (v3.4.0) added M9-M13, C7-C10, T16-T18, L11-L13, X5/X6 plus the X1-X6 detail block, and introduced `design-spec.md`.

Prior update (v3.2.0 → v3.3.0) added the six generic patterns V18/V19/V20/L10/F7/Q9, the generic↔hospitality mapping table, the font-pairing guide noting Inter is a *pairing* concern rather than a ban, `object-fit: cover` and standardized ratios on I5, and the OS-simulator exemption on H3.

Prior update (v3.1.0 → v3.2.0) extended the luxury hospitality contract to H1-H18: H13 commerce price and tag pills, H14 retail menu chrome, H15 spatial/factual hallucination (blocker, no exemption), H16 architectural signature footer, H17 curated third-party grading, H18 page-archetype uniformity with a section-by-section archetype ledger.

Existing IDs H1-H12 are unchanged and remain stable — the H1 box-in-a-box thumbnail tell, H2 ledger-line example, H3 chrome example, H7 touch-device failure, H10 FSSAI square tell, and H11 slow/atmospheric footage rule were strengthened in place. H3 and H6 also carry explicit scope notes (OS-simulator exemption; Inter is legitimate for clean/technical identities).

The evidence model (Source/Render/Judgment/Confidence), severity tags (blocker/major/nit), and auto_fix boolean are consistent with slop-audit v3.2.0+ and slop-log.json schema.