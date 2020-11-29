---
layout: post
title: Week 6 - Pivoting and The Path Forward
---

After wrapping up last week's fun and interesting ML-Agents project, I struggled to find an avenue forward toward the future. Basically, it was hard to get anything "deliverable" done this week. Between juggling EECS 482 Project 2, EECS 493, and this class and the mental deadlock I hit at the end of last week, I didn't really know where to go. It didn't help that the stakeholders I reached out to essentially called machine learning in Game Development a pipe dream, for the foreseeable future. Both of them argued that machine learning is too much of a hassle in complex games and it is not efficient enough to be useful for testing yet. They said maybe machine learning would be more useful in the future when machine learning algorithms improve and cloud computing allows ML agents to train significantly faster regardless of a user's hardware. I started this week's research by looking more into possible future approaches for machine learning in game development.

## Research into Possible Future Avenues (8-9 hours)

The majority of this week was spent researching and trying to think up ways to make something relevant for game developers or the video game industry involving machine learning. I started by researching articles and YouTube videos as research papers were far more academic than practical for real life situations. I went through a lot of articles and videos, but I thought I would highlight some of the more noteworthy ones I found below. 

### Google's Machine Learning Suite

While searching the web I came across Google's [Machine Learning for Game Developers](https://www.youtube.com/watch?v=2h-Wg5FDbtU) presentation at Google I/O'19. The half an hour long talk covered how Google has created a suite of machine learning APIs to make game development easier. They discussed machine learning APIs that can allow dynamic chat translation between languages, chat intention detection systems for handling inappropriate messages automatically, auto object detection in images and videos, and Auto ML and Cloud AI platform. The Auto ML and Cloud AI services allow a game developer to pass in data collected from their game to pass to Google's servers to train a custom machine learning model for their game and allow easy deployment of it worldwide. This service would allow game developers with no knowledge of machine learning to train advanced models for set purposes within their game.

Watching the video just further cemented my opinion of how insane Google is. It is amazing that Google is taking steps to begin the machine learning evolution within the game dev industry. Hopefully, within the next decade, machine learning will be something that is regularly used by game developers for assistance in the development process, as well as agents in actual games. Although I don't think I could work toward implementing anything similar in a feasible time, the presentation did, however, get the mental juices flowing for how to go about incorporating machine learning into games.

### Ubisoft and Machine Learning

