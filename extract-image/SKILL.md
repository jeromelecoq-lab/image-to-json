---
name: extract-image
description: >
  Extract a generation-ready JSON spec from reference images, then refine the
  words interactively with the user. Two-step process: (1) extract JSON structure
  with categories adapted to the image, (2) fill categories with short, punchy,
  generation-ready content based on user direction. Use when user says "extract image",
  "image to JSON", "analyze this image", "reproduce this image", "extract spec",
  "image JSON", "extract from these images".
metadata:
  author: Pletor
  version: 1.0.0
---

# Extract Image

You extract structured JSON specs from reference images, then refine the content interactively with the user. The goal: a generation-ready JSON where every value uses the RIGHT words — short, punchy, specific content that image models respond to.

**The core insight:** Same JSON structure with different words produces wildly different results. "raw iphone mirror selfie, wet hair, steamy bathroom atmosphere" beats "authentic social media aesthetic, candid lifestyle photography" every time.

## Process

### Step 1 — Get Images

Read the user-provided image(s). Accept one or more file paths. If no images were provided, ask for them.

### Step 2 — Load Knowledge

Read these files to guide your extraction:

1. `references/image-json-extractor.md` — the Analyzer system prompt (your reference for extraction)
2. `references/prompts-formulas/INDEX.md` — check which domain formula matches
3. Read the matching formula file from `references/prompts-formulas/{domain}.md` (or `generic.md` if no match)

### Step 3 — Extract (Analyzer Role)

Following the Extractor prompt's 3-stage process:

**Stage 1 — Visual Fingerprint:** What 3-5 visual forces define this image/set? For multiple images, find the unified thread. Classify the domain (interior, product, fashion, UGC, food, cinematic, architectural, general).

**Stage 2 — Category Selection:** Pick 6-10 categories using the domain formula as scaffold. Merge, split, rename as needed for THIS specific image. Name categories with precise snake_case keys.

**Stage 3 — Descriptive Extraction:** Write concise, factual values for each category. Document what IS in the image(s). Concrete nouns, material names, hex colors. No creative direction yet.

**Present the JSON skeleton to the user.**

### Step 4 — Refine with User

Ask the user: "What do you want your image to be? You can:
- Keep categories as-is and I'll sharpen the words
- Change specific values (e.g., 'make lighting golden hour')
- Add or remove categories
- Describe a creative direction shift (e.g., 'more raw', 'more editorial')
- Give me a complete brief of what you want"

This is the critical step. The user defines what they WANT, not just what's in the reference.

### Step 4b — Ad-Specific Awareness (Optional)

If the user is extracting from ad reference images, creating ad creatives, or mentions Amazon/Meta ads:

- For **Amazon ads**: read `references/ad-prompts/amazon-ads.md` for domain-specific prompt patterns (composed layouts, text treatment, style anchors, the 5-objective framework)
- For **Meta ads**: read `references/ad-prompts/meta-ads.md` for domain-specific prompt patterns (full-bleed photography, text-on-image treatment, hook angles, anti-stock-photo rules)

Use these as style references when enhancing the JSON in Step 5 — they inform how to write generation-ready values that produce high-performing ad creatives rather than generic product shots.

### Step 5 — Enhance (Enhancer Role)

Following the Enhancer prompt's rules, read `references/image-json-enhancer.md` for reference.

Rewrite every value applying the Word Quality Rules:

1. **Short and punchy** — "foggy mirror" not "slight steam on the corner of the glass shower door"
2. **Concrete nouns** — "marble sink" not "modern bathroom fixtures"
3. **Direct action** — "playful teasing glance over shoulder" not "relaxed facial features, soft natural gaze"
4. **One strong word beats three weak ones** — "instagram model" not "naturally stunning, fit and athletic build"
5. **No filler adjectives** — "ultra photorealistic" not "hyper-realistic, high-fidelity photographic quality"
6. **Build instructions** — "soft warm bathroom lighting, highlights on damp skin" not "the lighting creates a dramatic mood"

Add a `prompt` field: 2-4 sentence standalone generation prompt covering camera, subject, scene, lighting, atmosphere.

**Present the final JSON to the user.**

### Step 6 — Iterate

If the user wants changes, refine specific categories while maintaining word quality. Repeat until the user is satisfied.

### Step 7 — Output

When approved, output the clean final JSON. Mention this can be used as:
- Direct input to an image generation model
- Text input to an enhancer node in a Pletor workflow
- Reference spec for building a full workflow

## Word Quality Reference Card

| Rule | Bad (verbose/generic) | Good (punchy/specific) |
|------|----------------------|----------------------|
| Short over long | "authentic social media aesthetic, candid lifestyle photography" | "raw iphone mirror selfie, subtle sensor noise" |
| Concrete nouns | "modern bathroom fixtures and accessories" | "marble sink, foggy mirror" |
| Direct action | "relaxed facial features, soft natural gaze, hint of a smile" | "playful teasing glance over shoulder" |
| No hedging | "naturally stunning, fit and athletic build" | "instagram model" |
| Fewer words | "slight steam on the corner of the glass shower door" | "foggy mirror" |
| No filler | "hyper-realistic, high-fidelity photographic quality" | "ultra photorealistic" |
| Build instruction | "the lighting creates a dramatic mood with shadows" | "soft warm bathroom lighting, highlights on damp skin" |
| No marketing | "elevated, curated, aspirational lifestyle" | "clean minimalist, warm light, natural textures" |
