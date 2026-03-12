# Fashion & Garment Prompt Formula

Specialized for on-model garment try-on, fashion editorial, lookbook photography, e-commerce on-model shots. The domain where **the garment and the person wearing it are co-heroes** — neither exists without the other.

**Key insight:** Fashion photography is about the relationship between body and fabric. The garment's construction determines how it responds to the pose, the pose reveals the garment's character, and the model's presence sells the brand's casting archetype. Getting the character right (face geometry, skin rendering, grooming register) is as important as getting the garment right.

## Categories (priority order)

### 1. Garment Identity & Construction
**The garment, precisely described.** Silhouette, cut, fabric type and weight, color (specific hue, not "blue"), collar/neckline type, closure details (buttons, zippers, snaps), pocket presence or absence, seam lines, hem treatment, any distinctive construction features. NEGATIVE field: features explicitly absent ("NO chest pockets, NO hood, NO flap pockets").

- Analyzer: extract every construction attribute including a NEGATIVE list of absent features — this prevents hallucination of "typical" garment details
- Enhancer: lead with precise garment specs — "relaxed-fit band-collar linen shirt in pale sage, mother-of-pearl buttons, single chest patch pocket, curved hem, NO flap pockets, NO hood"
- Director: garment identity stays IDENTICAL across all outputs (this is the constant alongside character identity)

### 2. Model & Character Presence
**The person who wears it.** Casting archetype extracted from brand references (not an idealized face). Feature spacing, bone structure register, skin rendering level, grooming register, emotional register. Face geometry as generative instructions: proportional relationships ("eyes spaced slightly wider than one eye-width apart, set in shallow orbits"), not aesthetic labels ("beautiful almond eyes").

- Analyzer: map the brand's casting archetype — what proportional type do they cast? Feature spacing, jaw character, cheek volume, brow area, mouth-to-face ratio, skin treatment level, makeup register, hair treatment
- Enhancer: describe face geometry with spatial primitives — vertical thirds, bone prominence, skin texture level ("visible pores on nose and cheeks" not "flawless"), gender-appropriate vocabulary (curves for women, planes for men)
- Director: character identity stays IDENTICAL across all outputs; adapt description detail to shot scale

### 3. Pose & Body Language
**How the body holds the garment.** Weight distribution, spine line, shoulder position, hand placement, head tilt and turn. Transitional moments ("hand mid-reach toward collar") not held states ("hand on collar"). How the pose creates garment behavior — pulling, bunching, draping at joints.

- Analyzer: read the pose for its relationship to the garment — where does fabric pull, bunch, gap, drape?
- Enhancer: describe transitional body moments that reveal garment construction — "weight shifted to left hip, right hand lifting the hem, fabric pulling across the shoulder seam"
- Director: vary pose across outputs to show garment from different angles and in different body interactions

### 4. Fabric-Light Interaction
**How light reveals the material.** Crisp cotton catches light as flat planes. Soft linen absorbs it into diffuse glow. Silk pools light in its folds. Wool scatters it. Knit creates shadow rhythms between ridges. Each fabric type has a specific light behavior that the prompt must name.

- Analyzer: identify fabric type and describe how light behaves on it in the reference — sharp highlights or soft absorption, shadow depth in folds, sheen or matte
- Enhancer: write the light-fabric interaction — "overhead window light catches the starched collar as a crisp white plane, softens into a diffuse glow across the relaxed linen body, shadow gathers in the drape at the hip"
- Director: fabric-light interaction stays consistent (same fabric, same light behavior); vary the lighting direction/quality across outputs

### 5. Color Palette & Styling
**The complete look, anchored by the garment.** Garment color as palette anchor, complementary or tonal dressing (other garments, accessories), how colors relate across the full outfit. Styling details: tuck, roll, button count, sleeve push, layering order.

- Analyzer: inventory the complete outfit with specific color names and styling choices — half-tuck, sleeves rolled twice, top two buttons open
- Enhancer: build the palette from the garment outward — "pale sage linen shirt half-tucked into stone-washed indigo denim, tan leather belt, bare ankles in white canvas sneakers"
- Director: vary styling across outputs to show the same garment worn different ways (tucked vs untucked, layered vs solo, sleeves up vs down)

