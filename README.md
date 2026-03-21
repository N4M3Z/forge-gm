# forge-gm

RPG session prep toolkit for AI-assisted game mastering. Scene writing conventions, multi-phase review, art/music scouting, lore integrity, and GM adaptation agents.

## What It Does

Agents:

- **GameMaster** — generates and adapts scenes when the story deviates from the master arc
- **LoreMaster** — audits scenes for missing compendium references, enforces lore classification
- **ArtScout** — finds MTG card art from Scryfall for scene atmosphere
- **MusicScout** — finds Apple Music tracks for scene atmosphere
- **SessionScribe** — processes raw player notes into structured session journals
- **SceneCritic** — stress-tests scenes for table playability
- **PlanarSage** — Planescape lore consultant
- **VaultKeeper** — campaign vault auditor

Skills:

- **SceneReview** — multi-phase opponent review procedure
- **SceneGenerate** — generate or adapt scenes with diagnostic pre-flight
- **SceneConventions** — quick reference for scene writing
- **SessionPrep** — session prep workflow from outline to scene-ready files
- **LoreAudit** — audit scenes and compendium for lore integrity
- **CompendiumEntry** — create or enrich a compendium entry
- **DraftFeat** / **DraftItem** — homebrew D&D 5e content
- **SecretTracker** — track secrets and clues across sessions
- **ArtDescribe** — generate visual descriptions for MTG card art
- **VaultAudit** / **VaultCouncil** — vault health checks

## Install

Requires [forge-cli](https://github.com/N4M3Z/forge-cli):

```sh
make install
```

Or have your AI resolve [INSTALL.md](INSTALL.md) autonomously:

```sh
curl -s https://raw.githubusercontent.com/N4M3Z/forge-gm/main/INSTALL.md | claude
```

## Validate

```sh
make validate
```

## License

EUPL-1.2
