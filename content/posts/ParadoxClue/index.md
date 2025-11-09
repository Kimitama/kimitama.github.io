+++
title = 'Combination detective and heist puzzle game with "time travel"'
date = 2024-11-20
draft = false
summary = "Reduced game logic and time into simplified graph allowing reverting anything."
tags = ['Game Development', 'University']

+++
{{< zenmode-enabled >}}
University game project with a larger group in Godot with C# over 8 weeks. Everyone contributed to many aspects of the game, I list my main contributions here.

My biggest contribution is the "time travel system", the game is about figuring out how a crime was carried out, by acting out the crime as the criminal.
As you try out ways the crime could have occurred, and learn new information in form of clues, you have to be able to retrace your steps as the criminal.
I made a system that stores the entire level logic as a graph (what rooms you move through, what you interact with, what doors are open at any given time), and run pathfinding on that graph to ensure the paths you have tried are valid given the information the player has learnt and is assuming.
This then allowed you to retrace your steps by choosing any previous gamestate to return to. It even supported connecting different paths together, though that was cut due to confusion during playtests.
![your image](featuredcopy.jpg "Clue UI with the path system in the bottom right. It shows that on the current path, the player walked from the reception to the fileroom, where they picked up a key, to then walk to the cat in the reception. The key acts as a \"savepoint\" you can return to, unless you later learn there was a witness in the reception that would've spotted you.")

![your image](MGJuBM.gif "Being spotted forces you out of a flashback. I was responsible for the wavy effect in rooms that have witnesses in them, and the starry night transition effect, which was made by preprocessing the starry night by grayscaling it and using the kuwahara filter, and applying a step operation in shader.")

![your image](pKvsAu.png "Footsteps were used to signify the players current hypothesis of what the robber did.")