---
name: ui-antislop
description: Layout and visual rules that stop the model from assembling a generic AI landing page. Apply to anything with HTML/CSS, components, screens, mockups or dashboards.
---

# UI without slop

## When to apply

Any task whose result is seen: a page, a component, an email, a desktop window, a dashboard, a mobile screen.

## Banned patterns

| Pattern | Why it is bad | Replacement |
|---|---|---|
| `#6366f1 → #a855f7` gradient | the most common generation default, reads as "made in ten seconds" | one accent colour; a gradient only when it carries meaning (a scale) |
| Glass panels with `backdrop-filter: blur(20px)` | kills text contrast, breaks readability on light backgrounds | solid `#fff` / `#111` with a 1px border |
| Aurora blobs, noise, stars behind the hero | unrelated to the product | background colour or a real product screenshot |
| 24–32px radius on everything | flattens the hierarchy, all blocks look the same | 4–8px radius, 12px for large surfaces |
| A shadow on every card | destroys the idea of layers | shadow only on what actually floats: popover, menu, modal |
| `box-shadow` on text, `filter: drop-shadow` on a headline | dirt on any background | weight and size |
| Inter / Poppins by default with `letter-spacing: -0.03em` | a visual cliché marker | the project font or a system stack; do not touch tracking without a reason |
| Emoji as icons: 🚀 ✨ 🔥 ✅ | different rendering, different sizes, childish look | SVG `<path>`, one `stroke-width` |
| Three feature cards with the same icon in a circle | nothing to say about the product | a list of 2–5 points as text, or a comparison table |
| "Trusted by 10,000+", "★★★★★", testimonials with invented names | fake social proof | numbers that can be checked, or nothing |
| `Lorem ipsum`, `Your tagline here`, `href="#"` | gives away a draft | real copy, or an explicit `<!-- TODO: copy -->` next to it |

## Typography

- A scale of 4–5 sizes, no more. Example: 12 / 14 / 16 / 20 / 32.
- Line-height: 1.5 for body, 1.15–1.25 for headings.
- Line length: 60–75 characters (`max-width: 72ch`).
- Weight instead of size: importance comes from 400/500/600, not from jumping 14 to 40.
- A first-screen headline fits in two lines on desktop. If it does not, the text is long, not the column narrow.
- No all-caps, no `letter-spacing` above 0.08em except small labels.

## Colour

- Base: one neutral row (background, surface, border, text, muted text). One accent.
- Text contrast ≥ 4.5:1, large text ≥ 3:1. Verify it, do not assume it.
- Never encode meaning with colour alone: an error is colour plus text plus icon.
- A dark theme is not an inversion. Separate background and border values, the accent goes 10–15% lighter.

## Grid and spacing

- Step of 4px or 8px. Every spacing value is a multiple.
- Vertical rhythm: identical distances between identical blocks.
- Container: `max-width` for the content, not "full width with 5% margins".
- Check three widths: 320, 768, 1280. Nothing may overflow at 320.

## Components and states

Every interactive element needs:

- `:hover` — background or border change, not scaling.
- `:focus-visible` — a visible 2px outline with offset, never `outline: none`.
- `:active` — 1px shift or background change.
- `disabled` — dimmed, `cursor: not-allowed`, no animation.
- `loading` — spinner or skeleton with fixed dimensions, so the layout does not jump.
- `error` — the message under the field, `aria-invalid`, not just a red border.
- `empty` — what happened and what to do next, one button.

Forms: label above the field, `label` bound to `input`, error after the field. A placeholder is not a label.

## Graphics and icons

- Icons are vectors from one set, `stroke-width` 1.5–2, sizes 16/20/24, `fill="none"`.
- An icon without a label is allowed only for universally understood actions (close, search, back).
- Images: meaningful `alt`, `width`/`height` set, aspect ratio preserved.
- Illustrations only when they explain something. Decorative 3D people — no.

## Motion

- Allowed: popover appearing, accordion expanding, state change — 120–200ms, `ease-out`.
- Not allowed: fade-in on scroll for every block, parallax, endless pulses.
- Respect `prefers-reduced-motion: reduce`.

## Placeholder copy

Square brackets in the visible UI are forbidden: `[product name]`, `[Short headline about what the product does]`, `[product screenshot]`. A page made of placeholders is not a mockup, it is a refusal to work.

What to do when there is no content:

1. Ask with the brief (see `skills/brief-antislop/SKILL.md`) — four questions with defaults.
2. If asking is impossible, write working copy without invented numbers: "Download", not "Download · 12.4 MB"; "A tool for assembling releases", not "[Short headline]".
3. Keep the note about the unknown as a code comment: `<!-- TODO: exact product name -->`.

Invented testimonials, customer logos and metrics are forbidden. A missing block beats a fabricated block. A grey rectangle instead of a screenshot is acceptable only when the caption says what goes there and at which size.

## Acceptance

1. Open at 320px: is there a horizontal scroll? If yes — redo.
2. Tab through the page: is the focus visible? If not — fix `:focus-visible`.
3. Drop the screen brightness to 40%: is the text readable?
4. Remove all shadows and gradients: is the interface still clear? If yes, they were unnecessary.
5. Check text contrast with a calculator, not by eye.
