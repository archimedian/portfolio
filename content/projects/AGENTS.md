# AGENTS.md — content/projects/

Read this after the root AGENTS.md. This file covers decisions specific to the projects section.

---

## Structure

Each project is a page bundle: a directory containing `index.md` and collocated assets (photographs, feature image). This structure is required — Blowfish's thumbnail system detects images named `feature.*` within the bundle and uses them as card thumbnails automatically. Flat files will not get thumbnails.

## Front Matter Schema

Do not rename or add fields without explicit confirmation — changes require updating every file in this section.

```yaml
title: ""
date: YYYY-MM-DD          # Use first day of the month if only month/year known
summary: ""               # One sentence; used in card views
domain: ""                # One of: Conservation Science | Urban Ecology | International Development | Urban Planning | Economic Development | Real Estate Development
region: ""
ecosystem: ""             # Omit or leave blank for non-ecological projects
methods:
  - ""
sector: ""                # e.g. Conservation NGO | Academic | Municipal Government | Private Consulting
era: ""                   # Employer/affiliation shorthand (MLG, UU-GCSC, Hippodameian, Lochner, Patagon, UU-MRC, UH Mānoa, BYU, USU)
publications:             # List of associated peer-reviewed works; omit section if none
  - title: ""
    doi: ""
roles:                    # Your role(s) on the project
  - ""
```

`summary` is used natively by Blowfish in card views (controlled by `showSummary` in `params.toml`). `region`, `ecosystem`, `methods`, and `sector` are surfaced in card views via the card partial override at `layouts/partials/article-link/card.html`. `domain`, `era`, `publications`, and `roles` are presented in the Markdown body on single project pages — no card partial work is needed for those fields yet. On single project pages, all metadata is presented in the Markdown body.

## Card Partial Override

The override at `layouts/partials/article-link/card.html` (project root) adds `region`, `ecosystem`, `methods`, and `sector` below the summary. The metadata block only renders when at least one field is set, so the override is safe for all card views site-wide. After any Blowfish submodule update, compare the upstream card template against the override.

## Feature Images

Place the cover photograph as `feature.jpg` (or `feature.png`, `feature.webp`) directly inside the project bundle directory alongside `index.md`. The filename must match the `feature.*` glob — Blowfish picks it up automatically without any front matter reference.

## Adding a New Project

Create a new directory under `content/projects/`, add `index.md` with all front matter fields populated (no TODOs left), and add the feature image. Do not create content with placeholder values for production entries; TODOs are for structural stubs only.
