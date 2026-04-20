Scene files and long compendium entries include navigation links between sections. This helps the GM jump between the English content and translations without scrolling.

Add `[[#Translations|Translations →]]` before the Descriptions section. Add `[[#Descriptions|← Descriptions]]` at the top of the Translations section. Obsidian Linter enforces English link text.

For scene translations, use typed callouts:

| Callout                      | Purpose                            |
| ---------------------------- | ---------------------------------- |
| `[!abstract]` Terminologie   | Scene-specific terminology table   |
| `[!tip]` Otevírací scéna     | Opening translation                |
| `[!tip]` Závěrečná scéna     | Closing translation                |
| `[!hint]` Popis scény        | Sensory descriptions               |
| `[!quote]` Dialogy           | NPC dialogue                       |

For compendium entries with multiple languages, use `language: en` or `language: cs` in frontmatter and `aliases:` for the other language's name.
