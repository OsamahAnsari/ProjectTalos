---
layout: post
title: Week 4 - Experimentation Continues
---

The fourth week of research involved trying my hand at fixing the issues with the previous Penguins ML-Agents environment and then starting a new ML-Agents tutorial called Hummingbird.

## ML-Agents Penguins Update

This week I attempted to get the Penguins ML-Agent from last week working. After a few hours of messing around with the code and the config files, I realized I did not have enough knowledge to update the project to the latest release of Unity ML-Agents. I decided it would be better if I started another tutorial with a more recent version of ML-Agents. The end goal being that I learn enough about how ML-Agents works to be able to update the package to work with the more recent versions of ML-Agents.

## ML-Agents Hummingbird

After some searching, I found out that the creator of the ML-Agents Penguins Tutorial made an update tutorial for ML-Agents Release 1.0 on the Unity Learn Platform called [ML-Agents: Hummingbirds](https://learn.unity.com/course/ml-agents-hummingbirds). Although this tutorial was not completely up to date with the latest release, it was fairly close. I decided it would be worthwhile to follow along with the tutorial using a slightly outdated version of Unity ML-Agents (ML-Agents v1.4.0 vs ML-Agents v1.0.0). Whereas this tutorial is on the same base release v1, the old tutorial was built on v0 of Unity ML-Agents.

### The Environment

The Reinforcement Learning Hummingbirds tutorial has you setup up an environment and an agent that does the learning. The learning environment consists of a floating island with a trees, some rocks and bushes, and a lot of flowers. The agent in the environment is a brand new hummingbird who does not know how to fly properly or how to drink nectar.  The environment in questions looks like this:
![ML-Agents Hummingbird Environment](/resources/single-training-environment.PNG "ML-Agents Hummingbird Environment")

### The Objective

The objective for this project is simple in explanation, but complex in execution. The hummingbird agent must fly up to a flower, stick its beak inside and drink the sweet nectar from within. Once all the nectar from the flower is gone, the hummingbird must move on to the next flower. Sounds simple right?

Wrong! The hummingbird has 3 axes of movement and 2 axes of rotation and does not know what a flower is or what nectar is. It simply knows that hitting the environment boundaries will result in a reward loss, while drinking nectar will result in a reward gain. However, those words mean nothing to it until it has a chance to explore its environment and learn what those words mean for itself. Once it realizes that flying into a flower gives it a positive reward, it will continue to do so. Similarily, once it realizes hitting walls results in a penalty, it will slowly stop doing so.

For demonstration, here is my horrible attempt at being a hummingbird:
![My Horrible Attempt at Being a Hummingbird](/resources/my-attempt-at-being-a-hummingbird.gif "My Horrible Attempt at Being a Hummingbird")

### How Does it Work?

So you must be wondering, then how does it work? How is the ML-Agent able to do such a difficult task? The answer, with some sensory organs and a learning algorithm. The project uses the Proximal Policy Optimization (PPO) learning algorithm to train the hummingbird.

Here is a snippet of code that allows the ML-Agent to observe its environment:
![ML-Agents Observation System](/resources/ml-observations-system.PNG "ML-Agents Observation System")

The hummingbird is rewarded a small amount for every drop of nectar it drinks (it can drink one drop every 0.2 seconds). However, it is punished for colliding into the environment boundaries, such as the floor or the the invisible sky ceiling. This teaches the hummingbird to drink nectar from the flowers within the closed environment. Sorry, no true freedom for you.

Here is the code for giving the ML-Agent the reward:
![ML-Agents Reward System](/resources/ml-reward-system.PNG "ML-Agents Reward System")

In order to optimize the learning and speed up the process, I created 8 copies of the environment within the Unity project so that they can run in parallel. This allows the ML-Agent to learn 8 times as fast as a single instance of it would be able to. Why you might ask. Since each copy of the environment runs independently, the underlying nueral network is able to attempt a greater number of movements and experience the results in a shorter time frame. 

Here is what the full multi-instance training environment looks like:
![ML-Agents Hummingbird Multiple Environments](/resources/multiple-training-environments.PNG "ML-Agents Hummingbird Multiple Environments")

### The Training

Initially, when trying to run the training command, I was getting an error that the config file was invalid (great, not this issue again). Luckily, after some digging, I realized there was a script provided by Unity ML-Agents to upgrade from the old config file format to the new one. The command is as follows:
```
python -m mlagents.trainers.upgrade_config .\<old-trainer-config>.yaml .\<new-trainer-config>.yaml
```
I input the name of the old trainer config file (trainer_config.yaml) and the name I wanted the new trainer config to have (hummingbird_trainer_config.yaml). That fixed the issue and I was ready to go.

After setting up all the required config files and programming the entire environment and the ML agent's reward system, I was ready to start the training. I can run the python training simulation by using the following command:
```
mlagents-learn .\<trainer-config>.yaml --run-id <unique-id>
```
The trainer-config should be the name you gave to your trainer config file, mine is hummingbird_trainer_config.yaml. The unique-id should be a unique identifier for the traininig simulation. For example, I used the unique id "hb_01", where hb stands for hummingbird and the 01 is a unique id, between 01 and 99 inclusive, representing the training simulation number.

Originally, the training started off very slow and it seemed as though the hummingbird was just flying in random directions. That is because, it was! Since the nueral network had no prior knowledge of what happens when any given action is performed, it had no choice but to try them at random and see what happens.

Here's some footage from the earlier stages of the training session of the hummingbird just vibin':
![Hummingbird Vibin'](/resources/hummingbird-vibin.gif "Hummingbird Vibin'")

After about two hours of the simulation running, the hummingbird seemed to have learned what a flower is and how to drink nectar. Although it isn't the most accurate at aiming for the center of the flower, just yet, it seems to have figured out how to generally get its beak inside the flower and how long it needs to stay to get all the nectar.
![Hummingbird Drinking Nectar](/resources/hummingbird-drinking-nectar.gif "Hummingbird Drinking Nectar")

I can also view the training results in realtime through the tensorboard api by running the following command:
```
tensorboard --logdir .\results\<run-id>\Hummingbird\
```
The run-id is the unique run-id provided to the mlagents-learn command during training. For my training simulation, this would be "hb_01" since that is the run-id I gave it earlier.

Here is what the cumulative reward graph looks for the first two hours of training:
![Hummingbird Training 2hr Graph](/resources/training-2hr-graph.PNG "Hummingbird Training 2hr Graph")

After training the ML-Agent for about 3 hours, it has gotten decently good at finding flowers and drinking nectar, but it is not quite perfect at it yet. I plan on letting the simulation run for a few more hours and then turning it into a game. The plan is once the ML-Agent is finished training, it will be able to compete against a human player to see who is better at collecting nectar. 

## Next Week's Plan

Next week, I plan on returning with the results of many more hours of training and the completed environment where the player can compete against the ML-Agent. I also plan on going back and fixing up the ML-Agent Penguins just so I can experiment with it a bit more. Finally, I plan on diving into the UnityVGDL Framework.

Thanks for reading! Make sure to check back next week!
