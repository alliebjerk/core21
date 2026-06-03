<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Proposal Writer — Playbook

## Trigger
On-demand — triggered when Allie or ops adds the tag `needs-proposal` to a GHL contact, or a Notion task requests a proposal.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md`
3. Pull the lead's full contact record from GHL:
   - Opt-in form responses
   - Notes from the Lead Qualifier or team
   - Conversation history if available
4. Identify the appropriate offer from the offer ladder in business.md
5. Draft the proposal:
   a. Open with what you understand about their situation (specific to their form/notes)
   b. Name the gap or problem — no warmup
   c. Describe how the offer addresses it — specific, not generic
   d. State the offer name, format, and duration
   e. State the investment (confirm price from business.md before including)
   f. State the next step (one action only)
6. Save as `output/[YYYY-MM-DD]-proposal-[lead-id].md` (GHL contact ID, not name)
7. Add a note to the GHL contact record: "Proposal draft saved — [date]"

## Input
- GoHighLevel CRM (lead record, notes)
- `../business.md` (offer details, pricing)
- `../05-lead-qualifier/output/` (scoring rationale)

## Output
`output/[YYYY-MM-DD]-proposal-[lead-id].md`

## Error Handling
- If the lead record has insufficient information, save a partial draft with [FLAG: need more info about X]
- If the price for the relevant offer isn't confirmed in business.md, write [PRICE TBD — confirm before sending]

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
