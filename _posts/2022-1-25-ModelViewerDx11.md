---
layout: project
status: 2
title: Test bench renderer with Dx11
order: 2

type: fa-cogs
typeTitle: Demo

source: fa-male
sourceTitle: Personal Project

tools:
    CMake: Cmake_Logo.svg
    Neovim: Neovim_logo.svg
    DirectX 11: Dx11_Logo.svg

lang: icon-cplusplus
langTitle: C++

description: While reading papers on different rendering techniques over the course of my progress in graphics programming, I've found some that I would like to try and implement. This project is a very simple renderer to use as a base for these tests.
images:
---

The goal of this project is to setup an environment where I can implement some rendering techniques in a Dx11 engine that I setup myself. For now I am thinking of being able to select a model to render from an OBJ file (I did write a very simple OBJ parser for this project).

For now, I rely on 3 main libraries to work on this project:
* [SDL2](https://github.com/libsdl-org/SDL): So I can access OS and hardware functionality without writing Win32 code myself.
* [ImGui](https://github.com/ocornut/imgui): So I can easily add some debug information and controls so I can test the state of the renderer as it is running.
* [DirectX Math](https://github.com/microsoft/DirectXMath): So I do not have to implement my own functions to handle all the vector and matrix maths needed for this project. Can also help making sure the maths logic is well optimized.

I am still in the process of writing the base of the renderer as of now, but I plan to add some features as I go to test my implementations of techniques found in graphics programming papers online.
* Shadows: I would like to try out different style of shadow rendering:
    * Basic shadow maps
    * Cascading shadow maps
    * Variance shadow maps
* Bloom
* Depth + Stencil visual effects
* and more to come

Please keep up with my updates to this project in the future.

| Update from 2022-5-22 |

When I first wanted to be able to load model information from OBJ files, I wrote a very simple function to read and parse an OBJ file and return the vertex positions, UVs and normals. I then use this data as a vertex buffer that I upload on GPU for renderning.
As I was looking on the internet to download more example models, I noticed that some OBJ file will also contain some information related to materials (like textures used for certain meshes). I think it would be interesting to rework my renderer logic to be able to handle multiple meshes as well as some texturing. In order to do this, I will need to work on a couple details:

* Reading the vertex data like before but store meshes independently
    * Return an array of meshes to render one at a time to the renderer
* Read the material file if one is found
* For every mesh, find out the material that should be used
* List textures to be uploaded to GPU memory per meshes
* When rendering, we need to bind the correct texture

I would see this feature as a nice to have for now, but I would be curious to see what kind of work in needed to handle these situations.
