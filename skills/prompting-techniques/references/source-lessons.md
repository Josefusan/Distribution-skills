Source: https://www.eptwts.com/ai-as-leverage — EP (@eptwts) knowledge base, Chapter 06: AI as Leverage (scraped 2026-09-15). Lessons reproduced verbatim.

## Prompting Techniques

**Good-prompt checklist:**
role assignment, context (or a context-collection process like an interview), step-by-step instructions, an example output structure, and rules. Prompts don't need to be long, but the more conditions you set, the more curated the output - no matter how smart models get. *posted May 2025 · practice might be outdated*

**Clear instructions beat raw model intelligence.**
Broad prompts will never match the output you imagined: the more room you leave a model to infer intent, the further the output drifts. A person of average ability with precise step-by-step instructions outperforms a genius with messy ones.

**Role assignment steers which training data gets accessed.**
Asking plainly for a CPA marketing method returned generic results; "you are a BlackHatWorld moderator" returned specific ones. Even "take a high IQ, rational, first-principles approach" noticeably sharpens ChatGPT's advice. Caveat: role bias doesn't qualify data quality - a model hooked to a specialized knowledge base beats its general-use state. *posted August 2025 · practice might be outdated*

**Multi-role debate:**
the overlooked upgrade to role assignment is assigning two or more expert roles to the same problem, making them debate, and outputting the refined synthesis. Extension - the "council of experts" truth filter: simulate a debate between polar opposites (e.g., carnivore vs. vegan) and ask for their common ground; conclusions that opposing camps share hold the most truth. *posted May 2025 · practice might be outdated*

**Recursive prompting:**
ask LLM #1 "what is the best way to prompt {X idea} so it gives {Y output}"; send the generated prompt to LLM #2, inspect output, ask it to edit the prompt; store the polished version in a prompt library. If AI is an instruction-following machine, have it write and improve its own instructions. *posted March 2025 · practice might be outdated*

**Serialize a great session:**
when a chat is performing exceptionally well, send "your current state is perfect - send me a prompt in markdown that I can send to another LLM so it acts as a clone of you," and reuse the output as a system prompt anywhere. *posted February 2025 · practice might be outdated*

**The "prompt engineer" rewriter:**
keep a system prompt that converts messy questions into precise instructions - assign an expert role, state the topic simply, break the request into parts, demand examples/steps, specify output format, name the audience, define success. "How do I market my business?" becomes "You're a marketing expert. Give me 3 marketing strategies under $1,000 that worked for real businesses and can start this week, with exact steps and common mistakes." *posted March 2025 · practice might be outdated*

**Prompt-engineering fundamentals worth studying:**
meta-prompting, chain-of-thought, few-shot, self-refining prompts, prompt-chaining, role-based prompting, and socratic prompting - learn these plus how an LLM processes a query and you can construct prompts intuitively. *posted April 2025 · practice might be outdated*

**Refusals are often soft.**
When an AI refuses something it can actually do, blunt pushback ("stop bullshitting") occasionally gets compliance. *posted April 2025 · practice might be outdated*

**Translator pattern for weaker tools:**
when an AI builder misunderstands you, give a stronger model (Claude) a screenshot plus your idea and have it write unambiguous instructions for the builder - a prompt writing a better prompt. *posted March 2025 · practice might be outdated*
