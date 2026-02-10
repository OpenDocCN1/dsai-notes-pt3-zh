# IBM数据科学专业证书课程8：《Python数据可视化课程（IBM）》python-for-data-visualization（中英字幕） - P5：5_折线图绘制.zh_en - GPT中英字幕课程资源 - BV19k4y1375E

![](img/26a7e7baa472fb908a10460fa8cb8219_0.png)

In this video， things will start getting more exciting。

 We will generate our first visualization tool， the line plot。😊。



![](img/26a7e7baa472fb908a10460fa8cb8219_2.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_3.png)

So what is the length plot？As its name suggests， it is applied in the form of a series of data points connected by straight line segments。

 it is one of the most basic type of chart and is common in many fields， not just data science。



![](img/26a7e7baa472fb908a10460fa8cb8219_5.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_6.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_7.png)

The more important question is when to use line plots the best use case for a line plot is when you have a continuous data set and you're interested in visualizing the data over a period of time。

 as an example， say we're interested in the trend of immigrants from Haiti to Canada we can generate a line plot and the resulting figure will depict the trend of Haitian immigrants to Canada from 1980 to 2013。



![](img/26a7e7baa472fb908a10460fa8cb8219_9.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_10.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_11.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_12.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_13.png)

Based on this line plot， we can then research for justifications of obvious anomalies or changes。

 so in this example we see that there is a spike of immigration from Haiti to Canada in 2010。



![](img/26a7e7baa472fb908a10460fa8cb8219_15.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_16.png)

A quick Google search for major events in Haiti in 2010 would return the tragic earthquake that took place in 2010。

 and therefore this influx of immigration to Canada was mainly due to that tragic earthquake okay now how can we generate this line plot？



![](img/26a7e7baa472fb908a10460fa8cb8219_18.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_19.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_20.png)

Before we go over the code to do that， let's do a quick recap of our data。

Each represents a country and contains metadata about the country。

 such as where it is located geographically and whether it is developing or developed。

Each row also contains numerical figures of annual immigration from that country to Canada from 1980 to 2013。

Now let's process the data frame so that the country name becomes the index of each row。

 this should make worrying specific countries easier。

 also let's add an extra column which represents the cumulative sum of annual immigration from each country from 1980 to 2013。

 so for Afghanistan it is 58，639 total and for Albania it is 15，699 and so on。



![](img/26a7e7baa472fb908a10460fa8cb8219_22.png)

And let's name our data frame， DF_ Canada。So now that we know how our data is stored in the data frame。

 DF underscore Canada， let's generate the line plot corresponding to immigration from Haiti。



![](img/26a7e7baa472fb908a10460fa8cb8219_24.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_25.png)

First， we import Matplotlibb as MPL。

![](img/26a7e7baa472fb908a10460fa8cb8219_27.png)

And it's scripting interface as PLT。Then we call the plot function on the ro corresponding to Haiti。

 and we set kind equals line to generate a line plot。



![](img/26a7e7baa472fb908a10460fa8cb8219_29.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_30.png)

Note that we usedE， which is a list containing string format of years from 1980 to 2013 in order to exclude the column of total immigration that we added。



![](img/26a7e7baa472fb908a10460fa8cb8219_32.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_33.png)

Then to complete the figure， we give it a title and we label its axes。



![](img/26a7e7baa472fb908a10460fa8cb8219_35.png)

Finally， we call the show function to display the figure。



![](img/26a7e7baa472fb908a10460fa8cb8219_37.png)

Note that this is the code to generate the line plot using the magic function。



![](img/26a7e7baa472fb908a10460fa8cb8219_39.png)

Percent sign Mattlo laid with the inline backend。

![](img/26a7e7baa472fb908a10460fa8cb8219_41.png)

And there you have it， a line plot that depicts immigration from Haiti to Canada from 1980 to 2013。



![](img/26a7e7baa472fb908a10460fa8cb8219_43.png)

In the lab session， we explore line plots in more details so make sure to complete this module's lab session。



![](img/26a7e7baa472fb908a10460fa8cb8219_45.png)

![](img/26a7e7baa472fb908a10460fa8cb8219_46.png)

This concludes our video online plots， I'll see you in the next video。



![](img/26a7e7baa472fb908a10460fa8cb8219_48.png)