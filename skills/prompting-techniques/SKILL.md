---
name: prompting-techniques
description: Turn a vague or messy request into a precise, high-yield prompt using role assignment, context collection, step-by-step instructions, example output, rules, multi-role debate, recursive prompting, and session serialization. Use when the user says "the AI gives me generic answers", "how should I phrase this", "write me a prompt for X", "improve this prompt", "make the AI argue both sides", "save this chat's behavior", "the AI builder keeps misunderstanding me", or pastes a one-line question like "how do I market my business" that would benefit from being rewritten before it is run.
---

# Prompting Techniques

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill helps you convert a messy request into a precise instruction set and apply the handful of prompting patterns EP considers worth knowing. Core thesis: clear instructions beat raw model intelligence. The more room you leave a model to infer intent, the further the output drifts; a person of average ability with precise step-by-step instructions outperforms a genius with messy ones.

## When to use

- The user's prompt is a single broad question and the answer came back generic.
- The user wants a reusable prompt or system prompt for a recurring task.
- The user needs sharper, more specific advice than a plain question yields (role assignment).
- The user faces a contested question where opposing experts disagree (multi-role debate).
- A chat is performing exceptionally well and the user wants to keep that behavior.
- An AI builder or weaker tool keeps misinterpreting the user's instructions.
- The user asks what prompt-engineering fundamentals to learn.

## Core principles

**Every good prompt has five parts.** Role assignment; context (or a context-collection process such as an interview); step-by-step instructions; an example output structure; rules. Prompts do not need to be long, but the more conditions you set, the more curated the output, no matter how smart models get.

**Clear instructions beat raw intelligence.** Broad prompts will never match the output you imagined. Reduce inference room: state topic, audience, format, success criteria.

**Role assignment steers which training data gets accessed.** EP's example: plainly asking for a CPA marketing method returned generic results; "you are a BlackHatWorld moderator" returned specific ones. Even "take a high IQ, rational, first-principles approach" noticeably sharpens advice. Caveat: role bias does not qualify data quality; a model hooked to a specialized knowledge base beats its general state.

**Multi-role debate is the overlooked upgrade to role assignment.** Assign two or more expert roles to the same problem, make them debate, output the refined synthesis. Council-of-experts truth filter: simulate polar opposites (carnivore vs. vegan) and ask for common ground; conclusions opposing camps share hold the most truth.

**Have the AI write and improve its own instructions (recursive prompting).** Ask LLM #1 "what is the best way to prompt {X idea} so it gives {Y output}", send the result to LLM #2, inspect, ask it to edit the prompt, store the polished version in a prompt library.

**Serialize a great session.** When a chat is performing exceptionally well: "your current state is perfect - send me a prompt in markdown that I can send to another LLM so it acts as a clone of you." Reuse as a system prompt anywhere.

**Keep a prompt-engineer rewriter as a standing system prompt.** It converts messy questions into precise instructions: assign expert role, state topic simply, break into parts, demand examples/steps, specify output format, name the audience, define success.

**Context collection beats rules.** The secret behind viral mega-prompts is the interview at the start, not the rules; have the model gather context question by question before producing anything.

**Translator pattern for weaker tools.** When an AI builder misunderstands, give a stronger model (Claude) a screenshot plus your idea and have it write unambiguous instructions for the builder: a prompt writing a better prompt.

**Learn the fundamentals and prompt intuitively.** Meta-prompting, chain-of-thought, few-shot, self-refining prompts, prompt-chaining, role-based prompting, socratic prompting, plus how an LLM processes a query.

## Workflow

