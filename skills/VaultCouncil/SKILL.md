---
name: VaultCouncil
description: Convene a vault architecture council — multi-perspective debate on vault reorganization, directory structure, compendium taxonomy, template evolution, and campaign workflow. USE WHEN reorganize vault, restructure, rethink organization, vault architecture, improve vault, compendium redesign.
version: 0.1.0
---

# VaultCouncil

Convene a multi-perspective council to debate vault architecture decisions. For structural audits (finding problems), use VaultAudit. This council is for REDESIGN — when the GM wants to rethink how the vault is organized, not just fix what's broken.

## When to Use

- Reorganizing the Compendium taxonomy (adding/removing/merging directories)
- Changing the campaign file structure (chapter layout, scene template evolution)
- Introducing new conventions (tagging schemes, frontmatter schemas, naming patterns)
- Merging or splitting vaults
- Evaluating whether the current structure scales for multi-campaign use

## Council Roster

Three specialists, 3-round debate:

**Librarian** — organization and taxonomy. Asks: "Can a new GM find anything in 30 seconds? Does every entity have exactly one correct home? Are there overlaps, gaps, or ambiguities in the directory structure?"

**Architect** — workflow and scalability. Asks: "Does this structure support the session prep workflow? Does it scale to a second campaign without restructuring? Are there bottlenecks — places where files pile up because the routing is unclear?"

**Practitioner** — daily-use friction. Asks: "What annoys the GM every session? Where do files end up in the wrong place because the 'right' place is unintuitive? What conventions exist on paper but are never followed because they're too cumbersome?"

## Instructions

1. Create a team (TeamCreate). Spawn three agents with the specialist briefs above.

2. **Round 1 — Assessment.** Each specialist audits the vault from their perspective. Librarian checks taxonomy. Architect checks workflow. Practitioner checks friction. Each sends findings to the team lead.

3. Present Round 1 findings to the GM. Ask for input — what resonates, what's wrong, what constraints exist.

4. **Round 2 — Proposals.** Each specialist proposes changes. Librarian proposes directory restructuring. Architect proposes workflow changes. Practitioner proposes convention simplifications. Each challenges the others' proposals.

5. Present Round 2 proposals. GM selects direction.

6. **Round 3 — Convergence.** Specialists merge into a single reorganization plan. Include: what moves where, what gets created, what gets deprecated, migration steps, and what DOESN'T change (stability is a feature).

7. Present the final plan. Apply approved changes. Update `rules/user/VaultStructure.md` to reflect the new canonical structure.

## Constraints

- Never reorganize without the plan being approved. Propose, then execute.
- Update `rules/user/VaultStructure.md` after any structural change — it is the source of truth.
- Stability is a feature. Don't reorganize for the sake of reorganizing. If the current structure works, say so.
- The council debates structure, not content. Content decisions (lore, scenes, NPCs) belong to the GM and the other skills.
