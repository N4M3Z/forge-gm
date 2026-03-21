---
name: ArtDescribe
description: Generate visual descriptions for MTG card art in an art catalog. Reads images, writes one-line atmosphere descriptions into .art-catalog.json. USE WHEN describing art, populating descriptions, art catalog descriptions, describe card art.
version: 0.1.0
---

# ArtDescribe

Generate visual descriptions for MTG card art images stored in an art catalog. Each description is a one-line atmosphere summary useful for matching art to RPG scene themes.

## Instructions

1. Read `.art-catalog.json` from the art directory. Identify entries where `description` is empty.

2. Count the total number of empty descriptions. Divide by 3 — that is the maximum for one session. Present this to the user via AskUserQuestion before starting: "N images need descriptions. Session max: M (1/3 of total). How many to process?"

3. Process images in batches of 10. For each image:
   - Read the image file using the Read tool (it renders images visually)
   - Write a one-line description (10-20 words) capturing mood, setting, lighting, key visual elements, and dominant colors
   - Focus on atmosphere and scene-matching value, not card mechanics
   - Use lowercase, no period at end

4. After each batch of 10, update `.art-catalog.json` with the new descriptions and add a `described_at` ISO timestamp to each updated entry. Save the catalog after each batch (checkpoint).

5. After each batch, report progress and ask via AskUserQuestion whether to continue: "Batch N complete. Described: X, remaining: Y. Continue?"

6. When the user stops or the session limit is reached, report: `Done: N described, M remaining, K skipped`.

## Description Style

Descriptions should help a GM find art for a scene. Prioritize visual atmosphere over card identity.

| Image shows                        | Good description                                        |
| ---------------------------------- | ------------------------------------------------------- |
| Dark throne room with a demon lord | dark throne room, massive horned figure, red glow       |
| Glowing forest with ethereal light | luminous forest clearing, golden light filtering through |
| Battle on a bridge over lava       | stone bridge over molten river, armored figures clashing |
| Solitary figure on a mountain peak | lone silhouette on windswept peak, storm clouds below   |

Avoid card-specific terms (mana, tapping, counters). Describe what the eye sees.

## Constraints

- Never process more than 100 images in a single session
- Never dispatch parallel image-reading agents — process sequentially in batches of 10
- Always use AskUserQuestion after each batch to confirm continuing
- Checkpoint after every batch — safe to interrupt and resume
- Skip entries that already have a non-empty description unless `--full` is specified
- If an image file is missing from disk, log it and skip
- The `described_at` field uses ISO 8601 format (`2026-03-21T17:00:00Z`)
- Do not modify any catalog fields other than `description` and `described_at`
