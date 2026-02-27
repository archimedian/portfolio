---
title: "High-Resolution Fossil Fuel CO₂ Emissions Quantification — Salt Lake County (Hestia)"
date: 2016-09-01
summary: "First application of the Hestia bottom-up FFCO₂ framework outside Indianapolis — producing building- and street-segment-scale fossil fuel CO₂ estimates for Salt Lake County across eight sectors at hourly resolution, then using that data product to show that household income, population, building age, and household size explain residential emissions heterogeneity, and that primary versus secondary road type predicts onroad emissions density versus intensity."
domain:
  - "Urban Ecology"
  - "Urban Planning"
region: "Salt Lake County, Utah, USA"
ecosystem: "Urbanized intermountain basin; rapidly suburbanizing valley floor, Wasatch Front"
methods:
  - "Hestia bottom-up FFCO₂ quantification framework (building/street scale, hourly resolution)"
  - "Salt Lake County Assessor parcel data: building type classification (11 commercial + 4 residential types × 2 vintages)"
  - "Non-electric energy-use intensity (NE-EUI) from CBECS, RECS, eQUEST building energy model"
  - "Vulcan national product as county-total scaling anchor (scaled to 2011 via EIA state fuel statistics)"
  - "NEI 2011 onroad emissions by road type and vehicle class; spatially allocated via FHWA road network"
  - "STIRPAT regression on census block group sociodemographic variables"
  - "GIS pipeline: parcel, building, and traffic data processing and spatial disaggregation"
  - "Point source emitter location ground-truthing"
sector: "Academic"
era: "UU-GCSC"
featureimage: "images/projects/hestia-slc-2010/feature.png"
publications:
  - title: "Urban high-resolution fossil fuel CO₂ emissions quantification and exploration of emission drivers for potential policy applications"
    doi: "10.1007/s11252-016-0553-1"
roles:
  - "Co-author (7th of 10)"
  - "Local data acquisition: parcel data (Salt Lake County Assessor), building footprints (Salt Lake City IT, Murray City, South Jordan City), disaggregated traffic counts (Salt Lake City IT, UDOT Traffic Operations Center)"
  - "GIS pipeline processing of local datasets for Hestia production inputs"
  - "Data troubleshooting and local expert liaison for remote ASU team"
  - "Point source emitter location QA/QC (directed Fall 2013 REDEV 6450 graduate students)"
  - "Manuscript contribution: result interpretation, strategic messaging, relevant sections"
---

## Overview

The Hestia project is a building- and street-scale fossil fuel CO₂ (FFCO₂) emissions quantification system developed by Kevin Gurney's group at Arizona State University. Unlike national inventories or coarse top-down spatial proxies, Hestia uses sector-specific bottom-up modeling to estimate fine-grained relative demand among individual buildings and road segments — drawing on building-scale energy models driven by observed hourly weather data, observed traffic patterns, and direct point source records — and uses these relative demand estimates as disaggregation weights to allocate county-level FFCO₂ totals (themselves anchored to real regional fuel consumption statistics) down to the building and street-segment scale with hourly temporal structure. The methodology was first applied to Indianapolis, Indiana, and subsequently extended to Salt Lake County, Utah, as part of a collaboration between the Gurney lab and University of Utah researchers in atmospheric sciences, biology, and urban planning.

This paper presents the Salt Lake County Hestia data product — the first full Hestia implementation outside Indianapolis — covering eight emission sectors (residential buildings, commercial buildings, onroad transportation, non-road, airports, railroad, electricity production, and industrial point sources) at sub-parcel and street-segment spatial resolution. It then uses that data product to investigate two analytical questions with direct policy implications: What demographic and built-environment characteristics drive residential FFCO₂ heterogeneity across census block groups? And what road-network properties determine where onroad emissions are most concentrated?

The principal finding is that high-resolution bottom-up quantification reveals spatial and demographic structure that is completely invisible to zero-dimensional city carbon inventories — structure that could enable targeted intervention at the neighborhood or corridor level rather than aggregate sector targets.

