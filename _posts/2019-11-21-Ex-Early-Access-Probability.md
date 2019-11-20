---
layout: post
title: Ex Early Access Probability
subtitle: Lambda School - Data Science 9
gh-repo: JoshuaPMallory/Ex_Early_Access_Probability
gh-badge: [fork]
image: /img/unfinished.png
tags: [Data Science, Lambda School]
---

Of the sixty-eight thousand games on Steam about four thousand of them are Early Access, and of those about six hundred have made it to a full release. With a success rate of only about fifteen percent it doesn't seem too bright a concept, though, we don't know the success rate of those game which didn't made a traditional full release nor is there any length of time associated with it.

While there's a scarce few I've seen that actually made it I've also seen some that have turned out impressive like Hollow Knight or Warframe, and I'd like to have been able to know before hand if it had any chance of success. So...

So, is there anything concrete that determines a game's eventual release into 1.0? Let's fine out.

**Is there a way to determine if an Early Access game is actually going to hit 1.0 or not?**

It's important to note that just because a game releases doesn't mean that it's a particularly good one; Duke Nukem Forever was an example of that. However, while quality is important to me we're not going to focus on that too much here, all we care about is the probability of a developer keeping their word based on certain features.


# Overview
I started with a dataset of steam games from [Craig Kelly](https://data.world/craigkelly/steam-game-data) at data.world and added onto it with some information from [SteamSpy](https://steamspy.com/about). SteamSpy definitely had a lot more recent data but unfortunately it's a pain to get any of it. Regardless I used two models on my data.

I might still try to use [this site](https://steam.internet.byu.edu/) too, since it claims to use all of Steam's game data.

## Feature Engineering
I took the games release dates and subtracted them from the current year, and that tells us how long it's been since it was released to Early Access.

Talk about other features I've engineered, if any, and show how well they did.


### Random Forest Classifier
Here is where my findings on my Random Forest Classifier model will go.


### Logistic Regression
Here is where my findings on my Logistic Regression model will go.


## Features that I've found made a difference
Here I'll show a force plot or two, as well as a PDP plot and explain what we're looking at.


## Other stuff?
- Maybe I should block each type of game by it's genre?
We could take each group based on it's genre and run the numbers, normalize them, and compare each genre's chances of releasing.

- Asset flips


# Conclusion
This is where my conclusion will go when it's actually ready to be written.
