---
name: brand-voice-and-authentic-ai-writing
description: Build a reusable brand-voice profile from a corpus of someone's writing and run a daily writing loop where a human braindumps, AI formats, and the human rewrites in their own voice - so posts never read as AI-generated. Trigger when the user asks to "write in my voice", "make this sound like me", "does this sound AI", wants to replicate a creator's or YouTube channel's style, asks for a brand-voice/style guide or voice profile, asks whether to schedule/automate posts, worries their content sounds engineered or salesy, or wants a sustainable daily posting habit.
---

# Brand voice and authentic AI writing

Distilled from EP's (@eptwts) knowledge base, eptwts.com, plus voice notes from his X profile. These are EP's opinionated operator heuristics.

Authenticity is the only moat in a sophisticated market, and AI should be used to think, not to speak. This skill does two things: builds a brand-voice profile from a corpus (yours, or a creator/channel you want to model) so AI output stops sounding robotic, and installs the daily loop - braindump manually, let AI format, rewrite in your own voice, log every change. Core thesis: the substance must come from a human brain; AI helps only with clarity, and a voice profile is what separates indistinguishable output from ChatGPT slop.

## When to use

- User wants AI-assisted writing that still sounds like them.
- User wants to extract a creator's or YouTube channel's style into a reusable profile.
- User asks "does this sound AI-generated?" or has posts that feel synthetic.
- User is tempted to schedule tweets, batch-generate posts, or fully automate an account.
- User's content is visibly engineered to sell and engagement is falling.
- User wants a low-effort sustainable daily writing habit (EP: under 15 minutes a day).
- User is deciding whether to go "mass AI slop" or "high-quality" with AI content.

## Core principles

**99 out of 100 posts should have no ulterior motive beyond real value.** People copying a successful style fail because every post is visibly engineered to sell, and a sophisticated market knows exactly what you're doing. The followers who trust your authentic value are the ones who buy when you promote roughly once per 100 posts. EP: authentic value content now out-engages virality bait; the leased-supercar guru aesthetic is dying (2025).

**Write in one unedited stream, capped at about two minutes.** Over-editing makes writing sound synthetic. The occasional typo is the cost of sounding real - a deliberate trade for volume and authenticity. EP spends under 15 minutes a day writing tweets and sustains reach.

**Don't systemize X.** Post manually the moment you have an interesting thought. Never schedule. Never use AI to write tweets. Automation contradicts what the platform rewards: live, authentic thought.

**Share 99% of what you know; it will not hurt your business.** The whole audience-building protocol: when you learn something that makes your life easier, post it.

**Turn every act of consumption into a trigger for creation.** Watch a video, write an article. Scroll X, quote-tweet your take. Read a book, tweet the best ideas. This flips you from consumer to creator and gives an endless free pipeline.

**Ugly beats polished.** Aesthetic perfectionism is low-ROI unless your brand is literally built on aesthetics. Low-production authentic videos outperform over-produced brand content by orders of magnitude per dollar (EP: polished productions peaked at 3k views; paid college students making authentic videos did far better for a fraction of the cost). Optimize for perceived authenticity.

**Mask questions as authoritative statements.** Publish a confident guide containing the thing you're unsure about; experts flame you in the replies with detailed corrections. They get an ego boost, you get the knowledge.

**Never let AI fully write audience-facing posts.** Heavy AI users instantly recognize the tells ("the f*cked part? they didn't pay a dime", "here's the truth no one is talking about...") and it destroys credibility. On AI-focused X, hand-written accounts consistently outperform those publishing AI-generated posts (2026). AI lacks intuition; in personal branding the human element always wins.

**EP's content process: braindump, AI formats, you rewrite, log the diff.** Manually braindump the ideas, let AI format them more cleanly, rewrite in your own voice, and log every change plus why into a brand-voice markdown file the agent maintains. You cannot AI-generate good advice.

**Robotic output means no voice profile was used.** Collect a corpus of the target voice, extract its patterns into a reusable profile, attach it to every generation prompt. EP's proof point: a fully AI-generated tweet from his generator drew a reply from Elon Musk.

**AI content has two viable lanes; the middle is dead.** Mass-produced slop for cheap traffic at scale, or genuinely high-quality art. Mediocre AI-assisted content has no audience - pick a lane deliberately (2025).

## Workflow

### Part A: build a brand-voice profile from a corpus

