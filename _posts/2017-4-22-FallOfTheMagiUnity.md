---
layout: project-carousel
status: 1
title: Fall of The Magi
order: 12

type: fa-gamepad
typeTitle: Game

source: fa-male
sourceTitle: Personal Project

tools:
    Unity 3D: unityIcon.svg
    Visual Studio: VS2013Icon.svg

lang: icon-csharp
langTitle: C#

description: A game project where I wanted to keep everything as simple as possible to show my hobbyists friends the ropes of gamedev.
images:
    - /images/projs/FallOfTheMagi_1.png
    - /images/projs/FallOfTheMagi_2.png
    - /images/projs/FallOfTheMagi_3.png
    - /images/projs/FallOfTheMagi_4.png
    - /images/projs/FallOfTheMagi_5.png
    - /images/projs/FallOfTheMagi_6.png
---

After I was done with my studies, some of my friends contacted me because they were looking for a programmer to help them to build a game from their imagination. My friends are hobbyists with art skill for: texture drawing, animation, 3d modeling and sound design.

I wanted to make a project with them that was simplified so I could show them how gamedev projects usually go with Unity3D engine to help. The goal was to keep this project as simple as possible so it could be done quickly and them move onto more complicated projects.

The game was planned as a "infinite runner" type game. Instead of making the player's character running horizontally and avoiding some obstables on it's way, we wanted to make a vertical version. Since we wanted to make the game work on phones, it would also make sense to make it vertical for the phone's screen aspect ratio. We ended up choosing to make a game about a mage jumping down on books in his library.

Features included in the game:

- Menu UI with high-scores and options pages:
    - vfx/music volume options.
    - difficulty options.
- Procedural level generation based on a difficulty setting (3 difficulties).
- 2D character with sprite sheet animations:
    - Idle.
    - Run left/right.
    - Jump.
    - Fall.
- Lives system with kill planes placed off screen at the top and at the bottom
- 2 types of platforms:
    - One that is safe to walk on.
    - One that attacks the player and make them lose a life
- Score system for the player to try and gather as much points as possible.
- Pickups randomly generated that will award some points when picked by the player.
- Custom audio system based on events fired in game code.

Here are some screenshots of the game in action:
