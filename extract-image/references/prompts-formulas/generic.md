# Generic Prompt Formula

The universal fallback. Works for any photorealistic image generation. Domain formulas specialize this by reordering, replacing, or adding categories.

## Categories (priority order)

### 1. Subject
**What's in the frame.** Type, count, arrangement, physical details (colors, materials, textures, proportions), pose or staging, action or state.

- Analyzer: identify and describe the primary subject(s) with precise physical attributes
- Enhancer: lead with subject — this anchors the entire image
- Director: subject stays consistent across outputs (unless the brief says otherwise)

### 2. Composition
**How the frame is arranged.** Shot type (close-up, medium, wide), camera angle (eye-level, elevated, low), depth of field, spatial arrangement (centered, off-center, diagonal), what's in vs out of frame.

- Analyzer: identify framing, spatial relationships, foreground/background layers
- Enhancer: specify framing concretely — "occupying the lower two-thirds, centered"
- Director: vary composition across outputs (wide establishing → mid → close-up detail)

### 3. Environment
**The setting.** Background treatment, surface the subject sits on, surrounding elements, props, atmospheric conditions (fog, rain, dust), time of day, indoor/outdoor.

- Analyzer: extract setting details, surface materials, atmospheric conditions
- Enhancer: describe environment relative to subject — what supports the subject, what recedes
- Director: environment can vary (same subject in different settings) or stay constant (same setting, different angles)

### 4. Lighting
**Light behavior.** Source direction, quality (hard/soft), color temperature, shadow behavior, how light interacts with surfaces (catchlights, reflections, rim light, specular highlights).

- Analyzer: identify light source, direction, temperature, shadow quality
- Enhancer: specify concretely — "warm golden-hour sidelight from camera-left, soft ambient fill"
- Director: lighting usually stays consistent across outputs (unless creative brief varies it)

### 5. Color & Tone
**The palette.** Dominant colors, color temperature, contrast level, color grading, harmony (complementary, analogous, monochromatic).

- Analyzer: extract dominant palette and color relationships
- Enhancer: name specific colors — "deep navy blue with subtle teal undertones" not "blue"
- Director: palette usually stays consistent within a campaign/series

### 6. Style
**Visual rendering approach.** Always starts with "Photorealistic photograph" + type (editorial, studio, commercial, documentary). Includes texture quality (clean digital, film grain), mood qualifiers.

- Analyzer: identify the photographic genre and treatment
- Enhancer: set once, keep concise — "Photorealistic editorial photograph, clean digital rendering"
- Director: style stays constant across outputs (brand consistency)

### 7. Technical Detail
**Surface-level precision.** Material finishes, texture resolution, fine details (stitching, grain, reflections), manufacturing quality cues.

- Analyzer: zoom into material-level details the image model needs to reproduce
- Enhancer: add only when the subject demands it (product shots, garments, surfaces)
- Director: detail level can vary by zoom (wide = less, close-up = more)

### 8. Reference Lock
**How to use provided reference images.** What to match (appearance, proportions, materials, colors), what's flexible, how to handle the reference instruction.

- Analyzer: compare reference to brief — what matches, what the brief overrides
- Enhancer: when reference exists, lead with "Use the reference image to match [specifics]"
- Director: reference instruction stays identical across all outputs

## Notes

- Categories 1-4 are almost always present in any prompt
- Categories 5-8 are included when the brief or domain demands specificity
- This generic formula maps directly to the existing `image-prompt-enhancer-json` template fields: reference → Reference Lock, subject → Subject, environment → Environment, lighting → Lighting, camera → Composition, style → Style
