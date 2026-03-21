The Leviathan vault is an Obsidian-based D&D campaign management system. GREEN by default (Players/** is AMBER). Three active campaigns: Exodus (current), Labyrinth (legacy), Expeditions (side content).

Directory structure:

- `Campaigns/Exodus/` — active campaign. Chapters contain scene files (`Scene N.X Title.md`). Session Prep holds proposals and outlines. Journals hold player-written session recaps in Czech. `_Source/` holds the original ChatGPT Master Arc export.
- `Compendium/` — world-building library. Subdirectories by entity type: Characters, Locations, Organizations, History, Powers, Bestiary, Items, Seeds, Inspirations, Rulings, Homebrew (Feats, Items), Documents, Secrets, Encounters, Engines, Technologies, Nature, People, Buildings, Planes.
- `Orchestration/` — AI infrastructure. Scene Writing Conventions, Scene Review procedure, agent definitions (GameMaster, LoreMaster, ArtScout, MusicScout). Memory subdirectory for decisions, ideas.
- `Players/` — AMBER. Player cards and preferences. Do not read without safe-read.
- `Resources/` — D&D reference material, maps, MTG art library (`MTG Pics/` with `.art-catalog.json`), D&D Beyond integration files, external illustrations.
- `Templates/` — Scene template (`Scene.md`). Legacy templates in `Legacy/`.
- `Assets/` — shared assets across campaigns.

Scene files follow a two-zone structure: user-editable top (Objective, Interest, Challenges, Actions, Discoveries, Seeds, Notes, Assets) and AI-generated bottom (below `## Content` — Opening, Closing, Descriptions, Dialogue, Encounters, Outcomes). Czech translations in a `## Translations` section at the end.

The session is in Czech. Scene dialogue is written in both English (for AI reference) and Czech (for table use). Descriptions are bilingual. All wikilinks use English note names.

MTG card art is the primary visual reference. The art catalog at `Resources/MTG Pics/.art-catalog.json` contains card metadata and descriptions for searching. Art is organized by set name in subdirectories. Filenames follow `Card Name (Set Name) - art by Artist.jpg`.
