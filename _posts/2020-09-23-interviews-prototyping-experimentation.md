---
layout: post
title: Week 3 - Interviews, Prototyping / Experimentation
hidden: true
---

The third week of the research was pretty relaxed compared to last week. This week I reached out to some potential stakeholders and began experimenting with the [General Video Game AI Framework](https://github.com/GAIGResearch/gvgai/wiki).

## Small Update on Contacting Stakeholders

On Thursday, September 17, 2020, I reached out to eight different possible stakeholders from either the video game development industry or the artificial intelligence industry. I am happy to say I got a response back from three of them. Depending on how my research goes in the next two weeks, I might reach out to a couple more potential stakeholders in the upcoming weeks.

## The General Video Game AI Framework (GVG-AI) and Unity

I started off researching into the [GVG-AI Framework](https://github.com/GAIGResearch/gvgai/wiki) created by the people behind the [General Video Game AI Competition](http://www.gvgai.net/). I quickly realized the framework was built in Java and only supported controllers and models programmed in Java. Having not programmed in Java since the early years of high school, I was a bit disheartened. However, before looking for another framework, I decided I would read through the extensive documentation with the end goal being to see if I could port it over to C# and Unity. 

After reading through a decent chunk of the documentation, it became blatantly obvious that I was in over my head. I did not have the machine learning background necessary to port over such a massive framework. Especially, since I can't even remember the syntax for Java, making the entire process seem even more difficult. Prior to moving on, I thought it would be a good idea to search Google to see if anyone else had already ported the code over to C#/Unity. Luckily, I managed to find a [research paper](https://ieee-cog.org/2019/papers/paper_209.pdf) by some PhD students at the University of Copenhagen covering their Unity Framework, [Unity Video Game Description Language (UnityVGDL)](https://github.com/pyjamads/UnityVGDL). UnityVGDL combines the GVG-AI Framework's Video Game Description Language (GVG-AI VGDL) ontology with the [Unity ML-Agents Toolkit](https://github.com/Unity-Technologies/ml-agents).[^fn-unityvgdl_paper]

The Video Game Description Language (VGDL), designed by Tom Schaul, is a language that describes games in a very concise manner.[^fn-vgdl_definition] The description of any given video game is broken into four sections:
1. SpriteSet - Defines all available sprites for the game, including their parameters and display settings.
2. LevelMapping - Defines relationships between characters, used in the level definitions, and the available sprites.
3. InteractionSet - Specifies what events occur when two sprites of a given type collide in the game.
4. TerminationSet - Specifies the end conditions of the game, indicating whether the player wins or not.




## Unity ML-Agents



-----

[^fn-unityvgdl_paper]: [Video Game Description Language Environment for Unity Machine Learning Agents](https://ieee-cog.org/2019/papers/paper_209.pdf)
[^fn-vgdl_definition]: [Video Game Design Language (VGDL) - GVG-AI Competition](http://www.gvgai.net/vgdl.php)
