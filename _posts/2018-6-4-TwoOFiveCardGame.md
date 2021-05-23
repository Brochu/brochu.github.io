---
layout: project-carousel
status: 1
title: Two-O-Five
order: 4

type: fa-gamepad
typeTitle: Game

source: fa-male
sourceTitle: Personal Project

tools:
    Unity 3D: unityIcon.svg
    Visual Studio: VS2013Icon.svg

lang: icon-csharp
langTitle: C#

description: The video game verison of the board game known as Sequence. We wanted to make a network multiplayer game based on a game that already existed to complete the project faster
images:
    - /images/projs/TwoOFive_1.png
    - /images/projs/TwoOFive_2.png
    - /images/projs/TwoOFive_3.png
    - /images/projs/TwoOFive_4.png
    - /images/projs/TwoOFive_5.png
    - /images/projs/TwoOFive_6.png
    - /images/projs/TwoOFive_7.png
    - /images/projs/TwoOFive_8.png
    - /images/projs/TwoOFive_9.png
    - /images/projs/TwoOFive_10.png
    - /images/projs/TwoOFive_11.png
    - /images/projs/TwoOFive_12.png
---

When I moved out of the city where I grew up in, the main way I used to keep in contact with friends and family was with Skype/Discord calls and network multiplayer video games. Since then, I always wanted to build my own game that would connect people through the Internet. I wanted to find a game simple enough so I could focus on making it work in a networked environment but still would be fun to play with friends while having a voice call on.

Since I wanted to focus on the network tech needed to make this work, I thought it would be best to work on a game with some details already nailed down to simplify the process. The people that helped me with the visual aspects of the game and myself we decided to pick a board game we used to play with friends and family [Sequence](https://en.wikipedia.org/wiki/Sequence_(game)).

Here is a short explaination of the rules:

- Mix 2 decks of cards together and shuffle them.
- Each player will be dealt an amount of cards based on the amount of players in the game.
- Players are arranged in two teams (Red team, Blue team).
- There is a 10x10 board with some references to cards on it.
- Every player will play turn by turn so teams alternate.
- At their turn, a player will pick one of their cards and place it to a matching spot on the board.
- Jacks are a special case:
    - The jacks of 2 given suits will remove a token from the other team
    - The jacks of the 2 other suits will add a token on any free spot
- The goal for each team is to line up 5 tokens in a vertical/horizontal/diagnal line

In order to make this game wor on the Internet, I built a separate project in pure C# where I would implement the network layer for the game. The goal was to have an interface in the Unity3D game project that would send and receive commands from the network layer without having to care about the network connection. Having a separate project would also make it easier for me to debug the network layer in isolation. My C# solution for the network layer was comprised of a main project for the sockets interactions, a project that would list all the available commands for the layer and a console application to send commands to the backend manually for debugging.

The network layer would keep track of all the players connected (list of client sockets) and would keep track of the game state (board, player's hands). All the operations in the network layers used the `async` C# tech so make sure we would not block the process since we couldn't know which client was to send the next command. When the game state would change, the backend would broadcast the new game state to all connected clients.

I consider this project complete as of now since I was able to play some games with friends online already with the latest build of this game. Some there are some things that I would do differently if I had to redo this kind of project in  the future:

- Change the sockets from TCP to UDP: I am not sure why I decided to go with TCP sockets when I started this project but I think it would be better to use UDP since most of the modern game engines will use them for networked games)
- Multiplex the backend application: Right now, every instance of the backend process will handle only one game running at once. In order to handle scaling better, it would be possible to make it so  the backend could run multiple games at once
- Some kind of room code logic: It would be better to have the backend generate room codes (like the Jackbox party games) when a player starts a game server to make it easier for other clients to connect to it. There would be some kind of map in the backend that would link ip:port entry to some room code. Then a client could request to join a room with a given room code, then the backend could report back to which ip:port to connect to in the client's machine.

Here are some screenshots of the game being played (clients ran on the same machine for testing purposes, we can run the game on different machines and connect through the Internet):
