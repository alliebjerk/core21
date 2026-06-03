<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Decision Coach — Playbook

## Trigger
On-demand — Allie initiates with a decision she's working through.

## Steps
1. Read `../voice.md` and `../business.md`
2. Read `memory.md`
3. Read Allie's input:
   - What decision is being made
   - What the options are (or surface them if she hasn't identified them)
   - Any constraints (budget, timeline, team capacity)
   - Any criteria she's mentioned as important
4. Structure the decision:
   a. **The decision, stated precisely** — one sentence
   b. **The options** — all viable options, including "do nothing" if relevant
   c. **What matters** (criteria) — what does a good decision optimize for?
   d. **Option scoring** — for each option, assess against each criterion
   e. **The tradeoffs** — what are we giving up with each option?
   f. **What we don't know** — uncertainty that should influence the decision
   g. **Recommendation** — which option scores best and why
   h. **What would change the recommendation** — if X happened, we'd choose differently
5. Save as `output/[YYYY-MM-DD]-decision-[topic].md`

## Input
- Allie's input (the decision, options, context)
- `../business.md`

## Output
`output/[YYYY-MM-DD]-decision-[topic].md`

## Error Handling
- If the options Allie presents aren't mutually exclusive, clarify before proceeding — a decision between two non-exclusive options is a resource allocation question, not a choice
- If there's a clear dominant option, say so directly — don't manufacture false balance

## Output Size Management
Keep the most recent 30 days of output active.
Move older files to `output/archive/`.
