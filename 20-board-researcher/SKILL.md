<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Board Researcher — Playbook

## Trigger
Weekly, Monday at 6am CT.

## Steps
1. Read `../voice.md` and `../business.md` — understand current strategic priorities before researching
2. Read `memory.md` — check ongoing topics to monitor
3. Run research across these areas:
   a. **Industry trends:** digital products, online membership models, AI for business — new data, studies, or major platform changes
   b. **Competitor activity:** new offers, launches, positioning changes from key players in coaching/digital products
   c. **Audience conversation:** what Allie's ICP (coaches/consultants/course creators doing $100K+) is talking about on Reddit, Facebook groups, LinkedIn, Twitter/X
   d. **Platform changes:** Instagram, Facebook, email deliverability, or payment platforms
   e. **AI news relevant to the business:** new tools, policy changes, audience sentiment
4. Compile the weekly brief:
   - 3-5 items max — quality over quantity
   - Each item: what happened, source, and why it matters for Allie's business specifically
5. Save as `output/[YYYY-MM-DD]-research-brief.md`
6. Update `memory.md` with ongoing topics to continue monitoring

## Input
- Web search (Brave Search, Google)
- Public sources (social platforms, news, industry publications)

## Output
`output/[YYYY-MM-DD]-research-brief.md`
Format: one section per item — source cited, "Why it matters for Allie's business" note.

## Error Handling
- If a topic returns no meaningful new developments, note "no significant developments this week" — don't pad with thin content
- If a platform change could significantly affect the business, flag as URGENT to the Chief of Staff immediately

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
