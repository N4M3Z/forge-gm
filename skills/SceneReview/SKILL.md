---
name: SceneReview
description: Multi-phase scene review — opponent critique, GM answers, joint edits, user markup, cleanup, commit. USE WHEN reviewing scenes, scene review, review session prep, polish scenes.
version: 0.1.0
---

# SceneReview

Multi-phase review process for RPG scene files. Each scene passes through opponent critique, GM discussion, joint rewrite, user markup, and cleanup.

## Before Starting

Read these files at the start of every review session:

1. **Scene Writing Conventions** — the SceneConventions rule deployed by this module
2. **The campaign's scene template** — structural template with writing rules
3. **The session outline** — narrative context, timing, key beats

These three contain everything needed to review any scene. If context compacts mid-session, re-read them.

## Phase 1: Opponent Review

Spawn an opponent agent with the **full scene content embedded in the prompt**. Do not rely on file paths — agents try to read files instead of analyzing provided content.

Include in the prompt:
- The complete scene text
- All template conventions (from SceneConventions)
- Relevant session outline section
- Key facts from prior scenes (character names, established lore, continuity hooks)

The opponent returns **numbered questions** grouped by theme:
- Template compliance violations
- Character and lore inconsistencies
- Mechanical gaps (missing DCs, stats, skill checks)
- Narrative and dramatic gaps
- Structural and cross-scene consistency

Present the questions to the user organized by theme. **No edits yet.**

## Phase 2: GM Answers

Present the opponent's questions. User responds — confirming, rejecting, or redirecting. Discuss where needed. If the user provides new lore or design decisions, note them for the rewrite.

Key patterns:
- User may answer via voice (expect transcription artifacts — parse intent, not literal words)
- User may batch-answer ("the first three are fine, skip 4, and for 5...")
- User may redirect ("that's not important, focus on X instead")
- New lore decisions become Seeds or Notes in the scene

## Phase 3: Joint Edits

For non-obvious changes, propose options organized by category. Present 2-3 options with recommendations. User confirms before writing.

Then write the full scene in one pass:
- Apply all confirmed changes from Phase 2
- Fix all template compliance issues
- Generate full AI content zone (Opening, Closing, Descriptions, Encounters, Outcomes)
- Generate translations if the campaign uses them
- Use Write (full overwrite) not Edit — Obsidian Linter may modify the file between read and edit

## Phase 4: User Markup

User opens the scene in Obsidian and:
- Makes direct edits (character swaps, asset additions, structural changes)
- Adds `%% notes %%` comments for issues they want the AI to address
- Says "process notes" or similar when ready

## Phase 5: Process Comments

Read the file. For each `%%` comment:

1. **Design question** (ideas, options) — present options to user, confirm before implementing
2. **Specific change request** — apply directly
3. **Convention change** — update template and convention files
4. **Lore addition** — add to Seeds, Notes, or Discoveries as appropriate

Delete all `%%` markers when resolved. Preserve user's direct edits. Write with full overwrite.

## Phase 6: Commit

When user requests, commit the scene and any updated convention files. Stage only the specific files that changed.

## Repeat

Move to the next scene in session order. Re-read the session outline if needed for the next scene's context.
