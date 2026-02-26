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

### [x] GY Lidar Project
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
- [x] Place feature image as `feature.jpg` (or `.png`/`.webp`) in bundle directory
- [x] Verify card renders correctly with `hugo server`

---

### [x] Audubon Abert Lake Analysis
**Era:** Hippodameian | **Date:** May 2020 | **Flags:** ConSci, Report+Figs

**Context handoff (fill in before starting):**
```
Project description: Pro bono remote sensing analysis for Audubon Society's Saline Lakes Program to determine whether artificial wildlife habitat (ponds and canals) was ever constructed as required by the terms of a 1991 Oregon water use permit and 1993 lease agreement at River's End Reservoir (River's End Ranch) near the mouth of the Chewaucan River, Lake County, OR. Analysis was conducted to support potential legal action; Audubon ultimately did not pursue it.
Key findings/outputs: Across three independent lines of evidence — Global Surface Water occurrence/change products (Landsat-derived, 1984–2018), NDVI time series (Robinson et al. 2017 Landsat product), and historical aerial imagery (NAIP/NAPP 4-band, multiple dates) — no evidence of the promised ponds or canals was found. Professional conclusion: the habitat infrastructure required by the permit and lease was never constructed.
Methods used (be specific): Global Surface Water dataset (Pekel et al. 2016, Nature; Landsat-derived, 30 m, 1984–2018) for surface water extent, occurrence frequency, seasonality, and change detection; Robinson et al. (2017) Landsat NDVI time series product for pre/post-reservoir vegetation change analysis; NAIP/NAPP 4-band aerial imagery (1994, 2001, 2009, 2014, 2016) as historical imagery for earthworks inspection and high-resolution NDVI; georeferencing of scanned permit and lease maps against current aerial imagery for spatial overlay analysis; NHDPlus HR for hydrography reference; ArcGIS Pro 2.4.0.
Region/ecosystem: Lake Abert, Lake County, south-central Oregon — hypersaline terminal lake (Great Basin); adjacent semi-arid riparian corridor along lower Chewaucan River.
Associated publication(s) and DOI(s): None. Report only (incomplete draft being finalized as portfolio piece).
Your specific roles: Sole analyst and author. Originated research design in response to question from Marchelle Shoop (National Director, Audubon Saline Lakes Program); proposed methodology; conducted all data collection, processing, and analysis; wrote report. Pro bono consulting work.
Feature image filename: # TODO: select from available project figures (water occurrence map, NDVI change map, or aerial imagery panel)
Any materials Claude Code can read (report path, figures path): # TODO: provide path to report and figures before session
```

**Checklist:**
- [x] Create bundle directory `content/projects/audubon-abert-lake/`
- [x] Write `index.md` with all front matter populated; draft body; mark uncertain values `# TODO:`
- [x] Place feature image
- [x] Verify card renders

---

### [x] Bird NDVI Paper
**Era:** Hippodameian | **Date:** Jun 2020 | **Flags:** ConSci, PeerPub, Report+Figs

**Context handoff (fill in before starting):**
```
Project description: Analysis of 15 years of MAPS bird-banding data (1994–2008) from eight riparian sites across Utah to examine how interannual variation in climate and vegetation affects riparian bird communities at the community and population level. Published in Animal Conservation (2021).
Key findings/outputs: Bird captures and species richness increased in hotter, drier, less-green, and El Niño years, driven largely by an influx of non-riparian species into riparian oases. Population growth rates of ~47% of focal riparian breeding species declined in hotter years, driven by reduced recruitment rather than survival — suggesting warming concentrates bird diversity in riparian corridors while simultaneously undermining demographic performance of the species most dependent on them.
Methods used (be specific): 15-year MAPS bird-banding dataset; PRISM monthly climate data (tmean, ppt, AN81m, ~4 km); Robinson et al. (2017) Landsat-derived 30 m NDVI product (16-day composites, DOY 129 and 157); Multivariate ENSO Index (NOAA); Python scripting to compute mean values of spatial variables within 5-km buffer of each site; ArcGIS Pro 2.4.0 (Buffer, Zonal Statistics); GLMMs with Poisson errors (lme4); PCoA on Bray-Curtis dissimilarity (vegan); CJS and Pradel CMR models (RMark).
Region/ecosystem: Utah, USA — arid Intermountain West; perennial riparian corridors across Utah Mountains (north-central, 1777–1936 m) and Southern Deserts (Colorado Plateau, 1041–1550 m).
Journal and DOI: Animal Conservation, 2021. DOI: 10.1111/acv.12755
Your specific roles: Co-author (3rd of 8). Helped define research design around NDVI and PRISM datasets. Contributed to phenology analysis informing NDVI observation date selection (DOY 129, 157). Performed all NDVI and climate data processing including Python scripting for spatial variable extraction. Assisted in manuscript drafting and reviewer response strategy.
Feature image filename: Figure 1 from paper (overview map of eight banding stations with NAIP aerial imagery insets). # TODO: replace with high-resolution original.
Any materials Claude Code can read: PDF at /Users/admin/Library/CloudStorage/GoogleDrive-martinpbuchert@gmail.com/My Drive/0Admin/Employment/Publications/Neate-Clegg_etal_2021.pdf
```

