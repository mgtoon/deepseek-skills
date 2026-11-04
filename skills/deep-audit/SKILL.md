---
name: deep-audit
description: Deep review mode for DeepSeek: ten separate passes over code, behaviour and design before delivering. Use whenever thinking mode is on or the task is bigger than one file.
---

# Ten review passes

## The rule

Ten passes mean ten different checks, not one general look. Each ends with a **fix** if something was found. "The pass did not happen" is not a report: if a check does not apply, write "pass 6: not applicable, there is no interface".

The order is fixed: 1 → 10. Never start with design before the code builds.

## Passes

**1. Build.** The project compiles from scratch the way the project does it. No errors. Warnings I introduced are fixed. Do not disable linters, types or tests to "make it build".

**2. Run.** The main path goes through end to end. A task is not done if the code was never executed.

**3. Boundaries.** Empty input, zero, negative number, maximum length, missing file, empty list, double submit. Each case has defined behaviour, not a stack trace.

**4. I/O errors.** Network, files, parsing, external commands. Check: timeout, refusal, partial response, retry. No empty `catch`, no swallowed exceptions.

**5. Security.** No secrets in code. SQL is parameterised. User input is validated on entry. Paths are normalised. No `eval`, no `innerHTML` with user data, no disabled certificate checks and no `--insecure` by default.

**6. Accessibility.** Tab through the page: focus is visible. Fields have `label`, images have `alt`, errors have `aria-invalid` plus text. Text contrast ≥ 4.5:1 — verified with a calculator. Icon buttons have a label.

**7. Responsive.** 320, 768, 1280px. No horizontal scroll, nothing overlaps. Text stretched to twice the length does not break the card.

**8. Our design.** Re-read `skills/ui-antislop/SKILL.md` and `skills/brief-antislop/SKILL.md` before this pass and check line by line:
- one direction, named (minimalist / design-accent / utilitarian / poster);
- one accent colour, no more than five font sizes;
- radii 4–8px, up to 12 for large surfaces;
- shadows only on overlays: popover, menu, modal;
- icons are vectors with one `stroke-width`, no emoji;
- every state: hover, focus-visible, active, disabled, loading, error, empty;
- no gradients without meaning, no glass, no aurora blobs, no "Trusted by 10,000+";
- no square brackets and no `Lorem ipsum` in visible text.

**9. Weight and speed.** New dependencies are justified. No queries in a loop, no full-size images in a thumbnail, no blocking scripts without need.

**10. The whole diff.** Read the changes as someone else's code: names read well, no dead code, no debug output, `TODO` only with an owner, comments explain "why".

## Report

End the answer with seven lines at most:

```
Pass 1: build — ok
Pass 3: boundaries — added empty-input check
Pass 6: accessibility — added focus-visible
Pass 8: design — removed card shadow, kept it on the menu
Pass 10: diff — removed console.log
Not checked: pass 9, no dependencies added
Risks: none
```

## Forbidden

- Writing "everything is checked" when nothing was run.
- Justifying a cliché instead of fixing it.
- Skipping pass 8 "because the task is backend" — if there is no interface, say so.
- Running the review from memory: the design rules are re-read during pass 8.
