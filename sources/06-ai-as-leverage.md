# Chapter 06: AI as Leverage

Source: https://www.eptwts.com/ai-as-leverage — EP (@eptwts). Scraped 2026-09-15.

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

## Advisor and Self-Analysis Prompts

Default LLMs are dangerous yes-men - you must explicitly prompt for pushback. My library of counter-sycophancy prompts, each with its own distinct structure:

**The "brutally honest strategic advisor"**
(my most viral, ~1.5M views): IQ 180, brutally honest, built billion-dollar companies, expert in psychology/strategy/execution, cares about your success but tolerates no excuses, thinks in systems and root causes. Mission: identify critical gaps, design specific action plans, push past comfort zones, call out blind spots and rationalizations, force bigger thinking, hold you accountable. Response format: hard truth first, then specific actionable steps, ending with a direct challenge or assignment. Bonus: if its thinking exceeds yours, ask it to teach you how to think like it. *posted February 2025 · practice might be outdated*

**The "hyper-rational first-principles problem solver":**
break everything to foundational truths, challenge all assumptions, design interventions at leverage points by impact-to-effort ratio, cut off excuses. Fixed format: situation analysis (core problem, assumptions, first-principles breakdown) → solution architecture (intervention points, action steps, success metrics, risk mitigation) → execution framework (immediate next actions, progress tracking, course-correction triggers, accountability). Constraints: no motivational fluff, no vague advice, no theory without application. *posted March 2025 · practice might be outdated*

**The "brutally honest strategic analyst":**
an expert in behavioral psychology and cognitive biases with zero tolerance for self-deception. Extracts goals with exact metrics and timelines; asks what you actually did in the last 24-48 hours toward each; for every excuse, judges legitimate obstacle vs. rationalization and names the cognitive bias; forces confrontation of goals vs. daily actions, claimed priorities vs. time allocation, perceived vs. actual effort; never accepts vague answers. *posted June 2025 · practice might be outdated*

**The "accountability manipulator":**
questions your memories of "trying hard enough," compares you to an alternate-timeline self who took action, points out inconsistencies in excuses, reframes past failures as proof of capability, refuses sympathy - starts by asking your goals, then systematically dismantles every excuse. *posted April 2025 · practice might be outdated*

**The "Life Optimization Advisor":**
interviews you one question at a time on ultimate goals, hour-by-hour routine, income and spending, relationships, health, and time allocation, challenging every inconsistency; then lists every inefficiency, calculates opportunity cost of wasteful activities, highlights goal-action contradictions, and outputs a measurable plan with schedule optimization, habit protocols, weekly accountability metrics, and consequences. No sugar-coating, no platitudes, no vague answers accepted. *posted April 2025 · practice might be outdated*

**The "life analyzer":**
one question at a time across six phases (physical, mental/emotional, financial, professional, lifestyle, goals), then alignment scores (0-100%) per area, gap analysis, a 30-day/90-day/1-year action plan, systems recommendations, and resource allocation across time, money, energy, and skill development. *posted April 2025 · practice might be outdated*

**The "rational insights" anti-sycophancy system prompt:**
evaluates logical consistency, evidence quality, hidden assumptions, biases, emotional vs. rational reasoning, and causal claims; points out flaws with the specific logical error and a better reasoning path; acknowledges strong reasoning without flattery; calls out fallacies immediately, questions belief sources, encourages steel-manning; prohibits unnecessary politeness, appeals to authority, and vague feedback. *posted June 2025 · practice might be outdated*

**The "pure logic engine" (LogicCore):**
restates your problem stripped of emotional language, asks up to 10 clarifying questions (one at a time) targeting measurable variables and cause-effect, then delivers a core problem statement, causal chain, an IF/THEN solution framework prioritized by implementation speed, resource efficiency, success probability and measurable impact, and a numbered action protocol with success metrics and failure points. *posted March 2025 · practice might be outdated*

**Memory-powered flaw diagnosis:**
a ChatGPT prompt using its stored memory of you in three parts - Diagnosis (one core flaw only, citing specific patterns from memory), Consequences (how it has limited outcomes, referencing past behavior), Prescription (the highest-leverage shift aligned with known goals). Rules: no politeness, brutal clarity over comfort. *posted April 2025 · practice might be outdated*

**Goal-to-checklist ("elite strategic advisor"):**
one question at a time covering end goal, timeline, resources (skills/money/connections/tools), obstacles, success metrics; after 5-7 questions, summarize the goal in one sentence and confirm; then output a nested-checklist roadmap of milestones broken into tasks with dependencies, time and resource estimates, roadblocks with contingencies, and progress metrics. Companion aphorism: if you knew your next 100 actions, you'd do them in a quarter of the time. *posted June 2025 · practice might be outdated*

