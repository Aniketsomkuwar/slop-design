# slop-design

Design contract for AI agents: 245 anti-patterns to read before generating UI.

![slop-design](assets/hero.png)

Generated interfaces converge. The same card grid, the same violet gradient, the same three-icon feature row. This skill is the reference that stops it before the first line of markup: a catalog of what not to build, a workflow for what to build instead, and a gate that blocks delivery when the page still reads as a template.

It is a knowledge base, not a scanner. [slop-audit](https://github.com/Aniketsomkuwar/slop-audit) is the operational half.

## What it covers

Eighteen categories, 245 patterns, each with an ID, a detection rule and a replacement principle:

- **Render surface:** visual (V1-V21), typography (T1-T18), colour (C1-C11), layout (L1-L13), motion (M1-M18), copy (P1-P9), imagery (I1-I6), quality (Q1-Q10), composition (X1-X10), accessibility (A1-A16), tokens (D1-D6), state coverage (S1-S8), real content (R1-R6), responsive (B1-B5), interaction (F1-F7), dark mode (DM1-DM5).
- **Domain:** luxury hospitality and fine dining (H1-H18), activated only when the target is a venue.
- **Source:** engineering slop (E1-E58) - effects without cleanup, fetch races, secrets in the client bundle, `any` at the trust boundary, god components.

The catalog says what not to build. `references/design-spec.md` says how to build: the five-stage workflow, motion/colour/type token tables, and the pre-emit gate. `references/rule-gate.md` adds the decision layer: 38 rules in three tiers, the ENERGY/RHYTHM/MOTION dials, a Design Read, and a four-block PASS/FAIL Delivery Gate.

Alongside those, four specialised references cover the surfaces a landing-page catalog under-serves: copywriting with before/after rewrites, accessibility and mobile reflow (with a WCAG contrast checker), app and dashboard screens, and code comments.

## What is in the repo

| Path | Purpose |
|---|---|
| `SKILL.md` | The skill entry point: role, objective, loading order, catalog |
| `references/slop-patterns.md` | The full 245-pattern catalog with detection rules |
| `references/design-spec.md` | Construction workflow, token tables, pre-emit gate |
| `references/code-slop-guide.md` | The E1-E58 source contract, grep signatures, per-framework equivalents |
| `references/prompt-library.md` | Copy-paste activation prompts per stage |
| `references/luxury-hospitality-protocol.md` | H1-H18 domain contract |
| `references/content-quality-guidelines.md` | Copy and content quality rules |
| `references/regex-debugging.md` | Notes for the scanner patterns |
| `references/rule-gate.md` | 38 rules, three tiers, liveliness dials, Design Read, Delivery Gate |
| `references/copywriting.md` | Copy patterns, human-writing guardrails, voice calibration |
| `references/accessibility-mobile.md` | Contrast formula and table, keyboard, focus, states, reflow |
| `references/app-comments.md` | Dashboard screens and code-comment hygiene |
| `references/contrast-check.py` | WCAG contrast checker, with a self-test against the table |

## Install

### With an AI agent

Paste [`prompt.md`](prompt.md). It detects the OS, asks where skills live, copies the skill, verifies the frontmatter and tells you how to load it.

### Manually

```bash
git clone https://github.com/Aniketsomkuwar/slop-design.git
mkdir -p ~/.agents/skills/slop-design
cp -R slop-design/SKILL.md slop-design/references slop-design/README.md ~/.agents/skills/slop-design/
```

On Windows PowerShell, the same target is `%USERPROFILE%\.agents\skills\slop-design`. If your agent reads skills from another directory, use that one instead.

Restart the session, then:

```text
/skill slop-design
```

## Use

Load the skill before you generate or redesign UI. The order matters:

1. Read `references/slop-patterns.md` and check each design decision against the catalog.
2. Read `references/design-spec.md` and follow the five stages.
3. Before delivery, run the pre-emit gate. A failed check blocks the output; it is not a suggestion.

For a luxury hospitality or fine-dining target, also read the H1-H18 protocol. The domain test is whether the page says "this place exists" or "this place is listed".

## The pair

[slop-audit](https://github.com/Aniketsomkuwar/slop-audit) detects and tracks slop in existing code. This repo prevents it. Install both if you want the full loop: design before, audit after.

Each repo is self-contained. A few references are byte-identical between them so either can be installed alone.

## Scope

- No scanning, no tracking, no network calls, no telemetry.
- No files written outside the skill directory.
- It changes what an agent writes; it does not change an app at runtime.

## Credits and lineage

Created by Aniket Somkuwar. Integrates slop patterns from `miqdadbadjuber/anti-slop`, `discountry/ritmex-skills` (anti-ui-slop), and the motion principles popularised by Emil Kowalski: transform/opacity only, named transitions, duration scaled to distance and frequency.

v3.5.0 extends the source-code catalog with material from `Vanszs/Anti-AI-UI` (MIT), `design-taste-frontend`, `emilkowalski/skills`, `impeccable` (Apache 2.0) and `leeskills` (MIT): the E category, A9-A16, and the evidence-class and completion-rule discipline.

v3.6.0 merges the antislop rule system (MIT, `miqdadbadjuber/anti-slop`) as four references and a contrast checker. The 245 pattern IDs are unchanged.

Third-party material remains under its own license. See [`LICENSE`](LICENSE) for this repository's terms.

## Version

3.6.0. The skill frontmatter is the source of truth.
