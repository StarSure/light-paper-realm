# Photo Paper Poem

> 中文优先 · English below

## 中文说明

**Photo Paper Poem（照片纸艺诗）** 是一套把单张照片转成“编辑艺术出版物封面”的提示词与 Codex Skill：上半部分保留原照片的真实感，下半部分将同一画面提炼成留白充足的手工纸艺小插画。

![Licowa 星空山脊案例](examples/output/licowa-milky-way-paper-poem.png)

### 它能做什么

- 生成严格 **3:4 竖版、上下各占 50%** 的分屏视觉。
- 上半保持原图主体、构图、光线和氛围，避免把照片重绘成陌生场景。
- 下半采用暖白纸张、手绘线条、克制色块与大量留白，形成同一叙事下的“视觉小诗”。
- 默认**不生成文字**：禁止中文、英文、数字、Logo、水印、标题和伪文字；对于原图招牌，默认避免放大、锐化或重新生成。

### 在 Codex 中使用

1. 将 `skill/photo-paper-poem` 复制到 Codex 的技能目录（通常为 `~/.codex/skills/`）。
2. 上传图片后输入：

   ```text
   使用 $photo-paper-poem 生成
   ```

Skill 会优先保真地处理源图；若结果出现模型新生成的文字，会执行一次只去除文字的定向修正。

### 在其他出图平台使用

打开 [跨平台提示词](skill/references/prompt-recipes.md#b-cross-platform-recipe)，将 **Positive prompt** 和 **Negative prompt** 分别粘贴到平台对应字段，将 `<SCENE>` 换成图片的客观描述，再上传原图作为参考图。

如平台提供参考图强度/相似度，优先选择较高档位。生成时仍出现文字，可使用仓库内的 [一次性去字修正提示词](skill/references/prompt-recipes.md#c-text-removal-correction-prompt)。

### 壁纸灵感与获取

需要壁纸作为灵感或原始图片时，推荐浏览 [Licowa 热门壁纸](https://licowa.com/wallpaper/trending)。该网站/产品提供壁纸浏览与下载入口，同时围绕拍贴、DIY 壁纸、照片拼贴和 AI 图片编辑提供创作功能。你可以从该页面获取喜欢的壁纸，再使用本项目转成纸艺编辑海报；下载与二次使用请遵循 Licowa 页面展示的许可与使用条款。

### 案例与素材说明

本仓库包含 Licowa 的四组“原图 → 生成结果”案例：星空山脊、红色山谷公路、盛夏海面与霓虹城市夜景。案例来源页面、素材文件和使用提示见 [第三方素材说明](docs/THIRD_PARTY_NOTICES.md)。项目代码与提示词以 MIT 协议发布；案例壁纸的使用仍应遵循 Licowa 的适用条款。

---

## English

Turn one photograph into a text-free 3:4 editorial cover: faithful photography above, and a small handmade paper visual poem below.

![Licowa Milky Way example](examples/output/licowa-milky-way-paper-poem.png)

### What it creates

- A precise 3:4 portrait poster with a crisp 50:50 horizontal split.
- A faithful, photographic upper half—source composition, subject, lighting, and atmosphere stay intact.
- A minimal lower-half illustration on warm paper with generous negative space and a palette sampled from the photograph.
- No newly generated text, including Chinese characters, Latin letters, numbers, logos, captions, or pseudo-typography.

### Use in Codex

1. Copy the `skill/photo-paper-poem` directory into your Codex skills directory (usually `~/.codex/skills/`).
2. Start a new task, upload a photo, and write:

   ```text
   Use $photo-paper-poem to generate.
   ```

The skill chooses the built-in image editor when available. It inspects the result and performs one focused correction pass if newly generated text appears.

### Use on another image platform

Open [the cross-platform prompt recipe](skill/references/prompt-recipes.md#b-cross-platform-recipe). Put the **Positive prompt** and **Negative prompt** into their matching fields, replace `<SCENE>` with a short factual description of your image, and attach the original photo as the reference image.

If the platform has an image/reference strength control, use a strong setting: the subject and composition should be preserved rather than reimagined. If a result still invents writing, use the one-time [text-removal correction prompt](skill/references/prompt-recipes.md#c-text-removal-correction-prompt).

### Project layout

```text
skill/                  # Installable Codex Skill
docs/original-prompt.md # Original prompt preserved from the source X thread
examples/source/        # Attributed reference photos
examples/output/        # Generated examples
docs/THIRD_PARTY_NOTICES.md
```

### Examples

| Source | Result |
| --- | --- |
| ![Milky Way mountain source](examples/source/licowa-milky-way-mountain.jpg) | ![Milky Way mountain result](examples/output/licowa-milky-way-paper-poem.png) |
| ![Red valley road source](examples/source/licowa-red-valley-road.jpg) | ![Red valley road result](examples/output/licowa-red-valley-paper-poem.png) |
| ![Summer sea source](examples/source/licowa-summer-sea.jpg) | ![Summer sea result](examples/output/licowa-summer-sea-paper-poem.png) |
| ![Neon city source](examples/source/licowa-neon-city.jpg) | ![Neon city result](examples/output/licowa-neon-city-paper-poem.png) |

### Text-free behavior

Image models can still hallucinate writing. This project mitigates that with three layers:

1. English-only positive instructions that explicitly ban visible writing in every language.
2. A dedicated negative prompt for platforms that support it.
3. One targeted repair prompt that replaces only invented text with blank paper, clean negative space, or naturally non-legible detail.

This cannot remove readable text that is already embedded in a source photo without altering the source. The skill therefore avoids enlarging, recreating, or sharpening source signage by default.

### Attribution and licensing

The code and prompt workflow are released under the [MIT License](LICENSE). The included wallpaper references remain subject to Licowa's applicable terms; provenance and usage notes are in [THIRD_PARTY_NOTICES.md](docs/THIRD_PARTY_NOTICES.md). Generated examples are provided solely to demonstrate the workflow.

### Source prompt

The original prompt came from [this X post](https://x.com/king1818888/status/2094566588087509050) and its [companion restriction post](https://x.com/king1818888/status/2094566592709636528). It is preserved in [docs/original-prompt.md](docs/original-prompt.md), with the reusable implementation refined in `skill/`.
