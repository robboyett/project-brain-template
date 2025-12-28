# Project brain setup for Cursor

## What this is
This file is the single source of truth for scaffolding a new “project brain” repository: folder structure, file conventions, starter templates, and an LLM task library.

The goal is simple:
- markdown is the canonical memory
- FigJam, decks, transcripts, etc are work surfaces
- knowledge compounds across the project lifecycle
- documentation around the edges becomes fast and derived
- stakeholder understanding becomes portable across projects

## How to use this in Cursor
1. Create an empty folder for your project.
2. Save this file at the root as: `PROJECT_BRAIN_SETUP.md`
3. In Cursor, ask the LLM:

> Read `PROJECT_BRAIN_SETUP.md`. Create the folder structure and all template files exactly as specified. Use the file contents provided. Do not invent additional folders or files unless explicitly listed under “Optional extras”. After creating everything, output a checklist of created paths.

---

## Global conventions

### Naming
- lowercase for most filenames
- hyphen-separated words
- no spaces
- date-prefixed for time-based artefacts: `YYYY-MM-DD_<slug>.md`
- ADRs use `ADR-0001-<slug>.md`

Examples:
- `2026-01-03_interview-jane-doe.md`
- `ADR-0003-narrow-initial-scope.md`

### Markdown style
- use sentence case for headings
- keep sections short and scannable
- prefer bullets over long paragraphs for operational docs
- link to sources rather than duplicating content (eg link to Figma/FigJam rather than embedding)

### Front matter
Use YAML front matter for:
- stakeholders
- research notes
- decisions (ADRs)
- weekly updates
- LLM tasks and runs

### Evidence rule
When writing interpretive statements, include evidence references (quotes, transcript timestamps, or artefact links). Separate:
- signal (what was said/observed)
- inference (what we think it means)

### Canonical vs work surfaces
- Canonical: this repo (markdown + structured sidecars)
- Work surfaces: FigJam, slides, spreadsheets, whiteboards, transcripts/audio
- Work surfaces are inputs and views; final knowledge lands back in the repo.

---

## Create this folder structure

Create the following directories:

- project-brain/
    - 00_index/
    - 01_context/
    - 02_people/
        - stakeholders/
        - team/
    - 03_discovery/
        - research/
        - synthesis/
    - 04_product/
        - decisions/
    - 05_design/
    - 06_delivery/
        - updates/
        - handover/
    - 07_ops/
        - llm-tasks/
        - task-library/
        - runs/
        - schemas/
        - prompts/
    - _archive/

---

## Create these files with the exact contents below

### Root README

Path: `README.md`

```md
# Project brain

## What this project is
Add a one-paragraph summary of the client, the problem space, and the ambition.

## How to use this repo
- This is the canonical memory for the project (context, people, research, decisions, rationale).
- FigJam, decks, and other tools are work surfaces. Outputs should be brought back here.
- If something important is only in a board, a deck, or someone’s head, it isn’t durable.

## Current state
- Phase:
- Last updated:
- This week’s focus:
- Links:
  - [Problem framing](./04_product/problem-framing.md)
  - [Key stakeholders](./02_people/stakeholders/)
  - [Themes](./03_discovery/synthesis/themes.md)
  - [Decision log](./04_product/decisions/)

## Open questions
- …

## Quick links
- [Glossary](./00_index/glossary.md)
- [Search map](./00_index/search-map.md)
- [Ways of working](./02_people/team/ways-of-working.md)
- [LLM task library](./07_ops/llm-tasks/task-library/)

```
⸻

00_index

Path: `00_index/README.md`
```md
# Index

## Start here
- [Project overview](../README.md)
- [Problem framing](../04_product/problem-framing.md)
- [Themes](../03_discovery/synthesis/themes.md)
- [Decision log](../04_product/decisions/)

## How this repo is organised
- `01_context`: industry, organisation background, constraints, success measures
- `02_people`: stakeholders and team working notes
- `03_discovery`: research inputs and synthesis
- `04_product`: framing, principles, decision records (ADRs)
- `05_design`: rationale, inventory, accessibility notes (links to Figma)
- `06_delivery`: weekly updates and handover outputs
- `07_ops`: templates, prompts, LLM tasks, automations
```

Path: `00_index/glossary.md`

