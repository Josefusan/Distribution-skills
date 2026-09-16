Source: https://www.eptwts.com/ai-as-leverage — EP (@eptwts) knowledge base, Chapter 06: AI as Leverage (scraped 2026-09-15). Lessons reproduced verbatim.

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

Source: https://www.eptwts.com/tools-i-use — EP (@eptwts) knowledge base, Chapter 08: Tools I Use (scraped 2026-09-15). Lessons reproduced verbatim.

## Coding Agents

**Use Claude Code**
What I use it for. My main agent in the terminal: building products, ripping and rebuilding workflows, and automating anything I already know how to do by hand.
The terminal is becoming the everything-agent, and this is the one I live in. It is not a code tool, it is a leverage tool: I plan the job, let it execute, then audit the result. The rule that keeps it useful is knowing how to do the thing manually first. Hand an agent a task you do not understand and it fails in ways you cannot see.

**Use Codex**
What I use it for. The second opinion. I run it alongside Claude Code on the same problem when the answer actually matters.
Different models fail differently. Running two agents on the same task and comparing what comes back catches the confident-but-wrong answer that one alone would have shipped. There is no best model, only a division of labour.

**Use Hermes Agent**
What I use it for. The always-on agent. It lives on a server instead of my laptop, keeps its memory between sessions, and I reach it from my phone.
Every other agent forgets you the moment the session closes. This one accumulates: it builds skills from what it has already done and keeps a model of how I work, so it gets more useful the longer it runs. Decoupling where it runs from where I talk to it is the real unlock: the work happens on a cheap box while I am on the move.

## Social Media Tools

**Use Typefully**
What I use it for. Writing, scheduling, and queueing posts, plus the API I hit when I want the pipeline to post for me.
Volume compresses timelines, and you cannot run volume if every post has to be typed live. I draft in batches, queue them, and the account keeps running whether or not I am at a desk. The API is the part that matters most: it turns posting into something a script can do, which is the whole game once the content process is figured out.

**Use Apify**
What I use it for. Scraping social platforms: pulling posts, profiles, and engagement data off X, TikTok, Instagram and YouTube at scale.
Algorithms are learnable rules, and you cannot reverse engineer what gets pushed without the data in front of you. Scraping the accounts that already win in a niche turns a guess about what works into something you can count. It is also the input for everything downstream: swipe files, content pipelines, and knowing which offers a niche actually spends on.

**Use vidIQ**
What I use it for. YouTube search tracking: finding the keywords people actually search and how much competition sits on each one.
Search traffic on YouTube converts several times better than recommendations, because someone typing the query has already told you what they want. The whole play is finding low-competition, high-intent keywords and putting a VSL-structured video on each one, and that starts with knowing what the search volume actually is instead of guessing at titles.

## Analytics

**Use PostHog**
What I use it for. Product and funnel analytics on everything I ship: where traffic lands, where it drops, and what people actually do before they buy.
Success comes down to identifying the metrics that matter and then tracking and optimising them, and a funnel you have not instrumented is a funnel you are guessing about. Session replays are the part that changes decisions fastest: watching someone abandon a page tells you more in thirty seconds than a week of theorising about copy.

## Forms

**Use Tally**
What I use it for. Every form I put in front of people: applications, onboarding questions, lead capture, feedback.
Forms are the cheapest way to qualify people before they reach you. Tally builds one in minutes, looks like it belongs on the page instead of a corporate survey tool, and does not charge for the fields that matter. A short application in front of an offer filters out most of the people who would have wasted the call.
