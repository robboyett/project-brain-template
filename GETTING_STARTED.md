# Getting started

This guide explains how to use the project brain day to day.
It focuses on the things you will do *often*, not edge cases.

If in doubt, remember the rule:
**If it matters, it lands in the repo.**

---

## First 10 minutes on a new project

1. Open `README.md`
2. Read:
   - project summary
   - current state
   - open questions
3. Skim:
   - `/01_context/org-overview.md`
   - `/01_context/industry-brief.md`
4. Open:
   - `/03_discovery/synthesis/themes.md`
   - `/04_product/decisions/`

You should be oriented in under 10 minutes.  
If not, the repo needs tidying.

---

## What to do with meeting recordings and transcripts

### After *any* important meeting (interview, workshop, steerco)

**Goal:** convert conversation into durable knowledge.

#### Step 1: store the raw artefact
- Save transcript or notes into:

/03_discovery/research/YYYY-MM-DD_.md

- Link to:
- audio/video
- slides
- FigJam board (if used)

Messy is fine at this stage.

#### Step 2: run the transcript pipeline
Use the LLM task:

/07_ops/llm-tasks/task-library/transcript-ingest.md

This should:
- extract stakeholder signals
- identify decision candidates
- suggest updates to themes/risks/opportunities
- produce a structured summary

#### Step 3: human review (10–20 minutes)
- Approve or edit:
  - stakeholder signal updates
  - decision candidates
- Decide:
  - does any decision need an ADR now?

Nothing gets auto-committed without a human pass.

---

## Updating stakeholder understanding

### When to update stakeholders
- After interviews
- After steerco or sponsor meetings
- When behaviour or priorities visibly shift

### How to update safely
- Do **not** rewrite the whole stakeholder file
- Add entries under:
  - `Recent signals (last 30 days)`
  - `Timeline` (if it represents a shift)

Always include:
- signal type
- confidence
- evidence reference

Stakeholder files should feel *alive*, not overwritten.

---

## Keeping the project in order (weekly hygiene)

Once a week, do a 30-minute tidy:

### 1. README refresh
Update:
- current phase
- this week’s focus
- links to new decisions or themes

### 2. Theme hygiene
Open:

/03_discovery/synthesis/themes.md

Ask:
- Are any themes duplicated?
- Has confidence changed?
- Do old themes need archiving?

### 3. Decision check
Open:

/04_product/decisions/

Ask:
- Are there decisions we’re relying on but haven’t logged?
- Are any ADRs still “proposed” that should be accepted or rejected?

### 4. Stakeholder staleness
Quick scan:
- Any key stakeholder not updated in 3–4 weeks?
- Add a note even if nothing has changed (“no material shift”).

This keeps trust high.

---
## ‼️ Using importance, confidence, and context (how we manage focus)

As the project grows, not everything can stay equally important.
This system uses **lightweight ratings** to help humans and AI focus on what actually matters.

These ratings are not about status or correctness.
They are about **attention, trust, and recency**.

### The three questions every important document should answer

For documents that inform decisions (themes, risks, stakeholders, decisions, key context), we try to make three things explicit:

1. How important is this right now?
2. How confident are we that this is true?
3. Has a human looked at this recently?

We capture this using a small metadata block at the top of the file.

### The standard metadata block

```yaml
---
type: theme
status: active
importance: high
confidence: medium
scope: project
last_reviewed: 2026-01-18
owners:
  - design-lead
sources:
  - 2026-01-12_interview-jane-doe
```

---

## Using FigJam without losing knowledge

FigJam is a **work surface**, not memory.

### When using FigJam
- Exploration
- Clustering
- Voting
- Early synthesis

### After using FigJam
Do *one* of the following:
- Export clusters/insights and:
  - update `themes.md`
  - propose ADRs
- Or add a short summary note linking:
  - board → outcomes → next decisions

If insight only exists in a board, it will be forgotten.

---

## Generating reports, decks, and updates

### Weekly updates
Use:

/06_delivery/updates/_weekly-update-template.md

Populate it by:
- referencing ADRs
- referencing themes
- referencing recent research

LLMs are good here:
- assembling
- summarising
- formatting

Humans:
- decide emphasis
- check tone
- remove fluff

### Client decks
Decks are **renders**, not truth.

Before creating a deck:
- check if the content already exists in the repo
- generate an outline from:
  - themes
  - decisions
  - risks
- link slides back to source files

After the deck:
- store exported PDF
- add links in the repo
- do not create new thinking only in slides

---

## Using AI safely and well

### What AI is good at here
- extraction
- summarisation
- comparison
- drafting updates
- proposing structure

### What AI should not do alone
- final decisions
- stakeholder judgement
- rewriting core narratives
- inventing evidence

Always ask:
> “What source is this based on?”

If the answer isn’t clear, it doesn’t go in.

---

## When you’re unsure where something belongs

Ask:
1. Is this **context**? → `/01_context`
2. Is it about **people**? → `/02_people`
3. Is it **raw input**? → `/03_discovery/research`
4. Is it **interpreted**? → `/03_discovery/synthesis`
5. Is it a **decision**? → `/04_product/decisions`
6. Is it **design rationale**? → `/05_design`
7. Is it an **output**? → `/06_delivery`

If it still doesn’t fit, add a note and flag it in the README.

---

## What good looks like

You’re using this system well when:
- new joiners get oriented in under a day
- client questions are answered with links, not memory
- updates are boringly fast to produce
- disagreements reference evidence, not recollection
- AI outputs sound specific, not generic
- no one asks “why did we decide this?”

---

## Final rule

> This system exists to protect thinking time.

If it ever feels like it’s slowing thinking down,
stop and simplify.

Structure should create space for creativity,
not compete with it.