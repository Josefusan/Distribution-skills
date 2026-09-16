---
name: business-strategy-prompts
description: Ready-to-paste interview prompts for each stage of a business, from scoring an idea backlog and matching a business model, through positioning, ICP and marketing-strategy JSON, Reddit pain-point and distribution-channel deep research, to an execution checklist. Use when the user says "which of my ideas should I pursue", "what business should I start", "I have no capital", "how do I position myself", "who is my ideal customer", "where do my customers hang out", "research pain points on Reddit", "make me a marketing strategy", "turn this idea into a plan", or wants to mine chat history with a partner for ideas.
---

# Business Strategy Prompts

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill gives you EP's business-strategy prompt library and tells you which one to run at which stage. Core thesis: every prompt interviews first (one question at a time), injects business and ICP context, and outputs a structured artifact (JSON profile, roadmap, or checklist) that feeds the next stage. Once the plan exists, the only variable left is execution.

## When to use

- The user has a pile of ideas and cannot pick one.
- The user does not know what business fits their skills, capital, and risk tolerance.
- The user needs positioning, a distribution path, or a 30-day plan.
- The user needs a reusable ICP or marketing-strategy profile.
- The user needs customer language and pain points for copy or offers.
- The user needs to know which channels their buyers actually use.
- The user wants an idea turned into a tracked execution checklist.
- The user has years of chat history with a business partner.

## Core principles

**Interview, then output.** Each prompt gathers context question by question before producing anything; that is where the quality comes from.

**Score ideas on fixed axes and be brutal about flaws.** Market potential, execution complexity, resource requirements, time to market, revenue streams, risks, competitive advantage; then rank by profit potential, speed, resource efficiency, and moat.

**Match the model to the person, not the trend.** Skills, experience, personality, risk tolerance, time, capital, income goals determine which business models fit.

**Positioning branches on camera comfort.** On-camera path: YouTube/TikTok/Instagram. Off-camera path: X threads, newsletter, LinkedIn.

**Forbid speculation in research prompts.** Distribution research uses a senior market-research-analyst role and real behavior, buyer readiness, and quoted language, not guesses.

**Mine pain points in the customer's own words.** Reddit research uses three query formats (emotional triggers, aspirational language, pain indicators) and scores intensity via comment engagement.

**Output JSON when the result will be reused.** ICP, marketing strategy, and distribution channels become profiles fed into future prompts or handed to a team.

**A profile becomes a checklist becomes an agent task.** Interview → project profile → execution checklist → optionally a coding agent's tracked project.

**Your communication history is a second brain.** Partner chat exports contain every idea you ever discussed; make them AI-queryable.

## Workflow

Run the stages in order; skip stages the user has already completed.

1. **Idea stage.**
   - Many ideas → Idea Backlog Analysis.
   - No idea, unsure of fit → Business-Model Matcher (or the zero-capital variant if no money) and/or Objective Self-Analysis to find the unique edge.
   - Idea chat history exists → Mine Your Communication History.
2. **Validation stage.** One idea chosen → Idea-to-Execution Blueprint (phased interview up to 50 questions, flags critical flaws immediately). Pair with Reddit Pain-Point Research to confirm the pain is real and learn the language.
3. **Positioning stage.** Three-Phase Market-Positioning Strategist (skills → market validation → distribution by camera comfort). Build the ICP Interview → JSON now; it feeds every later prompt.
4. **Distribution stage.** Distribution-Channel Deep Research (JSON) and Traffic-Strategy Interview; then Marketing-Strategy Interview → JSON.
5. **Execution stage.** Interview → Project Profile → Checklist; optionally hand the checklist to a coding agent as a tracked project.
6. **Store every output** as a profile (see `context-engineering-profiles`) and inject it into the next stage's prompt.

## Checklists / templates

### Idea Backlog Analysis

```
Here is every idea from my notes app: [paste].
For each idea score 1-10: market potential; execution complexity. Also assess: resource requirements; time to market; revenue streams; risks; competitive advantage.
Then run pattern recognition: themes, synergies, and combinations across ideas. Suggest simplifications and pivots.
Rank all ideas by profit potential, speed, resource efficiency, and moat.
Produce an execution roadmap for the top three.
Be brutally honest about the flaws in every idea.
```

### Idea-to-Execution Blueprint

```
Interview me one question at a time (up to 50 questions). Flag any critical flaw the moment you see it.
Phases: (1) core idea extraction; (2) market and competitor analysis; (3) marketing strategy: content pillars, organic, SEO, paid with budget allocation; (4) execution framework: resources, risks, milestones, KPIs, cash flow, tech stack; (5) optimization and scaling.
Final output: executive summary; 30-60-90 day plan; resource requirements and burn rate; KPIs with break-even analysis; risk assessment; scaling triggers.
```

### Business-Model Matcher

```
Interview me one question at a time, maximum 20 questions, each building on my previous answers. Cover: my skills; experience; personality and work preferences (risk tolerance, time available); practical constraints (capital, income goals).
Output 3-5 business models aligned with my answers. For each: timeline to profitability; starting requirements; validation steps; scaling potential.
```

