<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Copywriter — Playbook

## Trigger
Weekdays at 6am CT, or when a new brief appears in `../01-content-strategist/output/` from the prior day.

## Steps
1. Read `../voice.md` — internalize before writing anything
2. Read `../business.md` — check current priorities and offer ladder
3. Read `memory.md` — apply recent feedback
4. Find the most recent unprocessed brief in `../01-content-strategist/output/`
5. Read the full brief: format, pillar, angle, CTA
6. Write the draft:
   - **Instagram:** Hook on line 1 (no "I"), body 3-8 lines, single CTA
   - **Email:** Subject line + preview text + body + single CTA; lead with the point
   - **Facebook:** Warmer, more conversational, often question-based
7. Self-check against voice.md banned words list — replace any violations
8. Add [FLAG: ...] notes for anything unclear or that contradicts brand guidelines
9. Save as `output/[YYYY-MM-DD]-[format]-draft.md`
10. Update `memory.md` if feedback from a prior draft is worth logging

## Input
- `../01-content-strategist/output/` (content briefs)
- `../voice.md`
- `../business.md`

## Output
`output/[YYYY-MM-DD]-[format]-draft.md`
Each file: original brief (quoted), draft copy, and any FLAGS.

## Error Handling
- If no new brief exists, write a short status note to `output/[YYYY-MM-DD]-no-brief.md` and stop
- If a brief references an unconfirmed price, add [FLAG: price not confirmed — verify before sending]
- If a brief calls for a banned word: [FLAG: "unlock" is banned per voice.md — replaced with "get access to"]

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
