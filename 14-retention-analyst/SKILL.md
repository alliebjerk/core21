<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Retention Analyst — Playbook

## Trigger
Weekly, Monday at 8am CT.

## Steps
1. Read `../business.md` — confirm active membership tiers
2. Read `memory.md`
3. Pull member activity data from GHL for the past 30 days:
   - Last login date (if tracked)
   - Email open/click activity
   - Community participation
   - Support inquiries about pausing or canceling
4. Pull Stripe data:
   - Payment failures in the past 7 days
   - Cancellations initiated
   - Downgrades (tier changes)
5. Score each member against at-risk signals:
   - No login in 14+ days: +1
   - No email engagement in 30+ days: +1
   - Unresolved payment failure: +2
   - Cancellation initiated: +3
   - Support inquiry about pausing/downgrading: +2
6. Flag any member with 3+ risk points
7. Recommend action:
   - 3-4 points: personal email from the CS team
   - 5+ points: escalate to Allie or CS lead for direct outreach
8. Save as `output/[YYYY-MM-DD]-retention-report.md`
9. Update `memory.md` with new at-risk patterns

## Input
- GoHighLevel (member activity, tags)
- Stripe (payment status, cancellations)

## Output
`output/[YYYY-MM-DD]-retention-report.md`
Sections: summary metrics, at-risk member list (IDs only), recommended actions, trend notes.

## Error Handling
- If Stripe data is unavailable, produce the report from GHL data only and note the gap
- If a member ID appears in both a cancellation and a new purchase in the same week, flag as a possible tier change — not churn

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
