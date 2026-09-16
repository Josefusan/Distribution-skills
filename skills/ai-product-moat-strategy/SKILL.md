---
name: ai-product-moat-strategy
description: Evaluate or design an AI product, wrapper, agent, API, or AI service for defensibility and profit. Use when the user asks "is this just a GPT wrapper", "will OpenAI/Anthropic kill my product", "what should I build with AI", "how do I make money with AI", "is SaaS dead", wants to start an AI automation agency, is choosing between a general agent and a niche tool, asks about GEO / getting cited by ChatGPT, or wants to know which AI sub-industries are worth entering. Also trigger when a user describes an AI idea with no data, domain, or distribution edge.
---

# AI Product Moat Strategy

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill evaluates and shapes an AI product so it survives base-model advances and frontier-lab competition. Core thesis: the model is not the product. Defensibility comes from niche-specific data and best practices wrapped around the model, a UX that makes one job 10x easier, a domain too narrow for frontier labs to bother with, and distribution. Specialized knowledge plus basic AI fluency out-earns elite technical skill.

## When to use

- Assessing whether an AI idea is defensible or a commodity.
- Deciding between a general-purpose agent and a narrow vertical tool.
- Someone is discouraged by "the next model update will kill this".
- Planning an AI automation agency or "AI person for X industry" positioning.
- Choosing which AI sub-industry or skill stack to invest in.
- Wanting the product or brand to be recommended by ChatGPT/LLM search (GEO).
- Evaluating an AI tool the user is spending time on ("is this worth learning?").

## Core principles

**Data is the moat, especially for small companies.** EP: SaaS in 2026 is niche-specific knowledge and best practices wrapped around an LLM API. A dedicated thumbnail SaaS beats vanilla Nano Banana while literally calling the Nano Banana API, because it injects context on what a good thumbnail looks like; customers pay $29/month for the data and specialty. Instrument every funnel to collect attributes and behavior from day one; 50k emails with no attributes are nearly worthless.

**Base-model advances strengthen specialized tools.** When 4o image generation was declared the death of thumbnail tools, EP's counter: foolproof single-job tools with element-level compositing, presets, templates, and emotion libraries beat raw ChatGPT, and get better with each model release.

**"Wrapper" is not an insult.** Value lives in the UX layer: clean interface, hard-coded optimal prompt structure for one use case, external integrations, memory, tool-calling, packaged so a task is 10x easier than in a raw LLM. Better UX than the underlying tool justifies an upcharge.

**Build narrow, never general.** The moment a general-purpose agent gets traction, frontier labs come for the market. Build domain-specific products they will not bother with.

**Specialized APIs are a major 2026 opportunity.** Packaged frameworks that let agents perform profitable actions better than vanilla models, in niches too small for labs: proprietary data, workflows, and best practices as a service. Motto: help an agent do things that increase profit for the business using it.

**Knowledge bases are the next info product.** EP's prediction (2025-06): people will sell curated knowledge bases queried through AI instead of courses. "GPT is an empty book, the knowledge base is the content inside." Knowing where information comes from and how to qualify it is the scarce skill.

**Durable edges are everything around the build.** Market understanding, deep domain knowledge, taste, writing like a human, attracting attention to a utility, human and creator networks, understanding social algorithms. Shipping fast produces a moatless app that bets everything on distribution; the same distribution plus a hard-to-replicate product (serious data engineering) compounds far more.

**Knowledge asymmetry is the edge.** Insiders overestimate what average people know; most people's AI knowledge stops at badly-used ChatGPT. An obscure niche with the best AI tool serving it is a realistic path to $1M.

**Specialized knowledge + AI is the #1 skill stack.** A dentist knows which AI tools would fix his daily problems; an outsider guesses. No specialization? Acquire it, or partner with someone who has it in a high-value niche, integrate AI into their workflow, productize.

**Become the go-to AI person for one domain.** Deep domain knowledge plus basic AI knowledge confers authority because every industry wants to replace workloads with agents. You need to understand the process being outsourced, not be highly technical.

**AI changes industries; it doesn't kill them.** People with money outsource to save time; EP can build a better site with AI than most front-end devs and still hires a dev 9 times out of 10. "SaaS is dead" is an indie-hackers-selling-to-tinkerers artifact.

**AI automation agencies: real demand, low bar, fast rinse.** The #1 skill is understanding how businesses operate, not automation. Specialize, be reliable, display competence through a personal brand. Don't automate everything: for content and customer-facing work, inexpensive human labor often beats AI.

## Workflow

1. **Name the job, the buyer, and the buyer's money.** "[Tool] helps [specific role in specific industry] do [one job] so that [profit / time saved]." Decision point: if the job is general ("an agent that does anything") or the buyer is a tinkerer without budget, stop and narrow.

2. **Score the moat with the rubric below.** Identify which of the five edges the product has today: data/context, UX-for-one-job, domain narrowness, distribution, network/taste. Zero or one edge → do not build yet; add edges in step 3.

3. **Design the data layer.** What niche-specific knowledge, best practices, examples, or user context does the product inject that the vanilla model lacks? Where does it come from (proprietary process, curated sources, collected user behavior)? How does it compound (funnel instrumentation, user feedback, outcome data)? If the answer is "the prompt", that is not enough on its own.

