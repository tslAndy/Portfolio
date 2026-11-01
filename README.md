# Portfolio

Hello! Thank you for checking out my portfolio. Below the TLDR list there are more specific descriptions of projects and videos. Projects are implemented in Unity or Raylib. 



TLDR:

- **GPU**
  
  - Raytracing
  
  - Radiance Cascades
  
  - Volumetric Rendering
  
  - Black Hole
  
  - Aurora Borealis
  
  - Atmosphere
  
  - Boids
  
  - Particle Life
  
  - Eulerian Fluid
  
  - FLIP Fluid
  
  - Slime Mold
  
  - N-Body LOD
  
  - Voxel Ray Traversal
  
  - Voxel Editor
  
  - Raymarching
  
  - Cell Shading



- **Physics**
  
  - Verlet Engine
  
  - 2D physics engine
  
  - GJK + EPA
  
  - Soft Body
  
  - N-body Barnes-Hut



- **Uncategorized**
  
  - Timeroll
  
  - Marching Squares 
  
  - Warp Grid 
  
  - Bridge Simulator 
  
  - Software Rasterizer 
  
  - Wolfenstein-like Raycaster 
  
  - ECS Survivors-like game 
  
  - Falling Sand Game (old version)
  
  - Falling Sand Game (new version)
  
  - Circle Inverse Kinematics 
  
  - FABRIK Inverse Kinematics
  
  - Multilayered Dual Grid 
  
  - Voronoi generator with Poisson disc sampling 
  
  - Bezier Curves drawing 



- **Trees** 
  
  - L-System trees 
  - Circle trees 
  - Fractal trees 
  - Colonization tree 
  - Transport trees 



- **DSA** 
  
  - A* family algorithms 
  - Unity-like job system 
  - Bitmap Roaring 



# GPU stuff

## Ray tracing

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

Repo: https://github.com/tslAndy/Raytrace

![image info](./Images/Raytrace.png)

## Radiance Cascades

- Radiance Cascades implementation in Compute Shaders
- Raycasting is sped up with GPU built SDF (log N time) 
- Basic version use preaveraging (only two cascade textures implemented as arrays with size 1/4 of original texture)
- Another version use direction first layout and preaveraging (two cascades, full size and quarter size). On my GPU it's slower than original version (may be because my GPU is integrated)
- Increased raycasting radius used as bilinear fix. It didn't allow to fully mitigate circles, but looks much better.

Repo: https://github.com/tslAndy/Cascades

Video:

