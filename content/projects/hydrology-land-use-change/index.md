---
title: "Climate and Land Use Change Impacts on Streamflow and Sediment Yield — Jordan River Watershed"
date: 2016-11-01
summary: "Scenario-based hydrological modeling study using HSPF to simulate streamflow and sediment yield in the snowmelt-dominated Jordan River watershed under future climate and LULC change — finding that climate change overwhelms any difference between business-as-usual and smart-growth development patterns as a driver of watershed-scale hydrology."
domain: "Urban Ecology"
region: "Jordan River watershed, Salt Lake County, Utah, USA"
ecosystem: "Snowmelt-dominated semiarid mountainous watershed; Wasatch Range headwaters draining through a rapidly urbanizing valley to the Great Salt Lake; Great Basin"
methods:
  - "HSPF v12 (EPA BASINS 4.1) for streamflow and sediment simulation"
  - "Dynamical downscaling via WRF at 4 km resolution (RCP 6.0, 2035–2044 and 2085–2094)"
  - "Statistical downscaling via BCSD from CMIP5 ensemble (231 simulations, 4 RCPs)"
  - "Change-factor bias correction for dynamically downscaled outputs"
  - "BUG LULC scenario: parcel-scale binary logistic regression spatial attraction model"
  - "COG LULC scenario: Wasatch Choice for 2040 via Envision Tomorrow+ sketch-planning tool"
  - "Parcel-scale impervious cover estimation using per-class EIF lookup (residential: 0.20; commercial/retail/industrial: 0.75)"
  - "Sensitivity analysis isolating climate vs. LULC change drivers"
  - "50th-percentile timing analysis for streamflow and sediment load"
sector: "Academic"
era: "UU-GCSC"
featureimage: "images/projects/hydrology-land-use-change/feature.jpg"
publications:
  - title: "Impact of Climate and Land Use Change on Streamflow and Sediment Yield in a Snow-Dominated Semiarid Mountainous Watershed"
    doi: "10.1111/1752-1688.12803"
roles:
  - "Co-author (4th of 5)"
  - "Identified and evaluated candidate LULC change models; recommended BUG and COG scenarios"
  - "Developed and executed parcel-scale impervious cover estimation methodology for both LULC scenarios — the direct HSPF inputs for the LULC model component"
  - "Assisted in BUG scenario development (led by Ewing/Tian, UU Metropolitan Research Center)"
  - "Contributed to study conceptualization and manuscript writing"
  - "Presented findings at 2016 Salt Lake County Watershed Symposium"
---

## Overview

This study investigated the combined effects of future climate and urban land use/land cover (LULC) change on streamflow and sediment yield in the Jordan River watershed, Salt Lake County, Utah — a snowmelt-dominated mountainous system draining through one of Utah's most rapidly urbanizing valleys. The research was conducted within the NSF-funded iUTAH (innovative Urban Transitions and Arid region Hydro-sustainability) EPSCoR consortium, which brought together atmospheric scientists, civil engineers, and urban planners at the University of Utah to study water sustainability under coupled climate and land use change.

Using the Hydrological Simulation Program — FORTRAN (HSPF v12), the study simulated hourly streamflow and sediment load under historical (2000s) and future (2040s and 2090s) conditions at two sites: Big Cottonwood Creek at the canyon mouth, which is largely free of urban influence and reflects climate change effects in isolation; and the Jordan River above the Surplus Canal, where both climate and LULC change were expected to affect hydrology. The central question was whether the form of future urban growth — business-as-usual sprawl versus a smart-growth alternative — would produce meaningfully different hydrological outcomes relative to climate change alone.

## Region & Ecosystem

The Jordan River watershed encompasses most of Salt Lake County, bounded by the Wasatch Mountains to the east, the Oquirrh Mountains to the west, the Traverse Range to the south, and the Great Salt Lake to the northwest. The watershed's hydrology is fundamentally split between its high-elevation Wasatch headwaters (1,960–2,607 m), where snowmelt dominates streamflow generation, and the broad urbanized valley floor below. About 46% of watershed area lies in rugged mountain terrain that is largely undevelopable; approximately 348 km² of the Wasatch headwaters are protected for municipal drinking water supply for Salt Lake City and Sandy City.

The Jordan River originates as outflow from Utah Lake to the south, flows northward approximately 80 km through the county, and discharges into the hypersaline Great Salt Lake — contributing more than 20% of that terminal lake's freshwater inflow. The river is highly managed, its flow affected by Utah Lake releases, wastewater effluent, stormwater, irrigation return flows, and snowmelt diversions from the Wasatch canyons, which collectively supply roughly two-thirds of the valley's drinking water. The two study sites bracket the hydrological spectrum: Big Cottonwood Creek's 129.24 km² upper subwatershed (average slope 50.8%) is essentially unurbanized, while the Jordan River at Surplus Canal integrates the full complexity of the urbanized valley.

## Methods

**HSPF model.** The study extended a calibrated HSPF v12 model originally built by Stantec Consulting Inc. for Salt Lake County Watershed Planning and Restoration, implemented within EPA BASINS 4.1. The model delineates the watershed into 17 major watersheds, 27 subwatersheds, and 197 subbasins. It was calibrated against observed streamflow and sediment data for January 1995 through December 2004 and validated through December 2006, with simulations run at hourly time steps and aggregated to daily results.

**Climate scenarios.** Future climate inputs were derived from two independent downscaling approaches. Dynamical downscaling used the WRF regional climate model at 4 km horizontal resolution under RCP 6.0, simulating the mid-century decade (2035–2044) and late-century decade (2085–2094), with boundary conditions derived from the NCAR Community Climate System Model. Because WRF outputs contain model biases, a change-factor approach was applied — using WRF-derived perturbation signals to offset historical temperature records and scale historical precipitation rather than using WRF outputs directly. Statistical downscaling provided a broader uncertainty envelope using BCSD-downscaled CMIP5 output from 231 simulations spanning more than twenty global climate models and all four RCPs (2.6, 4.5, 6.0, and 8.5).

