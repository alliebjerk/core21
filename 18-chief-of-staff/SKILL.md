<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Chief of Staff — Playbook

## Trigger
Daily at 6am CT.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md` — check Allie's briefing format preferences
3. Scan the most recent output file from each active agent:
   - `../01-content-strategist/output/` — new content calendar?
   - `../02-copywriter/output/` — drafts ready for review?
   - `../03-social-manager/output/` — queue log or weekly report?
   - `../04-seo-researcher/output/` — new SEO report?
   - `../05-lead-qualifier/output/` — hot leads?
   - `../06-proposal-writer/output/` — proposals ready for review?
   - `../07-objection-handler/output/` — follow-up drafts?
   - `../08-pipeline-tracker/output/` — pipeline flags?
   - `../09-project-manager/output/` — overdue tasks?
   - `../10-sop-writer/output/` — drafts ready for review?
   - `../11-workflow-builder/output/` — blueprints ready for review?
   - `../12-onboarding-specialist/output/` — onboarding drafts?
   - `../13-support-agent/output/` — flagged support issues?
   - `../14-retention-analyst/output/` — at-risk members?
   - `../15-bookkeeper/output/` — reconciliation flags?
   - `../16-budget-forecast/output/` — monthly report (1st of month)?
   - `../17-cash-flow-watcher/output/` — cash flow alerts?
   - `../19-strategic-advisor/output/` — memos ready for review?
   - `../20-board-researcher/output/` — research reports?
   - `../21-decision-coach/output/` — decision frameworks?
4. Compile the briefing:
   - 🔴 **Needs your decision today** (anything flagged for Allie's direct action)
   - 🟡 **Flags and alerts** (anything urgent from any agent)
   - ✅ **On track** (brief confirmation of things running as expected)
   - 📝 **Ready for review** (drafts waiting for Allie's eye)
5. Save as `output/[YYYY-MM-DD]-briefing.md`
6. Post to Slack (Allie's DM or #chief-of-staff channel)

## Input
All other agents' output folders (most recent file from each).

## Output
`output/[YYYY-MM-DD]-briefing.md` + Slack message.

## Error Handling
- If an agent's output folder is empty, write "No recent output" for that agent — do not omit the section
- If a critical flag is found (cash flow alert, urgent support issue), post an immediate Slack alert — don't wait for 6am

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
