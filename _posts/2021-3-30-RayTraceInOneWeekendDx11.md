---
layout: project-carousel
status: 1
title: Ray Tracer - DirectX 11 version
order: 3

type: fa-cogs
typeTitle: Demo

source: fa-male
sourceTitle: Personal Project

tools:
    Visual Studio: VS2013Icon.svg
    DirectX 11: Dx11_Logo.svg

lang: icon-cplusplus
langTitle: C++

description: Ray tracer implementation that will run on the GPU to explore the DirectX 11 graphics API. Also a good experience writing HLSL shaders (Compute, Vertex, Fragment)
images:
    - /images/projs/RayTraceDx11_1.png
    - /images/projs/RayTraceDx11_2.png
---

While browsing on my Twitter account, I found out about the book available online called [Ray Tracing in One Weekend](https://raytracing.github.io/books/RayTracingInOneWeekend.html) by [Peter Shirley](https://twitter.com/Peter_shirley). This book is a very good guide to write a CPU based ray tracer that will produce some images by emulating the physics of light rays boucing in a scene. The result is usually some images with a good realistic look but is not suited for full real time rendering with frame times under 16.67ms.

While studying in Sherbrooke University, I took one class for photorealistic rendering in which I had to go through the exercice of writing a ray tracer that executes on the CPU. This renderer had some interesting features:

- Mutiple shapes support(triangles, planes, spheres, cubes, cylinders, cones).
- Acceleration structure (uniform grid) to compute less ray/shape intersections.
- Volume textures.
- Multiple materials properties (mirror, matte color).

Since I already implemented this kind of demo before, I wanted to go through this book with one extra challenge in mind. I wanted to implement this ray tracer so it could run on the GPU instead of the CPU. I also wanted to learn how to une DirectX 11 so I decided to use this graphics API to help me with this task.

The implementation from Ray Tracing in One Weekend had similar features to the ray tracer I had to implement in my class. Throughout the experience, I was able to learn a lot about how DirectX is setup and how to use it for some performant rendering. Here are some of the things I learned:

- Boilerplate setup code for DirectX 11 applications.
- How to compile and load shader code (vertex and fragment shaders).
- How to create and send a vertex buffer to the GPU memory.
- How this vertex buffer is used on the GPU side to execute the vertex shader.
- How the data will flow from the vertex shader to the fragment shader.
- How to create a shared buffer between the GPU and CPU to send some constant buffer data to the shaders.
- Two different implementations of the ray trace algorithm:
    - One completely implemented in the fragment shader stage.
    - One where the ray trace algorithm is ran in a compute shader and stored in a texture that is then sampled in the fragment shader on a plane to show the results.
- Testing performance on the application with GPU profilers

Here are some screenshots of images rendered with the ray tracer:
