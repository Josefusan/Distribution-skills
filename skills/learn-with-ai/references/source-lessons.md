Source: https://www.eptwts.com/ai-as-leverage — EP (@eptwts) knowledge base, Chapter 06: AI as Leverage (scraped 2026-09-15). Lessons reproduced verbatim.

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
