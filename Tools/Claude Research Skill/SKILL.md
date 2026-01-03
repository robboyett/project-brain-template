---
name: project-brain-research
description: "Deep desk research skill for populating project brain context. Use when team members ask to: (1) Research a client's industry, business, or competitive landscape, (2) Build background context for a new project, (3) Populate the 01_context folder with structured knowledge, (4) Generate synthesis of business constraints, market dynamics, or regulatory environment, (5) Create stakeholder landscape analysis. Triggers on phrases like 'research this client', 'build context for', 'what do we know about [company]', 'industry analysis', 'competitive landscape'."
---

# Project brain research

Deep desk research for building project intelligence. Generates structured knowledge that maps directly to the project brain's `01_context` folder.

## Overview

This skill transforms web research into structured project brain entries. Team members can request research on clients, industries, or business contexts, and receive markdown files ready for review and integration.

## Quick start

When asked to research a client or build project context:

1. Clarify scope if needed (company name, industry focus, specific questions)
2. Conduct systematic web research using the research framework below
3. Generate markdown files following the output templates
4. Place outputs in `_pending/` for team review

## Research framework

### Entry points by request type

**"Research [company]"** → Full company research package
- Start with `company-profile.md`
- Add `industry-landscape.md` if industry context unclear
- Add `competitive-position.md` for strategic context

**"Build context for [project]"** → Project-focused research
- Start with `business-context.md` (project-specific framing)
- Add relevant modules based on project type

**"Industry analysis for [sector]"** → Industry deep-dive
- Start with `industry-landscape.md`
- Add `market-dynamics.md` for trends and forces

**"Who are the stakeholders?"** → Stakeholder mapping
- Generate `stakeholder-landscape.md`
- Focus on decision-makers and influencers

### Research sequence

For comprehensive client research, follow this sequence:

```
1. Company basics → 2. Industry context → 3. Competitive position → 4. Constraints & regulations → 5. Synthesis
```

Each step informs the next. Don't skip to synthesis without foundational research.

## Research modules

### 1. Company profile (`company-profile.md`)

**Research targets:**
- Official company website (About, Leadership, Press)
- Recent news (last 12 months)
- LinkedIn company page
- Crunchbase/PitchBook if startup/scale-up
- Annual reports if public company
- Glassdoor for culture signals

**Key questions:**
- What does the company actually do? (beyond marketing speak)
- How do they make money?
- How big are they? (employees, revenue, funding)
- Who leads them? What's their background?
- What's their stated strategy/mission?
- What have they announced recently?

### 2. Industry landscape (`industry-landscape.md`)

**Research targets:**
- Industry reports (search "[industry] market report 2024/2025")
- Trade publications and associations
- Analyst commentary
- Recent industry news

**Key questions:**
- What industry/industries do they operate in?
- How is this industry typically structured?
- Who are the major players?
- What are the industry-specific terms and concepts?
- What's the typical business model?

### 3. Competitive position (`competitive-position.md`)

**Research targets:**
- Competitor websites
- Comparison articles ("[company] vs competitors")
- Industry rankings
- Customer reviews (G2, Capterra, Trustpilot depending on sector)

**Key questions:**
- Who are the direct competitors?
- What's the basis of competition? (price, features, service, brand)
- Where does this company sit in the market?
- What's their apparent differentiation?
- Any recent competitive moves?

### 4. Business constraints (`constraints-and-regulations.md`)

**Research targets:**
- Regulatory body websites
- Industry compliance requirements
- Recent regulatory news
- Professional body guidelines

**Key questions:**
- What regulations govern this business?
- What compliance requirements exist?
- Are there industry-specific constraints?
- What are the typical operational constraints?
- Any recent regulatory changes?

### 5. Market dynamics (`market-dynamics.md`)

**Research targets:**
- Trend reports
- Technology analyst coverage
- Economic indicators for sector
- Investment activity

**Key questions:**
- What forces are shaping this market?
- What's growing/declining?
- What technology shifts are relevant?
- What do customers increasingly expect?
- What are the emerging business models?

## Output templates

All outputs go to `_pending/` for review before integration into `01_context/`.

### File structure

