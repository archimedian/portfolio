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

## End-of-Session Maintenance

Before ending any session, review whether any decision made during that session is undocumented. Update the relevant AGENTS.md in the same final commit. If a new section or subsystem was created, ensure it has an AGENTS.md if its logic isn't fully covered by this file.
