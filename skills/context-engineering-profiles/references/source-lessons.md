Source: https://www.eptwts.com/ai-as-leverage — EP (@eptwts) knowledge base, Chapter 06: AI as Leverage (scraped 2026-09-15). Lessons reproduced verbatim.

## Core Principles

**AI multiplies whatever you already are.**
If you're good at something, it gets you good results 10x faster; if you're bad, it produces trash 10x faster. The operator is the most important variable: give the same model to an average Fiverr copywriter and to David Ogilvy, and Ogilvy's output wins. Domain expertise remains priority number one, because you cannot instruct an LLM to embody a skill you do not possess - prompting is transferring your skill into words so the model can embody it. Skills are not replaced by AI; they are amplified through it.

**You don't make money by "learning AI."**
You make money by learning how to make money - AI is just a tool that performs those actions faster or at scale. There are cracked technical people documenting a $3k MRR SaaS while a non-technical marketer does a $100k day ripping AI creatives for affiliate offers. You don't need to know 99% of how AI works to profit from it (like driving a car without understanding the engine). Identify the actions that make you money, then find where AI performs those actions faster or better - and ignore tool-hopping hype cycles, much of which is paid influence or engagement bait.

**Stop obsessing over new model releases.**
A better model makes zero measurable difference for 99% of people. If current tools aren't enough for you to build a cash-flowing business, the bottleneck is you, not the model. (2026-06)

**Being "good at AI" means exactly two things:**
feeding it your domain knowledge, and prompting it to emulate your skills. AI alone, without a skill to amplify, produces little.

**Career positioning:**
whatever your current skill is, become the best AI operator for that skill - a copywriter should become the best copywriting-focused AI operator. Someone who feeds a model "the brain of a copywriter" will replace plain copywriters as demand for manual digital labor falls.

**AI-assisted iteration beats fully offloaded output.**
Asking AI to generate a whole article and posting it as-is produces generic content; asking it for an outline, brainstorming headlines back-and-forth, drafting in your brand voice, then manually polishing produces results. And if someone can tell your output was AI-written, you are using it wrong - effective prompting requires active thinking about frameworks, rules, and context; the payoff is reallocating hours from manual drafting to actual needle-movers.

**You must know how to do a thing manually before you automate it.**
Agents are not all-knowing; handing one a task and expecting it to figure everything out fails. You remain the mastermind who knows what needs to be done and where agents can and cannot help.

**Know AI's four structural bottlenecks**
and design around them: (1) every new chat starts from zero - solve with stored, reusable context profiles; (2) AI has no intuition - it only processes predefined data; (3) it has no true creativity - it remixes training data or provided context, so novel ideas must come from you; (4) it hallucinates confidently and is good at making false things sound true - verify claims.

**A base LLM without good information is confidently stupid.**
It answers with the authority of the top-ranking sources for a query, so researching unfamiliar topics with it means getting lied to a lot. Consequence: LLMs make genuinely good information MORE valuable, not less - now you can feed it in and converse with it. On uncertain or contested topics, feed the model multiple sources yourself and work from there instead of trusting base training data.

**Route around known weaknesses:**
LLMs are strong at verbal, logical, and memory reasoning but weak at spatial reasoning (a vanilla LLM fails badly at chess puzzles). Factor this into task delegation. *posted March 2025 · practice might be outdated*

**Privacy rule of thumb:**
don't tell an LLM anything you wouldn't type into Google - the data handling is identical.

**The highest-leverage use of an LLM is as an ideation partner,**
amplifying your thinking through back-and-forth discussion, not as an answer machine - the answers you need are usually not in the training data. Feed it your business data and let personalized analysis surface ideas you wouldn't have considered; it shouldn't make decisions.

## Context Engineering: Profiles, Files, and Skills

**Prompt engineering is primarily a game of storing and reusing context.**
You, your business, and everything personal to you are not in the model's training data; an LLM cannot tell you which solution is best for your business until it knows your business. Build reusable context profiles (business, audience, marketing channels, goals) pasted into any prompt in one action. Output quality with vs. without them is night and day - like overclocking your LLM. *posted June 2025 · practice might be outdated*

**Context is just two buckets:**
facts about your situation the model doesn't know, plus instructions on how to use those facts. Categorize it and retrieve selectively - never dump wholesale. The fuller the context window, the worse the outputs. *posted December 2025 · practice might be outdated*

**Why JSON for stored context:**
LLMs handle structured, machine-readable data well; it is modular, easily editable, mergeable, and condenses context into fewer tokens, letting the model reference the right fields without ingesting whole paragraphs. But JSON is for storing context, not for prompting - prompt in plaintext or XML and inject JSON profiles as needed. "JSON prompting" was never magic; its real benefit was navigable templates with swappable variables, not model performance. (2025-08, reaffirmed 2026-04)

