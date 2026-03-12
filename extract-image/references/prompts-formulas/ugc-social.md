# UGC & Social Prompt Formula

Specialized for user-generated content, social media creatives, influencer-style photography, selfie grids, and casual lifestyle imagery. The domain where **authenticity is the product** — every technical choice must break the "AI-generated" signal and replicate the feel of real people with real phones.

**Key insight:** UGC photography succeeds by what it gets wrong. The imperfect framing, the auto-exposure shifts, the slight motion blur, the deep focus from a wide front camera — these are not flaws to minimize but artifacts to reproduce. A UGC image that looks too polished has failed.

## Categories (priority order)

### 1. Authenticity & Device Artifacts
**The iPhone fingerprint.** Specific computational photography artifacts that signal "real phone, real person": Smart HDR feel (lifted shadows, controlled highlights), slight computational sharpening on hair edges and fabric texture, mild JPEG compression blocking in gradients, auto white-balance shifts between scenes (warm indoors, green under fluorescent, cool in shade), rolling-shutter wobble on walking shots, high ISO grain in low light, occasional lens smudge haze from fingerprints on the front camera.

- Analyzer: identify which device artifacts are appropriate for the scene's lighting and motion conditions
- Enhancer: layer 2-3 artifacts per frame from the menu — a sunny outdoor selfie gets Smart HDR + slight sharpening; a dim bar shot gets high ISO noise + auto-WB shift + mild compression
- Director: vary artifacts across frames to prevent the grid from looking uniformly processed; each frame gets a scene-appropriate artifact set

### 2. Character & Avatar Consistency
**The same real person in every frame.** Extract a highly specific physical description from the reference photo — skin tone, face shape, hair (color, length, texture, style), eyes, lips, distinguishing features, visible accessories, current outfit. Embed this description verbatim in every frame prompt. The description must be specific enough that someone could identify the person from text alone.

- Analyzer: extract a forensic-level physical description — "a late-teens Black man with very dark rich skin, high cheekbones, full lips, short textured afro sponge twists tapered on the sides, small stud earring in left earlobe, thin silver chain necklace"
- Enhancer: embed the full description in every prompt — repetition is intentional and required for cross-frame identity consistency
- Director: character stays IDENTICAL across all outputs; wardrobe and accessories can vary between frames

### 3. Scene & Location
**Real places, not sets.** Lived-in bedrooms, grocery store aisles, coffee shops, public transit, park benches, gym locker rooms, kitchen counters, sidewalks. Backgrounds must be readable (deep focus) and contain real-world clutter — messy beds, visible shelves, other people, everyday objects. Nothing staged, no seamless backdrops.

- Analyzer: identify the scene's everyday authenticity — what makes this feel like a real place vs a staged set?
- Enhancer: name specific location details — "small bathroom with warm overhead light, sink and towel rack visible, slightly messy counter" not "bathroom"
- Director: vary locations across frames for lifestyle diversity — mix indoor/outdoor, day/night, moving/static, public/private

### 4. Action & Candid Moment
**Mid-action, not posed.** The person is doing something real — mid-laugh, reacting to something off-screen, adjusting hair, flipping a page, walking, cooking, checking an outfit. Micro-expressions (squinting in sun, tired on transit, half-smile at phone). Imperfect body positioning — not centered, not square to camera, not perfectly composed.

- Analyzer: identify the specific moment being captured — what was the person doing 0.5 seconds before and after?
- Enhancer: describe the candid instant — "mid-sentence candid mouth shape, eyes glancing past the camera at something" not "smiling at camera"
- Director: vary the type of moment across frames — some static (sitting), some in motion (walking), some interactive (cooking, studying), some reflexive (checking mirror)

### 5. Composition & Framing Imperfections
**How a non-photographer frames a shot.** Arm's-length wide angle, slightly off-center subject, tilted horizons, partial head crop, too-close framing cutting shoulders, phone visible in mirror shots covering part of face. These imperfections signal authenticity — a perfectly composed UGC shot reads as fake.

