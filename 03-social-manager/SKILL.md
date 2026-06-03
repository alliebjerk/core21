<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Social Manager — Playbook

## Trigger
Hourly, 9am–6pm CT weekdays. Weekly engagement report every Friday at 5pm CT.

## Steps — Queuing Cycle (hourly)
1. Check `../02-copywriter/output/` for new files dated today or yesterday
2. Skip any file with "[DRAFT — NEEDS REVIEW]" in the body
3. For each approved draft:
   - Identify platform (Instagram, Facebook)
   - Queue in Buffer with correct posting time
   - Log in `output/[YYYY-MM-DD]-queue-log.md`
4. Check posts published in the last 24 hours — note engagement data

## Steps — Weekly Report (Friday 5pm)
1. Read `memory.md`
2. Pull 7-day engagement data from Buffer / Meta Business
3. Identify top 3 posts by reach, saves, and comments; identify notable underperformers
4. Identify patterns: which pillar, format, or hook type appeared in the top performers
5. Write report — save as `output/[YYYY-MM-DD]-weekly-report.md`
6. Update `memory.md` with new patterns

## Input
- `../02-copywriter/output/` (approved drafts)
- Buffer (queue and engagement data)
- Meta Business Suite (additional analytics)

## Output
- `output/[YYYY-MM-DD]-queue-log.md` (daily)
- `output/[YYYY-MM-DD]-weekly-report.md` (Fridays)

## Error Handling
- If Buffer is unavailable, log the failed queue and retry next cycle
- If engagement data is unavailable for the weekly report, note the gap and report with available data
- If a queued post has a broken link, flag immediately in Slack #marketing

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
