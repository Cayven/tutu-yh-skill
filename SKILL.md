---
name: tutu-yh-skill
description: Enhance user-provided images by randomly selecting exactly one of seven bundled character reference images and compositing it prominently into the uploaded image. Use this skill whenever the user provides an image and wants the character added to it, regardless of whether the source is a portrait, landscape, indoor scene, outdoor scene, square image, or another aspect ratio.
---

# 图图优化-skill

## Core workflow

When the user provides an image:

1. Treat the uploaded image as the original background.
2. Randomly select exactly one image from `assets/character_01.jpeg` through `assets/character_07.jpeg`.
3. Give all seven reference images equal selection probability: 1/7 each.
4. Do not choose based on the user's image content, aspect ratio, pose, scenery, or semantic similarity.
5. Composite the selected character into the user's image.
6. Place the character approximately at the visual center of the composition.
7. Scale the character as large as reasonably possible so that it dominates the image.
8. Allow parts of the character to extend beyond the image boundaries when necessary.
9. Adapt the character scale and crop to the user's original aspect ratio.
10. Preserve the user's original background and overall scene unless minor integration adjustments are needed for a natural composite.
11. Do not replace the selected character with another character.
12. Do not redesign the character unless the user explicitly requests a redesign.

## Reference assets

Use only these seven bundled images:

- `assets/character_01.jpeg`
- `assets/character_02.jpeg`
- `assets/character_03.jpeg`
- `assets/character_04.jpeg`
- `assets/character_05.jpeg`
- `assets/character_06.jpeg`
- `assets/character_07.jpeg`

Every image has equal selection probability.

## Aspect ratio

Support:

- portrait
- landscape
- square
- panoramic
- other user-provided aspect ratios

The character should remain visually dominant after resizing and cropping.

## Final check

Before producing the result, verify:

- exactly one of the seven references was selected;
- selection is random with equal weighting;
- the character is centered;
- the character occupies most of the frame;
- the original scene remains recognizable;
- the character is not unnecessarily reduced in size.