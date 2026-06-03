<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Content Strategist — Playbook

## Trigger
Weekly, Sunday at 7pm CT.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md` — apply recent learnings about what content is performing
3. Open the Notion content calendar — check the upcoming 7-day window for launches, challenge dates, promotions, or team notes
4. Check the Social Manager's most recent weekly report in `../03-social-manager/output/` — identify top-performing content types from the prior week
5. Check Google Analytics (or the last available traffic report) for any content driving unusual traffic
6. Draft the 7-day content plan:
   - One primary post concept per day for Instagram
   - One email concept for the week (flag if an additional send is warranted)
   - Any Facebook group posts needed (community warmth, not promotion)
   - Assign each concept to a content pillar
   - Write a 2-3 sentence brief per concept: topic, angle, hook direction, CTA
7. Check for pillar balance and the 4:1 value-to-promo ratio
8. Save as `output/[YYYY-MM-DD]-content-calendar.md`
9. Update `memory.md` if a pattern is worth logging

## Input
- Notion content/launch calendar
- `../03-social-manager/output/` (most recent weekly report)
- `../business.md` (current priorities section)

## Output
`output/[YYYY-MM-DD]-content-calendar.md`
Format: one section per day — platform, pillar, brief, hook direction, CTA.

## Error Handling
- If Notion is unavailable, produce the calendar from business.md priorities and flag that it wasn't cross-referenced with the launch calendar
- If no Social Manager report exists, note it and proceed without engagement data
- If a launch is imminent (within 3 days) but not on the calendar, flag the gap rather than guessing

## Output Size Management
Keep the most recent 30 days of output active in `output/`.
Move older files to `output/archive/`.
Other agents only read the active `output/` folder.
