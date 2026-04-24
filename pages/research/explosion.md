---
layout: default
title: Explosion Problem
---

### Explosion Problem

**Related publication:** [Levý & May (2025)]({{ '/pages/publications/#compfluids' | relative_url }})

This example considers the classical Explosion problem for the Euler equations, which can be interpreted as a radially symmetric counterpart of 1D Sod’s shock tube problem. A high-density, high-pressure state is initially prescribed inside a circular region, generating an expanding wave pattern with a shock wave, a contact discontinuity, and a rarefaction wave. The test case is particularly useful for assessing the developed methodology in the presence of nonplanar shock structures.

Due to symmetry, the computation is performed only on one quarter of the original domain, namely $\Omega = [0,1]^2$. In the present setting, the example is used to demonstrate the behaviour of the mesh-predictor approach for radially propagating flow features. As the shock and other wave structures expand outward, the adapted mesh must remain consistent with the evolving solution while keeping the mesh within a prescribed complexity limit of 4,000 elements.

The computation is carried out using polynomial degree $p = 2$, a variable time step with $\mathrm{CFL}=0.8$, and a mesh adaptation limit of 4,000 elements up to the final time $T = 0.25$. Both the Backward Euler method and the third-order three-stage diagonally implicit Runge–Kutta method are considered, while the mesh prediction is based on Backward Euler with an adaptation interval $\Delta t_A = 0.005$.

The resulting adapted meshes show that the mesh-predictor strategy successfully follows the expanding radial wave pattern. The artificial viscosity is concentrated mainly near the shock wave, while the limiting of the solution transfer procedure is likewise active primarily in the regions requiring stabilization. 

> The panels on the figures below correspond to:
> - *Top left:*  computational mesh 
> - *Top right:*  density field
> - *Bottom left:*  artificial viscosity field
> - *Bottom right:*  elements where the solution transfer procedure is limited. 

<div class="figure">
  <p class="figure-caption">
    <img src="{{ '/figs/explosion/explosion1.png' | relative_url }}" class="framed-image" style="width: 400px;">
    <br>
    Initial condition evaluated on the initial structured mesh with 512 elements based on which the first initial adaptation is performed.
  </p>
</div>

<div class="figure">
  <p class="figure-caption">
    <img src="{{ '/figs/explosion/explosion2.png' | relative_url }}" class="framed-image" style="width: 400px;">
    <br>
    Initial condition projected onto the initially adapted mesh obtained from the original coarse mesh. The adapted mesh has 4,000 elements and is refined near the initial discontinuity and serves as input to the first mesh-predictor iteration.
  </p>
</div>

<div class="figure">
  <p class="figure-caption">
    <img src="{{ '/figs/explosion/explosion3.png' | relative_url }}" class="framed-image" style="width: 400px;">
    <br>
    Initial condition evaluated on the mesh resulting from the first mesh-predictor step, illustrating the beginning of predictor-based mesh evolution.
  </p>
</div>

<div class="figure">
  <p class="figure-caption">
    <img src="{{ '/gifs/explosion.gif' | relative_url }}" class="framed-image" style="width: 400px;">
    <br>
    Simulation of the explosion problem using the mesh-predictor approach. The mesh is adapted every adaptation interval $\Delta t_A = 0.005$ based on the predictor density field, with a maximum of 4,000 elements. 
  </p>
</div>
