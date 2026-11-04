---
name: code-antislop
description: Coding rules that stop the model from generating architecture for the sake of architecture, empty stubs and unnecessary dependencies. Apply to any task with source files.
---

# Code without slop

## When to apply

A new feature, a change in existing code, a refactor, a bug hunt, a review.

## Main rule

Code is written for the task, not for a textbook. Every abstraction must pay off now, not "later": if a second implementation does not exist, the interface is not needed.

## Structure

- Do not multiply layers. For CRUD, three are enough: data model, data access, handler. That is all.
- One file, one responsibility. If the filename contains "and", it is two files.
- A function fits 40 lines and one screen. Longer — split by meaning, not by line numbers.
- Nesting up to three levels. Deeper — use early `return`.
- Minimise shared state. A global is acceptable when it is configuration or a process-level cache, and it is named accordingly.
- The project style beats personal habits: read the neighbouring code first, then write.

## Naming

- Banned: `data`, `info`, `result`, `temp`, `obj`, `item2`, `handleData`, `process`.
- Functions are verbs: `loadInvoices`, `retryRequest`, `parseHeader`.
- Booleans are `is`/`has`/`can`: `isDirty`, `hasAccess`.
- Units in the name when it is a number: `timeoutMs`, `sizeBytes`, `retryDelaySec`.
- One entity keeps one name across the whole project. Not `user` here and `account` there.

## Errors

- `try/catch` only where there is I/O: network, files, parsing, external processes.
- Catch a specific exception, not everything.
- An empty handler is forbidden. Either recovery, or a rethrow with context, or an explicit log and a decision.
- The error text says what was being done, with what, and what happens next. Not "Error", not "Something went wrong".
- The user gets a human sentence, the log gets technical detail with a stack trace.
- Do not swallow errors "so it does not crash". A crash with a clear message beats silent data corruption.

## Dependencies

- Before adding a package, check whether the standard library solves it.
- One function is not a reason for a package. A package means updates, vulnerabilities and weight.
- Do not drag in a framework for three screens.
- Pin versions, check that versions are current.
- No dependencies from unverified sources, no "universal helpers" with obfuscated code.

## Stubs

- `TODO` is allowed only with an owner: `// TODO(auth): replace with a refresh token`.
- Never ship a function returning fake data without saying so in the name: `mockInvoiceList` instead of `getInvoices`.
- "Done" means: it builds, it runs, it handles empty input, it handles I/O failure.
- Do not disable type checks or linters to "make it build".

## Comments

- A comment explains **why**, not **what**. `// wait 200ms: the API serves a stale cache right after a write`.
- Do not comment the obvious.
- Do not leave commented-out code. Delete it: history lives in git.
- Public functions get a short contract: what it takes, what it returns, what it throws.

## Tests

- A test checks behaviour, not implementation: input → output.
- One test, one reason to fail.
- Do not test getters or trivial constructors.
- Mandatory minimum: boundaries (0, empty, maximum), I/O failure, the main path.

## Security

- No secrets in code or in the repository. Environment variables and gitignored files only.
- SQL is parameterised, always.
- User input is validated on entry, not "somewhere later".
- Paths from input are normalised, `..` is rejected.

## Acceptance

1. Build the project from scratch: `dotnet build` / `npm run build` / `python -m compileall`. No errors.
2. Run the main path and one failing path.
3. Search the diff for `TODO`, `console.log`, `print(`, commented-out code.
4. Check that no new dependency was added without a reason.
5. Read the diff aloud: if a line needs explaining, rewrite it.
