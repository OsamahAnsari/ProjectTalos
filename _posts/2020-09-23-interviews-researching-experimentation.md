---
layout: post
title: Week 3 - Interviews, Researching, and Experimentation
---

The third week of the research was pretty relaxed compared to last week. This week I reached out to some potential stakeholders and began experimenting with the [Unity ML-Agents Toolkit](https://github.com/Unity-Technologies/ml-agents).

## Small Update on Contacting Stakeholders

On Thursday, September 17, 2020, I reached out to eight different possible stakeholders from either the video game development industry or the artificial intelligence industry. I am happy to say I got a response back from three of them. Depending on how my research goes in the next two weeks, I might reach out to a couple more potential stakeholders in the upcoming weeks.

## The General Video Game AI Framework (GVG-AI) and Unity

I started off researching into the [GVG-AI Framework](https://github.com/GAIGResearch/gvgai/wiki) created by the people behind the [General Video Game AI Competition](http://www.gvgai.net/). I quickly realized the framework was built in Java and only supported controllers and models programmed in Java. Having not programmed in Java since the early years of high school, I was a bit disheartened. However, before looking for another framework, I decided I would read through the extensive documentation with the end goal being to see if I could port it over to C# and Unity. 

After reading through a decent chunk of the documentation, it became blatantly obvious that I was in over my head. I did not have the machine learning background necessary to port over such a massive framework. Especially, since I can't even remember the syntax for Java, making the entire process seem even more difficult. Prior to moving on, I thought it would be a good idea to search Google to see if anyone else had already ported the code over to C#/Unity. Luckily, I managed to find a research paper by some PhD students at the University of Copenhagen covering their Unity Framework, [Unity Video Game Description Language (UnityVGDL)](https://github.com/pyjamads/UnityVGDL).[^fn-unityvgdl_paper] 

## Unity Video Game Description Language (UnityVGDL) Framework

UnityVGDL combines the "GVG-AI Framework's Video Game Description Language (GVG-AI VGDL) ontology with the Unity ML-Agents Toolkit." Essentially, it implemented the underlying language system that the GVG-AI Framework used to describe games and combined with the Unity ML-Agents Toolkit to create a wrapper for Unity ML-Agents which allows it to play a wider array of games defined with VGDL.

Although I understand the higher level concepts, before proceeding I thought it best that I research more into what exactly a Video Game Description Language (VGDL) is. As such, I turned to the paper where the term originated, [Schaul, Tom. “A Video Game Description Language for Model-Based or Interactive Learning.” 2013 IEEE Conference on Computational Inteligence in Games (CIG), 2013, doi:10.1109/cig.2013.6633610.](http://people.idsia.ch/~tom/publications/pyvgdl.pdf) 
- The paper described VGDL in great detail, explaining its higher level concept, the syntax, its features, and some classical, well known, Atari games encoded using it. On a more basic level VGDL, designed by Tom Schaul, is a language that describes games in a very concise manner. The description of any given video game is broken into four sections:
  1. SpriteSet - Defines all available sprites for the game, including their parameters and display settings.
  2. LevelMapping - Defines relationships between characters, used in the level definitions, and the available sprites.
  3. InteractionSet - Specifies what events occur when two sprites of a given type collide in the game.
  4. TerminationSet - Specifies the end conditions of the game, indicating whether the player wins or not.
- **Big Takeaway:** VGDL can be used to describe most games in a generalized form, which in turn allows AI to easily interface them. 

Great, now I have a good idea of what VGDL is, but how does the UnityVGDL Framework use it to allow ML AI to interface with a wide variety of games? For that, I turned to the paper on the UnityVGDL Frame, [Johansen, Mads, et al. “Video Game Description Language Environment for Unity Machine Learning Agents.” 2019 IEEE Conference on Games (CoG), 2019, doi:10.1109/cig.2019.8848072.](https://ieee-cog.org/2019/papers/paper_209.pdf)
- The paper discussed the process of porting over the VGDL Framework used by the GVG-AI Framework with some tweaks. They explained how they had to make some underlying changes to the structure to make porting easier and to get around some of the compatibility issues with Unity.
- After the port was complete, they ran tests using four games to make sure their new version was comparable to the original GVG-AI Framework. They were able to prove that cumulative training across eight instances using PPO through the Unity ML-Agents Toolkit was comparable (better in some situations) than training with A2C on the GVG-AI Framework.
- They also mentioned a list of features that they didn't have time to port over and still need to be implemented in the Unity version.
- **Big Takeaway:** The GVG-AI Framework was successfully ported over to Unity with comparable results using the Unity ML-Agents Toolkit for the machine learning.


## The Unity ML-Agents Toolkit

Since the UnityVGDL Framework requires using the Unity ML-Agents Toolkit, I thought it only appropriate that I look into it and learn how to use it first. The Unity ML-Agents Toolkit is an open-source Unity plugin that enables games and simulations to act as training environments for AI. It was released in September of 2017, but it still regularly gets updated (remember this, it will come back later). It has a wide range of training options, from reinforcement learning to nueroevolution. It even includes a simple Python API to allow you to develope and test your own machine learning methods. With some basic background knowledge, I was ready to dive in.

After a quick Google search I found a promising old [YouTube tutorial](https://www.youtube.com/watch?v=axF_nHHchFQ). However, after I started to follow along, I quickly realized that Unity made some major overhauls to their system since the video's release. Luckily, the creator of the video wrote an [extensive tutorial](https://www.immersivelimit.com/tutorials/unity-ml-agents-penguins) for *Unity ML-Agents Version 0.14.0*.

As I proceeded to follow the tutorial, I went on to install the ML-Agents Toolkit on my own Unity. But then I noticed something, *Unity ML-Agents Version 1.4.0*. I thought to myself, "It is only shifted over by one decimal place, how bad could it be?" Not to keep you in suspense, it was BAD.

After noticing the significant version discrepancy, I thought it would be a good idea to get aquainted with the possibilities of the Unity ML-Agents Toolkit,through their included examples, before getting discouraged by the inevitable problems I knew I would run into. Let's just say, I was fairly impressed.

![ML-Agents PushBlock Demo](https://i.imgur.com/DyadSMQ.gif "ML-Agents PushBlock Demo")
Just look at those little guys go!

The Reinforcement Learning Penguins tutorial has you setup up an environment and an agent that does the learning. The learning environment consists of an icy slab, probably part of an iceberg, and a shallow pond of water with a few fishes in it. The agent in the environment is a penguin, persumably a mother, and her penguin baby. The agent must go back and forth between the iceberg and the water collecting fishing and regurgitating them to its baby, who waits patiently on the iceberg. The environment uses the Proximal Policy Optimization (PPO) learning algorithm to train the agent. The environment in questions looks like this:

![Single ML-Agents Penguin Training Environment](https://i.imgur.com/QIABCBC.png "Single ML-Agents Penguin Training Environment")

After following along with the written tutorial, spending hours along the way debugging issues due to library changes, I finally managed to the get the test environment setup. Yay! However, several features were still broken. For example, I could not perform a Heuristic based run of the environment (where I control the ML agent directly). I also could not find the training_config.yaml and circulla directory within the installed package like instructed in the tutorial. At this point, I think I will just call it a week here and try to debug the rest next week. I shall leave you with a picture of my new constructed training environment.

![Multiple ML-Agents Penguin Training Environments](https://i.imgur.com/qVSJaYc.png "Multiple ML-Agents Penguin Training Environments")
