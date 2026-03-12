# Prompt Formulas

Prompt formulas define **what categories matter** for a specific domain, ordered by importance. They tell analyzers what to extract, enhancers what to prioritize, and directors what to vary across outputs.

Formulas are orthogonal to output format (prose vs JSON) and template tier (5-section vs 7-section). A food formula can be expressed as prose or JSON — the formula defines the categories, the format defines the structure.

## How Formulas Work

| Pipeline Stage | How it uses the formula |
|----------------|------------------------|
| **Analyzer** | Categories become the extraction schema — what to analyze from input images/text |
| **Enhancer** | Categories set priority order — top categories get the most detail in the prompt |
| **Director** | Categories define creative axes — what varies across N outputs vs what stays constant |
| **Writer** | Categories can map to output fields — each field covers one formula dimension |

**Element order matters.** First elements are highest priority. When prompt length is constrained, top categories get full sentences; bottom categories get a phrase or are omitted.

## Generic vs Domain Formulas

The **generic formula** (`generic.md`) is the universal fallback — it works for any image type. Domain formulas specialize it by reordering, replacing, or adding categories that matter most for that domain.

| Domain Formula | File | Serves Use Cases |
|----------------|------|-----------------|
| **Generic** | `generic.md` | All (fallback) |
| **Food & Beverage** | `food-beverage.md` | Food photography, restaurant, culinary content |
| **Interior & Staging** | `interior-staging.md` | Virtual staging, surface material placement, real estate, furniture |
| **Product Lifestyle** | `product-lifestyle.md` | Product placement, brand-driven ads, product shots |
| **Architectural Exterior** | `architectural-exterior.md` | 3D render → photo, development viz, architecture competition, real estate exterior |
| **Fashion & Garment** | `fashion-garment.md` | On-model garment try-on, fashion editorial, lookbook, casting archetype matching |
| **UGC & Social** | `ugc-social.md` | UGC creatives, social content, selfie grids, influencer-style |
| **Cinematic & Character** | `cinematic-character.md` | Character-vehicle pipelines, cinematic shots, editorial character-in-environment |

## How to Use

**When creating a prompt** (`/create-prompt`, `/create-node`, `/create-workflow`):

1. Identify the domain of the content being generated
2. Check this INDEX for a matching formula
3. If match → read the formula file, use its categories to structure the prompt
4. If no match → use `generic.md`, offer to create a domain formula after testing

**When creating a new formula:**
- Start from the generic formula
- Reorder categories by what matters most for this domain
- Replace generic categories with domain-specific ones where needed
- Keep 8-12 categories — enough to differentiate, not so many they become noise
- Each category must be orthogonal (non-overlapping)
- Each category must be actionable (an analyzer can extract it, a director can vary it)

## Formula Validation

- [ ] **Orthogonality**: Do categories describe non-overlapping dimensions?
- [ ] **Priority order**: Is the order based on what matters most for output quality?
- [ ] **Actionability**: Can an analyzer extract each category from an image? Can a director use it?
- [ ] **Coverage**: Does this formula serve 2+ active use cases?
- [ ] **Universality**: Could this formula work if the specific product/domain swapped?
