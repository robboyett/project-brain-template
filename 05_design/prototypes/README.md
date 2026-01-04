# Prototypes

This folder houses coded prototypes and their planning docs.

## Structure

```
prototypes/
├── README.md              ← You are here
├── _prototype-brief-template.md
├── _prototype-log-template.md
└── [prototype-name]/      ← One folder per prototype
    ├── brief.md           ← What we're testing, hypotheses
    ├── log.md             ← What we learned, iterations
    └── [code or link]     ← The actual build
```

## When to create a prototype folder

Create a new prototype folder when:
- Testing a specific hypothesis that needs to be coded
- Exploring a technical approach before committing
- Building something to show stakeholders for feedback
- Validating feasibility of a design direction

## What goes where

### `brief.md`
Created **before** building. Captures:
- What hypothesis we're testing
- Success criteria (how we'll know it worked)
- Scope boundaries (what's in/out)
- Time box

### `log.md`
Updated **during and after** building. Captures:
- What we built (with links/screenshots)
- What we learned
- What we'd do differently
- Recommendations for next steps

### The build itself
Options:
- **In-folder**: Simple HTML/CSS/JS can live here directly
- **Linked repo**: For larger builds, link to an external repository
- **Deployed link**: If hosted somewhere, link to the live version

## Naming conventions

- Folder names: `lowercase-hyphenated-descriptive-name`
- Date prefix optional but useful for sequencing: `2025-01-04-checkout-flow-v2`

## Tips

- **Keep prototypes disposable** — they exist to learn, not to ship
- **Document the "why"** — a prototype without a brief is just code
- **Close the loop** — always write up learnings, even if brief
- **Link to decisions** — if a prototype informs an ADR, reference it
