Source: https://www.eptwts.com/ai-as-leverage — EP (@eptwts) knowledge base, Chapter 06: AI as Leverage (scraped 2026-09-15). Lessons reproduced verbatim.

## Image Generation and Visual Content

**JSON style profiles are the master technique:**
feed reference images (ads, thumbnails, brand assets) to a model and have it extract the stylistic qualities - color palette, composition, character style, typography, textures, lighting, motifs, post-processing - into a structured JSON documenting only the design system, explicitly excluding specific subjects, logos, people, or brand names. Reuse the profile to generate new on-brand visuals for entirely different content; edit or merge profiles as needed. Variants: thumbnail profiles, brand-kit profiles for new products, and reusable "filter profiles" (extract the look, apply to a new image, iteratively ask it to update named qualities, save as a customizable filter). *posted March 2025 · practice might be outdated*

**Separate style from composition for maximum control:**
combine a JSON style profile with a rough visual layout - dump relevant PNGs into Canva/Photoshop/MS Paint arranged roughly as you want, export, and send the layout plus the JSON with "turn this into a finished image based on the profile." Far more control than any text prompt alone. *posted March 2025 · practice might be outdated*

**Sketch-to-finished-graphic:**
a hand-drawn sketch plus one structured prompt (set resolution, correct specific elements - "make the dollar bill a real $100 bill," remove labels, "let your creativity run wild but follow the instructions on the thumbnail") produces finished thumbnails; you can write instructions directly on the sketch. Current (2026) tool: Nano Banana Pro (run via Freepik with quality up) - extracts individual elements from existing thumbnails, turns paper sketches into finished logos/graphics, near-replacing thumbnail designers. *posted December 2025 · practice might be outdated*

**Prompt for imperfection to get realism:**
name a low-end camera, casual context, and explicitly ask for a noisy, authentic, non-cinematic look - e.g., "taken from an iPhone 6… noisy and look authentic not cinematic, this photo was lazily taken in the November cold." Polished defaults are what give AI away. *posted March 2025 · practice might be outdated*

**4o image-gen weaknesses and workarounds**
(2025-03): faces drift toward uncanny near-likenesses - train Flux on 5+ photos of your own face (krea.ai/train) for near-1:1 self-images; color grading biases orange/red - specify colors explicitly; text breaks - spell out exact text in the prompt; glitches - repair with Photoshop generative AI. Locked aspect ratios: add black bars to your sketch (62px bars yield exact 16:9), generate between them, crop after. Refused prompts: run the identical prompt through Sora - same image model, more lenient filtering. *posted April 2025 · practice might be outdated*

**Static-ad interview prompt:**
a legendary direct-response marketer persona gathers product, ideal customer, #1 problem solved, guarantee/USP, headline benefit and style (problem/benefit/question/direct), proof points, exact CTA, mood, visual style, and brand colors - then outputs an art-director brief (scene composition, lighting, camera angle, headline placement, text hierarchy, text-to-image balance) ready for an image model. *posted March 2025 · practice might be outdated*

**Adaptive image-interview prompt:**
before generating, the AI extracts the image in your head one question at a time, adapting by subject type (person → pose/expression/clothing; scene → perspective/time of day/weather) plus style, technical, mood, and use questions - wrapping within ~10 questions into a structured generation prompt. *posted April 2025 · practice might be outdated*

**Process infographics from one prompt:**
image models can generate complete step-by-step recipe/process infographics - specify view angle, layout, labels with exact quantities, connecting dotted lines with icons, and a final shot. Specificity is what makes it work. Chain tools for data-driven graphics: Perplexity extracts structured facts, ChatGPT renders them with formatting instructions ("1:1 grid, each time-slot its own box, no spelling mistakes"). *posted March 2025 · practice might be outdated*

**UI cloning with Claude Code (2026):**
Claude cannot extract accurate styling from screenshots alone but replicates given CSS very well. (1) Open dev tools on a UI you admire; copy the full CSS plus a screenshot. (2) "Rebuild the exact same UI design as the screenshot in a single html file, css attached." (3) Use VisBug to copy per-element CSS until pixel-perfect. (4) Have Claude generate a detailed style-guide markdown (palette, typography, spacing system, component styles, shadows, animations, radii, Tailwind usage, example components). (5) Drop that style guide into any project and Claude one-shots new pages in that style, even across context resets.

**One-shot branded decks (2026):**
paste content into Claude, invoke the pptx skill, attach a brand-style context profile - finished on-brand PowerPoint in a single prompt. *posted January 2026 · practice might be outdated*
