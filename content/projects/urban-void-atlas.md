+++
title = "Urban Void Atlas"
date = 2023-11-07
year = "2023"
role = "Researcher"
location = "Master's research"
summary = "A map of every vacant lot in a mid-size Brazilian city, with an index that ranks each one for public reuse."
cover = "/images/projects/urban-void-atlas.svg"
tools = ["QGIS", "Python", "PostGIS", "Illustrator"]
tags = ["research", "gis", "urban development"]
placeholder = true
[[links]]
name = "Dissertation (PDF)"
icon = "fa-solid fa-file-pdf"
url = "#"
[[links]]
name = "Data and notebooks"
icon = "fa-brands fa-github"
url = "https://github.com/bellaeloy"
+++

<!-- PLACEHOLDER: replace the text, the cover image and the links. -->

This is the core of my master's research in urban development. The city has no
list of its vacant lots. Without the list, no reuse policy can start.

## Method

The atlas joins three sources:

- The municipal cadastre, for lot boundaries and ownership.
- Satellite imagery from 2015 to 2023, for the built footprint.
- Property tax records, for the years of debt.

A Python pipeline flags a lot as vacant when the footprint stays under 5% for
three years in a row. The pipeline found 4,180 vacant lots. That is 6.3% of the
urban area.

## The reuse index

Each lot gets a score from four weights: distance to a bus stop, distance to a
school, the size of the lot and the years of tax debt. A high score marks a lot
that the city can take and reuse at low cost.

## Use

The city planning department now uses the atlas as the base layer for its social
housing program.