[![](./Images/Cascades.png)](https://www.youtube.com/watch?v=R0g4GFdLCNY)

## Volumetric Rendering

- Basic volumetric rendering with Compute Shaders

Repo: https://github.com/tslAndy/Volumetric

Video:

[![](https://img.youtube.com/vi/nXv9PXc2T7M/0.jpg)](https://www.youtube.com/watch?v=nXv9PXc2T7M)

## Black Hole

- Black hole simulation on Unity with Compute Shaders
- Gas disk is generated with Worley and Perlin noise
- Disk rendered with volumetric rendering

Repo: https://github.com/tslAndy/BlackHole

Video:

[![](./Images/BlackHole.png)](https://www.youtube.com/watch?v=hWAEQB-2bAU)

## Aurora shader

- Simple aurora borealis rendering with Perlin noise and volumetric raymarching

Repo: https://github.com/tslAndy/Aurora

Video:

[![](./Images/Aurora.png)](https://www.youtube.com/watch?v=2jf9wXUALuQ)

## Atmosphere Rendering

- Atmosphere rendering
- LUT for acceleration

Repo: https://github.com/tslAndy/Atmosphere

Video:

[![](./Images/Atmosphere.png)](https://www.youtube.com/watch?v=u2EjnY8i9Ms)

## Boids

- Boids algorithm implementation on the GPU
- Raylib for rendering
- ILGPU for OpenCL usage (other backends such as CUDA can be used aswell) 

Repo: https://github.com/tslAndy/Boids

Video:

[![](./Images/Boids.png)](https://www.youtube.com/watch?v=7xeWGgYISzI)

## Particle Life

- Same backend as in boids algorithm

Repo: https://github.com/tslAndy/ParticleLife

![image info](./Images/Life.png) 

## Eulerian Fluid Simulation

- GPU based Eulerian Fluid simulation (ILGPU, OpenCL)
- Obstacles are supported

Repo: https://github.com/tslAndy/EulerianFluidSim

Video:

[![](./Images/Eulerian.png)](https://www.youtube.com/watch?v=jZc8UK_pKiE)

## FLIP Simulation

- GPU based Fluid In Particle implementation
- Extended version of Eulerian simulation

Repo: https://github.com/tslAndy/FlipLiquidGPU

Video:

[![](./Images/FLIP.png)](https://www.youtube.com/watch?v=Vc5q7WPS4Dg)

## Slime Mold Simulation

- GPU based Slime Mold Simulation
- ILGPU, Raylib

Repo: https://github.com/tslAndy/SlimeSim

Video:

[![](./Images/Slime.png)](https://www.youtube.com/watch?v=yl8N5paE2xg)

## N-body GPU

- LOD-based simulation of N-body problem in Unity with Compute Shader
- Masses are transferred to textures
- Textures are blurred with Gaussian blur
- Several LOD (mipmaps) are created
- Only 3x3 square on each LOD-level used for gravity computation

Repo: https://github.com/tslAndy/GravComputeShader

Video:

[![](./Images/GravCompute.png)](https://www.youtube.com/watch?v=a2gq912Lm9w)

## Amanatides and Woo's fast Voxel Traversal

- Implementaion of voxel ray traversal in Compute Shaders

Repo: https://github.com/tslAndy/Voxelizer

Video:

[![](./Images/Amantides.png)](https://www.youtube.com/watch?v=Tbj0grPXC8U)

## Voxel Editor

- Simple voxel editor
- Binary Meshing (main goal of this project)

Repo: https://github.com/tslAndy/Voxel

Video:

[![](./Images/VoxelEditor.png)](https://www.youtube.com/watch?v=qh7dsT_-7LY)

## Raymarching

- SDF Raymarching with Unity and Compute Shaders
- For learining purposes shape operations (union, difference, intersection, mix) are implemented through bytecode.
- In the inspector created tree-like data structure (expression tree), after it get converted to bytecode which get transferred to GPU
- By using this approach there is no need to change shader code when complex hierarchies of operations is created (for example merge some objects and exclude other)

Repo: https://github.com/tslAndy/Raymarch

Video:

[![](./Images/Raymarch.png)](https://www.youtube.com/watch?v=TwwSHPYmgD8)

## Cell Shading

- Simple cell shading in Unity URP Shader Graph

Repo: https://github.com/tslAndy/Fur

Video:

[![](./Images/CellShading.png)](https://www.youtube.com/watch?v=M_2xZsWtEO8)

# Physics stuff

## Verlet Integration

- Rope implemented with verlet integration

Repo: https://github.com/tslAndy/Verlet

Video:

[![](./Images/Verlet.png)](https://www.youtube.com/watch?v=8q6YdGlpN7Q)

## Physics

- Simple physics engine with different colliders support
- Concave polygons support
- Quickhull support

Repo: https://github.com/tslAndy/Physics

Video:

[![](./Images/Physics.png)](https://www.youtube.com/watch?v=Y52Ldz2PnCw)

## N-body Barnes-Hut

- Multithreaded CPU-implementation of Barnes Hut algorithm
- Implemented own unity-like job system (later was improved)
- Objects are sorted by multithreaded merge sort by their Morton codes for improving space locality of quadtree

Repo: https://github.com/tslAndy/Gravity

Video:

[![](./Images/Gravity.png)](https://www.youtube.com/watch?v=AqEuBSJd-jQ)

## Soft Body

- Simple soft body implementation

Repo: https://github.com/tslAndy/SoftBody

Video:

[![](./Images/SoftBody.png)](https://www.youtube.com/watch?v=yeHUV0iDEpo)

## 2D GJK + EPA

- Implementation of GJK and EPA for collision detection and resolving

Repo: https://github.com/tslAndy/GJK

Video:

[![](./Images/GJK.png)](https://www.youtube.com/wat

# Other

## Timeroll

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

Repo: https://github.com/tslAndy/Timeroll

Video:

[![](https://img.youtube.com/vi/ZPSvGTJPMiw/0.jpg)](https://www.youtube.com/watch?v=ZPSvGTJPMiw)

## Marching Squares

- Metaballs implemented with marching squares
- Triangles for rendering are generated in multithread
- For reducing trigs amount Binary Meshing is used

Repo: https://github.com/tslAndy/MarchingSquares

Video:

[![](./Images/MarchingSquares.png)](https://www.youtube.com/watch?v=-OTAZTXqLnw)

## Warp Grid

- Simple warp grid implementation, nothing special

Repo: https://github.com/tslAndy/WarpGrid

Video:

[![](./Images/WarpGrid.png)](https://www.youtube.com/watch?v=UhpW3lMCEa0)

## Bridge

- Simple Bridge game

Repo: https://github.com/tslAndy/Bridge

Video:

[![](./Images/Bridge.png)](https://www.youtube.com/watch?v=3AqXc3j6b8Y)

## Software Rasterizer

- Simple Software Rasterizer
- Occlusion & Frustum Culling
- Hi-Z buffer optimization
- Multithreaded rendering

Repo: https://github.com/tslAndy/RastRefactor

Video:

[![](./Images/Rasterizer.png)](https://www.youtube.com/watch?v=fpddzHvOMzo)

## Durdoom

- Advanced implementation of Wolfenstein-like raycaster
- Sloped blocks support
- Transparent textures
- Player camera height changing

Repo: https://github.com/tslAndy/Durdoom

Video:

[![](./Images/Doom.png)](https://www.youtube.com/watch?v=y2-YEY0J8js)

## Survivors

- Survivors-like project implemented in Arch ECS
- Main goal of project was to learn Entity Component System paradigm
- Learned basics of Autofac DI

https://github.com/tslAndy/Survivors

Video:

[![](./Images/Survivors.png)](https://www.youtube.com/watch?v=UZB8wT53WtA)

## Sand 1

- First implementation of Noita-like falling sand

Repo: https://github.com/tslAndy/OldSand

Video:

[![](https://img.youtube.com/vi/3iZQmG9DUSc/0.jpg)](https://www.youtube.com/watch?v=3iZQmG9DUSc)

## Sand 2

- Improved implementation
- Chunked multithreaded update
- Dirty rect for excluding empty space in chunks
- Activity zones (if particles in chunk are idle, it will be excluded from update)
- Simple save system with Memory Pack

Repo: https://github.com/tslAndy/Sand

Video:

[![](./Images/Sand.png)](https://www.youtube.com/watch?v=ufNKMC0gQvc)

## Circle IK

- 2D Inverse Kinematics with circles

Repo: https://github.com/tslAndy/CircleIK

Video:

[![](./Images/CircleIK.png)](https://www.youtube.com/watch?v=HTjGrW2Etiw)

## FABRIK IK

- 2D FABRIK IK with angle limitation

Repo: https://github.com/tslAndy/FabrikIK

Video:

[![](./Images/FabrikIK.png)](https://www.youtube.com/watch?v=towby8B63UE)

## Dual Grid

- Advanced Dual Grid implementation in Unity
- While standard dual grid support 2 types of tiles, current implementation allow to use as much tiles as necessary (all on the same tilemap)
- Algorithm use 3 additional tilemaps for selecting corresponding border tiles, but interaction only with main one (border tiles are selected automatically)

Repo: https://github.com/tslAndy/Dual-Grid

Video:

[![](https://img.youtube.com/vi/GSTsdhGxDWE/0.jpg)](https://www.youtube.com/watch?v=GSTsdhGxDWE)

## Voronoi

- N^2 voronoi implementation

Repo: https://github.com/tslAndy/Voronoi

Video:

[![](./Images/Voronoi.png)](https://www.youtube.com/watch?v=FHGf70wENcg)

## Bezier

Simple bezier curves editor
3 points modes support:

- Broken Points
- Tangent Aligned
- Tangent Symmetric 

Repo: https://github.com/tslAndy/Bezier

Video:

[![](./Images/Bezier.png)](https://www.youtube.com/watch?v=S5ll_y1lUzc)

# Trees

## L-system trees

Repo: https://github.com/tslAndy/LSystemTree

Video:

[![](./Images/lsystemtree.png)](https://www.youtube.com/watch?v=S-zU_lngq4Q)

## Circle Trees

Repo: https://github.com/tslAndy/CircleTree

Video:

[![](./Images/CircleTree.png)](https://www.youtube.com/watch?v=cjF4IYcjbIs)

## Fractal Trees

Repo: https://github.com/tslAndy/FractalTree

Video:

[![](./Images/FractalTree.png)](https://www.youtube.com/watch?v=SWnHI6NVRRk)

## Colonization Tree

Repo: https://github.com/tslAndy/ColonizationTree

Video:

[![](https://img.youtube.com/vi/AZTfV8RlQWg/0.jpg)](https://www.youtube.com/watch?v=AZTfV8RlQWg)

## Transport Tree

Repo: https://github.com/tslAndy/TransportTree

Video:

[![](https://img.youtube.com/vi/IXi7ywQFxxg/0.jpg)](https://www.youtube.com/watch?v=IXi7ywQFxxg)

# Data structures / algorithms

## A*

- Implementation of several A* algorithms
- Basic A*
- JPS
- Precalculated JPS (improved complexity from original O(N^2) to O(n))
- HPA
- LPA*
- D* Lite

Repo: https://github.com/tslAndy/AStar

Video:

[![](./Images/AStar.png)](https://www.youtube.com/watch?v=MRuAWzU31ME)

## Job System

- Basic implementation of Unity-like job system
- IJob / IJobParallelFor are implemented by using input / output degree (dependencies)
- ThreadPool is used for running tasks 
- Two types of allocators, memory arena and pool

Repo: https://github.com/tslAndy/JobSystem

## Bitmap Roaring

- Implementation of bitmap roaring data structure

Repo: https://github.com/tslAndy/BitmapRoaring
