---
title: "Using LiDAR to Assess Transitions in Riparian Vegetation Structure along a Rural-to-Urban Land Use Gradient in Western North America"
date: 2020-04-01
summary: "LiDAR and field-based study of riparian forest structure along Red Butte Creek, Utah, finding that land use transitions — especially individual landowner decisions — decouple urban riparian vegetation from stream hydrology, producing exceptionally tall canopies in older residential reaches while native species dominate the protected canyon upstream."
domain: "Conservation Science"
region: "Salt Lake City, Utah, USA"
ecosystem: "Semiarid riparian corridor; montane canyon through urban valley, Great Basin"
methods:
  - "Airborne LiDAR (OpenTopography 2013–2014, 8 returns/m²)"
  - "Point cloud classification and CHM generation (LAStools: lasclassify, lasheight, lascanopy)"
  - "Spike-free canopy height model (Khosravipour et al. 2016)"
  - "50×50 m and 10×50 m plot delineation along smoothed stream centerline (ArcGIS 10.3.1)"
  - "Height above river (HAR) via Riparian Topography Tools (Dilts 2015)"
  - "Field woody species surveys: 23 transects, step-point technique (summer 2016)"
  - "Native status and wetland indicator status classification (USDA PLANTS)"
  - "GLS mixed-effects regression with spatial covariance structures (R: nlme, gstat, ape, car)"
sector: "Academic"
era: "UU-GCSC"
featureimage: "images/projects/lidar-riparian-veg/feature.jpeg"
publications:
  - title: "Using LiDAR to assess transitions in riparian vegetation structure along a rural-to-urban land use gradient in western North America"
    doi: "10.1002/eco.2259"
roles:
  - "Co-author (2nd of 4)"
  - "LiDAR data acquisition and processing"
  - "Plot delineation workflow design and implementation (ArcGIS 10.3.1)"
  - "DTM, CHM, and all vegetation structure metric computation (LAStools)"
  - "HAR calculation (Riparian Topography Tools)"
  - "Research design contribution, manuscript drafting, and review"
---

## Overview

Published in *Ecohydrology* (2020), this study used airborne LiDAR paired with ground-based field surveys to quantify the three-dimensional structure and woody species composition of the riparian forest along Red Butte Creek, Salt Lake City, Utah — a stream that flows 12 km from a highly protected montane Research Natural Area through the University of Utah campus and into densely built residential neighborhoods, spanning an elevation gradient of approximately 700 m.

The central finding is that while the structure of riparian vegetation in the protected upper canyon closely reflects the topographic and hydrological drivers one would expect — canopy height is negatively correlated with height above the river (HAR), and north-facing aspects support taller, denser canopies — these predictable relationships break down in the urbanized middle and lower reaches. There, individual landowner decisions appear to decouple riparian vegetation from stream hydrology entirely. Older residential neighborhoods are characterized by exceptionally tall trees (>18 m) introduced through horticultural planting, and introduced species reach 100% of woody canopy composition in the lower residential area — in contrast to the fully native assemblage of the upper canyon.

## Region & Ecosystem

Red Butte Creek flows from the Wasatch Range westward into the Salt Lake Valley, draining a 20.9 km² basin across an elevation gradient of approximately 700 m (2,020–1,330 m). The 12-km study reach passes through three major land use zones in rapid succession: a highly protected montane canyon (Red Butte Canyon Research Natural Area, managed by the USDA Forest Service); the University of Utah campus; and densely built residential neighborhoods in the Salt Lake Valley, where the creek is eventually channelized underground. Three distinct hydrologic domains identified by Gabor et al. (2017) overlay this gradient — an upper gaining reach (year-round groundwater input), a middle transitional reach (winter gaining, summer losing), and a lower gaining reach with strong urban water chemistry signatures — creating a matrix of interacting land use and hydrologic effects on riparian vegetation.

## Methods

**LiDAR data and vegetation metrics.** Raw airborne LiDAR data were obtained from OpenTopography (Salt Lake City area, 2013–2014; 8 returns/m², ~7 cm accuracy). The point cloud was classified into ground, buildings, water, and vegetation using *lasclassify* (LAStools); a DTM was derived from ground points and a spike-free CHM from height-normalized vegetation returns (Khosravipour et al. 2016). Sample plots — nominal 50×50 m for longitudinal analysis and 10×50 m at five lateral offsets from the stream centerline — were delineated in ArcGIS 10.3.1. Three vegetation structure metrics were computed per plot using *lasheight* and *lascanopy*: cover (%), average canopy height (m), and canopy density for five height intervals (<1.5 m, 1.5–5 m, 5–9 m, 9–18 m, >18 m).

**Stream topography and field surveys.** Height above river (HAR) was calculated using the Riparian Topography Tools extension (Dilts 2015) in ArcMap from the LiDAR-derived DTM and a flow accumulation model, with stream burning applied in culverted areas. Woody species composition was recorded along 23 transects (summer 2016) using a step-point technique, with each species classified by native status and wetland indicator status (WIS) per the USDA PLANTS database.

**Statistical analysis.** Generalized least squares (GLS) mixed-effects regression modeled each vegetation metric as a function of HAR, bank orientation, and elevation, with separate models fit for each of the three hydrologic domains. Spatial autocorrelation was assessed via variograms and Moran's I; optimal spatial covariance structures (exponential or spherical) were selected by AIC. A VarIdent variance structure accommodated heteroscedasticity among land use categories where needed; fixed effects were selected by backward elimination using likelihood ratio tests.

## Outputs

- LiDAR-derived vegetation profiles (cover, canopy height, 5-interval canopy density) for all 50×50 m and 10×50 m plots along 12 km of Red Butte Creek
- HAR surface and per-plot HAR estimates
- Woody species composition data from 23 field transects (relative density by species, native status, WIS)
- GLS models of vegetation structure for three hydrologic domains and three vegetation metrics
- Published article: *Ecohydrology*, 2020; DOI: [10.1002/eco.2259](https://doi.org/10.1002/eco.2259)

## My Role

As second of four co-authors, I acquired and processed the airborne LiDAR data from OpenTopography. I designed and implemented the plot delineation workflow in ArcGIS 10.3.1, establishing the 50×50 m and 10×50 m sample grids along the smoothed stream centerline. Using LAStools, I assisted in computing the DTM, spike-free CHM, and vegetation structure metrics (cover, average canopy height, and canopy density across the five height intervals) for the plots. I pre-processed DTMs including stream burning in culverted areas and calculated HAR for all plots using the Riparian Topography Tools extension in ArcMap. I contributed to the drafting and review of the manuscript. Statistical analysis and field data collection were led by the first author.