- Analyzer: identify which framing imperfections match the shot type (selfie, mirror, propped phone, someone else's phone)
- Enhancer: specify 1-2 framing flaws per frame — "imperfect framing with background tilted, arm's-length wide angle cutting a bit of hair on the right"
- Director: vary the type of framing imperfection — not every frame should be tilted, not every frame should crop the head

### 6. Color & Lighting Conditions
**Everyday ambient light only.** Window light, room light, street shade, golden hour, fluorescent overhead, dim lamp at night. NO studio lighting, NO flash, NO ring light, NO softbox. Color temperature shifts naturally between locations — warm indoors, cool in shade, mixed under fluorescent. The lighting is whatever the location provides, not what a photographer would set up.

- Analyzer: match the lighting to what the real location would produce at that time of day
- Enhancer: name the specific ambient source — "warm desk lamp plus ambient room light, visible low-light grain" not "indoor lighting"
- Director: vary lighting naturally across the frame set — morning outdoor, midday shade, afternoon indoor, evening dim, night low-light

### 7. Wardrobe & Props
**What real people actually wear and carry.** Casual, everyday clothing — hoodies, jeans, sneakers, athleisure. Minimal or no makeup. Real-life hair (not salon-fresh). Props are everyday objects — coffee cups, phones, bags, books, grocery items, umbrellas. Wardrobe can change across frames but stays within the same casual register.

- Analyzer: inventory the reference photo outfit as the "anchor" wardrobe; plan 2-3 casual variations across the frame set
- Enhancer: describe wardrobe specifically — "oversized grey crewneck hoodie, black leggings, white running shoes" not "casual outfit"
- Director: keep the anchor outfit for several frames, then introduce natural wardrobe changes; props should match the scene (spatula in kitchen, book at desk)

### 8. Depth of Field & Focus
**Deep focus is mandatory.** iPhone front cameras (~24-28mm equiv) produce deep focus where backgrounds stay readable. Image gen models default to portrait-mode bokeh because most training data features this. Every frame must enforce: "deep focus / no artificial blur." Backgrounds can be slightly soft only from real distance or motion, never from computational blur.

- Analyzer: verify that no prompt triggers shallow DOF — flag "bokeh", "portrait mode", "blurred background" as violations
- Enhancer: enforce in every prompt — "deep focus smartphone DOF (background stays readable, not blurred)" plus negation in avoid list
- Director: depth of field stays constant across all frames — this is a non-negotiable constraint, not a creative variable

### 9. Platform Format & Grid Structure
**How the content is consumed.** Contact sheet layout (4x4 = 16 frames), aspect ratio appropriate for platform (9:16 for Stories/TikTok, 1:1 for feed, 4:5 for Instagram). Global style rules enforce consistency across frames while per-frame prompts handle scene variation. Scene selection balances mandatory user scenes with complementary everyday fills.

- Analyzer: identify the target platform and its format requirements
- Enhancer: structure as JSON scaffold with global_style_rules (device look, focus rules, character consistency, avoid list) and per-frame prompts
- Director: ensure the 16-frame set tells a coherent lifestyle story — chronological day, highlights reel, or thematic collection

### 10. Visual DNA (Style Fingerprinting)
**When reference images define the style.** Extract the complete visual fingerprint before writing any prompts: film stock/sensor feel, color temperature and palette, grain and texture, flash behavior, depth of field character, compositional patterns, energy and mood. Output as a dense paragraph that flows into every downstream frame prompt.

- Analyzer: run Visual DNA extraction — identify the signature processing, palette, grain, flash, and compositional language of the reference set
- Enhancer: lead with the DNA paragraph — "Late-night flash photography, raw party energy, on-camera flash with deep black backgrounds, warm skin tones against cool night air, heavy film grain, amber-gold-teal palette"
- Director: Visual DNA stays constant across all outputs — it is the style authority that every frame inherits

## Mapping to Generic Formula

| Generic | UGC Equivalent | Notes |
|---------|---------------|-------|
| Subject | Character & Avatar Consistency | Narrowed to identity persistence across frames |
| Composition | Composition & Framing Imperfections | Inverted: imperfection is the goal, not polish |
| Environment | Scene & Location | Emphasized: backgrounds must be readable and real |
| Lighting | Color & Lighting Conditions | Restricted to ambient-only; no studio lighting allowed |
| Color & Tone | Visual DNA + Color & Lighting | Split: style fingerprint is a separate extraction step |
| Style | Authenticity & Device Artifacts | Promoted to #1: the "style" IS the device fingerprint |
| Technical Detail | Depth of Field & Focus + Platform Format | Split: DOF constraint + delivery format are distinct concerns |
| Reference Lock | *(same as generic)* | Unchanged |

## Use Cases Served

- UGC-style image generation (selfie grids, lifestyle content)
- Social media content creation (Instagram, TikTok, Stories)
- Influencer-style product placement
- Avatar-based content series
- Brand UGC campaigns
- Contact sheet generation for multi-frame storytelling
