---
name: learn-with-ai
description: Learn any book, video, PDF, course, or skill faster with AI by extracting only what applies to your situation, running interactive tutoring, and building personalized curricula. Use when the user says "summarize this book / video for me", "I don't have time to read this", "teach me X", "what's the 20% of X I actually need", "help me learn to code enough", "build me a curriculum", "what should I learn about AI", "how do I learn AI automation / vibe coding", or shares a transcript, PDF, or resource and asks what to do with it.
---

# Learn With AI

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill helps you convert any learning resource into personalized, applied understanding instead of passive consumption. Core thesis: most nonfiction is fluff around a few key points; if something can be digested more efficiently with AI, consuming it in full is leisure, not learning. Feed the resource plus your context, extract what applies, and practice interactively.

## When to use

- The user has a book, video, podcast, PDF, or course and limited time.
- The user wants to learn a skill and does not know where to start.
- The user wants to learn to code, build automations, or use AI tools properly.
- The user keeps consuming content without implementing.
- The user wants a tutor that adapts to how they learn.
- The user asks for a summary (redirect to the chapter/transcript methods).

## Core principles

**Stop consuming long-form content raw.** When a book is recommended, first ask an LLM for its chapters with bullets each, then choose what to learn deeply.

**Never ask for a whole-book summary; it loses crucial information.** Work one chapter per conversation with your context profile attached, so nothing gets skipped.

**Send the transcript, not the video link.** A 20-minute video analyzed as video is ~300k tokens; split prompts so each covers one sub-topic.

**Strip the why, keep the actions.** The implementation extractor turns any transcript into a max-10-step plan: action verbs, specific numbers, no explanations, vague steps deleted.

**Learn from a proven master, not the model's average.** Make the LLM pull exclusively from one person's educational content; it turns a mediocre generalist into a specialist with a trusted lens.

**Pareto everything.** Identify the 20% of concepts producing 80% of results, with exactly one vetted resource per concept, never "any YouTube video about X."

**Personalize with context.** A learning-style profile (assessed by behavior, not self-report) plus a personal context JSON makes every explanation land.

**Learn to code enough, in about a week.** It makes you a far better prompter. Beginners must not let the agent auto-generate everything; have a chat LLM explain every line or you lose grip on the codebase.

**Fundamentals before workflows.** Flows built without fundamentals function but are inefficient. Decide if you are an engineer or an operator; operators (99% of people) skip the mathematical internals.

**Sample all four learning paths, then specialize.** General foundations, creative, automation, vibe-coding.

## Workflow

1. **Identify the resource type and the user's goal.** What do they want to be able to do afterward? Build or fetch their personal/business context profile first (see `context-engineering-profiles`).
2. **Route by resource:**
   - Book → ask for chapter list with bullets; pick chapters; run the Book Method one chapter per conversation. Shortcut: pick the single relevant chapter and ask which concepts apply directly.
   - Video/podcast → pull the transcript; run the Video Method (key points, split by sub-topic) or the Implementation Extractor for an action plan.
   - Large PDF/course → Deep-Learn via AI IDE: agent extracts every practical detail into hierarchical markdown, then a chat LLM walks through it point by point. Merely-large docs fit Gemini's long context directly.
   - A skill with no resource → Pareto Learning Prompt to find the 20% and one resource per concept; or Learn From a Master by naming a proven practitioner.
   - Ongoing study → Personalized Curriculum Project (context JSON + curriculum JSON with learned booleans); ask for 100 practice projects relevant to real work.
3. **Run the Learning-Style Assessment once** and save the JSON so future explanations are tailored.
4. **Teach interactively.** Use the Recursive Tutor: syllabus, analogies, socratic questions, one exercise, proceed only when ready, mini-quiz, final integrative challenge.
5. **Convert to practice.** Every session ends with an implementation list or exercise; if the topic is coding, feed the roadmap to a coding agent and have it walk through exercises.
6. **For learning AI itself,** follow the no-BS curriculum order below, then pick a path.

## Checklists / templates

### Book Method

```
Context: [paste personal/business/mindset profile].
Here is one chapter: [paste].
For each topic in this chapter: (1) explain the theory; (2) convert it into practical applications for my specific situation; (3) run an interactive questionnaire, one question at a time, until I truly understand it.
```
Shortcut: "Here is the one chapter I think matters plus my context. Which concepts apply directly to my life, and how?"

### Video Method

```
Here is the transcript of [video] (sub-topic 1 of N): [paste].
Extract the key points. For each, give a personalized application for my situation: [context].
```

### Implementation Extractor

