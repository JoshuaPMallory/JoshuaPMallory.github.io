---
layout: post
title: Ex Early Access Probability
subtitle: Lambda School - Data Science 9
gh-repo: JoshuaPMallory/Ex_Early_Access_Probability
gh-badge: [fork]
image: /img/unfinished.png
tags: [Data Science, Lambda School]
---

Of the sixty-eight thousand games on Steam about four thousand of them are Early Access, and of those about six hundred have made it to a full release. With a success rate of only fifteen percent it doesn't seem too bright a concept, although, we don't know the success rate of those game which didn't release in either fasion nor.

While there's a scarce few I've seen that actually made it I've also seen some that have turned out impressive like Hollow Knight or Warframe, and I'd like to have been able to know before hand if it had any chance of success. So...

**So, is there anything concrete that determines a game's eventual release into 1.0? Let's fine out.**

It's important to note that just because a game releases doesn't mean that it's a particularly good one; take Duke Nukem Forever for example. However, while quality is important to me we're not going to focus on that too much here, all we care about is what features increase or decrease the probability of a developer keeping their word.


# Overview
I started with a dataset of steam games from [Craig Kelly](https://data.world/craigkelly/steam-game-data) at data.world and added onto it with some information from [SteamSpy](https://steamspy.com/about). SteamSpy definitely had a lot more recent data but unfortunately it's a pain to get any of it. Regardless I used two models on my data.

[comment]: # (I might still try to use https://steam.internet.byu.edu/ too, since it claims to use all of Steam's game data.)

![years_since_release](/img/pdp_isolate_years_since_release.png){: .center-block :}

To start I made a feature by taking the games release dates and subtracting them from the current year. That tells us how long it's been since it was released to Early Access, and as you can see as a game spends more time in development, generally it becomes more likely to release, though it's not guarenteed.


[comment]: # (Talk about other features I've engineered, if any, and show how well they did.)

![owners](/img/pdp_isolate_owners.png){: .center-block :}

This next plot is cut down substantially for readability, but suffice to say that as the number of adopters increases, so too does the chance of a game releaseing. However this doesn't tell the whole story either; people don't just adopt a game and ensure it releases, it may also be that people only flock to a game when it's actually good, so let's take a look at that too.

![owners_meta](/img/pdp_interact_owners_meta.png){: .center-block :}

Now we can see that as we have more and more people, generally, the metacritic score will be higher. However we also see that it's marginal at best; The difference between one and several thousand is maybe a point or two on metacritic. So while score matters, and the number of people matter, one does not cause the other.


![year_meta](pdp_interact_year_meta.png){: .center-block :}



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
