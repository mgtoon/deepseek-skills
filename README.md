# deepseek-skills

Prompt skills for DeepSeek that switch off "AI slop": template landing pages and placeholder-riddled code.

## What counts as slop

**Sites.** Purple-to-blue gradient, glass cards with blur, emoji instead of icons, "Trusted by 10,000+", three identical feature cards, everything rounded to 24px, Inter by default, a fade-in on every block.

**Code.** `BaseManagerFactoryProvider` for one table, empty `try/catch`, a dependency for one function, "done" with three TODOs in the body, names like `data`, `result`, `temp`.

**Copy.** "In today's fast-paced world…", "It is not just a tool, it is a philosophy", "seamless", "powerful yet flexible", "unlock your potential".

## Contents

| Path | Purpose |
|---|---|
| `DEEPSEEK.md` | compact system prompt, paste as the first message |
| `skills/brief-antislop/SKILL.md` | four questions before any markup: direction, density, theme, content |
| `skills/ui-antislop/SKILL.md` | typography, palette, grid, states, banned patterns |
| `skills/code-antislop/SKILL.md` | structure, naming, errors, dependencies, placeholders |
| `skills/copy-antislop/SKILL.md` | UI copy, errors, empty states, README |
| `skills/deep-audit/SKILL.md` | ten review passes before delivery |
| `skills/review-antislop/SKILL.md` | acceptance checks and self-review |
| `checklists/pre-release.md` | flat pre-ship checklist |

## How to use it

### DeepSeek chat

1. Open `DEEPSEEK.md` and copy it in full.
2. Paste it as the first message, then describe the task.
3. If the task is about UI, send the relevant `SKILL.md` as the second message: "Work by this skill from now on".

### API

```python
system = (
    open("DEEPSEEK.md", encoding="utf-8").read()
    + "\n\n"
    + open("skills/ui-antislop/SKILL.md", encoding="utf-8").read()
)
```

Skills are plain markdown with `name`/`description` frontmatter, so they fit any setup that reads rules from files: `.deepseek/`, `.cursor/rules/`, `AGENTS.md`.

## Principle

The skills do not forbid good design. They forbid **the default**: a decision made because every second generation makes it, not because it fits the task. Any deviation is allowed if the model can state the reason in one sentence and that reason belongs to the project, not to a template.

## License

MIT.
