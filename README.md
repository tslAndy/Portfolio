# Portfolio

List of my projects implemented in Unity or with Raylib.
Images are links to youtube with project showcase.

# GPU stuff

## Black Hole 
- Black hole simulation on Unity with Compute Shaders
- Gas disk is generated with Worley and Perlin noise
- Disk rendered with volumetric rendering

Repo: https://github.com/tslAndy/BlackHole

[![](https://img.youtube.com/vi/hWAEQB-2bAU/0.jpg)](https://www.youtube.com/watch?v=hWAEQB-2bAU)

--------------------------------------------------------------------------------------------------------------------------------------------

## Boids
- Boids algorithm implementation on the GPU
- Raylib for rendering
- ILGPU for OpenCL usage (other backends such as CUDA can be used aswell) 

Repo: https://github.com/tslAndy/Boids

[![](https://img.youtube.com/vi/7xeWGgYISzI/0.jpg)](https://www.youtube.com/watch?v=7xeWGgYISzI)

--------------------------------------------------------------------------------------------------------------------------------------------

## Eulerian Fluid Simulation
- GPU based Eulerian Fluid simulation (ILGPU, OpenCL)
- Obstacles are supported

Repo: https://github.com/tslAndy/EulerianFluidSim

[![](https://img.youtube.com/vi/jZc8UK_pKiE/0.jpg)](https://www.youtube.com/watch?v=jZc8UK_pKiE)

--------------------------------------------------------------------------------------------------------------------------------------------

## FLIP Simulation
- GPU based Fluid In Particle implementation
- Extended version of Eulerian simulation

Repo: https://github.com/tslAndy/FlipLiquidGPU

[![](https://img.youtube.com/vi/Vc5q7WPS4Dg/0.jpg)](https://www.youtube.com/watch?v=Vc5q7WPS4Dg)

--------------------------------------------------------------------------------------------------------------------------------------------

## Slime Mold Simulation
- GPU based Slime Mold Simulation
- ILGPU, Raylib
  
Repo: https://github.com/tslAndy/SlimeSim

[![](https://img.youtube.com/vi/yl8N5paE2xg/0.jpg)](https://www.youtube.com/watch?v=yl8N5paE2xg)

--------------------------------------------------------------------------------------------------------------------------------------------

## N-body GPU
- LOD-based simulation of N-body problem in Unity with Compute Shader
- Masses are transferred to textures
- Textures are blurred with Gaussian blur
- Several LOD (mipmaps) are created
- Only 3x3 square on each LOD-level used for gravity computation

Repo: https://github.com/tslAndy/GravComputeShader

[![](https://img.youtube.com/vi/a2gq912Lm9w/0.jpg)](https://www.youtube.com/watch?v=a2gq912Lm9w)

--------------------------------------------------------------------------------------------------------------------------------------------

## Amanatides and Woo's fast Voxel Traversal
- Implementaion of voxel ray traversal in Compute Shaders

Repo: https://github.com/tslAndy/Voxelizer

[![](https://img.youtube.com/vi/Tbj0grPXC8U/0.jpg)](https://www.youtube.com/watch?v=Tbj0grPXC8U)

--------------------------------------------------------------------------------------------------------------------------------------------

## Voxel Editor
- Simple voxel editor
- Binary Meshing (main goal of this project)

Repo: https://github.com/tslAndy/Voxel

[![](https://img.youtube.com/vi/qh7dsT_-7LY/0.jpg)](https://www.youtube.com/watch?v=qh7dsT_-7LY)

--------------------------------------------------------------------------------------------------------------------------------------------

## Raymarching
- SDF Raymarching with Unity and Compute Shaders
- For learining purposes shape operations (union, difference, intersection, mix) are implemented through bytecode.
- In the inspector created tree-like data structure (expression tree), after it get converted to bytecode which get transferred to GPU
- By using this approach there is no need to change shader code when complex hierarchies of operations is created (for example merge some objects and exclude other)

Repo: https://github.com/tslAndy/Raymarch

--------------------------------------------------------------------------------------------------------------------------------------------

# Physics stuff

## Verlet Integration
- Rope implemented with verlet integration

Repo: https://github.com/tslAndy/Verlet

--------------------------------------------------------------------------------------------------------------------------------------------

## Physics
- Simple physics engine with different colliders support
- Concave polygons support
- Quickhull support

Repo: https://github.com/tslAndy/Physics

--------------------------------------------------------------------------------------------------------------------------------------------

## N-body Barnes-Hut
- Multithreaded CPU-implementation of Barnes Hut algorithm
- Implemented own unity-like job system (later was improved)
- Objects are sorted by multithreaded merge sort by their Morton codes for improving space locality of quadtree

Repo: https://github.com/tslAndy/Gravity

[![](https://img.youtube.com/vi/AqEuBSJd-jQ/0.jpg)](https://www.youtube.com/watch?v=AqEuBSJd-jQ)

--------------------------------------------------------------------------------------------------------------------------------------------

## Soft Body 
- Simple soft body implementation

Repo: https://github.com/tslAndy/SoftBody

--------------------------------------------------------------------------------------------------------------------------------------------

# Other

## Marching Squares
- Metaballs implemented with marching squares
- Triangles for rendering are generated in multithread
- For reducing trigs amount Binary Meshing is used

Repo: https://github.com/tslAndy/MarchingSquares

--------------------------------------------------------------------------------------------------------------------------------------------

## Warp Grid
- Simple warp grid implementation, nothing special

Repo: https://github.com/tslAndy/WarpGrid

[![](https://img.youtube.com/vi/UhpW3lMCEa0/0.jpg)](https://www.youtube.com/watch?v=UhpW3lMCEa0)

--------------------------------------------------------------------------------------------------------------------------------------------

## Software Raterizer
- Simple Software Rasterizer
- Occlusion & Frustum Culling
- Hi-Z buffer optimization
- Multithreaded rendering

Repo: https://github.com/tslAndy/RastRefactor

--------------------------------------------------------------------------------------------------------------------------------------------

## Durdoom
- Advanced implementation of Wolfenstein-like raycaster
- Sloped blocks support
- Transparent textures
- Player camera height changing

Repo: https://github.com/tslAndy/Durdoom

--------------------------------------------------------------------------------------------------------------------------------------------

## Survivors
- Survivors-like project implemented in Arch ECS
- Main goal of project was to learn Entity Component System paradigm
- Learned basics of Autofac DI

https://github.com/tslAndy/Survivors

--------------------------------------------------------------------------------------------------------------------------------------------

## Sand 1
- First implementation of Noita-like falling sand

Repo: https://github.com/tslAndy/OldSand

--------------------------------------------------------------------------------------------------------------------------------------------

## Sand 2
- Improved implementation
- Chunked multithreaded update
- Dirty rect for excluding empty space in chunks
- Activity zones (if particles in chunk are idle, it will be excluded from update)
- Simple save system with Memory Pack

Repo: https://github.com/tslAndy/Sand

--------------------------------------------------------------------------------------------------------------------------------------------

## Circle IK
- 2D Inverse Kinematics with circles

Repo: https://github.com/tslAndy/CircleIK

--------------------------------------------------------------------------------------------------------------------------------------------

## FABRIK IK
- 2D FABRIK IK with angle limitation

Repo: https://github.com/tslAndy/FabrikIK

--------------------------------------------------------------------------------------------------------------------------------------------

## Dual Grid 
- Advanced Dual Grid implementation in Unity
- While standard dual grid support 2 types of tiles, current implementation allow to use as mych tiles as necessary (all on the same tilemap)
- Algorithm use 3 additional tilemaps for selecting corresponding border tiles, but interaction only with main one (border tiles are selected automatically)

Repo: https://github.com/tslAndy/Dual-Grid

--------------------------------------------------------------------------------------------------------------------------------------------

## Voronoi
- N^2 voronoi implementation

Repo: https://github.com/tslAndy/Voronoi

--------------------------------------------------------------------------------------------------------------------------------------------

# Trees

## L-system trees
Repo: https://github.com/tslAndy/LSystemTree

--------------------------------------------------------------------------------------------------------------------------------------------

## Circle Trees
Repo: https://github.com/tslAndy/CircleTree

--------------------------------------------------------------------------------------------------------------------------------------------

## Fractal Trees
Repo: https://github.com/tslAndy/FractalTree

--------------------------------------------------------------------------------------------------------------------------------------------

## Colonization Tree
Repo: https://github.com/tslAndy/ColonizationTree

--------------------------------------------------------------------------------------------------------------------------------------------

## Transport Tree
Repo: https://github.com/tslAndy/TransportTree

--------------------------------------------------------------------------------------------------------------------------------------------


# Data structures / algorithms

## A*
- Implementation of several A* algorithms
- Basic A*
- JPS
- Cached JPS (improved complexity from original O(N^2) to O(n))
- LPA*
- D* Lite
- Binary Heap (4-d heap) 

Repo: https://github.com/tslAndy/AStar

--------------------------------------------------------------------------------------------------------------------------------------------

## Job System
- Basic implementation of Unity-like job system
- IJob / IJobParallelFor are implemented by using input / output degree (dependencies)
- ThreadPool is used for running tasks 
- Two types of allocators, memory arena and pool

Repo: https://github.com/tslAndy/JobSystem

--------------------------------------------------------------------------------------------------------------------------------------------

## Bitmap Roaring
- Implementation of bitmap roaring data structure

Repo: https://github.com/tslAndy/BitmapRoaring

--------------------------------------------------------------------------------------------------------------------------------------------

