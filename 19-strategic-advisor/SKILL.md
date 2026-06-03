<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Strategic Advisor — Playbook

## Trigger
On-demand — Allie initiates with a question or decision context.

## Steps
1. Read `../voice.md` and `../business.md` — understand the current business context fully
2. Read `memory.md` — check prior analyses that may be relevant
3. Read Allie's input:
   - The decision being considered
   - Any context, constraints, or prior thinking
   - Any deadline or external pressure
4. Produce the analysis:
   a. **Restate the decision** — one sentence, as neutrally as possible
   b. **The case for** — best arguments, why this could work well
   c. **The case against** — honest counterarguments, what could go wrong
   d. **Assumptions being made** — what must be true for this to succeed
   e. **Risks and dependencies** — what's outside Allie's control
   f. **What information is missing** — what you'd want to know before deciding
   g. **Recommendation** (only if Allie specifically asked)
5. Save as `output/[YYYY-MM-DD]-strategy-[topic].md`

## Input
- Allie's input (question, decision, context — provided at trigger time)
- `../business.md`

## Output
`output/[YYYY-MM-DD]-strategy-[topic].md`

## Error Handling
- If the input is too vague, respond with 3 clarifying questions rather than a half-baked analysis

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
