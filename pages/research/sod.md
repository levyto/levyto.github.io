---
layout: default
title: Sod's Shock Tube Problem
---

### Sod's Shock Tube Problem

#### Initial mesh

<img src="{{ '/figs/sod/sod1.png' | relative_url }}" class="framed-image">

#### After first initial adaptation

<img src="{{ '/figs/sod/sod2.png' | relative_url }}" class="framed-image">

#### After predictor iteration adaptation

<img src="{{ '/figs/sod/sod3.png' | relative_url }}" class="framed-image">

#### Run

<img src="{{ '/gifs/sod.gif' | relative_url }}" class="framed-image">

<!-- ffmpeg -framerate 12 -start_number 1 -i %d.png -vf "palettegen" palette.png -->
<!-- ffmpeg -framerate 12 -i %d.png -i palette.png -lavfi "paletteuse" animation.gif -->