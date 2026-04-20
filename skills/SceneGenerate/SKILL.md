---
name: SceneGenerate
description: Generate or adapt scenes with diagnostic pre-flight — handles story deviations, new scene requests, and raw content formatting. USE WHEN story went sideways, generate scene, adapt scene, players deviated, new scene needed, rewrite scene.
version: 0.1.0
---

# SceneGenerate

Generate, adapt, or rewrite RPG scenes using the GameMaster agent's diagnostic workflow. Ensures adaptations preserve narrative payload, honor player choices, and don't orphan future content.

## Instructions

1. Determine the mode from the user's request:
   - **REWRITE** — "rewrite this", "format this into a scene", raw content provided
   - **ADAPT** — "players did X instead of Y", "story went sideways", deviation from plan
   - **GENERATE** — "I need a new scene for...", "create a scene about..."

2. For **REWRITE mode**, skip diagnostic pre-flight entirely. Read the source content and the campaign's scene template. Transform into full scene template format following SceneConventions. Output the complete scene file.

3. For **ADAPT mode**, run the diagnostic pre-flight:
   - Ask the GM: What narrative payload must survive this deviation?
   - Ask the GM: What did the players choose, and what would make that choice feel meaningful?
   - Research: Query the master arc and existing scenes to find what downstream content depends on this scene. Report dependencies before proposing options.

4. For **GENERATE mode**, query the master arc for context, then run the same diagnostic pre-flight. Challenge whether this scene is necessary — could existing content stretch to cover it?

5. In ADAPT and GENERATE modes, challenge the GM's framing before proposing options. Push back on "ruined" language, assumptions of correction, hidden GM attachment to specific outcomes, and missed opportunities where the deviation could be more interesting than the plan.

6. Propose 2-3 adaptation or generation options:
   - Option A: Minimal change (preserve most of the original)
   - Option B: Moderate rewrite (new challenges, same destination)
   - Option C: Full pivot (embrace the deviation, new destination)

7. Generate the chosen option as a complete, session-ready scene file following SceneConventions. Include combat encounters, skill challenges with DCs, NPC dialogue with voice tags, and translations if applicable.

## Constraints

- Never control player actions — scenes define situations, players decide responses
- Never contradict established master arc intent without explicit GM approval
- Always output complete scenes — no "fill in later" placeholders
- Surface lore contradictions before generating
- REWRITE mode is pure formatting — no questions, no diagnostics
- **Confirm every NPC, location, and invented term against the compendium before propagating.** Grep `Compendium/Characters/`, `Compendium/Locations/`, etc. for the name and likely near-variants. If a name does not exist, ask the user before inventing a spelling — never substitute a near-homophone from training-set fantasy lexicon. Once a wrong variant lands in a scene file, it propagates through every subsequent agent dispatch.
- Before dispatching parallel sub-agents (e.g., generating multiple scenes at once), sanitize the shared context — chapter overviews and earlier conversation may contain provisional names that have since been corrected. Contamination propagates silently across agents.
