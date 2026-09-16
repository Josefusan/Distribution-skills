# Skill authoring spec for the "Distribution skills" repo

Every skill lives in `skills/<skill-name>/` and follows the Anthropic skill format:

```
skills/<skill-name>/
├── SKILL.md              (required)
└── references/
    └── source-lessons.md (required: the verbatim source lessons this skill is built from)
```

## SKILL.md frontmatter

```yaml
---
name: <kebab-case, same as folder>
description: <1-3 sentences. What the skill does AND when to trigger it. Be "pushy": list the concrete user phrasings/situations that should trigger it, including cases where the user doesn't name the topic directly.>
---
```

## SKILL.md body (target 120-300 lines, hard max 400)

Write in imperative voice, explain the WHY behind each instruction (these are opinionated operator heuristics from EP/@eptwts — say so up top in one line and attribute: "Distilled from EP's (@eptwts) knowledge base, eptwts.com").

Required sections, in this order:

1. `# <Title>` + one-paragraph summary of what the skill helps with and the core thesis.
2. `## When to use` — bullets of triggering situations.
3. `## Core principles` — the 5-12 most important heuristics, each as a bold one-liner followed by 1-3 sentences of why/how. Keep EP's concrete numbers and examples where they make the point sharper (e.g. "1,000 real followers beat 10,000 random impressions").
4. `## Workflow` — a numbered, step-by-step procedure Claude should walk the user through (or execute) when the skill triggers. Include decision points ("if X, do Y").
5. `## Checklists / templates` — any reusable checklists, prompt templates, scoring rubrics, or output formats. If the source contains a named playbook or prompt structure, reproduce it as a usable template.
6. `## Anti-patterns` — what NOT to do, drawn from the source.
7. `## Dated / volatile notes` — anything the source flags as "practice might be outdated" or tied to a date (platform mechanics, tool names, prices). One line each with the date.
8. `## Read next` — pointer: "For the full verbatim lessons see `references/source-lessons.md`" plus names of sibling skills in this repo that pair with it.

## references/source-lessons.md

Copy the relevant lessons VERBATIM from the source chapter file (do not paraphrase; keep the bold titles and the "posted <month> · practice might be outdated" tags). Add a one-line header naming the source URL.

## Style rules

- No filler. No "In today's fast-paced world".
- Preserve EP's specific, opinionated claims; attribute them to him rather than presenting them as universal facts.
- Keep ethically dubious / ToS-violating tactics (bought engagement, account farms, content lockers that never pay out, fake giveaways, leak-forum seeding, upvote services) OUT of the Workflow section. They may appear in the references file verbatim and, at most, be mentioned in Anti-patterns or Dated notes as "EP describes X; it is patched/ToS-violating/unethical — don't run it." The skills should teach the whitehat, durable version.
- Never invent numbers or claims that aren't in the source.
