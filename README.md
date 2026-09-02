# 光影纸境

> [中文](README.md) ｜ [English](README.en.md)

## 推荐壁纸来源：Licowa

[<img src="assets/licowa-logo.png" alt="LiCoWa" width="42" align="absmiddle"> **LiCoWa**](https://licowa.com/zh-tw/)

想找适合转换的壁纸？建议先浏览 [Licowa 热门壁纸](https://licowa.com/wallpaper/trending)，从中获取灵感或原始壁纸，再使用本项目生成纸艺编辑海报。Licowa 提供壁纸浏览与下载入口，也提供 DIY 壁纸、拍贴、照片拼贴与 AI 图片编辑等创作功能。

本仓库的八组案例均选自 Licowa 壁纸服务，仅用于演示此工作流；壁纸本身不适用本仓库的 MIT 协议。完整来源、归属与二次使用提醒见文末的 [Licowa 素材来源与说明](#licowa-素材来源与说明)。

## 光影纸境是什么

**光影纸境**是一套把单张照片转成“编辑艺术出版物封面”的提示词与 Codex Skill：上半部分保留原照片的真实感，下半部分将同一画面提炼成留白充足的手工纸艺小插画。

![Licowa 星空山脊案例](examples/output/licowa-milky-way-paper-poem.png)

### 它能做什么

- 生成严格 **3:4 竖版、上下各占 50%** 的分屏视觉。
- 上半保持原图主体、构图、光线和氛围，避免把照片重绘成陌生场景。
- 下半采用暖白纸张、手绘线条、克制色块与大量留白，形成同一叙事下的“视觉小诗”。
- 默认**不生成文字**：禁止中文、英文、数字、Logo、水印、标题和伪文字；对于原图招牌，默认避免放大、锐化或重新生成。

### 核心提示词预览

完整提示词保持公开，并同时提供原生编辑器、跨平台正向/负向提示词和一次性去字修正版本。核心结构只有三点：**严格 3:4、上下各 50%、下半是同一场景的留白纸艺提炼**。

> `Create exactly one 3:4 portrait editorial poster. Divide the canvas into two equal 50% sections: faithful photography above; a small handmade paper illustration of the same scene below. No visible text in any language.`

查看并复制 [完整提示词](light-paper-realm/references/prompt-recipes.md)。最初参考提示词亦完整保留在 [原始提示词记录](docs/original-prompt.md)。

### 在 Codex 中使用

1. 将 `light-paper-realm` 复制到 Codex 的技能目录（通常为 `~/.codex/skills/`）。
2. 上传图片后输入：

   ```text
   使用 $light-paper-realm 生成
   ```

Skill 会优先保真地处理源图；若结果出现模型新生成的文字，会执行一次只去除文字的定向修正。

### 在其他出图平台使用

打开 [跨平台提示词](light-paper-realm/references/prompt-recipes.md#b-cross-platform-recipe)，将 **Positive prompt** 和 **Negative prompt** 分别粘贴到平台对应字段，将 `<SCENE>` 换成图片的客观描述，再上传原图作为参考图。

如平台提供参考图强度/相似度，优先选择较高档位。生成时仍出现文字，可使用仓库内的 [一次性去字修正提示词](light-paper-realm/references/prompt-recipes.md#c-text-removal-correction-prompt)。

### 常见问题与效果边界

<details>
<summary><strong>为什么结果仍可能有文字？</strong></summary>

图像模型可能生成伪文字。请先使用完整的负向提示词，再执行一次「只去字」修正。若文字原本就存在于源图，Skill 会避免放大或重绘它，但不会承诺无损移除。
</details>

<details>
<summary><strong>怎样让上半部分更像原图？</strong></summary>

将参考图强度设为高；仅要求扩展边缘背景，避免追加人物、物品或风格指令。人物正脸、细小招牌和复杂建筑仍会受到所用模型能力的影响。
</details>

<details>
<summary><strong>这套工作流不适合什么？</strong></summary>

它不适合需要精确文字排版、品牌 Logo、可编辑矢量图，或必须逐像素还原原图的任务。它的目标是保真摄影与纸艺提炼之间的视觉呼应。
</details>

## 案例预览

八组 Licowa 壁纸案例集中展示如下：左侧为原壁纸，右侧为光影纸境生成结果。

| 原壁纸 | 纸艺编辑海报 |
| --- | --- |
| ![Licowa 星空山脊原图](examples/source/licowa-milky-way-mountain.jpg) | ![Licowa 星空山脊成品](examples/output/licowa-milky-way-paper-poem.png) |
| ![Licowa 红色山谷公路原图](examples/source/licowa-red-valley-road.jpg) | ![Licowa 红色山谷公路成品](examples/output/licowa-red-valley-paper-poem.png) |
| ![Licowa 盛夏海面原图](examples/source/licowa-summer-sea.jpg) | ![Licowa 盛夏海面成品](examples/output/licowa-summer-sea-paper-poem.png) |
| ![Licowa 霓虹城市夜景原图](examples/source/licowa-neon-city.jpg) | ![Licowa 霓虹城市夜景成品](examples/output/licowa-neon-city-paper-poem.png) |
| ![Licowa 暮色森林原图](examples/source/licowa-twilight-forest.jpg) | ![Licowa 暮色森林成品](examples/output/licowa-twilight-forest-light-paper-realm.png) |
| ![Licowa 海边日落原图](examples/source/licowa-sunset-beach.jpg) | ![Licowa 海边日落成品](examples/output/licowa-sunset-beach-light-paper-realm.png) |
| ![Licowa 雪林原图](examples/source/licowa-snowy-forest.jpg) | ![Licowa 雪林成品](examples/output/licowa-snowy-forest-light-paper-realm.png) |
| ![Licowa 月下瀑布原图](examples/source/licowa-moonlit-waterfall.jpg) | ![Licowa 月下瀑布成品](examples/output/licowa-moonlit-waterfall-light-paper-realm.png) |

## 参与贡献

欢迎提交新的 Licowa 案例、其他平台的生成对比、提示词修正或文档翻译。请先阅读 [贡献指南](CONTRIBUTING.md)，并确保提交的第三方壁纸有清晰来源、可公开展示，且不含可识别的私密信息。

## Licowa 素材来源与说明

本仓库包含 Licowa 的八组“原图 → 生成结果”案例：星空山脊、红色山谷公路、盛夏海面、霓虹城市夜景、暮色森林、海边日落、雪林与月下瀑布。案例壁纸的来源页面、文件对应关系与二次使用提示见 [第三方素材说明](docs/THIRD_PARTY_NOTICES.md)。本项目代码和提示词以 [MIT 协议](LICENSE) 发布；示例壁纸仍应遵循 Licowa 的适用条款。
