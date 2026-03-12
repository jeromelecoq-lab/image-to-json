# Image to Json

An AI skill for Claude that extracts generation-ready JSON specs from reference images. Analyzes what's in the image, then rewrites every value into short, punchy, specific content that image models actually respond to.

## What it does

1. **Reads** one or more reference images
2. **Classifies** the domain (interior, product, fashion, UGC, food, cinematic, architectural)
3. **Extracts** a structured JSON skeleton with domain-appropriate categories
4. **Refines** interactively with the user — what do you want the output to be?
5. **Enhances** every value into generation-ready language (concrete nouns, build instructions, no filler)
6. **Outputs** a clean JSON spec ready for image generation models or Pletor workflows

Includes domain-specific prompt formulas for 8 image types, plus ad-specific prompt patterns for Amazon and Meta ad creatives.

## Install

### Claude.ai
1. Download or clone this repo
2. Zip the `extract-image/` folder
3. Go to Settings > Capabilities > Skills
4. Upload the zip

### Claude Code
Place the `extract-image/` folder in your project's `.claude/skills/` directory, or in `~/.claude/skills/` for global access.

## Usage

Provide one or more reference images:

```
Extract this image to JSON
```

```
Analyze these reference images — I want to reproduce this style
```

```
Image to JSON — make it more raw and editorial
```

```
Extract spec from these Amazon ad references
```

The skill will analyze the images, present a JSON skeleton, ask what you want to change, then sharpen every value into generation-ready content.

## Minimum input

- One or more reference images (file paths)

## Optional input

- Creative direction ("more cinematic", "raw UGC style", "golden hour")
- Specific changes ("make lighting warmer", "add fog")
- A complete brief of what you want
- Ad context (Amazon or Meta) for ad-specific prompt patterns

## What's inside

```
pletor-extract-image/
├── README.md                              # This file
├── extract-image/                         # The skill folder (uploadable unit)
│   ├── SKILL.md                          # Main skill definition
│   └── references/
│       ├── image-json-extractor.md       # Analyzer prompt (extraction reference)
│       ├── image-json-enhancer.md        # Enhancer prompt (word quality reference)
│       ├── prompts-formulas/
│       │   ├── INDEX.md                  # Formula index
│       │   ├── generic.md               # Universal fallback
│       │   ├── food-beverage.md
│       │   ├── interior-staging.md
│       │   ├── product-lifestyle.md
│       │   ├── architectural-exterior.md
│       │   ├── fashion-garment.md
│       │   ├── ugc-social.md
│       │   ├── cinematic-character.md
│       │   └── brief.md
│       └── ad-prompts/
│           ├── amazon-ads.md             # Amazon ad prompt patterns
│           └── meta-ads.md              # Meta ad prompt patterns
```

## Built by Pletor

AI-powered creative workflows for marketing teams.
