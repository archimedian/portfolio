# Portfolio Project Pages — Build Checklist
**For use in interactive Claude Code sessions.**
Read `AGENTS.md` and `content/projects/AGENTS.md` at the start of every session before taking any action.

---

## Session Protocol

At the start of every session: read `AGENTS.md` and `content/projects/AGENTS.md` before taking any action.

At the end of every session, before closing:
1. Mark completed checklist items with `[x]`
2. Add any decisions, deviations, or unresolved TODOs as an indented note directly below the relevant task
3. Commit the updated todo list in the same commit as the work it describes — not as a separate commit

If a project was partially completed, note which steps are done and what remains before the next session picks it up.

---

## How This Document Works

Each project task below follows the same structure:

1. **Context handoff** — Fill this in before asking Claude Code to work on the project. The richer the notes, the less Claude Code has to guess.
2. **Checklist** — Steps Claude Code executes, in order, within a single session.

When Claude Code cannot fill in a field or section confidently, it drafts a best-effort value and marks it `# TODO: [reason]`. Do not leave any field entirely empty.

---

## Front Matter Schema (all projects)

Every `index.md` must include these fields. Do not rename or add fields without updating this document and every existing file.

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
era: ""                   # Employer/affiliation shorthand from CSV (MLG, UU-GCSC, Hippodameian, etc.)
publications:             # List of associated peer-reviewed works; omit section if none
  - title: ""
    doi: ""
roles:                    # Your role(s) on the project
  - ""
```

The `domain` field drives grouping on the Projects listing page. The card partial override already surfaces `region`, `ecosystem`, `methods`, and `sector`. `domain`, `era`, `publications`, and `roles` will need to be added to the card partial — see the **Site-level tasks** section at the end of this document.

---

## Curated Project Set

Projects are drawn from the work inventory CSV using these criteria: IsConSci=1, HasPeerRevPub=1, HasReport=1+HasFigures=1, or manual inclusion. They are organized below by domain. Within each domain, order is newest-first.

---

## Domain: Conservation Science

### [~] GY Lidar Project
**Era:** MLG | **Date:** Aug 2024 | **Flags:** ConSci, Report+Figs

**Context handoff (fill in before starting):**
```
Project description: National airborne LiDAR + RGB orthoimagery survey (~16,000 km²), GLSC client, UN FAO funded.
Key findings/outputs: DTM/DSM, orthoimagery mosaic, transportation/hydrography layers, 3D building models, accuracy assessment, reports.
Methods used (be specific): LiDAR acquisition, RGB orthoimagery, GCP campaign, point cloud classification (LAStools/lidR), DTM/DSM generation, orthoimage mosaicking, feature extraction/digitizing, accuracy assessment, 3D building models, QC workflow.
Region/ecosystem: Guyana, South America — coastal lowlands through interior tropical forest.
Associated publication(s) and DOI(s): None.
Your specific roles: BD lead; report author; remote survey manager; QC workflow designer; subcontractor evaluator; primary GLSC/FAO liaison; GIS trainer.
Feature image filename: # TODO: select from available project graphics
Any materials Claude Code can read (report path, figures path): Report proprietary. Figures: provide path before next session.
```

**Checklist:**
- [x] Create bundle directory `content/projects/gy-lidar-survey/`
- [x] Write `index.md` with all front matter fields populated; draft body content (Overview, Region & Ecosystem, Methods, Outputs, My Role sections)
- [ ] Place feature image as `feature.jpg` (or `.png`/`.webp`) in bundle directory
- [ ] Verify card renders correctly with `hugo server`

---

### [ ] Audubon Abert Lake Analysis
**Era:** Hippodameian | **Date:** May 2020 | **Flags:** ConSci, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used (be specific):
Region/ecosystem:
Associated publication(s) and DOI(s):
Your specific roles:
Feature image filename:
Any materials Claude Code can read (report path, figures path):
```

