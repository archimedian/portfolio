# AGENTS.md — content/projects/

Read this after the root AGENTS.md. This file covers decisions specific to the projects section.

---

## Structure

Each project is a page bundle: a directory containing `index.md`. Feature images are **not** collocated in the bundle — they live in the global assets pipeline at `assets/images/projects/<slug>/feature.<ext>` and are referenced via the `featureimage` front matter field (see schema below). This is required for Hugo Pipes image optimization to apply.

## Front Matter Schema

Do not rename or add fields without explicit confirmation — changes require updating every file in this section.

```yaml
title: ""
date: YYYY-MM-DD          # Use first day of the month if only month/year known
summary: ""               # One sentence; used in card views
domain:                   # One or more of: Conservation Science | Urban Ecology | International Development | Urban Planning | Economic Development | Real Estate Development
  - ""
region: ""
ecosystem: ""             # Omit or leave blank for non-ecological projects
methods:
  - ""
sector: ""                # e.g. Conservation NGO | Academic | Municipal Government | Private Consulting
era: ""                   # Employer/affiliation shorthand (MLG, UU-GCSC, UU-GLSC, Hippodameian, Lochner, Patagon, UU-MRC, UH Mānoa, BYU, USU)
featureimage: ""          # Path relative to assets/; e.g. "images/projects/<slug>/feature.jpg"
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

Feature images live in the global Hugo assets pipeline, **not** inside the page bundle. The canonical location is:

```
assets/images/projects/<project-slug>/feature.<ext>
```

Reference the image in front matter via the `featureimage` field with a path relative to `assets/`:

```yaml
featureimage: "images/projects/kcmo-habitat-connectivity/feature.jpeg"
```

Blowfish resolves this via `resources.Get`, which applies Hugo Pipes image optimization (resizing) automatically. Supported extensions: `.jpg`, `.jpeg`, `.png`, `.webp`. Do not place feature images inside the bundle directory — they will not be found by the `featureimage` front matter path and the bundle's `.Resources` lookup is no longer used.

## Adding a New Project

1. Create a new directory under `content/projects/` containing only `index.md`.
2. Place the feature image at `assets/images/projects/<slug>/feature.<ext>`.
3. Set `featureimage: "images/projects/<slug>/feature.<ext>"` in the front matter.
4. Populate all front matter fields (no TODOs left for production entries).

## Content Development Pipeline

Project page content is developed in the Claude web interface through a structured discovery and drafting process. Claude Code sessions receive finished, approved `index.md` files only.

**Do not draft, edit, or generate project page content in Claude Code sessions.**

### Receiving a New Project Page

When Martin delivers a finished `index.md`:

1. Verify the slug matches an entry in `we-inventory.md` (Layer 2 project file)
2. Create `content/projects/<slug>/` and place `index.md` inside it
3. Verify feature image exists at `assets/images/projects/<slug>/feature.<ext>` — if absent, flag to Martin before committing
4. Run `hugo --buildDrafts` and confirm clean build
5. Commit: `add project page: <slug> (WENNN)`

### Per-WE Discovery Files

For any project page where you need background context (role, methods, findings, artifact inventory), load the corresponding `weNNN-slug.md` from Claude.ai project files. Do not infer content from the Hugo front matter alone — the discovery file is the authoritative record.

### Front Matter Schema

The schema is defined in this file's "Front Matter Schema" section above. Do not add or rename fields without explicit confirmation from Martin — changes require updating every file in this section.

Feature images live at `assets/images/projects/<slug>/feature.<ext>` — not inside the page bundle. The `featureimage` front matter field references a path relative to `assets/`.

### Domain Values

The `domain` front matter field is a **YAML list** accepting one or more values. Valid values (exactly as written):

- Conservation Science
- Urban Ecology
- Urban Planning
- International Development
- Economic Development
- Real Estate Development

Example for a multi-domain project:

```yaml
domain:
  - Conservation Science
  - Urban Planning
```

Cross-listed projects should list domains in order of primary to secondary. The card partial and any future domain-filtering logic depend on consistent spelling of these values.
