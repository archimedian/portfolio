---
title: "Graph-Theory Habitat Connectivity Modeling — Kansas City Metropolitan Region"
date: 2014-09-01
summary: "Proof-of-concept habitat connectivity analysis for the Mid-America Regional Council using the Kansas City NRI II land cover product, modeling functional patch networks and importance rankings for Western painted turtle and Eastern meadowlark — finding that highway infrastructure has fragmented turtle connectivity in the urbanizing suburban fringe, while meadowlark habitat forms a distinctive ring around the conurbation where total area, not connectivity, is the binding constraint."
domain: "Conservation Science"
region: "Kansas City metropolitan region, Missouri/Kansas, USA"
ecosystem: "Tallgrass prairie remnants, freshwater wetlands, urban/suburban fringe, agricultural matrix"
methods:
  - "Kansas City NRI II land cover (2.5m, 2012; multispectral imagery + airborne LiDAR)"
  - "Species-specific habitat reclassification and raster resampling (10m turtle, 20m meadowlark)"
  - "Morphological filtering (erode-then-dilate) for patch simplification"
  - "Large roadway extraction from impervious surface mask"
  - "HUC12 watershed delineation (National Watershed Boundary Dataset)"
  - "Graphab 1.2: graph-theory connectivity modeling, PC and dPC metrics"
  - "Least-cost/resistance path modeling (turtle); Euclidean dispersal (meadowlark)"
  - "Focal species parameterization from literature review and expert consultation"
  - "ArcGIS 10.2 for all spatial processing"
sector: "Regional Government"
era: "UU-MRC"
featureimage: "images/projects/kcmo-habitat-connectivity/feature.jpeg"
roles:
  - "Sole analyst and report author"
  - "Analytical design and all spatial data processing"
  - "Focal species literature review and expert consultation (Missouri Dept. of Conservation)"
  - "Connectivity graph construction and dPC analysis (Graphab 1.2)"
  - "Planning recommendations for MARC"
---

## Overview

This project was a proof-of-concept demonstration of graph-theory-based habitat connectivity modeling for the Mid-America Regional Council (MARC), delivered under an omnibus ecosystem services contract between MARC and the University of Utah Metropolitan Research Center. The immediate occasion was the completion of the Kansas City Natural Resource Inventory II (NRI II) — a 2.5-meter land cover product derived from multispectral imagery and airborne LiDAR — and a question about what more sophisticated ecological analyses that data product could support beyond the inventory itself.

The study was explicitly scoped as a demonstration rather than a conservation or management plan. The goal was to apply graph-theory connectivity methods to the NRI II using two real focal species, produce findings meaningful to MARC's planning context, and equip MARC staff with a conceptual and methodological foundation for incorporating connectivity into regional land use planning. The report concluded with direct recommendations for that integration.

## Region & Ecosystem

The study area covers the nine-county Kansas City metropolitan region straddling the Missouri–Kansas state line. The region sits at the eastern edge of the tallgrass prairie biome — one of the most historically extensive and now most converted ecosystems in North America — at its transition to eastern deciduous forest. Centuries of agricultural conversion and 20th-century urbanization have replaced most of the original prairie and wetland mosaic with row-crop agriculture (predominantly corn-soybean rotation) and urban/suburban development, leaving scattered remnant patches in a heavily modified matrix.

The resulting landscape has a distinctive spatial structure: intact riparian corridors along the Missouri and Kansas Rivers and their major tributaries; scattered prairie and wetland remnants at the suburban fringe; a dense urban core with minimal natural cover; and a rural agricultural hinterland with limited structural diversity for wildlife. For species dependent on wetland-riparian or native grassland habitat, the primary pressures are patch isolation at the urban edge and habitat simplification in the agricultural matrix. Major highway corridors — I-70, I-435, I-470/US-50, I-49 — function as hard movement barriers for species with low overland dispersal capacity or high road-crossing mortality.

## Focal Species

