# AGENTS.md — martinbuchert.com (root)

Read this file at the start of every session before taking any action. Section-level AGENTS.md files cover their own directories; this file covers what is true everywhere.

---

## Stack and Deployment

Hugo static site (v0.141.0 minimum), Blowfish theme as a Git submodule, deployed to GitHub Pages via GitHub Actions on every push to main. Repository: archimedian/portfolio. Custom domain: martinbuchert.com — baseURL is set to that domain and GitHub Pages redirects the github.io URL accordingly. HTTPS is enforced. The build output is never committed. SSH is used for all Git operations.

## The Theme

Blowfish is a Tailwind CSS theme. The theme directory is read-only — never modify it directly. Hugo's file lookup order means any file placed at the project root automatically shadows its theme equivalent. This is the correct and only customization pattern.

Blowfish's configuration is split across multiple files in `config/_default/` — not a single config file. When looking for a configuration setting, check the appropriate file in that directory. The `markup.toml` file in that directory is required and must always be present.

## What the Theme Handles Without Custom Work

The homepage profile layout, card-based list views, thumbnail display, dark/light mode, color schemes, navigation, responsive layout, SEO, and sitemap. Before writing any template or CSS override, verify the behavior isn't already controllable via `params.toml`.

## What Requires Custom Work

Surfacing project metadata fields (`region`, `ecosystem`, `methods`, `sector`) in list card views. This override exists at `layouts/partials/article-link/card.html` at the project root. It renders the metadata block only when at least one of those fields is present in front matter, so non-project cards are unaffected. If the Blowfish base card template changes after a submodule update, diff it against the override and reconcile.

## Content Is Page Bundles

Projects are page bundles — a folder with `index.md` and collocated assets. This is required by the Blowfish thumbnail system: images named `feature.*` in a bundle folder are automatically used as card thumbnails. Publications and simple pages use flat Markdown files. Do not reorganize this without understanding the thumbnail implications.

## Configuration Location

All site configuration lives in `config/_default/`. There is no root-level `hugo.toml`. When searching for a configuration value, look there first. `params.toml` controls most theme behavior. `languages.en.toml` controls author metadata and social links. `menus.en.toml` controls navigation.

## Style Customization

Color scheme: `forest` (set in `params.toml`). Color schemes are selected by name in `params.toml` or defined as a CSS file in `assets/css/schemes/`. Font overrides and minor style additions go in `assets/css/custom.css` — this file is loaded automatically after theme styles, no build step required. Extending Tailwind utility classes requires the Tailwind CLI; this is out of scope for this site.

## Contact

LinkedIn URL only. No form, no published email address. Deliberate decision.

## Constraints That Apply Everywhere

No server-side logic. Every solution must work without a backend. If a feature requires server processing, flag it rather than working around it. Git commits are descriptive and atomic. AGENTS.md files are updated in the same commit as the decision they describe.

## How to Search This Codebase

Configuration changes: look in `config/_default/`. Style changes that don't require new Tailwind classes: look in `assets/css/custom.css`. Color scheme changes: look in `assets/css/schemes/`. Template or layout overrides: look in `layouts/` at the project root — these shadow theme templates. Static files (images not in page bundles, PDFs): look in `static/`. When something seems absent from the theme, check `params.toml` before concluding a template override is needed.

## What to Flag

Requests that require server-side logic. Any modification to the theme submodule directly. Front matter schema changes — these affect every existing content file in a section and require explicit confirmation. Broken DOI or PDF links — flag for the site owner, do not silently remove. Any Blowfish submodule update — check whether the card partial override needs reconciliation.

## Portfolio Content Development System

Portfolio content is developed through a structured system of Work Effort (WE) records — one per project — managed outside the Hugo repository. This section documents the architecture so Claude Code sessions can orient without fetching the full discovery history.

**Do not generate, edit, or draft portfolio content in Claude Code sessions.** Content development (discovery, classification, drafting, review) happens in the Claude web interface. Claude Code sessions handle file creation, repo packaging, and Hugo build validation only — receiving finished, approved content.

### Asset Architecture

**Layer 1 — Session Bootstrap (Google Drive, fetched every session in the web interface)**

File: `session-log.md`
Contains: current session number, active WE, open decisions, flags from last session. Under 500 words always. This is the only file fetched at session open. Its Google Drive ID is recorded in userMemories.

**Layer 2 — Working Reference (Claude.ai project files, loaded on demand)**

- `we-inventory.md` — full WE table: UID, slug, short title, domain codes, tier, status. Load when doing triage or status review.
- `taxonomy-and-conventions.md` — domain code definitions, tier definitions, output tag set, era shorthand system, WE file template, discovery protocol, voice and tone guidelines. Load when authoring or reviewing content conventions.
- `publications.md` — all peer-reviewed articles, reports, conference presentations, invited talks, and grants with WE cross-references. Load when building or verifying WE blocks involving publications.

**Layer 3 — Per-WE Discovery Files (Claude.ai project files, loaded per WE)**

One file per DISCOVERY-COMPLETE WE, named `weNNN-slug.md` (e.g., `we019-sacog-suburbs.md`). Contains the confirmed discovery record for that WE: tier, domain codes, artifact inventory, role description (Led / Contributed to / Did not do), key findings, key numbers, open questions, downstream connections. Load one or two at a time during drafting. Never load all of them.

**Layer 4 — Source Documents (Claude.ai project files)**

PDFs, reports, and decks attached to the project. Load during discovery for the relevant WE; leave alone otherwise.

### What Claude Code Sessions Do

When Martin delivers finished, approved `index.md` content for a project page:

1. Create the page bundle directory at `content/projects/<slug>/`
2. Place `index.md` in that directory
3. Confirm feature image is present at `assets/images/projects/<slug>/feature.<ext>`
4. Run `hugo --buildDrafts` to confirm the build is clean
5. Commit with a descriptive message referencing the WE UID and slug

Do not modify front matter schema, domain taxonomy, or content without explicit instruction from Martin. Front matter schema changes affect every file in the section.

### WE Status Values

| Status | Meaning |
| --- | --- |
| `DISCOVERY-COMPLETE` | Discovery block confirmed; ready for drafting |
| `DRAFT-T1-COMPLETE` | T1 page drafted and approved |
| `DRAFT-T1-INCOMPLETE` | T1 page drafted but needs source materials, feature image, or revision |
| `DRAFT-T2-COMPLETE` | T2 page drafted and approved |
| `DRAFT-T2-INCOMPLETE` | T2 page drafted but needs source materials, feature image, or revision |
| `NOT-STARTED` | Not yet in discovery |
| `EXCLUDED` | Deliberately excluded from portfolio |

## End-of-Session Maintenance

Before ending any session, review whether any decision made during that session is undocumented. Update the relevant AGENTS.md in the same final commit. If a new section or subsystem was created, ensure it has an AGENTS.md if its logic isn't fully covered by this file.
