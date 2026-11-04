---
name: review-antislop
description: Acceptance checklist and model self-review before delivery. Required at the end of any code or interface task.
---

# Acceptance without self-deception

## How to use

Go through the items top to bottom. Each one is yes or no. If "no" — fix it, do not explain why it happened. A model that justifies a cliché instead of removing it has not done the task.

## Interface

- [ ] No horizontal scroll at 320px.
- [ ] Every interactive element is visible when tabbing.
- [ ] Text and background contrast was measured, not estimated by eye.
- [ ] All states exist: hover, focus, active, disabled, loading, error, empty.
- [ ] No emoji as icons; icons are vectors from one set.
- [ ] No invented testimonials, customer logos or metrics.
- [ ] No `href="#"`, `Lorem ipsum`, `TODO` in finished blocks.
- [ ] Shadows and gradients: each has a reason that fits in one sentence.

## Code

- [ ] The project builds from scratch without errors and without warnings I introduced.
- [ ] The main path and one failing path were verified by running them.
- [ ] The diff has no `TODO` without an owner, no `console.log`, no commented-out code.
- [ ] No new dependencies without justification.
- [ ] No secrets, keys or local machine paths in the diff.
- [ ] Variable names read without context.
- [ ] Error handling only where there is I/O.
- [ ] I did not disable the linter, tests or type checking to "make it pass".

## Copy

- [ ] No stop formulas from `skills/copy-antislop`.
- [ ] Every promise is backed by code or removed.
- [ ] Errors explain what to do next.

## The answer

- [ ] I do not praise my own work and do not apologise for the length.
- [ ] I named what is not done and why.
- [ ] I did not ask questions that the task already answers.
- [ ] Assumptions are listed explicitly.

## Report format

Short, without "Introduction" and "Conclusion":

```
Done: <1–3 items>
Not done: <item + reason> (if any)
Verified: <how exactly: build, run, screenshot>
Risks: <what may break> (if any)
```
