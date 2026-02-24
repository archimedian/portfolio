# AGENTS.md — content/publications/

Read this after the root AGENTS.md. This file covers decisions specific to the publications section.

---

## Structure

Publications use flat Markdown files, not page bundles. There are no single-page views — the list template is the only rendered output. An override of the list template renders entries as a scannable bibliography rather than the default card layout.

## Front Matter Schema

The schema is finalized. Required fields: `title`, `year`, `journal`, `doi`. Optional field: `pdf` (root-relative path to a file in `static/`, e.g. `/pdf/buchert-2024.pdf`; leave blank if unavailable).

Do not rename or add fields without explicit confirmation — changes require updating every file in this section.

## List Template Override

The list template override (when implemented) lives at `layouts/publications/list.html` at the project root. It renders a bibliography-style list without card layout. Until that override exists, Blowfish's default list view is used. This is a known gap, not a missing decision.

## No Single Pages

Single-page generation for publications is intentionally disabled or unused. Publications do not have detail pages. All content relevant to a publication is in its front matter. Do not add Markdown body content expecting it to be rendered.

## DOI and PDF Links

DOI values are stored as bare identifiers (e.g. `10.xxxx/xxxxx`), not full URLs. The list template is responsible for constructing the full DOI URL. If a DOI or PDF path appears broken, flag it for the site owner — do not silently remove it.

## Adding a New Publication

Create a flat `.md` file in this directory with all front matter fields populated. Filename convention: `author-year-slug.md` (e.g. `buchert-2024-conservation-planning.md`). If a PDF is available, place it in `static/pdf/` and set the `pdf` field to the root-relative path.