**Checklist:**
- [ ] Create bundle directory `content/projects/audubon-abert-lake/`
- [ ] Write `index.md` with all front matter populated; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Bird NDVI Paper
**Era:** Hippodameian | **Date:** Jun 2020 | **Flags:** ConSci, PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used (be specific):
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/bird-ndvi/`
- [ ] Write `index.md`; populate `publications` front matter block with DOI; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] LiDAR and Riparian Vegetation Structure
**Era:** UU-GCSC | **Date:** Apr 2020 | **Flags:** ConSci, PeerPub

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used (be specific):
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/lidar-riparian-veg/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] KCMO Habitat Connectivity
**Era:** UU-MRC | **Date:** Sep 2014 | **Flags:** ConSci, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used (be specific):
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/kcmo-habitat-connectivity/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Jordan River Open Space Inventory
**Era:** Hippodameian | **Date:** Feb 2016 | **Flags:** ConSci

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used (be specific):
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/jordan-river-open-space/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Russ Norvell Pelican Telemetry
**Era:** Hippodameian | **Date:** Jul 2018 | **Flags:** ConSci

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used (be specific):
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/pelican-telemetry/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Masters Thesis
**Era:** UH Mānoa | **Date:** Aug 2007 | **Flags:** ConSci, Report+Figs

**Context handoff (fill in before starting):**
```
Thesis title:
Abstract or summary:
Methods used (be specific):
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/masters-thesis/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Chameleon LUCC Agent-Based Model
**Era:** UH Mānoa | **Date:** May 2004 | **Flags:** ConSci, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/chameleon-lucc-abm/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Mapping Eelgrass Meadows (Towed Underwater Video)
**Era:** BYU | **Date:** Oct 2000 | **Flags:** ConSci

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/eelgrass-mapping/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Field Campaign: Ground Truth Vegetation Sampling
**Era:** USU | **Date:** Jun 2006 | **Flags:** ConSci

**Context handoff (fill in before starting):**
```
Project description / study area:
Methods used:
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/usu-veg-field-campaign/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Critical Evaluation of OR Fire Hazard Mapping
**Era:** Hippodameian | **Date:** Mar 2025 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client/audience:
Key findings/outputs:
Methods used:
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/or-fire-hazard-mapping/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

## Domain: Urban Ecology

### [ ] Hydrology from Future Land Use Change
**Era:** UU-GCSC | **Date:** Aug 2019 | **Flags:** PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/hydrology-land-use-change/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Modeling UTA Transit Emissions
**Era:** UU-GCSC | **Date:** May 2019 | **Flags:** PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/uta-transit-emissions/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] CO2 Emissions from Future Land Use Change
**Era:** UU-GCSC | **Date:** May 2018 | **Flags:** PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/co2-land-use-change/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Urban "Blue Spaces" Accessibility
**Era:** UU-GCSC | **Date:** Dec 2016 | **Flags:** PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/urban-blue-spaces/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Water-Related Urban Typology
**Era:** UU-GCSC | **Date:** Sep 2016 | **Flags:** PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/water-urban-typology/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Hestia SLC 2010
**Era:** UU-GCSC | **Date:** Mar 2016 | **Flags:** PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/hestia-slc-2010/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] LiDAR vs. Imagery as Predictors of Household Water Use
**Era:** UU-GCSC | **Date:** Feb 2015 | **Flags:** PeerPub

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Journal and DOI:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/lidar-imagery-water-use/`
- [ ] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Modeling Views of Urban Riparian Vegetation
**Era:** UU-GCSC | **Date:** Sep 2019 | **Flags:** Report+Figs (manual inclusion candidate)

