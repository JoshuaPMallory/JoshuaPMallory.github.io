---
layout: post
title: Sanctions Explorer
subtitle: Lambda School - Labs 22
image: /img/sanctions.jpg
tags: [Lambda School, C4ADS, Non-Profit]
---


SanctionsExplorer is a project by the Center for Advanced Defense Studies (C4ADS) to allow people to search for sanctioned entities. By scraping data from OFAC, the UN and the EU that is normally unsearchable we allow people and buisnesses to better comply with nations sanctions.


### Overview
It used to be that this sanctions data wasn't even in a database, but from I was told there were a couple students that worked to import some of this data into a database which the US is still using on their own website. C4ADS has taken over the project and offered it out to the students at Lambda School with the goal of finishing their work, adding in the EU and UN sanctions, as well as the UN Panel of Expert Reports.


## Labs 22

### Role
I was brought onto the project and took a backend role working on a postgres database and flask endpoints. The project didn't have a database to begin with as it was all being scraped from online and put into a combined csv where it was then being searched with pandas, with everything running inside flask on AWS.

Over the 6 weeks for this project I spent time cleaning the data, built a postgres database, and worked with the frontend web devs Derek Dryer, Adam Monast, Lilian Cha, Logan Sorensen, Eian Carter and worked closely with Preston Burton to setup endpoints that they would need to make the search function as well as the map.

### Tasks
My main priority was creating a database for the data to reside so I went with postgres due to the expanding nature of the tables and for reliability. After that it was to setup endpoints that the team could use to return search results. All of these we built before I'd gotten there but had to be redone from scratch due to the shift from pandas to SQL.

### Challenges
Initially we had to convert from using pandas to SQL. Pandas is great locally, but it needs to have all the data at once to really search anything and that means it doesn't really have the right hardware to handle that. The initial search times were around a minute to get a single result back, and the map took so long I thought it'd just crashed. In the end we brought that down to 1-2 seconds for a normal search, and if you add in all the columns possible it takes at max 10 seconds for over 70,000 rows. Can't really undersell how fast SQL can be and I really think if we could organize and clean the code better it'd be faster still.

By far the hardest part was finding the right commands for SQL because postgres doesn't use the same commands as most SQL. Many of the most common answers online for any given question would give commands that postgres either doesn't have, uses different words, or requires a very strict order that isn't specified in their documentation. Quite frustrating, but eventually it all worked.

At the same time, probably the best part of this project in terms of what got done was right in the last week. I had the same code written slightly differently across all the endpoints; things were being added and changed a lot for all the different things the frontend team needed. For cleanliness and legibility's sake I like to clean my code just about every time I come back to it, but in this last week that's about all we were supposed to be doing.

So after a day of staring at the code and wracking my brain trying to figure out how to make all of these things work together I finally broke each part down into functions. It's obvious after the fact, but before then it was hard enough just to read it due to the way the queries needed to be formated, plus we needed multiple queries per search, all with the same filters attached.

I wish I could've gone further and condensed them all down into a single endpoint that could search across all tables, but the difficulty there was in the data; it's quite unclean. Parsing is difficult and I can't blame anyone for messing it up as I had to work with converting an xml doc into a csv which technically functions but has the downside of making multiple extra columns for people with multiple of any given column. For example, if you have two addresses you get a seperate column, but if you only have one all that info gets broken down into their respective columns. It's a recursive nightmare to try and find every last outlier in that thing.

## Conclusion
I was pretty happy with working on this project because it's a real problem. OFAC does have a way to search right now, but as I understand it they don't have anything being added to it, it's the same one those students made back in college, so we got to make a legitamate difference that'll help people get what they need. I'm pretty exctatic about that and I really hope the next team can bring it up to prime time.
