---
name: context-engineering-profiles
description: Build, store, and stack reusable JSON context profiles (business, ICP, brand voice, marketing strategy, personal context) so every AI session starts with your situation instead of from zero. Use when the user says "the AI output is generic", "ChatGPT doesn't know my business", "how do I give Claude context", "set up a business profile / brand voice / ICP", "make a Claude skill for my company", "should I use ChatGPT memory", "my context window is full", "turn this course into something the AI can use", or is about to run any serious marketing/strategy/copy prompt without a stored profile. Also trigger when the user asks how to be "good at AI" or whether a newer model would fix their results.
---

# Context Engineering Profiles

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill helps you turn everything an LLM cannot know about you (your business, customers, voice, goals) into small, structured, reusable profiles you inject into any prompt in one action, and to stack them with task-specific instructions. Core thesis: AI multiplies whatever you already are, and prompt engineering is primarily a game of storing and reusing context. Output quality with vs. without profiles is "night and day - like overclocking your LLM."

## When to use

- AI output feels generic, obvious, or wrong for the user's specific business.
- The user is starting a new marketing, strategy, copy, or planning session and has no stored context to paste in.
- The user asks whether to rely on ChatGPT memory, GPT projects, RAG, or Claude skills for standing context.
- The user has a course, transcript, book, or SOP they want the AI to "know".
- The user's long session is degrading (model forgetting, repeating, drifting).
- The user wants a personal-development or advisory AI that actually knows their situation.
- The user believes a newer model is the fix for bad results.

## Core principles

**AI multiplies whatever you already are.** Give the same model to an average Fiverr copywriter and to David Ogilvy and Ogilvy wins. Prompting is transferring your skill into words; you cannot instruct a model to embody a skill you do not possess. Being "good at AI" means exactly two things: feeding it your domain knowledge and prompting it to emulate your skills.

**A better model makes zero measurable difference for 99% of people.** If current tools are not enough to build a cash-flowing business, the bottleneck is the operator, not the model (EP, 2026-06). Fix context and instructions before chasing releases.

**Design around the four structural bottlenecks.** (1) Every new chat starts from zero, so store reusable context profiles. (2) No intuition, only predefined data. (3) No true creativity, only remixing training data or your context, so novel ideas come from you. (4) Confident hallucination, so verify claims. On contested topics feed multiple sources yourself instead of trusting base training data.

**Context is two buckets: facts the model doesn't know, and instructions on how to use them.** Categorize and retrieve selectively. Never dump wholesale; the fuller the context window, the worse the output.

**JSON is for storing context, not for prompting.** JSON is modular, editable, mergeable, and token-dense, so the model can reference the right field without ingesting paragraphs. Write the actual prompt in plaintext or XML and inject JSON profiles where needed. "JSON prompting" was never magic; its real benefit was navigable templates with swappable variables.

**Build the business profile once (1-2 hours) and reuse forever.** Fill it by having the LLM interview you, not by typing it out; interviews surface more accurate data than self-description. Most of the time simple context injection beats building a RAG system.

**Stack profiles for hyper-specific advice.** Business + ICP + brand voice compound; offer + ICP + distribution strategy lets the model cross-reference. The three-input content formula is information context + brand-voice profile + instruction.

**Claude skills are the current (2026) best home for standing context.** A skill is markdown in a zip; Claude injects a short description into every chat and loads reference files only when relevant, so mentioning your VA's name pulls their profile only in that moment. Make business context (market, offer, positioning) a standalone skill, separate from task skills like copywriting; pairing the two is what produces useful output.

**Self-managed profiles beat built-in memory on six dimensions.** Structure, visibility, control, portability, modularity, collaboration. EP's failure case: detailed diet/macros context saved by ChatGPT memory as only "is interested in eating 4 meals per day." Use memory for light personalization and drafting an initial profile; use files you control for serious injection.

**The highest-leverage use of an LLM is ideation partner, not answer machine.** Feed it your business data and let personalized analysis surface ideas you would not have considered. It should not make decisions.

**The secret of viral mega-prompts is the context-collection window, not the rules.** Start any serious prompt with a question-by-question interview before the model produces anything; EP reports roughly 10x better output.

**Privacy rule of thumb:** do not tell an LLM anything you would not type into Google; data handling is identical.

## Workflow

1. **Diagnose the gap.** Ask: what does the model need to know about the user's situation that it cannot know? Sort into facts (business, product, customer, voice, goals, constraints) and instructions (how to use those facts). If the user is chasing a model upgrade, redirect here first.
2. **Pick the profile(s) to build.** The 8 core types EP published templates for: business context, brand voice, marketing strategy, ideal customer, content strategy, product roadmap, audience psychographics, YouTube scriptwriting. A business at full efficiency also holds one profile per product, per distribution strategy, plus sales process and team structure. Start with business context, then ICP, then brand voice (the compounding trio).
3. **Run the interview, one question at a time.** Do not ask the user to fill a form. Cover the business-profile fields (overview, products and pricing, personas, voice), asking follow-ups until each field has concrete, specific content. Interviews beat self-description.
4. **Compile into JSON.** Use the templates below. One fact or instruction per field. Keep it dense; strip prose. Confirm with the user and have them save the file where they control it (a repo, a folder, a Claude skill).
5. **Decide the storage home.**
   - Claude user: create a standalone business-context skill (SKILL.md description + reference JSON files) separate from task skills. Also make skills for people you work with and every SOP.
   - Other tools: keep profiles as files and paste them; use memory/projects only for light personalization.
   - Only build RAG when the corpus is genuinely too large for injection.
