# Cinematic & Character Prompt Formula

Specialized for cinematic character-vehicle pipelines, editorial character-in-environment placement, action sequences, commercial keyframes, and moodboard-driven cinematic photography. The domain where **the character exists inside a cinematic world** — every element serves the story beat and the visual language of the piece.

**Key insight:** Cinematic images are built as compositional recipes, not scene descriptions. The image gen model responds to instructions ("low angle shot, camera near ground level, looking up at the subject") not observations ("the camera captures a dramatic view"). Every prompt is a build instruction — what to place where, how light hits each surface, what motion state the body is in.

## Categories (priority order)

### 1. Character-Vehicle Relationship & Proportion
**The spatial bond between rider and machine.** Scale relationship (how large is the character relative to the vehicle), physical contact points (where the body meets the machine), how the rider's posture adapts to the vehicle's geometry, proportional type extracted from reference sheets (not invented).

- Analyzer: study the contact sheet from every angle — map where the body sits, how limbs wrap around the vehicle, the scale ratio, mechanical details at contact points
- Enhancer: describe the relationship at the shot's scale — wide shots get silhouette and dominant proportions; close-ups get the specific surface where body meets machine
- Director: proportional relationship stays IDENTICAL across all outputs; adapt description detail to what each shot scale can actually see

### 2. Reference Fidelity & Lock
**Only what you can see exists.** Extract every detail from reference images (vehicle design, character garments, accessories, materials, colors) into a reference_lock BEFORE writing any prompt. The `visible_at_this_scale` filter prevents dumping every reference detail into every prompt regardless of shot scale. If a detail is not in the reference, it does not appear in the prompt. No invented clothing, vehicle parts, exposed anatomy, or accessories.

- Analyzer: fill the reference_lock — vehicle (shape language, surface materials with colors, mechanical details, proportions) and character (every garment top-to-bottom with exact color and material, every accessory, hair, skin tone, build)
- Enhancer: use ONLY locked details in the prompt; filter through visible_at_this_scale — wide shot mentions silhouette and dominant color, close-up mentions surface texture of one or two elements
- Director: reference_lock stays identical across outputs; visible_at_this_scale changes per shot

### 3. Composition & Camera Recipe
**Build instructions, not shot labels.** Open with the core visual concept in one sentence. Describe spatial relationships (foreground/midground/background, what is sharp, what is blurred). Name visual techniques (natural vignette through foreground framing, perspective distortion from low angle, silhouette against backlight). Give concrete pose instructions (weight, angle, gaze direction). Never open with a shot type label.

- Analyzer: identify the shot's spatial architecture — where is the camera, what fills each depth layer, what compositional technique creates visual interest
- Enhancer: write 3-4 sentences of compositional recipe — "The vehicle's nose extends forward out of frame. The rider's torso fills the right half. Everything beyond dissolves into directional streaks."
- Director: vary composition across outputs using validated shot types — silhouette, reflection, foreground frame, low angle, interaction, wide

### 4. Action & Motion State
**Transitional moments, not held poses.** Motion in a still image comes from capturing an unstable instant — the body mid-shift, weight transferring, fabric caught between two positions. "The rider is pressed flat" is a state (static). "The rider's shoulder drops as the vehicle banks, one knee lifting off the chassis" is a moment (kinetic). Describe what the body is doing at this instant, what forces act on fabric and hair, what environmental elements show speed or stillness.

- Analyzer: identify the action beat — is this pre-action tension, mid-action peak, or post-action settling? What physical forces are present?
- Enhancer: describe the transitional instant — body responding to forces (leaning into acceleration, bracing against turn), fabric reacting to airflow (trailing horizontally, pulling taut, lifting off shoulder), environment showing motion (directional ground smear, dust frozen mid-scatter, particle streaks)
- Director: vary the motion state across outputs — stillness with latent tension, moment of ignition, sustained velocity, aftermath

### 5. Lighting & Color Grading
**Light as physical behavior on specific surfaces, and color as creative weapon.** Light does not "illuminate" — it pounds, bleaches, rakes, catches, burns on the specific materials present. Color grading is not a technical catalog but a creative vision: what color swallows the world, what single accent breaks the palette, what tension defines the look. Every surface in the prompt must show the grade.

- Analyzer: extract light physics (direction, quality, color temperature) and the color story (dominant wash, accent that breaks it, shadow tint, highlight behavior) from moodboard references
- Enhancer: apply the grade to every named surface — "noon sun carves the white composite into a blown-out plane, shadow edges knife-sharp against crushed black"; describe light by how it hits specific materials, not by mood labels
- Director: color grading stays constant across all outputs in a sequence; it is extracted once from the moodboard and applied to every shot

