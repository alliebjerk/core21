<!-- EXAMPLE CONTENT: This playbook is filled in for a sample business and its tools. Replace the steps, tools, and details with your own. -->

# Onboarding Agent — Playbook

## Trigger
Once, at initial setup. Buyer runs this agent manually after forking and cloning the repo.

## Steps
1. Greet the buyer — explain what this session does and how long it takes (~20-30 min)
2. **Section 1 — Business Context** (for business.md):
   - "What's your business name, and what do you sell?"
   - "Who do you sell to? Describe your best customer in 2-3 sentences."
   - "What are your main offers and their price points?"
   - "What tools do you use daily? (CRM, email, project management, payment processor)"
   - "What are you most focused on this quarter?"
3. **Section 2 — Voice** (for voice.md):
   - "How would a longtime client describe the way you communicate? Give me 3-5 words."
   - "What's a sentence you'd never write because it sounds like someone else?"
   - "What words or phrases make you cringe when you see them in your industry?"
   - "Do you have a signature phrase — something you say often that's become yours?"
   - "Paste one piece of your writing that sounds exactly like you. Even a paragraph."
4. **Section 3 — Agent Recommendations:**
   - Based on tool stack and priorities, recommend 3 agents to install first
   - For each: what it does, why it fits their situation, what they need to set it up
5. Produce the setup summary:
   - A filled-in draft of voice.md based on their answers
   - A filled-in draft of business.md based on their answers
   - The 3 recommended agents with setup notes
6. Save to `output/[YYYY-MM-DD]-onboarding-session.md`
7. Close: "Here's your next step: open voice.md and business.md, delete the example content, and paste in what we just built together."

## Input
Buyer's answers (provided interactively during the session).

## Output
`output/[YYYY-MM-DD]-onboarding-session.md`
Contains: draft voice.md content, draft business.md content, 3 agent recommendations with setup notes.

## Error Handling
- If the buyer doesn't know their tool stack yet, note it and include generic setup instructions for the most common tools (GHL, Notion, Stripe)
- If the buyer's business doesn't fit the product's ICP (very early stage, no offers yet), note it honestly — the product works best with at least one offer and some revenue

## Output Size Management
Keep all session output — do not archive onboarding sessions.
