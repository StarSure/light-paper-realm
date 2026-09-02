# Photo Paper Poem

Turn one photograph into a text-free 3:4 editorial cover: faithful photography above, and a small handmade paper visual poem below.

![City skyline example](examples/output/city-skyline-paper-poem.png)

## What it creates

- A precise 3:4 portrait poster with a crisp 50:50 horizontal split.
- A faithful, photographic upper half—source composition, subject, lighting, and atmosphere stay intact.
- A minimal lower-half illustration on warm paper with generous negative space and a palette sampled from the photograph.
- No newly generated text, including Chinese characters, Latin letters, numbers, logos, captions, or pseudo-typography.

## Use in Codex

1. Copy the `skill/photo-paper-poem` directory into your Codex skills directory (usually `~/.codex/skills/`).
2. Start a new task, upload a photo, and write:

   ```text
   Use $photo-paper-poem to generate.
   ```

The skill chooses the built-in image editor when available. It inspects the result and performs one focused correction pass if newly generated text appears.

## Use on another image platform

Open [the cross-platform prompt recipe](skill/references/prompt-recipes.md#b-cross-platform-recipe). Put the **Positive prompt** and **Negative prompt** into their matching fields, replace `<SCENE>` with a short factual description of your image, and attach the original photo as the reference image.

If the platform has an image/reference strength control, use a strong setting: the subject and composition should be preserved rather than reimagined. If a result still invents writing, use the one-time [text-removal correction prompt](skill/references/prompt-recipes.md#c-text-removal-correction-prompt).

## Project layout

```text
skill/                  # Installable Codex Skill
docs/original-prompt.md # Original prompt preserved from the source X thread
examples/source/        # Attributed reference photos
examples/output/        # Generated examples
docs/THIRD_PARTY_NOTICES.md
```

## Examples

| Source | Result |
| --- | --- |
| ![Alpine landscape source](examples/source/alpine-landscape-patrick-feirer.jpg) | ![Alpine landscape result](examples/output/alpine-landscape-paper-poem.png) |
| ![City skyline source](examples/source/city-skyline-sean-pollock.jpg) | ![City skyline result](examples/output/city-skyline-paper-poem.png) |
| ![White architecture source](examples/source/white-architecture-joel-filipe.jpg) | ![White architecture result](examples/output/white-architecture-paper-poem.png) |

## Text-free behavior

Image models can still hallucinate writing. This project mitigates that with three layers:

1. English-only positive instructions that explicitly ban visible writing in every language.
2. A dedicated negative prompt for platforms that support it.
3. One targeted repair prompt that replaces only invented text with blank paper, clean negative space, or naturally non-legible detail.

This cannot remove readable text that is already embedded in a source photo without altering the source. The skill therefore avoids enlarging, recreating, or sharpening source signage by default.

## Attribution and licensing

The code and prompt workflow are released under the [MIT License](LICENSE). The included reference photos remain subject to the [Unsplash License](https://unsplash.com/license); detailed attribution and provenance are in [THIRD_PARTY_NOTICES.md](docs/THIRD_PARTY_NOTICES.md). Generated examples are provided solely to demonstrate the workflow.

## Source prompt

The original prompt came from [this X post](https://x.com/king1818888/status/2094566588087509050) and its [companion restriction post](https://x.com/king1818888/status/2094566592709636528). It is preserved in [docs/original-prompt.md](docs/original-prompt.md), with the reusable implementation refined in `skill/`.
