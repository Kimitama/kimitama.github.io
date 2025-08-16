+++
title = 'Non-euclidean VR game with no artificial locomotion using portals'
date = 2024-04-03
draft = false
summary = "A game that had players walk more than a kilomter in real life."
tags = ['Game Development', 'University']
+++
{{< zenmode-enabled >}}
VR puzzle game with a large world, with the idea that you ahve to physically walk everywhere without any artificial movement options such as teleporting or joystick locomotion.
It worked succesfully, as we had playtesters who walked between 1-2km when playing the game, without getting lost or feeling like they had been walking too much.

![your image](Ki4FH3.gif "Main hub. Each of the three portals lead to a level designed by one of us each, focusing on one aspect. My focus was time.")

My responsibilites included shaders/graphics, modifying and fixing the portal system we took from a paper with implementation, tooling, and design and creation of my level.
![your image](orb.gif "These orbs are the objective of the level. Design and shaders by me.")

I also implemented spatial sound for portal, creating a graph between portals to correctly calculate how far each sound source was, and which portal the sound was coming from. This helped a lot with immersion as e.g. you can hear which portals to go through to reach the soud of a radio.

A lot of tooling was needed to create the levels, as every single room has to physically overlap eachother, as they all exist in the same 4x4 meters of physical space.

![your image](mylevel.png "Level editor of my level. Tools were made to make a room, wich overlays the physical space onto the virtual room. Tools were made to connect portals between rooms such that their physical position and rotation is the exact same across the two rooms it connects.")
![your image](mergeconflictme.png "Physical playspace. Note the tape on the ground matching the visual overlay in-game.")
![your image](mergeconflictwalkdata.jpg "Walking data from playtests. You had to walk all over the room to complete the puzzles and explore the world.")
