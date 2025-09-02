+++
title = 'Current indie project, first person cozy nature game'
date = 2024-12-21
draft = false
summary = "WIP 3D open world game about nature and ecology, complex UI."
tags = ['Game Development', 'Personal Project']
+++
This is a very work in progress early production indie game by me and my friend, made in Godot and C#. My friend is responsible for the majority of the assets, tech, graphics and shaders are mostly by me.

{{< zenmode-enabled >}}

It is a Voices of the Void inspired game mixed with cozy games, the idea being a small open world you can explore while observing wildlife, taking pictures, fishing, etc. 
Here is a small gif showing the current WIP game visual style. I contributed the custom made stylized water shader, modified the terrain shader to match our intended style, and a custom grass shader applied on instanced cards.
![your image](grass.gif "Current WIP visuals.")
For the complex game UI, I made multiple systems, including tetris style inventory sytems with smooth spring based rotation animation, which is flexible and can be reused for multiple purporses, e.g. the shops. Also a journal with spring physics based tabs. 
All of the UI is backed by serialized data in a class which is directly serialized to create the save data. Anytime the backing data is changed, this means the savedata is by definition updated, and events are invoked that the UI reacts to.
Item data is done through Godot resources (essentially files) placed in a categorized file structure. This structure parsed on load, creating an efficient representation that allows loading specific item data by id efficiently.
The structure is also used to automatically fill out the content of the journal, meaning it automatically updates based on the content. 

We also have dialogue implemented using Yarn Spinner, which is a dialogue system with a custom language, setup to be able to read and write, and call functions, between the dialogue scripts and the game scripts.
There is also a camera system built on top of the Godot Phantom Camera plugin, that allows switching to different perspectives automatically. Shown here is the FPS perspective switching to the dialogue perspective, the dialogue perspective automatically looking at the currently talking NPC from a third person view. This allows it to switch seamlessly to look at the currently talking NPC.

![your image](fieldbioui.gif "Various UI. Item rotation bounciness is probably a bit overtuned right now.")
The fishing minigame is still heavily WIP, but is inspired by souls like combat and includes timed "parries" along with matching the direction of the fish to avoid breaking the line. 
The fish icon can perform various animations, which have special callbacks that inform the moment of attack, along with the start of the parry window, etc.
Among other things tooling has been designed allowing every fish to have custom behavior during the minigame, and tooling to define the geometry of water areas and which fish spawn there, allowing fish to move freely in the pond.
![your image](fishing.gif "Fishing minigame.")


Currently we are working on implementing wildlife, which will involve creature AI that performs routines in the ecosystem and react to other creatures or the player by fleeing.