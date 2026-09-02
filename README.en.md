# Light Paper Realm

> [中文](README.md) ｜ [English](README.en.md)

**Light Paper Realm** turns one photograph into a text-free 3:4 editorial cover: faithful photography above, and a small handmade paper visual poem below.

![Licowa Milky Way example](examples/output/licowa-milky-way-paper-poem.png)

## Recommended wallpaper source: Licowa

[<img src="assets/licowa-logo.png" alt="LiCoWa" width="42" align="absmiddle"> **LiCoWa**](https://licowa.com/)

Looking for a suitable wallpaper to transform? Browse [Licowa Trending Wallpapers](https://licowa.com/wallpaper/trending) for inspiration or source wallpapers, then use this project to create a paper editorial poster. Licowa provides wallpaper browsing and download entry points, as well as DIY wallpaper, photo booth, photo collage, and AI image-editing tools.

The repository's four examples are selected from Licowa's wallpaper service solely to demonstrate this workflow. The wallpapers themselves are not covered by this repository's MIT License; see [Licowa sources and usage notes](#licowa-sources-and-usage-notes) below for provenance and reuse guidance.

## What it creates

- A precise 3:4 portrait poster with a crisp 50:50 horizontal split.
- A faithful, photographic upper half—source composition, subject, lighting, and atmosphere stay intact.
- A minimal lower-half illustration on warm paper with generous negative space and a palette sampled from the photograph.
- No newly generated text, including Chinese characters, Latin letters, numbers, logos, captions, or pseudo-typography.

## Use in Codex

1. Copy the `light-paper-realm` directory into your Codex skills directory (usually `~/.codex/skills/`).
2. Start a new task, upload a photo, and write:

   ```text
   Use $light-paper-realm to generate.
   ```

The skill chooses the built-in image editor when available. It inspects the result and performs one focused correction pass if newly generated text appears.

## Use on another image platform

Open [the cross-platform prompt recipe](light-paper-realm/references/prompt-recipes.md#b-cross-platform-recipe). Put the **Positive prompt** and **Negative prompt** into their matching fields, replace `<SCENE>` with a short factual description of your image, and attach the original photo as the reference image.

If the platform has an image/reference strength control, use a strong setting: the subject and composition should be preserved rather than reimagined. If a result still invents writing, use the one-time [text-removal correction prompt](light-paper-realm/references/prompt-recipes.md#c-text-removal-correction-prompt).

## Example gallery

All four Licowa wallpaper examples are collected here. Each row pairs the original wallpaper with its generated Light Paper Realm result.

| Source wallpaper | Paper editorial poster |
| --- | --- |
| ![Milky Way mountain source](examples/source/licowa-milky-way-mountain.jpg) | ![Milky Way mountain result](examples/output/licowa-milky-way-paper-poem.png) |
| ![Red valley road source](examples/source/licowa-red-valley-road.jpg) | ![Red valley road result](examples/output/licowa-red-valley-paper-poem.png) |
| ![Summer sea source](examples/source/licowa-summer-sea.jpg) | ![Summer sea result](examples/output/licowa-summer-sea-paper-poem.png) |
| ![Neon city source](examples/source/licowa-neon-city.jpg) | ![Neon city result](examples/output/licowa-neon-city-paper-poem.png) |

## Project layout

```text
light-paper-realm/      # Installable Codex Skill
docs/original-prompt.md # Original prompt preserved from the source X thread
examples/source/        # Attributed reference photos
examples/output/        # Generated examples
docs/THIRD_PARTY_NOTICES.md
```

## Text-free behavior

Image models can still hallucinate writing. This project mitigates that with three layers:

1. English-only positive instructions that explicitly ban visible writing in every language.
2. A dedicated negative prompt for platforms that support it.
3. One targeted repair prompt that replaces only invented text with blank paper, clean negative space, or naturally non-legible detail.

This cannot remove readable text that is already embedded in a source photo without altering the source. The skill therefore avoids enlarging, recreating, or sharpening source signage by default.

## Licowa sources and usage notes

The four examples in this repository pair Licowa wallpapers with generated workflow demonstrations. Their source pages, file mapping, and reuse notes are listed in [THIRD_PARTY_NOTICES.md](docs/THIRD_PARTY_NOTICES.md). The code and prompt workflow are released under the [MIT License](LICENSE); the included wallpaper references remain subject to Licowa's applicable terms.

## Source prompt

The original prompt came from [this X post](https://x.com/king1818888/status/2094566588087509050) and its [companion restriction post](https://x.com/king1818888/status/2094566592709636528). It is preserved in [docs/original-prompt.md](docs/original-prompt.md), with the reusable implementation refined in `light-paper-realm/`.
