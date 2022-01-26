---
layout: project
status: 2
title: Golf Terrain Highlights Widget (w/ Dx11)
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
