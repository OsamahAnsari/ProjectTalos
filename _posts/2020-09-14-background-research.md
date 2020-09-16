---
layout: post
title: Week 2 - Background Research
---

The second week of the project was significantly more work. The entire week essentially consisted of researching into a specific topic regarding AI in game development, reaching a dead end, brainstorming a new approach and repeating. I ran into a wall during the research process so many times that I actually started becoming depressed and almost gave up. But, one night at 5 am, as I was laying in bed trying to fall asleep after another hopeless night of research, it hit me - general game AI.

## Academic Research

Initially I wanted to research Enemy AI in video games but quickly realized that this field didn't have much to offer. Not only was there not much prior research, it also didn't offer anything special even if it succeeded. Even if AI was used to create unique adaptive enemies, what benefit would it serve? More than likely, it would result in unexpected behavior and break the game. In the best case scenario, it would result in an AI that is so difficult to beat that it would turn off most players. No one wants that, not players and not game developers.

So after many failed attempts, I eventually decided on the topic of General Game Playing AI (GGP). GGP is a design approach which allows an AI to play more than one game successfully. Unlike AI designed to specifically play one game, this AI cannot use a specifically designed AI as it will have no idea how to approach a game it has never played before. Such AI generally use algorithms such as [Monte Carlo Tree Search (MCTS)](https://en.wikipedia.org/wiki/Monte_Carlo_tree_search) and Upper Confidence Bound Trees (UCT Trees) or Directed Breadth First Search (DBS) to play a wide variety of games. 

Luckily while researching into the topic, I came across the [General Video Game AI Competition](http://www.gvgai.net/). This website was a treasure trove of information regarding general video game AI. It even provides a framework for creating your own AI and a testing suite. I plan on looking into this more in future weeks. 

Now without further ado, the five research papers/articles I found especially interesting:
- [Puigdomènech Badia, Adrià, et al. “Agent57: Outperforming the Human Atari Benchmark.” Deepmind, Alphabet Inc, 31 Mar. 2020.](https://arxiv.org/pdf/2003.13350.pdf)
  - This paper discusses Google's attempt to modify its Deep-Q network to better tackle Atari 57 test of general intelligence. They started by giving it short-term memory that lets it base its decisions on things previously seen in the game. They also added episodic memory to all the AI to discover more new more optimal strategies if they presented themselves. It explains how they updated their reward system to allow the AI to discover new strategies while also taking advantage of the current most optimal one it knows. They created a controller which balances the trade-offs between using a particular strategy and exploring a new one.
- [Jacquier, Yves. “Artificial Intelligence through Learning or Pavlovian Algorithm?” Ubisoft Montréal, Ubisoft Entertainment, 6 Feb. 2020.](https://montreal.ubisoft.com/en/artificial-intelligence-through-learning-or-pavlovian-algorithm/)
  - This article discusses all the many ways modern AI can be used to improve game development from using bots to perform specific tasks to autonomous testers to test a wide range of gameplay functions to autonomous agents that can interact with players in game. It discusses in detail the usefulness of AI in each of these subcategories, outlining the primary concepts behind such agents and how they would most likely work for an AI standpoint.
- [Fisher, Jordan. “How to Make Insane, Procedural Platformer Levels.” Gamasutra, Informa PLC Informa UK Limited, 10 May 2012.](https://www.gamasutra.com/view/feature/170049/how_to_make_insane_procedural_.php)
  - This article outlines how the startup company Pwnee, creators of Cloudberry Kingdom, created two advanced complimentary AIs. One of the AIs used the three rules of level design to create procedurally generated levels. The other used a standard machine learning model to test and find the possible solutions for said level. If a level was uncompletable, the level completor AI would signify such to the level creator AI which would use backtracking to find another possible configuration of level blocks. Together the two could create almost endless unique and completable levels.
- [Torrado, Ruben Rodriguez, et al. “Deep Reinforcement Learning for General Video Game AI.” 2018 IEEE Conference on Computational Intelligence and Games (CIG), 2018, doi:10.1109/cig.2018.8490422.](https://arxiv.org/pdf/1806.02448.pdf)
  - This paper discusses how Perez and his team created a general video game AI framework and connected it to the OpenAI Gym environment to allow testing of GVG-AI on a wide variety of video games very quickly. They outlined how they used DQN, Prioritized Dueling DQN and Advance Actor-Critic (A2C) on eighth different representative GVGAI games and the results of their tests.
- [Temming, Maria. “AI Can Learn Real-World Skills by Playing Video Games.” Science News for Students, Society for Science &amp; the Public, 12 Sept. 2019.](https://www.sciencenewsforstudents.org/article/ai-can-learn-real-world-skills-playing-video-games)
  - This article discusses the advances of DeepMind's AlphaStar AI against the world's best StarCraft II player. It discussed how the generalization of such an AI is good for performing tasks that require team coordination such as many robots working in a hospital or a warehouse. It also discussed how such an AI could perform individual tasks such as autonomous driving. But it explains that such AI can't work on many different tasks. As such, another AI would have to be trained to be more generalized. It covered how an Salesforce created a more generalized AI by training it in Minecraft to perform basic tasks and then forcing it to generalize that knowledge. For example, it was taught how to get a gold block from a house. But then it was given the same task with the door blocked. The AI had to learn to break the blocks in front of the door to get access to its target.

I'll include the list of the rest of the research papers and articles at the bottom of this post.

## Market Research

My research falls predominantly into the entertainment/gaming, tech/artificial intelligence market sectors. 

According to [Statista](https://www.statista.com/statistics/237749/value-of-the-global-entertainment-and-media-market/), the global entertainment market is expected to be worth $2.6 trillion by 2023. The global video game market was valued at [$121.7 billion in the year 2017](https://venturebeat.com/2018/05/09/newzoo-top-25-game-companies-captured-77-of-121-7-billion-market/). According to [All Top Everything](https://www.alltopeverything.com/top-10-biggest-video-game-companies/) the largest companies in this market include Sony ($20.3B), Nintendo ($11.1B), Microsoft ($11.0B), Tencent($9.2B), and Activision Blizzard ($6.5B).

The global technology market spending was [$3.2 billion in 2018](https://www.statista.com/statistics/886397/total-tech-spending-worldwide/). The global artificial software market revenue was [$10.1 billion in 2018](https://www.statista.com/topics/3104/artificial-intelligence-ai-worldwide/). According to [Visual Capitalist](https://www.visualcapitalist.com/the-worlds-tech-giants-ranked/), the world's leading tech companies are Apple ($352B), Microsoft ($327B), Google ($324B), Tencent ($151B), and Facebook ($147B).

There are currently only a few products on the market that use general AI in video games and a few others that use machine learning AI for very specific games. Google's [Agent57](https://deepmind.com/blog/article/Agent57-Outperforming-the-human-Atari-benchmark) can currently perform above the human benchmark on all 57 Atari 2600 games. Diego Perez and team created the [General Video Game AI (GVG-AI) Framework](https://github.com/GAIGResearch/GVGAI) for creating AI that can play a general variety of video games. [Test.AI](https://www.test.ai/about) is an AI that seeks to automate testing of mobile apps cutting down on the requirement for QA testers. [MarI/O](https://kottke.org/15/06/mario) is a video game AI that can play any level of Super Mario World. DeepMind's AI [AlphaStar](https://deepmind.com/blog/article/alphastar-mastering-real-time-strategy-game-starcraft-ii) can play StarCraft II so well that it is better than 99.8% of human players. 

## Stakeholder Research

The main benefit of my research will be to game development companies. Since a general video game AI would be able to playtest "any" video game, it would be greatly useful to development companies as it could save time and money on playtesting. It would be especially useful to smaller game development companies as they lack the resources to support a big playtesting team. Therefore, such an AI would allow them to build bigger and more complex games. As such, the cost of producing such an AI should be close to the lower end if possible.

This type of research could also benefit companies seeking general intelligent agents that can perform a myriad of tasks. Assuming it is possible to build an AI that can play any videogame without prior knowledge of it, how much further could you take it? Could they be taught to do everything under the sun? Many companies could benefit from such an advanced AI and could lead to possibly entirely new industries.

That is all for this week, thanks for reading!

-----

1. [Mateas, Michael. "Expressive AI: Games and Artificial Intelligence." DiGRA Conference. 2003.](https://users.soe.ucsc.edu/~michaelm/tenurereview/publications/mateas-digra2003.pdf)

2. [N. Shaker et al., "The turing test track of the 2012 Mario AI Championship: Entries and evaluation," 2013 IEEE Conference on Computational Inteligence in Games (CIG), Niagara Falls, ON, 2013, pp. 1-8, doi: 10.1109/CIG.2013.6633634.](http://julian.togelius.com/Shaker2013The.pdf)

3. [Shaker, Noor, Mohammad Shaker, and Julian Togelius. "Ropossum: An authoring tool for designing, optimizing and solving cut the rope levels." Ninth Artificial Intelligence and Interactive Digital Entertainment Conference. 2013.](https://d1wqtxts1xzle7.cloudfront.net/31923445/CTR-demonstration.pdf?1379679414=&response-content-disposition=inline%3B+filename%3DRopossum_An_Authoring_Tool_for_Designing.pdf&Expires=1600209846&Signature=K9o6iITBb47GpPh8LJqhbbNS6AhGbM3Aj8UqkIYXjvtgOxizRWfjYYnsWPYsixrmM~isfgd~TvI12USYdKr7IaHguPshyUobXbZE7ZfGZEfiV~KMmd42nLnGJI1nP4RooCOcCkcAUG43mJ6n7tXBR5AfLIjSYp~8yKJ7YS9KiH~3cYL3AbEJvKo8r~JT8Z2THZi1l2ujlgg6eZObinq8CFchBjBcJzevDftj6F7MGDtO7nzQADsOfWcwPoLosovqB~VVUvz2OVMnshpw-TFiOqiCJQOoX9xkTMFs~ezptpkPuO14iiBUXeNkO~Aq9-BEgilOMaFCeKvdWG1~r3rnQw__&Key-Pair-Id=APKAJLOHF5GGSLRBV4ZA)

4. [Togelius, Julian, and Georgios N. Yannakakis. “General General Game AI.” 2016 IEEE Conference on Computational Intelligence and Games (CIG), 2016, doi:10.1109/cig.2016.7860385.](http://julian.togelius.com/Togelius2016General.pdf)

5. [Statt, Nick. “How Artificial Intelligence Will Revolutionize the Way Video Games Are Developed and Played.” The Verge, The Verge, 6 Mar. 2019.](https://www.theverge.com/2019/3/6/18222203/video-game-ai-future-procedural-generation-deep-learning)

6. [Perez-Liebana, Diego, et al. “Analyzing the Robustness of General Video Game Playing Agents.” 2016 IEEE Conference on Computational Intelligence and Games (CIG), 2016, doi:10.1109/cig.2016.7860430.](http://www.diego-perez.net/papers/Robustness.pdf)

7. [Khalifa, Ahmed, et al. “General Video Game Rule Generation.” 2017 IEEE Conference on Computational Intelligence and Games (CIG), 2017, doi:10.1109/cig.2017.8080431.](http://www.diego-perez.net/papers/GVGRuleGeneration.pdf)

8. [Perez-Liebana, Diego, et al. “General Video Game AI: Competition, Challenges and Opportunities.” AAAI (2016).](http://www.diego-perez.net/papers/aaai2016_gvgai.pdf)

9. [Perez-Liebana, Diego, et al. “Knowledge-Based Fast Evolutionary MCTS for General Video Game Playing.” 2014 IEEE Conference on Computational Intelligence and Games, 2014, doi:10.1109/cig.2014.6932868.](http://www.diego-perez.net/papers/KBFastEvoMCTS_CIG2014.pdf)

10. [Perez-Liebana, Diego, et al. “Open Loop Search for General Video Game Playing.” Proceedings of the 2015 on Genetic and Evolutionary Computation Conference - GECCO '15, 2015, doi:10.1145/2739480.2754811.](http://www.diego-perez.net/papers/OpenLoopGVG.pdf)

11. [Perez-Liebana, Diego, et al. “Multi-Objective Tree Search Approaches for General Video Game Playing.” 2016 IEEE Congress on Evolutionary Computation (CEC), 2016, doi:10.1109/cec.2016.7743851.](http://www.diego-perez.net/papers/MOTS_GVG_CEC2016.pdf)

12. [Soemers, Dennis J. N. J., et al. “Enhancements for Real-Time Monte-Carlo Tree Search in General Video Game Playing.” 2016 IEEE Conference on Computational Intelligence and Games (CIG), 2016, doi:10.1109/cig.2016.7860448.](https://dke.maastrichtuniversity.nl/m.winands/documents/CIG2016_GVGAI.pdf)

13. [Levine, J. et al. “General Video Game Playing.” Artificial and Computational Intelligence in Games (2013).](http://people.idsia.ch/~tom/publications/dagstuhl-gvgp.pdf)

14. [P. Bontrager, A. Khalifa, A. Mendes and J. Togelius, "Matching games and algorithms for general video game playing", Twelfth Artificial Intelligence and Interactive Digital Entertainment Conference, 2016.](http://julian.togelius.com/Bontrager2016Matching.pdf)

15. [Riedl, Mark Owen, and Alexander Zook. “AI for Game Production.” 2013 IEEE Conference on Computational Inteligence in Games (CIG), 2013, doi:10.1109/cig.2013.6633663.](https://www.cc.gatech.edu/~riedl/pubs/cig13.pdf)

16. [Perez-Liebana, Diego, et al. “General Video Game AI: A Multitrack Framework for Evaluating Agents, Games, and Content Generation Algorithms.” IEEE Transactions on Games 11 (2019): 195-214.](https://arxiv.org/pdf/1802.10363.pdf)

17. [Li, Ted, and Sean Rafferty. “Playing Geometry Dash with Convolutional Neural Network.” Standford, CS231n, 2017.]( http://cs231n.stanford.edu/reports/2017/pdfs/605.pdf)

18. [Lavanchy, Maude, and Amit Joshi. “An AI Taught Itself to Play a Video Game – for the First Time, It's Beating Humans.” The Conversation, The Conversation US, Inc., 30 May 2019.](https://theconversation.com/an-ai-taught-itself-to-play-a-video-game-for-the-first-time-its-beating-humans-118028.)

19. [Hu, W. et al. “Component-based hierarchical state machine — A reusable and flexible game AI technology.” 2011 6th IEEE Joint International Information Technology and Artificial Intelligence Conference 2 (2011): 319-324.](https://ieeexplore.ieee.org/document/6030340)

20. [Turney, Drew. “AI Learns Multi-Player Video Game.” Cosmos Magazine, The Royal Institution of Australia Inc., 30 May 2019.](https://cosmosmagazine.com/technology/ai-learns-multi-player-video-game-and-smashes-it/)

21. [Shummon Maass, Laura  E. “Artificial Intelligence in Video Games.” Towards Data Science, Medium, 1 July 2019.](https://towardsdatascience.com/artificial-intelligence-in-video-games-3e2566d59c22)

22. [Sizer, Ben. “The Total Beginner's Guide to Game AI.” GameDev.net, GameDev.net, 12 Aug. 2018.](https://www.gamedev.net/tutorials/programming/artificial-intelligence/the-total-beginners-guide-to-game-ai-r4942/)

23. [Souppouris, Aaron. “Artificial Intelligence Learns Mario Level in Just 34 Attempts.” Engadget, Verizon Media, 17 June 2015.](https://www.engadget.com/2015-06-17-super-mario-world-self-learning-ai.html)

24. [Mallawaarachchi, Vijini. “Introduction to Genetic Algorithms - Including Example Code.” Towards Data Science, Medium, 7 July 2017.](https://towardsdatascience.com/introduction-to-genetic-algorithms-including-example-code-e396e98d8bf3)

25. [Paul, Sayak. “An Introduction to Q-Learning: Reinforcement Learning.” FloydHub Blog, FloydHub Blog, 15 May 2019.](https://blog.floydhub.com/an-introduction-to-q-learning-reinforcement-learning/)

26. [Stanley, Kenneth O., and Risto Miikkulainen. “Evolving Neural Networks through Augmenting Topologies.” Evolutionary Computation, vol. 10, no. 2, 2002, pp. 99–127., doi:10.1162/106365602320169811.](http://nn.cs.utexas.edu/downloads/papers/stanley.ec02.pdf)

27. [Galway, Leo, et al. “Machine Learning in Digital Games: a Survey.” Artificial Intelligence Review, vol. 29, no. 2, 2008, pp. 123–161., doi:10.1007/s10462-009-9112-y.](https://link.springer.com/article/10.1007/s10462-009-9112-y)