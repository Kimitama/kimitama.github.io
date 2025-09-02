+++
title = 'Dynamic procedural geneation using Wave Function Collapse'
date = 2024-04-03
draft = false
summary = "Dynamically regenerating the world when you aren't looking"
tags = ['Game Development', 'University']

+++
{{< zenmode-enabled >}}

During a Ludum Dare 48 hour comp I implemented the absolute minimum of the procedural generation algorithm, Wave Function Collapse being inspired by townscaper.
I used it to regenerate all tiles outside of the players view, meaning the entire world is always changing when you return.
![your image](qunatumcaves.gif "48 hour ludum dare game. Purple noise indicates it will be regenerated when you get closer. Notice terrain changes as you move back and forth.")

The code was later cleaned up and reused in a university project.
Here, again, terrain regenerates whne you are not looking, hidden behind the fog shader i made. You could lock routes by placing byous that would ensure the local area never regenerated, creating supply lines you could move along.

![your image](shipgamegif.gif "University project that used my wave function collapse procedural generation as a main mechanic.")

In order to make it performant for the ship game, it needed to be efficient across an, essentially, infinite area. 
Since the world is by default always regenerated, only the area around the player or tiles that are locked in place need to be kept in memory.
A dictionary was kept, with the tile coordinates as the key, that constantly updated as new tiles disappeared or regenerated.
The player was also able to place light buoys, which locks tiles in an area in place. For this reason, a data structure was made that tracks which tiles are locked in place, to avoid them from despawning.

To generate, tile rules had to be defined. I made scriptable objects (essentially files with an editor), where you can select which types of tiles were allowed to connect on each side, and which mirror variations should exist.
The game also contains different "biomes" as you move further from the spawn point. These biomes consist of different coloring, by interpolating post processing effects based on distance, and also use a different set of tilerules, which due to time constraints are the same time rules with different weighings to generate different shaped landmasses, such as weighing border tiles higher to generate thinner landscapes, weighing inner landmass high to generate big landmasses, or just weighing water low to generate more landscape in general

For the ship game, we also used a dual tile hexagonal tile system (i.e. triangle tiles that make up hexagonal sets of tiles), meaning we only needed very few tile variations, and dual tiles are used in Townscaper so they were a safe bet to use for wave function collapse.

![your image](shipgamegifwfc.gif "Here is the terrain regeneration shown in editor. It generates very fast and supports an infinite world, and the terrain generation changed depending on area by adjusting the numbers for the terrain generation rules.")

