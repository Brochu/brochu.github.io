---
layout: project-carousel
status: 2
title: DirectX 12 Model Viewer
order: 0

type: fa-cogs
typeTitle: Demo

source: fa-male
sourceTitle: Personal Project

tools:
    CMake: Cmake_Logo.svg
    Neovim: Neovim_logo.svg
    DirectX 12: Dx12_Logo.svg

lang: icon-cplusplus
langTitle: C++

description: Simple model viewer renderer using DirectX 12 that I implemented in order to get familiar with more modern rendering APIs used in game engines and to run simulations. My goals were to re-implement my simple DirectX 11 model viewer with a newer version of the API as well as adding some DirectX 12 specific features afterwards.
images:
    - /images/projs/DirectX12Renderer_1.png
---

After working on a simple renderer in DirectX 11, I started to be curious of the different features that are available in DirectX 12. I also wanted to keep up with the more recent render APIs that are used in Game Engines and simulations nowadays.

The goal of this project is to first take a feature set implemented with DirectX 11 and move them to another renderer based off of DirectX 12. Another goal of mine with this project is to add new features in the renderer that are found only with the more modern rendering API (eg. Ray tracing, manual sync, manual memory management, ...)

Throughout this project, I will use these tools to help build and verify the application:
* **CMake** - Build system
> Not my favorite to work with, but I would like to be able to work with and without Visual Studio when developing C++ projects. Also makes it ""easier"" to include libraries as libs are often managed by CMake as well.
* **MSBuild** - Compiler
> Since I do my work on Windows, I think it would be easier to debug issues later in the project if I am able to run the project in Visual Studio (even though I develop from Neovim most of the time). Outputting a .SLN from CMake and building with MSBuild let's me debug from VS and develop from Neovim. It might not be the most optimal setup but it's what I wanted to try this time.
* **[Orbit](https://github.com/google/orbit)** - Performance profiling from Google
> Unlike my previous DirectX 11 project, I wanted to plan some ways to profile performance from the start. This is one tool I was able to find that I would like to try. Let's me see where time is spent and which functions to look into for optimizations

Apart from tools, I will also use some libraries to help me focus on what I really want to practice and think about while working on this project. Here are the libraries I plan on using:
* **DirectX 12** - Main graphics API
* **[DirectX Math](https://github.com/microsoft/DirectXMath)** - Vector and matrix math helpers
* **[ImGUI](https://github.com/ocornut/imgui)** - Immediate mode UI
* **[Assimp](https://github.com/assimp/assimp)** - Help to load 3d model files
* **[Tracy](https://github.com/wolfpld/tracy)** - Performance profiling

For this project, I also did not start from an empty project. Here is the sample I used as a starting point: [Dx12 hello world project](https://gpuopen.com/learn/hellod3d12-directx-12-sdk-sample/). This starting point is the reason why I chose to skip on using [SDL](https://github.com/libsdl-org/SDL) for this project, which is one of the differences between this project and the DirectX 11 version.

Like I mentioned earlier, the first order of buisiness is to bring the previous project's features here:

* [X]Loading 3d model files with the help of Assimp, extract the information we need
* [X]Create VertexBuffers(+view) as well as IndexBuffers(+view)
* [X]Render models with one light source in the scene
* [X]Debug controls to move camera, view parameters and light position
* [X]Get the list of textures needed from the Assimp scene
* [ ]Upload texture data to GPU memory

After these features are in and stable, Here are some ideas for future developments that could happen in the lifetime of this project :

* Try and organize resources in one big heap allocation (w/ CreatePlacedResource calls)
* Idem with DescriptorHeaps
* Be able to change the model .obj file at runtime
    * Clear out the CPU and GPU memory for the old model.
    * Load the new data for the new model to render.
    * Re-upload all needed data to GPU.
    * Start rendering again.
* Try to build TopLevel/BottomLevel acceleration structures to test the DXR api (HWRT)
* Implement some simple RT shadows with MissShaders

As of 2023-02-15, I made a lot of progress bringing features from the previous DirectX 11 version of the model renderer over to the new DirectX 12 version. I currently am able to render the geometry of 3d model files without textures and lit with a single point light placed in the scene. The position of the point light can be changed through the debug menu. In order to place the vertices and indices into GPU memory, we are using only one allocation with offsets for both buffers in the upload heap. Unfortunately, we are still using separate allocations in the default heap afterwards. I will be changing this to also use only one allocation in default heap later.

My next steps is to look into how to handle texture data upload and access to shaders. I would like to be able to use only one allocation and sub-allocate resources myself for the different textures needed for the selected model. Since I know all the textures that are going to be needed in advance, I would like to bind a SRV array to the pixel shader and use an index from a constant buffer to index in this array and pick the right texture to sample for a given draw call. Need some work on the Root Signature used in order to make this happen after the texture data upload is done.
