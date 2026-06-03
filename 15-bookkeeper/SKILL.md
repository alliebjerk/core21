<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Bookkeeper — Playbook

## Trigger
Weekly, Friday at 6am CT.

## Steps
1. Read `../business.md` — confirm current offer names and revenue categories
2. Read `memory.md` — check for categorization rules and recurring patterns
3. Open QuickBooks — review all uncategorized transactions from the past 7 days
4. For each transaction:
   - Match to a Stripe payout or other source
   - Categorize to the correct account:
     - Tiny Offer product sales → Product Revenue
     - Self-Made membership payments → Recurring Revenue
     - Refunds → Refund / Contra-Revenue
     - Ad spend (when running) → Advertising Expense
     - Tool subscriptions (GHL, Notion, Buffer, etc.) → Software Expense
     - Team payments → Contract Labor or Payroll (confirm with accountant)
   - Flag anything that doesn't fit a known category
5. Reconcile Stripe payouts to QuickBooks bank deposits:
   - Every Stripe payout should appear as a bank deposit
   - Flag any payout without a matching deposit, or vice versa
6. Flag anomalies:
   - Transactions more than 50% above/below weekly average
   - Refunds with no corresponding sale
   - Duplicate charges
7. Save as `output/[YYYY-MM-DD]-bookkeeping-report.md`

## Input
- QuickBooks (transaction data)
- Stripe (payout history)

## Output
`output/[YYYY-MM-DD]-bookkeeping-report.md`
Sections: transactions categorized, reconciliation status, flags, open questions for the accountant.

## Error Handling
- If QuickBooks sync from Stripe failed, note the gap — do not manually enter data; flag for the accountant
- If a transaction category is ambiguous, leave uncategorized and add [FLAG: need accountant guidance]

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
