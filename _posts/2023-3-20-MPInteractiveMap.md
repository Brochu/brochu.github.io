---
layout: project-carousel
status: 2
title: Metroid Prime - Interactive Map
order: 0

type: fa-cogs
typeTitle: Demo

source: fa-male
sourceTitle: Personal Project

tools:
    CMake: Cmake_Logo.svg
    Neovim: Neovim_logo.svg
    Rider: JetBrainsRider_Logo.svg
    DirectX 12: Dx12_Logo.svg

lang: icon-cplusplus
langTitle: C++

description: A DirectX 12 application that will render an interactive map for Metroid Prime. The user can select an area of the game to show on screen and then move around the rooms.
images:
    - /images/projs/MPInteractiveMap_0.png
    - /images/projs/MPInteractiveMap_1.png
    - /images/projs/MPInteractiveMap_2.png
    - /images/projs/MPInteractiveMap_3.png
    - /images/projs/MPInteractiveMap_4.png
    - /images/projs/MPInteractiveMap_5.png
    - /images/projs/MPInteractiveMap_6.png
    - /images/projs/MPInteractiveMap_7.png
---

Recently, the Metroid Prime Remasted was release on Nintendo Switch. Being a fan of the game originally released on the Gamecube, I picked it up so I could relive Samus' first adventure in 3D.

When replaying the game, I remembered just how much I liked the way the map is shown to the player. After selecting one of the areas, the layout of this area is shown room by room. The player can also slide the area around as well as rotate it to explore all angles.

While playing, I tried to find an interactive re-creation of this map screen online in-browser to explore the areas from my computer. I know that this exists for games like Dark Souls where you can explore the full map of the game from a browser. Unfortunately, I could not find a version for Metroid Prime when I looked around the web. I decided to try and create my own version of it after I was able to find the models for all the rooms of the game.

At first, my goal was just to show the map like it is shown in the game with similar controls. Later, I was able to find the data for all the energy tanks and extra missile tanks that are hidden throughout the game. I then had the idea to add another rendering pass in the application to show where the items are in the rooms with some icons overlayed on top of the map. This will let me work on a rendering technique I never used before that can be very useful: Billboads.

The icons will be rendered on a quad that will be generated at runtime so it is always aligned with the camera. This way, it just feels like there is a UI rendered on top of the map that will follow the important positions on the map as it moves based on the user's input. As of now, I have the map rendering done at a acceptable level, meaning there are some details that I could implement better for performance but we can see the maps. The icons are currently being worked on and will be added later on.

Another rendering technique that I used for the map rendering part of this project is an edge detection algorithm (Sobel Filter). I wanted to be able to highlight the edges on the room models so it would have the same feel as in the game. I am pretty sure this wasn't what was used in the game to achieve the look, but the models I found did not include UVs, so I wanted to find a technique that would work without having this data available.

In the following screenshots, I show what the different areas of the game look like in the application. The areas will appear in this order:

* Introduction area - Space Pirate Frigate
* Chozo Ruins
* Phendrana Drifts
* Tallon Overworld
* Phazon Mines
* Magmoor Caverns
* Impact Crater

-------------------------------------------------

Icons rendering was added as a first version. The result is a little bit rough but it does show the right data for the users. For now I would like to integrate ImGui library in the project to control some settings at runtime as a next step for this project.
