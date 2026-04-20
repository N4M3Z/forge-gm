---
title: Planescape Knowledge Pipeline
description: How the PlanarSage agent sources Planescape lore — local markdown corpus first, online queries for gaps.
type: adr
category: architecture
tags:
    - planescape
    - agent
    - knowledge-corpus
status: accepted
created: 2026-03-23
updated: 2026-03-23
author: Martin Zeman
project: forge-gm
responsible:
    - Martin Zeman
accountable:
    - Martin Zeman
consulted: []
informed: []
upstream: []
---

# GM-0001 Planescape Knowledge Pipeline

## Context and Problem Statement

The Leviathan campaign is set in the Planescape multiverse. The PlanarSage agent needs authoritative Planescape lore to answer questions, suggest content, and validate canon accuracy. The 2nd Edition sourcebooks contain the deepest lore but exist only as scanned PDFs. The 5e release (2023) is thinner but structured. Fan resources (planewalker.com, mimir.net) contain substantial original synthesis not found in official sources.

The PDFs cannot be committed to the repository (size, copyright). The knowledge must be serialized into markdown files that the agent can read directly.

## Considered Options

- **Local markdown corpus, agent-driven reads** — serialize sources to markdown in the vault, agent uses Read/Glob/Grep
- **MCP Knowledge Server** — local MCP server that indexes the corpus and serves semantic search
- **Embed PDFs directly** — have the agent read PDFs via the Read tool
- **Enrich LoreMaster instead** — fold Planescape expertise into the existing LoreMaster agent

## Decision Outcome

Chosen: **Local markdown corpus, agent-driven reads**. Build a local markdown corpus from four sources, stored in the Leviathan vault under `Resources/Planescape/`. The PlanarSage agent reads local files first, then queries online sources for gaps. No MCP server or vector database — plain files the agent reads with standard tools.

### Sources

### 1. Planewalker.com Archive (complete)

Already serialized. 50 markdown files in `Resources/Planewalker.com/` covering the Rrakkma githyanki faction series, encyclopedia entries, adventure hooks, forum lore threads, and planar reference articles. Verbatim community content, freely shared.

### 2. archive.org OCR Texts (not started)

The Internet Archive hosts the complete 2e Planescape catalog with Tesseract OCR plain-text exports. Quality is ~95% but noisy — broken hyphenation, garbled sidebars, misread decorative typography.

**Pipeline:**

```
archive.org TXT download
    → cleanup script (fix hyphenation, strip OCR artifacts, normalize whitespace)
    → split by chapter headings
    → write to Resources/Planescape/Lore/{BookSlug}/{Chapter}.md
```

**Priority titles** (by campaign relevance):

| Title                        | Slug                   | Priority |
| ---------------------------- | ---------------------- | -------- |
| Planescape Campaign Setting  | `campaign-setting`     | 1        |
| In the Cage: Guide to Sigil  | `in-the-cage`          | 1        |
| Guide to the Astral Plane    | `astral-guide`         | 1        |
| Hellbound: The Blood War     | `hellbound`            | 1        |
| The Factol's Manifesto       | `factols-manifesto`    | 2        |
| Planes of Chaos              | `planes-of-chaos`      | 2        |
| Planes of Law                | `planes-of-law`        | 2        |
| Planes of Conflict           | `planes-of-conflict`   | 2        |
| The Planewalker's Handbook   | `planewalkers-handbook` | 2       |
| Uncaged: Faces of Sigil      | `uncaged`              | 3        |
| Faces of Evil: The Fiends    | `faces-of-evil`        | 3        |
| On Hallowed Ground           | `on-hallowed-ground`   | 3        |
| The Inner Planes             | `inner-planes`         | 3        |
| Guide to the Ethereal Plane  | `ethereal-guide`       | 3        |

**Cleanup script requirements:**
- Fix broken hyphenation at line boundaries (`war-\nrior` → `warrior`)
- Strip page numbers, headers, footers
- Normalize Unicode artifacts from OCR
- Preserve italic/bold markers where detectable
- Split on `## ` headings or detectable chapter boundaries
- Output one markdown file per chapter

### 3. ttrpg-convert-cli 5e Output (not started)

The `ebullient/ttrpg-convert-cli` tool converts 5etools JSON into Obsidian-flavored markdown. Covers the three 2023 5e Planescape releases:

| Source | 5etools Code |
| ------ | ------------ |
| Sigil and the Outlands | SatO |
| Morte's Planar Parade  | MPP  |
| Turn of Fortune's Wheel | ToFW |

**Pipeline:**

```
5etools JSON (user-supplied, from owned content)
    → ttrpg-convert-cli --output obsidian
    → write to Resources/Planescape/5e/
```

Output is clean, linked, template-driven. No post-processing needed.

### 4. Online Sources (live queries, no serialization)

The PlanarSage agent queries these sources at runtime when the local archive lacks coverage:

| Source                    | URL                                | Method       |
| ------------------------- | ---------------------------------- | ------------ |
| mimir.net                 | https://mimir.net                  | WebSearch + WebFetch |
| Forgotten Realms Wiki     | https://forgottenrealms.fandom.com | WebSearch + WebFetch |
| Planescape Wiki (Fandom)  | https://planescape.fandom.com      | WebSearch + WebFetch |
| planewalker.com           | https://planewalker.com            | WebSearch + WebFetch |

**Future option:** Bulk scrape mimir.net and/or export planescape.fandom.com via MediaWiki Special:Export for offline access. Not needed immediately — the agent can query live. Revisit if latency or availability becomes a problem.

## Directory Structure

```
Resources/
    Planewalker.com/           # Community articles (complete)
        Planewalker Archive.md # Index
        *.md                   # Individual articles
    Planescape/
        Lore/                  # OCR sourcebook text (future)
            campaign-setting/
            in-the-cage/
            astral-guide/
            ...
        5e/                    # ttrpg-convert-cli output (future)
            SatO/
            MPP/
            ToFW/
        *.png                  # Plane maps (existing)
```

## Alternatives Considered

### MCP Knowledge Server

A local MCP server that indexes the corpus and serves semantic search results. Rejected because:
- Adds infrastructure complexity (server process, embedding model, vector store)
- The corpus is small enough (~30 books, each splitting to ~10-20 chapters) that file reads are fast
- Claude Code's Glob and Grep tools already handle keyword search across hundreds of files
- Can revisit if the corpus grows beyond what file search handles comfortably

### Embed PDFs Directly

Have the agent read PDFs via the Read tool. Rejected because:
- PDFs are large (10-50 MB each with scanned images)
- Read tool has a 20-page limit per request
- OCR quality varies — pre-cleaned text is more reliable
- PDFs cannot be committed to the repo

### Enrich LoreMaster Instead

Fold Planescape expertise into the existing LoreMaster agent. Rejected because:
- LoreMaster's role is vault integrity (auditing, linking, consistency)
- PlanarSage's role is subject matter expertise (answering questions, suggesting content)
- Mixing both makes the agent prompt too large and the dispatch trigger ambiguous
- They collaborate naturally: PlanarSage provides lore, LoreMaster creates the Compendium entry

## Consequences

- The PlanarSage agent works immediately with the Planewalker archive and online sources
- The OCR pipeline and 5e conversion are independent tasks that can be done incrementally
- Each source added to `Resources/Planescape/` automatically becomes available to the agent
- The archive.org cleanup script is the main engineering work — estimated at a few hours of scripting
- No runtime dependencies beyond standard Claude Code tools (Read, Glob, Grep, WebSearch, WebFetch)
