---
layout: post
title: Sanctions Explorer
subtitle: Lambda School - Labs 22
image: /img/sanctions.jpg
tags: [Lambda School, C4ADS, Non-Profit]
---


SanctionsExplorer is a project by the Center for Advanced Defense Studies (C4ADS) to allow people to search for sanctioned entities. By scraping normally unsearchable data from OFAC, the UN and the EU we allow people and buisnesses to better comply with their sanctions.


### Overview
It used to be that sanctions weren't even listed in a database, but there were a couple students from UC Berkeley that worked to import some of this data into a database which the US is still using on their own website. C4ADS has taken over the project and offered it out to the students at Lambda School with the goal of finishing their work; to add in historical data for OFAC, adding in EU and UN sanctions, and finally the UN Panel of Expert Reports.


## Labs 22

### Start
When we recieved the project it's data was all being scraped from online and put into a combined csv. From there a Flask app running on Amazon Web Services used pandas to search the file based on user requests. With some 70,000 rows this led to search times around a minute while the analytics page often took several minutes to return anything. Most people thought it had just crashed!

### Backend Development
The stakeholders told us the most important thing was improving search times for the website, so over the 6 weeks we had for this project I assumed a backend role and decided the best way to accomplish that would be to build a database. I went with postgres due to the expanding nature of the tables and it's well known reliability. I also spent time understanding and cleaning the data and worked with the frontend web devs Derek Dryer, Adam Monast, Lilian Cha, Logan Sorensen, Eian Carter and worked closely with Team Lead Preston Burton to setup endpoints that could provide the data they would need for both the search and analytics pages.

### Challenges
Initially I had to convert from using pandas to SQL. Pandas is great locally but it needs to have all the data loaded into ram at once to search anything. So I started by implementing the database which was quite easy, but I ran into problems with AWS in the load balancer. It took awhile to find but it turns out to be one setting that was manual instead of automatic, and after that development cruised along.

After that I converted one endpoint to handle the same type of queries inside of SQL and slowly handled additional feature requests from the team while adding additional tables into the database. And by the end I brought the search time down to 1-2 seconds for a normal search, and if you add in all the columns possible it takes at max 10 seconds for well over 70,000 rows. Can't really undersell how fast SQL can be and I really think if we could organize and clean the code better it'd be faster still.

By far the hardest part was finding the right commands for postgres. Many of the most common answers online for any given question would give commands that postgres either doesn't have, uses different words, or requires a very strict order that isn't specified in their documentation. Quite frustrating, but eventually it all worked.

### High Point
Probably the best part of this project was right in the last week. I had the same code written slightly differently across all the endpoints; a programming sin if there ever was one. Things were being added and changed a lot based on the teams requests but really I was just having trouble getting it right the first time. So after a day of staring at the code and wracking my brain trying to figure out how to make all of these different things work together I finally decided to break each part down into functions one by one and I checked them for functionality as I went. It's obvious after the fact but before then it was hard enough just to read it due to the way the queries needed to be formated, nevermind having multiple queries per search all with the same filters attached. I'm pretty happy with how that went.

I wish I could've gone further and condensed them all down into a single endpoint that could search across all tables, but the difficulty there was in the data; it's quite unclean. Parsing is difficult and I can't blame anyone for messing it up as I had to work with converting an xml doc into a csv, which, technically it functions, but it has the downside of making multiple extra columns for people with multiple of any given column. For example, if you have two addresses you get a seperate column, but if you only have one all that info gets broken down into their respective columns. It's a recursive nightmare to try and find every last outlier and I couldn't find any packages that could handle it for me, sadly.

## Conclusion
I was pretty happy with working on this project because it's a real problem. OFAC does have a way to search right now, but as I understand it they don't have anything being added to it, it's the same one those students made back in college, so we got to make a legitamate difference that'll help people get what they need. I'm pretty exctatic about that and I really hope the next team can bring it up to prime time.
