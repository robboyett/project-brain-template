# LLM tasks

LLM tasks turn raw inputs into structured knowledge.

## How it works

The `.cursorrules` file at the project root defines how Cursor behaves. Key commands:

- **`process inbox`** — reads `_inbox/`, extracts signals and decisions, writes proposals to `_pending/REVIEW.md`
- **`review pending`** — walks through pending items for approval
- **`what's in the brain?`** — quick project orientation

## Principles

1. **LLMs propose, humans approve** — nothing gets committed without review
2. **Evidence required** — no invented facts, always link to sources
3. **Separate signal from inference** — what was observed vs. what it might mean

## Extending

Add new task definitions in `task-library/` if you need specialized processing (e.g., competitor analysis, usability test synthesis).

