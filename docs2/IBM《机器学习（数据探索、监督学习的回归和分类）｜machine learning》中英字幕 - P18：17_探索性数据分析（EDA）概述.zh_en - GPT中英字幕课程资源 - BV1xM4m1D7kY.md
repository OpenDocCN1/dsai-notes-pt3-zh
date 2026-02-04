# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P18：17_探索性数据分析（EDA）概述.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this section， we'll move on to the next all important step in our machine learning workflow。

Namely exploratory data analysis or EDA。So what are going to be our learning goals for this section？

We're going to discuss different approaches to conducting exploratory data analysis。

 which I'm just going to call EDA from here on。

![](img/28fa620a2f937ffc1cedf22e88e35c1d_1.png)

We'll talk about different EDA techniques， both statistical as well as visual techniques。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_3.png)

We'll use sampling to take a peek into our data。

![](img/28fa620a2f937ffc1cedf22e88e35c1d_5.png)

And it'll show how to produce useful visualizations when we're actually doing our EDA。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_7.png)

So what is exploratory data analysis？EDA is going to be the approach to analyzing data sets to summarize their main characteristics。

 often with visual methods， and as we'll see with statistical summaries as well。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_9.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_10.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_11.png)

And why is this EDA useful， I want you to think of it as your initial conversation with the data before getting started。

 it's kind of a getting to know you phase with your data set。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_13.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_14.png)

So this will determine if the data that we're looking at actually makes sense or if we need further cleaning or if more data is actually needed。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_16.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_17.png)

And EDA will help us identify patterns and trends in the actual data set。

 and sometimes this can be as important， if not more important than the actual findings from the modeling。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_19.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_20.png)

So some summary statistics that we do typically do with EDA， looking at the average， the median。

 the min， the max， the correlations between different columns。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_22.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_23.png)

Or we can look at the visualizations given our columns。

 we can look at histograms in order to see the distribution。

 the scatter plots to see the correlations or the relationship between two different columns。

 and box plots again to look at that distribution and to identify outliers and many others。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_25.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_26.png)

When we're doing data wrangling or if we're looking at those summary statistics。

 we're generally going to be using the Pandadas library。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_28.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_29.png)

And then for visualization， we will rely on the library's Mattplot Lib and Seaborn。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_31.png)

So an example of EDA for job applicant summary statistics。

 supposed we want to examine the characteristics of our job applicants。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_33.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_34.png)

We can look at the average， we can take the average of all interview scores。

 or maybe break it down by city or job function so that we can compare applicant scores to the averages of their direct competitors。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_36.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_37.png)

you can look at maximum values or hear more like the mode value to see which words were most common from all the applicants given the application materials。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_39.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_40.png)

Finally， we can look at correlations， we can look at the different correlations between technical assessments and the years of experience of our applicants。

 perhaps breaking it down again by type of experience so we're comparing against their direct competitors。

 and this allows us to see there's any type of initial relationship between different columns that may be worth being immediately being aware of。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_42.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_43.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_44.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_45.png)

Before doing any modeling。

![](img/28fa620a2f937ffc1cedf22e88e35c1d_47.png)

So let's discuss sampling from data frames for just a second。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_49.png)

Now there are many reasons to consider random samples from our data frames。For larger data sets。

 we may want to shrink down to a random sample if the computation would take too long for the larger data。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_51.png)

We may want to train models on a random sample of the data and hold out another set for testing later on。

 and we'll see more efficient ways of doing that than the code on the left later on。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_53.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_54.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_55.png)

We may also want a sample that is indicative of the proportions of the different observations of our outcome variables now what do I mean by this。

 let's say that you are working with a data that's supposed to determine whether or not a certain person has a terrible disease and only1% of the entire population has that disease。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_57.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_58.png)

If you want a sample， you also want to ensure assuming there's only 1% that have the disease。

 you want to ensure that you keep that proportion in your sample data set。

 so you want it to be a similar proportion， you want to ensure that you don't end up with a sample that doesn't have anybody with the infection which is possible or with an overrepresentation of that disease。

 so that's where this is called stratified sampling may come into play。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_60.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_61.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_62.png)

Now looking to the code on the left， what is that going to do for us？



![](img/28fa620a2f937ffc1cedf22e88e35c1d_64.png)

First， we are assuming that data is going to be a panda's data frame。

 and A panda's data frame has the method sample method is another word for a function that's available for a certain Python object。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_66.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_67.png)

And that sample method is going to allow us to take a random amount of rows from our actual data frame。

 So here we're saying n equals 5。 And we're also passing the argument replace equals false。

 That will be the default value。 Actually， if our equaled true。

 Then we can end up having the same row show up more than once。

 So this ensures that every row only shows up once in our sample。 And then we are going to print。

 We're taking our sample now， which only has five rows。 die dot I Lo。 we're taking all of the rows。

 That's what the colon there means。 And then we're only taking the last three columns。

 negative 3 through to the end is what negative three colon means。

 And we get the output we see here on the right。 with petal length， pedal width and species。

 which were the last three columns and the five random rows that showed up with our sample。😊。



![](img/28fa620a2f937ffc1cedf22e88e35c1d_69.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_70.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_71.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_72.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_73.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_74.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_75.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_76.png)

![](img/28fa620a2f937ffc1cedf22e88e35c1d_77.png)