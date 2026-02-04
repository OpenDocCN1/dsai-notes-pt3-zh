# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P30：29_特征工程实验解决方案（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/d55700b8861616a13f8e694d2a6c644e_0.png)

Let's dive into our notebook on feature engineering we're going to be using the AIES Hous data set if you're curious to learn more we've also provided a link here。

 we're going to do it in regards to linear regression our feature engineering。

 but this will be able to work in context for many of the machine learning models moving forward。



![](img/d55700b8861616a13f8e694d2a6c644e_2.png)

We're going to start off with some simple EDA， we'll import pandas SPD， Cborn as SNS。



![](img/d55700b8861616a13f8e694d2a6c644e_4.png)

When we run SNS dot set， we're just setting some defaults for outputs for each one of our seaborn plots。



![](img/d55700b8861616a13f8e694d2a6c644e_6.png)

So you run that。We then are going to specify the path to the file that we're going to be using we've been using CSV files here we're using a TSV file。

 all that means is that it's a tab separated value。We can still use the RET CSV function。

 we are just setting the separator argument equal to tab， and we do so using the string backslash T。



![](img/d55700b8861616a13f8e694d2a6c644e_8.png)

![](img/d55700b8861616a13f8e694d2a6c644e_9.png)

![](img/d55700b8861616a13f8e694d2a6c644e_10.png)

The next thing that we're going to do is run df。info。

 that method is going to provide us three important pieces of information。



![](img/d55700b8861616a13f8e694d2a6c644e_12.png)

It's going to provide us all of our column names。

![](img/d55700b8861616a13f8e694d2a6c644e_14.png)

It's also going to provide us how many non null values each one of our columns have。

 so if we look here we have 198 non null values， meaning we are probably missing a lot of values given that we have 2。

930 entries total。

![](img/d55700b8861616a13f8e694d2a6c644e_16.png)

![](img/d55700b8861616a13f8e694d2a6c644e_17.png)

And then finally， it'll tell you for each column the different data types。

 so we see here integer object float， now there's more object to would refer probably to categorical if you haven't seen this before。



![](img/d55700b8861616a13f8e694d2a6c644e_19.png)

![](img/d55700b8861616a13f8e694d2a6c644e_20.png)

So we're going to look at a histogram of a specific column and the reason we look at this column specifically is because the author of this data specified that there are some outliers in this column。

 so we're taking a quick look to see if they're truly outliers and we see that there is not a lot of frequency beyond 4000。

 which is where the outliers， the authors said the outliers lie。

So we're just going to filter out all those valuesals below 4000。So we see DF。

 and we're pulling in GR live area， which is the name of our column。

And we're pulling all of our rows。Right with theFt Lo。

 we're using all of our rows except for those under 4000， and then we're using all of our columns。

The next thing we want to do is see what is the new shape of our data frame。

 so we just call dot shape， and if you recall dot shape is going to output a tuple。

 the first value being the number of rows， the second value being the number of columns。



![](img/d55700b8861616a13f8e694d2a6c644e_22.png)

And then finally， we want to keep a copy of our data for later。

 so we're going to do these transformations and it is good practice to try and save original version of the data。

 so we do DF do copy so all of our changes that we do to DF won't affect our initial copy that we can come back to。



![](img/d55700b8861616a13f8e694d2a6c644e_24.png)

So we take a quick look at the first five values。First five rows。

And something to note is these first two columns order in PID， and there's more ways to look at this。

 for example， you can look at。Oh。Say， D F dot。P， I D dot unique。

And I'm going to look at the length of this。And we'll see that it's the same number as the number of rows that we have so there's a unique value for every row and that's not going to give us any predicted value for trying to run a machine learning model It can't learn anything if every single value for that column is a unique value So we're just going to drop those two columns the way that we do that is using the dot drop functionality and then we drop the specified columns PID and order。



![](img/d55700b8861616a13f8e694d2a6c644e_26.png)

![](img/d55700b8861616a13f8e694d2a6c644e_27.png)

![](img/d55700b8861616a13f8e694d2a6c644e_28.png)

We have to set access equals 1 by default， it'll look for those row indexes。

 we want to specify that we're looking at the column indexes。

 so we say access equals 1 and then in place equals true just sets it to a copy of itself。

 so DF is being replaced in place。

