---
layout: default
title: Shock-Vortex Interaction
---

## Shock-Vortex Interaction


This example considers a classical shock-vortex interaction problem for the Euler equations, in which a convected isentropic vortex passes through a stationary shock. The test case is particularly useful for assessing anisotropic mesh adaptation in the presence of strong discontinuities and evolving localized flow structures.

In the present setting, no mesh predictor was used and the transferred solution was not additionally limited after mesh adaptation. Despite this, the adaptive simulation remains stable and yields a sharp resolution of the main flow features. This is aided by the fact that the dominant shock is nearly stationary, making the case especially suitable for the immediate remeshing strategy.

The time step size is kept constant at $\Delta t = 0.005$, using a third-order three-stage diagonally implicit Runge-Kutta method and approximating polynomials of degree $p = 1$. The mesh is initially adapted according to the Mach number field given by the initial condition and is subsequently updated every two time steps using the anisotropic mesh adaptation algorithm. The adapted mesh is limited to at most 2,000 elements.

Compared with a static uniform coarse-mesh computation, the adaptive solution achieves a substantially sharper representation of the shock-vortex interaction while using fewer than one fifth of the elements required by the corresponding static reference mesh.

<!-- <img src="{{ '/gifs/shockvortex.gif' | relative_url }}" class="framed-image"> -->

<div class="figure">
  <p class="figure-caption">
    <img src="{{ '/gifs/shockvortex2.gif' | relative_url }}" class="framed-image" style="width: 400px;">
    <br>
    Simulation of the shock-vortex interaction. Comparison of results on uniform triangular mesh with 11,000 elements (top) and adaptive mesh with at most 2,000 elements (bottom). The mesh is refined automatically near the stationary shock and in the region affected by the passing vortex.
  </p>
</div>