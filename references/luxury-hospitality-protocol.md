# Luxury Hospitality Design Contract — H1-H18

Pre-generation design contract for ultra-luxury hospitality, Michelin-grade restaurants,
and architectural destination venues. Read this **before** generating UI in that domain.

The operational skill (`slop-audit`) detects these as H1-H18 after the fact. This
document exists so the patterns never get written in the first place.

**Scope gate:** applies to luxury hospitality, fine dining, and destination venues only.
Do not apply to SaaS, dashboards, dev tools, or aggregators.

## The Domain Thesis

A destination venue's value is sensory specificity. Generic UI grammar does not merely
look plain here — it actively miscategorises the venue as a booking aggregator. Every
rule below follows from one question:

> Does this element say *"this place exists"* or *"this place is listed"*?

Anything that reads as a listing is the defect. Structure must follow the venue's own
logic: the room, the service, the seasonal menu, the arrival.

**ID blocks:** forbidden patterns are H1-H7 and H13-H15. Mandatory codes — violations of
absence — are H8-H12 and H16-H18. IDs are stable across versions; new patterns append,
they never renumber.

---

## 1. Forbidden Patterns

Never generate these. IDs match the detection catalog.

### H1 — Card-grid aggregation
Never rows of identical rounded cards with a cropped image header and a plain text body.
**Instead:** full-bleed canvas, asymmetric split viewport, or an editorial index/ledger.
Signature dishes deserve full-bleed presence; the full menu belongs in a typographic index.

Two tells that mark the same defect:
- **Uniform container reflex** — every real-world space (hall, garden, gazebo, dish, event)
  poured into the same rounded rectangle: `border-radius: 12-16px`, a generic box shadow,
  a flat grey or dark fill. It reads as an admin tool, pricing matrix, or task tracker,
  never a physical estate.
- **Box-in-a-box thumbnail syndrome** — a photograph nested in its own secondary rounded
  container *inside* an already bordered card. Two frames where zero are needed. The
  replacement frame is an **inset gold bezel on a full-bleed 1:1 media plane**, not a
  rounded thumbnail in a rounded card.

### H2 — Generic status pills
Never a status pill with a pulsing green/red dot ("Open Today • Live", "Active Now").
**Instead:** a typographic ledger line — `Open · 18:00–23:00` — or a jewel dot that carries
meaning. Reserve live indicators for live inventory the user is about to act on.

The tell is the fabricated software chrome: `<span class="pulse-dot"></span> Open Today •
12:00 PM – 11:30 PM` reads as an automated server health monitor, not a host.

### H3 — Fake chrome around media
Never mock window headers, tab strips with close buttons, or "LIVE MAP" status bars around
embedded media. A bar reading `Sky Hi Dining • Live Map` with a status dot and an expand
icon is the canonical violation.
**Instead:** media is an architectural plane. Full-bleed, no simulated OS or browser UI.
A luxury brand never pretends its website is a desktop operating system.

**Exempt only when the product genuinely is an OS or browser simulator** — a real desktop
emulator, a window manager demo, a terminal. There the chrome is the subject, not decoration.

### H4 — Raw embedded maps
Never an unstyled Google Map — pastel roads, yellow highways, cyan water, glaring terrain —
inside a dark interface.
**Instead:** custom monochromatic CSS filters plus a dark overlay, or purpose-built vector
or static cartography drawn to the palette. Grading equation in H17.

### H5 — Circular icon lists
Never an icon-in-a-circle stacked beside label rows for address, phone, or hours. Rounded
SVG glyphs in tinted circles — pin, telephone, clock, car — stacked in identical vertical
rows is the single most reliable signature of a generic WordPress theme or auto-template.
**Instead:** structured tabular ledgers, architectural key-value rows, or editorial copy.

### H6 — Fintech sans pairing
Never geometric startup sans (Outfit, Poppins, Inter, DM Sans, Montserrat) against a
classical luxury serif. The geometric circularity of Outfit beside Cormorant Garamond
projects fintech/crypto, not heritage.
**Instead:** humanist, Roman, or sharp editorial — **Plus Jakarta Sans** (sharp optical
precision) or **Tenor Sans** (classical Roman proportions), also Syne, Manrope. The sans
must defer to the serif, not compete with it.

**This is a *pairing* rule, not a ban on Inter.** Inter is a legitimate face for a clean,
technical product identity where the brand justifies it — T8 flags it as an unjustified
*identity default*. H6 fires only on the *mismatched pairing* against a display serif.
Report T8 for the default, H6 for the clash.

