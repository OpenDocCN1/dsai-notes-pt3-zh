# 约翰霍普金斯大学《R语言数据可视化和仪表盘｜Data Visualization & Dashboarding with R》中英字幕 - P23：6_条形图第3部分.zh_en - GPT中英字幕课程资源 - BV1YWPjeKEWz

![](img/184f9c99e3efda075c3848f756245f89_0.png)

As we continue working with bar plots。Now I'm going to jump back to using some of our example data。

This time again， the sample of survey data that we've been working with from the Cooperative Congressional Eions survey。

I keep switching back and forth here intentionally because you want to practice learning to make different kinds of visualizations with different data sources all loaded into the same R session。

For this visualization， I'm going to break out the respondents that are Democrats， Republicans。

 and independents。And I'm going to show the count of each of these different classes of respondent by region of the country。

There are four regions set up in the codebook for our data。

 and so I'm going to show the number of Democrats， Republicans。

 and independents in each one of these regions using bar plots。When we're doing this。

 we can actually do it in two ways。One way you could create four separate stacked bar charts with the total number of respondents in each region and the different parts the different categories of party membership。

 Democrats， independent and Republicans， broken out into stacked bars for each region。

And the other way would be to create 12 separate bars that are grouped together into the four different regions。

Again， harder to understand than to actually just see and do， so let's go ahead and give it a shot。

To start， we read in the CCS data。And if you look at the codebook in the survey。

 there's a question about party identification that is posed to all the survey respondents。

 all the members of the general public。And this survey question is a seven point scale。

Where one to three means that the survey respondent is a strong Democrat who lean Democrat。

Four means that the respondent is a true independence and five to seven means that the respondent is a lean Republican to a strong Republican。

We're going to recode this data and collapse it， so it's just a three part variable for Republican。

 independent or Democrat。Now let's go to our GG plot command。On the X axis， we want the region。

And because we're doing this automated count with GM bar， we can leave the Y axis unmapped。

To create the stacked bars， we map the fill color for each bar to the collapsed party variable that we've created。

And you see when we run this， we get those stacked bars I was mentioning。

 so the fill is mapped to the count of the number of different respondents in each category。

 each party category by the four different regions of the country。Now。

 if you didnt when you stacked bars like this， and instead you wanted to have a grouped set of bars。

All you have to do is make one small change here。What you do is you go into the GM bar function and you set the option position to equal Dodge。

And this takes the stacked bar chart and breaks it apart。

 so you have 12 bars that are divided into four groups。

This is exactly the same information as the stacked bar chart。

 it's just formatted differently and whether or not you want to use one format of the other is really a personal preference based on the way you see the visualization and what you think is going to be most useful to your reader。

And of course， just like every other GG plot function we've created。gggi plot figure pardon me。

 you can fiddle with the titles， the legends and the colors， just as we have before。

 using precisely the same process。By now you should have a pretty good sense for the composition of a GT plot figure and a good foundation for continuing to learn new kinds of figures going forward。

