---
layout: post
title: Week 5 - Training Results, New Training, and The Future
---

The fifth week of research involved finishing up the ML-Agents Hummingbirds training. 

## ML-Agents Hummingbird: Training Results

The ML-Agent has made significant progress by the end of its training session which took a total of about 6 hours to complete. However, I was training using CPU only, so the required time could be significantly shorter. But before I show you the end results, I feel it fitting to remind you of how the Hummingbird was performing early on in its training.

### Where We Began

First hour and a half of training:
![Hummingbird Vibin'](/resources/hummingbird-vibin.gif "Hummingbird Vibin'")
The Hummingbird just aimlessly hovers pondering its existence.

After about two hours of training:
![Hummingbird Drinking Nectar](/resources/hummingbird-drinking-nectar.gif "Hummingbird Drinking Nectar")
The Hummingbird has discovered nectar and realized it is the drink of the gods. Although it is still not very good at getting to it, yet.

A quick graph of the first two hours of training:
![Hummingbird Training 2hr Graph](/resources/training-2hr-graph.PNG "Hummingbird Training 2hr Graph")
Look at that rapid growth! I knew he had it in him!

### How Far We've Come

Now it's about time I show you the fully trained agent. Here is an uninterrupted full minute of its nectar collecting spree:
<iframe width="560" height="315" src="https://www.youtube.com/embed/TJhCQ9WWLTM" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="allowfullscreen"> </iframe>
Look at him go! They grow up so fast. 

In all seriousness, the Hummingbird agent has significantly improved by the end of the training session, after 5 million steps, than where it was 2 hours in, at approx. 1.5 million steps. Although it isn't perfect, it generally has no issue getting its beak into the flower and staying long enough to collect the nectar before moving on the next flower. 

Now let's check out the graph of its progress throughout the training session.
![Hummingbird Completed Training Graph](/resources/training-completed-graph.PNG "Hummingbird Completed Training Graph")
From this we can see the Hummingbird agent started off very slow, not making any significant progress for the first approx. 1 million to 1.2 million steps (~1 hour). I assume this slow progress can be accounted for by the Hummingbird not accidently stumbling into some nectar. However, once the agent discovered nectar, it made progress significantly faster. The agent went from getting an average of 0 flowers at 1 million steps to an average of 34.26 flowers at 2 million steps. After about 2.5 million to 3 million steps, the agent's progress started to level off. At this point the agent averaged anywhere from just under 25 flowers on the low end to just over 50 flowers on the high end. Generally, it got about 38 flowers worth of nectar a run. Although this range may seem large, the disparity in average nectar collected can be attributed to the random spawn position of the Hummingbird agent at the start of any given run. 

All in all, I think it turned out to be a success. The Hummingbird agent was able to learn to collect a considerable amount nectar from flowers within only 5 million steps. This may seem like a lot, but consider the fact that any living thing with a brain is a product of millions of years of evolution, while the Hummingbird agent learned a fairly complex task in merely 6 hours. For some added perspective, fruit flies have about 25 thousand nuerons, while the hummingbird agent only has 512 nuerons. But then again, the hummingbird agent doesn't have to account for living.

## ML-Agents Hummingbird: The Game

After completing the training, I learned that you can connect the trained nueral network to the game object under Behavior Parameters. Then you can run the agent outside of training mode and watch it show off what it learned. As a fun experiment, I turned the project into a game where you compete with the ML agent to see who can collect a certain amount of nectar faster. 

During this process, I noticed some bugs in my earlier code that only seemed to occur outside of training mode. After spending an hour or so fixing them, I proceeded to setting up a new scene with a player and opponent hummingbird agents. I created a basic game manager class and imported the tutorial provided UI elements. Once I was finished setting everything up, I had a working game where a player could compete against the Hummingbird agent to see who was the better at collecting nectar.

Here is my best attempt at trying to beat the Hummingbird Agent:
<iframe width="560" height="315" src="https://www.youtube.com/embed/ByaFSv-F5Qg" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="allowfullscreen"> </iframe>
The Hummingbird agent was easily able to get 8 flowers worth of nectar in the time it took me to get only about half of that. Assuming the game went on longer, the agent probably would have only widened the gap. That should make it apparent that the ML agent fully learned the task it was created to.

In case anyone wants to try their hand at beating the Hummingbird agent, I will leave a Unity build with the game controls below. Fair warning, the controls are pretty janky (it wasn't intended to be a good game).

## ML-Agents Penguins

After completing the ML-Agents Hummingbirds tutorial I thought I would be able to go back and modify the old ML-Agents Penguins project to work. However, after about an hour to an hour and a half of tinkering with it. I realized that I would need to make far too many changes to even have a runnable version. At that point, I decided it wasn't really worth the extra effort and should just be left as a relic of the past. 

## Wrapping Up ML-Agents Hummingbird

After a discussion with Austin last week about the capabilities of machine learning agents, I wanted to try two final things before I closed the book on this project. I wanted to see if the ML agent would be able to handle a larger environment with less flowers and I wanted to test the impact of GPU acceleration on training time. The reason for the former being that if the ML agent could perform well in a larger environment with less flowers, then theoretically, machine learning agents could be used on more open world games. The reason for the latter being more self explanatory. 


### New Training Area

For the new arena I made is two times larger in the x and z dimensions. I also deleted all the flower clusters and scattered some single flower plants across the island. The number of flowers on the island is smaller by a magnitude of over 100, as the previous arena had clusters of flower plants in either 3 or 5 and had tons of those clusters. I then duplicated this arena, 7 more times and had 8 of them run in parallel like before.

Here is an aerial view of the larger training area:
![Hummingbird Larger Training Area](/resources/new-larger-training-area.PNG "Hummingbird Larger Training Area")
As you can see, there is only one flower plant in a given area of the the new island. They are significantly fewer and have far more distance between them.

### Starting the New Training

Once I had the new training scene setup, I ran a new training session, using GPU this time, with the training being initialized from the previous session. Here is the command I ran:
```
mlagents-learn .\<trainer-config>.yaml --run-id <new-unique-id> hb_02 --initialize-from <previous-unique-id>
```
The trainer-config is the name I gave to my trainer config file, hummingbird_trainer_config.yaml. The unique-id, similar to last time, should be a unique identifier for the traininig simulation. For example, I continued the convention from before and used the unique id "hb_02", where hb stands for hummingbird and the 02 is a unique id, between 01 and 99 inclusive, representing the training simulation number. Finally, the previous-unique-id is simply the unique id of the previous session that I want to initialize my nueral network from.

### New Training Results

Unsurprisingly, the GPU accelerated version of the training session finished in less than half the time of the original. While the original training session took over 6 and a half hours, the GPU accelerated one only took 2 and half hours. As such, if possible, ML agents should always be trained using GPU acceleration. 

Additionally, the ML agent performed comparable for to the original, despite the flower plants being significantly farther away. This shows the the ML agent was able to learn to prioritize heading straight for the next flower even if it is far away. Here is a short clip of the new fully trained agent:
<iframe width="560" height="315" src="https://www.youtube.com/embed/3MtflsuzuwY" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen="allowfullscreen"> </iframe>
As you can probably see, it is fairly similar to the last fully trained agent, except this one is a lot faster moving from one flower plant to the next. I assume it learned to optimize its path from one flower plant to the next over larger distances during this training session.

Let's also look at the comparison Tensor graph for sanity's sake:
![Hummingbird Completed Training on Larger Area Graph](/resources/training-complete-2-graph.PNG "Hummingbird Completed Training on Larger Area Graph")
As you can see, although we started a new training session, the Hummingbird agent's nueral network was initialized using the old training result. As such, the increase in score through the training isn't too significant. Furthermore, despite the flowers being further and significantly far between, the new Hummingbird agent managed to maintain a decent average of about 35 flowers. However, this score is lower than the average of the original training session, but this can be attributed to having the same number of steps for both training sessions yet requiring the Hummingbird to travel more in the second.

### Conclusions

ML Agents are able to complete complex tasks given the proper the reward system and the appropriate amount of time to learn. Even though the first training session started off very slow, once it discovered the objective, it progressed significantly faster. Additionally, these agents can be moved to new environments and be re-trained, with previous knowledge intact. This allows a developer to start training an agent on a simple scene and eventually move it to a significantly more complex one over time, letting the agent learn each aspect one at a time.

Also important note, if possible use GPU acceleration for training ML agents. It results in a significantly shorter training time.

## Next Week's Plan

I'm not exactly sure where to go from here. I think next week I am going to reach out to more stakeholders and being experimenting into creating a game with ML agents. This is because the two previous stakeholders I reached out to regarding ML in testing pointed out three major flaws:
1. Training an ML agent for each game would require too much time and computing power. At the moment it is simply easier to create a custom AI for testing games.
2. How would a ML agent even know if it discovered a bug? It can't. There is no way for an ML agent to test a game, come across a bug, and realize that the resultant behavior was unexpected.
3. There are already many plugins and proprietary software available to developers to test for crashes. These programs give very detailed information about a crash. As such, there isn't really a need for ML agents in this area.

Hearing that was a bit dishearting, but I hopefully will have something figured out for next week. 

Thanks for reading! Make sure to check back next week!

## ML-Agents Hummingbird: WebGL Build

The WebGL Build of the game is below. However, I have noticed that for some reason the nueral network doesn't properly work in WebGLs resulting in many situations where the Hummingbird agent just stops working. I would build a version for Windows/Mac but I don't think it is really necessary -- the videos and WebGL should get the idea across.

Controls:
 - Forward/Left/Backward/Right: W/A/S/D
 - Up/Down: E/Q
 - Pitch Up/Pitch Down: Up Arrow/Down Arrow/Down
 - Turn Left/Right: Left Arrow/Right Arrow

<iframe width="560" height="315" src="/resources/WebBuild/index.html" style="border:0px #000000 none;" name="ML Agents Hummingbird" scrolling="no" frameborder="1"> </iframe>