![](img/d55700b8861616a13f8e694d2a6c644e_30.png)

![](img/d55700b8861616a13f8e694d2a6c644e_31.png)

Now let's get into some feature transformations， we're going to use a log transformation for our skewed variables。



![](img/d55700b8861616a13f8e694d2a6c644e_33.png)

The first thing that we want to do is pull out our numerical variables。



![](img/d55700b8861616a13f8e694d2a6c644e_35.png)

So we're going to use this select D types functionality。



![](img/d55700b8861616a13f8e694d2a6c644e_37.png)

And you could pass in something an argument like number。



![](img/d55700b8861616a13f8e694d2a6c644e_39.png)

And that'll filter down your columns to only your numerical value， so floats and integers。

 you can also do something like objects。Or specifically。

And and this will be useful throughout your time working with Pada's data frame。



![](img/d55700b8861616a13f8e694d2a6c644e_41.png)

So we're going to say number specifically， and we want to pull out the columns。



![](img/d55700b8861616a13f8e694d2a6c644e_43.png)

So that's going to be equal to our variable nu calls。

We're going to set the Sw limit as a variable that we'll come back to later。

 we want to look for heavily skewed distributions for each one of our columns。



![](img/d55700b8861616a13f8e694d2a6c644e_45.png)

A normal distribution with zero skew would have a sU we're going to see here that we tried to find a value an actual numerical value to describe Skew。

 something above 0 has a right skew below  zero has a left skew generally we use here around 0。

75 and below we probably do not have that heavily of a skewed of a data set or of a column something above 0。

75 probably indicates that we have a heavily skewed distribution and we should probably run some type of transformation。



![](img/d55700b8861616a13f8e694d2a6c644e_47.png)

![](img/d55700b8861616a13f8e694d2a6c644e_48.png)

![](img/d55700b8861616a13f8e694d2a6c644e_49.png)

So to look at what we actually ran， so we said for Df。

I want to pull the Df dot scheme now we can also。Filter down。

 which was the original plan to each one of our numerical columns。

Why we left that out is that you can note that each one of the by default， when you run dot S。

 itll filter down to the numerical values。

![](img/d55700b8861616a13f8e694d2a6c644e_51.png)

So。

![](img/d55700b8861616a13f8e694d2a6c644e_53.png)

Sw vows。It's just going to give you a Skuw value。

![](img/d55700b8861616a13f8e694d2a6c644e_55.png)

Remember zero being no skew。A positive number being a right skew。

 a negative number being a left skew to tell you how skewed data your distribution is。



![](img/d55700b8861616a13f8e694d2a6c644e_57.png)

Now we are going to want to。

![](img/d55700b8861616a13f8e694d2a6c644e_59.png)

Filter down what we see here to only those above our Sku limit。 So we're going to say。

 I want my Skuw valves， which is this panda series here。

 such that the absolute value of these numerical values on the right。



![](img/d55700b8861616a13f8e694d2a6c644e_61.png)

![](img/d55700b8861616a13f8e694d2a6c644e_62.png)

Are greater than the skill limit。All right， that's all we're doing with this portion of the code。



![](img/d55700b8861616a13f8e694d2a6c644e_64.png)

And then we're just going to sort those values saying ascending equals false from largest to smallest。



![](img/d55700b8861616a13f8e694d2a6c644e_66.png)

So we see here we now only have values above 0。75 with the most skewed data on top and the least skewed above 0。

75 on the bottom。

![](img/d55700b8861616a13f8e694d2a6c644e_68.png)

![](img/d55700b8861616a13f8e694d2a6c644e_69.png)

![](img/d55700b8861616a13f8e694d2a6c644e_70.png)

Now let's take a quick look at the distributions that we are now going to have now that we have a transformation versus a non transformed version of our data。

The way that we're going to do this is we're going to specify the fields。

 it's going to be sale pricericier。

![](img/d55700b8861616a13f8e694d2a6c644e_72.png)

We're going to use Plt。splots。Now PLt。splots is going to allow you to graph two axes in one figure。

 so remember if the axes are going to be those bounding boxes so we're going to have two bounding boxes in one figure and then the figure is just going to be everything in relation to the actual output of our different visualizations。



![](img/d55700b8861616a13f8e694d2a6c644e_74.png)

![](img/d55700b8861616a13f8e694d2a6c644e_75.png)