### H7 — Hover-gated core content
Never hide core sensory information — dish photos, ingredients, tasting notes, pricing —
entirely inside hover reveals unless explicitly instructed.
**Instead:** confident, static presence. Hover may *add*; it must never *gate*. Hover
dependencies also fail outright on touch devices, where no hover state exists at all —
so the information is not merely delayed, it is unreachable.

Generic case: **F7 — hover-locked essential data.** Same defect outside hospitality, where
the gated content is not dish photos but prices, specs, or primary actions.

### H13 — Commerce price and tag pills
Never trap a price (`₹200`), a tag, or a category inside a rounded pill, chip, or grey
button box. Price-in-chip is checkout-counter grammar; it converts a dining room into a
shopping cart. Category-in-chip does the same to the menu.
**Instead:** the **editorial dining ledger** — title in Cormorant Garamond, a hairline
dot-leader running to a standalone price set in gold serif numerals. The price is
typography, not a control. Tags are lightweight text labels or an integrated typographic
scale, never boxed controls.

### H14 — Retail menu chrome
Never put a search toolbar with a magnifying glass, pill-shaped filter chips, or an
"Expand All" toggle on a dining menu. It makes a restaurant read as an online pharmacy or
a retail catalog, and it admits the menu was too disorganised to navigate by structure.
**Instead:** category switching is editorial — a typographic index, a chapter curtain, or
a video chapter transition. Navigation by composition, never by filter apparatus.

### H15 — Spatial and factual hallucination
Never describe a ground-level botanical estate as a "rooftop venue", "high-rise", or
"skyline balcony". Never invent floors, views, amenities, awards, or capacity that the
property does not have.
**Severity: blocker.** This is the only pattern in the catalog that a guest can falsify by
arriving. Generic styling loses a booking; a fabricated rooftop loses trust permanently,
at the door. Verify every spatial and factual claim against the supplied brief; where the
brief is silent, omit the claim rather than defaulting to the aspirational one.

---

## 2. Mandatory Design Codes

Absence of these is itself the defect.

### H8 — The canvas over the card
Full-bleed backgrounds, architectural hairline borders
(`1px solid rgba(223, 191, 108, 0.18)`), and asymmetrical split viewports — rather than
boxed containers. Let the surface run to the edge. Deep ambient gradients, not floating
rounded boxes.

### H9 — Editorial typographic scale
Numbers, coordinates, and labels are design elements, not incidental text. Roman or serif
numerals ("01", "02"), wide letter-spacing (`0.2em`), small caps. An index of dishes reads
`01 — Rogan Josh`, not `1. Rogan Josh`.

### H10 — Discreet dietary and status indicators
Replace heavy "VEG / NON-VEG" badges with minimalist jewel dots — 4-6px glowing accents
framed in glass discs, `box-shadow` glow at low alpha, positioned discreetly on the media
frame. The information survives; the shouting does not.

**The FSSAI square is the specific forbidden form:** a bordered square with a green or red
dot inside. It is a packaging mark, and transplanting it onto a website signals cloud
kitchen, takeout, or a Zomato/Swiggy listing. Same ID, same fix — the jewel dot — so report
H10, never both.

### H11 — Cinematic media integration
Background video always carries calibrated gradient scrims — linear **and** vignette —
that bleed seamlessly into the dark palette without harsh edges. A scrim that fights the
palette is worse than none.

Media discipline, same code: footage stays **atmospheric, slow-motion, low-contrast**, so
text remains legible over it without harsh highlights and without the video competing with
the dish. Tandoor embers, a simmering rogan, steam in cold light. Never a stock whoosh,
a hard cut, or a parallax stunt.

### H12 — Tabular concierge hierarchy
Present arrival, contact, and venue data like a five-star concierge dossier: category key
on the left in letter-spaced uppercase sans, refined Cormorant Garamond serif value on the
right. A ledger, not a paragraph, and never an icon row.

### H16 — Architectural signature footer
The footer is the venue's signature, not a sitemap. It carries: a grand brand masthead, the
**direct telephone booking line** as the primary action (a real `tel:` link — the highest-
intent conversion a restaurant has), tabular navigation, and a large background **watermark
brand stamp** set in the display serif at low opacity.

Violation tell — the generic 3-column template: tiny corner logo, three plain link lists,
and floating circular SVG social icons. That footer belongs to every site and therefore to
no venue.

### H17 — Curated third-party grading
Any third-party embed — map, review strip, booking widget, social feed — inherits a foreign
palette and must be graded back into the house one. Never place a raw embed beside a
contact card in an uninspired 50/50 box split.

The grading equation, to be tuned per palette:

```css
filter: invert(92%) hue-rotate(185deg) saturate(35%) brightness(78%) contrast(125%);
```

Frame it asymmetrically instead: a floating glass **Concierge Dossier** over full-canvas
cartography, not two equal columns in a box.

