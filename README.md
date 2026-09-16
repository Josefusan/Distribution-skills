# Distribution Skills

35 Claude skills distilled from **EP's (@eptwts) Signal Knowledgebase** — "all the signal from my 14,000 tweets" — at [eptwts.com](https://www.eptwts.com), plus his partnership-program page and a sample of his recent/top X posts.

EP's thesis, and this repo's organizing idea: **all roads lead to distribution.** A 10x worse product with the right distribution beats the best product with none. The skills cover the whole loop he describes — picking a market, designing an offer, driving traffic, converting in owned channels, using AI as a multiplier, and executing.

> Everything here is EP's opinionated operator heuristics, attributed to him, not universal fact. Tactics he flags as dated carry a "practice might be outdated" note. ToS-violating or manipulative tactics he describes are kept out of every skill's workflow and appear only in the verbatim references, marked "don't run."

## Layout

```
skills/<skill-name>/
├── SKILL.md                    # frontmatter + principles, workflow, templates, anti-patterns
└── references/source-lessons.md   # the verbatim source lessons the skill is built from
sources/                        # full scrape of eptwts.com (8 chapters), partners page, X sample
SKILL_SPEC.md                   # the authoring spec every skill follows
```

## Using the skills

**Claude Code / Cowork:** copy any `skills/<name>/` folder into your skills directory (e.g. `~/.claude/skills/` or a project's `.claude/skills/`). Each SKILL.md is self-contained; the `references/` file is loaded only when needed.

**Claude.ai:** zip a skill folder and upload it under Settings → Skills, or run `python -m scripts.package_skill skills/<name>` from the Anthropic skill-creator to produce a `.skill` file.

Skills reference each other in their "Read next" sections — e.g. `distribution-first-strategy` hands off to `offer-design-and-buyer-psychology`, which hands off to `funnels-and-owned-channels`.

## The skills

### Business strategy

| Skill | What it does |
|---|---|
| [`distribution-first-strategy`](skills/distribution-first-strategy/SKILL.md) | Pick and validate a distribution channel for a product before (or instead of) building more product. |
| [`market-and-problem-selection`](skills/market-and-problem-selection/SKILL.md) | Select and validate a niche, market, or problem to build a business around, with a scoring rubric. |
| [`offer-design-and-buyer-psychology`](skills/offer-design-and-buyer-psychology/SKILL.md) | Design an offer from problem to packaging (info, SaaS, service, community) to price to test, using EP's buyer-psychology heuristics. |
| [`ai-product-moat-strategy`](skills/ai-product-moat-strategy/SKILL.md) | Evaluate or design an AI product, wrapper, agent, API, or AI service for defensibility and profit. |
| [`online-business-playbooks`](skills/online-business-playbooks/SKILL.md) | Pick and walk an end-to-end online business playbook matched to the user's constraints (skills, capital, willingness to show their face, coding ability). |
| [`partnerships-hiring-delegation`](skills/partnerships-hiring-delegation/SKILL.md) | Decide when, what, and how to delegate, hire, or partner, and how to structure the deal (incentives, performance pay, equity/revshare). |
| [`brand-leverage-and-information-hygiene`](skills/brand-leverage-and-information-hygiene/SKILL.md) | Decide how much to build on a personal brand vs. faceless or operator-behind-creators models, what to reveal publicly (niche, earnings, methods, client results), how to vet gurus and communities, and how to convert volatile online income into durable wealth. |

### Growing an audience

| Skill | What it does |
|---|---|
| [`x-algorithm-optimization`](skills/x-algorithm-optimization/SKILL.md) | Audit and optimize an X (Twitter) post or account against the ranking signals the open-source X algorithm actually weights (retweets/quotes, follows, dwell time, profile clicks, replies, negative signals, tweepcred, author-diversity decay). |
| [`x-growth-from-zero`](skills/x-growth-from-zero/SKILL.md) | Build a phased 0-to-10k follower plan for a new or tiny X (Twitter) account using EP's playbook — big-account engagement as the distribution unlock, the affiliate route, experience-based value posts, lead magnets under 10k, follow lists, intro tweets, profile/bio rules, and weekly cadence. |
| [`content-principles-and-audience-quality`](skills/content-principles-and-audience-quality/SKILL.md) | Define who a creator's content is for, set content pillars that attract buyers rather than spectators, and run a pre-publish checklist (provoke / spark / start, reader-as-protagonist, no self-documentation early, honesty over flex). |
| [`platform-strategy-and-youtube-mechanics`](skills/platform-strategy-and-youtube-mechanics/SKILL.md) | Choose the platform mix for a specific offer (X vs YouTube vs TikTok/Reels/Shorts) using EP's traffic-quality map, and run a YouTube channel launch and diagnosis procedure (first 6-10 video test, search vs browse, never linking from outside, permanent-VSL structure, Shorts related-video trick). |
| [`platform-growth-playbooks`](skills/platform-growth-playbooks/SKILL.md) | Run platform-specific growth funnels the whitehat way — Instagram comment-to-DM funnel, 7-second loop reels, localized town/community pages run by real hires, clipping partnerships with permission, spectacle/trend-adjacent content — and explain why EP's grey-hat versions (bought followers, account farms, fake persona pages, proxies) are not worth running. |

### Writing & content

| Skill | What it does |
|---|---|
| [`write-for-reach`](skills/write-for-reach/SKILL.md) | Turn a raw idea into a post, thread, or piece of content that gets reach - hook it, dumb it down, structure it for scannability, and pick the right format/platform. |
| [`direct-response-copywriting`](skills/direct-response-copywriting/SKILL.md) | Write persuasive, conversion-focused copy (landing pages, VSL scripts, sales emails, ad copy, lead magnets, product-promoting content) by mapping the customer's desire chain, mining real customer language from Reddit/Quora/reviews, and structuring content like a VSL. |
| [`brand-voice-and-authentic-ai-writing`](skills/brand-voice-and-authentic-ai-writing/SKILL.md) | Build a reusable brand-voice profile from a corpus of someone's writing and run a daily writing loop where a human braindumps, AI formats, and the human rewrites in their own voice - so posts never read as AI-generated. |

### Monetization & offers

| Skill | What it does |
|---|---|
| [`funnels-and-owned-channels`](skills/funnels-and-owned-channels/SKILL.md) | Design a monetization funnel that routes social/content traffic into an owned channel (email list or Telegram) before a sales page, and decide how to pair a traffic source with an offer. |
| [`info-products-sell-transformation`](skills/info-products-sell-transformation/SKILL.md) | Design and price an info-product ladder (low-ticket front end → paid community → high-ticket done-with-you/service) that sells a transformation rather than information. |
| [`selling-without-sales-calls`](skills/selling-without-sales-calls/SKILL.md) | Close sales through a buy-now button and short DM exchanges instead of booked sales calls or long VSLs. |
| [`paid-community-design`](skills/paid-community-design/SKILL.md) | Launch and run a paid community - platform choice (Telegram vs Discord vs Whop), pricing gate, structure, onboarding, automated upsells, support, and retention metrics - plus the payment and platform mechanics around it. |
| [`monetization-playbooks`](skills/monetization-playbooks/SKILL.md) | Pick a niche by viewer value and run one of EP's complete step-by-step online business playbooks (minimal online business, $0-to-$10k insecurity play, level-0 baseline, faceless niche content, influencer piggyback, faceless trading brand, operator revshare, Telegram crypto channel, college pages, UGC retainer, beginner affiliate, local events, CPA training ground). |
| [`ethical-selling-and-grifter-detection`](skills/ethical-selling-and-grifter-detection/SKILL.md) | Evaluate whether an info offer, course, mentorship, or "guru" is legitimate - as a buyer deciding whether to pay, or as a seller deciding how to market and whom to accept. |

### Affiliate & traffic

| Skill | What it does |
|---|---|
| [`affiliate-and-clipping-onramp`](skills/affiliate-and-clipping-onramp/SKILL.md) | Plan and execute a first online income path via clipping/UGC and affiliate marketing - learn traffic as the transferable skill before building any product. |
| [`affiliate-traffic-playbooks`](skills/affiliate-traffic-playbooks/SKILL.md) | Run EP's concrete affiliate-traffic plays as step-by-step checklists - clipping-and-affiliate at scale, the beginner content-boost-for-promotion deal, broke-start replication with an owned channel, the YouTube-to-X transcript engine, language-arbitrage promo videos, AI slideshows, and AI angle-mining - plus a "dead/patched, don't run" register. |

### AI as leverage

| Skill | What it does |
|---|---|
| [`context-engineering-profiles`](skills/context-engineering-profiles/SKILL.md) | Build, store, and stack reusable JSON context profiles (business, ICP, brand voice, marketing strategy, personal context) so every AI session starts with your situation instead of from zero. |
| [`prompting-techniques`](skills/prompting-techniques/SKILL.md) | Turn a vague or messy request into a precise, high-yield prompt using role assignment, context collection, step-by-step instructions, example output, rules, multi-role debate, recursive prompting, and session serialization. |
| [`advisor-and-self-analysis-prompts`](skills/advisor-and-self-analysis-prompts/SKILL.md) | A library of ready-to-paste anti-sycophancy advisor prompts (brutally honest strategic advisor, first-principles problem solver, accountability manipulator, life optimizer, LogicCore, goal-to-checklist, journal profiling, and more) and a picker for which one fits the user's situation. |
| [`business-strategy-prompts`](skills/business-strategy-prompts/SKILL.md) | Ready-to-paste interview prompts for each stage of a business, from scoring an idea backlog and matching a business model, through positioning, ICP and marketing-strategy JSON, Reddit pain-point and distribution-channel deep research, to an execution checklist. |
| [`learn-with-ai`](skills/learn-with-ai/SKILL.md) | Learn any book, video, PDF, course, or skill faster with AI by extracting only what applies to your situation, running interactive tutoring, and building personalized curricula. |
| [`ai-image-and-visual-style-profiles`](skills/ai-image-and-visual-style-profiles/SKILL.md) | Extract a reusable JSON visual style profile from reference images and use it to generate on-brand thumbnails, ads, infographics, UI, and decks with image models. |
| [`ai-ugc-video-production`](skills/ai-ugc-video-production/SKILL.md) | Produce AI-generated UGC and short-form video ads by researching winning videos, analyzing them with Gemini, rewriting the context for your product, and generating with image-to-video models, then editing. |
| [`coding-agents-and-knowledge-systems`](skills/coding-agents-and-knowledge-systems/SKILL.md) | Set up a coding-agent harness and a continuously-fed second brain (Obsidian + Claude Code, drop-folder pipelines, RAG over conversation data, always-on server agent) for an operator, and pick the right model and tool per task. |

### Mindset & execution

| Skill | What it does |
|---|---|
| [`execution-and-focus-systems`](skills/execution-and-focus-systems/SKILL.md) | Turns a vague ambition into an 8-week goal, three daily needle-moving tasks, a daily audit and a one-month kill/iterate review. |
| [`network-and-outreach`](skills/network-and-outreach/SKILL.md) | Builds a business network from zero and writes cold outreach that established operators actually answer. |
| [`motivation-identity-and-career-strategy`](skills/motivation-identity-and-career-strategy/SKILL.md) | Runs a self-audit, builds a skill-stack plan, and sets a 90-day skill sprint for someone deciding what to do with their career or online-business ambitions. |
| [`money-management-and-advice-filtering`](skills/money-management-and-advice-filtering/SKILL.md) | Evaluates whether to trust a piece of advice, a guru, a course, or an offer, and sanity-checks personal finances for people with volatile internet income. |
## Sources

| File | Content |
|---|---|
| `sources/01-business-strategy.md` … `08-tools-i-use.md` | Full text of the eight chapters of eptwts.com, scraped 2026-09-15 |
| `sources/09-partners-program.md` | partners.eptwts.com application (useful as an operator-vetting template) |
| `sources/10-twitter-eptwts.md` | @eptwts profile + a sample of recent and top posts (X throttled pagination; the knowledge base is itself the distillation of the full archive) |

## Suggested reading order (a distribution curriculum)

1. `distribution-first-strategy` → `market-and-problem-selection` → `offer-design-and-buyer-psychology`
2. `x-growth-from-zero` → `x-algorithm-optimization` → `write-for-reach` → `content-principles-and-audience-quality`
3. `funnels-and-owned-channels` → `selling-without-sales-calls` → `info-products-sell-transformation` → `paid-community-design`
4. `affiliate-and-clipping-onramp` → `affiliate-traffic-playbooks` (if starting with zero product)
5. `context-engineering-profiles` → `prompting-techniques` → `business-strategy-prompts` → `ai-ugc-video-production`
6. `execution-and-focus-systems` → `network-and-outreach`

All credit for the underlying ideas to EP — [x.com/eptwts](https://x.com/eptwts).
