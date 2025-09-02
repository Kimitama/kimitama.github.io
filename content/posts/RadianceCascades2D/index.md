+++
title = 'Radiance Cascades 2D Graphics Course Project'
date = 2024-06-07
draft = false
summary = "2D Real Time Diffuse Global Illumination without Temporal Accumulation"
tags = ['Graphics', 'University']

+++
{{< zenmode-enabled >}}

Solo university project where we could implement a graphics technique of our choice, made with C++ and Vulkan.
It is fully dynamic global illumination in 2D, where you can draw lights and walls with a brush.
I implemented Radiance Cascades in 2D from scratch, and got good real time performance at 1080p on a GTX1070, without any temporal accumulation, in the range of milliseconds heavily depending on settings.
This means it is fast enough to to provide real time global illumination for 2D games.
Bounce lighting was also implemented at very little performance cost by caching and reusing radiance from previous frames. 
It contained various optional fixes and optimizations that could be used to dial the performance.
Performance is only dependent on resolution.


![your image](rcimage1.png "In development screenshot. SHowing 8ms for the full pipeline here on a gtx1070, slower than the final version.")

It was built on top of a basic Vulkan engine made by the lecturer, however most of it was ignored or rewritten to properly learn vulkan.
The pipeline consists of many passes, as Radiance Cascades requires raymcarching and merging multiple cascades, and applying the result from the cascade to the scene.
Many of the options modified the render pipeline dynamically, by replacing render passes to try out different options, such as diffferent methods of marching, different methods of merging, different optimization techniques, and options that improved accuracy at a cost to performance.


Sadly i cannot get the project to build anymore so i couldn't get the final images, these are taken during development, performance and quality is improved and can be varied depending on settings.
The ringing that can be seen can be fixed using extra rays, called the bilinear fix, which was implemented at the cost of performance as an option.


![your image](rcimage2.png "Thumbnail.")
