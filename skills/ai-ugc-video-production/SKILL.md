---
name: ai-ugc-video-production
description: Produce AI-generated UGC and short-form video ads by researching winning videos, analyzing them with Gemini, rewriting the context for your product, and generating with image-to-video models, then editing. Use when the user says "make me UGC ads with AI", "clone this viral TikTok for my product", "generate a video ad", "analyze why this video works", "write a video prompt", "Seedance / Veo / Sora / Kling prompt", "AI avatar creatives", "green screen presenter", "turn these articles into a video script", or wants to scale video creatives without filming.
---

# AI UGC Video Production

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill helps you run EP's clone-a-winner assembly line: find videos already converting for products like yours, extract everything about them into structured context, rewrite that context to promote your product, generate scene by scene from a starting frame, and finish in an editor. Core thesis: AI UGC works commercially (passes as real to roughly 80% of viewers) and the fastest path to a working creative is to clone the structure of a proven winner, not to invent from scratch.

## When to use

- The user needs video creatives for an offer and cannot or will not film.
- The user has a reference video that performs and wants their own version.
- The user wants to understand hook, pacing, and structure of winning videos.
- The user needs a prompt for a video model.
- The user wants an evergreen presenter/explainer format.
- The user wants to turn written content into video scripts at scale.

## Core principles

**Clone a winner; do not invent.** Pull ~100 videos promoting products like yours, pick one that fits, extract all context, rewrite for your product. EP reports ~80% first-try success.

**Video is a chain of short clips from starting frames.** Realistic UGC is 4-8 second (up to ~17-30s) segments, each from a starting-frame image plus a short prompt; consistency comes from the frame and a global consistency lock, not from long prompts.

**Gemini is the video-analysis model, full stop.** It sees a video's actual visuals, not just the transcript. Judge multimodal models by hard real-world tests (it deciphers 200-year-old Kurrentschrift), not leaderboards.

**Get the prompt right so you one-shot it.** Seedance 2.5 is shockingly realistic and instruction-following but expensive (~$5 per 17s clip, ~$10 per 30s, 2026-08). Analysis and rewriting are cheap; generation is not.

**Add text in the editor, never in the model.** Video models are still bad at text; captions, overlays, cuts, zooms, and music are the human editor's job.

**Grab frames just after the cut.** ffmpeg at ~0.08s past a hard cut avoids transition motion blur; also take mid and end frames.

**Copy the professional prompt scaffold.** Style prefix, shot mode, identity/wardrobe locks, global consistency lock, per-shot camera and diegetic sound, long negative list.

**For openly-AI entertainment, go maximally absurd.** "No way this is real" is the viral hook; audiences accept fantasy like VFX. For UGC ads, the goal is the opposite: imperfect, organic, hand-held.

**Platform risk is low.** TikTok's parent built Seedance and Meta ships AI creative tools; they will not ban AI content (EP's claim).

## Workflow

1. **Research winners.** Use a short-form research API/scraper (Apify or similar) on the niche, filtered to 100k+ views, outliers, and sales intent. Pull ~100 videos promoting products like the user's. Pick one that fits format, audience, and product type. One project folder per video.
2. **Acquire and split.** Download with yt-dlp. PySceneDetect splits at hard cuts. ffmpeg grabs each scene's start frame ~0.08s past the cut plus mid/end frames.
3. **Analyze with Gemini.** Feed the video (or frames) to Gemini; for non-YouTube videos upload to a private YouTube account and pass the link; chunk anything over 1-2 hours. Output structured JSON/markdown: scenes, motions, appearance, mannerisms, accents, tone, hook, pacing, structure, why it converts. At scale, give Claude Code a Gemini Flash API key (EP: 1M+ videos for ~$140).
4. **Rewrite for your product.** Keep structure, pacing, and energy; replace product, claims, and script. Constrain claims to what the offer can deliver.
5. **Generate starting frames.** Per scene, create a frame with an image model (Nano Banana Pro / GPT-Image), or screenshot real UGC and change the person's appearance. Pick the best candidates.
6. **Write one generation prompt per scene** using the scaffold below. Ask Claude Code to draft them from the analysis JSON.
7. **Generate image-to-video** (Seedance 2.5 / Veo / Sora / Kling) per scene; expect a few generations per segment. Segment prompt: "extend this video and make her say this (make sure she is very expressive and enthusiastic): {script}".
8. **Edit.** Compile in CapCut or similar: captions, cuts, zooms, music, overlays. Then run as a traffic creative and iterate on hook/first seconds.
9. **Reusable formats:** green-screen presenter (still of a presenter in the bottom corner, green behind, organic hand-held quality → animate with script → chroma-key any screenshot behind); avatar tools (makeugc-style: script, avatar with product in hand, iterate on tone).
10. **Content at scale without cloning an expert:** put the expert's knowledge in a knowledge base, generate scripts from it, and use human presenters on multiple channels (EP's 2025 recommendation while AI presenters were unconvincing).

