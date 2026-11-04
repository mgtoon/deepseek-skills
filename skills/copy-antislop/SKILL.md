---
name: copy-antislop
description: Copy rules for interfaces and documentation that remove the marketing AI tone. Apply to headlines, buttons, errors, READMEs and project descriptions.
---

# Copy without slop

## When to apply

Any text a human reads: a landing page, an interface, an email, a README, a repository description, an error message.

## Stop formulas

Do not use in any form:

- "In today's fast-paced world…", "In the age of digitalisation…"
- "It is not just X, it is Y"
- "Let us dive in", "Imagine that…", "As you know…"
- "seamless", "powerful yet flexible", "revolutionary", "innovative", "unique"
- "unlock your potential", "take it to the next level", "elevate", "game-changer"
- "we believe technology should…"
- "Hope this helps", "Let me know if you need anything else"

## How to write

- One statement — one sentence. A full stop instead of a comma with "which".
- Specifics instead of evaluation: not "fast", but "responds in 120ms on 10,000 records".
- Never promise what the code does not do. Every "supports" is checked against the implementation.
- Active voice: "the service removes duplicates", not "duplicates are removed by the service".
- Do not start a paragraph with "Moreover", "Furthermore", "It is also worth noting".
- Numbers as digits when they are data: "3 steps", "2 files".

## Interface

**Buttons.** Verb plus object: "Save draft", "Delete invoice". Not "Submit" when it is unclear what is submitted. Not "OK" and not "Yes" in confirmation dialogs.

**Headlines.** Up to six words. No wordplay, no "Welcome to the future".

**Errors.** What happened, why, what to do:
> Could not save: no connection. Your changes are still in the browser, retry in a minute.

Not "An error occurred", not "Something went wrong".

**Empty states.** What will appear here and how to add it. One button.

**Hints.** Only where people would otherwise make a mistake. Do not explain the obvious.

## README

Order: what it is → why → install → run → example → limitations.

- The first paragraph answers "what do I get", without project history.
- Commands can be copied and they work. Not "install dependencies in the usual way".
- Limitations are stated honestly: what is missing, what is unsupported.
- No badges that nobody updates.

## Repository description

One line, up to 100 characters, no trailing period: what it does and for whom. Not "A powerful tool for…".

## Checks

1. Remove every adjective that is not backed by a number or a fact. Does the meaning survive? Then they were filler.
2. Read it aloud. If it sounds like a TV ad — rewrite.
3. Find every "we". Ask: who is "we"? If you cannot name them, remove it.
