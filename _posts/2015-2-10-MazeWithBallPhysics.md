---
layout: project-carousel
status: 1
title: Maze with Ball Physics
order: 5

type: fa-gamepad
typeTitle: Game

source: fa-male
sourceTitle: Personal Project

tools:
    Unity 3D: unityIcon.svg
    Visual Studio: VS2013Icon.svg

lang: icon-csharp
langTitle: C#

description: Game project to re-create some gameplay features from an existing game. Implemented with the Unity3D engine.
images:
    - /images/projs/MkbClone_1.png
    - /images/projs/MkbClone_2.png
    - /images/projs/MkbClone_3.png
    - /images/projs/MkbClone_4.png
    - /images/projs/MkbClone_5.png
    - /images/projs/MkbClone_6.png
---

This project is my first serious try to come up with a complete game with the Unity 3D engine. One of my friends introduced me to Super Monkey Ball a while back and I found the game to be very entertaining. Usually when I find a good game, I try to figure out the mechanics and how it is done technically. I also try to single out why is the game fun and what makes it good. Since I spent a lot of time figuring out those details about this game, I had an idea of how to start my own spin on the base idea.

When I started this project I already worked with the Unity engine when I worked at Square Enix Montreal, my choice to use this tool was to improve using Unity at the same time. The good thing is i worked for some time with C# now and I am comfortable with the language. This way I can concentrate in learning the good practices in Unity and create an enjoyable experience for players.

First I wanted to create a simple example of camera control to mimic the effect of moving the entire stage to move the ball. When I succeeded and showed the results to some of my friend, they were quickly interested in the concept so I was happy with the results.

As of now, I am still building mechanics and systems to be used in this game so it is still a project that is in progress. Here are the features that are in a usable state in the project as of now:

- 3D character setup with a robot model found online for prototyping.
- 3D animations that are linked with some gameplay values blend spaces with player speed to blend between walk/run animations.
- Some shader work to render the ball around the character with easy to change parameters.
- Asset packaging setup based on asset bundles for characters, levels and worlds.
- Camera setup that will rotate around the player.
- Skybox asset used to give the idea that the player is found in space.
- Movement system based on the `Super Monkey Ball` video game for the Nintendo Gamecube.
- A very simple test scene with a slope to test physics.

If you are interested in trying out the movement mechanics of the game, here is a [download link]({{site.baseurl}}/downloads/mkb-demo.zip) to a windows executable. If you would like to try out this on Linux or Mac, please contact me.
