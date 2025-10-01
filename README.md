# 2D Particle-based Fluid Simulation using WebGPU and WGSL's Compute Shaders
Crude implementation of 2d particle-based fluid simulation using WebGPU and WGSL's compute shaders.
Run live [demo](https://therenderman.github.io/WebGPU-2D-Compute-Fluid/) in your browser!

## Insight
I wrote this compact 2d fluid simulation so that I could learn how to write GPU programs (simulations and rendering programs) using WebGPU and WGSL's compute.
The fluid simulation algorithm implemented is pretty straightforward and it works by estimating pressure from the fluid particles' density field and relaxing the particle's position afterwards, thereby enforcing incompressibility.
Each step of the fluid algorithm is chunked into different WGSL's compute shaders and then computed pass by pass. 

The computation complexity of the fluid engine is 0(N)*(N), but can be furthered simplified to O(NxM) by using a spatial partitioning algorithm (where N = num. of particles and M = num. of grid cells.)
But currently, each particle is querying all other fluid particles to determine its neighbors.
Even for 5000 particles, *22,500,000* density relax computations are being processed per-frame (excluding other physics computations) and the simulation still runs in real-time.


