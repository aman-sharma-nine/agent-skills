---
name: watercolour-blog-art
description: Generate coordinated editorial watercolour blog art.
---

# Watercolour Blog Art

Generate two separate landscape images for a blog: a readable thumbnail and a quieter, complementary in-article illustration. Adapt the subjects and visual metaphors to the article while preserving the art direction below.

## Style specification

Include this complete specification in every generation prompt:

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

## Workflow

1. Read the complete blog. Identify the central idea, emotional tone, and one or two concrete motifs.
2. Create two separate images, never a contact sheet, in landscape with a 3:2 target or the closest supported landscape format:
   - Thumbnail: one strong, immediately readable composition. Keep the focal subject in a central crop-safe area.
   - In-article illustration: a quieter composition exploring a specific idea rather than repeating the thumbnail.
3. Keep palette, ink treatment, pigment texture, and detail level consistent. Change subjects to fit the article. Do not reuse pregnancy, botanical, or domestic imagery unless the article calls for it.
4. Use the built-in `image_gen` tool by default. Treat attached images as style references only; do not copy their subjects or composition into unrelated articles.
5. Inspect outputs for relevance, consistency, whitespace, anatomy, crop safety, and thumbnail readability. Iterate with one targeted change when needed.
6. Save project-bound outputs in the project's established asset directory. Never leave a project-referenced asset only under `$CODEX_HOME/generated_images/`.
7. Recommend where the second image belongs, normally after the paragraph introducing the specific idea it explores.
8. If image generation is unavailable, provide two complete prompts and state that no images were generated.

## Prompt template

```text
Use case: editorial-blog-illustration
Asset type: <thumbnail or in-article illustration>
Article idea: <central idea>
Emotional tone: <tone>
Concrete motifs: <one or two motifs>
Subject and visual metaphor: <what is shown and why>
Composition: landscape, 3:2 target, generous negative space, crop-safe focal subject
Style/medium: editorial ink-and-watercolour illustration on warm ivory paper
Style specification: <include every bullet from the Style specification section above>
Relationship to pair: <how this complements the other image>
Constraints: separate image, no text, no lettering, no logos, no border
Avoid: photorealism, 3D, glossy digital rendering, heavy shading, harsh outlines, neon colours, dense detail, stock-art clichés, generic corporate vector art
```

## Verification

- Two separate, non-zero-size image files exist.
- Both images share the palette and visual language.
- The thumbnail reads at small size and remains crop-safe.
- The in-article image adds a distinct article-specific idea.
- No unrequested text, logos, borders, or unrelated reference motifs appear.
- The article or publishing record points to the exact saved asset paths.
