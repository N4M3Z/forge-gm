# Fantasy

Pán-prstenů-style elevated Czech fantasy register, modeled on Stanislava Pošustová's translation of Tolkien's *Lord of the Rings*. Loaded by the `StyleCzech` skill when polishing Czech fantasy prose — high narration, prophetic declarations, ancient/divine NPC dialogue.

## Graded register

Apply archaism selectively. Pošustová mirrors the source material's stratification:

- **Up (hardest)** — elvish, divine, ancient NPC dialogue; prophecies; high narration in `[!hint]` descriptions and `[!tip]` openings/closings.
- **Middle** — scene narration, named-character dialogue.
- **Down (lightest)** — folk NPCs, banter, humor, commoners.

Do not apply all levers uniformly. Each lever below is tagged with its register zone.

## Levers

Each lever: cue, before/after, register zone, confidence. "Sourced" = backed by citations in § Sources; "asserted" = consistent with her method but not directly sourced.

### Tense and narration

#### Narrative past over gnomic present

Descriptive prose in past tense, not gnomic present.

- Before: *Komora zadržuje dech.*
- After: *Komora zadržela dech.*
- Register: narration (middle, up)
- Confidence: asserted — common Czech literary norm; not sourced specifically

#### Archaic speech verbs

Elevate dialogue attribution with `pravil`, `děl`, `vece` instead of `řekl`. Sparingly — one per scene maximum in the up zone. Over-use becomes pastiche.

- Before: *„…," řekl Elrond.*
- After: *„…," pravil Elrond.*
- Register: up only
- Confidence: sourced

### Relatives

#### `jenž/jež/jehož` over `který`

Relative pronoun swap at elevated beats. Canonical anchor: the Ring verse — *„Jeden pro Temného pána, jenž dlí na trůně v zemi Mordor."*

- Before: *Pán, který dlí v Mordoru.*
- After: *Pán, jenž dlí v Mordoru.*
- Register: up, middle
- Confidence: sourced

Reserve `který` for neutral and folk register.

### Lexicon

#### Slavic-root archaic landscape and state terms

Replace neutral modern terms with native Slavic archaisms in descriptive and prophetic prose.

| Neutral  | Archaic  | Domain          |
| -------- | -------- | --------------- |
| les      | hvozd    | dark old forest |
| hrob     | mohyla   | barrow          |
| kopec    | mohyla   | burial mound    |
| být      | dlít     | to dwell        |
| vysloven | vyřčen   | uttered         |

- Register: up (landscape, prophecy, ancient speech)
- Confidence: sourced

#### Native Slavic roots over Latinate/Germanic loans

Prefer the native synonym when one exists and register is up.

| Loan    | Native    |
| ------- | --------- |
| funkce  | úloha     |
| situace | postavení |
| moment  | chvíle    |
| koridor | chodba    |

- Register: up
- Confidence: sourced

#### Instrumental after `být` for identity

Predicative instrumental for identity statements.

- Before: *Není člověk.*
- After: *Není člověkem.*
- Register: up, middle
- Confidence: asserted — standard Czech literary marker; not sourced specifically

### Syntax

#### VS inversion at dramatic beats

Pull the verb forward, or front a locative, at openings, closings, and prophetic declarations.

- Before: *Svislá puklina se rozevřela.*
- After: *Rozevřela se svislá puklina.*
- Register: up
- Confidence: sourced via Ring verse (`jenž dlí na trůně`)

#### Rhythmic compression

Replace subclause-heavy Englishisms with short dramatic beats.

- Before: *Čepel přijde první, a pak ji bude následovat tělo.*
- After: *Ostří šlo první. Tělo za ním.*
- Register: all
- Confidence: asserted — consistent with her calibrated style but not quantified

### Typography

#### Czech low-open/high-close quotes

Always `„…"`. Never `"…"`, never `''`.

- Confidence: sourced (Argo / Mladá fronta publisher convention)

#### Em dash for parenthetical breaks

Use ` — ` for asides. Never `--` or hyphen.

- Confidence: sourced (publisher convention)

## Non-levers

- **Biblical-tier archaisms** (`druhdy`, `kdož`, verb-enclitic clitic piles). Her register is calibrated, not cranked. Test: would a 1960s Czech literary novel use this? If no, cut.
- **19th-century Rukopis pastiche**. Pošustová explicitly rejected Old Czech as incomprehensible to modern readers.
- **Uniform archaism across all register zones**. Hobbits do not speak like elves.
- **Rewriting Terminologie glossary entries inline**. Surface as flags; user decides.

## Measurement units (GAP)

**Not sourced.** Research could not confirm whether Pošustová converts Tolkien's imperial units (`míle`, `stopa`, `furlong`) to native Czech units (`sáh`, `hon`, `loket`). Prior assertions in the motivating session (e.g. `stop → sáhů`) are uncorroborated.

To resolve: grep a Pošustová ebook for unit terms and establish her actual practice before prescribing a rule. Until resolved, do not mass-convert units; flag any unit in the source and let the user decide.

## Register summary (Pošustová)

Stanislava Pošustová's translation (drafted 1979–1980 in samizdat, published by Mladá fronta 1990–1992) is the canonical Czech *Lord of the Rings*. Her self-described method is *"mírně archaická, důsledně literární čeština"* ("slightly archaic, consistently literary Czech") applied as a graded register: elves and Gondorians get the elevated tier, hobbits lean toward folk register. She leans on her training in historical Czech grammar rather than on blanket archaism, and she explicitly concedes Czech lacks English's deep class-marked register stratification — so her "high" tier is built by accumulating small elevated markers rather than by switching language varieties. The result is a durable literary Czech that reads as timeless-elevated rather than period-pastiche — closer to Vančura or literary Jirásek than to 19th-century Rukopis-archaism.