```md
# Glossary

Add product terms, acronyms, and domain definitions here.

## Terms
- Term:
  - Definition:
  - Notes:
  - Synonyms:
```

Path: `00_index/search-map.md`

```md
# Search map

This is a curated list of the most useful entry points for humans and LLMs.

## If you need to understand the client fast
- [Organisation overview](../01_context/org-overview.md)
- [Industry brief](../01_context/industry-brief.md)

## If you need to understand the people
- [Stakeholders](../02_people/stakeholders/)

## If you need to understand what we believe
- [Themes](../03_discovery/synthesis/themes.md)
- [Risks](../03_discovery/synthesis/risks.md)
- [Opportunities](../03_discovery/synthesis/opportunities.md)

## If you need the “why”
- [Problem framing](../04_product/problem-framing.md)
- [Principles](../04_product/principles.md)
- [Decision records](../04_product/decisions/)

## If you need delivery outputs
- [Weekly updates](../06_delivery/updates/)
- [Handover](../06_delivery/handover/)

```
⸻

01_context
Path: `01_context/org-overview.md`

```md
# Organisation overview

## Snapshot
- Organisation:
- Sector:
- Product(s):
- Business model:
- Primary customers:
- Primary channels:

## History and context
A short narrative of how the business got here.

## What they care about right now
- …

## Known constraints
- …

## Sources
- Link to sales notes:
- Link to client docs:
```

Path: `01_context/industry-brief.md`

```md
# Industry brief

## What industry are we in?
Describe the industry in plain terms.

## Market dynamics
- Growth/decline signals:
- Typical competitors:
- Typical customer expectations:
- Technology shifts:
- Regulatory pressures (if any):

## Where this client sits
- Category position:
- Differentiators:
- Known threats:

## What we should be curious about
- …

Path: 01_context/constraints.md

# Constraints

## Technical
- …

## Legal and regulatory
- …

## Organisational
- …

## Delivery
- Timelines:
- Dependencies:
- Non-negotiables:

## Sources
- …
```

Path: `01_context/success-metrics.md`

```md
# Success metrics

## Stated outcomes
What the client says success looks like.

## Measurable signals
- Metric:
- Baseline:
- Target:
- Owner:
- Data source:

## Risks to success
- …
```

Path: `01_context/assumptions.md`

```md
# Assumptions

Assumptions are allowed early. They must be made explicit and then tested.

## Current assumptions
- Assumption:
  - Why we think this:
  - Confidence (low/medium/high):
  - How we will test it:
  - By when:
```

⸻

02_people

Path: `02_people/team/ways-of-working.md`

```md
# Ways of working

## Tools
- Canonical memory: this repo (markdown)
- Work surfaces: FigJam, decks, spreadsheets, whiteboards, transcripts/audio
- AI workflow: Cursor, using `/07_ops/llm-tasks`

## Cadence
- Weekly: publish update in `/06_delivery/updates/`
- After each key meeting: log decisions and stakeholder signals
- Fortnightly: refresh themes/risks/opportunities

## House rules
- If it matters, it lands in the repo.
- FigJam is for exploration; outcomes come back as themes/decisions.
- Stakeholder profiles get updated as “signals” with evidence references.
```

Path: `02_people/team/delivery-team.md`

```
# Delivery team

## Roles
- Delivery lead:
- Strategy:
- Design lead:
- Designers:
- Research:
- Engineering partner(s):

## RACI notes
Add any role clarity here as needed.
```

Path: `02_people/stakeholders/_stakeholder-template.md`

```md
---
type: stakeholder
stakeholder_id: jane-doe
name: Jane Doe
role: VP Product
organisation: ClientCo
status: active
importance: high
confidence: medium
scope: client
first_seen: 2026-01-01
last_reviewed: 2026-01-15
owners:
  - delivery-lead
sources:
  - 2026-01-03_interview-jane-doe
---

## Overview
Who they are and why they matter.

## Motivations
What success looks like for them.

## Concerns
What they are wary of, politically or practically.

## Decision-making style
Fast/slow, consensus-led, data-led, intuition-led, risk appetite.

## Language and framing
What resonates and what doesn’t.

## Current view (curated)
A short paragraph that reflects the team’s best current understanding.

## Recent signals (last 30 days)
- YYYY-MM-DD (signal_type, confidence): signal text. Evidence: [source](../..)

## Timeline
- YYYY-MM-DD: notable behaviour or shift, with evidence link.
```

