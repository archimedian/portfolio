---
title: "The Effects of Climate Change and Fluctuations on the Riparian Bird Communities of the Arid Intermountain West"
date: 2020-06-01
summary: "Analysis of 15 years of MAPS bird-banding data from eight Utah riparian sites showing that hotter, drier years concentrate greater bird diversity in riparian corridors while simultaneously depressing population growth rates in the breeding species most dependent on them."
domain: "Conservation Science"
region: "Utah, USA"
ecosystem: "Semi-arid riparian corridors, Intermountain West"
methods:
  - "MAPS bird-banding data (15 years, 8 sites)"
  - "PRISM climate data (temperature, precipitation)"
  - "Landsat NDVI time series (Robinson et al. 2017)"
  - "Multivariate ENSO Index"
  - "GLMMs with Poisson errors"
  - "Principal Coordinate Analysis (Bray-Curtis)"
  - "Capture-mark-recapture models (CJS and Pradel)"
sector: "Academic"
era: "Hippodameian"
publications:
  - title: "The effects of climate change and fluctuations on the riparian bird communities of the arid Intermountain West"
    doi: "10.1111/acv.12755"
roles:
  - "Co-author (3rd of 8)"
  - "Research design input: NDVI and climate dataset selection"
  - "Phenology analysis informing NDVI observation date selection"
  - "All NDVI and climate spatial data processing (Python, ArcGIS Pro)"
  - "Manuscript drafting and reviewer response strategy"
---

## Overview

Published in *Animal Conservation* (2021), this study used 15 years of MAPS (Monitoring Avian Productivity and Survivorship) bird-banding data from eight riparian sites across Utah to examine how interannual variation in climate and vegetation greenness affects riparian bird communities — both at the level of community composition and at the level of individual population demographics.

The central finding captures a tension that has direct conservation implications: in hotter, drier, less-green years, riparian corridors attract *more* birds and greater species richness as the surrounding landscape desiccates and non-riparian species crowd into these oases. Yet those same conditions are associated with declining population growth rates in nearly half of the focal riparian breeding species — driven not by increased mortality but by reduced recruitment. Warming concentrates diversity in riparian corridors while undermining the breeding performance of the species that depend on them most.

## Region & Ecosystem

Eight MAPS banding stations along perennial streams across Utah, representing two physiographic regions. The **Utah Mountains** sites (DUTC, SLC1, RUSH, NEPH) in north-central Utah occupy elevations of 1,777–1,936 m and are cooler, wetter, and greener. The **Southern Deserts** sites (MOAB, MONT, SMOK, STGE) on the Colorado Plateau sit at 1,041–1,550 m and are hotter, drier, and sparser. Both regions lie within the broader arid Intermountain West, where riparian corridors along perennial streams represent critical and scarce concentrations of water, vegetation, and prey for breeding and migratory birds.

## Methods

**Bird banding.** The Utah Division of Wildlife Resources (UDWR) operated MAPS banding stations at eight sites with ≥8 years of data between 1994 and 2008. Each banding day consisted of 6 hours of sampling with a uniform number of mist nets. A total of 31,788 birds of 148 species were captured over 1,247 banding days.

**Climate data.** PRISM monthly temperature (tmean) and precipitation (ppt) data (AN81m, ~4 km resolution) were extracted for 5-km radii around each banding station using ArcGIS Pro 2.4.0 Buffer and Zonal Statistics tools. Annual climate variables were computed over the October–September period preceding each survey season to capture the full water and vegetation phenocycle.

**NDVI.** Landscape greenness was represented using the Robinson et al. (2017) 30-m Landsat-derived NDVI product, with two 16-day composites per year at DOY 129 (09–24 May) and DOY 157 (14–30 Sep) — dates selected to bracket the peak of water availability and correspond to spring and fall migration peaks. Mean NDVI within the 5-km buffer of each station was extracted using Zonal Statistics in ArcGIS Pro; open water pixels were masked prior to extraction. Python scripting was used to automate extraction of mean spatial variable values across buffer distances and sites.

**ENSO.** The Multivariate ENSO Index (NOAA) was averaged over the same October–September annual window.

**Community analyses.** Daily total captures and species richness were modeled as functions of temperature, precipitation, ENSO, NDVI, year, and physiographic region using GLMMs with Poisson errors (R package *lme4*), with banding station as a random intercept. Community composition was analyzed via Principal Coordinate Analysis on a Bray–Curtis dissimilarity matrix (R package *vegan*).

**Demographic rates.** For 30 riparian species with sufficient recapture data, Cormack–Jolly–Seber and Pradel capture–mark–recapture models (R package *RMark*) estimated apparent survival (φ), recruitment (F), and realized population growth rates (λ) as functions of the same climate and greenness covariates.

## Outputs

- Published article: *Animal Conservation*, 2021; DOI: [10.1111/acv.12755](https://doi.org/10.1111/acv.12755)
- Community-level analyses: captures, species richness, and PCoA composition models
- Demographic rate estimates for 30 riparian species across three parameters (φ, F, λ)
- PRISM and NDVI spatial datasets extracted for 8 sites × 15 years

## My Role

As third of eight co-authors, I contributed to the early research design — particularly around the selection of NDVI and PRISM climate datasets and the definition of spatial extraction parameters. I led the phenology analysis that informed the choice of NDVI observation dates (DOY 129 and 157), which were selected to bracket the peak of seasonal water availability in the region and align with spring and fall migration windows. I performed all NDVI and climate data processing, including Python scripting to compute mean spatial variable values within multiple buffer distances around each banding station, and used ArcGIS Pro (Buffer, Zonal Statistics) to execute the extractions. I assisted in drafting the manuscript and in developing the strategy for responding to reviewer comments. Statistical modeling — including the GLMMs, PCoA, and CMR analyses — was led by the first author.
