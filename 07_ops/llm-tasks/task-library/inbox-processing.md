# Task: Inbox processing

## Purpose
Turn raw inputs from `_inbox/` into structured project knowledge proposals.

## Trigger
User says `process inbox` (or similar).

## Inputs
- All files in `_inbox/` (excluding `_processed/`)
- Current stakeholder files in `02_people/stakeholders/`
- Current insights in `03_discovery/synthesis/insights.md`

## Process

1. **Read each inbox item**
2. **Classify**: transcript, meeting notes, observation, thought, link, other
3. **Extract**:
   - Stakeholder signals (with evidence)
   - Decision candidates (with context)
   - Insight updates (themes, risks, opportunities)
4. **Write proposals** to `_pending/REVIEW.md`
5. **Summarize** what was processed
6. **Move** processed files to `_inbox/_processed/` with date prefix

## Output rules
- Every signal needs: stakeholder_id, type, text, confidence, source
- Every decision needs: statement, context, consequences, source
- Every insight needs: description, evidence, confidence
- Separate observation from inference
- Don't duplicate existing content

## Human review
After processing, human reviews `_pending/REVIEW.md` and approves/rejects each proposal.

