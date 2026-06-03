<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Objection Handler — Playbook

## Trigger
On-demand — triggered when Allie or ops tags a GHL contact with `needs-followup` or `objection-[type]`.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md`
3. Pull the lead record from GHL — review full notes and prior conversation
4. Identify the objection type from the tag or notes
5. Draft the response:
   a. Acknowledge the objection specifically (not generically)
   b. Reframe if appropriate — connect to what they said they wanted
   c. Provide one clarifying piece of information or proof
   d. One CTA — not multiple options
6. If writing a follow-up sequence (stalled deal):
   - Email 1 (Day 1): Gentle check-in, no sales pressure, reference their specific situation
   - Email 2 (Day 4): One piece of value — case study, specific result, or clarifying info
   - Email 3 (Day 8): Honest close — either they're in or they're not, and both are okay
7. Save as `output/[YYYY-MM-DD]-objection-[lead-id].md`

## Input
- GoHighLevel CRM (lead record, tags, notes)
- `../business.md` (offer details)

## Output
`output/[YYYY-MM-DD]-objection-[lead-id].md`
Includes: objection type, draft response(s), recommended send timing.

## Error Handling
- If the objection type is unclear, draft a general check-in that doesn't address a specific objection and flag for clarification
- If the lead hasn't received a proposal yet, escalate to the Proposal Writer first

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