## Research findings

Each finding below is usable as a polishing cue. Confidence levels reflect what the public record supports.

1. **Graded register, not uniform archaism** (established). Elves' speech rendered in *"mírně archaickou a důsledně literární češtinou"*; hobbits in folk dialect; narrator between ([PROOF3], [MEDIUM3]).
2. **Relative `jenž/jež/jehož` over `který` at elevated beats** (likely). The Ring verse is the canonical case ([WIKIQUOTE]).
3. **Archaic literary verbs for speech acts** (likely). `pravil`, `děl`, `vece` appear where unmarked translators use `řekl`.
4. **Archaic lexical stock in descriptive passages** (established, narrow examples). *mohyla* (barrow), *hvozd* (old forest), *vyřčen* (uttered), *dlí* (dwells) ([CESKYJAZYK]).
5. **Consulted Old Czech month names and historical grammar as reference stock** (established). She mined Slavic-studies seminars for Old Czech calendar names and used historical-grammar knowledge across the text ([AKTUALNE], [MEDIUM3], [PROOF3]).
6. **Preference for native Slavic roots over Latinate/Germanic loans in high register** (likely). Consistent with her "důsledně literární" aim.
7. **Verb-subject inversion and fronted adverbials at dramatic beats** (uncertain — inferred from Ring verse construction).
8. **Punctuation and typography follow Czech literary norms** (inferred from publisher convention, not stylistic analysis).
9. **Narrative past tense, not gnomic present, for descriptive prose** (uncertain — general Czech literary norm, not Pošustová-specific).
10. **Contrast with alternative Czech fantasy registers** (likely, coarse). She sits between 19th-century Rukopis archaism (rejected) and modern neutral literary Czech. Test each archaism against "would a 1960s Czech literary novel use this?"

## Research gaps

- **Measurement units** — public sources do not document whether Pošustová converts Tolkien's imperial units to native Czech. Verifying needs grep-level reading of a Pošustová ebook.
- **Instrumental case after `být` for identity** — asserted as a Czech literary marker; no source specifically attributes this pattern to her prose.
- **Subordinate clause rhythm** — no academic analysis surfaced that quantifies her clause-length distribution.
- **Corpus-linguistic analysis (ČNK)** — no published ČNK study citing Pošustová specifically.
- **Comparison with Petr Štěpán's poetry translations** — Konrádová's thesis covers this for verse; full PDF reading needed for confirmation.

## Sources

- [Wikipedia — Stanislava Pošustová][WIKI_POSUSTOVA]
- [Tolkien.cz — rozhovor s Pošustovou][TOLKIENCZ]
- [Proofreading.cz — interview 3. díl (register a archaism)][PROOF3]
- [Proofreading.cz — interview 1. díl][PROOF1]
- [Medium — Pekarik rozhovor, 3. časť][MEDIUM3]
- [Aktuálně.cz — Pána prstenů šířila Charta 77][AKTUALNE]
- [Argo — Vymýšlení českých jmen byla zábavná výzva][ARGO]
- [Hospodářské noviny — rozhovor][HN]
- [Wikiquote — Dílo: Pán prstenů (Ring verse, canonical lines)][WIKIQUOTE]
- [ČeskyJazyk — rozbor Pán prstenů (archaismy: mohyla, hvozd, vyřčen)][CESKYJAZYK]
- [Pokorný — *Překlad neologismů a vlastních jmen v trilogii Pán prstenů*, UJEP 2022][POKORNY]
- [Konrádová — *Srovnání dvou českých překladů vybraných básní z trilogie Pán prstenů*, JČU][KONRADOVA]
- [Hrabal — *Pán Prstenů: Analýza překladu vlastních jmen*, UTB][HRABAL]

[WIKI_POSUSTOVA]: https://cs.wikipedia.org/wiki/Stanislava_Po%C5%A1ustov%C3%A1
[TOLKIENCZ]: http://fantasy-scifi.net/jrr_tolkien/vite_ze/vite_ze.php?cl=285
[PROOF3]: https://proofreading.cz/interview-s-prekladatelkou-pana-prstenu-3-dil/
[PROOF1]: https://proofreading.cz/interview-s-legendarni-ceskou-prekladatelkou/
[MEDIUM3]: https://medium.com/@thalensvk/3-as-rozhovoru-s-eskou-prekladate-kou-knih-j-r-r-tolkiena-stanislavou-postustovou-mensikovou-10d0ed926c39
[AKTUALNE]: https://magazin.aktualne.cz/prekladatelka-posustova-pana-prstenu-sirila-charta-77/r~ce788efe37fe11e494d7002590604f2e/
[ARGO]: https://argo.cz/prekladatelka-tolkiena-vymysleni-ceskych-jmen-byla-zabavna-vyzva/
[HN]: https://hn.cz/c1-23232075-stanislava-posustova-pana-prstenu-jsem-si-hned-zamilovala
[WIKIQUOTE]: https://cs.m.wikiquote.org/wiki/D%C3%ADlo:P%C3%A1n_prsten%C5%AF
[CESKYJAZYK]: https://www.cesky-jazyk.cz/ctenarsky-denik/john-ronald-reuel-tolkien/pan-prstenu-spolecenstvo-prstenu-rozbor.html
[POKORNY]: https://theses.cz/id/tg0anj/?lang=sk
[KONRADOVA]: https://theses.cz/id/ulhxcf/
[HRABAL]: https://theses.cz/id/2cmbdb/
