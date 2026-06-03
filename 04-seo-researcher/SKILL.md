<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# SEO Researcher — Playbook

## Trigger
Weekly, Monday at 6am CT.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md` — note keywords or topics currently being tracked
3. Pull Google Search Console data for the past 30 days:
   - Pages gaining or losing impressions
   - Queries where Allie ranks positions 11-20 (quick-win opportunities)
   - Pages with high impressions but low CTR (title/meta issue)
4. Run keyword research in Ahrefs/SEMrush:
   - Seed terms: "tiny offer," "digital products," "offer suite," "online course pricing," "how to sell digital products," "AI for online business"
   - Filter: KD under 40, monthly volume 500+, commercial or informational intent
   - Map to content pillars
5. Identify 3-5 priority opportunities:
   - Quick win (page 2 ranking needing a boost)
   - New content opportunity (keyword with no existing content)
   - Competitor gap (competitor ranks; Allie doesn't)
6. Save as `output/[YYYY-MM-DD]-seo-report.md`
7. Update `memory.md` with new tracking notes

## Input
- Google Search Console
- Ahrefs or SEMrush
- `../business.md` (content pillars, offer ladder)

## Output
`output/[YYYY-MM-DD]-seo-report.md`
Format: 3-bullet executive summary, quick wins table, new opportunity table, competitor gap section.

## Error Handling
- If Search Console data is delayed, run keyword research only and note the gap
- If an opportunity conflicts with current promotional priorities, flag and defer

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
