---
layout: default
title: Shock Diffraction Problem
---

### Shock Diffraction Problem

**Related publication:** [Levý & May (2025)]({{ '/pages/publications/#compfluids' | relative_url }})

This example considers the diffraction of a shock wave over a backward-facing step, a classical benchmark for compressible flow solvers involving complex wave interactions and strongly anisotropic flow structures. In contrast to the previous test cases, the present problem combines geometric complexity with evolving shock patterns, vortical structures, and secondary wave interactions.

In the present setting, the mesh is adapted according to the magnitude of the gas velocity after each adaptation interval, with $\Delta t_A = 0.05$, $\mathrm{CFL} = 0.5$, and final time $T = 3.5$. When the total number of mesh elements is kept fixed throughout the simulation, the initial shock is resolved relatively well, but the resolution necessarily becomes less effective as the flow develops and additional structures appear. This highlights a limitation of using a fixed number of mesh elements for problems whose complexity changes substantially in time.

To address this issue, a simple strategy was introduced to dynamically adjust the number of mesh elements during the computation. The adjustment is based on the total area in which the shock sensor is active, so that the number of mesh elements increases when the shock-dominated region expands. The resulting simulations show that this approach provides a more appropriate distribution of resolution in the later stages of the flow and improves the representation of the developing wave pattern.

<div class="figure">
  <p class="figure-caption">
    <img src="{{ '/gifs/shockdiffraction.gif' | relative_url }}" class="framed-image" style="width: 500px;">
    <br>
    Simulation of the Mach 2 shock diffraction problem using the mesh-predictor approach. The number of mesh elements is adjusted dynamically according to the total area where the shock sensor is active, starting from 2,000 elements and increasing up to 9,600 as the shock-dominated region expands.
  </p>
</div>