**The 8 core profile types**
I published templates for: business context, brand voice, marketing strategy, ideal customer, content strategy, product roadmap, audience psychographics, and YouTube scriptwriting. A business at full efficiency also holds profiles for each product, each distribution strategy, sales process, and team structure. Most of the time, simple context injection into prompts beats building a RAG system. *posted June 2025 · practice might be outdated*

**Build the business profile once - 1-2 hours - and reuse forever.**
Include: general overview (name, mission, problem solved, elevator pitch), product details and pricing, ideal customer personas (problems, desired outcomes, objections), and brand voice (tone, writing guidelines, example copy snippets). Fill it via an LLM interview rather than typing it out - interviews surface more accurate data than self-description. *posted June 2025 · practice might be outdated*

**Profile stacking:**
give the LLM multiple JSON profiles simultaneously (e.g., offer + ideal customer + distribution strategy) so it cross-references them for hyper-specific advice. Compounding quality: business + ICP + brand voice. *posted May 2025 · practice might be outdated*

**The three-input content formula:**
information context + brand voice profile + instruction. Example: a copywriting course transcript (info) + a creator's brand-voice profile + "generate 30 short-form reel scripts in this voice using this info." Feed a YouTube transcript to an LLM to clone any creator's voice into a reusable profile. *posted June 2025 · practice might be outdated*

**Claude skills are the current (2026) best home for standing context**
- effectively SOPs for AI, significantly better than GPT projects. A skill is just markdown files in a .zip: Claude injects a short description of each skill into every chat and loads only the relevant reference files when a task calls for them, so your context window isn't polluted (mentioning your VA's name pulls their full profile only in that moment). Turn every process, SOP, and standing context - including profiles of people you work with - into a skill. Make your business context (market, offer, positioning) a standalone skill, separate from task skills like copywriting; pairing a task skill with your business-context skill is what produces genuinely useful output. *posted November 2025 · practice might be outdated*

**ChatGPT's built-in memory is inferior to self-managed context profiles on six dimensions:**
structure (vague impressions vs. structured data), visibility, control (loads every session regardless of relevance), portability (vendor lock-in), modularity (mixes all projects), and collaboration (unshareable). My failure case: detailed diet/macros context saved as only "is interested in eating 4 meals per day." Memory also silently pollutes future outputs and cross-references unrelated conversations. Use memory for light personalization and drafting an initial profile; use files you control for serious context injection. (My earlier 2025-04 take advocated flooding ChatGPT memory with context - profiles-over-memory is my later, settled position.) *posted June 2025 · practice might be outdated*

**When context grows large, use a two-call pattern:**
call 1's only job is extracting task-relevant slices from your context store and assembling a prompt; call 2 does the actual work with a fresh window. Extendable to retrieval → LLM filtering/summarization → final call; also applies to filtering RAG context. *posted June 2025 · practice might be outdated*

**For long work sessions, keep the context window small**
and continuously save relevant context externally as you go - model output degrades as context grows (even Gemini degrades past ~100k tokens). Treat context as a curated, persistent asset you re-inject. *posted December 2025 · practice might be outdated*

**Convert courses and knowledge sources into context profiles:**
split by module, extract transcripts, and have an LLM compress each key point into a field containing one instruction or fact. Feeding a raw course in wholesale drowns the model in filler; the compiled profile is an editable, persistent "course" aligning the model with exactly the knowledge you want. *posted August 2025 · practice might be outdated*

**The secret behind viral mega-prompts is not the rules - it's the context-collection window.**
Begin any serious prompt by having the model gather context question by question (an interview) before producing anything; this reliably yields roughly 10x better output. *posted May 2025 · practice might be outdated*

**Personal context database:**
maintain a file covering basic stats, current situation (focus, routine, time, resources, constraints), goals at 3-month/1-year/3-5-year horizons, problems and past obstacles, thinking style, interests, strengths and gaps. Have the AI interview you to fill it, and end sessions by asking it to update the database - plus the companion prompt: "based on this interaction, tell me a few things I may not know about myself that are either beneficial or detrimental to my growth." *posted February 2025 · practice might be outdated*

**Master health context profile:**
a five-phase interview (bloodwork across dates for trends; symptoms/injuries/chronic conditions; weight, activity, sleep, hydration; diet patterns; imaging - MRI, X-ray, ECG, DEXA) compiled into one updateable document with values vs. reference ranges and flagged abnormalities, pasted into any future health question. The pattern generalizes: durable context profiles for any recurring advisory domain. *posted December 2025 · practice might be outdated*
