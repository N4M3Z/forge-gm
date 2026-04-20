---
name: SceneConventions
description: Quick reference for scene writing conventions — terse vs rich, wikilinks, formatting, combat, secrets, rewards, translations. USE WHEN writing scenes, checking scene format, scene conventions.
version: 0.1.0
---

# SceneConventions

Quick reference for scene writing conventions. Read this before writing or reviewing any scene file.

## Core Principle: Terse vs Rich

**Everything except Descriptions should be scannable at a glance.** Short, telegraphic, one line per item. The GM needs to recognize what they need instantly.

**Descriptions are the exception** — rich, high literary quality, full sensory immersion. This is what gets read aloud.

## Wikilinks

**Every named entity gets `[[ ]]`.** No exceptions: characters, locations, items, creatures, concepts, skills in challenges. This applies everywhere — frontmatter, user zone, AI zone, translations.

## Formatting Rules

| Element               | Rule                                                            |
| --------------------- | --------------------------------------------------------------- |
| Objective and Interest | Bullet list: `- **Objective:** ...` and `- **Interest:** ...`  |
| Notes                 | Bullet list, not paragraph                                      |
| Challenges            | Name + description + DCs on main line, sub-bullets for outcomes |
| Actions               | One line per character, all party members included               |
| Discoveries           | One line each                                                   |
| Seeds                 | One line each, don't restate Discoveries or Secrets             |
| Dialogue              | NPC voices only. PC lines only if no NPCs present (labeled)    |
| Combat                | Always present — contingent if not primary focus                |
| Secrets               | Every clue has a skill check + DC                               |
| Rewards               | Table format (Reward / Type / Mechanic)                         |
| Homebrew rewards      | Link to Compendium entries, don't embed full descriptions       |
| Names                 | 3 improvisation names per scene                                 |
| Music                 | Individual tracks with links, not full OSTs                     |
| Frontmatter `title:`  | Scene number only (e.g., `Scene 3.8`)                           |

## Closing Section Structure

- Closing image merges INTO the `[!tip] Closing` callout text
- **Transition** and exit triggers go OUTSIDE the callout as plain text
- Format: `**Transition:** → [[Next Scene]]` followed by bullet list of exit conditions

## Callout Types

| Callout       | Purpose                           |
| ------------- | --------------------------------- |
| `> [!tip]`    | Opening and Closing beats         |
| `> [!hint]`   | Sensory descriptions              |
| `> [!quote]`  | NPC dialogue with voice tags      |
| `> [!info]`   | Backup NPC names                  |
| `> [!warning]` | Skill encounters (non-combat)    |
| `> [!danger]` | Combat encounters (monster tables) |
| `> [!flame]`  | Complications (mid-scene twists)  |
| `> [!success]` | Rewards                          |
| `> [!question]` | Secrets (GM-only)               |
| `> [!fail]`   | Failure consequences              |

## Tags

### Scene Tags (frontmatter)

| Category     | Values                                                                  |
| ------------ | ----------------------------------------------------------------------- |
| `type/`      | `scene`                                                                 |
| `status/`    | `draft`, `review`, `final`                                              |
| `duration/`  | `short`, `medium`, `long`, `extended`                                   |
| `adventure/` | `thwart`, `collect`, `deliver`, `discover`, `escape`, `protect`         |
| `theme/`     | `awe`, `fear`, `dread`, `chase`, `discovery`, `mystery`, `betrayal`     |
| `adversary/` | `henchmen`, `lieutenant`, `mastermind`, `environment`, `faction`        |

### Inline Tags

| Tag                  | Usage                    |
| -------------------- | ------------------------ |
| `#voice/low`, etc.   | Character voice direction |
| `#sense/sight`, etc. | Sensory callouts          |
| `#lore/canon`        | Official D&D content     |
| `#lore/homebrew`     | Original campaign content |
| `#lore/adapted`      | Canon with campaign spin  |

## Status Field

```yaml
status: draft | canon | revealed | secret
```

- `draft` — Work in progress
- `canon` — GM truth (may contain secrets)
- `revealed` — Players have learned this
- `secret` — Players must not see

## Comments

Delete all `%%` comments when processing a scene. They are user instructions to the AI, not content.