1. **Capture the raw request.** Take the user's messy question as-is. Identify what is missing among: role, topic, audience, constraints (budget, time, tools), desired output format, definition of success.
2. **Decide whether to interview first.** If the task depends on the user's situation (business, audience, goals), add a context-collection window: the prompt must instruct the model to ask one question at a time before producing anything. If stored profiles exist, inject them instead (see `context-engineering-profiles`).
3. **Assign the role.** Pick the most specific persona whose training data you want (a niche forum moderator, a direct-response copywriter, a first-principles rationalist). For contested topics, assign two opposing experts and require a debate plus synthesis.
4. **Write the instruction in the five-part structure.** Role → context/interview → numbered steps → example output structure → rules (constraints, banned behaviors, success definition). Keep it as short as the conditions allow.
5. **Run the rewriter if the user wants speed.** Paste the raw question into the prompt-engineer rewriter template below and use its output.
6. **Iterate recursively.** Send the prompt to a second model, inspect output, ask it to edit the prompt. Store the polished version in the user's prompt library.
7. **If the session is excellent, serialize it.** Ask the model for a markdown clone-prompt and save it as a system prompt.
8. **If the target is a weaker builder tool,** have Claude translate: screenshot + idea → unambiguous instructions for the builder.
9. **Verify output.** Check hallucinations against sources; role assignment does not guarantee data quality.

## Checklists / templates

### Good-prompt checklist

- [ ] Role assigned (specific, not "helpful assistant")
- [ ] Context provided, or an interview step that collects it one question at a time
- [ ] Step-by-step instructions
- [ ] Example output structure
- [ ] Rules: constraints, banned behaviors, audience, definition of success

### Prompt-engineer rewriter (system prompt)

```
You are a prompt engineer. Your only job is to rewrite the user's messy question into a precise instruction for an LLM. Do not answer the question.

For every input:
1. Assign the most specific expert role for the topic.
2. State the topic in one simple sentence.
3. Break the request into its component parts.
4. Demand concrete examples, exact steps, and numbers where relevant.
5. Specify the output format (list, table, steps, word count).
6. Name the audience and their level.
7. Define what a successful answer must contain.
8. Add rules that remove vagueness (budget, timeframe, constraints, what to exclude).

Output only the rewritten prompt, ready to paste.
```

Before/after from the source:

- Before: "How do I market my business?"
- After: "You're a marketing expert. Give me 3 marketing strategies under $1,000 that worked for real businesses and can start this week, with exact steps and common mistakes."

### Multi-role debate template

```
Assign two experts with opposing views on [problem]: [Role A] and [Role B].
Round 1: each states their position and strongest arguments.
Round 2: each rebuts the other.
Round 3: identify every conclusion both agree on.
Output: the shared conclusions first, then a refined synthesis with the remaining disagreements and what evidence would settle them.
```

### Recursive prompting

```
LLM #1: "What is the best way to prompt {X idea} so it gives {Y output}? Write the prompt."
LLM #2: run the generated prompt. Then: "Inspect your output. Edit the prompt so the output would be better on [criteria]. Return the improved prompt."
Store the final version.
```

### Session serialization

```
Your current state is perfect - send me a prompt in markdown that I can send to another LLM so it acts as a clone of you.
```

### Translator pattern

```
[attach screenshot of the builder's current state]
I am using [builder tool]. What I want: [idea in plain words]. It keeps misunderstanding me.
Write unambiguous, step-by-step instructions I can paste into the builder to get exactly this.
```

## Anti-patterns

- Broad one-line questions expecting curated answers.
- Assuming a role makes the data accurate; specialized knowledge injected beats persona alone.
- Writing long rule lists without a context-collection step.
- Running a great prompt once and losing it; keep a prompt library.
- Trusting refusals or compliance blindly. EP notes refusals are often soft and blunt pushback occasionally gets compliance (April 2025); do not use this to push past legitimate safety or policy limits.

## Dated / volatile notes

- Good-prompt checklist, multi-role debate: posted May 2025, practice might be outdated.
- Role assignment examples: August 2025.
- Recursive prompting, rewriter, translator pattern: March 2025.
- Serialize a session: February 2025.
- Fundamentals list and soft refusals: April 2025.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `context-engineering-profiles` (the context half of a prompt), `advisor-and-self-analysis-prompts` and `business-strategy-prompts` (worked examples of full five-part prompts), and `learn-with-ai`.