![](img/d55700b8861616a13f8e694d2a6c644e_76.png)

We're also going to specify the fig size to be 10 by5。



![](img/d55700b8861616a13f8e694d2a6c644e_78.png)

So let's just pull this out real quick。

![](img/d55700b8861616a13f8e694d2a6c644e_80.png)

![](img/d55700b8861616a13f8e694d2a6c644e_81.png)

And we see we have two blank plots to start。

![](img/d55700b8861616a13f8e694d2a6c644e_83.png)

The next thing that we're going to do is plotdffield。hist， and we're going to run this。

 so we say Df field， we're just calling from pandas。The sale price fields。



![](img/d55700b8861616a13f8e694d2a6c644e_85.png)

Running a histogram， and we're saying using our pandas version of Matpllootlib。

 right rather than our default of Matpllootlib， we're using the built in pandas plotting functionality。

 we will say that we want to plot it on which axis and which bounding box the ae before。



![](img/d55700b8861616a13f8e694d2a6c644e_87.png)

Right？

![](img/d55700b8861616a13f8e694d2a6c644e_89.png)

That's what this one is going to do， and I'm going to copy that in。



![](img/d55700b8861616a13f8e694d2a6c644e_91.png)

And show you what that looks like。Oh， that didn't copy incorrect correctly just one second。

 we're going to copy this in。

![](img/d55700b8861616a13f8e694d2a6c644e_93.png)

![](img/d55700b8861616a13f8e694d2a6c644e_94.png)

So we didn't define sale price。Always make sure that you define your variables before running any code。

 and we see that it is filling in that first box and we see a right skewed data set。

 which makes sense， given that when we look here， our sale price is at around 1。6。

 It's a positive value。 So we have a positive skew。



![](img/d55700b8861616a13f8e694d2a6c644e_96.png)

![](img/d55700b8861616a13f8e694d2a6c644e_97.png)

![](img/d55700b8861616a13f8e694d2a6c644e_98.png)

![](img/d55700b8861616a13f8e694d2a6c644e_99.png)

The next thing that we do。

![](img/d55700b8861616a13f8e694d2a6c644e_101.png)

Is that we and again， I'm going to need this because it hasn't been defined because I'm pulling it out from here。

 He out that second box。

![](img/d55700b8861616a13f8e694d2a6c644e_103.png)

![](img/d55700b8861616a13f8e694d2a6c644e_104.png)

By running the same thing， except this time we are transforming that data using NP dot log 1P right。

 we did dot apply and what do we want to apply this function of the log of the values and we see we have a much more normally distributed data。



![](img/d55700b8861616a13f8e694d2a6c644e_106.png)

![](img/d55700b8861616a13f8e694d2a6c644e_107.png)

And we're using the X before， which is going to specify that this axis， this first one。

 and we can set the title， the Y label and X label， and do the same thing for X after。



![](img/d55700b8861616a13f8e694d2a6c644e_109.png)

![](img/d55700b8861616a13f8e694d2a6c644e_110.png)

And then for the entire figure， we can say that we want a super title that'll just be field sale price。



![](img/d55700b8861616a13f8e694d2a6c644e_112.png)

![](img/d55700b8861616a13f8e694d2a6c644e_113.png)

So we see that that's transforming it into a more normally distributed column and then finally we're going to do a skew transformation。

 we're going to leave out sale price here， so if you see we say four column in each one of our sw columns。



![](img/d55700b8861616a13f8e694d2a6c644e_115.png)

That's for each one that had above 0。75 that we defined earlier。



![](img/d55700b8861616a13f8e694d2a6c644e_117.png)

For each one of the index values。Assuming the columns not equal to sales price。

 if we say continue it's going to skip it over。Set that column equal to the log of itself。

So running that code， we have now transformed each one of those columns。



![](img/d55700b8861616a13f8e694d2a6c644e_119.png)

That we had here。So when we come back， we will talk about。



![](img/d55700b8861616a13f8e694d2a6c644e_121.png)

Looking through what we have left in regards to the data that we are working with。

 as well as working with one hot encoding。

![](img/d55700b8861616a13f8e694d2a6c644e_123.png)

![](img/d55700b8861616a13f8e694d2a6c644e_124.png)

![](img/d55700b8861616a13f8e694d2a6c644e_125.png)