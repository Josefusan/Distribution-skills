---
name: ai-image-and-visual-style-profiles
description: Extract a reusable JSON visual style profile from reference images and use it to generate on-brand thumbnails, ads, infographics, UI, and decks with image models. Use when the user says "make this look like our brand", "generate a thumbnail / ad creative / infographic", "clone this style", "my AI images look fake or too polished", "the text in my AI image is broken", "turn my sketch into a graphic", "rebuild this UI", "make a branded deck", or shares reference visuals and wants more in the same look.
---

# AI Image and Visual Style Profiles

Distilled from EP's (@eptwts) knowledge base, eptwts.com. These are EP's opinionated operator heuristics, not universal facts.

This skill helps you separate style from subject: extract the design system of any set of references into a JSON profile, then combine it with a rough layout or interview-derived brief to generate consistent on-brand assets. Core thesis: JSON style profiles are the master technique; a profile plus a rough composition gives far more control than any text prompt alone.

## When to use

- The user needs many visuals in one consistent look (thumbnails, ads, brand assets).
- The user has references they like and wants new content in that style.
- The user wants realistic (non-AI-looking) images.
- The user is building a static ad and does not know what to ask for.
- The user wants a process/recipe infographic or data graphic.
- The user wants to replicate a UI or produce a branded PowerPoint.

## Core principles

**Extract the design system, exclude the subject.** Feed references to a model and have it document palette, composition, character style, typography, textures, lighting, motifs, post-processing in JSON, explicitly excluding specific subjects, logos, people, or brand names. Reuse the profile for entirely different content; edit or merge profiles freely.

**Separate style from composition.** Rough-arrange PNGs in Canva/Photoshop/MS Paint, export, and send the layout plus the JSON with "turn this into a finished image based on the profile."

**A sketch plus one structured prompt yields a finished graphic.** Set resolution, correct specific elements ("make the dollar bill a real $100 bill"), remove labels, "let your creativity run wild but follow the instructions on the thumbnail." You can write instructions directly on the sketch.

**Prompt for imperfection to get realism.** Name a low-end camera, casual context, and ask for noisy, authentic, non-cinematic output; polished defaults are what give AI away.

**Interview before generating.** Both the static-ad brief and the adaptive image interview extract the picture in the user's head one question at a time, then output a structured generation prompt.

**Specificity makes infographics work.** View angle, layout, labels with exact quantities, connecting dotted lines with icons, final shot. Chain tools for data graphics: one tool extracts structured facts, the image model renders with formatting rules.

**Models replicate CSS, not screenshots.** Claude cannot extract accurate styling from a screenshot alone but reproduces given CSS very well; copy the CSS, then generate a style-guide markdown that lets it one-shot future pages.

**Reusable filter profiles.** Extract a look, apply it to a new image, iteratively ask to update named qualities, save as a customizable filter.

## Workflow