**Context handoff (fill in before starting):**
```
Project description:
Key findings/outputs:
Methods used:
Region/ecosystem:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/urban-riparian-views/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

## Domain: International Development

### [ ] DRC Boundary DTM Analysis
**Era:** MLG | **Date:** Jul 2021 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client/program context:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/drc-boundary-dtm/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] DRC Treaty Language Analysis
**Era:** MLG | **Date:** Jul 2021 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client/program context:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/drc-treaty-language/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] National Strategic Planning Spatial Analysis
**Era:** MLG | **Date:** Dec 2020 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Country/program context:
Project description:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/national-strategic-planning/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Copperbelt Campaign Planning Analysis
**Era:** MLG | **Date:** Dec 2020 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Country/program context:
Project description:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/copperbelt-campaign-planning/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

## Domain: Urban Planning

### [ ] SACOG Employment Near Rail Transit
**Era:** UU-MRC | **Date:** Sep 2014 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/sacog-employment-rail/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] SACOG CECI
**Era:** UU-MRC | **Date:** Aug 2014 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description (expand CECI acronym if possible):
Client:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/sacog-ceci/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Provo-Orem BRT Environmental Assessment
**Era:** Lochner | **Date:** Apr 2011 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client/agency:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/provo-orem-brt-ea/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Bluff Street Environmental Assessment
**Era:** Lochner | **Date:** Jul 2012 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client/agency:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/bluff-st-ea/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Cottonwood Street Environmental Assessment
**Era:** Lochner | **Date:** May 2012 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client/agency:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/cottonwood-st-ea/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

## Domain: Economic Development

### [ ] Puget Sound Market — Net Demand Analysis
**Era:** Patagon | **Date:** Sep 2018 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/puget-sound-net-demand/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

## Domain: Real Estate Development

### [ ] Car Wash SLCo Site Analysis
**Era:** Hippodameian | **Date:** Jun 2020 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/car-wash-slco-site/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Car Wash Markets Cluster Analysis
**Era:** Hippodameian | **Date:** Mar 2020 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/car-wash-markets-cluster/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

### [ ] Running Shoe Store Analysis
**Era:** Hippodameian | **Date:** Aug 2019 | **Flags:** Report+Figs

**Context handoff (fill in before starting):**
```
Project description:
Client:
Key findings/outputs:
Methods used:
Region:
Your specific roles:
Feature image filename:
Any materials Claude Code can read:
```

**Checklist:**
- [ ] Create bundle directory `content/projects/running-shoe-store/`
- [ ] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [ ] Place feature image
- [ ] Verify card renders

---

## Manual Inclusion Candidates

These items from the CSV did not meet the automated criteria but may be worth including. Review and move into the appropriate domain section above if you decide to include them. Delete this section when resolved.

- `Sierra Leone village mapping` (MLG, Jun 2025) — recent, international, no report/figs yet
- `ZM drone imagery positional accuracy assessment` (MLG, Jul 2023) — technical, no report
- `DRC tree artifacts removal` (MLG, Jul 2021) — not complete
- `Sandy City Quail Hollow "ungroomed park" analysis` (Hippodameian, Oct 2019) — figures only
- `modeling mission footprint of drone system` (MLG, Sep 2025) — very recent, complete
- `SLC kids access to parks` (UU-MRC, May 2016) — no figures
- `Gridworks sample data analysis` (Hippodameian, May 2018) — private client
- `Leader.org School:Restaurant assignment` (Hippodameian, Oct 2017) — private client
- `analysis of walking time to transit on UU campus` (UU-GCSC, Feb 2018) — figures only
- `visualizing HH-scale urban water use` (UU-GCSC, Jul 2017) — figures only
- `Sanborn 1950 database creation` (UU-GCSC, May 2017) — no figures

---

## Site-Level Tasks

These structural tasks should be done once, either before or after the project pages are built. They are not project-specific.

### [ ] Extend card partial for new front matter fields

The existing card override at `layouts/partials/article-link/card.html` surfaces `region`, `ecosystem`, `methods`, and `sector`. Add `domain`, `era`, and `roles` display as needed. The `publications` field does not need to appear on cards.

### [x] Implement domain grouping on the Projects listing page

The default Blowfish list view does not group by a custom front matter field. A list template override at `layouts/projects/list.html` is needed to group cards by `domain` in this order:
1. Conservation Science
2. Urban Ecology
3. International Development
4. Urban Planning
5. Economic Development
6. Real Estate Development

Confirm the approach with the site owner before implementing — options include a custom list template, taxonomy (using `domain` as a taxonomy), or JavaScript client-side grouping.

### [x] Remove stub files

Once real project pages exist, delete `content/projects/stub-project-1/` to prevent it appearing in the listing.

### [x] Update `content/projects/_index.md` description

Replace the `TODO` description placeholder with a real section description.

### [x] Update AGENTS.md

After front matter schema is finalized (especially if `domain`, `era`, `publications`, or `roles` are added), update `content/projects/AGENTS.md` to reflect the complete schema. Do this in the same commit as the schema change.