4. **Design the UX layer.** List the steps a user takes in a raw LLM to do this job. Collapse them: hard-coded prompt structure, presets, templates, integrations, memory, tool-calling. Target "10x easier than doing it manually in ChatGPT".

5. **Test against base-model advance.** Ask: if the next frontier release does this task better out of the box, does the product get better (integrates the new model plus keeps its data/UX/workflow) or die? Redesign until the answer is "gets better".

6. **Check frontier-lab exposure.** Would a lab plausibly build this in-house? If yes, narrow the domain or convert to a specialized API/workflow layer businesses plug into agents.

7. **Choose the form.** Vertical SaaS, specialized API, curated knowledge base queried via AI, AI-powered tutor/education, or an AI-integrated service delivered by a practitioner. For agencies: sell the automated outcome of a process you understand, on a reliable, specialized basis; skip retainers you can't justify.

8. **Plan distribution and authority.** Become the go-to AI person in the domain: publish niche-specific automations and results; own an email list or community; consider running an active subreddit for LLM-search findability. Route to `distribution-first-strategy`.

9. **Apply GEO to the product and brand.** Follow the GEO checklist below so the brand enters the retrieval set and is the clearest, most extractable source.

## Checklists / templates

### AI moat rubric (0-2 each, out of 10)

| Edge | 0 | 2 |
|---|---|---|
| Data / context | Vanilla prompt only | Proprietary, compounding niche data and user context |
| UX for one job | Chat box | Presets, templates, integrations, memory; 10x faster than raw LLM |
| Domain narrowness | General-purpose | Niche too small for frontier labs, buyers with budget |
| Distribution | None planned | Owned channel, domain authority, creator network |
| Hard-to-replicate build | Weekend clone | Serious data engineering, workflows, integrations |

Under 4: commodity; 4-6: needs an added edge; 7+: defensible enough to ship and iterate.

### Money map for AI tools (EP, 2025-04)

Every tool you learn must map to one: AI as advisor, web scraping, market research, fast MVPs, visualizing product ideas, training your team, copywriting, content creation, static ads, traffic generation. If a tool maps to none, deprioritize it.

### Not-getting-left-behind framework (EP, 2025-04)

- Stay informed: make AI the feed's focal point; notifications on key accounts; newsletters; try every new tool.
- Weaponize industry depth; ideally run a business in the industry you serve.
- Act on ideas immediately; they expire fast.
- Learn how to learn with AI (summaries, roadmaps, interactive courses).
- Master prompting and tool-chaining (n8n workflows).
- Automate your own daily workflow, starting small.
- Build a distribution edge: personal brand, platform algorithms, owned channels.

### GEO checklist (EP, 2025-06)

Mechanics: the LLM splits the query into subqueries, searches (ChatGPT uses Bing) when training data is insufficient, retrieves the top 5-20 results, and cites the clearest, most extractable source. Ranking is the gateway; clarity wins the citation.

- [ ] Crawlable and indexed in Bing.
- [ ] Clear structure: headings, bullets, FAQs.
- [ ] Specific data and statistics.
- [ ] Firsthand experience and case studies.
- [ ] Cite authoritative sources.
- [ ] Original, quotable content.
- [ ] Optimize for question-phrased queries ("How to rank my YouTube video").
- [ ] Include credentials.
- [ ] Get mentioned on high-authority sites (Reddit, Quora); run an active subreddit.

### Profitable AI sub-industries (EP, 2025-06)

Generative AI (copy, video, images, speech, code); AI-powered hardware; retrieval optimization (GEO, RAG infrastructure, custom search indexing, knowledge graphs); agents/automation; AI-powered education; context engineering; vertical-specific SaaS (legal, healthcare, logistics, marketing).

### AI automation agency filter

- Can you explain the purpose of the workflow you propose to automate, in the owner's terms?
- Is the process time-burning for a profitable owner?
- Does a human still need to be in the loop (content, customer-facing)? If so, propose labor + AI, not AI alone.
- Can you show competence publicly (published automations, case studies) before asking for a retainer?

## Anti-patterns

- Building a general-purpose agent.
- Selling moatless products to indie hackers who like to tinker, then concluding "SaaS is dead".
- Positioning as a human-like AI coach instead of a curated knowledge base.
- Charging $10k/month retainers off one n8n tutorial.
- Learning tools for novelty with no money-map application.
- Collecting leads without attributes and behavior.
- Automating content or customer-facing work fully when cheap human input would perform better.

## Dated / volatile notes

- 2025-04: money map and not-getting-left-behind framework; tool names (n8n) may change.
- 2025-06: knowledge-base-as-info-product prediction ("within two years"); GEO mechanics (ChatGPT uses Bing, top 5-20 results); sub-industry list.
- 2025-07: AI automation agency assessment ("the new SMMA").
- 2026: "SaaS is niche knowledge wrapped around an LLM API" and specialized-API thesis; thumbnail SaaS / Nano Banana example ($29/month).
- 4o image generation reference is a 2025 event.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `market-and-problem-selection` (finding the niche), `offer-design-and-buyer-psychology` (packaging and pricing, BYO-API-key), `distribution-first-strategy` (owned channels and authority), and `online-business-playbooks` (AI-from-scratch and A-to-Z playbooks).
