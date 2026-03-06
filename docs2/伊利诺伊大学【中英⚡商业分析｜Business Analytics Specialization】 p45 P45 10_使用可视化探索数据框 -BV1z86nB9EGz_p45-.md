# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p45 P45 10_使用可视化探索数据框 -BV1z86nB9EGz_p45-

This lesson is all about creating exploratory data visualizations Now data visualizations usually come in two categories。

 exploratory and explanatory。On one hand， exploratory visualizations are quickly created just to explore the data。

 and they're not refined to carefully identify the access labels title or other features about the plot。

On the other hand， explanatory visualizations are typically used to summarize and communicate key findings to others。

 And so those are usually carefully crafted in such a way that you carefully decide what font to use may be。

 and the color schemes and the titles and so on。 So like I said。

 we're going to focus on exploratory visualizations。

 Quick visualizations that you can create with pandas data frames。

 and we'll calculate these by using the plot method。😊。



![](img/281ad111663c5d8e424ed29677e30c14_1.png)

So let's jump over to a Python environment in Jupyter lab and demonstrate how you can do that。

 So again， the key thing to remember is up here at the top， we're going to use the dot plot method。

 So first we're going to read in the data So I'm going to type B to create a new cell below that one that I had selected and I'm going to import functions from the pandas module。



![](img/281ad111663c5d8e424ed29677e30c14_3.png)

![](img/281ad111663c5d8e424ed29677e30c14_4.png)

And I'll run that。And now I can read in the data， and I'll save it as a data frame S D。

And then after I read in the data from the salary Sur 21。 Xz file， a pickle file。

 I'm going to show the first five rows using the head method。Okay， so here's the first five rows。

 And you can see that I've got a lot of。Information。

 and this is from a survey about how much money people make。 What is their annual salary。

I've got the time when they took it， their age range， their industry， job title， and job context。

 annual salary and bonuses， these are key columns here。

 and then a lot of other pieces of information。Okay， so let's start by showing how you can calculate。

Any plot。 All right， so I'll put it under this heading right here and I'll come back and talk about this heading。

So for all of these plots， what we're going to do is we're going to calculate or we're going to type out the data frame name。

Period。And then we can use plot。 Okay now， once we add that and hit a period。

 at least in Jupiter lab， you can see all the different types of plots that I can really quickly create just within pandas。

 So what I want to do here is start by calculating univevariate plots for columns that are numeric。

 So the annual salary column， that's a numeric column。



![](img/281ad111663c5d8e424ed29677e30c14_6.png)

![](img/281ad111663c5d8e424ed29677e30c14_7.png)

![](img/281ad111663c5d8e424ed29677e30c14_8.png)

So I'm going to add in annual salary in a dot here。All right so I've got data frame， the column。

 now the plot method and now I can see the types of plots well one of the key plots that we often use is a histogram。

 so Ill use this hist method I need to add open close parentheses and then I will just run that sill and I get a histogram。



![](img/281ad111663c5d8e424ed29677e30c14_10.png)

![](img/281ad111663c5d8e424ed29677e30c14_11.png)

Now， before I move on， I also get this label right here， which isn't that helpful。

 and I can get rid of that by adding a semicolon and then rerunning it and that gets rid of it。



![](img/281ad111663c5d8e424ed29677e30c14_13.png)

All right， let's talk about what a histogram is。 So a histogram counts the number of times that observations show up within specific intervals。



![](img/281ad111663c5d8e424ed29677e30c14_15.png)

So along the X axis， I have values that represent my annual salary。

 so it goes from 0 up to 1 billion or 6 billion up here。

 And most of the observations fall into this bucket right here。 Now。

 the height of this bucket or this bar represents how many times an observation falls in here。

 And you can see we've got over 25000 around 28000 observations that are in this range right here。

 Well， I only have about 28000 observations in this data set。

 So why do I have such a large space here。 Well， I've got one or two are just a small number of observations that are really big。

 at least one that's up here close to the end here。 And so it's using all of this space for nothing。

 really， or maybe just a few outliers。

![](img/281ad111663c5d8e424ed29677e30c14_17.png)

![](img/281ad111663c5d8e424ed29677e30c14_18.png)

![](img/281ad111663c5d8e424ed29677e30c14_19.png)

![](img/281ad111663c5d8e424ed29677e30c14_20.png)

![](img/281ad111663c5d8e424ed29677e30c14_21.png)

So we can make this a lot more helpful by filtering the data。

 So let's copy this by pressing C and then V。And let's filter this data and then plot it。

 So I'm going to add on to this in here， the query method。Allright， and I want to query。And say。

 I only want observations for which values in the annual salary column are less than。1 million。

 so I'll type one E to the sixth。Or E6， which means a one with six zeros after it。

And then I'll plot this。And I left off of why。Okay， all right， now this is a lot more helpful。

 I've got three buckets that I can see and actually fourth。

 fifth and sixth one down here it's just that there aren't a lot of observations there。 Okay。

 so this maybe highlights the usefulness of a histogram I can refine this a little bit more and I can add in some additional arguments in this hist method here。

 So let's say we want to increase the number of bins to 50。



