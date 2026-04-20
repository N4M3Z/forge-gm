---
name: SceneCard
description: Generate a GM-facing scene execution card — atmospheric narration interlaced with mechanics, designed for at-the-table reading. Compresses a scene file into phase-by-phase read-aloud + locked beats + mechanics quick-ref. USE WHEN scene card, GM card, table card, executive summary, run sheet, prep for the table.
version: 0.1.0
---

# SceneCard

Generate a SceneCard from an existing scene file. The card is the artifact the GM reads at the table — atmospheric narration interlaced with mechanics, organized phase by phase, with locked story beats that must fire regardless of dice.

## Instructions

1. **Confirm the source scene file.** Ask the user which scene if not specified. Read the full scene file before drafting.

2. **Identify the structural skeleton:**
    - Opening (`[!tip] Opening`) and Closing (`[!tip] Closing`) callouts
    - Combat or encounter blocks (`[!danger]`, `[!warning]`)
    - Translations under `## Translations` (if the campaign runs in a non-English language)
    - Locked beats — anything in Discoveries, Notes, or Combat that says *"this happens regardless"* / *"must fire"* / explicit trigger conditions

3. **Determine phase count.** Combat scenes use waves. Escape/discovery scenes use phases (rooms, encounters, choke points). Social scenes may have just 2-3 beats. One phase per major mechanical-or-narrative inflection.

4. **Read the template** at `Templates/SceneCard.md`. Substitute every `${VARIABLE}` placeholder. Strip the trailing `%% comment %%` annotations after substitution. Delete unused phase blocks.

5. **Write the read-aloud in the campaign's table language.** For Czech-language campaigns: Pošustová literary style, full diacritics, present-tense, sensory-rich; past tense for narrative wrap-ups in Closing; indeclinable for foreign proper names; wikilink the entities with declined display text (`[[Seraphis|Seraphisina]]`). Reference the existing scene's Translations section if narration text already exists — reuse, don't reinvent.

6. **Mechanics blocks must include** initiative-count locks, HP totals or monster references (link to Bestiary entries), DCs for skill checks, and explicit exit conditions per phase.

7. **Locked beats are the core value of the card.** These are story triggers that fire on a clock or condition, not a dice roll. List them at the top AND at the phase where they fire.

8. **Write to** `Campaigns/<campaign>/<Chapter>/<Scene Title> — SceneCard.md` next to the source scene. Frontmatter `scene:` field links back.

9. **Improv pivot field** — capture where to steer if players go off-script. The card should anticipate the most likely deviation and offer a pre-thought pivot.

## Constraints

- Read-aloud blocks use `>` blockquotes so the GM can scan them visually mid-table
- Locked beats appear twice: in the top summary AND at the phase where they fire (redundancy is the point — the GM will skim)
- Mechanics tables and quick-ref must use markdown tables, not bullets — easier to scan during play
- Never invent narration that contradicts the source scene's `[!tip]` callouts; reuse and compress instead
- File naming: `<Scene Title> — SceneCard.md` (em dash, space-separated, English)
- One SceneCard per scene file. If a session covers multiple scenes, generate one card per scene.
