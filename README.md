# write-cut

![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)

Agent skill for writing and editing technical documentation in infostyle.

Based on Maxim Iliyakhov's books ["Пиши, сокращай"](https://book.ilyahov.ru/) ("Write, Cut") and "Ясно, понятно" ("Clear, Understandable").

## What it does

Guides the agent to produce documentation that is:
- Concise — removes filler, nominalizations, and AI boilerplate
- Scannable — uses lists and checklists over dense prose
- Honest — replaces vague adjectives with facts and metrics
- Clear — active voice, one idea per paragraph

Rules apply to **any language** — English, Russian, German, and others.

## When to activate

Ask the agent to use `write-cut` when:
- Writing or reviewing a README
- Drafting a postmortem or incident report
- Creating a technical plan or spec
- Writing API documentation or instructions
- Editing any text that explains or records something

## Installation

```bash
npx skills add todatasudata/write-cut
```

## How to activate

The skill loads automatically in every conversation (`alwaysApply: true`).

To invoke explicitly:

```
Use the write-cut skill to write/edit the following: ...
```

## Token consumption

`SKILL.md` loads as a Core Skill (`alwaysApply: true`) — added to every conversation context.

- **~2200 tokens** per conversation (1704 words × ~1.3 tokens/word, mixed EN/RU/DE content)

## Structure

```
write-cut/
├── SKILL.md    # Agent instructions (loaded by agent)
├── README.md   # This file (not loaded)
└── SPEC.md     # Original Russian specification, archive (not loaded)
```

## Credits

Rules based on:
- Maxim Iliyakhov — *Пиши, сокращай* (Write, Cut)
- Maxim Iliyakhov — *Ясно, понятно* (Clear, Understandable)