![](img/281ad111663c5d8e424ed29677e30c14_23.png)

![](img/281ad111663c5d8e424ed29677e30c14_24.png)

All right， and that makes it a much more refined plot and I can break that area up into smaller pieces and really kind of see more details there。

Alright， so anyway， there's the histogram method。 Let's add a little bit more detail to it。

 If I want to add a title in here， I can just type out title and then equals。

Histogram of annual salary。 and then run this and it adds this title up here at the top。 All right。

 so anyway， we could continue to refine this more。 But remember。

 we're doing exploratory visualization。 So really just for our own sake。

 to get a feel for what's in the data。 Let me go ahead and create a copy of that。

 So I copied and pasted it。 And let's just change the arguments in here， we'll get rid of those。

 And we'll change this from hist to density。And theyll run that。All right。

 Now a density plot is a smooth out version of a histogram。 So if you compare this here。

To what we have right here， it's just a smoother version of it。

 And the reason why it has more space after 0 is so that it can kind of smooth out this curve here。

 even though there aren't observations that are less than 0。 Okay。

 so this is another helpful plot for numeric columns。

 One other one that I want to show you is a box plot。

So I'm just going to replace density with box and run that。

 and this is a box or box and whisker plot。So I've got the intercorrtile range or the 25th percentile median and 75th percentile。

 So the middle 50% of the data represented in this box here。

 and then the whiskers and the stubble or the outliers。 So all of these dots here， you know。

 there's a lot here。 since we've got 28000 observations。 even if this is 100 observations。

 It's not very many。 So most of the others fall below about 200000 right there。

 So this is a single box plot for all of our observations。 But we can make a really cool box plot。

 And what we can do is we can say， hey， I'm not going to just。Base it on the annual salary column。

 I'll still look at annual salary， but I want to divide this up。By maybe the age range。 And then。

Then I'm going to create a box and whisker plot for each of those age ranges。Okay。

 so this is really helpful now now I can see for each of the different age ranges。

The distribution of observations。 And so this helps me to real quick。

 I can look at the medians here and see that the median for the 45 to 54 age range appears to be the highest。

 pretty close to 35 to 44。 Then it kind of goes down。 And for the 65 or over。

 there's a much bigger range or。Well， a bigger range， it is much bigger than 18 to 24。 And actually。

 that median is a little bit higher there。 So anyway， real quickly。

 you can create this really informative series of box and whisker plots that allow you to get some really good insight about how annual salary is distributed within different age categories。

 So that's pretty cool。😊，All right， Well， speaking of age， it is a categorical columns。

 Let's talk about some plots that we can use for categorical columns。

 So I'm going to start by typing out my data frame name and then age。

 And then one of the things we often like to do with categorical columns is see how many times each value appears。

 And so we're gonna add on here， the value counts method。 If I just run that。

 you can see that I get this summary of how many times each age group appears in here。

 and it's sorted in descending order。 So 25 to 34 shows up the most 12679 times followed by the 35 to 44 age range and so on。

 All right， so we can take that。 And then we can add on the dot plot method And then dot bar。

Allright， and so what this allows me to do is just to visualize that summary from the value counts。

 but as a barpl so I can real quickly see communicate a lot faster than just comparing numbers that 25 to 34 is the highest followed by a decent drop from 35 to 44 and then a huge decrease in observations for all of the other age categories in there All right and so this is really helpful I could do this with other categories as well。

 so I copied and pasted that if I want to do this with the industry。



![](img/281ad111663c5d8e424ed29677e30c14_26.png)

Category， and I'm going to add a semicolon at the end。



![](img/281ad111663c5d8e424ed29677e30c14_28.png)

This one's going to take a little bit longer because I've got like 1200 different industries in here。

 So this is overwhelming。 It doesn't really help us much because there's so many observations。

 So I can add on other methods here。 This is where we can really be creative in our understanding of the methods available to us。

 And so I just want to look at maybe the first five rows here rather than all 1200。

 So I'm going just use the head method after value counts。 and then plot and bar。

 And now I get just the first five most frequently occurring industries。

 So I can see that computing or tech is huge。 And then about half of that I've got。



![](img/281ad111663c5d8e424ed29677e30c14_30.png)

Education， higher education， and in these other ones here。 If I wanted to add 6 or 7 in here。

 I'll just type 7。 I can just put a 7 in the head there。 And now I've got 7 of those。 So anyway。

 that's a really quick way to see what's in the categorical columns。 Now。

 I can also just add an H at the end here。

![](img/281ad111663c5d8e424ed29677e30c14_32.png)

![](img/281ad111663c5d8e424ed29677e30c14_33.png)

![](img/281ad111663c5d8e424ed29677e30c14_34.png)