**Species selection.** Three candidate species were evaluated at the outset: Western painted turtle (*Chrysemys picta bellii*), Eastern meadowlark (*Sturnella magna*), and white-tailed deer (*Odocoileus virginianus*). Species selection was guided in part by expert consultation with Larry Rizzo of the Missouri Department of Conservation, who advised on identifying species of genuine conservation concern and regional significance while avoiding species whose selection might be politically contentious. Deer were dropped after literature review and that consultation confirmed that white-tailed deer are habitat generalists with high dispersal capacity and well-documented tolerance of urban and agricultural matrices — characteristics that make discrete-patch connectivity modeling an inappropriate analytical frame for the species. The two retained species represent contrasting habitat dependencies and dispersal ecologies that together illuminate different dimensions of landscape connectivity in the Kansas City region.

**Western painted turtle (*Chrysemys picta bellii*).** The painted turtle is a semi-aquatic species associated with ponds, wetlands, and slow-moving stream reaches with basking structure and emergent vegetation. Although capable of overland movement during nesting dispersal, turtles have limited terrestrial mobility and high road mortality, making paved roadways — and highways in particular — effective barriers to population connectivity. The turtle analysis was conducted at the HUC12 watershed scale and used a least-cost/resistance path framework to model functional dispersal pathways through the landscape matrix. Dispersal distance parameters were derived from the primary literature; habitat requirements were informed by the literature and by expert consultation with Larry Rizzo of the Missouri Department of Conservation.

**Eastern meadowlark (*Sturnella magna*).** The meadowlark is an obligate grassland songbird requiring large, structurally intact grassland patches for successful breeding. Its regional habitat consists of tallgrass prairie remnants, managed grasslands, and hayfields — elements now squeezed between the urban core and the intensive agricultural matrix. Unlike the turtle, meadowlarks disperse across relatively large distances and are not strongly deterred by roads. Euclidean (straight-line) distance was used as the dispersal model, and the analysis was conducted at the full nine-county metro scale to capture the regional distribution of grassland connectivity.

## Methods

**Primary dataset.** The Kansas City NRI II (2012) was the sole land cover input throughout. This 2.5-meter product — produced from multispectral aerial imagery fused with airborne LiDAR-derived canopy height and structure — provided sufficient thematic resolution to distinguish wetland, grassland, and upland cover types at the patch scales relevant to both focal species. For each species, the NRI was resampled to an analysis resolution appropriate to its dispersal scale: 10 m for turtle, 20 m for meadowlark.

**Habitat reclassification.** NRI land cover classes were reclassified into binary habitat/non-habitat maps for each species based on species-specific requirements from the literature. Turtle habitat included ponds, wetlands, lacustrine shorelines, and slow-water stream corridors with suitable basking substrate. Meadowlark habitat included native and managed grasslands, hayfields, and other open herbaceous covers meeting minimum structural criteria.

**Morphological filtering and patch definition.** Binary habitat maps were processed with an erode-then-dilate morphological filter to remove isolated single-pixel noise and simplify patch geometry, producing cleaner patch boundaries better suited to graph-theory modeling. Patch area thresholds were then applied: minimum 0.03 ha and maximum 5.9 ha for turtle (calibrated to wetland patch size distributions in the region); minimum 50 acres for meadowlark (reflecting published territory and minimum viable patch area requirements for breeding success).

**Roadway barriers.** Major roads functioning as effective movement barriers for turtles were extracted from the NRI impervious surface layer using an erode-then-dilate operation calibrated to isolate features of approximately four-lane width or greater. The resulting barrier layer was incorporated into the turtle resistance surface, imposing high movement cost on crossings of barrier-class roads in the least-cost path calculations.

**Watershed delineation.** The turtle analysis was structured at the HUC12 watershed scale, reflecting the hydrologically defined unit most relevant to a semi-aquatic species. Two watersheds were selected for detailed comparison to bracket the range of connectivity conditions present in the metro region: the **Longview** watershed on the urbanizing suburban fringe (southeast KC), and the **Freeman** watershed in a less-fragmented agricultural area to the south.

