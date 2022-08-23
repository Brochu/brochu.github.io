---
layout: project
status: 2
title: Golf Terrain Highlights Widget (w/ Dx11)
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

description: From the 3D golf games I used to play, there was always this widget to show terrain heights at a given part of a hole. I wanted to re-create this myself with the help of Dx11
images:
    - /images/projs/GolfHighlights0.png
---

One of my favorite 3D golf game is `Mario Golf: Toadstool Tour` for Nintendo Gamecube. In this game, players have access to a special widget in the UI to help make every shot as perfect as it can be. Here is an example of the said widget:

[<img src="https://www.mobygames.com/images/shots/l/154451-mario-golf-toadstool-tour-gamecube-screenshot-wario-putting.png
">](Terrain Highlight Grid from Toadstool Tour)

As we can see, the grid is rendered on top of the terrain and will show the features of this part of the course. The grid's colors are selected with a lerp based on the terrain's height at that point. Red means the terrain is higher, blue means it is lower.

We cannot really see with an image, but the grid's lines are also animated to show the difference in heights between 2 neighbour points.

As of now, I just started the project structure and included the Dx11 SDK files. I also started making a list of the features I will need to implement for this demo. I am also looking into how I am going to dynamically generate the vertex data to render the grid.

* We will use vertex color data to store the height, we can then decode this information to feed into the color lerp.
* This resulting color will be used to tint a texture on the grid lines
* This texture is used to be able to animate the lines
    * Texture UVs offset to give the effect of points moving along the lines
    * Texture UVs tiling to make the points closer or farther from each other

Stay tuned for more updates on this project and screenshots!
