# Portfolio

Hello! Thank you for checking out my portfolio. Below the TLDR list there are more specific descriptions of projects and videos. Projects are implemented in Unity or Raylib. 



TLDR:

- **GPU**
  - [Raytracing](https://github.com/tslAndy/Raytrace)
  - [Radiance Cascades](https://github.com/tslAndy/Cascades)
  - [Volumetric Rendering](https://github.com/tslAndy/Volumetric)
  - [Black Hole](https://github.com/tslAndy/BlackHole)
  - [Aurora Borealis](https://github.com/tslAndy/Aurora)
  - [Atmosphere](https://github.com/tslAndy/Atmosphere)
  - [Boids](https://github.com/tslAndy/Boids)
  - [Particle Life](https://github.com/tslAndy/ParticleLife)
  - [Eulerian Fluid](https://github.com/tslAndy/EulerianFluidSim)
  - [FLIP Fluid](https://github.com/tslAndy/FlipLiquidGPU)
  - [Slime Mold](https://github.com/tslAndy/SlimeSim)
  - [N-Body LOD](https://github.com/tslAndy/GravComputeShader)
  - [Voxel Ray Traversal](https://github.com/tslAndy/Voxelizer)
  - [Voxel Editor](https://github.com/tslAndy/Voxel)
  - [Raymarching](https://github.com/tslAndy/Raymarch)
  - [Cell Shading](https://github.com/tslAndy/Fur)

- **Physics**
  - [Verlet Integration](https://github.com/tslAndy/Verlet)
  - [2D physics engine](https://github.com/tslAndy/Physics)
  - [GJK + EPA](https://github.com/tslAndy/GJK)
  - [Soft Body](https://github.com/tslAndy/SoftBody)
  - [N-body Barnes-Hut](https://github.com/tslAndy/Gravity)

- **Uncategorized**
  - [Timeroll](https://github.com/tslAndy/Timeroll)
  - [Marching Squares](https://github.com/tslAndy/MarchingSquares) 
  - [Warp Grid](https://github.com/tslAndy/WarpGrid)
  - [Bridge Simulator](https://github.com/tslAndy/Bridge)
  - [Software Rasterizer](https://github.com/tslAndy/RastRefactor)
  - [Wolfenstein-like Raycaster](https://github.com/tslAndy/Durdoom) 
  - [ECS Survivors-like game](https://github.com/tslAndy/Survivors) 
  - [Falling Sand Game (old version)](https://github.com/tslAndy/OldSand)
  - [Falling Sand Game (new version)](https://github.com/tslAndy/Sand)
  - [Circle Inverse Kinematics](https://github.com/tslAndy/CircleIK) 
  - [FABRIK Inverse Kinematics](https://github.com/tslAndy/FabrikIK)
  - [Multilayered Dual Grid](https://github.com/tslAndy/Dual-Grid)
  - [Voronoi generator with Poisson disc sampling](https://github.com/tslAndy/Voronoi)
  - [Bezier Curves drawing](https://github.com/tslAndy/Bezier)

- **Trees** 
  - [L-System trees](https://github.com/tslAndy/LSystemTree) 
  - [Circle trees](https://github.com/tslAndy/CircleTree)
  - [Fractal trees](https://github.com/tslAndy/FractalTree)
  - [Colonization tree](https://github.com/tslAndy/ColonizationTree) 
  - [Transport trees](https://github.com/tslAndy/TransportTree)

- **DSA** 
  - [A* family algorithms](https://github.com/tslAndy/AStar)
  - [Unity-like job system](https://github.com/tslAndy/JobSystem) 
  - [Bitmap Roaring](https://github.com/tslAndy/BitmapRoaring)


# GPU stuff

## Ray tracing
**Repo**: https://github.com/tslAndy/Raytrace
- Basic raytracing in Unity Compute Shaders
- Two types of BVH
  - BVH containing objects boxes, built with Morton codes
  - BVH for model triangles, built with optimized SAH
- Two types of Next Event Estimation
  - Basic version, MIS. Trace additional ray to random triangle.
  - More accurate version with RIS. Creates several possible rays, then select one by it's weight.
- Shared between objects for reducing amount of data transferred to GPU 
  - Meshes
  - Materials
  - BVH for triangles
- Universal simple for packing custom material data (max 60 bytes). On shader side should be unpacked.


![image info](./Images/Raytrace.png)

## Radiance Cascades
**Repo**: https://github.com/tslAndy/Cascades
- Radiance Cascades implementation in Compute Shaders
- Raycasting is sped up with GPU built SDF (log N time) 
- Basic version use preaveraging (only two cascade textures implemented as arrays with size 1/4 of original texture)
- Another version use direction first layout and preaveraging (two cascades, full size and quarter size). On my GPU it's slower than original version (may be because my GPU is integrated)
- Increased raycasting radius used as bilinear fix. It didn't allow to fully mitigate circles, but looks much better.


Video:

[![](./Images/Cascades.png)](https://www.youtube.com/watch?v=R0g4GFdLCNY)

## Volumetric Rendering
**Repo**: https://github.com/tslAndy/Volumetric
- Basic volumetric rendering with Compute Shaders

Video:

[![](https://img.youtube.com/vi/nXv9PXc2T7M/0.jpg)](https://www.youtube.com/watch?v=nXv9PXc2T7M)

## Black Hole
**Repo**: https://github.com/tslAndy/BlackHole
- Black hole simulation on Unity with Compute Shaders
- Gas disk is generated with Worley and Perlin noise
- Disk rendered with volumetric rendering

Video:

[![](./Images/BlackHole.png)](https://www.youtube.com/watch?v=hWAEQB-2bAU)

## Aurora shader
**Repo**: https://github.com/tslAndy/Aurora
- Simple aurora borealis rendering with Perlin noise and volumetric raymarching

Video:

[![](./Images/Aurora.png)](https://www.youtube.com/watch?v=2jf9wXUALuQ)

## Atmosphere Rendering
**Repo**: https://github.com/tslAndy/Atmosphere
- Atmosphere rendering
- LUT for acceleration

Video:

[![](./Images/Atmosphere.png)](https://www.youtube.com/watch?v=u2EjnY8i9Ms)

## Boids
**Repo**: https://github.com/tslAndy/Boids
- Boids algorithm implementation on the GPU
- Raylib for rendering
- ILGPU for OpenCL usage (other backends such as CUDA can be used aswell) 

Video:

[![](./Images/Boids.png)](https://www.youtube.com/watch?v=7xeWGgYISzI)

## Particle Life
**Repo**: https://github.com/tslAndy/ParticleLife
- Same backend as in boids algorithm

![image info](./Images/Life.png) 

## Eulerian Fluid Simulation
**Repo**: https://github.com/tslAndy/EulerianFluidSim
- GPU based Eulerian Fluid simulation (ILGPU, OpenCL)
- Obstacles are supported

Video:

[![](./Images/Eulerian.png)](https://www.youtube.com/watch?v=jZc8UK_pKiE)

## FLIP Simulation
**Repo**: https://github.com/tslAndy/FlipLiquidGPU
- GPU based Fluid In Particle implementation
- Extended version of Eulerian simulation

Video:

[![](./Images/FLIP.png)](https://www.youtube.com/watch?v=Vc5q7WPS4Dg)

## Slime Mold Simulation
**Repo**: https://github.com/tslAndy/SlimeSim
- GPU based Slime Mold Simulation
- ILGPU, Raylib

Video:

[![](./Images/Slime.png)](https://www.youtube.com/watch?v=yl8N5paE2xg)

## N-body GPU
**Repo**: https://github.com/tslAndy/GravComputeShader
- LOD-based simulation of N-body problem in Unity with Compute Shader
- Masses are transferred to textures
- Textures are blurred with Gaussian blur
- Several LOD (mipmaps) are created
- Only 3x3 square on each LOD-level used for gravity computation

Video:

[![](./Images/GravCompute.png)](https://www.youtube.com/watch?v=a2gq912Lm9w)

## Amanatides and Woo's fast Voxel Traversal
**Repo**: https://github.com/tslAndy/Voxelizer
- Implementaion of voxel ray traversal in Compute Shaders

Video:

[![](./Images/Amantides.png)](https://www.youtube.com/watch?v=Tbj0grPXC8U)

## Voxel Editor
**Repo**: https://github.com/tslAndy/Voxel
- Simple voxel editor
- Binary Meshing (main goal of this project)

Video:

[![](./Images/VoxelEditor.png)](https://www.youtube.com/watch?v=qh7dsT_-7LY)

## Raymarching
**Repo**: https://github.com/tslAndy/Raymarch

- SDF Raymarching with Unity and Compute Shaders
- For learining purposes shape operations (union, difference, intersection, mix) are implemented through bytecode.
- In the inspector created tree-like data structure (expression tree), after it get converted to bytecode which get transferred to GPU
- By using this approach there is no need to change shader code when complex hierarchies of operations is created (for example merge some objects and exclude other)


Video:

[![](./Images/Raymarch.png)](https://www.youtube.com/watch?v=TwwSHPYmgD8)

## Cell Shading
**Repo**: https://github.com/tslAndy/Fur
- Simple cell shading in Unity URP Shader Graph

Video:

[![](./Images/CellShading.png)](https://www.youtube.com/watch?v=M_2xZsWtEO8)

# Physics stuff

## Verlet Integration
**Repo**: https://github.com/tslAndy/Verlet
- Rope implemented with verlet integration


Video:

[![](./Images/Verlet.png)](https://www.youtube.com/watch?v=8q6YdGlpN7Q)

## Physics
**Repo**: https://github.com/tslAndy/Physics
- Simple physics engine with different colliders support
- Concave polygons support
- Quickhull support


Video:

[![](./Images/Physics.png)](https://www.youtube.com/watch?v=Y52Ldz2PnCw)

## N-body Barnes-Hut
**Repo**: https://github.com/tslAndy/Gravity
- Multithreaded CPU-implementation of Barnes Hut algorithm
- Implemented own unity-like job system (later was improved)
- Objects are sorted by multithreaded merge sort by their Morton codes for improving space locality of quadtree


Video:

[![](./Images/Gravity.png)](https://www.youtube.com/watch?v=AqEuBSJd-jQ)

## Soft Body
**Repo**: https://github.com/tslAndy/SoftBody
- Simple soft body implementation


Video:

[![](./Images/SoftBody.png)](https://www.youtube.com/watch?v=yeHUV0iDEpo)

## 2D GJK + EPA
**Repo**: https://github.com/tslAndy/GJK
- Implementation of GJK and EPA for collision detection and resolving


Video:

[![](./Images/GJK.png)](https://www.youtube.com/wat

# Other

## Timeroll
**Repo**: https://github.com/tslAndy/Timeroll
- Time rewinding system in Unity
- Three types of operations are supported
  - Recording
  - Rewind Soft (rewinding back without snapshots deletion)
  - Rewind Hard (rewinding back with snapshots deletion)
  - Replay (play forward from current snapshot)
- Continuous
  - Continuous snapshots are taken with user-defined delay and limited in amount. Snapshots are stored in ring buffer, so overwriting old entries is easy.
  - Between snapshots used interpolation.
  - Interpolation, taking snapshot and restoring state are defined by user (in that way system is more flexible)
- Discrete
  - User register event snapshot
  - Events are handled by Undo/Redo operations (also defined by user)


Video:

[![](https://img.youtube.com/vi/ZPSvGTJPMiw/0.jpg)](https://www.youtube.com/watch?v=ZPSvGTJPMiw)

## Marching Squares
**Repo**: https://github.com/tslAndy/MarchingSquares
- Metaballs implemented with marching squares
- Triangles for rendering are generated in multithread
- For reducing trigs amount Binary Meshing is used


Video:

[![](./Images/MarchingSquares.png)](https://www.youtube.com/watch?v=-OTAZTXqLnw)

## Warp Grid
**Repo**: https://github.com/tslAndy/WarpGrid
- Simple warp grid implementation, nothing special


Video:

[![](./Images/WarpGrid.png)](https://www.youtube.com/watch?v=UhpW3lMCEa0)

## Bridge
**Repo**: https://github.com/tslAndy/Bridge
- Simple Bridge game


Video:

[![](./Images/Bridge.png)](https://www.youtube.com/watch?v=3AqXc3j6b8Y)

## Software Rasterizer
**Repo**: https://github.com/tslAndy/RastRefactor

- Simple Software Rasterizer
- Occlusion & Frustum Culling
- Hi-Z buffer optimization
- Multithreaded rendering


Video:

[![](./Images/Rasterizer.png)](https://www.youtube.com/watch?v=fpddzHvOMzo)

## Durdoom
**Repo**: https://github.com/tslAndy/Durdoom

- Advanced implementation of Wolfenstein-like raycaster
- Sloped blocks support
- Transparent textures
- Player camera height changing


Video:

[![](./Images/Doom.png)](https://www.youtube.com/watch?v=y2-YEY0J8js)

## Survivors
**Repo**: https://github.com/tslAndy/Survivors

- Survivors-like project implemented in Arch ECS
- Main goal of project was to learn Entity Component System paradigm
- Learned basics of Autofac DI


Video:

[![](./Images/Survivors.png)](https://www.youtube.com/watch?v=UZB8wT53WtA)

## Sand 1
**Repo**: https://github.com/tslAndy/OldSand
- First implementation of Noita-like falling sand


Video:

[![](https://img.youtube.com/vi/3iZQmG9DUSc/0.jpg)](https://www.youtube.com/watch?v=3iZQmG9DUSc)

## Sand 2
**Repo**: https://github.com/tslAndy/Sand
- Improved implementation
- Chunked multithreaded update
- Dirty rect for excluding empty space in chunks
- Activity zones (if particles in chunk are idle, it will be excluded from update)
- Simple save system with Memory Pack


Video:

[![](./Images/Sand.png)](https://www.youtube.com/watch?v=ufNKMC0gQvc)

## Circle IK
**Repo**: https://github.com/tslAndy/CircleIK
- 2D Inverse Kinematics with circles


Video:

[![](./Images/CircleIK.png)](https://www.youtube.com/watch?v=HTjGrW2Etiw)

## FABRIK IK
**Repo**: https://github.com/tslAndy/FabrikIK
- 2D FABRIK IK with angle limitation


Video:

[![](./Images/FabrikIK.png)](https://www.youtube.com/watch?v=towby8B63UE)

## Dual Grid
**Repo**: https://github.com/tslAndy/Dual-Grid

- Advanced Dual Grid implementation in Unity
- While standard dual grid support 2 types of tiles, current implementation allow to use as much tiles as necessary (all on the same tilemap)
- Algorithm use 3 additional tilemaps for selecting corresponding border tiles, but interaction only with main one (border tiles are selected automatically)


Video:

[![](https://img.youtube.com/vi/GSTsdhGxDWE/0.jpg)](https://www.youtube.com/watch?v=GSTsdhGxDWE)

## Voronoi
**Repo**: https://github.com/tslAndy/Voronoi
- N^2 voronoi implementation


Video:

[![](./Images/Voronoi.png)](https://www.youtube.com/watch?v=FHGf70wENcg)

## Bezier
**Repo**: https://github.com/tslAndy/Bezier

Simple bezier curves editor
3 points modes support:

- Broken Points
- Tangent Aligned
- Tangent Symmetric 


Video:

[![](./Images/Bezier.png)](https://www.youtube.com/watch?v=S5ll_y1lUzc)

# Trees

## L-system trees
**Repo**: https://github.com/tslAndy/LSystemTree

Video:

[![](./Images/lsystemtree.png)](https://www.youtube.com/watch?v=S-zU_lngq4Q)

## Circle Trees
**Repo**: https://github.com/tslAndy/CircleTree

Video:

[![](./Images/CircleTree.png)](https://www.youtube.com/watch?v=cjF4IYcjbIs)

## Fractal Trees
**Repo**: https://github.com/tslAndy/FractalTree

Video:

[![](./Images/FractalTree.png)](https://www.youtube.com/watch?v=SWnHI6NVRRk)

## Colonization Tree
**Repo**: https://github.com/tslAndy/ColonizationTree

Video:

[![](https://img.youtube.com/vi/AZTfV8RlQWg/0.jpg)](https://www.youtube.com/watch?v=AZTfV8RlQWg)

## Transport Tree
**Repo**: https://github.com/tslAndy/TransportTree

Video:

[![](https://img.youtube.com/vi/IXi7ywQFxxg/0.jpg)](https://www.youtube.com/watch?v=IXi7ywQFxxg)

# Data structures / algorithms

## A*
**Repo**: https://github.com/tslAndy/AStar
- Implementation of several A* algorithms
- Basic A*
- JPS
- Precalculated JPS (improved complexity from original O(N^2) to O(n))
- HPA
- LPA*
- D* Lite


Video:

[![](./Images/AStar.png)](https://www.youtube.com/watch?v=MRuAWzU31ME)

## Job System
**Repo**: https://github.com/tslAndy/JobSystem
- Basic implementation of Unity-like job system
- IJob / IJobParallelFor are implemented by using input / output degree (dependencies)
- ThreadPool is used for running tasks 
- Two types of allocators, memory arena and pool


## Bitmap Roaring
**Repo**: https://github.com/tslAndy/BitmapRoaring
- Implementation of bitmap roaring data structure

