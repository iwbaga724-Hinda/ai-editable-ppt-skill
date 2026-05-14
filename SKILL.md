---
name: ai-editable-ppt
description: Create high-quality editable presentation decks from reports, outlines, slide briefs, templates, or AI-generated slide images. Use when the user wants to build a PPT/PPTX workflow with AI image generation, turn slide images into editable PowerPoint, produce per-slide image prompts, convert generated slide visuals into editable layouts, or improve a presentation-generation pipeline using tools such as ChatGPT image generation, Gemini image generation, SVG conversion, or Codex presentations.
---

# AI Editable PPT

## Overview

Use this skill to turn source material into a high-quality presentation through an image-first workflow, then convert the result into editable PowerPoint where possible. Optimize for users who care about output quality and are willing to iterate slide by slide, not for one-click bulk deck generation.

## Workflow

1. Gather the brief.
   - Ask for or infer the topic, audience, occasion, duration, language, slide count, speaker count, required sections, source files, and target visual style.
   - If the user has a PPT template, request the template or screenshots of representative pages.
   - If the user has only a broad topic, first create or request a research report and then derive an outline.

2. Create the report and outline.
   - For early research, prefer a deep-research workflow that produces a structured report with traceable facts.
   - Turn the report into a presentation outline with clear sections, page count, page titles, and narrative order.
   - Iterate on the outline before generating visuals; weak outlines create weak slide images.

3. Convert the outline into per-slide visual directions.
   - Produce one slide brief per page: template page type, main message, visual focus, ready-to-place copy, recommended visual elements, layout guidance, data/source constraints, and direct image-generation prompt.
   - Read `references/prompt-templates.md` when the user needs concrete prompt text.
   - Keep each slide brief specific enough that an image model can generate the page without guessing the story.

4. Generate slide images one by one.
   - Use the best available image model for the user's language and visual requirements.
   - Upload the outline and the relevant template page or screenshot for each slide.
   - Prompt one slide at a time. Ask for a 16:9 slide image, strong visual hierarchy, legible text, and high resolution.
   - Iterate after each image. The second or third attempt is often materially better than the first.

5. Convert images to editable PowerPoint.
   - Preferred: use Codex with the presentations capability when available. Instruct it to recreate the slide as editable objects rather than placing a full-slide screenshot.
   - Fallback: ask an AI tool to convert the image to SVG, place the SVG in PowerPoint, then convert it to shapes. Expect cleanup.
   - Fallback: ask an AI tool to rebuild the image directly as an editable PPTX. Expect lower layout fidelity and verify carefully.

6. Verify and polish.
   - Check that text boxes, axes, arrows, labels, shapes, and major layout objects are editable.
   - Allow icons, photos, and complex illustrations to remain PNG/JPG when editability is not important.
   - Compare each recreated slide against the source image for layout, font weight, spacing, alignment, and hierarchy.
   - Fix hallucinated numbers, unclear Chinese text, broken labels, and charts without credible sources.

## Conversion Guidance

When asking Codex or another agent to convert slide images into PPTX, include these constraints:

- Do not use a single full-slide image with text overlaid unless the user explicitly accepts non-editable output.
- Split the design into editable layers: background, title, body text, shapes, charts, arrows, labels, and decorative elements.
- Convert coordinate axes, arrows, timelines, callouts, and simple diagrams into editable shapes.
- Keep complex icons, photos, and decorative illustrations as raster images if rebuilding them would waste time.
- Match the original layout, typography, colors, spacing, and hierarchy as closely as possible.

## Quality Bar

Favor fewer, better slides over many weak slides. A good result should have:

- A coherent story from outline to slide sequence.
- Page-level prompts that specify message, layout, visual metaphor, and exact copy.
- Images with readable text and no vague placeholder content.
- Editable PPT objects for content the user is likely to modify later.
- Explicit caveats where a conversion path is slow, token-heavy, or only partially editable.

## Prompt Templates

Use `references/prompt-templates.md` for reusable Chinese prompts covering:

- Research brief creation
- Outline-to-slide visual direction
- Slide image generation
- Image-to-editable-PPT conversion
- Codex presentations conversion constraints
