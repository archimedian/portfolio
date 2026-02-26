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

Red Butte Creek flows from the Wasatch Range westward into the Salt Lake Valley, draining a 20.9 km² basin across an elevation gradient of 2,020–1,330 m. The study area encompasses nine distinct stream reaches organized into three major land use zones:

**Natural montane canyon (0–7.7 km):** Upper Canyon (0–5.6 km) in the Red Butte Canyon Research Natural Area, managed by the USDA Forest Service and closed to the public; a reservoir and dam (5.6–6.1 km, built 1930); and Lower Canyon (6.1–7.7 km), including the Red Butte Garden.

**University of Utah campus (7.7–10.1 km):** Three reaches crossing institutional property — Campus Research Park, Campus VA (Veterans Affairs), and Campus Sunnyside Park.

**Residential Salt Lake Valley (10.1–11.9 km):** Three reaches flowing through Residential Miller Park, Residential Upper, and Residential Lower neighborhoods, where most riparian habitat consists of privately owned yards. After 12 km, the creek is channelized underground.

Three distinct hydrologic domains, identified by Gabor et al. (2017) from discharge and water chemistry, overlay these land use transitions: an *upper gaining* reach (0–6 km) that receives groundwater year-round; a *middle transitional* reach (6–9.5 km) that gains in winter and loses to groundwater in summer; and a *lower gaining* reach (9.5–12 km) that gains year-round but carries clear urban chemical signatures.

## Methods

**LiDAR data.** Raw airborne LiDAR data were obtained through OpenTopography for the Salt Lake City area, collected in 2013–2014 with eight returns per m² and horizontal and vertical accuracy of approximately 7 cm. The raw point cloud was classified into ground, buildings, water, and vegetation points using the *lasclassify* tool in LAStools. A digital terrain model (DTM) was derived from ground points only; a spike-free canopy height model (CHM) was derived from height-normalized ground and vegetation points following Khosravipour et al. (2016).

**Plot delineation.** Sample plots were defined in ArcGIS 10.3.1 starting from a smoothed stream centerline. Nominal 50×50 m plots were delineated at 50 m increments along the stream for longitudinal analysis; nominal 10×50 m plots were created by offsetting the centerline in 10 m increments to 50 m on each side for lateral (stream-to-upland) analysis. Right-bank plots were categorized as generally south-facing and left-bank plots as generally north-facing.

**Vegetation metrics.** Three metrics were computed for every plot using *lasheight* and *lascanopy* (LAStools): vegetation cover (%), as the ratio of first returns classified as vegetation to total first returns; average canopy height (m), calculated from the pit-free CHM; and canopy density for five height intervals — low (<1.5 m), low/mid (1.5–5 m), mid (5–9 m), high (9–18 m), and very high (>18 m) — representing the 3D distribution of vegetation returns.

**Height above river (HAR).** HAR was calculated using the Riparian Topography Tools extension (Dilts 2015) in ArcMap, using the DTM and a flow accumulation model as inputs. The stream was burned into the DTM in areas redirected through culverts to produce an accurate flow accumulation surface.

**Field surveys.** Woody species composition was recorded along 23 transects in summer 2016. Each 20-m transect (10 m on each side of the stream) was placed approximately equidistant (~500 m) along the creek. Species composition was determined using a step-point technique, recording hits at 1-m intervals. Each species was classified by native status (native vs. introduced) and wetland indicator status (WIS) following the USDA PLANTS database.

**Statistical analysis.** Generalized least squares (GLS) mixed-effects regression was used to model each vegetation metric (cover, canopy height, canopy density) as a function of HAR, bank orientation, and elevation, with separate models for each of the three hydrologic domains. Spatial autocorrelation was evaluated with variograms and Moran's I, and an optimal spatial covariance structure (exponential or spherical) was selected via AIC. A VarIdent variance structure was incorporated where necessary to accommodate heteroscedasticity among land use categories. Model selection used backward elimination by likelihood ratio test.

## Outputs

- LiDAR-derived vegetation profiles (cover, canopy height, 5-interval canopy density) for all 50×50 m and 10×50 m plots along 12 km of Red Butte Creek
- HAR surface and per-plot HAR estimates
- Woody species composition data from 23 field transects (relative density by species, native status, WIS)
- GLS models of vegetation structure for three hydrologic domains and three vegetation metrics
- Published article: *Ecohydrology*, 2020; DOI: [10.1002/eco.2259](https://doi.org/10.1002/eco.2259)

## My Role

As second of four co-authors, I acquired and processed the airborne LiDAR data from OpenTopography. I designed and implemented the plot delineation workflow in ArcGIS 10.3.1, establishing the 50×50 m and 10×50 m sample grids along the smoothed stream centerline. Using LAStools, I assisted in computing the DTM, spike-free CHM, and vegetation structure metrics (cover, average canopy height, and canopy density across the five height intervals) for the plots. I pre-processed DTMs including stream burning in culverted areas and calculated HAR for all plots using the Riparian Topography Tools extension in ArcMap. I contributed to the drafting and review of the manuscript. Statistical analysis and field data collection were led by the first author.
