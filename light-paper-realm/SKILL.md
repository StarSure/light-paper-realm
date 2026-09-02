---
name: light-paper-realm
description: "Create text-free 3:4 split-panel editorial posters from photos: faithful photography above and premium handmade paper illustration below. Use when a user requests the 光影纸境 paper-art cover style."
---

# 光影纸境 · Light Paper Realm

Transform each uploaded image into one 3:4 vertical art-publication cover. The visual system is fixed: a faithful editorial photograph in the upper 50% and a minimal paper illustration of the same story in the lower 50%.

## Non-negotiable visual system

- **Geometry:** exact 3:4 portrait canvas; exact 50:50 horizontal split. A clean, straight seam; no blend, overlap, or collage at the seam.
- **Upper half:** preserve the source’s main composition, identity, silhouette, subject/object relationships, lighting direction, atmosphere, and color story. Only reframe and seamlessly outpaint peripheral background to fit. Do not stretch, replace, or stylize the main subject.
- **Lower half:** reduce the source to its most recognizable narrative elements. Center a small hand-rendered paper illustration (10–20% of lower-half area), holding ample negative space. It must echo the upper half’s composition and palette, without merely duplicating it.
- **Material language:** warm off-white or natural paper; visible fine paper grain; restrained imperfect ink/brush edges; 3–4 sampled flat colors; quiet editorial art-book character. No photorealistic illustration or polished commercial look below.

## Text suppression: priority rule

The finished image must contain **no new readable text, characters, numbers, logos, captions, signatures, watermarks, glyph-like decoration, or pseudo-typography in any language**. This rule outranks all decorative choices.

Source text is separate from generated text. If source signage would be enlarged, sharpened, or recreated, keep it non-legible by natural crop, distance, blur, occlusion, or blank paper treatment. Do not invent a translation or substitute text.

## Workflow

1. Inspect the source and identify its dominant subject, horizon/leading line, lighting direction, three-to-four dominant colors, and any text-bearing regions.
2. Select the appropriate platform recipe in [prompt-recipes.md](references/prompt-recipes.md). Use the native recipe for a built-in image editor; use the cross-platform recipe when the target tool has separate positive and negative prompt fields.
3. Replace only `<SCENE>` with a concrete factual scene summary. Keep the rest intact; do not add optional typography.
4. Generate once and inspect for: exact split; upper-half fidelity; lower-half negative space; palette continuity; and unwanted text.
5. If any generated text or pseudo-text appears, perform one focused retry using the correction prompt in the reference. Do not keep retrying blindly. Report pre-existing source text separately if it remains.

## Delivery standard

Save variants non-destructively. Deliver only an image that meets the visual system and text-suppression check; otherwise state which constraint the selected model could not reliably preserve.

## Invocation

Users can simply upload an image and say: `Use $light-paper-realm to generate.`
