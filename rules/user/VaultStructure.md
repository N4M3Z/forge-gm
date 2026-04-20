The campaign vault is an Obsidian knowledge base for tabletop RPG session planning. This file defines the canonical directory structure. All vault operations reference this as the source of truth.

## Top-Level Directories

- `Campaigns/` — active campaign content, one subdirectory per campaign
- `Compendium/` — the world's collection. Everything that exists IN the fiction: characters, locations, items, lore. Organized by entity type. Equivalent to the Personal vault's Collection directory.
- `Orchestration/` — AI infrastructure (agents, patterns, conventions, memory)
- `Players/` — player cards and preferences (AMBER — use safe-read)
- `Resources/` — everything OUTSIDE the fiction. Rules systems, art libraries, maps, external tools, GM aids, reference PDFs. If it's about the real world or the game system rather than the campaign world, it lives here.
- `Templates/` — canonical templates for scenes, notes, and other file types
- `Assets/` — shared assets across campaigns

## The Compendium/Resources Split

Compendium answers: "What exists in the world?" Resources answers: "What do I as a GM need to run the game?"

- A description of Sigil → `Compendium/Locations/Sigil.md`
- The D&D 5e SRD rules for planar travel → `Resources/D&D 5E SRD/`
- Asmodeus's stat block and lore → `Compendium/Characters/Asmodeus.md`
- The D&D Beyond link to his official stat block → referenced inside the compendium entry
- A homebrew feat earned in-game → `Compendium/Homebrew/Feats/`
- MTG art used for scene atmosphere → `Resources/MTG Pics/`
- A canonical source analysis → `Compendium/Inspirations/`

## Campaign Structure

```
Campaigns/[Name]/
    [Name].md              Campaign outline and source material index
    _Source/                Raw exports (ChatGPT, voice transcripts, player notes)
    Chapter N/              Canonical scene files
        Chapter N.md        Chapter outline — at-the-table cheatsheet
        Scene N.X Title.md  Scene files following Templates/Scene.md
        Assets/             Chapter-specific maps and images
    Session Prep/           Working documents (proposals, outlines)
        Chapter N/          Per-chapter prep
    Journals/               Player-written session recaps (typically Czech)
    Characters/             Campaign-specific character files
```

## Compendium Structure

The world's collection. Each subdirectory has a MoC file using Dataview queries, not manual lists.

- `Characters/` — named NPCs active in current campaigns
- `Locations/` — places (cities, planes, landmarks)
- `Organizations/` — factions, guilds, cults, governments
- `History/` — historical figures and events
- `Powers/` — deities, celestials, fiends
- `Bestiary/` — creatures and monster types
- `Items/` — magic items, artifacts, notable objects
- `Seeds/` — plot hooks and campaign ideas
- `Inspirations/` — external media and canonical sources influencing the campaign
- `Rulings/` — campaign-specific rule decisions
- `Homebrew/Feats/` — homebrew feat definitions
- `Homebrew/Items/` — homebrew item definitions
- `Documents/` — in-world texts, letters, prophecies, songs
- `Secrets/` — GM-only lore not yet revealed
- `Encounters/` — pre-built encounters and traps
- `Engines/` — random tables, name generators, mechanical tools
- `Technologies/` — vehicles, constructs, magical devices
- `Nature/` — cosmology, phenomena, natural laws
- `People/` — races, classes, languages (categorical, not individual)
- `Buildings/` — notable structures
- `Planes/` — planar descriptions and connections

## Resources Structure

Everything outside the fiction. GM tools, external references, art, rules.

**Rules & System Reference:**
- `D&D 5E SRD/` — System Reference Document, organized by category (Adventuring, Classes, Equipment, NPCs, Spells, Treasure)
- `D&D 5E Homebrew/` — third-party homebrew rules and supplements
- `D&D 5E House Rules/` — table-specific rule modifications
- `D&D 5E Character Sheet/` — character sheet templates and tools

**Digital Tools & Integrations:**
- `D&D Beyond/` — character sheet links, homebrew creation guides
- `D&D App Files/` — exported compendiums and item databases (XML)

**Art & Visual Reference:**
- `MTG Pics/` — MTG card art organized by set name. `.art-catalog.json` for search. ASCII filenames only. `Card Name (Set Name) - art by Artist.jpg`.
- `D&D Illustrations/` — official D&D artwork
- `D&D Fan Site Kit/` — official fan-use assets
- `ArtStation/` — collected artist work
- `DeviantArt/` — collected fan art
- `Midjourney/` — AI-generated concept art
- `Inkarnate/` — map-making tool exports
- `DysonLogos.com/` — dyson-style dungeon maps

**Maps & Cartography:**
- `Leviathan Maps/` — campaign-specific world maps
- `Campaign Cartographer/` — Fractal Terrains world generation files
- `Medieval Fantasy City Generator/` — city map exports
- `Inkwell Ideas/` — dungeon and city map tools

**GM Aids & Education:**
- `GreatGM Templates/` — session planning templates
- `GreatGM Training Grounds/` — GM education material
- `MCDM/` — Matt Colville resources
- `Strongholds & Followers/` — stronghold rules supplement
- `DnDspeak/` — random tables and encounter generators
- `Roleplaying Survey/` — player preference surveys

**External Setting References:**
- `Planescape/` — Planescape setting material
- `Planescape Torment/` — video game reference material
- `Planewalker.com/` — community Planescape resources

**Inspiration Sources (non-D&D):**
- `Ambient Mixer/` — ambient sound presets for sessions
- `Anno 1800/` — architectural and city reference
- `Baldur's Gate III/` — visual and narrative reference
- `Star Wars The Old Republic/` — sci-fi visual reference
- `StarCraft/` — sci-fi visual reference
- `Skull and Bones/` — naval and ship reference
- `Stargaser/` — astronomical reference

**Loose Files at Root:**
- Unsorted images, wallpapers, and reference screenshots. These are staging — should be organized into appropriate subdirectories or moved to campaign Assets.

**Working:**
- `Todo/` — pending tasks and organization notes
- `D&D Shop Catalog/` — product reference

## Naming Conventions

- Scene files: `Scene N.X Title.md`
- Scene frontmatter `title:`: scene number only (e.g., `Scene 4.1`)
- Compendium entries: entity name as filename (e.g., `Asmodeus.md`)
- Journals: `Session NN - Character.md`
- Chapter outlines: `Chapter N.md`
- Art: `Card Name (Set Name) - art by Artist.jpg` — ASCII only

## Access Control

GREEN by default. `Players/**` is AMBER. See `.tlp` for full configuration.

## Language

The campaign is played in Czech. Scene files are bilingual:

- **English** is the authoring language — AI generates content in English, the GM thinks in English when structuring scenes, and all wikilinks and filenames use English note names.
- **Czech translations** exist so the GM can read descriptions, dialogue, and opening/closing beats aloud during the session without translating on the fly. The `## Translations` section at the bottom of each scene contains ready-to-read Czech prose — openings, closings, sensory descriptions, NPC dialogue.
- **Player journals** are written in Czech by the players after each session. They capture what happened from a character's perspective.
- **Compendium entries** are in English unless the entry is inherently Czech (a Czech-language prophecy, a song, in-world text written for Czech delivery).