## Region & Ecosystem

Salt Lake County occupies the central portion of Utah's Wasatch Front, a rapidly urbanizing conurbation of approximately 1.1 million people (2010) stretching along the eastern edge of the Great Basin between the Wasatch Mountains and the Great Salt Lake. The county encompasses Salt Lake City and dozens of suburban municipalities across a valley floor that has experienced rapid low-density residential expansion since the 1960s. The region's geography — a topographically enclosed airshed prone to severe wintertime temperature inversions — gives emissions quantification at high spatial resolution direct public health relevance beyond climate policy: ground-level FFCO₂ emitters are co-located with the vehicle exhaust, space-heating combustion products, and industrial emissions that drive PM₂.₅ exceedances during inversion events.

## Methods

**The Hestia framework.** Hestia's core logic is a two-step disaggregation: sector-specific bottom-up models estimate the *relative* spatial and temporal distribution of demand among buildings or road segments, and those relative demand patterns are used as weights to allocate county-level FFCO₂ totals — which are themselves anchored to observed regional fuel consumption data — down to individual spatial units at hourly resolution. This approach differs from both top-down spatial proxies (which smear totals by population density or land use) and direct metering (which is infeasible in practice because individual and business energy consumption records are held by utilities under privacy constraints that make acquisition essentially impossible): the county totals are real, and the within-county spatial and temporal structure reflects modeled sector-specific activity rather than generic proxies. The result is a gridded and vector data product giving FFCO₂ in kg C hour⁻¹ for each building or street segment and each hour of the year.

**Residential and commercial buildings.** Non-point building FFCO₂ covers on-site fossil fuel combustion; emissions associated with electricity consumption are attributed to the electricity generation facilities (point sources), not to buildings. Individual building emissions were estimated using Salt Lake County Assessor parcel data, which were classified into eleven commercial and four residential building types, each further split into pre-1980 and post-1979 vintages, yielding 22 commercial and 8 residential building type categories. Non-electric energy-use intensity (NE-EUI) values for each category were drawn from CBECS, RECS, and eQUEST building energy models, then combined with each parcel's total floor area to produce estimated non-electric energy consumption. Critically, these estimates were not used in absolute form — they served as a relative weighting among buildings within each sector to spatially disaggregate county-level FFCO₂ totals drawn from the Vulcan national product (Gurney et al. 2009), which were in turn scaled from the Vulcan base year (2002) to 2011 using EIA state-level fuel statistics. Parcel data were similarly updated to include buildings constructed through 2011. Building energy modeling was led by Daniel Mendoza (UU Atmospheric Sciences).

**Onroad transportation.** Onroad FFCO₂ was estimated using NEI 2011 emissions by road type and vehicle class, spatially allocated to the FHWA-classified road network. Salt Lake City Transportation Division traffic count data, acquired and processed as part of this project's local data pipeline, informed the road-level vehicle activity disaggregation.

**Local data acquisition and GIS pipeline.** Translating the Hestia framework to Salt Lake County required assembling a suite of local datasets that the remote ASU team could not easily access or interpret without in-market knowledge. I identified, located, and secured permission to use the suite of local datasets the SLCo implementation required: parcel data from the Salt Lake County Assessor's Office; building footprints from Salt Lake City IT, Murray City, and South Jordan City; and disaggregated traffic counts from both Salt Lake City IT and UDOT's Traffic Operations Center. I then performed much of the geospatial processing needed to translate these raw local datasets into Hestia-ready inputs — joining, projecting, cleaning, and spatially disaggregating the parcel, building, and traffic data to match the model's spatial framework. For industrial point sources where source data was ambiguous or confusing to the remote ASU team, QA/QC of emitter locations was carried out by graduate students in my Fall 2013 REDEV 6450 course, working under my direction.