### 6. Environment & Atmosphere
**The world the character inhabits.** Setting details (terrain, architecture, sky condition), atmospheric elements (dust, haze, heat shimmer, rain), depth and scale cues, time of day. Environment is described through generic object categories with options ("a doorway, archway, window frame, or gap between pillars"), not literal copies from reference images.

- Analyzer: extract setting characteristics — surfaces, depth layers, atmospheric conditions, scale markers
- Enhancer: describe environment relative to the character — what surrounds, what recedes, what atmospheric element adds life. One atmospheric detail per prompt, never stack multiple.
- Director: environment can stay constant (same setting, different angles/actions) or vary (same character in different worlds)

### 7. Surface Texture & Material Detail
**What light reveals at each scale.** Matte white composite catching noon sun as a flat blown-out plane. Scuffed brown leather with grain visible in raking light. Dark glass warping the horizon into a distorted panorama. Fabric creases frozen mid-snap. Dust grains casting pinpoint shadows on armor surface. Material description scales with shot distance — wide gets dominant finish, close-up gets micro-texture.

- Analyzer: identify material types and their light behavior — matte absorbs, glossy reflects, translucent transmits, textured creates micro-shadows
- Enhancer: write material-light interaction at the shot's scale level — close-ups describe the specific texture of whatever surface fills the frame; wide shots describe the dominant finish as blocks of tone
- Director: materials stay constant (same vehicle/character); detail level varies with shot scale

### 8. Directional Energy & Narrative Beat
**Where the next seconds go.** Every keyframe must be loaded with directional energy — the viewer feels what happens next. A static vehicle is never just sitting there: a hand on the throttle is anticipation, heat shimmer behind dormant thrusters is latent power. A vehicle at speed implies continued velocity. The narrative beat (tension, release, exhilaration, arrival) shapes what the frame emphasizes.

- Analyzer: identify the sequence intention — what this moment IS in the story arc (pre-flight tension, ignition, sustained chase, aftermath)
- Enhancer: embed the energy into visual details — "dust stirs beneath dormant thrusters, blue glow creeping into the exhaust ports" signals impending launch without stating it
- Director: vary narrative beats across the sequence — build from stillness through tension to release

### 9. Director & Film Reference Anchors
**Compression of visual language into 2-5 words.** "Cinematic photography inspired by Tarkovsky's Solaris" or "Inspired by Bruno Dumont" compresses color grade, atmosphere, grain, and framing philosophy. These anchors replace elaborate atmosphere and rendering specifications. They work especially well as closing lines that set the overall visual register.

- Analyzer: identify which cinematic reference best matches the moodboard's visual language
- Enhancer: close the prompt with a director/film reference — "Cinematic photography inspired by [Director]'s [Film]." This replaces generic "photorealistic cinematic widescreen frame."
- Director: film reference stays constant across all outputs in a sequence — it is the rendering anchor

### 10. Out-of-Frame Declarations
**What the shot crops.** For close-ups and tight compositions, explicitly describe what extends beyond the frame edges. "The vehicle's nose extends forward out of frame." "The coat hem disappears below the bottom edge." This prevents the image model from awkwardly fitting everything inside the frame, and produces more natural, cinematic compositions.

- Analyzer: identify which elements in the composition extend beyond frame boundaries
- Enhancer: state cropped elements as facts — "torso fills the right half, legs and vehicle underbody out of frame below"
- Director: out-of-frame declarations vary per shot — wide shots rarely need them, close-ups almost always do

## Mapping to Generic Formula

| Generic | Cinematic Equivalent | Notes |
|---------|---------------------|-------|
| Subject | Character-Vehicle Relationship + Reference Fidelity | Split: the subject is a relationship, and fidelity requires a lock mechanism |
| Composition | Composition & Camera Recipe + Out-of-Frame | Split: recipes replace labels, and cropping is an explicit concern |
| Environment | Environment & Atmosphere | Combined: atmospheric conditions are integral to cinematic environments |
| Lighting | Lighting & Color Grading | Merged: in cinematic work, color grade is inseparable from lighting |
| Color & Tone | *(absorbed into Lighting & Color Grading)* | Color grading subsumes color and tone as a unified creative weapon |
| Style | Director & Film Reference Anchors | Compressed: a film reference replaces elaborate style specifications |
| Technical Detail | Surface Texture & Material Detail | Same principle, adapted for cinematic scale-adaptive description |
| Reference Lock | Reference Fidelity & Lock | Promoted to #2: the lock mechanism is fundamental to cinematic work |

## Use Cases Served

- Cinematic character-vehicle pipelines (speeder bikes, motorcycles, mecha)
- Editorial character-in-environment placement
- Action sequence keyframe generation
- Commercial and trailer keyframes
- Moodboard-driven cinematic photography
- Multi-sequence video pre-production (keyframe + motion brief pipelines)
