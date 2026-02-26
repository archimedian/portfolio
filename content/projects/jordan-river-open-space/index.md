---
title: "Jordan River Open Space Inventory — Salt Lake County Conservation Prioritization and Gap Analysis"
date: 2016-02-01
summary: "Parcel-level conservation prioritization and gap analysis for the Jordan River Commission, producing a geodatabase of all Salt Lake County parcels within a 1-mile corridor coded by open-space zoning, conservation easement, and public ownership status — subsequently adopted by three stakeholder organizations for land acquisition planning and regulatory decision-making."
domain: "Conservation Science"
region: "Salt Lake County, Utah, USA"
ecosystem: "Urban riparian corridor (Jordan River)"
methods:
  - "1-mile buffer around Jordan River centerline (NHDPlus v2, USGS)"
  - "Parcel data from UGRC statewide parcel layer"
  - "Ownership typology from SLCo Assessor data (reclassified to private/public binary)"
  - "Conservation easements from National Conservation Easement Database (NCED)"
  - "Water-related land use from UGRC (State of Utah)"
  - "Municipal zoning data from 12 SLCo municipal GIS departments"
  - "Manual crosswalk of 12 zoning schemas to unified open-space-compatible classification"
  - "ArcGIS Desktop 10.3.1"
sector: "Regional Government"
era: "Hippodameian"
featureimage: "images/projects/jordan-river-open-space/feature.jpeg"
roles:
  - "Research design lead"
  - "Sole GIS analyst"
  - "Led UU Urban Planning graduate student team in zoning crosswalk development"
  - "Primary client liaison (Jordan River Commission Executive Director)"
---

## Overview

The Jordan River Open Space Inventory (JROSI) was a parcel-level conservation prioritization and gap analysis commissioned by the Jordan River Commission to identify open-space-compatible land within a 1-mile buffer of the Jordan River centerline in Salt Lake County. The project was designed to serve two functions: guide future land acquisition along the corridor, and inform permitting decisions by giving agencies and planners a parcel-by-parcel picture of current ownership, zoning, and conservation status.

The deliverable — a geodatabase assigning each parcel in the study area a yes/no code on three independent dimensions (open-space zoning, conservation easement coverage, public ownership) — proved immediately useful. Within months of delivery, Executive Director Laura Hanson confirmed in writing that the JROSI database was in active use by three separate organizations: the Jordan River Commission Technical Advisory Committee (general reference), the Salt Lake County Open Space Trust (guiding land acquisition discussions), and the Utah Division of Forestry, Fire and State Lands, which drew on the inventory in developing its Comprehensive Management Plan — specifically to inform decisions about whether to approve future permit applications for new structures along the river.

## Region & Ecosystem

The Jordan River flows approximately 51 miles northward through the Salt Lake Valley, draining Utah Lake to the Great Salt Lake through one of the most densely urbanized corridors in the state. The study area encompasses all Salt Lake County parcels within 1 mile of the river centerline — a corridor that crosses twelve municipalities ranging from urban Salt Lake City through suburban and semi-rural communities to the south. Davis County and Utah County portions of the river were excluded from scope.

As an urban riparian corridor in an arid region, the Jordan River carries disproportionate ecological value relative to its disturbed condition: it provides the primary continuous greenway and wildlife movement corridor through the valley, supports cottonwood-willow riparian vegetation where banks remain undeveloped, and is subject to ongoing conservation, restoration, and recreation investment by multiple agencies and organizations. The fragmented ownership and zoning landscape along the corridor — spanning private parcels, municipal parks, county open space, and state lands — makes systematic parcel-level inventory essential for coordinated conservation action.

## Methods

**Study area delineation.** A 1-mile buffer was generated around the Jordan River centerline derived from the USGS NHDPlus v2 hydrography dataset. The analysis was scoped to Salt Lake County parcels only; Davis County and Utah County were excluded at the client's direction.

**Parcel data.** Base parcel geometries and attributes were sourced from the UGRC statewide parcel layer. Ownership typology was derived from Salt Lake County Assessor ownership codes, which were manually reviewed and reclassified into a binary private/public typology applicable uniformly across the corridor.

**Conservation easements.** Easement coverage for each parcel was determined by spatial overlay against the National Conservation Easement Database (NCED), identifying parcels with recorded conservation easements regardless of ownership type.

**Water-related land use.** Utah's state water-related land use classification, maintained by UGRC, was overlaid to provide an additional regulatory context layer for parcels adjacent to or intersecting the river channel.

**Zoning crosswalk.** Municipal zoning data were obtained directly from the GIS departments of all twelve Salt Lake County municipalities whose jurisdictions intersect the study area. Each municipality maintains its own zoning schema with distinct class names, definitions, and hierarchies. A manual review and crosswalk was conducted to translate all twelve schemas into a single unified open-space-compatible classification, establishing a consistent typology for determining whether each parcel's zoning permits or encourages open-space-compatible uses. This crosswalk was developed in collaboration with a team of University of Utah Urban Planning graduate students.

**Geodatabase assembly.** All parcel features within the study area were cleaned and assembled into a geodatabase, with each parcel attributed on three binary dimensions: (1) zoned as open space or open-space-compatible; (2) protected by a recorded conservation easement; (3) publicly owned. The combination of these three fields enables prioritization of parcels that are privately owned, not yet under easement, and zoned compatibly — the primary acquisition targets for conservation organizations working in the corridor.

## Outputs

- Geodatabase of SLCo parcels within 1-mile Jordan River buffer, each coded on three dimensions: open-space zoning, conservation easement, public ownership
- Standardized crosswalk of zoning classifications from 12 SLCo municipalities to unified open-space-compatible typology
- Reclassified SLCo Assessor ownership typology (private/public binary)
- Map series: parcels by ownership/easement/zoning status; federal flood zone classification; Utah State water-related land use classification
- Final report and geodatabase delivered to Jordan River Commission

## My Role

This was a paid contract through Hippodameian. I led the research design in direct collaboration with Jordan River Commission Executive Director Laura Hanson, served as the sole GIS analyst throughout, and served as primary client liaison. I designed the three-dimensional parcel coding framework (zoning, easement, ownership), assembled and processed all spatial datasets, and performed all GIS analysis in ArcGIS Desktop 10.3.1. I led a team of University of Utah Urban Planning graduate students in the zoning crosswalk work — the most labor-intensive component of the project, requiring individual review of zoning ordinances and GIS data from twelve separate municipalities. I produced the final map series and delivered the report and geodatabase to the client.
