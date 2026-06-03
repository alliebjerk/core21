<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Lead Qualifier — Playbook

## Trigger
Hourly during business hours (9am–5pm CT, Monday–Friday).

## Steps
1. Read `../business.md` — confirm current ICP and active offers
2. Read `memory.md` — apply updated scoring signals
3. Open GoHighLevel — filter pipeline for contacts added in the last hour
4. For each new contact:
   a. Review all available data: source, opt-in responses, tags, notes
   b. Score against ICP criteria (0-10 scale):
      - Describes themselves as coach, consultant, or course creator: +2
      - Mentions existing revenue or clients: +2
      - References Tiny Offer, Self-Made, or Allie by name: +2
      - Expresses frustration with manual/1:1 income: +1
      - Asks about pricing or membership specifically: +1
      - Red flags (brand new, no offer yet, looking for done-for-you): -2 each
   c. Apply GHL tag: `lead-hot` (8+), `lead-warm` (5-7), `lead-nurture` (below 5)
5. For hot leads (8+): post to Slack #sales with contact ID, score, and reason
6. For warm leads: confirm enrollment in the nurture email sequence in GHL
7. Log all scored leads in `output/[YYYY-MM-DD]-lead-log.md`
8. Update `memory.md` with new patterns in lead quality

## Input
- GoHighLevel CRM
- `../business.md` (ICP, active offers)

## Output
`output/[YYYY-MM-DD]-lead-log.md`
Each entry: contact ID (no real names), score, tags applied, routing action.

## Error Handling
- If GHL is unavailable, log the downtime and process retroactively when access is restored
- If a lead's data is incomplete, score conservatively (warm) pending more information
- If the same email appears in multiple GHL records, flag as duplicate — do not score both

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