**Checklist:**
- [x] Create bundle directory `content/projects/bird-ndvi/`
- [x] Write `index.md`; populate `publications` front matter block with DOI; draft body; mark uncertain values `# TODO:`
- [x] Place feature image
- [x] Verify card renders

---

### [x] LiDAR and Riparian Vegetation Structure
**Era:** UU-GCSC | **Date:** Apr 2020 | **Flags:** ConSci, PeerPub

**Context handoff (fill in before starting):**
```
Project description: Analysis of 3D riparian vegetation structure and woody species composition along Red Butte Creek, Utah, using airborne LiDAR paired with ground-based field surveys, to evaluate how a rural-to-urban land use gradient and gaining/losing stream hydrology influence riparian forest canopy structure and community composition.
Key findings/outputs: Urban reaches had higher proportions of introduced species (reaching 100% in lower residential areas) and exceptionally tall trees (>18 m) in older neighborhoods, while natural canyon reaches were dominated by native riparian species. In natural upper-gaining reaches, canopy height was negatively correlated with HAR and was higher on north-facing aspects. Land use transitions — particularly individual landowner decisions — appeared to decouple riparian vegetation structure from stream hydrology in urban reaches.
Methods used (be specific): Airborne LiDAR (OpenTopography, 2013–2014, 8 returns/m², ~7 cm accuracy); LAStools (lasclassify, lasheight, lascanopy) for point cloud classification and DTM/CHM generation; spike-free CHM (Khosravipour et al. 2016); ArcGIS 10.3.1 for 50×50 m and 10×50 m plot delineation along smoothed stream centerline; Riparian Topography Tools (Dilts 2015) for HAR calculation; stream burning for culvert correction; vegetation metrics: cover (%), average canopy height (m), canopy density for five height intervals (<1.5 m, 1.5–5 m, 5–9 m, 9–18 m, >18 m); field woody species surveys via step-point technique along 23 transects (summer 2016); WIS and native status (USDA PLANTS); GLS mixed-effects regression with spatial covariance structures and VarIdent variance structure (R: nlme, gstat, ape, car).
Region/ecosystem: Red Butte Creek, Salt Lake City, Utah — semiarid Intermountain West; montane canyon through urban valley, ~700 m elevation gradient; Great Basin.
Journal and DOI: Ecohydrology, 2020. DOI: 10.1002/eco.2259
Your specific roles: Co-author (2nd of 4). Acquired and processed airborne LiDAR data; designed and implemented plot delineation workflow in ArcGIS; computed DTM, CHM, and all vegetation structure metrics using LAStools; calculated HAR using Riparian Topography Tools; contributed to research design, manuscript drafting, and review.
Feature image filename: feature.jpeg (Figure 1 — study area map with land use transitions, hydrologic domains, and field transect locations).
Any materials Claude Code can read: PDF at /Users/admin/Library/CloudStorage/GoogleDrive-martinpbuchert@gmail.com/My Drive/0Admin/Employment/Publications/Grijseels_etal_2020.pdf
```

**Checklist:**
- [x] Create bundle directory `content/projects/lidar-riparian-veg/`
- [x] Write `index.md`; populate `publications` block; draft body; mark uncertain values `# TODO:`
- [x] Place feature image
- [x] Verify card renders

---

### [x] KCMO Habitat Connectivity
**Era:** UU-MRC | **Date:** Sep 2014 | **Flags:** ConSci, Report+Figs