After some more digging, I came across an article discussing how Ubisoft took significant steps towards incorporating machine learning into game development within their company. According to the article, [How Ubisoft Is Mainstreaming Machine Learning Into Game Development](https://analyticsindiamag.com/how-ubisoft-is-mainstreaming-machine-learning-into-game-development/), Ubisoft incorporated a machine learning algorithm into Assassin's Creed Origins to dynamically recognize hieroglyphics in ancient Eyptian sources (they used these as references while creating the game). The machine learning model then identifies hieroglyphs and uses completed translations to translate previously untranslated patterns of hieroglyphs. Ubisoft also partnered with Firefox to create [Commit Assistant](https://www.kitguru.net/channel/generaltech/matthew-wilson/ubisoft-is-using-machine-learning-to-spot-bugs-before-they-make-it-into-the-final-game-code/), a machine learning program that can catch bugs in developer code. The model trained on 10 years worth of old Ubisoft developer code to learn what types of statements will cause bugs and how they can be fixed. Using this information the model can predict with 60% accuracy (2018) lines that will cause bugs and suggest potential fixes.

This one wasn't super helpful for coming up with feasible projects, but I thought it was really cool so I thought I'd share it.

### EA SEED

SEED is a research team at EA studying machine learning and its applications into game development. [This short video](https://www.youtube.com/watch?v=LW20UbquVBU) demonstrates a machine learning agent that uses reinforcement learning, using a professional player's inputs, to learn to play a decently complex shooter game. The video describes the process of how the ML agent works and how it was trained. 

I can see these types of machine learning agents being trained to eventually be able to play with or against human players with varying levels of skill. Such agents could be used to create more enjoyable and skill accurate opponents to help fill lobbies in games. Such an agent would be very useful for a competitive shooter where there is a hidden ELO system that determines a player's skill. Such a model could be adjusted to play the game at a relatively comparable ELO level and result in fairly balanced machine learning enemies. Although this is a cool prospect, such a system could only be implemented by bigger game development companies who have access to large amounts of player data to train the machine learning models with. Smaller companies would not be able to pull this off with current technology. 

### Jabril's Run Forrest! ML Game

While randomly searching YouTube for videos on machine learning and game development, I came across an old video series by one of my favorite machine learning YouTubers, Jabrils. Jabrils is like a machine learning guru on YouTube, showcasing many cool machine learning projects he has done. To top it all off, he often makes the neural network algorithms himself from scratch based on his needs! Anyways, in his [short video series](https://www.youtube.com/playlist?list=PL0nQ4vmdWaA0mzW4zPffYnaRzzO7ZqDZ0), Jabrils talks over his process of making a video game that uses a machine learning model. He essentially creates and trains a machine learning model that should be able to complete a run through any maze the he creates backwards and forwards twice. However, because of how long he spent on the project and him realizing his initial model plan wasn't going to be optimal enough without restarting, he decided to turn it into a game where players compete to train a model that can complete the five compaign maps that Jabrils made. He even had a prize for the first person to create a model that could finish all the levels. 

Although, I personally wouldn't play such a game, as I don't know how to code a neural network from scratch, Jabril's series sparked something in me. It made me want to try to make a game or something similar using a machine learning model. I originally was gonna go this route at the start of the project but backed off because I thought it unfeasible and as a dead road as no other developers as doing it. However, I now know about Unity ML Agents. Furthermore, it seems that some other companies are starting to dip their toes into this aspect of machine learning. As such, I think it necessary that the path, although not frequently travelled must be expanded. If more people explore this area of machine learning in game development, maybe more developers will be willing to try it out.

## Machine Learning Game (3-4 hours)

I began contemplating ideas for how I could go about making a game centered around a machine learning agent. Would the player face off against the machine learning model? Would the player just cooperate with an ML model? How can I make an ML mechanic be the center of a game? Then I remembered the project, by a previous student, Prof. Yarger told me about. It also incorporated machine learning and ended up going down a similar route of making a game centered around an ML agent.

### Project Bella

[Project Bella](http://www-personal.umich.edu/~nbadami/ProjectBella/) is Natasha Badami's EECS 499 machine learning research project from WINTER 2020. She was initially exploring machine learning in game NPCs but eventually pivoted to a game centered around a machine learning agent. By the end of her project, she had a game where there were 5 penguins (4 ML agents, 1 controller by the player) that competed to gather ice slabs to build their igloo forts. Penguins would have to compete for the ice slabs as they were shared resources. Additionally, the penguins had a berserk mode where they moved faster and dealth damage to enemy penguins and enemy igloos. If a berserk penguin charged at an enemy igloo, they could cause it to break and steal the slabs of ice for their own igloo. She trained the machine learning agents to be aggressive and slightly prone to complete the objective. The mix seem to have resulted in a game where the ML agents were fun to interact with and made an interesting mechanic to the game. 

From reading her developer logs from weeks 1-12, I got a pretty good idea of the process she followed when creating her game. I think I can apply the knowledge to create my own original game using machine learning agents as focal point. 

### Messing Around with ML-Agent Examples

From what I read in Natasha's developer logs, she started with a base from one of the Unity provided examples and added elements to it to make it more into a game. I thought as such I should start with something similar. So off into the Unity ML-Agent example scenes I went. I spent the next couple of hours just messing around with different example scenes. 

## Next Week's Plan

Next week, I plan on beginning the implementation and testing of a new ML agents centered game. A good portion of this will brainstorming and planning out ideas and implementing quick tests to see if they stick. For each of the ideas, I will have to implement as simple machine learning model and see if it will be feasible for it to learn the other mechanics I plan to implement. However, as I learned in EECS 494, I plan to "follow the fun" and as such am gonna be prioritizing making something fun and playable over following through a strict plan. Hopefully, by the end, I am able to make something that is substanial and enjoyable to play. This portion of the project will probably span the next few weeks, if not the remainder of the semester.

Thanks for reading! Make sure to check back next week!
