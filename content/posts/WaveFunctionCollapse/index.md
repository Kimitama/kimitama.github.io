+++
title = 'Dynamic procedural geneation using Wave Function Collapse'
date = 2024-04-03
draft = false
summary = "Dynamically regenerating the world when you aren't looking"
tags = ['Game Development', 'University']

+++
{{< zenmode-enabled >}}

During a Ludum Dare 48 hour comp I implemented the absolute minimum of the procedural generation algorithm, Wave Function Collapse being sinpired by townscaper.
I used it to regenerate all tiles outside of the players view, meaning the entire world is always in flux.
![your image](qunatumcaves.gif "48 hour ludum dare game. Purple noise indicates it will be regenerated when you get closer. Notice terrain changes as you move back and forth.")

The code was later cleaned up and reused in a university project.
Here, again, terrain regenerates whne you are not looking, hidden behind the fog shader i made. You could lock routes by placing byous that would ensure the local area never regenerated, creating supply lines you could move along.

![your image](shipgamegif.gif "University project that used my wave function collapse procedural generation as a main mechanic.")


![your image](shipgamegifwfc.gif "Here is the terrain regeneration shown in editor. It generates very fast and supports an infinite world, and the terrain generation changed depending on area by adjusting the numbers for the terrain generation rules.")

