# AGENTS.md — content/projects/

Read this after the root AGENTS.md. This file covers decisions specific to the projects section.

---

## Structure

Each project is a page bundle: a directory containing `index.md` and collocated assets (photographs, feature image). This structure is required — Blowfish's thumbnail system detects images named `feature.*` within the bundle and uses them as card thumbnails automatically. Flat files will not get thumbnails.

## Front Matter Schema

The schema is finalized. Fields: `title`, `date`, `summary`, `region`, `ecosystem`, `methods` (list), `sector`. Do not rename or add fields without explicit confirmation — changes require updating every file in this section.

`summary` is used natively by Blowfish in card views (controlled by `showSummary` in `params.toml`). The remaining metadata fields are surfaced in card views via the card partial override at `layouts/partials/article-link/card.html`. On single project pages, metadata is presented in the Markdown body — no template work is required there.

## Card Partial Override

The override at `layouts/partials/article-link/card.html` (project root) adds `region`, `ecosystem`, `methods`, and `sector` below the summary. The metadata block only renders when at least one field is set, so the override is safe for all card views site-wide. After any Blowfish submodule update, compare the upstream card template against the override.

## Feature Images

Place the cover photograph as `feature.jpg` (or `feature.png`, `feature.webp`) directly inside the project bundle directory alongside `index.md`. The filename must match the `feature.*` glob — Blowfish picks it up automatically without any front matter reference.

## Adding a New Project

Create a new directory under `content/projects/`, add `index.md` with all front matter fields populated (no TODOs left), and add the feature image. Do not create content with placeholder values for production entries; TODOs are for structural stubs only.
