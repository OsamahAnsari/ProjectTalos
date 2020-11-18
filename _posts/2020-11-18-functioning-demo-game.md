---
layout: post
title: Week 11 - Functioning Demo Game
---

This week I pushed to make a fully functioning implementation of the game. The focus was not proper balance, although it was slightly touched on, but rather to have a game that is functioning on a basic level with all the intended end features.

## Functioning Game

I spent all of my time this week converting the game into a fully function version of the game I had last week. This entailed finishing the ML Hummingbird's training, adding functioning game logic for starting and ending the game, functioning UI elements, the logic to actually have the Hummingbird's impact the player's health, and tuning these values to be in a generally playable spot. I also had to extend the map, finish fleshing it out, and adding additional obstacles types to increase the variety and challenge of moving through the map.  

I noticed even after training the ML Hummingbird's even further, they were underperforming. However, after studying their behavior for possible issues, I noticed that the biggest cause of them not being able to collect nectar was them simply shoving each other to try to get to the nectar. It was an all out brawl for the nectar. Although it is funny to watch them push each other around, it doesn't result in much nectar collected making the game too easy. After disabling collisions between the Hummingbirds, I quickly noticed they became efficient nectar collecting machines once again. I still need to fine tune their speeds and weights in the future.

![New and Improved Hummmingbirds](/resources/new-hummingbirds.gif "New and Improved Hummmingbirds")

I also extended the length of the map and fully fleshed it out with environment and obstacles. It now looks like a forest consistently throughout the level rather than just at the beginning of the level. The new obstacles are also purposely places in a more tricky layout requiring more fast reactions from the player lest they get stunned. 

![New Updated Scene View](/resources/updated-scene.PNG "New Updated Scene View")

I also added the logic for the game UI, the Hummingbird's interactions with the player's nectar, the game win/lose conditions, and additional functionality that the game needed to be playable. In the process, I made some of the older scenes unusable, but they are no longer needed so I don't see it as a major issue. There are also still a decent number of bugs caused by some weird uneven ground leveling. Also some of the obstacles still aren't set at the appropriate distances, but these can be fixed for the next week. 


## Working Build

Currently the Unity build process keep failing on my computer. I plan to come back and update this post to include a link to a download for the working Windows/Mac Builds.

In case anyone is curious, the error I keep getting is the following:
``` Exception: C:\Program Files\Unity\Hub\Editor\2019.4.13f1\Editor\Data\il2cpp/build/deploy/net471/il2cpp.exe did not run properly! ```

## Next Week's Plan

Next week, I plan on making the final touches to the game. Balancing stats and abilities, properly spacing out obstacles, tuning the hummingbirds to be menacing but not overwhelming, etc. Hopefully it will do a decent job of demonstrating the concept of game centered around ML Agents. The goal was not to make a full fledged fun game, but rather a short demo that highlighted what could be done with ML agents in games. 

Thanks for reading! Make sure to check back next week!
