---
name: coding-agents-and-knowledge-systems
description: Set up a coding-agent harness and a continuously-fed second brain (Obsidian + Claude Code, drop-folder pipelines, RAG over conversation data, always-on server agent) for an operator, and pick the right model and tool per task. Use when the user says "set up Claude Code for my business", "build me a second brain", "which AI model should I use for X", "should I automate this", "what's the difference between an agent and a workflow", "help me plan before vibe-coding", "my vibe-coded app is a mess", "build an internal tool / dashboard", "make a knowledge base from our Slack", "AI content sounds like slop", or asks which tools (Claude Code, Codex, Hermes, Typefully, Apify, vidIQ, PostHog, Tally) to use for what.
---

# Coding Agents and Knowledge Systems

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill helps an operator turn the terminal into their everything-agent: a second brain that accumulates context, a small set of specialized agents around lucrative tasks, and a model division of labor. Core thesis: the continuously-fed knowledge base is the real edge, not asking ChatGPT questions; and automation only pays when the underlying process is already lucrative and you already know how to do it by hand.

## When to use

- The user wants to adopt Claude Code (or similar) for business work beyond code.
- The user wants a personal/company knowledge base agents can query.
- The user is deciding whether and what to automate.
- The user is about to build something with an agent and has no plan.
- The user asks which model/tool to use for a task.
- The user wants AI-written long-form content that does not read as AI.
- The user asks about EP's tool stack.

## Core principles

**The terminal is becoming the everything-agent.** Coding, marketing, ops, note-taking, payments: anything executable through code should be automated with a coding agent. EP's 2026 80/20: go deep on the Anthropic ecosystem (Claude, Claude Code, its agent tooling) rather than spreading across every tool.

**Know how to do it manually first.** Hand an agent a task you do not understand and it fails in ways you cannot see. Plan the job, let it execute, audit the result.

**Agents and workflows are not interchangeable.** A workflow is a predefined sequence (you reason at design time); an agent reasons about execution itself. An agent can be one step in a workflow. This matters for scoping and pricing.

**Automation only pays on lucrative processes.** Litmus test: if hiring a human assistant would not yet be profitable, an AI assistant will not be either. Skip general-purpose agent hype; build small specialized agents around the few tasks that move the needle.

**Plan, audit, then execute.** One LLM writes the build instructions as markdown, another audits for consistency and efficiency (repeat several times), then the agent builds. Separating planning, verification, and execution catches inconsistencies before code exists.

**Run a second agent for answers that matter.** Different models fail differently; Claude Code plus Codex on the same problem catches the confident-but-wrong answer one alone would ship. There is no best model, only a division of labour.

**The knowledge base that feeds itself is the edge.** An agent scrapes competitors, ad libraries, forums, YouTube, X, podcasts, newsletters; filters into a personal knowledge base; produces a daily report; ties findings to your business context via profiles.

**Ask "best model for this task," never "best LLM."** Chain specialized models. Use the most readable, human-feeling model for human-facing text and stronger reasoning models elsewhere.

**Slop is a user-skill problem.** EP's formula: strong writing-style training data plus fresh, high-quality informational input per piece; keep DMs and one-to-one interaction human. You will not one-shot good copy; you must first teach the model what good copy is.

**Bespoke internal tools beat off-the-shelf.** Prompt a builder for a dashboard that matches your workflow instead of adapting to Notion.

**Instrument the funnel; qualify with forms.** A funnel you have not instrumented is a guess (PostHog session replays change decisions fastest); a short application in front of an offer filters out wasted calls (Tally).

## Workflow

