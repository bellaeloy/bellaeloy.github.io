+++
title = "Parametric Facade Study"
date = 2022-03-15
year = "2022"
role = "Computational designer"
location = "João Pessoa, PB"
summary = "A brise-soleil that changes its blade angle per floor. Grasshopper drives the angle from the sun path, and the result cuts the cooling load by a fifth."
cover = "/images/projects/parametric-facade-study.svg"
tools = ["Grasshopper", "Rhino 3D", "Ladybug", "Fabrication drawings"]
tags = ["parametric modeling", "facade", "architecture"]
placeholder = true
[[links]]
name = "Grasshopper definition"
icon = "fa-brands fa-github"
url = "https://github.com/bellaeloy"
[[links]]
name = "Grasshopper primer"
icon = "fa-solid fa-book"
url = "https://github.com/bellaeloy/grasshopper-primer"
+++

<!-- PLACEHOLDER: replace the text, the cover image and the links. -->

An office block faces west. A flat brise-soleil either blocks the view or lets
the afternoon sun in. This study removes that trade-off.

## Definition

Ladybug gives the sun vector for every hour of the year. The Grasshopper
definition sets one blade angle per floor. It picks the angle that blocks direct
sun after 14:00 and keeps the largest view cone toward the street.

The angle runs from 18° at the ground floor to 47° at the top floor. The change
is small enough that the facade still reads as one surface.

## Fabrication

The definition writes a cut list. Every blade uses the same extrusion. Only the
bracket angle changes, in steps of 1°. The contractor needs 30 bracket types for
1,240 blades.

## Result

The energy model shows a cooling load 21% below the flat brise-soleil, and a 34%
larger view area.
