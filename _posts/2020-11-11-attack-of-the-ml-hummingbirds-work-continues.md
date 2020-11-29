---
layout: post
title: Week 10 - Attack of the ML Hummingbirds Work Continues
---

This week I continued working on my Hummingbird ML Agent based game, which I have now aptly dubbed Attack of the ML Hummingbirds. I will definitely need to improve that name for future weeks. 

## New Mechanics and Testing (~7 hours)

I added a couple of new game mechanics this week to spice up the gameplay a bit. I added a slide, sprint, stun, and speeding up/slowing down mechanics. Together the intention was to allow more dynamic movement of the character so that I can make the ML agents a bit stronger to keep the tension high, but allow the player some more control over their character so they can still have a chance. The values will need to be adjusted over the weeks and be more fine tuned to match the experience I seek to create. 

The slide mechanic makes the player basically move while laying on their back for a brief period. As the intention is to make this game as dopey as possible, I thought it would be a good idea to make it a straight 90 degree change rather than something more realistic. This mechanic is intended to be used by the player in a pinch or to dodge obstacles. It throws the Hummingbirds' NN off pretty hard and buys the player some breathing room, but it comes with a slower speed making spamming it detrimental for progressing through the level. 

![Sliding Mechanic](/resources/sliding.PNG "Sliding")

The sprint mechanic makes the player speed double for a very brief period and then gives them a temporary speed debuff. The intention of this is to allow the player to get out of a sticky situation or close certain gaps quickly with the downside that they will be moving significantly slower afterwards for a short period of time. This can give you some major breathing room, but if you're not careful the Hummingbirds will catch up just as fast. 

The stun mechanic makes the player stunned upon colliding with an obstacle. I added this as I felt without it the player could haphazardly traverse the area and still be safe from the Hummingbirds. But this mechanic puts more emphasis on the need to avoid the obstacles or to face certain demise by the Hummingbirds. I kept the stun short, as not being able to move sucks, but I added an additional speed up process after where the player slowly picks up speed again until they reach their base running speed. 

The speeding up/slowing down mechanics are added to make transitions between these different speeds more subtle and less jerky. It gives the added bonus of allowing me to make more dynamic effects like I mentioned with the stun effect.

I spent a lot of time testing and tweaking these mechanics as I was making them. The one that probably took me the longest was the slide mechanic as it took me way longer than I ever hoped to remember how to use Quaternions and Euler Angles in Unity. I tried many different methods and I kept running into bugs and weird behavior. Luckily, I eventually I figured it out and now it works as intended. 

## Obstacles (~1 hours)

As I mentioned earlier, I added obstacles to the game. These various obstacles can vary from logs or rocks to trees and other bigger obstacles. I tried creating a bunch of different ones with different dimensions to create unique combinations of hazards along the path. At the moment I am using a box collider for most of them as the mesh collider wouldn't stop the player before, but now that I implemented a stun mechanic, I plan on modifying them next week to use mesh colliders. I also plan to continue to make more obstacles as I continue to work. At the moment I feel like they are okay but not great. 

![Obstacles](/resources/obstacles.PNG "Obstacles")

## Visual Scene Improvement (~2.5 hours)

I spent a good chunk of time improving the scene visually and fleshing it out more. I searched for and found more free assets to use for my game. I also modified some old ones to try and fill up the scene some more. It is still far from finished, but it feels a lot less empty. 

![Updated Game Scene](/resources/updated-game-scene.PNG "Updated Scene")

## Hummingbirds and Training (~2 hours)

I also imported over the Hummingbirds this week. I messed with their parameters to make them a little bit more terrifying and chaotic to keep the game interesting. I also did some tweaking to the environment and them as well as the player movement to give them a bigger advantage as originally they were not performing well enough.

After messing around with them for awhile, I realized they were far too inaccurate with the new map and flower type. I messed with a lot of the parameters and then decided to train them again. I decided to let them train for a few hours and see how they perform next week. But at the moment, even when the player is standing still, they tend to miss fairly often. Hopefully by next week, they are a lot more menacing and demand more action on the player's part. 

## Next Week's Plan

Next week I plan to continue to tweak the game mechanics and the Hummingbird parameters. I also plan on continuing to flesh out the environment and adding more obstacles. Also, I plan on continuing the implement the game logic and allow the player to being taking damage when the hummingbirds drink nectar from the flower. Finally, if I have time I plan to begin working on UI elements. 

Thanks for reading! Make sure to check back next week!
