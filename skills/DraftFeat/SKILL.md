---
name: DraftFeat
description: Draft a homebrew D&D 5e feat with mechanical backing, compendium entry, and D&D Beyond formatting guide. USE WHEN create feat, homebrew feat, new feat, draft feat, custom feat.
version: 0.1.0
---

# DraftFeat

Create a homebrew D&D 5e feat with proper structure, mechanical balance, and integration into both the campaign vault and D&D Beyond.

## Instructions

1. Ask what the feat does narratively and mechanically. If the user has a concept ("reward for surviving the void," "heptahedron exposure"), start from there. If they have specific mechanics, validate balance.

2. Draft the feat in this structure:

```markdown
# Feat Name

*Prerequisite: [if any]*

[Narrative description — one sentence, what the feat represents in the fiction.]

You gain the following benefits:
- **[Benefit 1]:** [Mechanical description]
- **[Benefit 2]:** [Mechanical description]
- **[Benefit 3 (optional)]:** [Mechanical description]
```

3. Balance check against official feats. Compare to a similar published feat (e.g., if it grants resistance, compare to feats that grant resistance). Flag if it's too strong or too weak.

4. Create a compendium entry in `Compendium/Homebrew/Feats/` with frontmatter:

```yaml
---
aliases: []
type: feat
status: draft
tags:
    - "#lore/homebrew"
language: en
campaigns:
    - "[[Campaign Name]]"
---
```

5. Provide D&D Beyond formatting instructions: the feat name, description (with HTML tags for the D&D Beyond editor), snippet codes where applicable (`{{modifier:cha}}`, `{{savedc:str}}`), and any action/modifier configuration needed.

## Constraints

- All homebrew feats are type "General" in D&D Beyond — the builder cannot create Origin Feats, Fighting Styles, or Epic Boons
- Actions with limited uses require a two-step save in D&D Beyond: create the action first, save, then edit to unlock limited uses
- Narrative description first, mechanics second. The feat should tell a story.
- If the feat is campaign-specific (tied to a heptahedron, a specific event, a divine blessing), note that in the compendium entry
