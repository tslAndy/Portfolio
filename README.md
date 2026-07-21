# Portfolio

List of my projects implemented in Unity or with Raylib.
Images are links to youtube with project showcase.

## Black Hole 
- Black hole simulation on Unity with Compute Shaders
- Gas disk is generated with Worley and Perlin noise
- Disk rendered with volumetric rendering

Repo: https://github.com/tslAndy/BlackHole

[![](https://img.youtube.com/vi/hWAEQB-2bAU/0.jpg)](https://www.youtube.com/watch?v=hWAEQB-2bAU)

## Boids
- Boids algorithm implementation on the GPU
- Raylib for rendering
- ILGPU for OpenCL usage (other backends such as CUDA can be used aswell) 

Repo: https://github.com/tslAndy/Boids

[![](https://img.youtube.com/vi/7xeWGgYISzI/0.jpg)](https://www.youtube.com/watch?v=7xeWGgYISzI)

## Warp Grid
- Simple warp grid implementation, nothing special

Repo: https://github.com/tslAndy/WarpGrid

[![](https://img.youtube.com/vi/UhpW3lMCEa0/0.jpg)](https://www.youtube.com/watch?v=UhpW3lMCEa0)

## Eulerian Fluid Simulation
- GPU based Eulerian Fluid simulation (ILGPU, OpenCL)
- Obstacles are supported

Repo: https://github.com/tslAndy/EulerianFluidSim

[![](https://img.youtube.com/vi/jZc8UK_pKiE/0.jpg)](https://www.youtube.com/watch?v=jZc8UK_pKiE)


## FLIP Simulation
- GPU based Fluid In Particle implementation
- Extended version of Eulerian simulation

Repo: https://github.com/tslAndy/FlipLiquidGPU

[![](https://img.youtube.com/vi/Vc5q7WPS4Dg/0.jpg)](https://www.youtube.com/watch?v=Vc5q7WPS4Dg)


## Slime Mold Simulation
- GPU based Slime Mold Simulation
- ILGPU, Raylib
  
Repo: https://github.com/tslAndy/SlimeSim

[![](https://img.youtube.com/vi/yl8N5paE2xg/0.jpg)](https://www.youtube.com/watch?v=yl8N5paE2xg)


## N-body Barnes-Hut
- Multithreaded CPU-implementation of Barnes Hut algorithm
- Implemented own unity-like job system (later was improved)
- Objects are sorted by multithreaded merge sort by their Morton codes for improving space locality of quadtree

Repo: https://github.com/tslAndy/Gravity

[![](https://img.youtube.com/vi/AqEuBSJd-jQ/0.jpg)](https://www.youtube.com/watch?v=AqEuBSJd-jQ)


## N-body GPU
- LOD-based simulation of N-body problem in Unity with Compute Shader
- Masses are transferred to textures
- Textures are blurred with Gaussian blur
- Several LOD (mipmaps) are created
- Only 3x3 square on each LOD-level used for gravity computation

Repo: https://github.com/tslAndy/GravComputeShader

[![](https://img.youtube.com/vi/a2gq912Lm9w/0.jpg)](https://www.youtube.com/watch?v=a2gq912Lm9w)


## Amanatides and Woo's fast Voxel Traversal
- Implementaion of voxel ray traversal in Compute Shaders

Repo: https://github.com/tslAndy/Voxelizer

[![](https://img.youtube.com/vi/Tbj0grPXC8U/0.jpg)](https://www.youtube.com/watch?v=Tbj0grPXC8U)

## Voxel Editor
- Simple voxel editor
- Binary Meshing (main goal of this project)

Repo: https://github.com/tslAndy/Voxel

[![](https://img.youtube.com/vi/qh7dsT_-7LY/0.jpg)](https://www.youtube.com/watch?v=qh7dsT_-7LY)


