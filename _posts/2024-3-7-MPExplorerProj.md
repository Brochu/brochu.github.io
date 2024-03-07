---
layout: project
status: 2
title: Metroid Prime - Explorer
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

description: A DirectX 12 application that will let the user explore the world of Metroid Prime 1. The user can select a level of the game world and move around in the rooms.
---

After completing a new run of Metroid Prime 1 on the Nintendo Switch and creating a high level interactive map project for this game, I had another idea for a new project. Now that I can move around the game world map and explore maps for the different levels, I would like another application that would let the use explore the rooms themselves in the first person.

At the same time, I would like to use some different tools for this project with the challenges I had to overcome with the interactive map project. Here are some differences I am planning:

- Use Microsoft's C++ compiler through the VS Developer Powershell (CL.exe) w/ CMake
- Use [SDL2](https://github.com/libsdl-org/SDL) in order to handle inputs and window creation
- Use [RAD Debugger](https://github.com/EpicGamesExt/raddebugger) in order to debug issues as the project evolves
- Use [WinDbg](https://learn.microsoft.com/en-us/windows-hardware/drivers/debugger) to capture DirectX12 debug layer outputs

I am still in the starting steps of this project, but I already have some idea of the features I would like to handle :

- First person camera controls (WASD + mouse)
- Render rooms for one level selected
    - Maybe look into some dynamic loading algo to only show rooms in a given range around the player
- Render objects in the rooms as well
    - Maybe look into rendering VFX
- Implement rendering motion vectors in order to unlock effects that require reprojection
    - Used to implement TAA at a later stage
- Look into some effects using DXR if possible with the models (reflections?)
- Look into having GPU driven rendering with some culling
- Going with bindless model for the renderer
- Trying my hand at using C-style C++ to see how I like it

I will come back with screenshots whenever I have something ready to show, please come back for updates