**Relationship to H4:** H4 fires when the map is raw and default-styled. H17 fires when
*any* embed is ungraded or box-split. H4 is the specific case — report H4 for a raw map,
H17 for every other embed, never both for one element.

**Generic case: V19 — ungraded third-party embed.** Same defect outside hospitality, where
the palette clash is a credibility problem rather than a house-style violation.

### H18 — Page-archetype uniformity
Every page must be built from the venue's own spatial logic. The defect is one generic
template reused across the whole site: 3 feature boxes on the events page, a 3×3 grid on
the gallery, static paragraphs plus three icon bullets on the experience section, a 50/50
split on location.

Correction ledger — each archetype has its own correct architecture:

| Page / section | Uniform-template defect | Venue-logic architecture |
|---|---|---|
| Menu cards | 4 identical rounded cards, cropped image headers, hover drawers | 1:1 square media frames with inset gold bezels, discreet jewel dots, static tasting notes, bold serif numerals `01`, `02` |
| Individual dish | Rounded thumbnail, delivery badge, title, price in a chip | Editorial dining ledger: framed 1:1 thumbnail, floating jewel dot, Cormorant Garamond title, hairline dot-leader, standalone gold serif price |
| Experience | Static paragraphs with 3 generic icon bullets (Hall/Garden/Gazebo) | Full-screen 3-column vertical curtain — `flex: 1`, expanding to `flex: 1.7` on hover — individual looping video per column, gold dividers, cinematic scrims |
| Location / arrival | 50/50 box split, fake browser bar, raw bright map, vertical icon rows | Full-canvas monochromatic dark cartography (CSS filters) with an asymmetrical floating glass Concierge Dossier (key-value ledger) |
| Footer | Generic 3-column template, floating SVG circles | Architectural signature — masthead, telephone booking line, tabular nav, background watermark stamp (H16) |
| Menu page | Dry catalog: search box, status pills, static table | Culinary theater: ambient header video loop (tandoor embers / rogan simmer), category-switching video curtain, cursor-tracking dish portals |
| Event pages | 3 generic feature boxes with checkmark lists | Spatial occasions lookbook: alternating full-width visual spreads (Gazebo, Garden, Hall Buyout), each with guest-capacity specifications |
| Gallery | Uniform 3×3 grid plus generic lightbox | Asymmetric exhibition filmstrip: alternating portrait (4:5) and landscape (16:9) frames, stills mixed with living video cinemagraphs |

The page is a walk through the estate. Uniformity is the tell that no one has been there.

**Tell — every section a 50/50 split.** The unvarying half-and-half box is the clearest
single symptom of one shared template: text column left, media column right, repeated down
the page. Break it with full-width banners, asymmetric 40/60, tabular rows, or an
interactive multi-panel viewport. Generic case: **L10 — default 50/50 split reflex.**

---

## 3. Pre-Emit Checklist

Run before handing back any luxury hospitality UI:

- [ ] No 3+ sibling rounded cards with image headers and plain text bodies (H1)
- [ ] No box-in-a-box thumbnail — image nested in a rounded container inside a bordered card (H1)
- [ ] No animated or pulsing status dot (H2)
- [ ] No simulated window/tab chrome around media (H3)
- [ ] Every map is filtered or redrawn to the palette (H4)
- [ ] No icon-in-circle contact rows (H5)
- [ ] No geometric startup sans paired with the display serif (H6)
- [ ] No `<img>`, ingredient, tasting note, or price gated behind hover (H7)
- [ ] No price, tag, or category inside a pill, chip, or button box (H13)
- [ ] No search box, pill filter, or "Expand All" toggle on the menu (H14)
- [ ] Every spatial and factual claim is verifiable against the brief — no invented rooftop, floor, view, or capacity (H15)
- [ ] No section defaults to an unvarying 50/50 box split (H18 / L10)
- [ ] No class, ID, or `data-*` attribute renamed or removed where JS depends on it (Q9)
- [ ] Full-bleed sections and `rgba(gold, 0.18)` hairline borders present, not boxed containers (H8)
- [ ] Numerals, coordinates, and labels set editorially (H9)
- [ ] Dietary indicators are jewel dots, not badges or FSSAI squares (H10)
- [ ] Every background video has linear + vignette scrim, no hard edge; footage slow, atmospheric, low-contrast (H11)
- [ ] Contact/arrival data is a key-value dossier (H12)
- [ ] Footer carries masthead, telephone booking line, tabular nav, watermark stamp (H16)
- [ ] Every third-party embed is graded and asymmetrically framed, not box-split (H17)
- [ ] Each page uses its own architecturally-appropriate archetype, not one shared template (H18)

---

## 4. Exemption Rules