### 6. Skin & Texture Rendering
**Anti-airbrushing as a category.** AI image models default to plastic, waxy skin. Every fashion prompt must explicitly instruct natural skin texture: visible pores, subtle asymmetry, natural variation. Match the brand's retouching threshold from references — bare skin with texture, "no-makeup makeup", or editorial level.

- Analyzer: assess the brand's skin rendering standard — how much pore detail, how much imperfection, what retouching level
- Enhancer: always include in render instructions — "natural skin texture with visible pores, NOT airbrushed or waxy"; avoid smooth-skin triggers ("flawless", "porcelain", "glowing")
- Director: skin rendering stays consistent across outputs; this is a non-negotiable quality gate

### 7. Environment & Set
**Where the model stands.** Studio (seamless, textured wall, architectural element) or location (street, interior, outdoor). Background treatment: how much environment is visible, depth of field, whether the setting tells a story about the garment's context or stays neutral.

- Analyzer: identify setting type and its relationship to the fashion story — editorial location, commercial studio, lifestyle context
- Enhancer: describe environment relative to the garment story — "sun-bleached stone courtyard with Mediterranean textures echoing the linen's relaxed register"
- Director: vary environment across outputs (same model and garment in studio, street, interior, outdoor)

### 8. Composition & Camera
**How the frame serves the garment.** Framing that shows the garment's key features (full-length for silhouette, three-quarter for fit, close-up for fabric detail). Camera angle relative to the face (slightly above softens the jaw for women, eye-level shows true proportions, below strengthens jawline). Lens choice (85mm flatters, 50mm is editorial, 135mm isolates).

- Analyzer: identify what the composition prioritizes — full garment, detail, or lifestyle context
- Enhancer: specify framing and camera angle with reasoning — "three-quarter crop from mid-thigh, camera at eye level to preserve natural jaw proportion, 85mm compression"
- Director: vary composition across outputs (full-length editorial, mid-crop commercial, detail close-up, environmental wide)

### 9. Mood & Editorial Register
**The emotional temperature.** Quietly detached (high fashion), warm and approachable (commercial), sharp and present (streetwear), intimate and candid (lifestyle). The mood must match the brand's casting archetype energy — if references show detached expressions, do not generate warm smiles.

- Analyzer: read the brand's emotional register from reference faces — what energy do they consistently project?
- Enhancer: convey mood through expression and body language specifics, not abstract labels — "gaze directed past camera-left, lips barely parted, jaw relaxed" not "mysterious mood"
- Director: mood stays consistent within a campaign; the brand's casting archetype sets the register

### 10. Hair as Physical Material
**How hair behaves in the shot.** Color as specific hue ("medium ash brown with warm highlights at the crown"), texture as physics (fine strands that fall flat, dense waves that hold volume, tight coils that catch light at each peak), how light moves through it, how gravity and wind affect it, how it frames the face and interacts with the garment's neckline.

- Analyzer: describe hair by its physical behavior — weight, movement, light interaction, texture pattern
- Enhancer: write hair as material — "dense chestnut waves falling past the collar, single broad highlight band across the crown where overhead light catches the wave peaks"
- Director: hair stays consistent across outputs; styling can vary slightly (down, half-up, tucked behind ear)

## Mapping to Generic Formula

| Generic | Fashion Equivalent | Notes |
|---------|-------------------|-------|
| Subject | Garment Identity + Model & Character Presence | Split: garment and person are co-heroes with distinct extraction needs |
| Composition | Composition & Camera | Reframed around how framing serves the garment |
| Environment | Environment & Set | Narrowed to fashion-relevant settings |
| Lighting | Fabric-Light Interaction | Reframed: light exists to reveal fabric character |
| Color & Tone | Color Palette & Styling | Expanded to include full outfit styling |
| Style | Mood & Editorial Register | Narrowed to fashion's emotional vocabulary |
| Technical Detail | Skin & Texture Rendering + Hair as Material | Split: skin realism and hair physics are distinct craft concerns |
| Reference Lock | *(same as generic)* | Unchanged |

## Use Cases Served

- On-model garment try-on
- Fashion editorial photography
- Lookbook and e-commerce on-model shots
- Character generation for fashion brands
- Pose transfer with garment fidelity
- Brand casting archetype matching