**Connectivity modeling.** Functional connectivity graphs were constructed and analyzed in Graphab 1.2. Habitat patches served as graph nodes; least-cost paths (turtle) or Euclidean paths (meadowlark) parameterized with species-specific maximum dispersal distances served as edges. The Probability of Connectivity (PC) index summarized whole-network functional connectivity for each analysis area. Patch importance was quantified via the delta-PC (dPC) metric — a patch-removal experiment measuring the fractional decline in overall PC when each patch is individually removed — producing a ranked list of patches and links by their contribution to network-wide connectivity.

## Findings

**Turtle — Longview watershed.** Despite containing substantial wetland and pond habitat, the Longview watershed network is fragmented into isolated, non-communicating components by its highway infrastructure. The I-470/US-50 corridor and I-49 together bisect the patch network, severing functional connectivity between turtle subpopulations on opposite sides of these barriers. No least-cost dispersal paths cross these corridors under the modeled parameters, meaning that turtle populations in different portions of the Longview watershed have no functional exchange. High-dPC patches and links are concentrated at the edges of the highway barriers — precisely the locations where targeted habitat protection or wildlife crossing infrastructure could restore network-level connectivity most efficiently.

**Turtle — Freeman watershed.** The Freeman watershed presents a markedly different picture. With lower road density and a less fragmented matrix, all habitat patches participate in a single fully-connected network. dPC values are distributed more evenly across a larger number of individually important patches rather than concentrated at a few critical bottleneck nodes. This watershed illustrates the baseline connectivity condition the metro region could sustain under less intensive urbanization and serves as a reference against which the fragmentation effects in Longview are legible.

**Meadowlark — metro-wide pattern.** The meadowlark analysis revealed a geographically striking pattern: grassland habitat forms a near-continuous ring around the urban core, occupying the suburban-agricultural fringe where building density is low enough to permit herbaceous ground cover but agricultural intensity has not yet eliminated all unplowed land. This ring is not a planning artifact — it emerges directly from the land cover data and reflects the dual squeeze of intense urbanization from the center and intensive row-crop agriculture from the periphery. Within this ring, patch connectivity is generally adequate; meadowlarks can move among most habitat patches at literature-supported dispersal distances. The binding constraint for this species in the Kansas City region is not connectivity — it is total habitat area. Further conversion of grassland remnants at the suburban fringe, whether to development or cropland, reduces the absolute amount of breeding habitat available regardless of how well-connected the remaining patches are. Management and planning attention should focus on protecting and restoring grassland area, not primarily on improving linkages between existing patches.

## Outputs

- Binary habitat patch maps for Western painted turtle and Eastern meadowlark derived from NRI II
- Functional connectivity graphs with PC index values for all analysis areas
- dPC patch and link importance maps: turtle (Longview and Freeman HUC12 watersheds) and meadowlark (nine-county metro)
- Comparative network statistics for Longview and Freeman turtle watersheds
- Roadway barrier layer derived from NRI II impervious surface
- Final report: species profiles, methods, findings, and recommendations for incorporating connectivity analysis into MARC's regional planning program

## My Role

As sole analyst and author, I designed the full analytical framework, selected and parameterized the focal species, and executed all spatial processing and connectivity modeling independently. I conducted the focal species literature review for all three candidate species — including the analysis that led to dropping white-tailed deer — and led the expert consultation with Larry Rizzo of the Missouri Department of Conservation, whose input informed both species selection (prioritizing species of conservation concern and regional significance over politically contentious options) and the habitat requirements incorporated into the habitat and mobility modeling. I performed all raster processing, morphological filtering, habitat reclassification, and roadway extraction in ArcGIS 10.2; constructed and analyzed all connectivity graphs in Graphab 1.2; and produced all output maps and figures. I wrote the full report, including the findings and the planning recommendations addressed to MARC staff.