**Goal-to-system prompt:**
the AI interviews you about what you want, why, what blocks you, and what structure suits you, then designs a system that is specific, includes daily/weekly actions, minimizes decision fatigue, includes tracking, and adapts over time. *posted April 2025 · practice might be outdated*

**Journal profiling:**
feed daily journal entries to a prompt that builds and continuously updates an identity profile (core identity, cognitive patterns, behavioral patterns, emotional landscape, relationships, goals, challenges, strengths), extracting explicit and implicit information, tracking patterns and contradictions, and updating confidence levels over time. *posted March 2025 · practice might be outdated*

**Expert-corpus self-assessment:**
build a context-profile template from a body of expert writing (I used Corporate Machiavelli's 55 essays), have the AI fill it via interview, chat history, or journals, then rate you 1-10 on every measurable value, identify your best-fit fields, and lay out a course of action. Honest answers make it scarily accurate. *posted March 2025 · practice might be outdated*

## Business Strategy Prompts

**Idea backlog analysis:**
dump every idea from your notes app into a prompt that scores each on market potential (1-10), execution complexity (1-10), resource requirements, time to market, revenue streams, risks, and competitive advantage; runs pattern recognition for themes, synergies, and combinations; suggests simplifications and pivots; ranks by profit potential, speed, resource efficiency, and moat; and produces an execution roadmap for the top three. End with: be brutally honest about flaws. *posted March 2025 · practice might be outdated*

**Idea-to-execution blueprint:**
a phased interview (one question at a time, up to 50, flagging critical flaws immediately) through core idea extraction, market/competitor analysis, marketing strategy (content pillars, organic, SEO, paid with budget allocation), execution framework (resources, risks, milestones, KPIs, cash flow, tech stack), and optimization/scaling - outputting an executive summary, 30-60-90 day plan, resource requirements and burn rate, KPIs with break-even analysis, risk assessment, and scaling triggers. *posted March 2025 · practice might be outdated*

**Business-model matcher:**
an interview prompt (one question at a time, max 20, each building on prior answers) across skills, experience, personality and work preferences (risk tolerance, time), and practical constraints (capital, income goals) - outputting 3-5 aligned business models with timelines to profitability, starting requirements, validation steps, and scaling potential. Zero-capital variant: three parts (up to 10 skill questions, up to 5 resource questions), ending with your 3 most valuable skill combinations and the top 2 zero-cost opportunities launchable within 24 hours, each with 5 immediate action steps. *posted May 2025 · practice might be outdated*

**Three-phase market-positioning strategist:**
(1) skill assessment - probe existing specialized skills or guide selection via what you research for fun and where you beat peers, ending with a 90-day learning roadmap; (2) market validation - demand, competition, pricing, service vs. product vs. hybrid; (3) distribution - branch on camera comfort: on-camera path (YouTube/TikTok/Instagram) vs. off-camera path (Twitter threads, newsletter, LinkedIn). Ends with a 30-day action plan and metrics. *posted May 2025 · practice might be outdated*

**"Objective Self-Analysis" for business direction:**
interview across five categories - natural proclivities (what energizes you, flow states), skills (what people pay for and ask your help with), experience (repeated patterns, proven wins), network (who can help, communities), unfair advantages (resources, background, head starts) - producing per-category analysis and a 3-5 sentence summary of your unique edge. *posted July 2025 · practice might be outdated*

**Traffic-strategy interview (Traffic Secrets-based):**
the AI interviews you (product and UVP, ideal customer, current channels, top three traffic challenges, 6-12 month goals), then applies Brunson's frameworks - Dream 100, content distribution across owned and external platforms, hook-story-offer funnels - output as business summary, traffic diagnosis, strategic framework, and a 30-60-90 day plan. *posted March 2025 · practice might be outdated*

**Marketing-strategy interview → JSON:**
four phases (business foundation; positioning and messaging; channels and content; strategy design - customer journey, lead capture, offers, pricing, campaigns), one question at a time, exported as a JSON profile you feed into future prompts or hand to a team. Similar: an ICP interview (ten questions across demographics, values, lifestyle, pains, purchase triggers, price sensitivity, platforms, brand expectations) ending in a reusable ideal-customer JSON with recommended channels, content strategy, messaging, and USPs. *posted April 2025 · practice might be outdated*

**Reddit pain-point research prompt**
(best in deep-research mode): inject product and ICP; generate psychographic search queries in three formats - emotional triggers ("frustrated with", "hate when"), aspirational language ("wish I could"), pain indicators ("anyone else struggle with") - then analyze emotional themes, recurring frustrations, language patterns, intensity via comment engagement, and competing solutions; organize into primary/secondary/emerging pain points with direct quotes, 1-10 intensity scores, frequency, solutions tried, and gaps. *posted May 2025 · practice might be outdated*

**Distribution-channel deep research:**
role of senior market research analyst; inject business context and ICP; forbid speculation; step through where ideal customers spend time online, their frustrations and unmet needs, and highest-ROI organic and paid channels based on real behavior and buyer readiness; output JSON of distribution_channels (name, organic/paid, reason, strategy), audience_touchpoints, audience_painpoints. *posted May 2025 · practice might be outdated*

**Interview → project profile → checklist:**
have the AI interview you about idea and strategy to build a "project profile," feed that into a profile-to-execution-checklist prompt, optionally hand the result to a coding agent as a tracked project checklist. Once the plan exists, the only variable left is execution. *posted March 2025 · practice might be outdated*

**Mine your communication history:**
export chat history with a business partner (Telegram/Slack), have AI write a conversion/cleaning script (Cursor, optimizing for token economy, chunking if needed), then feed it to an LLM to extract every business idea ever discussed - or fill a partner-analysis profile template (communication style, problem-solving approach, decision speed, skills, confidence, delegation, leadership, adaptability) for both parties. Extension: message your partner every idea you have and treat the archive as an AI-queryable second brain - Napoleon Hill's "mastermind third mind" made literal. *posted June 2025 · practice might be outdated*

## Learning with AI

**Stop consuming long-form content raw.**
Most nonfiction is fluff around a few key points; if something can be digested more efficiently with AI, consuming it in full is leisure, not learning. When a book is recommended, first ask an LLM for its chapters with bullets each, then choose what to learn deeply. *posted March 2025 · practice might be outdated*

**The book method (full version):**
don't ask for a whole-book summary - it loses crucial information. (1) Create a personal/business/mindset context profile. (2) Paste one chapter plus the profile into the LLM - one chapter per conversation so nothing gets skipped. (3) For each topic, ask it to explain the theory, convert it into practical applications for your specific situation, and run an interactive questionnaire until you truly understand. Shortcut variant: flick through a book, pick the topic that will benefit you, send just that chapter with your context and ask which concepts apply directly to your life. *posted August 2025 · practice might be outdated*

**The video method:**
pull the transcript (youtubetotranscript or similar) and have an LLM extract key points - or watch with an AI chat open beside the video for instant clarification and personalized applications. Send the transcript, not the video link: a 20-minute video analyzed as video is ~300k tokens; split prompts so each covers one sub-topic. *posted April 2025 · practice might be outdated*

**The "implementation extractor":**
turn any video transcript into a max-10-step action plan - only concrete, immediately executable actions; each step numbered, starting with an action verb; specific numbers/timeframes preserved; all "why" explanations removed; vague steps made specific or deleted. Output: EXECUTION STEPS, KEY METRICS, REQUIRED TOOLS/RESOURCES. *posted March 2025 · practice might be outdated*

**The recursive tutor prompt:**
AI asks what you want to learn, builds a progressive syllabus, and per lesson explains with analogies, asks socratic questions, gives one short exercise, and only proceeds when you're ready - rephrasing if not. Mini-quiz after each section; final integrative challenge plus real-world reflection. Replaces passively watching hours of course video. *posted April 2025 · practice might be outdated*

**The Pareto learning prompt:**
identify the critical 20% of concepts producing 80% of results in any skill; output core concepts with reasoning, what was cut and why, a learning sequence formatted [Concept] - [Resource] - [why this resource] with exactly one vetted, specific resource per concept (never "any YouTube video about X"), practical challenges, and mastery metrics ("you truly understand this when…"). *posted April 2025 · practice might be outdated*

**Deep-learn any resource via an AI IDE:**
put it in Cursor/Windsurf, have the agent extract every practical detail into a hierarchical markdown, then have a chat LLM walk you through it point by point - guaranteeing full coverage instead of skimming. For PDFs too big for a chat context window, the IDE chunks them and can explain each chunk "like you're a smart 12-year-old" into an ordered markdown; merely-large documents fit Gemini's long context directly. *posted March 2025 · practice might be outdated*

**Learn from a proven master, not the model's average:**
pick a person with demonstrated mastery of the skill and make the LLM pull exclusively from their educational content - converting it from mediocre generalist into a specialist with a trusted lens.

**Personalized curriculum project:**
a ChatGPT project with two JSON files - your personal context (what you do, workflow, how you learn) and a curriculum with learned/unlearned booleans. Each session: new chat, run an interactive lesson on the first unlearned item, grounded in your context; update the boolean manually after. Also ask AI for 100 practice projects that would benefit your real work. *posted July 2025 · practice might be outdated*

**Learning-style assessment interview:**
a "behavioral learning strategist" prompt in five phases - situational questions, a format resonance test (one topic explained three ways), a learning-by-doing reflection, pattern-recognition questions, then a structured JSON learning_style profile (dominant/secondary style, input preferences, friction points, optimal self-learning strategy) - assessing observed behavior rather than self-reporting; save it so future explanations are tailored. *posted April 2025 · practice might be outdated*

**Learn to code (enough):**
ask Claude for a learning roadmap, feed it to a coding agent, and have it walk you through each part with practical exercises. Basics take about a week and make you a far better prompter - you can specify technologies and reason about logic. Beginners should not let the agent auto-generate everything: have a chat LLM explain every line you add and why, or you lose grip on the codebase. *posted July 2025 · practice might be outdated*

**RAG-chatbot tutor prompt:**
teaches an absolute beginner the full build - defines "embedding" and "vector store" in plain English, asks what chatbot you want as the running example, then numbered steps (OpenAI embeddings → Pinecone storage → retrieval → GPT generation → commented Jupyter cells) with installation instructions, common-error fixes, current SDK, stopping after every step until you say "continue." *posted July 2025 · practice might be outdated*

**Learn by watching agents:**
give a task to an autonomous agent (e.g., Manus) and watch how it decomposes and solves it - you absorb tool-use patterns by observation. *posted April 2025 · practice might be outdated*

**The no-BS AI curriculum, in order:**
what an LLM is (training, fine-tuning, inference); capabilities vs. limitations (hallucination, bias); model types and best use-cases; context windows and token economy; tools by function and how to find niche ones; tool-chaining; meta-prompting; abstraction prompts for ideation and reasoning prompts for planning; context management and memory architecture; then domain-specific application. Learn fundamentals before building workflows - flows built without them function but are inefficient. Pareto framing: decide if you're an engineer or an operator; operators (99% of people) skip the mathematical internals entirely. *posted June 2025 · practice might be outdated*

**Four learning paths**
(sample all, then specialize): general foundations (LLM mechanics, token economy, context management, prompt engineering, RAG/embeddings/vector DBs, MCP); creative (multimodal capabilities per model, style profiles, image/video/sound tools, tool-chaining); automation (n8n/Make/Zapier, JSON, triggers/actions/APIs, error handling); vibe-coding (coding LLMs by power vs. cost, AI IDEs, breaking projects into step-goals, debugging, front-end tools like v0/Tailwind/shadcn). *posted May 2025 · practice might be outdated*

## Image Generation and Visual Content

**JSON style profiles are the master technique:**
feed reference images (ads, thumbnails, brand assets) to a model and have it extract the stylistic qualities - color palette, composition, character style, typography, textures, lighting, motifs, post-processing - into a structured JSON documenting only the design system, explicitly excluding specific subjects, logos, people, or brand names. Reuse the profile to generate new on-brand visuals for entirely different content; edit or merge profiles as needed. Variants: thumbnail profiles, brand-kit profiles for new products, and reusable "filter profiles" (extract the look, apply to a new image, iteratively ask it to update named qualities, save as a customizable filter). *posted March 2025 · practice might be outdated*

**Separate style from composition for maximum control:**
combine a JSON style profile with a rough visual layout - dump relevant PNGs into Canva/Photoshop/MS Paint arranged roughly as you want, export, and send the layout plus the JSON with "turn this into a finished image based on the profile." Far more control than any text prompt alone. *posted March 2025 · practice might be outdated*

**Sketch-to-finished-graphic:**
a hand-drawn sketch plus one structured prompt (set resolution, correct specific elements - "make the dollar bill a real $100 bill," remove labels, "let your creativity run wild but follow the instructions on the thumbnail") produces finished thumbnails; you can write instructions directly on the sketch. Current (2026) tool: Nano Banana Pro (run via Freepik with quality up) - extracts individual elements from existing thumbnails, turns paper sketches into finished logos/graphics, near-replacing thumbnail designers. *posted December 2025 · practice might be outdated*

**Prompt for imperfection to get realism:**
name a low-end camera, casual context, and explicitly ask for a noisy, authentic, non-cinematic look - e.g., "taken from an iPhone 6… noisy and look authentic not cinematic, this photo was lazily taken in the November cold." Polished defaults are what give AI away. *posted March 2025 · practice might be outdated*

**4o image-gen weaknesses and workarounds**
(2025-03): faces drift toward uncanny near-likenesses - train Flux on 5+ photos of your own face (krea.ai/train) for near-1:1 self-images; color grading biases orange/red - specify colors explicitly; text breaks - spell out exact text in the prompt; glitches - repair with Photoshop generative AI. Locked aspect ratios: add black bars to your sketch (62px bars yield exact 16:9), generate between them, crop after. Refused prompts: run the identical prompt through Sora - same image model, more lenient filtering. *posted April 2025 · practice might be outdated*

**Static-ad interview prompt:**
a legendary direct-response marketer persona gathers product, ideal customer, #1 problem solved, guarantee/USP, headline benefit and style (problem/benefit/question/direct), proof points, exact CTA, mood, visual style, and brand colors - then outputs an art-director brief (scene composition, lighting, camera angle, headline placement, text hierarchy, text-to-image balance) ready for an image model. *posted March 2025 · practice might be outdated*

**Adaptive image-interview prompt:**
before generating, the AI extracts the image in your head one question at a time, adapting by subject type (person → pose/expression/clothing; scene → perspective/time of day/weather) plus style, technical, mood, and use questions - wrapping within ~10 questions into a structured generation prompt. *posted April 2025 · practice might be outdated*

**Process infographics from one prompt:**
image models can generate complete step-by-step recipe/process infographics - specify view angle, layout, labels with exact quantities, connecting dotted lines with icons, and a final shot. Specificity is what makes it work. Chain tools for data-driven graphics: Perplexity extracts structured facts, ChatGPT renders them with formatting instructions ("1:1 grid, each time-slot its own box, no spelling mistakes"). *posted March 2025 · practice might be outdated*

**UI cloning with Claude Code (2026):**
Claude cannot extract accurate styling from screenshots alone but replicates given CSS very well. (1) Open dev tools on a UI you admire; copy the full CSS plus a screenshot. (2) "Rebuild the exact same UI design as the screenshot in a single html file, css attached." (3) Use VisBug to copy per-element CSS until pixel-perfect. (4) Have Claude generate a detailed style-guide markdown (palette, typography, spacing system, component styles, shadows, animations, radii, Tailwind usage, example components). (5) Drop that style guide into any project and Claude one-shots new pages in that style, even across context resets.

**One-shot branded decks (2026):**
paste content into Claude, invoke the pptx skill, attach a brand-style context profile - finished on-brand PowerPoint in a single prompt. *posted January 2026 · practice might be outdated*

## AI Video and UGC Production

**The 2025 pipeline (dated):**
Flux 1.1 Pro Ultra for images to animate, Kling for animation, chaining ~10-second clips since nothing longer was economical. For storyline consistency, have an LLM write the sequential image prompts following the storyline, generate each image, then animate each. By 2026 the stack moved to Seedance 2.5 / Veo / Sora for video and Nano Banana Pro / GPT-Image for frames.

**Seedance 2.5 honest assessment (2026-08):**
shockingly realistic - near-solved realism for UGC - and excellent at following instructions, but expensive (~$5 per 17-second clip, ~$10 per 30 seconds; get the prompt right so you one-shot it) and still bad at rendering text - add captions and overlays yourself in an editor.

**AI UGC works commercially:**
AI-generated UGC passes as real to roughly 80% of viewers, collapsing creative costs. Platform risk is low: TikTok's parent built Seedance and Meta ships AI creative tools - they will not ban AI content. And for openly-AI entertainment content, the viral secret is the opposite of hiding it: make it as absurd and obviously AI as possible ("no way this is real") - audiences accept fantasy like they accept VFX.

**The clone-a-winner assembly line (2026-08, my flagship workflow):**
(1) give your agent a short-form content research API and pull ~100 videos promoting products like yours; (2) pick one that fits; (3) have the agent extract ALL context via a video-analysis tool (Higgsfield CLI has one built in) into a structured markdown - scenes, motions, appearance, mannerisms, accents, tone; (4) generate candidate starting frames via the CLI and pick the best; (5) rewrite the context so it promotes YOUR product; (6) send rewritten context plus starting frame to Seedance 2.5. I get ~80% first-try success. Ten-minute variant: research agent finds references → Gemini 2.5 Flash produces a scene-by-scene analysis with image-reference placeholders → GPT-image-2 recreates a frame per cut-scene → Higgsfield video generation with Seedance → human editor adds captions, cuts, zooms, music.

**Fully automated viral-video cloning with Claude Code:**
query a TikTok research API for a niche filtered to 100k+ views, outliers, and sales intent; one project folder per video; download with yt-dlp; PySceneDetect splits scenes at hard cuts; ffmpeg grabs each scene's start frame ~0.08s past the cut (avoiding transition motion blur) plus mid/end frames; Gemini API analyzes hook, pacing, structure, and why it converts as structured JSON; Claude Code writes one generation prompt per scene; each start frame + prompt goes to Seedance image-to-video.

**Segment-assembly UGC:**
realistic UGC videos are chains of 4-8 second clips, each from a starting-frame image plus a short prompt. Get frames by screenshotting real TikTok UGC and having an image model change the person's appearance; prompt template: "extend this video and make her say this (make sure she is very expressive and enthusiastic): {script}". Expect a few generations per segment; compile in CapCut. Avatar-tool alternative (makeugc): input script, pick or create an avatar (including product-in-hand), iterate on script and tone - good enough to run as traffic creatives.

**The green-screen format:**
generate a still of a presenter in the bottom corner with a green screen behind them (prompt for organic, hand-held, imperfect quality), animate with Seedance 2.5 plus the script, then chroma-key any screenshot in as the background - endlessly reusable for selling almost anything.

**Anatomy of a professional AI video prompt**
(from Higgsfield's open-sourced packs): style prefix (film stock, lens, color grading, director-style camera language); shot-mode declaration (multi-shot montage, hard cuts); image references with explicit identity/wardrobe locks; a global consistency-lock section (what must never change between shots); diegetic sound and lip-synced dialogue per shot; per-shot camera and framing direction; and a long negative-prompt list (no watermark, no wardrobe change, no lip-sync drift, no morphing). Copy the scaffold. Career path: study these open-sourced packs, practice in Cinema Studio, make trend-tied shorts, network with AI filmmakers - corporate deals in the space are large.

**Gemini is the video-analysis model, full stop.**
Google has by far the best vision model regardless of benchmarks (it deciphers 200-year-old Kurrentschrift handwriting other models fail on) - judge multimodal models by hard real-world tests, not leaderboards. Gemini sees a YouTube video's actual visuals (and Google-private data), not just the transcript like Perplexity. Non-YouTube videos (reels, TikToks, VSLs): rip the file and upload to a private YouTube account, then feed the link. Screen recordings work too - it extracts structured data from any on-screen workflow. Limit: ~2 hours of video floods the context window; chunk into 1-2 hour segments (use AI Studio for this). At scale: give Claude a Gemini 2.5 Flash API key - I analyzed over 1 million videos this way for about $140 total.

**Gemini editing workflows:**
extract an "editing-style profile" JSON from a well-edited reference video, upload your raw footage to a private YouTube account, and ask for a breakdown of cuts, VFX, and transitions with exact timestamps - or use the profile as a manual that makes a human editor faster and cheaper. Retention reverse-engineering: extract shot-by-shot profiles (script, visuals, SFX, mood) from successful videos, ask Gemini for the key retention strategies, build a profile of your own channel, and request an implementation manual. Wrapper opportunity: Gemini video-analysis apps are far less crowded than image-gen wrappers because even daily AI users don't know Gemini processes visuals. *posted April 2025 · practice might be outdated*

**Articles → video scripts:**
scrape articles with Firecrawl, extract a "script profile" from a proven video in your niche (pacing, storytelling, retention), then have an LLM write a script pulling information from the articles in the style of the profile. Automatable via the Firecrawl MCP server. *posted April 2025 · practice might be outdated*

**Scaling expert content without cloning the expert:**
put the expert's wisdom into a knowledge base, build an AI system that pulls topics from it to generate scripts, then hire and train human presenters - multiple lead-generating channels hands-off (recommended in 2025 over full AI presenters, which weren't convincing yet). *posted May 2025 · practice might be outdated*

## Coding Agents, Automation, and Knowledge Systems

**The terminal is becoming the everything-agent.**
Coding, marketing, ops, note-taking, payments - anything executable through code should be automated with a coding agent. My 2026 80/20: get deeply familiar with the Anthropic ecosystem (Claude, Claude Code, and its agent tooling) rather than spreading across every new tool.

**Agents vs. workflows - not interchangeable:**
a workflow is a predefined sequence of steps (you do the reasoning at design time); an agent takes a task and reasons about execution itself (you outsource the reasoning). An agent can be one step inside a workflow. Important when scoping and pricing automation projects.

**Automation only pays when the underlying process is already lucrative.**
Skip general-purpose agent setups (e.g., Clawdbot hype); build small specialized agents around the few tasks that actually move the needle. Litmus test for always-on assistants: if hiring a human assistant wouldn't yet be profitable for you, an AI assistant won't be either - beginners with nothing to automate gain nothing from automation tools.

**AI automation needs only six baseline skills:**
workflow tools like n8n, JSON data structures, prompt engineering, conditional logic, API requests, and webhooks - after which you can charge companies thousands to build agents. Learn market-relevant projects by browsing Upwork's "AI automation" listings and building what businesses actually pay for; every practice project becomes a portfolio piece. Free n8n resources: RoboNuggets' videos and Nick Saraev's free 6-hour YouTube course. Graduation path: prototype in n8n to learn workflow logic, then have a reasoning model break each workflow down node by node and teach you to rebuild it in Python - production agents need the control only code provides. *posted July 2025 · practice might be outdated*

**Plan, audit, then execute:**
before building with a coding agent, have one LLM write the full build instructions as markdown, have another LLM audit the file for consistency and efficiency (repeat the audit several times), then hand it to the agent. Separating planning, verification, and execution catches inconsistencies before any code is written. *posted April 2025 · practice might be outdated*

**Vibe-coding guardrails:**
for complex systems, have your agent maintain a visual flow diagram of every back-end process, with an agent skill that auto-updates it whenever code changes - a middle ground between reading all generated code and going blind, and it makes collaboration ~10x easier. And don't vibe-code your landing page: tapped-in buyers instantly sniff it out; use a proper builder like Framer.

**MCP tool-chaining:**
research MCP feeds fresh data, generation MCP renders output, the agent orchestrates - e.g., Roo Code + Perplexity MCP + ElevenLabs MCP producing automated voiceovers with real-time researched data (2025-04 example; the pattern generalizes). *posted April 2025 · practice might be outdated*

**Conversation data → custom agent (2025 RAG pipeline):**
export Slack data as JSON (and dump ChatGPT's knowledge of your business as JSON); use Cursor with a long-context model to write a LangChain script that cleans (strips filler), chunks, and converts to Q&A pairs; embed with OpenAI embeddings into Pinecone; wrap as a LangChain agent and deploy. Tip: paste the outline into an LLM and have it walk you through each step. *posted April 2025 · practice might be outdated*

**The continuously-fed knowledge base is the real edge**
- not asking ChatGPT questions. An agent that scrapes relevant sources (competitors, ad libraries, forums, YouTube, X, podcasts, newsletters), filters into a personal knowledge base, produces a daily report, and ties findings to your business context via profiles - queryable directly instead of relying on training data. *posted May 2025 · practice might be outdated*

**The Obsidian + Claude Code second brain (2026):**
open the terminal inside Obsidian and have Claude Code create an Obsidian-optimized structure (daily notes, projects, knowledge, resources), one main index for agent navigation, a CLAUDE.md with conventions, interlinked concepts, and a single BRAINDUMP.md where you dump raw info that Claude organizes on command. Always-on version: host an agent on a VPS, connect it to Telegram, and have it build and maintain the vault around your entire life - agentically searchable, with a skill that always appends new info about you, seeded by braindumping goals and uploading chat history, Notion databases, and tweet archives. Put the agent inside the chat app where your team already communicates so the compounding is automatic. Hosting option: a spare Mac mini keeps the knowledge base local, letting every agent (Claude Code, Codex, Hermes) access the same centralized information remotely under your control.

**Drop-folder document pipelines:**
my private family wiki in Claude Code - drop scanned documents, Gemini vision transcribes them (including 120 pages of old German Kurrentschrift and cursive Cyrillic), and the agent routes extracted facts into the correct person's markdown page (one page per person, an index, a family-tree.md with relationship links). Once populated, it can one-shot a printable family-history book. The drop-folder → vision-transcribe → route-to-entity architecture applies to any document corpus.

**Bespoke internal tools beat off-the-shelf:**
instead of adapting to Notion, prompt an AI builder to generate a dashboard customized to your exact workflow - my 2025 example: Bolt.new + Supabase + a DeepSeek API key produced a working board in about three prompts. Micro-SaaS extension: build a tool that fixes a problem you personally have, paywall it with a free trial, and market it with screen-recorded short-form videos of the tool in action. Small utility example (2026): Tally for forms because its API lets an agent generate a complete form in ~30 seconds.

## Model and Tool Selection

**"What is the best LLM?" is the wrong question**
- ask which model is best for a specific task, and chain specialized models rather than committing to one. Benchmark intelligence isn't the only criterion: use the most readable, human-feeling model for human-facing text and stronger reasoning models elsewhere.

**My division of labor (2025-12 → 2026):**
Claude for writing copy, context management, documents, and repeatable workflows via skills (most intuitive for context profiles); Gemini for heavy reasoning, very large context, and all video/vision analysis; ChatGPT for quick summarization and basic questions; Grok for researching trends or anything extractable from X. (Earlier snapshots for reference: 2025-03 - Claude for copy, Perplexity for research, Poe at ~$20/month for credit-based access to all major LLMs without daily caps; 2025-04 - Gemini as main LLM, ChatGPT for images, n8n for automation, Kling for video, ElevenLabs for sound, Windsurf for coding.) *posted December 2025 · practice might be outdated*

**The 2026 category map**
(know the current best per category, not every release): LLMs - Claude, Gemini, GPT, Kimi. Coding agents - Claude Code, Cursor, opencode, Lovable. Computer-use agents - Manus, OpenAI/Claude. Image - Nano Banana Pro, GPT-Image, Midjourney. Video - Google Veo, Sora, Kling, Seedream. Audio - ElevenLabs, Suno. Automation - Claude Code, n8n, OpenClaw. Claude Code alone covers many categories when plugged into the right tools.

**Cheap tiered pipelines:**
use a free reasoning model to write instructions, a scaffolding tool for the bulk, and an AI IDE for finishing (2025 example: Grok/Kimi → Replit → Cursor) - each tool where it's strongest, cost minimized. *posted March 2025 · practice might be outdated*

**Six low-barrier AI skills anyone can build:**
LLM proficiency (which model per task), prompt engineering, context management, no-code automation, AI-assisted coding, and AI creative work (style profiles, brand-voice copy, image/video/audio tools). *posted April 2025 · practice might be outdated*

**The highest-ROI AI use cases, as a checklist:**
delegating repetitive tasks to agents; coding assistance; reasoning steps inside automations; content creation (10x the process even if not fully automated); marketing (landers, ads, copy); learning assistance; deep research; brainstorming; chatbots on internal knowledge bases. *posted April 2025 · practice might be outdated*

**Deep research is genuinely powerful:**
Gemini Deep Research scraped ~200 websites from a 50-word prompt and identified a half-forgotten WW2-era family figure, down to living relatives, in 5 minutes. Pattern: give it every known specific and let it triangulate. Gemini is also remarkably good at deciphering old handwritten documents - least hallucination in my testing, unlocking hundreds of genealogical records. *posted December 2025 · practice might be outdated*

## AI Content Without the Slop

**"AI slop" is a user-skill problem, not a model problem.**
Several highly respected X accounts run roughly 80% AI-generated content undetected. My formula: strong writing-style training data plus fresh, high-quality informational input per piece - but keep DMs and genuine one-to-one interactions human. *posted August 2025 · practice might be outdated*

**The long-form copywriting workflow:**
braindump key details into a doc, let AI fill gaps and handle formatting with a brand-voice profile in context, then skim every line and humanize. Claude-skill version: dump your bullet-point draft as context, generate with a skill built on good copywriting practices, constrain the model to use only the information you gave in the structure you request, then humanize. You will not one-shot good copy - and the system only works if you first teach the model what good copy is (e.g., extract style from landing pages you know convert). Copywriters claiming AI can't replicate their style are coping: instructing AI well is itself a writing skill. *posted November 2025 · practice might be outdated*

## Adjacent Tool Picks (early, dated)

**2024 endorsements:**
Simple Analytics over Google Analytics for lean online businesses; ElevenLabs as the most useful SaaS I'd used; Framer for landing pages; the "Control Panel for Twitter" extension to remove the algorithmic For You tab. *posted December 2024 · practice might be outdated*

**Google-dork lead generation:**
search site:linkedin.com {occupation} {area} @gmail.com to surface people in a role and city who list an email publicly - an instant free outreach list. *posted July 2024 · practice might be outdated*

**US TikTok For You page from abroad (2024):**
either a US SIM + fresh US Apple ID + US 4G proxy connected via PC hotspot dongle (never connect the phone directly to the proxy - TikTok detects it; VPNs don't work), or simply rent remote control of a physical US phone for ~$130/month. *posted August 2024 · practice might be outdated*
