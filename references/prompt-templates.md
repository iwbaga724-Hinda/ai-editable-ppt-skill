# Prompt Templates

Use these templates as starting points. Replace bracketed placeholders and trim anything irrelevant to the user's task.

## Research Brief

```text
我需要制作一个关于「[主题]」的汇报。请先生成研究方案，再输出结构化研究报告。

汇报场合：[课堂/竞赛/公司汇报/路演/答辩/其他]
汇报对象：[听众背景]
汇报时长：[分钟]
汇报人数：[总人数与分工]
重点希望表达：[重点]
必须覆盖的问题：[问题列表]
输出语言：[中文/英文/双语]

请优先使用可靠来源，区分事实、推断和建议。报告最后给出适合转成 PPT 的章节结构。
```

## Outline To Slide Directions

```text
请阅读我上传的汇报大纲、研究报告和 PPT 模板。我负责制作第 [X] 部分「[标题]」，一共需要制作 [N] 页 PPT，暂定标题为：
[逐页标题]

请从“如何表现主题”的角度，给出每页 PPT 的制作指引。每页请按以下格式输出：

1. 页码与标题
2. 建议套用的模板页型
3. 最适合的主体表达
4. 视觉焦点
5. 可直接放入 PPT 的要点文案
6. 建议的视觉元素与主体关系
7. 布局建议
8. 数据、图表或来源约束
9. 直接给图像生成模型的提示词

注意：我希望下一步直接用图像生成模型生成 PPT 图片，所以请把指引写到足够具体，尤其要优化页面文字、视觉层级和版式。
```

## Slide Image Generation

```text
我在制作大纲中第 [X] 部分「[标题]」的汇报。请参考上传的 PPT 模板页面，帮我生成第 [Y] 页的 16:9 PPT 图片。

本页要求：
- 页面标题：[标题]
- 主体表达：[主体表达]
- 视觉焦点：[视觉焦点]
- 可直接放入 PPT 的要点文案：[文案]
- 建议视觉元素与主体关系：[说明]
- 布局建议：[说明]
- 数据与来源约束：[说明]

请生成高分辨率、文字清晰、层级明确、适合正式汇报的 PPT 页面。尽量采用视觉化表达形式；图表数据必须来自真实可靠来源；不要生成模糊文字或无意义占位符。
```

## Image Iteration

```text
请基于上一张图继续优化，不要重新改变整体方向。

需要改进：
1. [问题一]
2. [问题二]
3. [问题三]

请保持原模板风格和主视觉关系，强化文字清晰度、版式稳定性和信息层级，输出 16:9 高分辨率版本。
```

## Image To Editable PPT

```text
请把这张 PPT 图片重建为可编辑的 PowerPoint 页面。

要求：
1. 不要采用“整张图片作为背景再叠加文本”的方式。
2. 请拆分为可编辑图层：背景、标题、正文、形状、图表、箭头、标签、装饰元素。
3. 坐标轴、箭头、时间线、流程线、标签框和简单图形必须尽量转成可编辑形状。
4. 图标、照片和复杂插画可以保留为 PNG/JPG。
5. 请尽量完全匹配原图的布局、字体大小、颜色、间距和视觉层级。
6. 输出 PPTX，并在完成后说明哪些元素仍然不是可编辑对象。
```

## Codex Presentations Constraints

```text
Use the presentations capability to recreate the provided slide image as an editable PPTX slide.

Do not place the full slide image as a single background. Rebuild the slide with editable text boxes, shapes, lines, arrows, charts, labels, and grouped objects. Rasterize only complex icons, photos, or decorative illustrations where editability is not useful.

Match the source image's 16:9 layout, spacing, font weight, color palette, alignment, hierarchy, and text content. After generating the deck, inspect the output and report any elements that remain raster images or may need manual cleanup.
```