1. **Audit what is worth automating.** List the user's recurring tasks; keep only those tied to revenue the user already performs manually. If nothing qualifies, stop: learn the process or the business first.
2. **Install the harness.** Claude Code as the main terminal agent; Codex as second opinion on high-stakes problems; an always-on agent (Hermes on a VPS, reachable from phone/Telegram) only once there is real work to accumulate.
3. **Build the second brain (Obsidian + Claude Code).**
   - Open the terminal inside the Obsidian vault.
   - Have Claude Code create the structure: `daily/`, `projects/`, `knowledge/`, `resources/`, one main `INDEX.md` for agent navigation, a `CLAUDE.md` with conventions, interlinked concepts, and a single `BRAINDUMP.md` for raw dumps that Claude organizes on command.
   - Seed it: braindump goals, upload chat history, Notion exports, tweet archives; add a skill that always appends new info about the user.
   - Store context profiles (business, ICP, voice) here so every agent reads the same source.
   - Always-on: host on a VPS connected to Telegram (or the team's chat app) so compounding is automatic; or a spare Mac mini keeps it local and lets Claude Code, Codex, and Hermes share it remotely.
4. **Add feed pipelines.**
   - Continuous research: scraper (Apify for X/TikTok/Instagram/YouTube; vidIQ for YouTube search demand) → filter → knowledge base → daily report tied to business profiles.
   - Drop-folder documents: drop scans → vision model (Gemini) transcribes → agent routes facts to the right entity page (one page per entity, an index, relationship links). Applies to any document corpus.
   - Conversation data: export Slack/Telegram JSON → clean, chunk, Q&A-pair → embed → queryable agent (2025 RAG pattern), or simply inject cleaned excerpts when small.
5. **Build with plan → audit → execute.** Write the spec markdown, audit it 2-3 times with a second model, then hand it to the agent. Maintain a flow-diagram skill that auto-updates a visual map of every back-end process on code changes.
6. **Chain tools via MCP** where fresh data or generation is needed: research MCP feeds data, generation MCP renders, the agent orchestrates. Small utilities: Tally forms via API (~30 seconds per form), Typefully API so a script can queue posts.
7. **Assign models per task.** See the division-of-labor table. Run cheap tiered pipelines when cost matters.
8. **Ship content without slop.** Long-form workflow below; humanize every line; never let agents run one-to-one conversations.
9. **Do not vibe-code the landing page.** Use a proper builder (Framer); tapped-in buyers sniff out vibe-coded pages instantly. Instrument everything shipped with PostHog.

## Checklists / templates

### Second-brain scaffold (`CLAUDE.md` starter)

```
# Vault conventions
- Structure: daily/ projects/ knowledge/ resources/; INDEX.md is the entry point; update it when adding notes.
- BRAINDUMP.md: raw input only. On "organize", file each item into the right note, link concepts, clear the dump.
- Profiles live in knowledge/profiles/*.json (business, icp, brand-voice, people). Read the relevant one before any marketing/strategy task; never load all.
- Every session: append new facts about the operator to knowledge/profiles/personal.json.
- Link related concepts with [[wikilinks]]. One entity per page.
```

### Plan → audit → execute

1. "Write complete build instructions for [system] as markdown: architecture, files, steps, edge cases."
2. Second model: "Audit this plan for inconsistencies, inefficiencies, missing steps. Return the corrected plan." Repeat 2-3 times.
3. Agent: "Implement exactly this plan. Maintain `docs/flow.md` (mermaid) showing every back-end process; update it on every code change."

### Model division of labor (EP, 2025-12 → 2026)

| Task | Model |
|---|---|
| Copy, context management, documents, repeatable workflows via skills | Claude |
| Heavy reasoning, very large context, all video/vision analysis | Gemini |
| Quick summarization, basic questions | ChatGPT |
| Trends, anything extractable from X | Grok |

2026 category map: LLMs (Claude, Gemini, GPT, Kimi); coding agents (Claude Code, Cursor, opencode, Lovable); computer-use (Manus, OpenAI/Claude); image (Nano Banana Pro, GPT-Image, Midjourney); video (Veo, Sora, Kling, Seedream); audio (ElevenLabs, Suno); automation (Claude Code, n8n, OpenClaw).

Tiered pipeline: free reasoning model writes instructions → scaffolding tool for bulk → AI IDE for finishing (2025 example: Grok/Kimi → Replit → Cursor).

### Six baseline automation skills

workflow tools (n8n), JSON data structures, prompt engineering, conditional logic, API requests, webhooks. Learn by building what Upwork "AI automation" listings pay for; prototype in n8n, then have a reasoning model teach you to rebuild each workflow in Python.

### Six low-barrier AI skills

LLM proficiency (which model per task), prompt engineering, context management, no-code automation, AI-assisted coding, AI creative work.

### Highest-ROI use cases checklist

- [ ] Delegating repetitive tasks to agents
- [ ] Coding assistance
- [ ] Reasoning steps inside automations
- [ ] Content creation (10x the process even if not fully automated)
- [ ] Marketing: landers, ads, copy
- [ ] Learning assistance
- [ ] Deep research (give it every known specific and let it triangulate)
- [ ] Brainstorming
- [ ] Chatbots on internal knowledge bases

### Long-form copywriting workflow (no slop)

1. Braindump key details into a doc.
2. Generate with a brand-voice profile in context and a skill built on good copywriting practice (teach it first by extracting style from pages you know convert).
3. Constrain: use only the information given, in the structure requested.
4. Skim every line and humanize.

### EP's tool stack (2026)

- Claude Code: main terminal agent; plan, execute, audit.
- Codex: second opinion on the same problem.
- Hermes Agent: always-on, server-hosted, remembers between sessions, reachable from phone.
- Typefully: batch-draft and queue posts; API lets a script post.
- Apify: scrape X/TikTok/Instagram/YouTube for swipe files and reverse-engineering what gets pushed.
- vidIQ: YouTube search volume and competition for high-intent, low-competition keywords.
- PostHog: funnel analytics and session replays.
- Tally: applications, onboarding, lead capture, feedback forms.

## Anti-patterns

- Automating a process you have never done manually or that does not yet make money.
- General-purpose "assistant" agent setups with nothing to automate (EP: Clawdbot hype).
- Handing an agent a task without a plan and audit.
- Vibe-coding blind on complex systems with no flow diagram; vibe-coding the landing page.
- Loading the whole vault into context; navigate via the index and load selectively.
- Choosing one "best LLM" for everything.
- Posting raw AI output; letting AI answer DMs.
- Adapting your workflow to an off-the-shelf tool when a bespoke one is three prompts away.

## Dated / volatile notes

- Six automation skills, free n8n resources (RoboNuggets, Nick Saraev): July 2025. Plan→audit, MCP chaining (Roo Code + Perplexity + ElevenLabs), Slack→LangChain→Pinecone RAG, low-barrier skills, ROI checklist: April 2025. Continuously-fed knowledge base: May 2025. Tiered pipeline (Grok/Kimi → Replit → Cursor): March 2025. Division of labor: December 2025. Deep research anecdote: December 2025. Slop formula: August 2025. Long-form workflow: November 2025.
- Obsidian second brain, drop-folder wiki, Mac mini hosting, 2026 category map, tool stack: 2026.
- Bolt.new + Supabase + DeepSeek dashboard: 2025 example.
- Earlier stack snapshots: 2025-03 Claude/Perplexity/Poe; 2025-04 Gemini/ChatGPT/n8n/Kling/ElevenLabs/Windsurf.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `context-engineering-profiles` (what the vault stores), `learn-with-ai` (learn to code enough), `ai-ugc-video-production` (an automated pipeline example), and `brand-voice-and-authentic-ai-writing`.
