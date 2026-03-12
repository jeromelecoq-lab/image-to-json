# Architectural Exterior Prompt Formula

For exterior architectural visualization — transforming 3D renders, CAD views, or conceptual drawings into photorealistic architectural photography. Covers buildings, complexes, public spaces, and development projects.

## Categories (priority order)

### 1. Structural Fidelity Lock
**Preserve the exact building form.** Massing, facade rhythm, fenestration pattern, floor count, roof profile, cantilevered volumes, entrance treatment, ground-floor transparency. When reference images carry the structure, the prompt reinforces "maintain exact form" rather than re-describing it.

- Analyzer: extract building typology, scale, key architectural features, proportions
- Enhancer: lead with structural preservation — "maintain exact building massing and facade rhythm"
- Director: structure stays locked across all outputs — only angle, light, and atmosphere change

### 2. Material & Facade Realism
**The biggest gap between 3D and photo.** 3D renders have too-uniform, too-perfect surfaces. Concrete needs pour-line texture and rain staining. Glass needs sky reflections with slight color variation per panel. Steel needs oxidation at joints. Wood needs grain direction and weathering gradient. Stone needs joint shadows and efflorescence.

- Analyzer: identify each facade material, note uniformity problems in the 3D render
- Enhancer: describe material imperfections — "concrete with formwork marks and rain staining down from ledges"
- Director: material description stays consistent; what varies is how light reveals different material qualities at different times of day

### 3. Environmental Integration
**What surrounds the building.** Real buildings exist in a context — paved streets with wear patterns, mature trees with irregular canopy, neighboring buildings at appropriate scale and age, ground-plane vegetation, urban furniture (benches, bollards, bike racks). The ground-plane junction (where building meets earth) is where renders fail hardest.

- Analyzer: determine plausible context from building type and location cues
- Enhancer: describe environment relative to building — what's at the base, what's across the street, what frames it
- Director: environment stays consistent across outputs (same site context) but viewed from different angles

### 4. Lighting & Time of Day
**Sun position, sky, and shadow behavior.** Not "golden hour lighting" but how light behaves on THIS building — sun raking across the west facade at 15 degrees, balcony slabs casting shadow on the one below, bounced light from pavement warming the underside of cantilevered volumes, interior warm-white glow at dusk.

- Analyzer: identify facade orientation (which walls face which direction) for realistic sun behavior
- Enhancer: describe light as surface interaction — how it hits specific materials
- Director: time of day is a primary variation axis — each output should feel like a different moment

### 5. Atmospheric Depth
**Sky is half the exterior image.** Clouds with volume, horizon haze, light scattering. Weather traces: wet pavement reflections, condensation on north-facing glass, heat shimmer off dark roofs, dust in construction context. Air has presence in real photos — 3D renders look "vacuum-clean."

- Analyzer: note any sky/atmosphere already present in 3D render
- Enhancer: always specify sky condition and at least one weather trace
- Director: atmosphere is a variation axis — vary sky dramatically across outputs (clear, overcast, dusk, storm approaching)

### 6. Composition & Camera
**Upgrading from flat 3D render angles.** Camera height, lens choice (24mm wide for establishing, 85mm for detail), foreground framing (tree branch, parked car, low wall), vanishing point placement, vertical correction. Architectural photography conventions: corrected verticals for wide shots, intentional perspective for dramatic shots.

- Analyzer: assess the 3D render's current angle — what's weak about the composition
- Enhancer: specify lens and camera position concretely — not "dramatic angle" but "low camera at 1.2m, 24mm lens, verticals corrected"
- Director: composition is a variation axis — wide establishing, dramatic angle, detail close-up, street-level lifestyle

### 7. Scale & Life Indicators
**What makes a render look like a photograph of a real place.** People at correct proportion (head height ≈ door handle), cars parked and moving, bicycles, street furniture, signage, café terraces. People in natural mid-stride poses, not centered or staring. 3D renders either omit these or place them too perfectly.

- Analyzer: note what's missing from the 3D render (usually everything in this category)
- Enhancer: place 2-3 specific life elements with physical specificity
- Director: life density varies by shot — sparse for establishing, rich for lifestyle

### 8. Landscape & Vegetation
**Trees and planting are notoriously bad in 3D renders.** Real vegetation: irregular growth, seasonal color, cleared lower branches, shadow dappling on facades and ground, ground-cover at building base, planter boxes with varied species. Not "lush greenery" — specific plants with growth habits.

- Analyzer: identify any vegetation in the 3D render, note how it's simplified
- Enhancer: name tree types or describe growth habit — "mature plane tree with asymmetric canopy, lower branches cleared to pedestrian height"
- Director: vegetation stays consistent across outputs (same trees) but appears differently under different light/season

## Key Insight

Categories 1 is carried primarily by the reference image, not the text. Categories 2-4 are where the text prompt does the heaviest lifting — they describe the TRANSFORMATION from 3D to photo. Categories 5-8 are refinement that elevates the result from "good" to "publishable."

## Serves Use Cases
- 3D render → photorealistic architectural photography
- Development project visualization
- Architecture competition presentation
- Real estate marketing (exterior)
- Urban planning visualization
