<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# SOP Writer — Playbook

## Trigger
On-demand — triggered by a Notion task tagged `needs-sop` or a manual request from ops.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md`
3. Locate the raw input:
   - Notion task body (simple processes)
   - Google Drive document (longer notes or transcripts)
4. Read the raw input fully before writing anything
5. Draft the SOP:
   a. Title (action-based: "How to Onboard a New Self-Made Member")
   b. Purpose (1-2 sentences)
   c. Trigger (what starts this process)
   d. Owner (person or role)
   e. Steps (numbered, sequential, one action each)
   f. Decision points (if/then branches, clearly labeled)
   g. What "done" looks like
   h. Related documents or templates (link to Notion pages if applicable)
6. Flag unclear or missing information with [FLAG: ...]
7. Save draft to `output/[YYYY-MM-DD]-sop-[name].md`
8. Ops team moves approved SOPs to the Notion SOP library

## Input
- Notion (triggering task, raw notes)
- Google Drive (transcripts, longer notes)

## Output
`output/[YYYY-MM-DD]-sop-[process-name].md`

## Error Handling
- If the raw input is too vague, produce an outline with [FLAG: need detail] markers rather than guessing
- If the process involves a tool not in business.md, flag for ops to confirm

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
