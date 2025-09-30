# 2D Particle-based Fluid Simulation using WebGPU and WGSL's Compute Shaders
Crude implementation of 2d particle-based fluid simulation using WebGPU and WGSL's compute shaders.
Run live [demo](https://therenderman.github.io/WebGPU-2D-Compute-Fluid/) in your browser!

## Insight
I wrote this compact 2d fluid simulation so that I could learn how to write GPU programs (simulations and rendering programs) using WebGPU and WGSL's compute.
The fluid simulation algorithm implemented is pretty straightforward and it works by estimating pressure from the fluid particles' density field and relaxing the particle's position afterwards, thereby enforcing incompressibility.
Each step of the fluid algorithm is chunked into different WGSL's compute shaders and then computed pass by pass. 

## Disclaimer!
This is entirely a learning project, so the implementation may contain some redundancies or bad practices. The project is nowhere near R&D and never aimed to be, but it just serves as a major milestone in my learning experience of the WebGPU API and WGSL.