```
Turn this transcript into an action plan of at most 10 steps. Only concrete, immediately executable actions. Each step numbered and starting with an action verb. Preserve specific numbers and timeframes. Remove all "why" explanations. Make vague steps specific or delete them.
Output sections: EXECUTION STEPS; KEY METRICS; REQUIRED TOOLS/RESOURCES.
```

### Recursive Tutor

```
Ask me what I want to learn. Build a progressive syllabus. For each lesson: explain with analogies; ask socratic questions; give one short exercise; only proceed when I say I am ready, and rephrase if I am not. Mini-quiz after each section. End with a final integrative challenge plus a real-world reflection.
```

### Pareto Learning Prompt

```
For the skill [X], identify the critical 20% of concepts that produce 80% of results.
Output: core concepts with reasoning; what you cut and why; a learning sequence formatted [Concept] - [Resource] - [why this resource], with exactly one vetted, specific resource per concept (never "any YouTube video about X"); practical challenges; mastery metrics phrased "you truly understand this when...".
```

### Deep-Learn via AI IDE

1. Put the resource in Cursor/Windsurf (or Claude Code).
2. "Extract every practical detail into a hierarchical markdown. For PDFs too big for one window, chunk and explain each chunk like I'm a smart 12-year-old, ordered."
3. Chat LLM: "Walk me through this markdown point by point; do not skip anything."

### Learn From a Master

```
Pull exclusively from [named practitioner]'s educational content on [skill]. Do not use general advice. Teach me their approach to [problem].
```

### Personalized Curriculum Project

Two JSON files: `personal_context.json` (what I do, workflow, how I learn) and `curriculum.json` (items with `"learned": false`). Each session: new chat, "run an interactive lesson on the first unlearned item, grounded in my context"; flip the boolean after. Also: "Give me 100 practice projects that would benefit my real work."

### Learning-Style Assessment

```
You are a behavioral learning strategist. Five phases: (1) situational questions; (2) format resonance test: explain one topic three different ways and ask which landed; (3) a learning-by-doing reflection; (4) pattern-recognition questions; (5) output a JSON learning_style profile: dominant style, secondary style, input preferences, friction points, optimal self-learning strategy. Assess observed behavior, not self-report.
```

### Learn to Code (enough)

1. Ask Claude for a learning roadmap for [goal].
2. Feed it to a coding agent: "walk me through each part with practical exercises."
3. Rule: for every line I add, explain what it does and why.

### RAG-Chatbot Tutor

```
Teach me, an absolute beginner, to build a RAG chatbot. Define "embedding" and "vector store" in plain English. Ask what chatbot I want as the running example. Then numbered steps: OpenAI embeddings → Pinecone storage → retrieval → GPT generation → commented Jupyter cells, with installation instructions, common-error fixes, and the current SDK. Stop after every step until I say "continue."
```

### No-BS AI curriculum (in order)

1. What an LLM is (training, fine-tuning, inference)
2. Capabilities vs. limitations (hallucination, bias)
3. Model types and best use cases
4. Context windows and token economy
5. Tools by function and how to find niche ones
6. Tool-chaining
7. Meta-prompting
8. Abstraction prompts for ideation, reasoning prompts for planning
9. Context management and memory architecture
10. Domain-specific application

### Four learning paths

- General foundations: LLM mechanics, token economy, context management, prompt engineering, RAG/embeddings/vector DBs, MCP.
- Creative: multimodal capabilities per model, style profiles, image/video/sound tools, tool-chaining.
- Automation: n8n/Make/Zapier, JSON, triggers/actions/APIs, error handling.
- Vibe-coding: coding LLMs by power vs. cost, AI IDEs, breaking projects into step-goals, debugging, front-end tools (v0/Tailwind/shadcn).

## Anti-patterns

- Whole-book summaries.
- Sending a video link instead of a transcript, or one giant prompt for a whole video.
- Learning without a context profile attached, so applications stay generic.
- Letting a coding agent auto-generate everything while a beginner.
- Vague resources ("watch some videos on X").
- Building automation workflows before learning fundamentals.
- Learning the model's average take instead of a proven master's.

## Dated / volatile notes

- Stop consuming raw, implementation extractor, deep-learn via IDE: March 2025. Video method, recursive tutor, Pareto, learning-style, watching agents (Manus): April 2025. Four paths: May 2025. No-BS curriculum: June 2025. Curriculum project, learn to code, RAG tutor: July 2025. Book method: August 2025. All flagged "practice might be outdated."
- Tool names (youtubetotranscript, Cursor/Windsurf, Pinecone, Manus, v0) are 2025 snapshots.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `context-engineering-profiles` (convert courses into profiles), `prompting-techniques`, and `coding-agents-and-knowledge-systems`.