6. **Stack and prompt.** Write the task prompt in plaintext or XML; inject the relevant profiles (not all of them). For content: information context + brand-voice profile + instruction (e.g. a copywriting course transcript + creator voice profile + "generate 30 short-form reel scripts in this voice using this info").
7. **If context grows large, use the two-call pattern.** Call 1 only extracts task-relevant slices from the context store and assembles the prompt; call 2 does the work in a fresh window. Extend to retrieval → LLM filtering/summarization → final call.
8. **For long sessions, keep the window small.** Continuously save relevant context externally as you go; output degrades as context grows (even Gemini past ~100k tokens). Treat context as a curated persistent asset you re-inject.
9. **Convert knowledge sources into profiles.** For a course or book: split by module, extract transcripts, have the LLM compress each key point into a field containing one instruction or fact. A raw course drowns the model in filler; the compiled profile is an editable persistent "course."
10. **Close the loop.** End sessions by asking the model to update the relevant profile, and (for personal profiles) ask: "based on this interaction, tell me a few things I may not know about myself that are either beneficial or detrimental to my growth."

## Checklists / templates

### Business context profile (fields named by EP)

```json
{
  "general_overview": {
    "business_name": "",
    "mission": "",
    "problem_solved": "",
    "elevator_pitch": ""
  },
  "products": [
    {
      "name": "",
      "description": "",
      "pricing": "",
      "delivery_format": "",
      "key_outcomes": []
    }
  ],
  "ideal_customer_personas": [
    {
      "persona_name": "",
      "problems": [],
      "desired_outcomes": [],
      "objections": []
    }
  ],
  "brand_voice": {
    "tone": "",
    "writing_guidelines": [],
    "example_copy_snippets": []
  },
  "market_and_positioning": {
    "market": "",
    "positioning": "",
    "competitors": []
  },
  "goals_and_constraints": {
    "current_goals": [],
    "constraints": []
  }
}
```

### Ideal customer profile (ICP)

```json
{
  "icp_name": "",
  "demographics": {},
  "values": [],
  "lifestyle": "",
  "pains": [],
  "desired_outcomes": [],
  "purchase_triggers": [],
  "objections": [],
  "price_sensitivity": "",
  "platforms": [],
  "brand_expectations": [],
  "language_they_use": [],
  "recommended_channels": [],
  "messaging_angles": []
}
```

### Brand voice profile

```json
{
  "voice_name": "",
  "tone": "",
  "personality_traits": [],
  "writing_guidelines": {
    "do": [],
    "dont": [],
    "sentence_length": "",
    "formatting_habits": "",
    "vocabulary": [],
    "banned_words": []
  },
  "hooks_and_openers": [],
  "example_copy_snippets": [],
  "audience_relationship": ""
}
```

To clone a creator's voice: feed a YouTube transcript and ask the model to fill this profile from it.

### Personal context database (fields named by EP)

basic stats; current situation (focus, routine, time, resources, constraints); goals at 3-month / 1-year / 3-5-year horizons; problems and past obstacles; thinking style; interests; strengths and gaps. Fill by interview; update at session end.

### Interview opener (paste as the first message)

```
You are helping me build a reusable [business / ICP / brand voice] context profile in JSON.
Interview me one question at a time. Ask follow-ups until each field is concrete and specific.
Do not produce the JSON until you have covered every field. Fields: [paste template keys].
When done, output only the completed JSON, one fact or instruction per field, no filler.
```

### Injection pattern

```
<business_context>{paste business JSON}</business_context>
<icp>{paste ICP JSON}</icp>
<brand_voice>{paste voice JSON}</brand_voice>

Task: [plaintext instruction]. Cross-reference the profiles above. Output format: [...]
```

## Anti-patterns

- Dumping every profile into every prompt. Retrieve selectively; a full window degrades output.
- Prompting in JSON. Store in JSON, prompt in plaintext/XML.
- Typing the profile yourself instead of being interviewed; self-description is less accurate.
- Relying on ChatGPT memory for serious context (vague impressions, silent pollution, cross-referenced unrelated chats, vendor lock-in). EP's 2025-04 "flood memory" take is superseded by profiles-over-memory.
- Mixing business context into a task skill. Keep the business-context skill standalone.
- Feeding a raw course or book wholesale instead of compiling it into a profile.
- Letting the model make decisions instead of surfacing ideas for you to decide.
- Tool-hopping on release hype; much of it is paid influence or engagement bait.
- Pasting sensitive data you would not type into Google.

## Dated / volatile notes

- "Stop obsessing over model releases" stated 2026-06.
- Profiles/business-profile/8 types/three-input formula/memory critique/two-call pattern: posted June 2025, practice might be outdated.
- Context two-buckets and keep-window-small: December 2025.
- JSON for storing not prompting: 2025-08, reaffirmed 2026-04.
- Profile stacking and context-collection window: May 2025.
- Claude skills as home for context: November 2025 (claims "significantly better than GPT projects").
- Convert courses into profiles: August 2025. Personal context database: February 2025. Health profile: December 2025.
- LLMs weak at spatial reasoning (chess puzzles): March 2025, may be outdated.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `prompting-techniques` (how to write the instruction half), `business-strategy-prompts` (interview prompts that output marketing/ICP JSON), `brand-voice-and-authentic-ai-writing`, and `coding-agents-and-knowledge-systems` (second-brain storage for profiles).