**Context handoff (fill in before starting):**
```
Project description: Proof-of-concept demonstration of graph-theory-based habitat connectivity modeling for the Mid-America Regional Council (MARC), leveraging their newly delivered Kansas City Natural Resource Inventory II (NRI) — a 2.5m land cover product derived from multispectral imagery and airborne LiDAR. Part of an omnibus ecosystem services contract with the University of Utah Metropolitan Research Center. The study was explicitly scoped as a demonstration, not a conservation or management plan.
Key findings/outputs: Habitat patches and functional connectivity networks modeled for two focal species — Western painted turtle (Chrysemys picta bellii) and Eastern meadowlark (Sturnella magna) — using the Probability of Connectivity (PC) index and patch-removal experiments (dPC) to rank patch and link importance. White-tailed deer was dropped after literature review confirmed it is a habitat generalist not amenable to discrete patch modeling. Turtle analysis compared two contrasting HUC12 watersheds (Longview: urbanizing suburban fringe; Freeman: agricultural, less fragmented); the Longview watershed was bisected into isolated network components by I-470/US-50 and I-49, while Freeman patches formed a single fully-connected network. Meadowlark habitat forms a distinctive ring around the KC conurbation squeezed between intense urbanization and intensive agriculture; connectivity is not the limiting factor for this species — total habitat area is. Report concludes with recommendations for incorporating habitat connectivity into MARC's ongoing regional planning work.
Methods used (be specific): Kansas City NRI II land cover (2.5m, 2012) as primary input; NRI resampled to 10m (turtle) and 20m (meadowlark) for analysis; species-specific habitat reclassification; erode-then-dilate morphological filtering to remove salt-and-pepper artifacts and simplify patch geometry; patch area thresholding (turtle: 0.03–5.9 ha; meadowlark: ≥50 acres); large roadway extraction via erode-then-dilate on impervious surface mask (~4-lane threshold); HUC12 watershed delineation (National Watershed Boundary Dataset) for turtle sub-area analysis; Graphab 1.2 for functional connectivity graph construction and dPC metric computation; Euclidean distance for meadowlark dispersal (literature-supported); least-cost/resistance modeling for turtle; focal species parameterization from primary literature review and expert consultation (Larry Rizzo, Missouri Dept. of Conservation); ArcGIS 10.2 for all spatial processing.
Region/ecosystem: Nine-county Kansas City metro region (Missouri/Kansas) — tallgrass prairie remnants, freshwater wetlands, urban/suburban fringe, agricultural matrix.
Associated publication(s) and DOI(s): None. Report only.
Your specific roles: Sole analyst and author. Designed and executed all methods; conducted species literature review; led expert consultation with Missouri Dept. of Conservation biologist (species selection and habitat requirements); performed all spatial data processing and connectivity modeling; wrote report and recommendations for MARC.
Feature image filename: feature.jpeg (Figure 13 — MARC-region-wide dPC for patches and links, meadowlark model).
Any materials Claude Code can read: Report at # TODO: provide local path before session.
```

**Checklist:**
- [x] Create bundle directory `content/projects/kcmo-habitat-connectivity/`
- [x] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [x] Place feature image
- [x] Verify card renders

---

### [x] Jordan River Open Space Inventory
**Era:** Hippodameian | **Date:** Feb 2016 | **Flags:** ConSci