⸻

03_discovery

Path: `03_discovery/research/_research-note-template.md`

```md
---
type: research
status: active
importance: medium
confidence: low
scope: project
method: interview
date: 2026-01-01
participants:
  - jane-doe
related_stakeholders:
  - jane-doe
last_reviewed: 2026-01-01
owners:
  - researcher
artefacts:
  - kind: transcript
    link:
sources:
  - raw transcript
---

# Research note

## Purpose
Why this session happened.

## Context
What we were trying to learn.

## Key signals
- …

## Notable quotes
> “…”

## Interpretation (initial)
What this might mean. Label uncertainty.

## Feeds into
- [Themes](../synthesis/themes.md)
- [Risks](../synthesis/risks.md)
- [Opportunities](../synthesis/opportunities.md)
- [Decision candidates](../../07_ops/llm-tasks/runs/)
```

Path: `03_discovery/synthesis/themes.md`

```md

# Themes
Themes are named patterns supported by evidence. Keep them tight and reusable.

---
type: theme
status: active
importance: high
confidence: medium
scope: project
last_reviewed: 2026-01-15
owners:
  - strategist
sources:
  - 2026-01-03_interview-jane-doe
---

## Theme: <name>

### Description
What this theme is.

### Evidence
- Link to research note(s):
- Link to transcript sections:
- Link to artefacts:

### Implications
- What this changes in our approach:
- What to prioritise:
- What to avoid:

### Confidence
Low / medium / high
```
---

Path: `03_discovery/synthesis/risks.md`

```md
# Risks

---
type: risk
status: active
importance: high
confidence: medium
scope: project
last_reviewed: 2026-01-15
owners:
  - delivery-lead
sources:
  - 2026-01-10_workshop-notes
---

## Risk: <name>

### Description
What could go wrong.

### Evidence
- …

### Mitigation
- …

### Owner
- …

### Confidence
Low / medium / high
```
---

Path: `03_discovery/synthesis/opportunities.md`

```
# Opportunities

---
type: opportunity
status: active
importance: medium
confidence: low
scope: project
last_reviewed: 2026-01-15
owners:
  - design-lead
sources:
  - 2026-01-12_interview-jane-doe
---

## Opportunity: <name>

### Description
The potential value and why it matters.

### Evidence
- …

### How we might explore
- …

### Confidence
Low / medium / high
```
---

04_product

Path: `04_product/problem-framing.md`

```md
# Problem framing

## The problem as stated
What the client says the problem is.

## The problem as observed
What we believe is actually happening (with evidence).

## Who is affected
- Primary users:
- Secondary users:
- Internal stakeholders:

## Why now
What has changed or created urgency.

## What good looks like
Outcome-focused description of success.

## Open questions
- …
```

Path: `04_product/principles.md`

```md
# Principles

Principles guide decisions when requirements are incomplete.

## Principle: <name>
- Meaning:
- Example behaviours:
- Anti-patterns:
```

Path: `04_product/decisions/ADR-0001-template.md`

```md
---
type: decision
status: proposed
importance: high
confidence: high
scope: project
date: 2026-01-01
last_reviewed: 2026-01-01
owners:
  - design-lead
related_themes:
  - <theme-name>
sources:
  - 2026-01-12_interview-jane-doe
---

# ADR-0001: <decision title>

## Context
What led to this decision.

## Decision
What we chose and why.

## Alternatives considered
- Option:
  - Why not:

## Consequences
- What this enables:
- What this limits:
- Follow-on work:

## Evidence
- Links to research notes/transcripts/artefacts:

## Review trigger
What would make us revisit this.
```

⸻

05_design

Path: `05_design/rationale.md`

```md
# Design rationale

## Where the design lives
- Figma file:
- Relevant pages/frames:
- FigJam boards:

## Rationale snapshots
Add short rationale notes that link to ADRs and themes.

### Snapshot: <area>
- What we’re trying to achieve:
- Key trade-offs:
- Linked decisions:
- Evidence:
```

Path: `05_design/ui-inventory.md`

```md
# UI inventory

A lightweight index of key UI areas and their purpose.

## Areas
- Area:
  - Purpose:
  - Link to Figma:
  - Related themes/decisions:

Path: 05_design/accessibility.md

# Accessibility

## Standards and expectations
- …

## Known risks
- …

## Checks and outcomes
- …
```

