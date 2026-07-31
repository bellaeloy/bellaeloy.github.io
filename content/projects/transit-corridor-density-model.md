+++
title = "Transit Corridor Density Model"
date = 2025-04-18
year = "2025"
role = "Urban designer"
location = "Campina Grande, PB"
summary = "A parametric model that tests density scenarios along a bus rapid transit corridor and scores each one on walk distance, shade and daylight."
cover = "/images/projects/transit-corridor-density-model.svg"
tools = ["Grasshopper", "Rhino 3D", "QGIS", "Python"]
tags = ["parametric modeling", "urban design", "mobility"]
featured = true
placeholder = true
[[links]]
name = "Case study (PDF)"
icon = "fa-solid fa-file-pdf"
url = "#"
[[links]]
name = "Model repository"
icon = "fa-brands fa-github"
url = "https://github.com/bellaeloy"
+++

<!-- PLACEHOLDER: replace the text, the cover image and the links. -->

The city plans a bus rapid transit corridor. The plan sets one density rule for
the whole corridor. This project asks a different question: what happens if the
rule changes block by block?

## The model

A Grasshopper definition reads the lot geometry from QGIS. It then builds
massing for each lot from four inputs: floor area ratio, setback, height limit
and ground floor use. The definition writes every scenario to a CSV file.

## The scores

A Python script scores each scenario on three measures:

- Walk distance from each home to the nearest station.
- Hours of shade on the sidewalk at 15:00 in January.
- Daylight factor in the worst apartment of each block.

## The result

Three scenarios beat the single-rule plan on all three measures. The best one
puts the tallest blocks 200 m from the stations, not next to them. That keeps
the sidewalk in shade and keeps the walk under five minutes.
