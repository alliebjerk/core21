<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Support Agent — Playbook

## Trigger
Hourly during business hours (9am–5pm CT, Monday–Friday).

## Steps
1. Read `../business.md` — confirm current offer names, tier names, any known issues
2. Read `memory.md` — check for recurring issues or updated response patterns
3. Check Gmail support inbox and GHL conversations for new inquiries in the last hour
4. For each new inquiry:
   a. Categorize: access issue / billing / content question / refund / feedback / other
   b. Look up the member record in GHL — confirm tier and purchase history
   c. Draft a response:
      - Open with their first name
      - Address their specific question — not a generic response
      - Access issue: confirm what they should have and what to check first
      - Billing question: confirm what the record shows and what the next step is
      - Refund request: acknowledge, do not promise, flag for ops
      - Close with one clear next step
   d. Save draft as `output/[YYYY-MM-DD]-support-[inquiry-id].md`
   e. Flag any inquiry needing human review
5. Update `memory.md` if a new pattern or recurring issue appears

## Input
- Gmail (support inbox)
- GoHighLevel (member records, conversation history)

## Output
`output/[YYYY-MM-DD]-support-[inquiry-id].md`
Each file: inquiry summary, category, draft response, and any flags.

## Error Handling
- If GHL member record can't be found, draft an acknowledgment only and flag for manual lookup
- If the inquiry is time-sensitive (can't access just-purchased content), flag as URGENT to Slack #support

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