⸻

06_delivery

Path: `06_delivery/updates/_weekly-update-template.md`

```md
---
type: update
status: active
importance: medium
confidence: high
scope: project
week_of: 2026-01-01
last_reviewed: 2026-01-01
owners:
  - delivery-lead
sources:
  - ADRs
  - themes
  - research notes
---

# Weekly update

## What changed
- …

## Decisions made
- Link ADR(s):

## What we learnt
- …

## Next focus
- …

## Open questions
- …

## Links
- …
```

Path: `06_delivery/handover/summary.md`

```md
# Handover summary

## What we delivered
- …

## Key decisions and rationale
- …

## What we learnt
- …

## What remains open
- …

## Recommended next steps
- …

## Links
- …
```

⸻

07_ops and LLM task layer

Path: `07_ops/templates.md`

```md
# Templates

Templates live in-place as `_...-template.md` files.
Use them by copying and renaming, then deleting the leading underscore.
```

Path: `07_ops/automations.md`

```md
# Automations

Track any scripts or repeatable workflows here.

## Candidates
- Build index/search-map automatically
- Flag stale stakeholder files (eg not updated in 30 days)
- Generate weekly update draft from ADRs + themes + research notes
```

Path: `07_ops/prompts.md`

```md
# Prompts

This file holds short reusable prompt fragments for Cursor.

## Evidence rule
When writing outputs, do not invent facts. Separate signals from inferences. Include evidence links or transcript references.

## House style
- sentence case headings
- short paragraphs
- bullets for operational content
- avoid marketing language unless explicitly producing client-facing copy
```

LLM tasks

Path: `07_ops/llm-tasks/README.md`

```md
# LLM tasks

LLM tasks turn raw inputs into durable knowledge updates.

## Principles
- LLMs propose changes; humans approve and commit.
- Every run produces a run log in `/07_ops/llm-tasks/runs/`.
- Outputs should be structured where possible (JSON sidecars) and linked to evidence.

## Standard pipelines

### Transcript pipeline
When a transcript is added:
1. Extract stakeholder signals
2. Detect decision candidates
3. Suggest theme/risk/opportunity updates
4. Create a structured summary
5. Propose patches to stakeholder files and ADR drafts

### Workshop/FigJam pipeline
When a FigJam synthesis session completes:
1. Export clusters/stickies to JSON/MD
2. Update themes and opportunities
3. Draft decisions or principles if needed
```

Path: `07_ops/llm-tasks/task-library/_task-template.md`

```
---
type: llm_task
task_id: <task_id>
version: 1.0
inputs: []
outputs: []
quality_bar: []
---

# Task: <name>

## Purpose
What this task is for.

## When to run
Trigger moment.

## Inputs
- Required files/links:

## Outputs
- Files to create or update:

## Steps
1. …
2. …

## Output rules
- Evidence linking required
- Separate signal vs inference
- No duplication
- Use repo naming conventions

## Human review checklist
- …
```

Path: `07_ops/llm-tasks/task-library/transcript-ingest.md`

