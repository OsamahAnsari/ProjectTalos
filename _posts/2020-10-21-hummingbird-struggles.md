---
layout: post
title: Week 7 - Hummingbird Struggles
---

This week I didn't have time to get much done. With having to study for two midterm exams on the this Tuesday (Oct. 20), a project for another class, and having to correct the bugs in my old EECS 482 projects to make them exam ready, I was extremely busy. I also just haven't been getting great sleep the past week due to being swamped in stuff to do (4-5 hours a night). However here is a brief outline of the little progress I made this week.

## Trying to Implement Escape the ML Hummingbirds (~8-9 hours)

Last week, Austin suggested I create a game where the player (a flower) must run from the ML agents as they chase you down. I thought this idea was super fun and I could put many different twists on it. I spent some time planning out the idea I wanted to prototype. However, I planned on going for the bare basic implementation this week. 

After working on trying to setup a scene where the player (a flower plant) could move around freely trying to avoid the Hummingbirds as they decended upon you, the problems began. As soon as I ran the game, I noticed two major issues. 
 1. The Hummingbird was flying endlessly upward into the sky
 2. I was getting a ton of errors in the console.

The first of the two issues was fixed by putting the Hummingbird in Training Mode. However, this is not how the script is intended to work. The fix was simply a bandaid hiding a bigger bug in the code. I intended to come back and fix this as it would be a big endeavour having to look through all the scripts and trace the issue down.

The second issue was caused by the Rigidbody I attached to the variant Flower prefab I made. Unity was complaining that I put a Rigidbody on an object with a Mesh Collider, something they no longer supported. The suggest fix was to make the Rigidbody Kinematic. Seemed simple enough, so I went ahead and did so. 

Then I tried running it again and I couldn't get the player to move at all, I thought this had something to do with my movement script, so I did some googling to make sure I didn't forget how to write a basic Unity 3D movement script. I later realized it was because I changed the Rigidbody to Kinematic. Meaning I was stuck, I needed to remake the flower collider or mark them as convex (not optimal). Temporarily, I opted for that solution.

After "fixing" that issue, I realized the multitude of problems I was facing were caused by the way the Hummingbird Agent script was written. It was created with the intent to mostly focus on training and it is interwoven into many areas of the code, essentially breaking it when trying to use it for other purposes. I've spent the rest of the time trying to rework this code into something more usable. It is still a work in progress.

## Next Week's Plan

Hopefully, by next week I'll have the bugs worked out and a functioning prototype for the game. I probably won't bother with aesthetics or any other polish stuff unless I find the game fun and have extra time. I might also need to retrain the ML agent to adapt it to the new moving target.

Thanks for reading! Make sure to check back next week!