Now， oftentimes when I have long values in my categorical columns。

 I like the horizontal bar chart because there's more room for the labels here。Alright。

 so I still have computing or tech， but it's down here at the bottom。

 And then it goes in descending order from bottom to top。 All right， another type of plot that。



![](img/281ad111663c5d8e424ed29677e30c14_36.png)

Is helpful for looking at the proportion of observations is a pie chart so。

I'm going to use everything the same that I use for the bar plot， the horizontal bar plot。

 but I'll replace the bar H with pi and run that。 And I get a pie chart。 And this again。

 helps me to kind of visualize the proportion with which each of those categories shows up。

 So it starts with the biggest ti and it gets smaller as we go Countclockwise。 All right。

 let's go ahead and talk about how we can calculate plots when we want to look at things over time。

 Now most of the time we're going to want to summarize things so that we summarize like what's the total number of observation on this date or something like that。

 But for our purposes， what we're going to do is we're going just look at the number of observations that come。



![](img/281ad111663c5d8e424ed29677e30c14_38.png)

Just over time， we're not going to summarize it at all。 Okay。

 so I'm to use the plot method and then the line method and on the X axis。

 I'm going to use the time column and the y axis， I'll use the annual salary column。

I'll add that semicolon at the end， and run that。All right， And so I get this line plot。

 which doesn't look too useful Again， we've got one observation that's huge。

 so it really makes it hard to see everything else that's happening here。

 So let's copy and paste that and let's reduce this data。 So we'll use the query method。



![](img/281ad111663c5d8e424ed29677e30c14_40.png)

We want to look at values or observations for which the annual salary。Is less than。1 million。

 So one these6。

![](img/281ad111663c5d8e424ed29677e30c14_42.png)

Okay， now this， this is helpful to see that。I've got some of the higher annual salaries occurring earlier on。

 and I can also kind of see more observations earlier on too， it's just busier here。All right。

 so anyway， there's a line plot copy and paste that very close cousin to the line plot is the area plot。



![](img/281ad111663c5d8e424ed29677e30c14_44.png)

![](img/281ad111663c5d8e424ed29677e30c14_45.png)

And you may not be able to tell much of a difference。

 but the area plot just fills in the space under the line。 So this。

 it's all blue under the line here， whereas some places over here， it's blank。 All right。

 And then the last category of plots are relationship plot。

 So when we want to look at how two numeric columns are associated with each other。

 Like the annual salary and bonus is column。 Is it the case that the higher the annual salary。

 the higher the bonus， Let's find out。So we're going to start with S。

 and then we're not going to reduce it to any column。

 So we'll just go ahead and jump right into the plot method。

Then we're going to use the scatter method here。 And on the X axis， we'll put annual salary。

I usually like to put the cause of what is on the y axis on the X axis。

And then the Y axis will put bonuses。And then I'll add that semicolon at the end。Okay， once again。

 I get a plot here and it's really skewed because I got this one observation that's huge。

So it's really hard to see what's happening with most everything else。

 So let's copy and paste this and let's query this。

So that we're only looking at observations that are less than a million dollars or a million。Okay。

 now this is a lot more informative。 Now I can see that， yeah。

 going from like0 up to about maybe 250000。 there does seem to be。

An upward trend here where the higher the annual salary， the higher the bonus， but。

That's just kind of going off this edge here。 There's a lot of overlap here。

 and this is one of the problems with scatter plots is that when you have so many observations and they overlap it's hard to see what's going on。

So I'll copy and paste this and show you another alternative for this type of situation。

 and that is the hex bin plot。

![](img/281ad111663c5d8e424ed29677e30c14_47.png)

![](img/281ad111663c5d8e424ed29677e30c14_48.png)

So you can see all I did is I replaced scatter with he bin and everything else is the same。

Now it removes a lot of the nuance， but the idea is that it's dividing this grid up into hexagons。

And then it will represent the number of observations based on the intensity of the color over here。

 So darker colors means more observations。 So I've got a lot of observations down in this area right here。

 Can we， we don't really see that same relationship in the scatter plot here。 Well。

 now that I see that， I might want to zoom in a little bit further。

 maybe look at observations where the annual salary is less than 200000。

 So I'll copy and paste this and。

![](img/281ad111663c5d8e424ed29677e30c14_50.png)

![](img/281ad111663c5d8e424ed29677e30c14_51.png)

I'll say，2 E5。Run that。 Okay， again， this is helpful to see。 I've got a lot down here。 Basically。

 a lot of people don't have bonuses。 Allright， so that's a hexman plot。

 And I could continue to refine this if I wanted to。 but for exploratory purposes。

 this really helps me get a feel for kind where a lot of the observations fall。

 So that wraps up our look at quickly generating exploratory plots with pandas。

 there are many other modules that you can use to create plots。

 both for exploratory and explanatory purposes。But being able to visualize your data is a critical part of any data analytic workflow。



![](img/281ad111663c5d8e424ed29677e30c14_53.png)

![](img/281ad111663c5d8e424ed29677e30c14_54.png)