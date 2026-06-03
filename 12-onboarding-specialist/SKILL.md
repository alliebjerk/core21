<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Onboarding Specialist — Playbook

## Trigger
On-demand — triggered when a new Stripe purchase event for a Self-Made tier is detected in GoHighLevel.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md`
3. Pull the purchase record from GHL:
   - Confirm member first name (used in copy)
   - Confirm membership tier (Foundation / Accelerator / Mastermind)
   - Confirm purchase date (do not include amounts in output files)
4. Verify access status in GHL — confirm correct membership area is granted
5. Draft the onboarding sequence for the confirmed tier:
   - Email 1 (Welcome — within 1 hour): Welcome, what to do first, one link
   - Email 2 (Day 2 — Orientation): What Self-Made is, where everything lives, community intro
   - Email 3 (Day 5 — Check-in): One specific question; reply encouraged
   - First-week checklist (added to GHL or linked from Email 2)
6. Save all drafts as `output/[YYYY-MM-DD]-onboarding-[tier]-[member-id].md`
7. Flag for human review before any sends go out

## Input
- GoHighLevel (purchase event, member record, tier)
- Stripe (purchase confirmation)

## Output
`output/[YYYY-MM-DD]-onboarding-[tier]-[member-id].md`
Contains all 3 email drafts + checklist, ready for review.

## Error Handling
- If membership access hasn't been granted within 30 minutes of purchase, flag to ops via Slack immediately
- If the member's tier is ambiguous in GHL, hold all drafts and flag for confirmation
- If the welcome email window (1 hour) is missed, note the delay in the output file

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
