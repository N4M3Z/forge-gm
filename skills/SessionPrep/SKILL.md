---
name: SessionPrep
description: Session prep workflow — from outline to scene-ready files. Covers proposal, outline, scene population, and review. USE WHEN preparing a session, session prep, plan session, build scenes from outline.
version: 0.1.0
---

# SessionPrep

Session preparation workflow for tabletop RPG campaigns. Takes a session from proposal through to reviewed, table-ready scenes.

## Workflow

### Step 1: Session Proposal

Create a session proposal document with:

- **Session goals** — what narrative beats must land
- **Foundational rules** — any new world rules established this session
- **Lore updates** — what becomes canon
- **Day-by-day breakdown** — parts with scene references, timing, and core beats
- **Lazy DM elements** — strong starts, secrets and clues, fantastic locations, NPCs, monsters

The proposal is the high-level "what happens and why." Status: `draft` until GM approves, then `approved`.

### Step 2: Session Outline

Convert the approved proposal into a GM running outline:

- Scene-by-scene with timing estimates
- Key dialogue lines with voice tags
- Rules established (table format)
- Secrets and clues checklist (`- [ ]` items)
- NPC quick reference (NPC / Voice / Key Line)
- Quick reference table (Scene / Time / Core Beat)

The outline is the at-the-table reference. Keep it scannable.

### Step 3: Scene Population

For each scene in the outline:

1. Check if the scene file exists in the campaign's chapter directory
2. If not, create it from the campaign's scene template
3. Populate the user-editable zone (top): Objective, Interest, Challenges, Actions, Discoveries, Seeds, Notes, Assets
4. Generate the AI content zone (below `## Content`): Opening, Closing, Descriptions, Dialogue, Encounters, Combat, Complications, Outcomes
5. Generate translations if the campaign uses them
6. Set frontmatter status to `draft`

Use the GameMaster agent in REWRITE mode for bulk scene population.

### Step 4: Scene Review

Run SceneReview on each scene in session order. This promotes scenes from `draft` to `review` or `final`.

### Step 5: Asset Scouting

Optionally dispatch ArtScout and MusicScout agents to find art and music for each scene. These run in parallel and update scene asset fields.

### Step 6: GM Cheat Sheet

After all scenes are reviewed, create a condensed cheat sheet for at the table:

- Scene order with page/time estimates
- Key NPC names and voice notes
- Critical DCs and stat blocks
- Secrets checklist
- Music playlist links

## Session Prep Directory

Store working documents in `Session Prep/Chapter N/`:

```
Session Prep/
    Chapter 3/
        Session 06 Proposal.md
        Session 06-07 Outline.md
        Session 06-07 Proposal.md
```

Archive Session Prep after the session is played. Canonical scene files live in `Chapter N/`.
