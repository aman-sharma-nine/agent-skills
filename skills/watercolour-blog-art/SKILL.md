---
name: watercolour-blog-art
description: Generate coordinated editorial watercolour blog art.
version: 1.0.0
author: Agent Skills Library
license: MIT
platforms: [macos, linux, windows]
metadata:
  hermes:
    tags: [editorial, blog, illustration, watercolour, image-generation]
    category: creative
    related_skills: [editorial-visual-publishing, editorial-blog-visuals]
---

# Watercolour Blog Art

Generate a coordinated pair of landscape blog images: a readable thumbnail and a quieter in-article illustration. Adapt subjects and visual metaphors to the article while preserving the editorial ink-and-watercolour art direction below.

## When to Use

Use when a blog, newsletter, Substack draft, or thought-leadership article needs a consistent thumbnail and in-article illustration. Do not carry motifs from the reference compositions into unrelated articles.

## Style Specification

Include this full specification in every image-generation prompt:

- Sophisticated, gentle editorial illustration for a literary magazine.
- Warm ivory paper background with subtle fine paper grain.
- Delicate, slightly irregular charcoal ink outlines.
- Translucent watercolour washes with natural pigment variation.
- Restrained palette: ivory `#F8F4EA`, sage `#92977B`, terracotta `#C58165`, ochre `#D8B66D`, charcoal `#39352F`.
- Soft organic shapes, quietly balanced compositions, and generous negative space, usually around half the canvas.
- Recognisable subjects with selective detail, expressive silhouettes, softly suggested faces, natural hands, and relaxed poses.
- Warm, reflective, intimate mood without sentimentality.
- Translucent colour and gently imperfect edges.
- Avoid photorealism, 3D, glossy digital rendering, heavy shading, harsh outlines, neon colours, dense decorative detail, stock-art clichés, and generic corporate vector illustration.
- No text, lettering, logos, or borders unless explicitly requested.

## Procedure

1. Read the complete article. Identify its central idea, emotional tone, and one or two concrete motifs. Completion check: write a one-sentence visual brief before generating.
2. Create two separate landscape images in a 3:2 composition, or the closest supported landscape format:
   - Thumbnail: one strong, immediately readable composition capturing the central idea. Keep the focal subject in a central crop-safe area.
   - In-article illustration: a quieter complementary composition exploring a specific idea, not repeating the thumbnail.
3. Use matching palette, ink treatment, pigment texture, and detail level across the pair. Change the subjects to fit the article. Do not reuse pregnancy, botanical, or domestic imagery unless the article calls for it.
4. Use the available image-generation tool. Generate separate images, never a combined contact sheet. If reference images are provided, inspect them as style references only and do not copy their subjects or composition into unrelated work.
5. Inspect both outputs for relevance, consistency, whitespace, anatomy, crop safety, and thumbnail readability. Regenerate when a material defect is present.
6. Save assets using the environment's normal image-saving workflow. For project-bound work, place final files in the project's established asset directory and verify both paths.
7. Recommend where the second image belongs, normally after the paragraph that introduces the specific idea it explores.
8. If generation is unavailable, provide two ready-to-use prompts and state plainly that no images were generated.

## Prompt Template

Use this structure for each prompt and include the full Style Specification above:

```text
Use case: editorial-blog-illustration
Asset type: <thumbnail or in-article illustration>
Article idea: <central idea>
Emotional tone: <tone>
Concrete motifs: <one or two motifs>
Subject and visual metaphor: <what is shown and why>
Composition: landscape, 3:2 target, generous negative space, crop-safe focal subject
Style/medium: editorial ink-and-watercolour illustration on warm ivory paper
Style specification: <paste every bullet from the Style Specification>
Relationship to pair: <how this complements the other image>
Constraints: separate image, no text, no lettering, no logos, no border
Avoid: photorealism, 3D, glossy digital rendering, heavy shading, harsh outlines, neon colours, dense detail, stock-art clichés, generic corporate vector art
```

## Reference Compositions

The original reference pair showed a couple reading together on a terracotta sofa and a pregnant woman sitting on an ochre cushion with a journal and restrained botanical motif. Preserve only the ink, watercolour, palette, negative space, and emotional restraint, not those objects.

## Verification

- Two separate image files exist and are non-zero size.
- Both images use the same palette and visual language.
- The thumbnail reads at small size and keeps its subject crop-safe.
- The in-article image adds a distinct article-specific idea.
- No unrequested text, logos, borders, or unrelated reference motifs appear.
- The article or publishing record points to the exact saved asset paths.