**STIRPAT analysis.** The paper's analytical core is a STIRPAT (Stochastic Impacts by Regression on Population, Affluence, and Technology) regression estimating elasticities of residential FFCO₂ with respect to census block-group-level population, per capita income, household size, building age, and development density. This analysis was led by lead author Risa Patarasuk.

## Key Findings

**Residential sector.** All sociodemographic variables were statistically significant. Population, per capita income, and building age showed positive relationships with block-group residential FFCO₂; household size showed a negative relationship. The income elasticity exhibits a striking heterogeneity: high-income block groups are approximately twice as sensitive to income variation as low-income block groups, while low-income block groups are roughly four times as sensitive to household size. Development density (compactness) showed little effect in this domain after controlling for the other variables — suggesting that, for residential emissions in this built context, demographic and building-stock characteristics matter more than form.

**Onroad sector.** Primary roads (interstates and arterials) show high emissions *density* (FFCO₂ per kilometer of road) due to high vehicle volumes, but secondary roads show higher emissions *intensity* (FFCO₂ per VMT) — a distinction that matters for intervention strategy. The spatial analysis identifies specific road corridors with the highest onroad emissions concentrations, and the paper notes that alignment of potential transit extensions with high-emission road segments represents an identifiable policy lever for emissions reduction.

**Policy implication.** The central argument of the paper is methodological as much as empirical: the spatial and demographic structure revealed by Hestia's high-resolution approach simply cannot be detected by conventional city-scale carbon inventories, which report aggregate totals without the sub-parcel and street-segment resolution needed to identify which neighborhoods, building types, or corridors should be prioritized for intervention.

## Outputs

- Salt Lake County Hestia FFCO₂ data product: eight sectors, building/street-segment spatial resolution, hourly temporal structure, 2011 base year
- STIRPAT regression models for residential FFCO₂ by census block group, with income-stratified elasticity estimates
- Spatial analysis of onroad emissions density and intensity by road type and corridor
- Published article: *Urban Ecosystems*, 2016, Vol. 19(3): 1013–1039; DOI: 10.1007/s11252-016-0553-1
- Revised and improved Hestia SLC data product (Gurney et al., released 2018/2019 by the Gurney lab at Northern Arizona University): publicly available via NIST at [doi:10.18434/T4/1503340](https://data.nist.gov/od/id/696FD547910012A0E0532457068160E41910) — gridded FFCO₂ at 0.002° resolution, hourly and annual temporal frames, years 2002/2010/2011/2012

## My Role

I served as the urban planning and GIS bridge between Kevin Gurney's ASU lab and the Salt Lake County data ecosystem. The Hestia framework is technically sophisticated but dependent on locally sourced datasets that vary substantially in format, coverage, and quality across cities. My job was to make Salt Lake County's data legible to the remote ASU team and to translate raw local sources into model-ready inputs.

On the data acquisition side, I identified and located the parcel, building attribute, and traffic datasets needed for the SLCo implementation, corresponded with data maintainers at the Salt Lake County Assessor's Office and Salt Lake City Transportation Division to understand data idiosyncrasies, and secured access for the project. I then performed much of the geospatial processing required to convert these raw inputs into Hestia production inputs — spatial joins, projections, attribute cleaning, and disaggregation to the building and street-segment scale. Throughout production, I served as the local ground-truth resource for the ASU team working remotely: when data quality issues arose, I helped develop handling strategies; when point source locations were ambiguous or inconsistent across source databases, QA/QC was conducted by graduate students in my Fall 2013 REDEV 6450 course under my direction. I also contributed to manuscript writing, primarily in sections covering results closest to my contributions — local data, GIS processing, and the policy implications of the spatial analysis.

The building energy modeling was led by Daniel Mendoza; the STIRPAT regression analysis was led by Risa Patarasuk; the Hestia conceptual framework is a pre-existing Gurney lab methodology. My placement at 7th of 10 in the author list reflects the author group's deliberate attribution decision: despite coming ahead of senior UofU participants Lin, Mendoza, and Ehleringer, my position reflects the direct and concrete role I played in producing the local data inputs that made the SLCo implementation possible.
