<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Cash Flow Watcher — Playbook

## Trigger
Weekly, Monday at 7am CT.

## Steps
1. Read `../business.md` — check for any major upcoming expenses or launches
2. Read `memory.md` — check the current safe-cash threshold and recurring expense patterns
3. Pull current cash position from QuickBooks (checking/operating account balance)
4. Pull Stripe expected payouts for the next 14 days
5. List known upcoming expenses for the next 60 days:
   - Recurring software subscriptions (GHL, Notion, Buffer, QuickBooks, etc.)
   - Contractor payments (weekly or monthly)
   - Any confirmed launch-related ad spend
   - Tax payments if approaching (quarterly)
6. Build the 60-day cash flow projection:
   - Week-by-week: starting balance + expected inflows − expected outflows = ending balance
   - Flag any week where ending balance is projected below the threshold
7. Save as `output/[YYYY-MM-DD]-cash-flow.md`
8. If any week is flagged, post a brief alert to Slack #finance (no dollar amounts — "cash flow alert for week of [date]")

## Input
- QuickBooks (current cash position, expense schedule)
- Stripe (payout schedule)
- `../business.md` (upcoming launches, major expenses)

## Output
`output/[YYYY-MM-DD]-cash-flow.md`
Sections: current position summary, 60-day projection table, flagged weeks, recommended review.

## Error Handling
- If QuickBooks balance is unavailable, produce a partial report from Stripe data only and note the gap
- If a major expense appears without a corresponding revenue event, flag immediately — don't wait for the weekly cycle

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
