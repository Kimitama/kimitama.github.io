+++
title = 'Tactics game engine with C# and SDL'
date = 2024-04-03
draft = false
summary = "Almost from scratch C# game engine designed for grid based tactics games."
tags = ['Game Development', 'University']
+++
{{< zenmode-enabled >}}
Using SDL and C# we made a game engine that makes it simple to make Tactics games by designing an engine for enqueuing and playing back actions to allow animations to play out easily.
Most of the work was designing systems that were generic enough that any tactics game or similar could be made in it, that it allowed everything to be animated, while keeping it easy to create games in it.

In collaboration we designed a system for how objects and units fit on a grid, "collision" and layers, and how actions are performed and how turns work.
This was a very difficult system to design, as the intersection of a system being easy to use and understand, but also flexible enough to make any kind of turn based tactics game you can imagine, is very difficult to find. Especially when we wanted it to allow everything to be properly animataed, playing back every action at the intended time without the developer having to manage timing themselves.
The hardest to create example we were aiming for was into the breach, which contains very complex orders of events, where multiple units may be pushed at the same time, and could be interrupted at any tile during the push, or interact with other characters on the screen. In the end we created a system that was able to manage such cases without the developer having to worry about it too much.
![your image](combat.png "Demo tactics game using the engine.")

Examples of systems I made is a generic pathfinding system integrated into the engine, FMOD integration for audio, and the action queue system.
This was a basic implementation of Dijkstra, with an API that allowed grabbing every possible tile and the cost that the developer can use however they want.
It is integrated with the tilemap system, where cost or blocking the player can be defined per tile in Tiled, the tilemap editor we supported.
This worked by assigning layers to tiles in Tiled, and assigning a cost to each layer in the pathfinding settings object.
Different units could use different pathfinding setting instances to allow different types of units, e.g. water units only travelling on water tiles.

In order to properly animate the actions, each action is enqueued in the system such that they play in the correct order, and can potentially be interrupted. E.g. if you push a unit, the push animation plays, the unit gets pushed one tile at a time, and if they hit a tile while this happens, they take damage or potentially die, ending the turn.
![your image](map.png "Overworld map for demo tactics game.")

In the around 8 weeks, we made the engine and two demo games, a simple puzzle game and a level based tactics game with a few levels, different unit types, different abilities, stats, and an overworld map.
The tactics game we made took only a few days, under game jam like conditions, proving the engine was capable enough from the plan that we could make a game fast, without any engine bugs, though obviously the game we made was the kind that the engine was designed for in the first place.

![your image](puzzle.png "Demo puzzle game using the engine.")
