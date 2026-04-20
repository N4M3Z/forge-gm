---
name: SessionHandoff
description: Pack a played session's state into vault structure so a fresh Claude Code session can resume cold — handoff doc, NPC stub updates, journal stub, vault TODOs. USE WHEN session handoff, session wrap-up, hand off, prep for next session, capture session state.
version: 0.1.0
---

Pack the state of a played (or about-to-be-played) session into vault structure so another Claude Code session can resume without re-excavating the conversation.

## Instructions

1. **Confirm the session label.** Ask if not specified (e.g., "Session 08"). Identify the campaign and chapter from context or by reading the current chapter overview.

2. **Read the template** at `Templates/SessionHandoff.md`. Substitute every `${VARIABLE}` placeholder. Strip the trailing `%% comment %%` annotations.

3. **Gather state from the conversation:**
    - **What changed:** canon shifts, character state changes, NPC reveals, locked outcomes
    - **Active NPCs:** present-tense state — who is alive, where they are, what they want
    - **Pacing firewalls:** explicit player constraints (e.g., "Player X: NO godhood reveal — Umilier=Milil stays secret")
    - **Sensitivity scopes:** narrow scope, not broad. Record what IS in scope and what is NOT.
    - **Open threads:** unresolved hooks, foreshadow waiting to land, secrets not yet spent
    - **Improv overrides:** where the table deviated from prep — these become canon and must propagate

4. **Write the handoff** to `Campaigns/<campaign>/Session Prep/<Chapter>/<Session> Handoff.md`. Frontmatter `session:` field links to the journal or session prep proposal.

5. **Audit the compendium for staleness.** For each NPC in the Active NPCs table, grep `Compendium/Characters/` (or `Compendium/Powers/`) for the entry. If the entry is stale (does not reflect current state), add a TODO to the handoff's "Pending vault work" section. Do NOT auto-update entries — flag for user review.

6. **Create or update the journal stub** at `Campaigns/<campaign>/Journals/<Session> - <Title TBD>.md` if it does not already exist. Match existing journal format (read a recent journal as template).

7. **Update CLAUDE.md if and only if** the chapter pointer is stale. The current chapter is the one with the most recent session prep work. Do not bloat CLAUDE.md with NPC canon — the canon lives in `Compendium/Characters/`.

8. **Verify** by asking: could a fresh Claude session, reading only this handoff + the linked files, answer "what's the state of <chapter> and what's next?" If not, expand the relevant section.

## Constraints

- Pacing firewalls and sensitivity scopes use explicit scope language — never overgeneralize. State what IS in scope and what is NOT.
- NPC state goes in the handoff table, not in CLAUDE.md. The single source of truth for NPC canon is `Compendium/Characters/`.
- Do not invent state changes — if you are unsure whether something happened or was just discussed, ask the user before recording it as canon.
- The handoff is a checkpoint, not a journal. The player writes the journal post-session in their own voice. The handoff is for the next Claude.
- File naming: `<Session Label> Handoff.md` (e.g., `Session 08 Handoff.md`). English. No diacritics in filename.
- Improv overrides must be flagged loudly — they are the most common cause of next-session drift.
