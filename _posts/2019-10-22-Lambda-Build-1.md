---
layout: post
title: Build 1 -
subtitle: Lambda School - Data Science 9
image: /img/there-there-skeleton.png
---

This is my first project for Lambda School's monthly build week. I think the media presents a hostile view of life in the US; that shootings are happening more frequently than ever, that politicians are manipulating us, and that an excess diet of fried eggs is going to give us cancer. It sounds like other countries are taking note as well, as I've even heard of some warning their citizens of “highly frequent” gun violence. But I don't think death is nearly as common or likely as they believe.

By using data gathered from the CDC on deaths in California I intend to give a clear view on death - albeit a very small subset of the larger USA - and it's general probability against the surviving population as well as it's most common causes. I believe the most likely causes of death are cardiac arrest and motor-vehicle collisions and I'll compare that with what I believe most people would worry about; terrorism and homicide. I intend to show whether or not either view is correct.

### Donut charts

I intend to make this interactive, as that'll allow viewers the best possible chance at an unbiased answer, but for now all I have are these graphs.

![Pie-San-Diego](/img/Example-pie-San-Diego.png)

Starting off with my first donut chart shows that for people aged 20 to 24 in San Diego for the latest year in the dataset - 2016 - we have accidental poisoning at the top with 22%. However, two of the major causes of death on this chart are actually different types of suicides accounting for 40% of the deaths. If we wanted to focus on the firearms in the chart, we'd similarly see that it accounts for 36%.

Now, when I made these charts, they actually only show the top five, with a sixth chunk holding all other values together in order to make the chart legible. Fortunately for this chart, it actually doesn't have any more beyond this, and at 0.02% I'd say that makes a pretty stellar ratio. All in all though, this doesn't really seem to say much.

So now let's take a look at the same age range, but for all years.

![Pie-San-Diego](/img/Example-pie-San-Diego-all-years.png){: .center-block :}
In this case we see something a bit more interesting. For one, three of the top five causes of death are vehicle related. For two, 52 other things account for 85% of all deaths. It's pretty clear that despite trying to make it legible, when it comes to larger datasets this pie chart really isn't cutting it.


### Graphs
![Graph-San-Diego](/imd/San-Diego-Graph.png)
Changing from people in their twenties we'll now see infants. Fortunately, these have some of the lowest rates of death out of any age range that I could find. This graph doesn't say any more than which year each number died, but just so you know there were very few types of death for these with nearly all of them being SIDS. Additionally because the number of dead is so low compared to the population (1093 dead out of a total of 39,396, 2.77%) and the sum is bouncing around the graph we can assume rather safely that there isn't a trend going on; infants aren't dying any faster across the years, I'd call that a win.

### Seaborn Scatterplot
![SNS-San_Diego](/img/Seaborn-County Scatter-Plot.png)
Lastly here I have a scatterplot from seaborn. This shows each of the different counties in California and graphs each of the numbers of death - pre-sorted by age group - and plots them on the graph. In the end it doesn't really show anything we wouldn't have guessed though. A higher population means more death.


### In Conclusion



![Skeleton](/img/dont-give-up-skeleton.png){: .center-block :}