```yaml
---
type: research
status: pending
confidence: [high|medium|low]
sources: [number of sources consulted]
date: [YYYY-MM-DD]
researcher: Claude
---
```

### Template: company-profile.md

```markdown
---
type: research
status: pending
confidence: medium
sources: X
date: YYYY-MM-DD
researcher: Claude
---

# [Company name]

## What they do

[2-3 sentences. Plain language. What problem do they solve, for whom?]

## Business model

[How they make money. Revenue streams. Pricing approach if known.]

## Scale and stage

- **Employees**: [number or range]
- **Revenue**: [if known/estimable]
- **Funding**: [if relevant]
- **Founded**: [year]
- **Headquarters**: [location]

## Leadership

| Name | Role | Background |
|------|------|------------|
| [Name] | [Title] | [Brief relevant background] |

## Recent developments

- [Date]: [Development]
- [Date]: [Development]

## Strategic direction

[What they've publicly stated about where they're headed]

## Sources

- [Source 1]
- [Source 2]
```

### Template: industry-landscape.md

```markdown
---
type: research
status: pending
confidence: medium
sources: X
date: YYYY-MM-DD
researcher: Claude
---

# [Industry name] landscape

## Industry definition

[What this industry encompasses. Boundaries and adjacent sectors.]

## Market structure

[How the industry is organised. Typical value chain. Key segments.]

## Major players

| Company | Position | Notes |
|---------|----------|-------|
| [Name] | [Role in market] | [Distinguishing characteristic] |

## Industry dynamics

[Key forces shaping the industry. Consolidation, disruption, regulation, etc.]

## Key terminology

| Term | Meaning |
|------|---------|
| [Term] | [Plain language explanation] |

## Sources

- [Source 1]
- [Source 2]
```

### Template: business-context.md

```markdown
---
type: research
status: pending
confidence: medium
sources: X
date: YYYY-MM-DD
researcher: Claude
project: [Project name]
---

# Business context: [Project name]

## The organisation

[Brief company context relevant to this project]

## The problem space

[What business problem or opportunity is this project addressing?]

## Constraints we should know about

### Regulatory
[Relevant regulations, compliance requirements]

### Technical
[Known technical constraints, legacy systems, integration requirements]

### Organisational
[Team structure, decision-making, politics if known]

### Commercial
[Budget signals, business case drivers, success metrics]

## What success looks like

[How the organisation likely measures success for work like this]

## Open questions

- [Question we should explore]
- [Question we should explore]

## Sources

- [Source 1]
- [Source 2]
```

## Research quality guidelines

### Confidence levels

**High confidence**: Multiple authoritative sources agree. Official company statements. Verifiable facts.

**Medium confidence**: Single authoritative source. Reasonable inference from available data. Industry standard assumptions.

**Low confidence**: Limited sources. Significant inference required. Contested or unclear information.

### Source quality hierarchy

1. Official company sources (website, press releases, SEC filings)
2. Major business publications (FT, WSJ, Bloomberg, Reuters)
3. Industry-specific trade publications
4. Analyst reports and research firms
5. General news coverage
6. User-generated content (reviews, forums)

### What to flag

Mark with `[VERIFY]` when:
- Information is from a single source
- Data is more than 18 months old
- Numbers are estimates or ranges
- Inference is required

Mark with `[ASK CLIENT]` when:
- Public information contradicts itself
- Critical information is unavailable
- Assumptions need validation

## Integration workflow

1. **Generate** research outputs to `_pending/`
2. **Review** via standard project brain review process
3. **Approve/edit** in `_pending/REVIEW.md`
4. **Move** approved content to `01_context/`
5. **Update** `00_index/` if adding new knowledge areas

## Example prompts

Team members can trigger this skill with:

- "Research Acme Corp for the new project"
- "Build industry context for healthcare tech"
- "What do we know about the competitive landscape in fintech lending?"
- "Create a business context file for Project Phoenix"
- "Who are the key players in [industry]?"
- "What regulations affect [sector]?"

## Handling gaps

When research reveals gaps:

1. Document what's unknown in the output file
2. Add to "Open questions" section
3. Suggest specific questions for client conversations
4. Flag high-priority gaps for team attention

Research is never complete. The goal is useful context, not exhaustive coverage.
