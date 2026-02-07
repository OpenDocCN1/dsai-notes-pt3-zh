# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P22：21_EDA笔记本解决方案（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_0.png)

Now let's look at question  three。And we're going to want to determine the following the number of each species present。

 so we won to see the count of each one of our three species。

 and we're going to use the dot value counts method that's going to be available for pandas series。

 so in the individual column， we're going to look at the mean median and the quantiles。

 quantiles being the 25th percentile 50th percentile and so on。

 as well as the ranges just from the minimum to the max for each pal and sepel measurement。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_2.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_3.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_4.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_5.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_6.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_7.png)

The hints that we have here are that the dot describe method。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_9.png)

Is going to have the median， but it won't be called median。

 it will be called the 50th quantile and it does not have the range。

 so we'll have to come up with that range ourselves。

 It does have the min in the maxo and we'll see that in just a second。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_11.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_12.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_13.png)

So the first thing we want to do is get the value counts。

 we're going to specify data from our data frame， we're going to pull out the species column and we just call value counts。

 we just call that method and we see that we have 50 of every single of each of the three species。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_15.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_16.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_17.png)

Now I'm going to break this out step by step if we look at stats。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_19.png)

Df。Sorry， let's actually look at data。describe and see what the output for the describe function is。

 it's a function that's available working with A panda's data frame， we see that it has the counts。

 the mean standard deviation， 25th， 50th percentile and so on。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_21.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_22.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_23.png)

And we know we only want the。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_25.png)

Different quantiles as well the mean， the median， the different quantiles and the range。

 so we're going to have to filter this down， but we're working stats Df is equal to this and we are working within app panda's data frame。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_27.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_28.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_29.png)

So the next thing that we're going to want to do is I'm going to copy over this line of code and show you just this output。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_31.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_32.png)

Let's first just do this before we set it equal to anything。

 and we're going to locate the max value and subtract the min value for each one of these different columns。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_34.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_35.png)

Right so we're doing dot Lo and we're just specifying the row。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_37.png)

Sorry， we didn't define this yet。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_39.png)

That'll make it clear。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_41.png)

And we have we see the mean for each one， and we're going to set that equal to。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_43.png)

We're going to pop in a row by using the dot Lo， and we're going to set that equal to the range。

 and that's going to be the index value。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_45.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_46.png)

And then at this point， if we look at stats Df， we see that we've now added on range。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_48.png)

The next thing that we do here is we specify the rows that we actually want to look at。

 which are going to be the mean， the 25th percentile， 50th， 75th percentile in range。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_50.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_51.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_52.png)

And then we're going to use。They dot look in order to get those outfield。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_54.png)

So just to show you how that works。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_56.png)

We have our。Outfields。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_58.png)

And we have our。Stat's Df。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_60.png)

And we're just going to do dot Lo。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_62.png)

Our out fields。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_64.png)

And that's going to specify I only want the mean 25th percentile， 50th percentile。

 75th percentile and range。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_66.png)

We're only selecting those rows， and we didn't specify any columns in our dot Lo so we got all of the columns。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_68.png)

The last thing that we do here is we just rename， and I'm not going to run this above as it's simple enough。

 we use the rename function and we say we want to rename this。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_70.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_71.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_72.png)

Row， which is 50 percentile to medium。And running all of that。

 we see that we have our median replacing that 50th percentile。

 and this is going to be all of the questions that were asked for。

 all the answers that were asked for in question three。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_74.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_75.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_76.png)

Moving on to question four。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_78.png)

They asked to calculate the following for each species in a separate data frame。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_80.png)

The mean of each measurements。 So you want the sepel length mean， the sepel width， mean。

 paddle width and paal length。 And then the median for each of these。

 And what we want to do here is leverage the group by method that's available for panda's data frames to group by the different species and calculate the statistic。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_82.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_83.png)

And then once you're able to find the mean and medium。

 we also want to show how we can calculate both statistics in a single table。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_85.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_86.png)

As well as later on， we're going to show you how to add on specific ones so you're not having to specify mean and medium for all of your features。

 but rather maybe for one of those features you want a different group by aggregation。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_88.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_89.png)

So starting with just the mean， we're going to use the data。 groupI。

 we specify that we are grouping by the different species。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_91.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_92.png)

And we have the mean values for each one of our different features， grouped by species。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_94.png)

We can get the median by just doing dot median。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_96.png)

And that method is available to us as well。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_98.png)

Now， assuming now that we have both of these available， we want to know。

 how can we get both of these in a single table？

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_100.png)

