---
layout: post
title: Week 9 - Aesthetic Work Begins, Prototyping Continues
---

This week I spent the majority of time fixing up scripts and adding many assets to the project. As a result, this week's project is significantly more visually appealing. 

## Unity Asset Struggles (~6.5 hours)

I spent the first several hours of this week dealing with Unity Asset issues. My issue was in regard with importing any Unity Asset I could find for free on the Unity Asset store. Every asset I imported would appear with pink materials and not properly load textures. I could not figure out what was happening for the longest time. I think I spent more than 2-3 hours googling about the issue with no avail. Luckily, I thought it would be a good idea to ask my friend who has significantly more Unity 3D experience than I do. After spending about another hour of troubleshooting in Unity, we realized the issue was resulting from incompatible materials caused by these assets not using materials set up for the Universal Render Pipeline. We discovered that Unity had a button (Edit->Render Pipeline->Universal Render Pipeline->Upgrade ... Materials to UniversalRP Materials) that would automatically upgrade the materials to a compatible one. This fixed the issue for the asset we were testing on when we discovered it. 

However, as I continued to add more assets from the store, I quickly realized this was not an universal solution for this issue. It turns out Unity cannot upgrade any assets that do not have a defined a conversion function for its shaders to upgrade the materials to UniversalRP compatible materials. As such, any asset that had custom shaders (i.e. not one of the Unity default ones) and didn't have specific functionality for upgrading to UniversalRP, Unity could not upgrade them and as such they could not be used in my project. I spent a good chunk of time looking through assets, trying to convert them, and realizing they couldn't be used. However, in the end, I found a good few assets that I was able to convert and could use for my project.  

## Scene Creation and Improving Scripts (~5.5 hours)

After getting an acceptable amount of free assets, I began making a scene more similar to what I envisioned for the project. I essentially created a scene where the player is running through a forest in the middle of the night. The player model is now a humanoid t-posing with a giant flower on his head. 

![New Player Model](/resources/new-player-model.PNG "New Player Model")

I created a brand new flower collider from scratch using a bunch of cube colliders. Since it is no longer a mesh collider on a GameObject with a Rigidbody, it solved the weird issues I was running into last week.

![New Flower Collider](/resources/new-flower-collider.PNG "New Flower Collider")

I also created a moon using 3 spheres and applied some special materials to it to give it a nice glow. The extra two spheres were to add the dark pools that you can typically see on the moon. 

![New Moon](/resources/new-moon.PNG "New Moon")

I set up a full environment with a dirty path, trees, bushes, stones, and clouds to create the feeling of a forest. I also added a skybox that made it night in my game. As a bonus, it came with a nice night sky with stars texture. 

![New Game Scene](/resources/alpha-2-scene.PNG "New Game Scene")

Finally, I improved a lot of the scripts I already had to make player movement more smooth and to add a jump mechanic. I also made camera movement much more smooth and accurate to the player's movements. Finally I continued working on the GameManager, setting up more of the features necessary to run the game. I began setting up win conditions and starting states.

![Gameplay Update](/resources/alpha-2-basic.gif "Gameplay Update")

## Basic Prototyping (~0.5 hours)

I did some very basic prototyping with the new jump mechanic and the new flower model. It seems to work okay, but both things definitely need some tweaking and work before next week. I feel like until I add obstacles and the health decrease, the game won't truely be testable or "fun". 

## Next Week's Plan

Next week I plan on continuing to flesh out the scene and adding the Hummingbird back into the scene with the newer functionality. I also plan on adding obstacles that the player will have to dodge as they avoid the ML Agents Hummingbirds on the way to home. I want to eventually add a dive/slide mechanic where you can go under obstacles. Also, I'm thinking of adding a sprint mechanic that will give you a temporary speed boost, but after it runs out you will run slightly slower for a period. As such it is intended to be a mechanic to dodge the Hummingbirds last second. Finally, I want to flesh out the scene more visually adding more forest like assets to add to the believability of the game. 

Thanks for reading! Make sure to check back next week!
