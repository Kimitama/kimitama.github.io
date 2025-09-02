+++
title = 'Rain World Rendering Recreation'
date = 2022-01-01
draft = false
summary = "Recreating efficient 2D palette based renderer with dynamic shadows"
tags = ['Graphics', 'Personal Project']

+++
{{< zenmode-enabled >}}
A project to learn how rendering in Rain World works by recreating it in Unity, using Rain World Assets.
Contains Rain Worlds palette rendering, shadowcasting, and dynamic lights, which were slowly added throughout a long period as I wanted to learn specific aspects of their renderer.



![your image](rwshadow2.png "a.")

It was made by analyzing how their color palettes work (helpfully described by their community), so I could unpack them in shader.
I impleented lighting based on the very short description posted by the developers on how sun lights work, extending it to work with cloud shadows and point lights.

![your image](rainworldrendering5.png "My recreation, sun shadows are cast from dynamic objects using 1 sample per pixel, wiht shadow distance increasing by depth. Cloud shadows are rendered as scrolling noise texture that applies shadows.")

![your image](tentaclePlants_1.png "Input data that rain worlds renderer works with. Most data is packed in red channel, though other channels are also used in the game which I have ignored in my recreation.")

![your image](rwrendering3.png "I also added dynamic point lights as I assume theyre implemented in Rain World, here a light is placed at the gizmo, showing a strong shadow cast on the right drill.")
![your image](rwrendering4.png "Dynamic point light moved to bottom right corner of the same scene.")