We're going to show you two different methods of doing so。

 There's going to be a list of recognized strings that will come up with the aggregation。

 So we say data duck group by， we're grouping by our species。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_102.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_103.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_104.png)

And we're doing dot Ag， rather than doing dot mean dot media。

 we can do dot Ag and pass in the type of aggregation functions that we want to use。

So here we see mean and median， another option would be any type of aggregation function that you personally want to pass through。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_106.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_107.png)

So we're going to run this just to see what that looks like。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_109.png)

So we get a multi level column where we have sepal length and then for sepal length。

 we have both the mean and the median， and the same fall for each one of the four different features。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_111.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_112.png)

What's special about this second version of using the aggregation versus the first is。

 let's say you wanted the product of all the values。

 So product is an aggregation that wouldn't be recognized here。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_114.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_115.png)

We can pass that through and you see that we have an error。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_117.png)

But there is a nuy product， product， meaning just multiplying all of them together。

 I can do NP dot products。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_119.png)

おます。Just so we don't have so many columns and P dot products。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_121.png)

And run this。And we see that it's obviously can to be a large number because it's multiplying them all together。

 we can pass in， we have more flexibility in regards to the different aggregation methods that we can pass through。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_123.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_124.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_125.png)

算 just说完了。Just in case you're looking at this， bring this back to what it was before。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_127.png)

And then we talked about what if we want to aggregate different fields differently？



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_129.png)

We can pass in a dictionary and saying that for each one of our different fields， we may want。

 you know mean median or max， just to show you what we're doing here。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_131.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_132.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_133.png)

'mDoing a dictionary comprehension。We're saying four fields in data。 columns。

 so for each one of our different fields， we want to have a dictionary where the key is that field name and the values are the list mean and medium。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_135.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_136.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_137.png)

As long as that field is not equal to species， right， we can't get the numerical。

 we're not going to get a numerical summary of the species。

 and that's going to be the field we want to group by as well。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_139.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_140.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_141.png)

So if I look at agict as it's currently formed。We now have set length and then mean median and then each of the four features。

 and then the list mean and media。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_143.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_144.png)

The next thing that we do is we replace pedal length with just the max。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_146.png)

So now that we have Agic defined。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_148.png)

We're just going to set that equal to the max and we see that we are replacing that value before pedal length was mean and median。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_150.png)

Now we see it's just equal to max。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_152.png)

We run P print， that's just going to be a prettier version of printing out outputs。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_154.png)

And then finally， we're going to use data doc group。 We're going to group by the different species。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_156.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_157.png)

And then we're going to use the dot Ag functionality。

 and we're going to pass in our dictionary that'll tell us for each one of the features。

 how do we want to aggregate it and we'll get the mean and mediumn for each feature。

 But for pal length， we will get the max。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_159.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_160.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_161.png)

And we see that here that for pal length， we got the max。

 and then we got the mean and medium for each of the other four features。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_163.png)

Let's go into question five and then we'll take a break before going into question six。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_165.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_166.png)

We're going to start here with mattepllootlib， and we want to make a scatter plotot of sepel length versus Sepel width using matteplotlib。

 and we're going to label the axes and give the plot a title as well。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_168.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_169.png)

So as we discussed in lecture， we want to import Matpllootlibib。piplloot as PLT。

 that's going to be just the most common practice when working with MatpllootlibB。

 and then we have to run this magic function。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_171.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_172.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_173.png)

Percentage mat plotlib space inline for any of our output four graphs to show up within our Jupyter notebook。

 So we run that。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_175.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_176.png)

We're going to set our axes， which is just going to be essentially the。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_178.png)

Graph or the container of our image is just going to have the different axes。

 We also have the figure which will just have all of the information in regards to our graph。

 but we can focus right now in just running PLT。 axes。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_180.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_181.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_182.png)

So we set x equal to our axis， which is just our box， which is now empty。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_184.png)

And within our box， we want to enter a scatter plot， so we just do a dot scatter。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_186.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_187.png)

We pass in as the x values data。sple length， as our y values data。sple width。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_189.png)

When we're working with axes， we can sayax dot set and pass in a bunch of arguments in regards to labeling our X axis。

 our y axis as well as our overall title， which is what we do here with the X label。

 Y label and title。

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_191.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_192.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_193.png)

I run this and you see that we have our full title。

 we have the Sepel width as our Y label and our Sepel length as our X label。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_195.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_196.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_197.png)

So we're going to take a break here， and when we come back。

 we'll jump into question six and talk about making a histogram。



![](img/32459848e4cc7a7ac8fcd4405b0d10a8_199.png)

![](img/32459848e4cc7a7ac8fcd4405b0d10a8_200.png)