## Checklists / templates

### Video-analysis prompt (Gemini)

```
Analyze this video shot by shot. Output JSON:
{
  "hook": {"first_3_seconds": "", "why_it_stops_scroll": ""},
  "structure": [{"scene": 1, "start": "", "end": "", "visual": "", "motion": "", "camera": "", "dialogue": "", "on_screen_text": "", "sfx_music": ""}],
  "presenter": {"appearance": "", "wardrobe": "", "mannerisms": "", "accent": "", "tone": "", "energy": ""},
  "pacing": "", "retention_devices": [], "cta": "", "why_it_converts": ""
}
```

### Professional AI video prompt scaffold (from Higgsfield's open-sourced packs)

```
STYLE PREFIX: [film stock], [lens], [color grading], [director-style camera language]. UGC variant: iPhone, hand-held, organic, imperfect, non-cinematic.
SHOT MODE: [single continuous shot | multi-shot montage with hard cuts].
IMAGE REFERENCES: [frame 1 = presenter identity lock: face, hair, wardrobe, product in hand]. Do not alter.
GLOBAL CONSISTENCY LOCK: presenter identity, wardrobe, location, lighting, product appearance never change between shots.
SHOT 1: [framing], [camera move], [action]. Dialogue (lip-synced): "[line]". Diegetic sound: [ambient, product sounds].
SHOT 2: ...
NEGATIVE: no watermark, no wardrobe change, no lip-sync drift, no morphing, no extra people, no on-screen text, no logo distortion, no cinematic lighting, no slow motion.
```

### Clone-a-winner assembly line (6 steps)

1. Research API → ~100 videos for products like yours.
2. Pick one that fits.
3. Extract all context via a video-analysis tool into structured markdown (scenes, motions, appearance, mannerisms, accents, tone).
4. Generate candidate starting frames; pick the best.
5. Rewrite the context so it promotes YOUR product.
6. Rewritten context + starting frame → Seedance 2.5.

Ten-minute variant: research agent finds references → Gemini Flash scene-by-scene analysis with image-reference placeholders → GPT-image recreates a frame per cut-scene → Higgsfield/Seedance generation → human editor adds captions, cuts, zooms, music.

### Fully automated pipeline (Claude Code)

research API (100k+ views, outliers, sales intent) → folder per video → yt-dlp → PySceneDetect → ffmpeg frames (+0.08s, mid, end) → Gemini JSON (hook, pacing, structure, why it converts) → Claude Code writes one prompt per scene → each start frame + prompt → Seedance image-to-video.

### Gemini editing workflows

- Extract an "editing-style profile" JSON from a well-edited reference; upload raw footage privately; ask for cuts, VFX, transitions with exact timestamps, or hand the profile to a human editor as a manual.
- Retention reverse-engineering: shot-by-shot profiles (script, visuals, SFX, mood) from successful videos → key retention strategies → profile of your channel → implementation manual.

### Articles → video scripts

Scrape articles (Firecrawl) → extract a "script profile" from a proven video in the niche (pacing, storytelling, retention) → LLM writes a script from the articles in the profile's style. Automatable via the Firecrawl MCP server.

## Anti-patterns

- Inventing a creative from scratch when a proven structure exists.
- Asking the video model to render captions or text.
- Sending long prose prompts without identity/consistency locks.
- Analyzing video with a transcript-only tool and calling it visual analysis.
- Feeding 2+ hours of video into one context window.
- Making UGC look cinematic; polish is the tell.
- Generating before the prompt is right; each Seedance clip costs real money.
- Making claims in the rewritten script the product cannot back; keep ads truthful.

## Dated / volatile notes

- 2025 pipeline (dated): Flux 1.1 Pro Ultra images, Kling animation, ~10s clips chained. By 2026: Seedance 2.5 / Veo / Sora for video; Nano Banana Pro / GPT-Image for frames.
- Seedance 2.5 assessment and clone-a-winner: 2026-08; pricing ~$5/17s, ~$10/30s.
- "AI UGC passes as real to ~80% of viewers" and platform-risk claim: EP's assertions, 2026.
- Gemini analysis, editing workflows, articles→scripts: April 2025; 1M videos for ~$140 with Gemini 2.5 Flash.
- Human presenters over AI presenters: May 2025, likely superseded by 2026 realism.
- Tool names (Higgsfield CLI, makeugc, CapCut, Firecrawl) are snapshots.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `ai-image-and-visual-style-profiles` (starting frames, style profiles), `coding-agents-and-knowledge-systems` (automating the pipeline), `affiliate-traffic-playbooks`, and `direct-response-copywriting` (scripts).
