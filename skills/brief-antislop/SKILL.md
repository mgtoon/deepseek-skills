---
name: brief-antislop
description: Mandatory short brief before any layout work. Four questions with defaults covering direction (minimalist or design-accent), density, theme and content. Stops the model from falling into a template or shipping square-bracket placeholders.
---

# Brief before markup

## The rule

Before the first line of HTML, ask **one** block of questions. No more than four. Every question carries options and a default, so the user can answer "2, defaults" and get the work immediately.

If the user already described everything — do not ask. Repeat their choice in one line and start.

## Questions

**1. Direction**

- **A. Minimalist.** Lots of air, thin rules, one accent colour, a large headline and a quiet body. No decoration, no icons in circles, no animation.
- **B. Design-accent.** Large typography, an expressive grid, colour planes, contrast of scale. No gradients, glass, neon or text shadows.
- **C. Utilitarian.** Dense grid, tables, tabular numerals, zero decoration. For admin panels, dashboards, documentation.
- **D. Poster.** High contrast, asymmetry, big numbers, magazine margins. For a landing page with a single idea.

Default: **A**.

**2. Density.** Compact (14px base, 8–12 spacing) / normal (16px, 16–24) / large (18px, 24–40). Default: normal.

**3. Theme.** Light / dark / both. Default: light.

**4. Content.** Real copy and data from the user / permission to write it yourself / structure only, no text.

For a landing page add one question: **what should the visitor do** — download, buy, request, read.

## Applying the answers

- Direction decides everything: container width, headline size, number of accents, presence of borders.
- Minimalist: one accent, one large headline size, 1px borders, shadow only on overlays.
- Design-accent: two or three colour planes, big numbers, but the one-accent rule still holds; check contrast.
- Poster: headline 48–72px, body 16–18px, large spacing, real imagery.
- Utilitarian: 13–14px, tables, `font-variant-numeric: tabular-nums`, no illustrations.

## Placeholders

Square brackets must not appear in the visible UI: `[product name]`, `[Short headline]`, `[screenshot]` is not a mockup, it is a refusal to do the work.

If a fact is unknown:

1. Ask — if the page cannot exist without it.
2. Write an honest sentence without an invented number: "Download", not "Download · 12.4 MB".
3. Leave `<!-- TODO: exact product name -->` in the code, and in the UI write a working phrase: "A tool for assembling releases".

Invented testimonials, customer logos and metrics are forbidden. A missing block beats a fabricated block.

## What makes a site good without slop

- Hierarchy: one main headline, one accent, three levels of text.
- Rhythm: identical spacing between identical blocks.
- Air: empty space is part of the composition, not an unfinished corner.
- Typography instead of effects: size, weight, line-height.
- Real data and screenshots instead of grey rectangles.
- One memorable detail: a large number, an unusual grid, a precise caption. One, not five.

## Acceptance

1. Can you name the direction in one phrase? If not, two styles got mixed — pick one.
2. There is not a single square bracket in the UI.
3. Every block answers a user question instead of filling space.
