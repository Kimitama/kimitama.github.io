+++
title = 'Current indie project, first person cozy nature game'
date = 2024-12-21
draft = false
summary = "WIP 3D open world game about nature and ecology, complex UI."
tags = ['Game Development', 'Personal Project']
+++
Very work in progress, here is some current features. For the visuals, no assets are made by me, procedural animation and most shaders made by me.

{{< zenmode-enabled >}}

Custom water shader, grass shader, modified terrain shading.
![your image](grass.gif "Current WIP visuals.")
The game has complex UIs, including tetris style inventory sytems with smooth spring based rotation animation, which is flexible and can be reused for multiple purporses, e.g. the shops. Also a journal with spring physics based tabs, the content of which gets automatically generated based on the data for collectables such as fish, the same data that is used to define the items in the inventory and the fish in the ponds.
![your image](fieldbioui.gif "Various UI.")
The fishing minigame is still heavily WIP, but is inspired by combat and includes timed "parries" along with matching the direction of the fish to avoid breaking the line. Among other things tooling has been designed allowing every fish to hav custom behavior during the minigame, and tooling to define the geometry of water areas and which fish spawn there, allowing fish to move freely in the pond.
![your image](fishing.gif "Fishing minigame.")

Visit the [Hugo](https://gohugo.io) website!