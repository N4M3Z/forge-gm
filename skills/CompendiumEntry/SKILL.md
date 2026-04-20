---
name: CompendiumEntry
description: Create or enrich a compendium entry from vault templates — proper frontmatter, central-tenet pattern, lore classification, folder placement. USE WHEN create compendium entry, new NPC, new location, new item, new power, enrich entry, add to compendium.
version: 0.2.0
---

Create or enrich compendium entries using the vault's standard templates. Templates live in the vault's `Templates/` directory and define the structure for each entry type.

## Instructions

1. **Determine the entity type and folder placement.** Use the table:

    | Entity                                  | Template                 | Folder                          |
    | --------------------------------------- | ------------------------ | ------------------------------- |
    | Mortal NPC, named character             | `Templates/Character.md` | `Compendium/Characters/`        |
    | Deity, archfiend, celestial, cosmic     | `Templates/Power.md`     | `Compendium/Powers/`            |
    | Magic item, artifact, notable object    | `Templates/Item.md`      | `Compendium/Items/`             |
    | City, plane, landmark, gate-town        | `Templates/Location.md`  | `Compendium/Locations/`         |
    | Faction, guild, troupe, government      | `Templates/Character.md` (adapted) | `Compendium/Organizations/` |
    | Creature, monster type, encounter foe   | `Templates/Character.md` (adapted) | `Compendium/Bestiary/`      |

    If the entity does not clearly map, ask the user.

2. **Confirm name spelling against the existing compendium first.** Grep `Compendium/<folder>/` for the name and likely near-variants. If a name does not exist in the compendium, ask the user before inventing a spelling — never substitute a near-homophone from training-set fantasy lexicon. If the name already exists, switch to enrichment mode. If a near-duplicate exists (similar name, same entity), flag it before creating a new file. Once a wrong variant lands in a vault file, it propagates through every subsequent agent dispatch.

3. **Apply the naming convention.** Filename and `title:` are English. If the user supplied a Czech or other-language name, translate to a poetic English equivalent and preserve the original under `aliases:`. Example: `Pyritová zahrada` → file `The Gilded Garden.md`, alias `Pyritová zahrada`.

4. **Read the template** for the entity type. Substitute every `${VARIABLE}` placeholder with the appropriate content. Strip the trailing `%% comment %%` annotations after substitution. Preserve the structural shape (frontmatter, central-tenet bold sentence, appearance paragraph, history paragraph, sectioned body).

5. **Write the central tenet** as a single bold sentence following the pattern: *"X wants Y, by Z — and is having difficulty getting it because [obstacles]."* This is the most important line — it captures motivation, method, and friction together.

6. **Set lore classification correctly.** Use `lore/canon` for unmodified D&D content, `lore/homebrew` for original campaign content, `lore/adapted` for canon with campaign-specific changes. Adapted entries must explain what differs from canon in the body.

7. **Cross-reference scenes that already mention the entity.** Grep the campaign folders for the wikilink and add an `## Appearances` section if the entity is referenced in scenes that predate the entry.

8. **For canon entries**, add a `## References` section with links to D&D Beyond or Forgotten Realms Wiki at the bottom. Skip for homebrew.

## Constraints

- Filename and `title:` always English. Czech, French, or other-language names go in `aliases:`.
- Frontmatter must include: `title`, `aliases`, `tags` (with `type/<kind>` + lore tag), `keywords`, `description`, `status`, `created`, `updated`.
- Every entry needs a central-tenet sentence — do not skip it even for minor entries.
- Never invent a near-variant of an existing name. Confirm spelling first.
- Compendium folder routing is non-negotiable — Powers/ is for cosmic entities, Characters/ is for mortals (including PCs whose god-identity is a pacing-firewalled secret).
