+++
title = 'Codeveloped indie game on Itch.io'
date = 2024-12-20
draft = false
summary = "Contributing Unity rendering modifications, shaders, rope physics, procedural animation, and general support."
tags = ['Game Development', 'Personal Project']

+++
{{< zenmode-enabled >}}
A metroidvania style indie game I contributed a lot to, designed by my friend.
I am responsible for the many technical systems in the game, such as custom robust performant rope physics with stiffness and friction, modifying the Unity 2D URP pipeline source to achieve the desired lighting with cel shading, various shaders, and tooling.
Made in Unity.
![your image](roakamitsuno.gif "A boss fight showcasing the rope physics. ")

The rope physics system is a verlet integration style system with constraints between nodes. Technically supports cloth physics aswell (a cloth is just a grid of nodes with constraints).
In addition to basic distance constraints between nodes, a stiffness constraint is added, ensuring the angle between nodes doesnt get too high. This is important for using it for procedurally animated creatures, as it is essentially what acts as the skeleton on the body, avoiding it folding inside itself.

Friction and collision with arbitrary unity colliders was also added.

Also seen is simple water simulation for puddles, shaders for basic fog and waterwallfs, and the cel shaded light.

The ropephysics system is very flexible, being used for scondary movement for the boss. The boss animation consists solely of animating key points, namely the hip, torso, and head, with the rest being procedurally moved using the rope physics which are constrained to key points.
The legs are procedurally animated using very simple custom IK, with the target position changing whenever the leg is stretching too much, which causes the illusion of the creatures walking.

All of these systems run well enough that multiple creatures with multiple simulated ropes can run around in the game world at any time.

![your image](roa1ffmpeg.gif "Typical gameplay showing off two creatures, both making use of my physics systems. The lizard enemy can be seen stumbling occasionally as the player jumps over it or hits it.")

[Roa on itch.io](https://ressii.itch.io/roa "")
