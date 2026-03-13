# AGENTS.md — content/publications/

Read this after the root AGENTS.md. This file covers decisions specific to the publications section.

---

## Structure

Publications use flat Markdown files, not page bundles. There are no single-page views — the list template is the only rendered output. An override of the list template renders entries as a scannable bibliography rather than the default card layout.

## Front Matter Schema

Required fields: `title`, `year`, `journal`, `doi`. Optional fields:
- `pdf` — root-relative path to a file in `static/`, e.g. `/pdf/buchert-2024.pdf`; leave blank if unavailable.
- `alturl` — override link for entries whose DOI is dead or unregistered. When present, the title and inline label link to this URL instead of `https://doi.org/<doi>`. The `doi` field should still be populated for citation integrity. Example: `alturl: "https://digitalcommons.lmu.edu/cate/vol9/iss1/5/"`.

Do not rename or add fields without explicit confirmation — changes require updating every file in this section.

## List Template Override

The list template override lives at `layouts/publications/list.html` at the project root. It renders a bibliography-style list (no cards, no links to single pages), sorted by `year` front matter descending. Each entry shows: title linked to the primary URL, journal, year, DOI/Link label, and PDF link when present. The primary link resolves to `alturl` if set, otherwise to `https://doi.org/<doi>`.

## No Single Pages

Single-page generation for publications is intentionally disabled or unused. Publications do not have detail pages. All content relevant to a publication is in its front matter. Do not add Markdown body content expecting it to be rendered.

## DOI and PDF Links

DOI values are stored as bare identifiers (e.g. `10.xxxx/xxxxx`), not full URLs. The list template is responsible for constructing the full DOI URL. If a DOI or PDF path appears broken, flag it for the site owner — do not silently remove it.

## Adding a New Publication

Create a flat `.md` file in this directory with all front matter fields populated. Filename convention: `author-year-slug.md` (e.g. `buchert-2024-conservation-planning.md`). If a PDF is available, place it in `static/pdf/` and set the `pdf` field to the root-relative path.
