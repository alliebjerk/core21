<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Project Manager — Playbook

## Trigger
Daily at 7am CT.

## Steps
1. Read `../business.md` — check current priorities to weight which projects matter most
2. Read `memory.md`
3. Open Notion — query all tasks:
   - Due today or overdue
   - Due in the next 3 days
   - No assignee
   - No due date
   - No activity in 7+ days (stalled)
4. Organize into the daily report:
   - 🔴 Overdue (task name, project, days overdue)
   - 🟡 Due in 3 days (task name, project, due date)
   - ⚪ Stalled (project name, last activity date)
   - ⚠️ Needs attention (no assignee or no date)
5. Post Slack message to #ops with only 🔴 items
6. Save full report as `output/[YYYY-MM-DD]-project-status.md`
7. Update `memory.md` with recurring patterns (same tasks going overdue, same projects stalling)

## Input
- Notion (all projects and tasks)
- `../business.md` (current priorities)

## Output
- `output/[YYYY-MM-DD]-project-status.md`
- Slack #ops message (overdue items only)

## Error Handling
- If Notion API is unavailable, log the gap and skip the report
- If a project's structure has changed significantly, flag before reporting

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