These are legitimate and must not be "fixed":

- **H1** — the grid *is* the product (a real listing or taxonomy the venue operates)
- **H2** — the status is live inventory the user is about to act on
- **H3** — the product genuinely is an OS or browser simulator; the chrome is the subject
- **H4** — the map is the primary interaction *and* is restyled to the palette
- **H7** — the user explicitly asked for hover-gated content on a named component
- **H9** — a house style guide mandates a different numeral treatment (cite the guide)
- **H10** — regulatory or allergy-safety labelling mandates explicit dietary text.
  **Safety labelling is never slop.**
- **H13** — the venue operates genuine e-commerce (retail jars, gift boxes shipped) where
  a price is an add-to-cart control, not a menu entry
- **H14** — the menu exceeds the scale where composition alone can navigate it, and search
  is a documented user need rather than template reflex
- **H16** — the venue has no telephone booking channel
- **H17** — the embed's own branding is contractually required (a booking partner's widget)

**H15 has no exemption.** A fabricated claim about the property is not a style choice.

---

## 5. Relationship to the Base Catalog

In this domain these H-IDs supersede their base-catalog equivalents. Report one, not both.

| H-ID | Supersedes | Note |
|------|-----------|------|
| H1 | L2, V6, I5, L4 | H1 when the cards carry image headers; also absorbs box-in-a-box nesting |
| H2 | V12, M4, M6 | H2 when the badge reports venue status; the pulse is the tell |
| H4 | C1, C4 | H4 is the cause; C1/C4 fire only on residual contrast after filtering |
| H5 | A4, L9 | H5 when the icon list encodes contact or venue data |
| H6 | T8, V14 | H6 names the *pairing* failure, which T8 does not |
| H7 | F7 | H7 names dish photos, ingredients, and tasting notes; F7 is the generic case |
| H10 | V12 | H10 when the badge is dietary — including the FSSAI square form |
| H8 | L4, V6 | H8 for "unbox", L4 for "un-nest" |
| H9 | T5, L5 (inverse) | T5/L5 flag decorative overuse; H9 flags editorial treatment that is absent |
| H13 | V12 | H13 when the capsule contains a price or a tag. Price is not a badge |
| H17 | V19 | H17 when the embed is a map or carries house-palette branding |
| H18 | L2, L3, L4, L10 | H18 is page-level; L2/L3/L4/L10 are the local symptoms it produces. Fix H18 first |

H3, H11, H14, H15, and H16 have no base-catalog equivalent — they are new.

### Generic ↔ Hospitality Mapping

The same defect exists at both scopes. Report it at the scope of the target — one report,
never both.

| Generic | Hospitality | Relationship |
|---------|-------------|--------------|
| V19 Ungraded third-party embed | H17 (any embed), H4 (maps) | Same defect; H17 carries the house-palette severity |
| V20 Unscrimmed ambient video | H11 | H11 adds the slow / atmospheric / low-contrast footage rule |
| F7 Hover-locked essential data | H7 | H7 names dish photos, ingredients, tasting notes |
| V18 Border-as-hierarchy crutch | H8 (inverse) | H8 is the positive framing: canvas over card |
| L10 Default 50/50 split reflex | H18 | H18 is page-level; L10 is the section-level symptom |
| L9 Non-semantic markup | H5 | H5 when the icon list encodes contact or venue data |

**Q9 — contract-breaking refactor applies at both scopes with no mapping.** Never rename,
remove, or modify existing classes, IDs, or `data-*` attributes while refactoring styles
when JS, data fetching, or event listeners depend on them. **Blocker**, Stage 1, in either
domain.

---

## 6. Application Order

When generating, resolve in this order — later choices depend on earlier ones:

1. **Truth** (H15, Q9) — establish the venue's real spatial and factual facts before any
   layout, and keep every existing class, ID, and `data-*` hook the JS depends on intact
2. **Canvas** (H8) — full-bleed planes and split viewports before any component exists
3. **Page archetype** (H18) — each page's own architecture, not one shared template
4. **Media** (H3, H4, H11, H17) — how imagery, video, maps, and embeds sit in the canvas
5. **Structure** (H1, H5, H12, H16) — index vs grid, ledger vs icon list, dossier vs prose, footer as signature
6. **Type** (H6, H9) — serif/sans pairing, then numeral and label treatment
7. **Indicators** (H2, H10, H13, H14) — status, dietary, price, and menu controls last, sized to the system
8. **Content presence** (H7) — confirm nothing sensory ended up behind a hover

Generating in reverse — indicators before canvas — is what produces a luxury site that
looks like a SaaS dashboard wearing a serif font. Skipping step 1 is what produces a
beautiful site that lies about the building.
