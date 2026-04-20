Every compendium entry needs frontmatter with at minimum: `type`, `status`, `tags` (with lore classification). No orphaned files — every entry linked from at least one scene or MoC. No duplicates — merge entries with similar names for the same entity. Aliases in frontmatter for alternate names and spellings.

Minimum frontmatter:

```yaml
---
aliases: []
type: character | location | organization | item | creature | event | concept
status: draft | canon | revealed | secret
tags:
    - "#lore/canon" | "#lore/homebrew" | "#lore/adapted"
language: en | cs
---
```

Full entry body structure:

```markdown
# Entity Name

Brief description (1-2 sentences).

## Details

Expanded lore, backstory, abilities, relationships.

## Appearances

- [[Scene X.Y]] — context of appearance

## References

- [D&D Beyond: Name](url) — for canon entries only
```

Canon entries get external reference links. Homebrew entries do not. Adapted entries note what differs from canon in the body. Czech entries use `language: cs` and keep the original language — do not translate to English.