Zero-capital variant:

```
Part 1: up to 10 questions about my skills. Part 2: up to 5 questions about my resources. Part 3: output my 3 most valuable skill combinations and the top 2 zero-cost opportunities I can launch within 24 hours, each with 5 immediate action steps.
```

### Three-Phase Market-Positioning Strategist

```
Phase 1, skill assessment: probe my existing specialized skills. If none, guide selection via what I research for fun and where I outperform peers. End with a 90-day learning roadmap.
Phase 2, market validation: demand, competition, pricing, and whether service, product, or hybrid fits.
Phase 3, distribution: ask whether I am comfortable on camera. On-camera path: YouTube / TikTok / Instagram. Off-camera path: X threads, newsletter, LinkedIn.
End with a 30-day action plan and metrics. One question at a time.
```

### Objective Self-Analysis (business direction)

```
Interview me across five categories: natural proclivities (what energizes me, flow states); skills (what people pay me for and ask my help with); experience (repeated patterns, proven wins); network (who can help, communities I belong to); unfair advantages (resources, background, head starts).
Output per-category analysis and a 3-5 sentence summary of my unique edge.
```

### Traffic-Strategy Interview (Traffic Secrets-based)

```
Interview me about: my product and unique value proposition; ideal customer; current channels; my top three traffic challenges; 6-12 month goals.
Then apply Russell Brunson's frameworks: Dream 100; content distribution across owned and external platforms; hook-story-offer funnels.
Output: business summary; traffic diagnosis; strategic framework; 30-60-90 day plan.
```

### Marketing-Strategy Interview → JSON

```
Interview me one question at a time through four phases: (1) business foundation; (2) positioning and messaging; (3) channels and content; (4) strategy design: customer journey, lead capture, offers, pricing, campaigns.
Export the result as a JSON marketing-strategy profile I can feed into future prompts or hand to a team.
```

### ICP Interview → JSON

```
Ask me ten questions, one at a time, covering: demographics; values; lifestyle; pains; purchase triggers; price sensitivity; platforms; brand expectations.
Output a reusable ideal-customer JSON including: recommended channels; content strategy; messaging; unique selling propositions.
```

### Reddit Pain-Point Research (run in deep-research mode)

```
Product: [inject]. ICP: [inject JSON].
Generate psychographic Reddit search queries in three formats: emotional triggers ("frustrated with", "hate when"); aspirational language ("wish I could"); pain indicators ("anyone else struggle with").
Analyze results for: emotional themes; recurring frustrations; language patterns; intensity (via comment engagement); competing solutions mentioned.
Organize into primary, secondary, and emerging pain points. For each: direct quotes; intensity score 1-10; frequency; solutions tried; gaps.
```

### Distribution-Channel Deep Research

```
You are a senior market research analyst. Business context: [inject]. ICP: [inject]. Do not speculate; base everything on real observed behavior.
Step 1: where do my ideal customers spend time online? Step 2: what are their frustrations and unmet needs there? Step 3: which organic and paid channels have the highest ROI given real behavior and buyer readiness?
Output JSON:
{
  "distribution_channels": [
    {"name": "", "type": "organic | paid", "reason": "", "strategy": ""}
  ],
  "audience_touchpoints": [],
  "audience_painpoints": []
}
```

### Interview → Project Profile → Checklist

```
Prompt A: Interview me about my idea and strategy, one question at a time, and compile a "project profile" JSON.
Prompt B: Using this project profile, produce a complete execution checklist with milestones, tasks, dependencies, and estimates.
Optional: hand the checklist to a coding agent as a tracked project checklist.
```

### Mine Your Communication History

```
1. Export chat history with my business partner (Telegram / Slack).
2. Have an AI IDE write a conversion/cleaning script optimized for token economy, chunking if needed.
3. Feed the cleaned export to an LLM: "Extract every business idea ever discussed, with date and context."
Alternative: fill a partner-analysis profile for both parties: communication style; problem-solving approach; decision speed; skills; confidence; delegation; leadership; adaptability.
Habit: message your partner every idea you have; the archive becomes an AI-queryable second brain.
```

## Anti-patterns

- Skipping the interview and asking for a strategy from a one-line description.
- Letting research prompts speculate instead of grounding in real behavior and quotes.
- Producing a plan without an ICP profile first.
- Keeping outputs as chat text instead of saving them as reusable JSON.
- Running the zero-capital matcher and then picking an opportunity that needs capital.
- Solving product and distribution simultaneously as a first-timer (see `distribution-first-strategy`).

## Dated / volatile notes

- Idea backlog, blueprint, traffic-strategy, interview→checklist: March 2025, practice might be outdated.
- Marketing/ICP JSON interviews: April 2025. Business-model matcher, positioning strategist, Reddit research, distribution research: May 2025. Communication mining: June 2025. Objective self-analysis: July 2025.
- "Deep-research mode" refers to 2025-era product features; the pattern generalizes to any agentic research tool.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `context-engineering-profiles`, `distribution-first-strategy`, `market-and-problem-selection`, `offer-design-and-buyer-psychology`, and `advisor-and-self-analysis-prompts`.
