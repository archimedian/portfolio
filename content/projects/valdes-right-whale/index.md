---
title: "GIS Digitization of Historical Aerial Survey Data — Southern Right Whales, Península Valdés"
date: 2017-07-01
summary: "Collaboration with Ocean Alliance's Right Whale Program to digitize eight years of analog aerial survey sightings of Eubalaena australis into GIS, including a mileposted bathymetric centerline representing the whales' preferred coastal corridor around Golfo Nuevo, Península Valdés, and Golfo San José."
domain: "Conservation Science"
region: "Península Valdés, Patagonia, Argentina"
ecosystem: "Coastal marine; critical breeding and nursery habitat for Southern right whales (Eubalaena australis)"
methods:
  - "ArcGIS Desktop 10.5 for all GIS processing"
  - "Manual digitization of bathymetric contour centerline from Argentine nautical charts"
  - "Manual digitization of sightings data from paper field maps"
  - "Georeferencing of historical base-map scan"
  - "Geodatabase design and mileposting"
sector: "Academic"
era: "UU-GLSC"
featureimage: "images/projects/valdes-right-whale/feature.png"
roles:
  - "Project lead"
  - "GIS data model design and geodatabase development"
  - "Manual digitization (whale road centerline and 1997 sightings)"
  - "Historical base-map georeferencing"
  - "Volunteer GIS technician recruitment and coordination"
  - "Digitization protocol and training tutorial development"
---

## Overview

This project was a collaboration with Dr. Victoria Rowntree, Director of the Ocean Alliance Right Whale Program, to rescue and formalize thirty-three years of historical aerial survey data on Southern right whales (*Eubalaena australis*) at Península Valdés, Argentina. The surveys, conducted annually since 1971, recorded whale sightings on paper field maps through the 2004 field season using distance along the coastline as the positional reference. When the program transitioned to electronic data collection after 2004, these analog records remained outside any GIS, inaccessible to spatial analysis.

The project involved designing a data model and workflow for converting the paper records into a queryable geodatabase, building the core spatial framework (a mileposted centerline representing the whales' preferred bathymetric corridor), georeferencing the historical base-map used in the surveys, digitizing the 1997 sightings dataset as proof of concept, and recruiting and training volunteer GIS technicians to carry the digitization forward across the remaining survey years.

## Region & Ecosystem

Península Valdés is a UNESCO World Heritage Site on the Atlantic coast of Patagonia, Argentina, recognized in part for its importance as a breeding and nursery ground for the Southern right whale. The peninsula's two sheltered gulfs — Golfo Nuevo to the south and Golfo San José to the north — provide calm, shallow waters where mother-calf pairs congregate from June through December each year. According to Dr. Rowan the 5–10 fathom bathymetric band along the gulf coastlines represents the depth range most consistently used by nursing mothers (hypothesized to minimize predation risk to young calves from orcas), and we referred to this corridor informally as the "whale road."

The aerial survey program operated out of the peninsula from 1971 onward, flying systematic transects to count and record the positions of whales relative to the coastline. Because perpendicular distance from the shore was not recorded — only distance along the coastline — all sightings are positioned on the centerline of the whale road rather than at their true locations, and positional accuracy is inherently limited compared to GPS-based methods. This constraint was a central consideration in the data model design.

## Methods

**Data model and workflow design.** The first deliverable was a strategic plan establishing the data model, file structure, and digitization workflow for the full 1971–2004 archive. Key design decisions included how to represent positional uncertainty, how to structure the annual sightings tables for comparability across years, and how to mileposts the centerline to enable position-along-coastline values from the field maps to be translated into point features.

**Whale road centerline.** The core spatial framework for the dataset is a mileposted polyline representing the 5–10 fathom bathymetric contour around Golfo Nuevo, Península Valdés, and Golfo San José — the depth band consistently used by mother-calf pairs. This centerline was manually digitized in ArcGIS Desktop 10.5 from Argentine nautical charts supplied by Dr. Rowntree, which served as both the digitization source and the base layer for sightings data entry. The centerline was mileposted at regular intervals to provide the reference framework for translating paper-recorded positions into GIS point features.

**Base-map georeferencing.** The historical base-map used during the survey years was georeferenced in ArcGIS, establishing a spatial reference for the paper field maps and enabling consistent interpretation of recorded sighting positions across years.

**Sightings digitization.** The 1997 survey year (selected by Dr. Rowntree) was digitized as a proof-of-concept implementation of the workflow, placing individual sightings as point features along the mileposted centerline based on the along-coastline positions recorded in the field. This dataset demonstrated the end-to-end process and served as a template and quality-control reference for subsequent years.

**Volunteer recruitment and training.** To make completion of the remaining survey years feasible, I recruited an undergraduate GIS technician from my University of Utah student pool and a graduate-student volunteer through the Society for Conservation GIS listserv. I developed a digitization protocol and supervised production of a step-by-step training tutorial to standardize the workflow across technicians and ensure consistent output quality.

## Outputs

- Strategic plan: data model, file structure, and digitization workflow for the 1971–2004 archive
- Geodatabase with mileposted bathymetric centerline ("whale road") covering Golfo Nuevo, Península Valdés, and Golfo San José
- Georeferenced scan of the historical base-map used during aerial surveys
- Digitized 1997 sightings dataset (proof-of-concept implementation)
- Recruited volunteer GIS technician team (1 undergraduate, 1 graduate student)
- Digitization protocol and training tutorial for volunteer technicians

## My Role

I led the project from initial scoping through delivery, working pro bono. Working directly with Dr. Rowntree, I designed the GIS data model and digitization workflow, built and mileposted the whale road centerline geodatabase, georeferenced the historical base-map, and supervised digitization of the 1997 sightings dataset. I recruited and coordinated the volunteer technician team and developed the protocol and tutorial used to train them. All GIS work was performed in ArcGIS Desktop 10.5.
