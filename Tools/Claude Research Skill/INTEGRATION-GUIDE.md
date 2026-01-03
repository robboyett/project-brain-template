# Project brain research skill

A Claude skill for deep desk research that populates your project brain's `01_context` folder.

## What it does

Team members can ask Claude to research clients, industries, or business contexts. Claude conducts systematic web research and generates structured markdown files ready for review and integration into the project brain.

## Installation options

### Option A: Claude.ai skill (recommended for Claude.ai users)

1. Upload `project-brain-research.skill` to Claude.ai via Settings → Skills
2. The skill will activate when you ask research-related questions

### Option B: Cursor rules (recommended for Cursor users)

1. Copy `cursor-rules-research.mdc` to your project's `.cursor/rules/` folder
2. Rename to `research.mdc`
3. The rules will activate when working in `01_context/` or `_pending/` folders

### Option C: Manual reference

Keep the SKILL.md and references folder accessible and reference them when doing research tasks.

## Usage

Ask Claude things like:

- "Research Acme Corp for the new project"
- "Build industry context for healthcare tech"
- "What's the competitive landscape in fintech lending?"
- "Create a business context file for Project Phoenix"
- "Who are the key players in renewable energy?"

Claude will:
1. Clarify scope if needed
2. Conduct systematic web research
3. Generate markdown files with proper frontmatter
4. Place outputs in `_pending/` for your review

## Output structure

Research generates files like:

```
_pending/
├── company-profile.md
├── industry-landscape.md
├── competitive-position.md
├── constraints-and-regulations.md
└── market-dynamics.md
```

Each file includes:
- YAML frontmatter with confidence level and source count
- Structured sections matching the template
- `[VERIFY]` flags for uncertain information
- `[ASK CLIENT]` flags for things needing validation
- Source list

## Review workflow

1. Research outputs land in `_pending/`
2. Review using your normal project brain process
3. Edit or approve in `_pending/REVIEW.md`
4. Move approved content to `01_context/`
5. Update `00_index/` if adding new knowledge areas

## Customisation

### Adding sector-specific strategies

Edit `references/sector-strategies.md` to add research approaches for sectors you frequently work with.

### Adding search patterns

Edit `references/search-patterns.md` to add queries that work well for your clients or domains.

### Modifying templates

Edit `references/additional-templates.md` to adjust output formats to your team's preferences.

## Files included

```
project-brain-research/
├── SKILL.md                           # Main skill definition
└── references/
    ├── sector-strategies.md           # Industry-specific research approaches
    ├── search-patterns.md             # Effective search queries
    └── additional-templates.md        # Extra output templates
```

## Tips

- **Start broad, then focus**: Initial research reveals what's worth digging into
- **Mark confidence honestly**: Low confidence is fine—it's a signal, not a failure
- **Document gaps**: Unknown things are valuable to record
- **Iterate after client conversations**: Research + client input = real understanding
