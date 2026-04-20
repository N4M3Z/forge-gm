---
name: StyleCzech
description: Polish Czech prose in RPG scene files to a register matching the setting (fantasy, sci-fi, etc.). USE WHEN polishing Czech translations, stylistic pass on Czech scene translations, Czech register cleanup, applying Pošustová style, Czech fantasy register, Czech translation polish.
version: 0.1.0
---

# StyleCzech

Polish Czech prose in RPG scene files to a register matching the setting. Text is delivered aloud at the table; clarity wins over pedantic register-cranking.

Each register is a self-contained style companion in this skill directory. Current styles:

- `Fantasy.md` — elevated Pán-prstenů register (Pošustová etalon); for high fantasy and Tolkien-adjacent settings.

Future styles land as sibling files (`Scifi.md`, `Noir.md`, etc.) following the same shape — graded register, levers, non-levers, gaps, and sources.

## Scope

Target: the `## Translations` section of scene files (Obsidian vault). Not for English source content, frontmatter, Assets, scene mechanics, or the Terminologie glossary block (surfaced as flags — user decides).

## Workflow

1. **Select the style**. Default is `Fantasy` unless the user specifies another. Read the chosen style companion (e.g. `Fantasy.md`) for levers, graded-register guidance, and references.

2. **Scope the pass**. Determine target scene(s). The style file documents which callouts and dialogues map to `up/middle/down` register zones.

3. **Refresh research (optional)**. If the style file's `## Sources` are stale or this is the first invocation in the repository, dispatch a WebResearcher agent to refresh and commit the update.

4. **Sample calibration**. Pick the most register-relevant passage (usually an opening or a description in the up zone). Produce a before/after using the style's levers. Annotate which levers fired. Present to user. Get sign-off or adjustments before mass application. No writes.

5. **Dispatch translator**. Spawn a general-purpose agent with:
    - Scene file paths.
    - Contents of the selected style file.
    - Preservation invariants: `[[wikilinks]]`, callout headers, `#sense/*` and `#voice/*` tags, italics, Czech diacritics, the Terminologie glossary block.
    - Target: only the `## Translations` section of each scene.
    - Output format: per-scene rewritten block + cross-scene consistency notes + glossary flags.

6. **Diff review**. Present the agent's diffs scene by scene. User approves, adjusts, or skips per-scene.

7. **Apply**. For each approved scene, replace the `## Translations` section via Edit. Preserve Terminologie blocks byte-identical unless the user explicitly authorized a glossary edit.

8. **Verify**. Grep the post-edit state for obvious issues (reverted quote styles, broken wikilinks, remnants of old spellings). Report.

## Pressure scenarios

**"Just one scene, skip the sample."** Still do the sample. A single scene's `## Translations` block is often ~100 lines of Czech; the user may reject the register direction after seeing the full rewrite. Sample-first costs little and prevents scope regret.

**"Apply all levers uniformly."** No. The selected style file defines graded register zones (e.g. up/middle/down). Do not flatten. Hobbits do not speak like elves; noir PIs do not speak like technocrats.

**"The glossary has modern terms — fix them in one go."** No. Terminologie changes are user decisions. Flag suggested replacements in a separate `## Glossary flags` section at the end of the diff report. The user amends the glossary in a follow-up pass.

## Constraints

- Preserve every `[[wikilink]]` byte-identical, including display text.
- Preserve callout headers, sense/voice tags, italic markers, Czech diacritics.
- Do not touch English content, frontmatter, Assets, scene mechanics.
- The Terminologie glossary is never rewritten inline; surface changes as flags.
- Sample-first is mandatory on any pass touching more than one scene or more than ~30 lines of Czech.
- Respect the style file's graded register zones.
- Style-specific gaps (e.g. Fantasy's measurement-units gap) are documented in the style file; do not override them without fresh research.
