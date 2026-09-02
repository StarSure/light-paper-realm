# Prompt Recipes

Use English for the generation prompt even when the user speaks another language. This reduces—but cannot mathematically guarantee—text hallucination across models.

## A. Native image-editing recipe

Use when the image generator accepts an attached edit target and one unified prompt.

```text
Use case: style-transfer.
Asset type: premium independent art-publication cover, text-free.
Input image: edit target and sole visual reference.
Scene summary: <SCENE>.

Create exactly one 3:4 portrait editorial poster from the uploaded image. Divide the canvas with one crisp horizontal seam into two exactly equal 50% sections.

UPPER HALF — FAITHFUL EDITORIAL PHOTOGRAPH
Preserve the source scene faithfully: its main composition, recognizable subject(s), identity, silhouette, proportions, pose, meaningful objects, spatial relationships, lighting direction, shadows, atmosphere, photographic texture, and original color mood. Use only refined subtle editorial color grading. To fit the format, outpaint only peripheral environment such as sky, ground, wall, or distant background; extensions must be seamless and photographic. Never stretch, distort, reshape, replace, add, remove, or re-style the main subject.

LOWER HALF — MINIMAL HANDMADE PAPER IMAGE
Translate the source into its clearest visual shorthand: key silhouette, essential gesture, important object, horizon, and core relationship. Make a small centered handmade paper illustration taking 10–20% of the lower half, with expansive deliberate negative space. Use warm off-white rough paper, subtle fine paper grain, 3–4 sampled colors from the photo, restrained acrylic-like flat shapes, delicate imperfect hand-drawn ink lines, visible handmade brush marks, and organic uneven edges. The lower half must feel like a quiet visual poem derived from the photograph, not a duplicate or a commercial illustration.

ART DIRECTION
Quiet, poetic, intelligent, understated, refined, premium, contemporary independent art book. Strong visual continuity between both halves; strong material contrast between authentic photography above and handmade paper below.

ABSOLUTELY NO VISIBLE TEXT OR CHARACTERS OF ANY LANGUAGE. Generate no Chinese characters, English letters, Japanese characters, Korean characters, numbers, punctuation, icons that resemble writing, logos, labels, captions, titles, signatures, or watermarks. Leave any potential text region blank, plain, abstract, naturally blurred, cropped, or non-legible. No typography.

Avoid: all words, characters, symbols, numbers, logos, watermark, caption, signature, pseudo-text, colored pencil, crayon, bleeding watercolor, pure line art, intricate realistic illustration, heavy oil painting, smooth digital painting, 3D, gloss, commercial cartoon, cute character design, e-commerce advertising, generic poster template, decorative clutter, busy composition.
```

## B. Cross-platform recipe

Use this when a platform exposes a **Positive prompt** and a **Negative prompt**. Put the following two blocks in their matching fields. If it offers image/reference strength, prefer a high or strong value because fidelity matters more than stylistic variation.

### Positive prompt

```text
One 3:4 vertical independent art-publication cover, precise 50/50 horizontal split. Upper half: faithful authentic editorial photography of <SCENE>, preserving the reference photo's composition, main subject, proportions, lighting direction, atmosphere, real texture and color mood; only seamless peripheral background extension permitted. Lower half: the same scene distilled into a small centered handmade paper illustration, 10–20% of the lower half, large negative space, warm off-white rough paper, fine paper grain, imperfect ink lines, restrained acrylic-flat color shapes, organic brush edges, 3–4 colors sampled from the reference. Quiet, poetic, refined, premium, non-commercial. No typography. No readable source signage; text regions remain naturally blurred, cropped, blank, or non-legible.
```

### Negative prompt

```text
text, words, Chinese characters, Hanzi, English letters, Japanese characters, Korean characters, typography, captions, titles, labels, numbers, dates, logos, brands, signatures, watermark, glyphs, symbols, pseudo-text, calligraphy, handwriting, signage, poster copy, colored pencil, crayon, bleeding watercolor, pure line art, heavy oil painting, polished digital illustration, 3D render, glossy texture, cute commercial cartoon, e-commerce ad, generic poster template, ornate decoration, busy composition
```

## C. Text-removal correction prompt

Use exactly once when output contains newly generated readable text or text-like marks.

```text
Keep the composition, subjects, colors, exact 50/50 split, and material style unchanged. Remove every newly generated letter, Chinese character, word, number, logo, label, watermark, symbol, signature, and pseudo-text. Replace those areas only with blank warm paper texture, clean negative space, or naturally non-legible photographic blur. Do not add any replacement text.
```

## Acceptance checklist

- Canvas is 3:4 portrait, and the seam is at exactly half-height.
- Upper half is recognizably the source photo, not a newly imagined scene.
- Lower half is simplified, centered, materially handmade, and surrounded by clear negative space.
- Lower palette derives from the upper image and does not exceed four key colors.
- No new readable text or writing-like marks are visible. If text persists only because it exists in the source, it was not enlarged or recreated.
