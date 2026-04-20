---
name: DraftItem
description: Draft a homebrew D&D 5e magic item with rarity, attunement, properties, compendium entry, and D&D Beyond formatting guide. USE WHEN create item, homebrew item, new magic item, draft item, custom item, magic weapon, magic armor.
version: 0.1.0
---

# DraftItem

Create a homebrew D&D 5e magic item with proper structure, rarity balance, and integration into both the campaign vault and D&D Beyond.

## Instructions

1. Determine the item type (weapon, armor, wondrous item, potion, scroll, ring, rod, staff, wand) and rarity (common, uncommon, rare, very rare, legendary, artifact). If the user has a concept, suggest appropriate rarity based on power level.

2. Draft the item:

```markdown
# Item Name

*[Type], [rarity] (requires attunement [by X])*

[Narrative description — what it looks like, where it comes from, what it feels like to hold.]

[Mechanical properties — each on its own line or as a bullet list.]

**Charges.** [If applicable — charges, recharge conditions.]

**Curse.** [If applicable — curse description, how it manifests, how to break it.]
```

3. Balance check: compare to DMG items of the same rarity. A rare item should be comparable to a Flame Tongue or Cloak of Displacement, not to a Holy Avenger.

4. Create a compendium entry in `Compendium/Homebrew/Items/` with frontmatter:

```yaml
---
aliases: []
type: item
subtype: [weapon/armor/wondrous/etc]
rarity: [common/uncommon/rare/very rare/legendary/artifact]
attunement: [true/false]
status: draft
tags:
    - "#lore/homebrew"
language: en
campaigns:
    - "[[Campaign Name]]"
---
```

5. If the item appears in a scene, ensure the scene's Rewards table links to the compendium entry via `[[Item Name]]` — full description lives in the compendium, not the scene.

6. Provide D&D Beyond formatting: item name, type, rarity, attunement, description with HTML, and any modifier/action configuration.

## Constraints

- Artifacts get special treatment — they should have minor and major beneficial/detrimental properties from the DMG artifact tables
- Cursed items must have both the curse effect AND a way to discover/break the curse
- Campaign-specific items (heptahedron-touched, god-corpse harvested) note their origin in the compendium entry
- If the item is a weapon, specify the base weapon type (longsword, shortbow, etc.) and what modifications it adds
