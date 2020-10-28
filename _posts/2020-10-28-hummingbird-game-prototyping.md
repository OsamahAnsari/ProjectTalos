---
layout: post
title: Week 8 - Hummingbird Game Prototyping
---

This week I spent a good deal of time catching up on where I fell behind last week. I spent this week making a basic prototype to see if my game idea would even be feasible.

## Game Idea (~1.5 hours)

I spent some more time this week planning out an idea for the game concept. The game idea I had was to have a player (a flower) heading home from work (collecting sunlight and making nectar) when he suddently gets attacked by a hoard of hummingbirds. The hummingbirds are trying to drink the nectar from the player. The player must run home to its family before all the nectar is collected is lost. The game was eventually intended to take place in a forest where the player must run and dodge hoards of ML agent hummingbirds as they swoop down from the skies.

## Basic Prototype (~13.5 hours)

I spent the entirity of this week reworking old code and fixing bugs while working on creating a basic prototype. I had to rewrite a lot of the previous functionality for the Hummingbird Agent to allow proper functionality with the new game. I also needed to write a new GameManager script to handle the game state set up.

I spent a lot of time (~3 hours) trying to fix issues with the flower collider. Unity does not like having rigidbodies and mesh colliders interacting together. I tried reworking the mesh collider into something else, but Unity didn't have anything but the basic collider shapes for 3D. At first I tried recreating the flower collider using basic shapes, but it was taking forever and wasn't really working. After trying many online scripts and other methods for fixing the issue, I just gave in and changed the collider to convex making it work, but significantly more inaccurate. Although in the end this is still not perfect and I will probably have to rework it. 

I spent a great deal of time (~8 hours) reworking the old scripts, setting up the new scripts, and modifying the environment and Hummingbird GameObject for the basic prototype. I had to create a new PlayerMovement, PlayerFollow, and GameManager scripts. I ended up more time than I would like to admit googling how to get a proper working Unity3D player movement script as mine did not work as intended, resulting in some weird physics upon collisions. The current one still isn't ideal either, but I didnt want to spend too much more time on getting those working. I set up a basic environment which allows the player run from the hummingbird and has the hummingbird chase the player around trying to drink the nectar. I had to rework the whole flower plant system because I didn't want an entire flower plant sticking out of the player's head, but rather a singular flower. This required more work than I expected because the script was set up with that specific design of the flower plant in mind. I still occasionally run into bugs where the Hummingbird can't find a flower to drink nectar from. I feel I will have to revist the script again to rework how it searches for flowers.

I also lost a decent amount of time (~1 hour) after setting everything up trying to figure out why the Hummingbird was not moving. I tried looking at the scripts, checking key variable values and messing with its rigidbody settings. However, when I eventually realized I forgot to attach the nueral network to the Hummingbird, I felt extremely stupid. Once attached, I wasn't surprised when the Hummingbird began working as intended.

[Basic Hummingbird Game Prototype](/resources/attack-of-hummingbird-prototype.gif "Hummingbird Game Prototype")

Currently, the Hummingbird can keep up with the player, but struggles to get the nectar. I will try to tweak and fix this next week. I will also add some more Hummingbird agents to add more pressure to the game.

I spent some time (~1.5 hours) trying to find and add more textures from the Unity Asset Store into the environment. I found a couple of cool assets but I could not get the assets to load up properly into the Unity project. The 3D model would load, but the texture would never display. All I would see was a pink colored 3D model. I tried fixing this in multiple ways but couldn't figure out how and decided to leave it for a future time. 

## Burnout and Next Week's Plan

After working with the Hummingbirds for the past 5-6 weeks, I am starting to suffer burnout on this project. I don't know if it has to do with the constant bugs Im running into or just dealing with the Hummingbirds in general. But, it is making it really hard to focus on the project on a weekly basis. Depending on how I feel over this weekend, I will probably decide whether to continue this specific game or to switch to something else I find more interesting. 

If I continue with the Hummingbirds, Im gonna fix up the movement and the camera scripts. Im gonna set up a UI and add some sort of Hummingbird spawner that will add more hummingbirds as you go on further into the level. I also plan on fixing up the colliders to make getting the nectar easier for the Hummingbird. 

Thanks for reading! Make sure to check back next week!
