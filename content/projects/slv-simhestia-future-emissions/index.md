---
title: "SimHestia: Projected CO₂ Emissions from Future Land Use Change — Salt Lake Valley"
date: 2018-11-01
summary: "Forward projection of building-sector fossil fuel CO₂ emissions under two 2040 growth scenarios for the Salt Lake Valley, translating EnvisionTomorrow+ regional planning data into parcel-scale building stock changes and reaggregating to the Hestia atmospheric modeling grid for direct comparison with the 2010/2011 baseline inventory."
domain:
  - "Urban Ecology"
  - "Urban Planning"
region: "Wasatch Front, Utah, USA"
ecosystem: "Urbanized intermountain basin; rapidly suburbanizing valley floor, Wasatch Front"
methods:
  - "ET+ (EnvisionTomorrow+) Development Type → BuildingType disaggregation for trend and compact 2040 growth scenarios"
  - "Building type crosswalk: ET+ regional planning typology → Hestia energy modeling building types"
  - "Parcel-scale building stock allocation via lot-size weighting (four-state accounting: 2010 baseline, demolition/redevelopment, new construction, 2040 total)"
  - "Grid-cell reaggregation to 0.002° × 0.002° (~200 m) Hestia atmospheric modeling grid"
  - "Building energy use and FFCO₂ modeling by building type and vintage (Mendoza et al.), driven by 2040 future climate scenarios"
  - "WFRC travel demand model outputs for on-road emissions projection"
sector: "Academic"
era: "UU-GCSC"
featureimage: "images/projects/slv-simhestia-future-emissions/feature.png"
publications:
  - title: "CO2 and Carbon Emissions from Cities: Linkages to Air Quality, Socioeconomic Activity, and Stakeholders in the Salt Lake City Urban Area"
    doi: "10.1175/BAMS-D-17-0037.1"
  - title: "Urban high-resolution fossil fuel CO₂ emissions quantification and exploration of emission drivers for potential policy applications"
    doi: "10.1007/s11252-016-0553-1"
roles:
  - "Co-author (5th of 18) on Lin et al. 2018; Co-Investigator on NOAA grant NA14OAR4310178"
  - "ET+ Development Type → BuildingType disaggregation"
  - "Building type crosswalk development (ET+ planning typology → Hestia energy modeling typology)"
  - "Parcel-scale building stock allocation with explicit 2010-to-2040 delta accounting"
  - "Grid-cell reaggregation to Hestia atmospheric modeling grid"
  - "First author, Maps on the Hill 2019 poster (with Mendoza and Lin)"
---

## Overview

SimHestia extended the Hestia SLCo fossil fuel CO₂ inventory (Patarasuk et al. 2016) into projected 2040 conditions, asking what building-sector emissions would look like if Salt Lake Valley grew according to its own adopted regional plans. Where Hestia SLCo had established a high-resolution, sector-disaggregated baseline for approximately 2010/2011 by building up from actual parcel, utility, and traffic data, SimHestia performed the inverse operation: taking the region's future land use and transportation scenarios and translating them back into the same building-type and grid-cell framework, so that projected 2040 emissions could be placed alongside the baseline in direct, cell-by-cell comparison.

The future land use inputs came from EnvisionTomorrow+ (ET+), the regional scenario planning tool used by the Wasatch Front Regional Council (WFRC) to develop inputs for its Regional Transportation Plan. This was not a hypothetical exercise — ET+'s development quantities were governed by Governor's Office of Planning and Budget population control totals and constrained by municipal General Plans, making the projections the region's actual adopted planning parameters. Two scenarios were modeled: a "trend" (business-as-usual) scenario reflecting likely development patterns under current market and policy conditions, and a "compact" growth scenario concentrating development into designated centers. On-road emissions for 2040 were modeled in parallel using WFRC travel demand model outputs.

The project was funded by NOAA Climate Program Office grants NA14OAR4310178 and NA17OAR4310084 (PI: John Lin, UU Atmospheric Sciences) and NSF grant EF-1137336. Martin was a Co-Investigator on the NOAA grant and, with Daniel Mendoza, one of the two primary execution leads. Primary outputs were a 3D visualization appearing as Figure 8 in Lin et al. 2018 (*Bulletin of the American Meteorological Society*) and a 2019 poster presented to the Utah State Legislature at Maps on the Hill.

## Region & Ecosystem

The study area is the Salt Lake Valley and the broader Wasatch Front — the urbanized corridor stretching from Ogden through Salt Lake City to Provo along the eastern edge of the Great Basin. At the time of the analytical work, the region housed approximately 1.1 million people in Salt Lake County alone and was one of the fastest-growing metro areas in the United States. The topographically enclosed airshed — bounded by the Wasatch Range to the east, the Oquirrh Mountains to the west, and the Great Salt Lake to the northwest — traps wintertime temperature inversions that concentrate ground-level emissions into severe PM₂.₅ episodes, giving the question of how growth form affects emissions direct public health relevance beyond climate policy.

## Methods

