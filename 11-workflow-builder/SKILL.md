<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Workflow Builder — Playbook

## Trigger
On-demand — triggered by a Notion task tagged `needs-workflow` or a manual request from ops or Allie.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md`
3. Read the workflow request:
   - What problem is being solved?
   - What triggers the workflow?
   - What's the desired outcome?
   - Which tools are in scope?
4. Map the current manual process if one exists
5. Draft the workflow blueprint:
   a. Name and purpose
   b. Trigger (form submission, Stripe event, date, manual)
   c. Tool responsible at each step
   d. Data passed between steps
   e. Human review points (mark clearly — at minimum one per workflow)
   f. Failure state (what happens if a step fails)
   g. Estimated setup time (rough)
6. Flag any step requiring a tool integration that may not exist
7. Save blueprint as `output/[YYYY-MM-DD]-workflow-[name].md`

## Input
- Notion (workflow request task)
- `../business.md` (tools list)

## Output
`output/[YYYY-MM-DD]-workflow-[name].md`
Format: narrative description + step-by-step table: Step | Tool | Action | Human Review?

## Error Handling
- If the request is too vague, produce a discovery questions document instead
- Note uncertain integrations as [INTEGRATION NEEDED: confirm before building]

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