1. **Collect the corpus.** Gather 30-100 representative pieces of the target voice: your own best posts, or a creator's tweets, or a YouTube channel's transcripts (any transcript extractor, or paste the link into Perplexity). Prefer top-performing pieces plus a sample of ordinary ones so the profile captures the baseline, not only the outliers.

2. **Decide the profile type.** If the target is short-form text (tweets, posts, emails): use the brand-voice JSON template below. If the target is a YouTube/video style: use the script-profile JSON template below (EP's script-profile playbook). Note the limitation: transcript-based extraction cannot capture visual elements.

3. **Extract patterns with AI.** Send the corpus plus the empty template to the model and have it fill every field with evidence - quote 2-3 examples from the corpus per field. Reject fields filled with generic adjectives ("engaging", "authentic") that have no quoted evidence.

4. **Verify by generation.** Have the model write 5 new pieces using only the profile. Read them next to real corpus items. Anything that reads as "the tells" (rhetorical "here's the truth..." openers, forced contrast lines, em-dash cascades) means the profile is missing a "never does" rule - add it.

5. **Save it as a living file.** Store as `brand-voice.md` (or JSON). This is the file the daily loop appends to.

### Part B: the daily writing loop

6. **Trigger on consumption.** Every time you consume something (video, thread, book, conversation), that's a creation trigger. Don't systemize the schedule; post when the thought arrives.

7. **Braindump manually, two-minute cap.** Stream of thought, unedited. If it's a tweet, this is often the finished product - post it. Typos are acceptable. Do not spend 15 minutes polishing a tweet.

8. **If the idea needs structure (thread, article, lead magnet): AI formats only.** Prompt: "Format this braindump for clarity using the attached brand-voice profile. Do not add ideas, claims, or examples. Do not change the substance." The model reorganizes; it does not author.

9. **Rewrite in your own voice.** Go line by line over the formatted version and put it back into how you'd actually say it. This pass is not optional - it's what keeps the human element.

10. **Log the change.** For every edit you made to the AI version, append one line to `brand-voice.md`: what you changed and why. Over time the agent learns your voice from these diffs, and steps 8-9 get shorter.

11. **Check the motive ratio.** Before posting, ask: is this one of the 99 (pure value) or the 1 (promotion)? If you've promoted recently, this one is pure value.

12. **Pick the lane if you're producing AI content at scale.** Decision point: either it's high-volume slop for cheap traffic (a separate, unbranded operation - see `affiliate-traffic-playbooks`) or it's high-quality work with your name on it. Never ship the middle under your personal brand.

## Checklists / templates

### Brand-voice profile JSON template

```json
{
  "name": "",
  "corpus": { "source": "", "pieces": 0, "date_range": "" },
  "casing_and_punctuation": {
    "casing": "",
    "sentence_endings": "",
    "signature_punctuation": [],
    "emoji_usage": ""
  },
  "structure": {
    "line_length": "",
    "ideas_per_line": "",
    "spacing": "",
    "list_style": "",
    "typical_length": ""
  },
  "hook_patterns": [],
  "closer_patterns": [],
  "stance": {
    "person": "",
    "attitude": "",
    "evidence_style": ""
  },
  "vocabulary": {
    "recurring_phrases": [],
    "slang_and_signoffs": [],
    "complexity": ""
  },
  "topics_and_lenses": [],
  "never_does": [],
  "examples": [
    { "text": "", "why_representative": "" }
  ],
  "change_log": [
    { "date": "", "ai_wrote": "", "i_changed_to": "", "why": "" }
  ]
}
```

### Worked example: EP (@eptwts) voice profile (from the X profile voice notes)

```json
{
  "name": "EP (@eptwts) - 'attention engineer'",
  "corpus": { "source": "x.com/eptwts sample, Aug-Sep 2026", "pieces": 18, "date_range": "2026-08 to 2026-09" },
  "casing_and_punctuation": {
    "casing": "all lowercase",
    "sentence_endings": "no period at the end of the last line",
    "signature_punctuation": ["frequent '...' trailing ellipses to set a hook then deliver a payoff"],
    "emoji_usage": "none observed"
  },
  "structure": {
    "line_length": "short",
    "ideas_per_line": "one idea per line",
    "spacing": "blank line between beats",
    "list_style": "'-' or '>' bullets",
    "typical_length": "one line to a short multi-beat post"
  },
  "hook_patterns": ["'the funny thing about people saying X is that...'", "'we've reached a point where...'", "'one of the biggest unlocks i've found...'"],
  "closer_patterns": ["aphoristic one-liners: 'if distribution is everything, build a distribution business'"],
  "stance": {
    "person": "first-person",
    "attitude": "contrarian",
    "evidence_style": "experience-backed ('i was doing it before AI was a thing')"
  },
  "vocabulary": {
    "recurring_phrases": ["one-shot", "distribution", "agent", "skill"],
    "slang_and_signoffs": ["God bless AI", "open your minds people", "maxxing"],
    "complexity": "simple words, no jargon"
  },
  "topics_and_lenses": ["distribution > product", "agents doing the work autonomously", "AI as leverage for individuals", "double down on natural gifts"],
  "never_does": ["title case", "hashtags", "AI tells like 'here's the truth no one is talking about'", "scheduled or batch-generated posts"],
  "examples": [
    { "text": "if distribution is everything, build a distribution business", "why_representative": "lowercase, aphoristic closer, no period, contrarian thesis in one line (2,388 likes, 92K views)" },
    { "text": "i no longer want to buy saas that helps ME do something... i want to buy saas that lets my agent autonomously do the things i'm currently doing manually", "why_representative": "ellipsis hook-then-payoff, first-person, one idea per beat" }
  ],
  "change_log": []
}
```

### Script-profile JSON template (EP's playbook for replicating a YouTube style, March 2025)

```json
{
  "channel_or_video": "",
  "hook": { "type": "", "duration_seconds": 0, "example": "" },
  "pacing_and_segments": { "pace": "", "segment_structure": [], "avg_segment_length": "" },
  "storytelling": { "approach": "", "arc": "" },
  "tone": { "baseline": "", "shifts": [], "emotional_triggers": [] },
  "humor": { "type": "", "joke_frequency": "" },
  "language": { "vocabulary_complexity": "", "catchphrases": [] },
  "retention_points": [],
  "seo_elements": { "title_pattern": "", "keywords": [], "description_pattern": "" },
  "limitations": "transcript-based; visual elements not captured"
}
```

Steps: 1) find a well-scripted video in your niche; 2) get its transcript; 3) send transcript + this template to AI; 4) use the filled profile to instruct AI to write new scripts in that style.