**The translation problem.** The core analytical challenge was that ET+'s output format and building typology were designed for regional planning purposes, not atmospheric emissions modeling. ET+ described future development not as parcel-level records but as aspatial pro-forma quantities — combinations of building types with specified floor area ratios and density targets — aggregated into "Development Types" (linear mixtures of BuildingTypes) and assigned to spatial planning units (census blocks, synthetic planning units, TAZs). These had to be converted into the same building-type and spatial framework used by Hestia's energy modeling before any emissions projection was possible.

**Step 1: Development Type → BuildingType disaggregation.** Martin disaggregated ET+'s planning-unit-level Development Type quantities into their constituent building types — a necessary precursor to applying Mendoza's per-building-type energy use models.

**Step 2: Building type crosswalk.** ET+'s building typology was developed for SLCo regional planning and did not map directly onto the building types used for Hestia energy modeling. Martin developed the crosswalk between the two typologies.

**Step 3: Parcel-scale allocation with four-state building stock accounting.** Within each TAZ and building type, Martin allocated the ET+ development quantities across individual parcels using lot-size weighting. The allocation was structured as explicit four-state accounting: 2010 baseline stock, demolition/redevelopment, new construction, and 2040 total. The explicit tracking of the baseline-to-2040 delta — rather than just the 2040 endpoint — was the step that made coherent scenario comparisons possible and grounded the projection in the actual starting conditions of each parcel. Lot-size weighting was the appropriate disaggregation basis given the subsequent reaggregation to 200 m grid cells, at which resolution sub-parcel precision would be spurious.

**Step 4: Grid-cell reaggregation.** Parcel-level building stock quantities were intersected with the 0.002° × 0.002° atmospheric modeling grid used for the Hestia SLCo baseline and reaggregated per Hestia building type. This produced a change layer, in the same spatial and typological units as the Hestia baseline, that could be directly combined with the 2010/2011 inventory and compared against atmospheric transport model outputs.

**Building energy and emissions modeling.** With parcel-scale 2040 building stock quantities in hand in Hestia building types, Daniel Mendoza applied the same building energy modeling framework used for the baseline — driven by hourly weather data representing 2040 future climate conditions — to produce grid-cell-level FFCO₂ projections for both growth scenarios.

**Induced emissions.** A parallel thread, developed with a collaborator in the UU Mechanical Engineering department, worked toward disaggregating electrical consumption to the building scale in order to model induced emissions (CO₂ attributable to grid electricity consumption) alongside Hestia's direct onsite combustion emissions. This distinction has significant local policy value — Utah's electricity generation mix and grid topology mean that induced emissions from buildings have a different spatial signature than direct combustion — but this thread did not produce publishable outputs within the project timeline.

## Outputs

- **Lin et al. 2018, Fig. 8** (*Bulletin of the American Meteorological Society*, Vol. 99(11); DOI: 10.1175/BAMS-D-17-0037.1): A 3D visualization of 2012 baseline annual CO₂ emissions from combined residential and commercial building stocks across the Salt Lake Valley (gray bars, from Hestia SLCo) and the projected 2012–2040 incremental increase under the Wasatch Front Regional Council's business-as-usual growth scenario (color bars, from SimHestia), looking northeast across the valley. Bar heights represent kg CO₂/yr per grid cell. The compact growth scenario comparison, though underway at the time of publication, was described in the paper as a "next step" and does not appear in the published figure.
- **Maps on the Hill 2019 poster** — "People, Buildings, and Air" (Buchert, Mendoza, Lin; first author: Martin Buchert): presented to the Utah State Legislature at Maps on the Hill, the annual research-to-legislature event hosted by Utah universities. The poster advanced beyond the published figure by presenting the scenario comparison: panels include 2011 baseline total emissions (residential + commercial), residential-only emissions, per-capita emissions on a log scale, building stock distribution by type under both growth scenarios, and employment/residential center-of-gravity shifts under trend vs. compact growth.

## My Role

My core contribution was solving the spatial and typological translation problems that made the forward projection possible — the analytical steps connecting ET+'s planning abstractions to the Hestia modeling framework. As a Co-Investigator on the NOAA grant and one of two primary execution leads (alongside Daniel Mendoza), I was responsible for the GIS and scenario translation pipeline from ET+ inputs to grid-cell building stock quantities.

The four sequential steps — disaggregating Development Types to BuildingTypes, developing the typology crosswalk, allocating parcel-scale building stock with explicit delta accounting, and reaggregating to the Hestia grid — are straightforward to describe but each required working across two institutional vocabularies (regional planning and atmospheric emissions science) that do not naturally speak to each other. The delta accounting in particular — tracking the full four-state transition from 2010 baseline through demolition, new construction, and 2040 total, parcel by parcel — was not technically complex but was analytically essential: without it, the 2040 projection floats free of the baseline and cannot be placed in the same cell-by-cell comparison framework that makes the SimHestia results scientifically useful rather than merely illustrative.

I was also first author on the Maps on the Hill 2019 poster, which translated the SimHestia results for a legislative audience. My listed affiliation on that poster is the Department of City & Metropolitan Planning (adjunct faculty), reflecting my institutional position at the time of the 2019 presentation; the underlying analytical work was conducted during my full-time GCSC employment, which ended in August 2017.
