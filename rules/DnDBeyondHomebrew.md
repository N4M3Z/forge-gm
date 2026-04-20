D&D Beyond homebrew feats are web-UI only (no API). Create at Collections > My Homebrew Creations > Create a Feat.

Key fields: Name, Description (HTML via `</>` icon), Snippet (dynamic codes), Prerequisites, Modifiers, Spells, Actions, Options.

Snippet codes: `{{modifier:cha}}`, `{{savedc:str}}`, `{{proficiency}}`, `{{classlevel}}`. Codes only work in snippet fields, not descriptions.

Actions with limited uses require a two-step save: create the action first with Activation Type and Reset Type, save, then edit to unlock the limited uses field.

Options can only grant Actions, not Modifiers or Spells. For branching mechanics, use top-level modifiers with "Choose" subtype.

All homebrew feats are type "General" — the builder cannot create Origin Feats, Fighting Styles, or Epic Boons.
