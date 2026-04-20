---
name: LoreAudit
description: Audit scenes and compendium for lore integrity — missing wikilinks, unclassified entries, consistency issues, orphaned stubs. USE WHEN auditing scenes, lore check, compendium audit, consistency check, find missing entries.
version: 0.1.0
---

# LoreAudit

Audit campaign vault content for lore integrity. Dispatches the LoreMaster agent for heavy lifting, synthesizes findings into a structured report.

## Instructions

1. Ask the user for scope: single scene, chapter (all scenes in a directory), or full compendium audit.

2. For **scene audit** scope, read each scene file and extract every `[[wikilink]]`. For each link, search the Compendium directory for a matching `.md` file. Categorize results as: exists and rich, exists but stub-only, or missing entirely.

3. For **compendium audit** scope, scan all `Compendium/**/*.md` entries. Check each for: frontmatter present, lore classification tag (`#lore/canon`, `#lore/homebrew`, `#lore/adapted`), status field, language field. Flag entries missing required fields.

4. Check for duplicates — similar names, same entity in different files. Check for orphans — entries with no inbound links from scenes or MoC files. Check folder placement — a character in the Locations directory is misplaced.

5. For **consistency checking**, grep for entity names across all scene files. Collect every description, trait, location, and timeline reference. Flag contradictions with file paths and line references.

6. Present findings as a structured report:

```markdown
## Lore Audit Report

### Missing from Compendium
| Entity       | Scenes Referenced | Suggested Folder | Lore Type |
| ------------ | ----------------- | ---------------- | --------- |

### Stubs Needing Enrichment
| Entity       | Current State   | Priority                   |
| ------------ | --------------- | -------------------------- |

### Consistency Issues
| Entity       | Issue           | Files                      |
| ------------ | --------------- | -------------------------- |

### Misclassified Lore
| Entity       | Current Tag     | Should Be | Reason          |
| ------------ | --------------- | --------- | --------------- |
```

7. Ask the user which missing entries to create as stubs. Create approved stubs with proper frontmatter and folder placement.

## Constraints

- Never modify scene content — scenes are GM territory
- Create stubs freely when approved, but only enrich entries when explicitly asked
- Report problems as a structured table, don't silently fix consistency issues
- Use wikilinks for all entity references in the report
