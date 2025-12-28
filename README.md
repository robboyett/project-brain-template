# Project brain

## How to use this

**Drop things in `_inbox/`.** That's it.

Then type `process inbox` in Cursor. AI extracts the useful stuff and proposes updates. You review and approve in `_pending/REVIEW.md`.

No filing. No remembering where things go. The structure maintains itself.

### The full workflow (still simple)

| Step | Action | Time |
|------|--------|------|
| 1 | Drop anything in `_inbox/` — notes, transcripts, thoughts | 5 sec |
| 2 | Type `process inbox` in Cursor | 2 sec |
| 3 | Review proposals in `_pending/REVIEW.md` | 5 min |
| 4 | Approve, edit, or reject each item | Done |

### Other commands

- `review pending` — walk through pending items interactively
- `what's in the brain?` — quick project orientation
- `summarise stakeholder [name]` — get a stakeholder summary

---

## Where things live

| What | Where |
|------|-------|
| Drop raw inputs here | `_inbox/` |
| AI proposals for review | `_pending/REVIEW.md` |
| Stakeholder profiles | `02_people/stakeholders/` |
| Themes, risks, opportunities | `03_discovery/synthesis/insights.md` |
| Decisions (ADRs) | `04_product/decisions/` |
| Problem framing | `04_product/problem-framing.md` |
| Org/industry context | `01_context/` |
| Design rationale | `05_design/` |
| Weekly updates | `06_delivery/updates/` |

You don't need to memorise this — Cursor handles the filing.

---

## Quick links

- [Inbox](./_inbox/) — drop stuff here
- [Pending review](./_pending/REVIEW.md) — approve AI proposals
- [Stakeholders](./02_people/stakeholders/)
- [Insights](./03_discovery/synthesis/insights.md)
- [Decisions](./04_product/decisions/)

---

## What you can do with this

Everyone on the team keeps a copy of this brain on their machine. It's not just storage — it's a working tool.

### Ask questions

Open Cursor (or any AI tool that can read files) and ask:

- "What do we know about Sarah's concerns?"
- "Summarise the decisions we've made so far"
- "What are the main risks we've identified?"
- "What did we learn in the last round of interviews?"

The AI has context. Answers are grounded in actual project knowledge, not generic guesses.

### Generate work

Use the brain to draft real outputs:

- "Write a stakeholder update email for this week"
- "Draft talking points for the steering committee"
- "Compare our findings to what the client originally asked for"
- "Suggest what we should explore next based on the themes"

### Stay in sync

Pull the latest changes from git. Everyone sees the same knowledge. New team members get oriented in minutes, not days.

---

## As the project grows

Early on, everything is relevant. But as the brain accumulates knowledge, some things matter more than others.

You need to think about this when:
- The project has gone for a few iterations of decision making
- AI responses start feeling unfocused or pulling in old/stale content
- New team members ask "what should I actually read?"

### How to mark importance

Add simple frontmatter at the top of any document:

```yaml
---
status: active
importance: high
confidence: medium
---
```

**Status options:**
- `active` — current, relevant (default)
- `archived` — outdated, superseded, or no longer relevant
- `draft` — work in progress, not yet reliable

**Importance** (only add when notable):
- `high` — core to current work, read this first

**Confidence** (only add when uncertain):
- `low` — early hypothesis, needs validation
- `medium` — reasonable belief, some evidence
- `high` — well-established, strong evidence

### What this enables

When you ask Cursor questions, it can prioritise:
- Active over archived content
- High-importance documents over background material
- High-confidence insights over tentative ones

You can also ask things like:
- "What are our high-confidence themes?"
- "Show me active decisions only"
- "What's marked as low confidence that we should validate?"

### Moving things to archive

When something is no longer relevant:
1. Move the file to `_archive/`
2. Or just add `status: archived` to its frontmatter

Archived content isn't deleted — it's still searchable if you need history. It just stops cluttering current queries.

---

## Why this works

Most project knowledge lives in people's heads, scattered docs, or gets repeated in every meeting.

This system fixes that by making knowledge:
- **Queryable** — ask questions, get grounded answers
- **Generative** — produce new work from accumulated understanding
- **Shared** — everyone has the same context
- **Maintained by AI** — you drop stuff in, it organises

**You** do the thinking — conversations, research, design.
**The brain** remembers what was said and decided.
**AI** does the organising and retrieval.

If it ever feels like overhead, simplify. The structure serves you, not the other way around.