### Daily loop checklist

- [ ] Consumed something -> wrote something
- [ ] Braindump was manual, under ~2 minutes, unedited
- [ ] If AI touched it: it formatted only, added nothing
- [ ] Rewrote in my own voice line by line
- [ ] Logged every change + why to brand-voice.md
- [ ] Motive check: pure value (99) or promotion (1)?
- [ ] Posted manually, not scheduled

## Anti-patterns

- Every post visibly engineered to sell. The sophisticated market sees it and stops trusting you.
- Scheduling, batching, or letting AI write tweets. Automation contradicts what X rewards.
- Over-editing a two-minute thought into something that sounds synthetic.
- Shipping AI output with the tells: "here's the truth no one is talking about...", "the f*cked part?..." constructions.
- Using AI with no voice profile and blaming the model for sounding robotic.
- Adding ideas during the AI formatting step. Substance comes from the human.
- Skipping the change log - it's the mechanism by which the profile improves.
- Aesthetic perfectionism on creatives when the brand is not about aesthetics.
- Mediocre AI-assisted content under your personal brand. Middle lane has no audience.
- Hoarding knowledge for a paid product instead of sharing 99%.

## Dated / volatile notes

- December 2025 (flagged "practice might be outdated"): "Don't systemize X" - never schedule, never AI-write tweets. Platform reward mechanics may shift.
- March 2025 (flagged outdated): brand-voice profile method and the Elon Musk reply proof point; script-profile YouTube playbook (transcript extractors, Perplexity).
- 2025: the two-lanes claim about AI content; "authentic value out-engages virality bait".
- 2026: "never let AI fully write posts" and the observation that hand-written AI-niche accounts outperform AI-generated ones; the braindump -> format -> rewrite -> change-log process.
- 2026-09: EP voice sample above is from a throttled scrape of recent/top posts, not the full archive.

## Read next

For the full verbatim lessons see `references/source-lessons.md`.

Pairs with: `write-for-reach` (packaging the braindump for reach), `direct-response-copywriting` (the brand-voice component of the four-part AI copy prompt, and the 1-in-100 promotional post).
