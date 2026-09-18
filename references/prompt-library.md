# Prompt Library — Anti-Slop Activation Prompts

Copy-paste prompts that put the catalog and the design spec to work. Each one names the
pattern IDs it enforces, so the agent has something concrete to check against instead of
"make it beautiful" — which is another way of saying "use the statistical default".

Pair every prompt with `references/design-spec.md` (how to build) and
`references/slop-patterns.md` (what not to build).

**Sequencing.** The prompts are stages, not alternatives. Running prompt 1 before prompt 2,
and prompt 10 last, is where most of the quality comes from. Skipping the strategy pass and
the final gate is the usual mistake — those two are where generic output is caught.

---

## 1 — Design strategy pass (run before any code)

```text
Act as a senior design engineer. Do not write code yet.

Read references/design-spec.md (Stage 1) and references/slop-patterns.md.

Before proposing anything, decide and record:
1. Is this brand-first or product-first?
2. Who is the audience, in what context, on what device?
3. What mood? Three specific adjectives, not "modern/clean/premium".
4. Visual density and visual variance?
5. Motion intensity: none / functional / expressive?
6. What is the single visual idea this interface is remembered by?
7. Which generic patterns are banned for this project?

Answer question 6 concretely. If the answer is "a card grid", the brief is unfinished.

Output the brief only, in the Stage 1 table format. Wait for approval.
```

Enforces: X6 (visual anchor), L2, L10, X5. The banned-list answer becomes the project's
scan baseline.

---

## 2 — Anti-slop landing page

```text
Design a landing page. Read references/design-spec.md first.

Banned by default — report if you cannot avoid one:
- Centred hero + purple/violet gradient + tracked eyebrow badge + three-card row (C1, T4, L2)
- Fake dashboard mockups, floating icon pills (I2, V15)
- "BETA" / "AI POWERED" badges carrying no information (V12)
- Decorative arrows on every button (V11)
- Every container carrying a border or a soft shadow (V4, V18)
- Section after section splitting 50/50 (L10)

Required:
- Bold hero, strong type hierarchy, asymmetric composition (T1, L10)
- One visual anchor per section (X6)
- One primary CTA; secondaries subordinate and genuinely different (L13)
- Header one row under 80px; CTA above the fold at 1440×900 (L12)
- Type roles on one scale, measured prose, tabular numerals in any metric (T18, L6, T16)

Motion per the spec's frequency table. Production-ready code.
```

Enforces: the highest-density cluster of patterns in real AI output.

---

## 3 — Product dashboard

```text
Design a product dashboard. Read references/design-spec.md (Stage 1: product-first).

Prioritise: speed, clarity, density, predictable navigation, low cognitive load.

Rules:
- Do not put a card around everything. Group with spacing, alignment, borders, and type
  before reaching for a container (L2, L4, V18).
- Tabular numerals on every metric, price, date, and data column (T16).
- Colour only where it improves comprehension; no decorative gradients (C1, C3).
- Motion: none on search, filters, and keyboard shortcuts (M10). Subtle hover and active
  feedback only. Nothing decorative.
- Full state coverage: empty, loading, error, disabled, partial-data (S1-S8).
- Real-content stress: 0 items, 1 item, 100+ items, long strings, nulls (R1-R6).

Product UI and marketing UI do not follow the same rules. This is the efficient one.
```

Enforces: L1, L2, L3, L4, V18, T16, S1-S8, R1-R6, M10.

---

## 4 — Typography polish

```text
Run a typography pass. Read references/slop-patterns.md T1-T18, Q6-Q8.

Fix:
- Flat hierarchy: adjacent roles must differ visibly in combined size/weight/spacing (T1)
- No defined scale: put roles on one ratio, 1.2-1.333 (T18)
- Proportional numerals in metrics, prices, dates, or table columns -> tabular-nums (T16)
- Uppercase micro-labels at default tracking -> 0.05-0.12em (T17)
- Measure outside 60-75ch (L6); line height below ~1.3 on body (Q6)
- Wide tracking on body copy (Q8)
- Inter/Roboto/Open Sans as an unexamined identity default (T8)
- A geometric sans paired against a display serif (H6)

A second family must earn its place by role. One family with strong hierarchy is better.

Output the role/scale table, then the updated component code.
```

---

## 5 — Bento / asymmetric grid

```text
Build an asymmetric grid section for [feature set]. Read references/slop-patterns.md
L2, L11, X6.

Rules:
- Cell count equals item count. No empty cells, no filler cell to square the layout (L11).
- Not a 3-column row of identical cards (L2).
- One dominant cell carrying the section's anchor (X6).
- Mix large, medium, and compact cells, sized by content priority, not by decoration.
- CSS grid areas used deliberately.
- Hierarchy preserved on mobile — no cell loses its content.

The grid is composed from the content. Never pour content into a pre-decided grid.
```

---

## 6 — Motion polish

