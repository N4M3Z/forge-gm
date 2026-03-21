---
name: VaultAudit
description: Structured vault health check — directory structure, orphans, broken links, frontmatter, template compliance. Dispatches VaultKeeper agent. USE WHEN vault audit, check vault health, find problems, broken links, orphans, cleanup.
version: 0.1.0
---

# VaultAudit

Run a structured vault health check. Dispatches the VaultKeeper agent for the scan and presents findings organized by severity.

## Instructions

1. Ask for scope: quick (current chapter), compendium (full Compendium scan), campaign (active campaign structure), or full (everything).

2. Read `rules/user/VaultStructure.md` and `rules/user/CompendiumConventions.md` to establish what "correct" looks like.

3. Dispatch VaultKeeper agent with the scope and convention files embedded in the prompt. Wait for findings.

4. Present the audit report. Group by severity: structural, schema, hygiene, convention. For each issue, include the file path and a concrete fix.

5. Ask which issues to fix. Apply approved fixes.

## Constraints

- Never fix without asking. Report first, fix only after approval.
- The `rules/user/` directory is the authority. Don't invent standards.
- If the vault is clean, say so and stop.