1. **Collect 3-10 references** that share the look the user wants (ads, thumbnails, brand assets, a competitor's style).
2. **Extract the style profile.** Run the extraction prompt below on a vision model. Review: strip any subject/logo/person/brand that leaked in. Save as `style-profile.json`. Make variants (thumbnail profile, brand-kit profile) if needed.
3. **Define the composition separately.**
   - If layout matters: rough-arrange elements in any editor, export a PNG, or hand-draw a sketch with written instructions.
   - If the user is unsure what they want: run the Adaptive Image Interview (~10 questions) or, for ads, the Static-Ad Interview to get an art-director brief.
4. **Generate.** Send layout/sketch + JSON profile + brief. For realism, add the imperfection clause. Spell out exact text strings; specify colors explicitly.
5. **Iterate by named qualities.** "Keep everything, change lighting to X"; update the profile when a change should persist.
6. **Repair, do not regenerate.** Fix small glitches or text in an editor with generative fill.
7. **Special cases:**
   - Infographic → the process-infographic prompt; for data graphics chain a research tool for facts then the image model with formatting rules.
   - UI clone → 5-step Claude Code procedure below, ending in a style-guide markdown.
   - Deck → paste content, invoke the pptx skill, attach the brand-style profile (2026).

## Checklists / templates

### JSON style profile template

```json
{
  "profile_name": "",
  "color_palette": {
    "primary": [], "secondary": [], "accents": [], "backgrounds": [],
    "contrast_level": "", "grading_bias": ""
  },
  "composition": {
    "layout_patterns": [], "focal_point_rules": "", "negative_space": "",
    "aspect_ratios": [], "framing": ""
  },
  "character_style": {
    "rendering": "", "proportions": "", "expression_style": "", "poses": []
  },
  "typography": {
    "headline_style": "", "weight": "", "case": "", "placement": "",
    "effects": [], "text_to_image_balance": ""
  },
  "textures": [],
  "lighting": {"type": "", "direction": "", "mood": "", "shadows": ""},
  "motifs": [],
  "post_processing": {"grain": "", "sharpness": "", "vignette": "", "filters": []},
  "exclusions": "No specific subjects, logos, people, or brand names are recorded in this profile."
}
```

### Style-extraction prompt

```
Analyze the attached reference images. Extract only the shared design system into the JSON schema below: color palette, composition, character style, typography, textures, lighting, motifs, post-processing. Do NOT record specific subjects, logos, people, or brand names. Output valid JSON only.
[paste schema]
```

### Generation call

```
<style_profile>{paste JSON}</style_profile>
Attached: my rough layout / sketch. Turn this into a finished image based on the profile. Resolution: [W x H]. Exact text to render: "[...]". Corrections: [...]. Let your creativity run wild but follow the instructions on the sketch.
```

### Realism clause

"Taken from an iPhone 6, casual snapshot, noisy and authentic, not cinematic; this photo was lazily taken in the November cold." Adapt camera, context, and weather to the scene.

### Static-Ad Interview prompt

```
You are a legendary direct-response marketer and art director. Interview me one question at a time to gather: the product; ideal customer; the #1 problem it solves; guarantee or USP; headline benefit and headline style (problem / benefit / question / direct); proof points; exact CTA; mood; visual style; brand colors.
Then output an art-director brief ready for an image model: scene composition; lighting; camera angle; headline placement; text hierarchy; text-to-image balance; exact text strings.
```

### Adaptive Image Interview prompt

```
Before generating anything, extract the image in my head one question at a time. Adapt to the subject type: if a person, ask pose, expression, clothing; if a scene, ask perspective, time of day, weather. Then ask style, technical (resolution, aspect ratio, camera), mood, and intended use. Wrap up within about 10 questions and output a single structured generation prompt.
```

### Process infographic prompt scaffold

"Generate a complete step-by-step [recipe/process] infographic. View angle: [top-down]. Layout: [grid/vertical flow]. Label each step with exact quantities/values. Connect steps with dotted lines and icons. End with a final shot of the result. No spelling mistakes." For data: "1:1 grid, each [time-slot] its own box, no spelling mistakes."

### UI cloning with Claude Code (5 steps, 2026)

1. Open dev tools on the UI you admire; copy the full CSS plus a screenshot.
2. "Rebuild the exact same UI design as the screenshot in a single html file, css attached."
3. Use VisBug to copy per-element CSS until pixel-perfect.
4. Have Claude generate a detailed style-guide markdown: palette, typography, spacing system, component styles, shadows, animations, radii, Tailwind usage, example components.
5. Drop that style guide into any project; Claude one-shots new pages in that style, even across context resets.

### One-shot branded deck (2026)

Paste content into Claude → invoke the pptx skill → attach the brand-style context profile → finished on-brand PowerPoint in one prompt.

## Anti-patterns

- Letting subjects, logos, people, or brand names into the style profile (it stops being reusable and can reproduce others' marks).
- Describing layout in prose when a rough PNG or sketch would do.
- Accepting polished, cinematic defaults for content meant to look real.
- Leaving text to the model without spelling it out exactly.
- Regenerating the whole image to fix a small glitch.
- Expecting a model to extract exact styling from a screenshot alone; give it CSS.
- Cloning a specific brand's identity rather than a generic look; use profiles for your own brand system.

## Dated / volatile notes

- JSON style profiles, style/composition separation, imperfection prompt, static-ad interview, infographics: March 2025, practice might be outdated.
- Adaptive interview: April 2025.
- 4o image-gen weaknesses and workarounds (2025-03/04, dated): faces drift to uncanny near-likenesses (train Flux on 5+ photos at krea.ai/train); orange/red grading bias (specify colors); broken text (spell it out); glitches (Photoshop generative fill); locked aspect ratios (add black bars to the sketch, 62px bars yield 16:9, crop after); refused prompts re-run through Sora. Many of these are likely fixed in current models.
- Sketch-to-graphic current tool (December 2025): Nano Banana Pro via Freepik with quality up.
- UI cloning and one-shot decks: 2026 / January 2026.

## Read next

For the full verbatim lessons see `references/source-lessons.md`. Pairs with `context-engineering-profiles` (profile storage), `ai-ugc-video-production` (starting frames for video), `direct-response-copywriting` (ad copy), and `platform-strategy-and-youtube-mechanics` (thumbnails).
