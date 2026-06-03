<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Budget and Forecast — Playbook

## Trigger
Monthly, 1st of the month at 7am CT.

## Steps
1. Read `../business.md` — check current priorities and any planned launches for the next 90 days
2. Read `memory.md`
3. Pull last month's actuals from QuickBooks:
   - Total revenue by category (product sales, membership MRR, challenge, other)
   - Total expenses by category (software, contractor, advertising, other)
   - Net
4. Compare actuals to the budget in Google Sheets — calculate variance per category
5. Draft the budget vs. actual report:
   - Summary table (category | budget | actual | variance %)
   - Flag categories with >20% variance
   - 3-bullet narrative: what came in over, what came in under, the biggest variance driver
6. Draft the 90-day forecast:
   - Project MRR from current membership count and average retention
   - Add confirmed launch revenue from business.md
   - Add seasonal patterns from memory.md
   - Express as a range, not a point estimate
7. Save as `output/[YYYY-MM-DD]-budget-forecast.md`

## Input
- QuickBooks (last month actuals)
- Google Sheets (budget model)
- `../business.md` (planned launches, current priorities)

## Output
`output/[YYYY-MM-DD]-budget-forecast.md`
Sections: last month summary, budget vs. actual table, variance flags, 90-day forecast.

## Error Handling
- If QuickBooks data is incomplete, produce the report with a note about the data gap and estimated actuals
- If the Google Sheets budget hasn't been updated for the current month, flag — do not forecast against a stale budget

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