**Context handoff (fill in before starting):**
```
Project description: Conservation prioritization and gap analysis for the Jordan River Commission identifying open-space-compatible parcels within a 1-mile buffer of the Jordan River centerline in Salt Lake County. Designed to guide future land acquisition and inform permitting decisions along the corridor.
Key findings/outputs: Standardized crosswalk of zoning classifications from all 12 SLCo municipalities within the AOI, enabling uniform classification of parcels by open-space compatibility; reclassification of SLCo Assessor ownership codes into a binary private/public typology; geodatabase of cleaned SLCo parcel features within 1-mile buffer, each coded Y/N on three dimensions: zoned as open space, protected by conservation easement, publicly owned; map series representing parcels by ownership/easement/zoning status, federal flood zone classification, and Utah State water-related land use classification. Adopted by three stakeholder organizations: Jordan River Commission Technical Advisory Committee (general reference), Salt Lake County Open Space Trust (land acquisition guidance), and Utah Division of Forestry Fire and State Lands (informed Jordan River classification decisions in their Comprehensive Management Plan).
Methods used (be specific): 1-mile buffer around Jordan River centerline (NHDPlus v2, USGS); parcel features from UGRC statewide parcel layer; ownership typology from SLCo Assessor data, reclassified to private/public binary; conservation easements from National Conservation Easement Database; water-related land use from UGRC (State of Utah); municipal zoning data obtained directly from 12 SLCo municipal GIS departments; manual review and crosswalk of all 12 zoning schemas to unified open-space-compatible classification; AOI scoped to SLCo parcels only (Davis and Utah County excluded); ArcGIS Desktop 10.3.1.
Region/ecosystem: Jordan River corridor, Salt Lake County, Utah — urban riparian corridor.
Associated publication(s) and DOI(s): None. Report and geodatabase only.
Your specific roles: Research design lead (in collaboration with client); sole GIS analyst; led team of University of Utah Urban Planning graduate students in zoning crosswalk development; primary client liaison (Jordan River Commission Executive Director Laura Hanson). Paid Hippodameian contract.
Client impact: Per email from Laura Hanson (Jordan River Commission Executive Director), April 5, 2016, the JROSI database was in active use by three organizations: (1) Jordan River Commission Technical Advisory Committee — general reference; (2) Salt Lake County Open Space Trust — guiding discussions about future land acquisitions along the river; (3) Utah Division of Forestry Fire and State Lands — informed decision-making on proposed Jordan River classifications in their Comprehensive Management Plan, specifically directing the agency on whether to approve future permit applications for new structures in the river. Quote available for use in page body.
Feature image filename: JROSI-feature.jpeg
Any materials Claude Code can read: # TODO: provide report path if available before session
```

**Checklist:**
- [x] Create bundle directory `content/projects/jordan-river-open-space/`
- [x] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [x] Place feature image
- [x] Verify card renders

---

### [x] Península Valdés Right Whale Sightings
**Era:** UU-GLSC | **Date:** Jul 2017 | **Flags:** ConSci, Manual

**Context handoff (fill in before starting):**
```
Project description: Collaboration with Dr. Victoria Rowntree, Director, Ocean Alliance Right Whale Program, to digitize into GIS the results of annual aerial surveys of Southern right whales (Eubalaena australis) along Península Valdés, Argentina. Surveys covered 1997–2004 (the period before the program transitioned to electronic data collection); positional data were recorded on paper field maps as distance along coastline, with no perpendicular offset, so positional accuracy of sightings is low relative to GPS-based methods.
Key findings/outputs: Strategic plan for data model and digitization workflow; geodatabase with mileposted centerline representing the 5–10 fathom bathymetric contour ("whale road") around Golfo Nuevo, Península Valdés, and Golfo San José, digitized from Argentine nautical charts supplied by Dr. Rowntree; georeferenced scan of historical base-map; digitized 1997 sightings dataset; recruitment of undergraduate GIS technician from student pool and graduate-student volunteer via Society for Conservation GIS listserv; digitization protocol and training tutorial for volunteer technicians.
Methods used (be specific): ArcGIS Desktop 10.5 for all GIS processing; bathymetric contour ("whale road") manually digitized from Argentine nautical charts supplied by Dr. Rowntree; sightings data manually digitized from paper field maps using same nautical chart as base layer; historical base-map georeferenced in ArcGIS.
Region/ecosystem: Península Valdés, Patagonia, Argentina — Golfo Nuevo, Golfo San José, and adjacent coastal waters; critical breeding and nursery habitat for Southern right whales (Eubalaena australis).
Associated publication(s) and DOI(s): None.
Your specific roles: Project lead. Designed GIS data model and digitization workflow; developed geodatabase; manually digitized bathymetric contour centerline and 1997 sightings data; georeferenced historical base-map; recruited and coordinated volunteer GIS technicians; developed digitization protocol and training tutorial.
Feature image filename: feature.png (satellite imagery of Península Valdés showing Golfo Nuevo and Golfo San José).
Any materials Claude Code can read: No report or figures available; only informal email exchanges.
```

**Checklist:**
- [x] Create bundle directory `content/projects/valdes-right-whale/`
- [x] Write `index.md`; draft body; mark uncertain values `# TODO:`
- [x] Place feature image
- [x] Verify card renders

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