**LULC scenarios.** Two future LULC scenarios for the valley (mountain areas were held constant) were compared against a no-change baseline. The **BUG (Business-As-Usual Growth)** scenario was a parcel-scale spatial attraction model developed by researchers at the University of Utah Metropolitan Research Center, using logistic regression models for five land use types calibrated to observed 2015 land use patterns. Predictor variables included neighboring land uses and parcel accessibility to regional population and employment using WFRC's 2040 travel demand model, with population and employment allocated parcel-by-parcel against Utah GOMB 2040 projections as control totals. The **COG (Centers-Oriented Growth)** scenario was the Wasatch Choice for 2040 regional plan, developed by the Wasatch Front Regional Council through participative planning with municipal and county governments, focusing one-third of projected growth into development centers occupying just 3% of the growth areal footprint. COG scenario outputs were produced using the Envision Tomorrow+ sketch-planning tool, which generates parcel-level impervious fraction estimates alongside land use designation changes.

**Parcel-scale impervious cover estimation.** Translating LULC change outputs into HSPF inputs required estimating net changes in impervious surface area at the parcel level. I developed and executed this methodology for both scenarios: parcel-level land use conversions were assigned impervious cover fractions using a per-class effective impervious fraction (EIF) lookup (residential: 0.20; commercial/retail/industrial: 0.75), applied to each parcel with a changed land use designation. For the COG scenario, which modeled redevelopment of previously developed parcels, gross impervious area gains and losses were both accounted for. These parcel-scale impervious area estimates were the direct HSPF inputs for the LULC model component.

**Sensitivity analysis.** To isolate the relative contributions of climate and LULC change, three sensitivity runs were compared at the Jordan River site: (1) LULC change only with historical climate; (2) climate change only with existing LULC; and (3) combined climate and LULC change. Results were also compared across all three LULC scenarios under a consistent climate input to identify which growth scenario produced the largest hydrological response.

## Findings

**Big Cottonwood Creek — climate change only.** At the canyon mouth, where LULC is effectively static, mean annual streamflow was projected to increase 11.2% by the 2040s and 6.8% by the 2090s under the RCP 6.0 scenario. Sediment load changes were larger and nonlinear: +6.7% by the 2040s and +39.7% by the 2090s, driven by a projected shift from snow to rain in the headwaters and more frequent high-intensity rainfall events intercepted by the steeply sloped watershed. The 50th-percentile timing of both streamflow and sediment load is projected to shift approximately four weeks earlier by mid-century and eight weeks earlier by late-century — a dramatic compression of the historical spring runoff window with significant implications for water supply management.

**Jordan River above Surplus Canal — climate and LULC change.** At the valley site, mean annual streamflow was projected to increase 14.5% (2040s) and 15.3% (2090s). Sediment increases were more modest — +7.4% (2040s) and +14.2% (2090s) — reflecting the dampening effects of canal diversions, Utah Lake management, and the urban landscape's reduced sediment supply relative to the mountain headwaters. Snowmelt timing shifted similarly, with the 50th-percentile flow date advancing from mid-May in the 2000s to April and early March in the 2040s and 2090s.

**Climate change dominates over LULC scenario choice.** The sensitivity analysis produced the study's most consequential planning finding: despite the BUG scenario generating a net 65 km² of new impervious surface compared to just 10 km² under COG — a 6:1 ratio — neither scenario produced streamflow or sediment loads meaningfully different from each other or from the no-change LULC baseline. All three LULC scenarios generated streamflow changes within about 2.7% of each other under identical climate inputs, and sediment load differences were similarly negligible. Climate change, by contrast, drove streamflow and sediment shifts an order of magnitude larger than any LULC effect. In a snowmelt-dominated watershed of this scale — where the dominant hydrological signal originates in the largely undevelopable mountain headwaters — the form of future valley development has little leverage over aggregate watershed hydrology at the locations and scales modeled here.

## Outputs

- Hourly and daily HSPF streamflow and sediment concentration simulations for 2000s, 2040s, and 2090s at two sites (Big Cottonwood canyon mouth; Jordan River above Surplus Canal)
- Parcel-scale impervious cover change maps for BUG and COG LULC scenarios (2010–2040)
- Climate uncertainty bounds from 231-member CMIP5 statistical downscaling ensemble
- Sensitivity analysis quantifying relative contributions of climate vs. LULC change drivers
- Streamflow–sediment concentration regression relationships at both sites for 2040s and 2090s
- Seasonal streamflow and sediment box plots (5th–95th percentile) for 2000s, 2040s, and 2090s
- Peer-reviewed publication in the *Journal of the American Water Resources Association* (2019)

## My Role

I joined this project as a collaborator bridging the urban planning and hydrological modeling components. My primary contribution was the LULC change methodology: I identified and evaluated candidate LULC change models for the study and recommended both the BUG spatial interaction model and the COG Wasatch Choice scenario as the contrasting scenario pair. I then developed and executed the parcel-scale impervious cover estimation methodology — the analytical step that translated LULC change outputs from both scenarios into the impervious area estimates used directly as HSPF model inputs. For the COG scenario, which also modeled redevelopment of previously developed parcels, I accounted for both gross impervious gains and losses at the parcel level. I also assisted in the BUG scenario development (led by Ewing and Tian at the UU Metropolitan Research Center), contributed to study conceptualization and manuscript writing, and presented findings from this work at the 2016 Salt Lake County Watershed Symposium.
