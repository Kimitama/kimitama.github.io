+++
title = 'Masters Thesis on Radiance Cascades SSGI with Box Dragon'
date = 2025-06-26
draft = false
summary = "Real Time Diffuse Global Illumination without Temporal Accumulation"
tags = ['Graphics', 'University']

+++
{{< zenmode-enabled >}}
This was a collaboration with Box Dragon to create global illumination fit for their games.
Using Radiance Cascades and screen-space information, we managed to create convincing dynamic diffuse global illumination in screen-space, running at 6ms on a 9070xt without any temporal accumulation. The fastest performance mode ran at around 2ms though lacked accuracy.
Performance could be significantly improved using temporal accumulation sadly we did not have time to experiment.
![your image](particles.png "Lit solely by emission from particles. Performance is fully independent of amount of lights.")
The technique is able to capture high frequency occlusion, due to the dense probe grid (density varies on distance to light source). 
![your image](bigsphere.gif "Showing shadows and occlusion updating instantly from moving the emissive sphere. Notice even small shadows from the items on the bar are captured.")


![your image](manyparticles3.gif "GIF version of previous image.")
![your image](manyparticles4.gif "Smaller particles. Turned particles on and off to show instant response and all light is from the small particles.")

A big part of the project was optimization, as we went from an entire second per frame with the proof of concept, down to a few milliseconds per frame. This involved optimizations in the pipeline, algorithm, register pressure, wave intrinsics experiments, and latency hiding. 
![your image](RC.png "Lit solely by rainbow light in the ceiling, with very high settings. Notice how parts of the dragon appear differently colored, due to either the normals facing specific colors of the rainbow more, and at times some colors getting occluided. See the neck under the chin, where the light is greed due to the purple light getting occluded by the head.")

Accuracy was important, and throughout we compared to pathtraced results and found in our test scenes screen-space could well approximate pathtracing, assuming relevant info was on-screen as is mostly the case in the game this was designed for.
![your image](base.png "Lit by the pipeline we developed using very high settings for comparison. Wall in the background is too blue due to an artifact inherent to the ray-marching method we used that we did not have time to fix in time. Notice light is cast across the entire screen and soft shadows are cast from all objects.")
![your image](Bistro1Bounce.png "Pathtraced reference.")
It scales downwards using multiple settings. The method at lower settings is still more than sufficient for e.g. bounce lighting and some emissive effects, as lighting the scene using solely emission highlights the artifacts here.
![your image](medium.png "6ms @ native 1080p, 9070XT")
![your image](low.png "2ms @ native 1080p, 9070XT.")

It was integrated into Unreal Engine 4 as a plug and play plugin, involving significant work figuring out how to properly hook into Unreal Engines rendering pipeline.
