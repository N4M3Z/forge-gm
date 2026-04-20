Scene files have two zones: user-editable (top) and AI-generated (below `## Content`). Everything except Descriptions is terse and scannable. Descriptions are rich, literary, full sensory immersion.

Every named entity gets `[[wikilinks]]` — characters, locations, items, creatures, concepts, skills. No exceptions.

Every scene needs a combat option — contingent if not primary focus. Every secret needs a skill check with DC. Every reward needs a table (Reward / Type / Mechanic). Seeds are one line each. Dialogue is for NPC voices the GM performs. Delete all `%%` comments when processing.

Closing images merge into the `[!tip] Closing` callout. Transition and exit triggers go outside as plain text.

Frontmatter `title:` is the scene number only (e.g., `Scene 3.8`). The scene name lives in the heading.

Assets section follows a fixed pattern: `**Maps:**` line with `![[Map Name]]` or blank; `**Images:**` with exactly 6 art embeds arranged as 3 pairs per line (`![[file.jpg|330]] ![[file.jpg|330]]`); `**Music:**` as 3–4 Apple Music URLs formatted as `- [Track - Artist (Album)](url)`.

`![[*.jpg]]` embeds with short, unstructured filenames (e.g., `Fortitude Pyramid.jpg`) are likely placeholders — real art library files carry source and artist attribution. Verify their existence on disk before trusting them, and offer to replace with catalog entries when authoring or cleaning up a scene.

Before authoring or cleaning a scene's Assets or Translations section, read a recent sibling scene in the same campaign arc. The written conventions above document the current baseline; siblings reveal stylistic drift and local variations the rule does not capture.
