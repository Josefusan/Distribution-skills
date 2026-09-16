Source: https://www.eptwts.com/ai-as-leverage — EP (@eptwts) knowledge base, Chapter 06: AI as Leverage (scraped 2026-09-15). Lessons reproduced verbatim.

## AI Video and UGC Production

**The 2025 pipeline (dated):**
Flux 1.1 Pro Ultra for images to animate, Kling for animation, chaining ~10-second clips since nothing longer was economical. For storyline consistency, have an LLM write the sequential image prompts following the storyline, generate each image, then animate each. By 2026 the stack moved to Seedance 2.5 / Veo / Sora for video and Nano Banana Pro / GPT-Image for frames.

**Seedance 2.5 honest assessment (2026-08):**
shockingly realistic - near-solved realism for UGC - and excellent at following instructions, but expensive (~$5 per 17-second clip, ~$10 per 30 seconds; get the prompt right so you one-shot it) and still bad at rendering text - add captions and overlays yourself in an editor.

**AI UGC works commercially:**
AI-generated UGC passes as real to roughly 80% of viewers, collapsing creative costs. Platform risk is low: TikTok's parent built Seedance and Meta ships AI creative tools - they will not ban AI content. And for openly-AI entertainment content, the viral secret is the opposite of hiding it: make it as absurd and obviously AI as possible ("no way this is real") - audiences accept fantasy like they accept VFX.

**The clone-a-winner assembly line (2026-08, my flagship workflow):**
(1) give your agent a short-form content research API and pull ~100 videos promoting products like yours; (2) pick one that fits; (3) have the agent extract ALL context via a video-analysis tool (Higgsfield CLI has one built in) into a structured markdown - scenes, motions, appearance, mannerisms, accents, tone; (4) generate candidate starting frames via the CLI and pick the best; (5) rewrite the context so it promotes YOUR product; (6) send rewritten context plus starting frame to Seedance 2.5. I get ~80% first-try success. Ten-minute variant: research agent finds references → Gemini 2.5 Flash produces a scene-by-scene analysis with image-reference placeholders → GPT-image-2 recreates a frame per cut-scene → Higgsfield video generation with Seedance → human editor adds captions, cuts, zooms, music.

**Fully automated viral-video cloning with Claude Code:**
query a TikTok research API for a niche filtered to 100k+ views, outliers, and sales intent; one project folder per video; download with yt-dlp; PySceneDetect splits scenes at hard cuts; ffmpeg grabs each scene's start frame ~0.08s past the cut (avoiding transition motion blur) plus mid/end frames; Gemini API analyzes hook, pacing, structure, and why it converts as structured JSON; Claude Code writes one generation prompt per scene; each start frame + prompt goes to Seedance image-to-video.

**Segment-assembly UGC:**
realistic UGC videos are chains of 4-8 second clips, each from a starting-frame image plus a short prompt. Get frames by screenshotting real TikTok UGC and having an image model change the person's appearance; prompt template: "extend this video and make her say this (make sure she is very expressive and enthusiastic): {script}". Expect a few generations per segment; compile in CapCut. Avatar-tool alternative (makeugc): input script, pick or create an avatar (including product-in-hand), iterate on script and tone - good enough to run as traffic creatives.

**The green-screen format:**
generate a still of a presenter in the bottom corner with a green screen behind them (prompt for organic, hand-held, imperfect quality), animate with Seedance 2.5 plus the script, then chroma-key any screenshot in as the background - endlessly reusable for selling almost anything.

**Anatomy of a professional AI video prompt**
(from Higgsfield's open-sourced packs): style prefix (film stock, lens, color grading, director-style camera language); shot-mode declaration (multi-shot montage, hard cuts); image references with explicit identity/wardrobe locks; a global consistency-lock section (what must never change between shots); diegetic sound and lip-synced dialogue per shot; per-shot camera and framing direction; and a long negative-prompt list (no watermark, no wardrobe change, no lip-sync drift, no morphing). Copy the scaffold. Career path: study these open-sourced packs, practice in Cinema Studio, make trend-tied shorts, network with AI filmmakers - corporate deals in the space are large.

**Gemini is the video-analysis model, full stop.**
Google has by far the best vision model regardless of benchmarks (it deciphers 200-year-old Kurrentschrift handwriting other models fail on) - judge multimodal models by hard real-world tests, not leaderboards. Gemini sees a YouTube video's actual visuals (and Google-private data), not just the transcript like Perplexity. Non-YouTube videos (reels, TikToks, VSLs): rip the file and upload to a private YouTube account, then feed the link. Screen recordings work too - it extracts structured data from any on-screen workflow. Limit: ~2 hours of video floods the context window; chunk into 1-2 hour segments (use AI Studio for this). At scale: give Claude a Gemini 2.5 Flash API key - I analyzed over 1 million videos this way for about $140 total.

**Gemini editing workflows:**
extract an "editing-style profile" JSON from a well-edited reference video, upload your raw footage to a private YouTube account, and ask for a breakdown of cuts, VFX, and transitions with exact timestamps - or use the profile as a manual that makes a human editor faster and cheaper. Retention reverse-engineering: extract shot-by-shot profiles (script, visuals, SFX, mood) from successful videos, ask Gemini for the key retention strategies, build a profile of your own channel, and request an implementation manual. Wrapper opportunity: Gemini video-analysis apps are far less crowded than image-gen wrappers because even daily AI users don't know Gemini processes visuals. *posted April 2025 · practice might be outdated*

**Articles → video scripts:**
scrape articles with Firecrawl, extract a "script profile" from a proven video in your niche (pacing, storytelling, retention), then have an LLM write a script pulling information from the articles in the style of the profile. Automatable via the Firecrawl MCP server. *posted April 2025 · practice might be outdated*

**Scaling expert content without cloning the expert:**
put the expert's wisdom into a knowledge base, build an AI system that pulls topics from it to generate scripts, then hire and train human presenters - multiple lead-generating channels hands-off (recommended in 2025 over full AI presenters, which weren't convincing yet). *posted May 2025 · practice might be outdated*
