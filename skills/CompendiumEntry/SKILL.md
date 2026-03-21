---
name: CompendiumEntry
description: Create or enrich a compendium entry — proper frontmatter, lore classification, external references, folder placement. USE WHEN create compendium entry, new NPC, new location, enrich entry, add to compendium.
version: 0.1.0
---

# CompendiumEntry

Create or enrich compendium entries with proper structure, lore classification, and cross-references.

## Instructions

1. Determine the entity: name, type (character, location, organization, item, creature, event, concept), and lore origin (canon, homebrew, adapted).

2. Determine folder placement using the CompendiumHygiene rule. If the entity type doesn't clearly map to a folder, ask the user.

3. Check for existing entries — search for the name and common aliases in the Compendium directory. If found, switch to enrichment mode (add content to the existing entry). If a near-duplicate exists (similar name, same entity), flag it.

4. Build the frontmatter:

```yaml
---
aliases: []
type: character
status: canon
tags:
    - "#lore/homebrew"
language: en
first_appearance: "[[Scene X.Y]]"
campaigns:
    - "[[Campaign Name]]"
---
```

5. Write the body:

```markdown
# Entity Name

Brief description (1-2 sentences).

## Details

Expanded lore, backstory, abilities, relationships.

## Appearances

- [[Scene X.Y]] — context of appearance

## References

- [D&D Beyond: Name](url) — for canon entries
```

6. For canon entries, search D&D Beyond and Forgotten Realms Wiki for authoritative references. Add links to the References section. For homebrew entries, skip external references.

7. After creating the entry, check which scenes reference this entity via wikilink. If scenes reference it but the entry didn't exist before, list those scenes in the Appearances section.

## Constraints

- Every entry needs frontmatter with `type`, `status`, and lore classification tag
- Canon entries get external reference links, homebrew entries do not
- Adapted entries must note what differs from canon
- Czech entries stay in Czech with `language: cs`
- Aliases in frontmatter for alternate names and spellings
- Never create an entry without knowing its lore classification — ask if unsure