```md
---
type: llm_task
task_id: transcript_ingest_v1
version: 1.0
inputs:
  - transcript_markdown_path
  - optional_related_stakeholders
outputs:
  - research_summary_markdown
  - stakeholder_signals_json
  - decision_candidates_json
  - theme_patch_markdown
quality_bar:
  - evidence_linking_required
  - no_invented_facts
  - separate_signal_vs_inference
---

# Task: transcript ingest

## Purpose
Turn a raw transcript into structured project knowledge updates.

## When to run
After any interview, workshop, or steering meeting transcript is added to `/03_discovery/research/`.

## Inputs
- Transcript markdown file (with timestamps if available)
- Relevant stakeholder files (if known)
- Current synthesis files:
  - `/03_discovery/synthesis/themes.md`
  - `/03_discovery/synthesis/risks.md`
  - `/03_discovery/synthesis/opportunities.md`

## Outputs
Create a new run log folder (or files) in `/07_ops/llm-tasks/runs/` for this transcript, containing:
- `<date>_<slug>__summary.md`
- `<date>_<slug>__stakeholder-signals.json`
- `<date>_<slug>__decision-candidates.json`
- `<date>_<slug>__theme-patch.md`

Also propose patches (as markdown snippets) to:
- stakeholder files in `/02_people/stakeholders/`
- ADR drafts in `/04_product/decisions/` where warranted

## Steps
1. Extract stakeholder signals (facts and behavioural cues).
2. Extract decision candidates (anything that changes direction, scope, constraints, or priorities).
3. Map content to existing themes/risks/opportunities; propose additions where needed.
4. Produce a structured summary:
   - decisions discussed
   - new info learned
   - tensions and risks
   - open questions
   - stakeholder signals
5. Write everything into the run outputs with evidence references.

## Output rules
- Stakeholder signals must include:
  - stakeholder_id
  - signal_type (motivation, concern, constraint, preference, decision_style, language)
  - signal_text
  - confidence (low/medium/high)
  - evidence reference (timestamp/section + short quote if available)
- Decision candidates must include:
  - decision_statement
  - context
  - options implied
  - consequences
  - evidence reference
- Theme patch must list:
  - which theme to update
  - what to add (evidence + implication)
  - confidence

## Human review checklist
- Are signals grounded in evidence?
- Are inferences clearly labelled?
- Are suggested updates additive (not noisy duplication)?
- Do any decision candidates deserve an ADR now?
```

Path: `07_ops/llm-tasks/task-library/stakeholder-update.md`

```md
---
type: llm_task
task_id: stakeholder_update_v1
version: 1.0
inputs:
  - stakeholder_signals_json
  - stakeholder_file_path
outputs:
  - stakeholder_file_patch
quality_bar:
  - additive_updates_only
  - evidence_required
---

# Task: stakeholder update

## Purpose
Update stakeholder profiles from extracted signals without rewriting the entire file.

## When to run
After transcript ingest or any session that yields new stakeholder signals.

## Inputs
- Stakeholder signals JSON
- Target stakeholder file

## Outputs
- A patch snippet that adds items under:
  - `Recent signals (last 30 days)`
  - `Timeline` if the signal indicates a shift

## Rules
- Do not rewrite the whole stakeholder doc.
- Prefer short, high-signal bullets.
- Include evidence links or transcript references.
- Mark confidence.
```

Path: `07_ops/llm-tasks/schemas/stakeholder-signal.json`

```md
{
  "type": "array",
  "items": {
    "type": "object",
    "required": ["stakeholder_id", "signal_type", "signal_text", "confidence", "evidence"],
    "properties": {
      "stakeholder_id": { "type": "string" },
      "signal_type": {
        "type": "string",
        "enum": ["motivation", "concern", "constraint", "preference", "decision_style", "language"]
      },
      "signal_text": { "type": "string" },
      "confidence": { "type": "string", "enum": ["low", "medium", "high"] },
      "evidence": {
        "type": "object",
        "required": ["source_file", "reference"],
        "properties": {
          "source_file": { "type": "string" },
          "reference": { "type": "string" },
          "quote": { "type": "string" }
        }
      }
    }
  }
}
```

Path: `07_ops/llm-tasks/schemas/decision-candidate.json`

```
{
  "type": "array",
  "items": {
    "type": "object",
    "required": ["decision_statement", "context", "consequences", "evidence"],
    "properties": {
      "decision_statement": { "type": "string" },
      "context": { "type": "string" },
      "options_implied": { "type": "array", "items": { "type": "string" } },
      "consequences": { "type": "string" },
      "evidence": {
        "type": "object",
        "required": ["source_file", "reference"],
        "properties": {
          "source_file": { "type": "string" },
          "reference": { "type": "string" },
          "quote": { "type": "string" }
        }
      }
    }
  }
}
```

⸻

Optional extras (only create if asked)

If the user explicitly asks later, create:
	•	a scripts/ folder with helper scripts (sync, save, share)
	•	a local docs site scaffold (MkDocs/Docusaurus) for read-only browsing
	•	a FigJam import/export schema for stickies and clusters

Do not create these by default.

⸻

Done criteria (output after scaffolding)

After creating the structure and files, output:
	1.	A tree of created paths
	2.	A short checklist:
	•	Repo opens cleanly in VS Code
	•	README links resolve
	•	Templates are present
	•	LLM task library exists
	•	Schemas exist
	•	No extra files were added