```text
Apply a motion pass. Read references/design-spec.md (Stage 2 motion tokens) and
references/slop-patterns.md M1-M18.

Required:
- No `transition: all` — name the properties (M9)
- Animate transform and opacity only; never width/height/padding/margin/top/left (M2)
- Durations from the frequency table: high-frequency interactions 0-100ms or none (M10)
- Entrances decelerate: ease-out, short. Never ease-in on an entrance (M11)
- Curves chosen per interaction class, not the browser default (M13)
- One duration for everything is a defect (M5)
- Active feedback on buttons: scale(0.98) or translateY(1px)
- Never scale(0) on entry — start at 0.9-0.97 with opacity 0 (M14)
- Transitions for anything retriggerable; keyframes restart from zero (M15)
- Popovers scale from their trigger; modals from center (M16)
- Stagger 30-80ms between items, never blocking interaction (M17)
- Hover motion behind @media (hover: hover) and (pointer: fine) (M18)
- prefers-reduced-motion removes transform motion, preserves opacity, and never removes
  the only signal of a state change (M7, M12)

Output a Before / After / Why table first, then the code.
```

---

## 7 — Colour system

```text
Build the colour system in OKLCH. Read references/slop-patterns.md C1-C11, DM1-DM5 and
references/design-spec.md (colour tokens).

Rules:
- No pure #000 or #fff as large planes; lift and tint the dark floor (C7)
- Neutrals carry a small chroma at the brand hue (C8)
- Dark-mode fills use lower chroma and higher lightness (C9)
- Every colour has a job: brand, action, status, emphasis, surface (C10)
- Status and action never share a colour (C10)
- 4.5:1 body text, 3:1 large text and UI boundaries (C6)
- Re-verify contrast in dark mode against the actual dark surface (DM1)
- Icons and illustrations purpose-built for dark, not inverted (DM2)

Output CSS custom properties plus the Tailwind token mapping.
```

---

## 8 — Redesign audit (run before changing an existing interface)

```text
Act as a principal design engineer. Audit before changing any code.

Inventory: design tokens, type roles and scale, spacing scale, grid structure, colour
palette and roles, repeated layout patterns, accessibility, animation, routes, form field
names, and conversion links.

Report:
1. What must be preserved — especially every class, ID, and data-attribute the JS, data
   fetching, or event listeners reference (Q9). This is a blocker: check it first.
2. What must be removed.
3. Which patterns make the current UI read as generic, by ID.
4. The modernisation strategy, in fix-order sequence.

Findings table in the standard format, with confidence and severity. No code yet.
```

Enforces: Q9 above all. A visual redesign must not break product behaviour.

---

## 9 — Hero section

```text
Design the above-the-fold hero. Read references/slop-patterns.md L12, L13, T4, T6, X6.

Constraints:
- Header one row, under 80px
- Headline maximum two lines (T6)
- Subtext maximum 20 words
- Primary CTA visible without scrolling at 1440×900 (L12)
- CTA text does not wrap
- One primary action (L13)
- No tracked eyebrow chip above the headline (T4)
- No fake SaaS badges, scroll arrows, floating stamps, or decorative text strips (V12)
- One clear visual idea (X6)

Strong type, confident spacing, one idea. A hero needs one idea, not ten decorations.
```

---

## 10 — Final gate (blocks delivery)

```text
Run the pre-emit gate from references/design-spec.md (Stage 5) against the code you just
produced. Report every failure with its pattern ID.

Check contract, access, layout, motion, type, colour, states, content, and domain.

If any check fails, fix it and re-run. Do not deliver with a failing check. A failure is
not a note — it blocks.
```

Enforces: the whole catalog, as a gate rather than a review.

---

## Master prompt (when only one prompt is possible)

```text
Before generating UI, run a design strategy pass using references/design-spec.md.
Decide: mode (brand-first or product-first), mood, visual density, visual variance, motion
intensity, type direction, colour system, and the banned generic patterns.

Then build against the token layer from Stage 2, not before it.

Then run the Stage 5 gate: contract, access, layout, motion, type, colour, states, content,
domain. Fix every failure before final output.

Cite pattern IDs from references/slop-patterns.md for anything you change.
```

---

## Rejected prompt sets — do not re-add

The widely circulated "designer-skill-mcp" prompt list is **not** included, and should not
be. Its prompts mandate patterns this catalog classifies as defects:

| That list prescribes | Our catalog says |
|---|---|
| "3-4 feature cards with icons" | T2 icon tile above heading, L2 identical card grid |
| "modular card-based layout", "Quick Stats cards" | H1 card-grid aggregation, L1 hero-metric layout |
| "collapsible left sidebar + metric cards + chart + table" | L2, L3 monotonous spacing |
| "3 pricing cards", Pro plan emphasised | L2 |
| "right sidebar with author bio, search bar, category list" | H14 retail chrome grammar |
| "generous white space" as the whole design instruction | L3 — one spacing token for every boundary |

Importing them would put the skill in contradiction with itself. Their page-type coverage
(404, contact, pricing, onboarding) is legitimate scope, but the *prescriptions* inside are
the slop. Write those briefs from the Stage 1 table and the catalog instead.
