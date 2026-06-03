<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Pipeline Tracker — Playbook

## Trigger
Daily at 7am CT.

## Steps
1. Read `../business.md` — confirm active offers and any pipeline stage changes
2. Read `memory.md`
3. Open GHL pipeline — pull a snapshot of all contacts and current stages
4. Flag:
   - "Proposal Sent" with no activity in 5+ days → tag `needs-followup`
   - `lead-hot` with no logged activity in 48 hours → urgent flag
   - "Discovery" stage for 14+ days → stale; recommend moving or closing
   - Any stage with an unusual cluster of leads (bottleneck signal)
5. Calculate pipeline summary:
   - Total leads by stage
   - Leads added in last 7 days
   - Leads won/closed-lost in last 7 days
6. Post a brief summary to Slack #sales (flags only — no clutter when nothing to flag)
7. Save full snapshot as `output/[YYYY-MM-DD]-pipeline-snapshot.md`
8. Update `memory.md` with pipeline patterns worth tracking

## Input
- GoHighLevel CRM (full pipeline)

## Output
- `output/[YYYY-MM-DD]-pipeline-snapshot.md`
- Slack #sales message (flags only)

## Error Handling
- If GHL is unavailable, log the outage and skip the day's report — do not post incomplete data to Slack
- If a pipeline stage has been renamed or restructured, flag the discrepancy before reporting

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
