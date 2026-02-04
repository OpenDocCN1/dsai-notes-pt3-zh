# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P106：17_K最近邻笔记本（选修部分）第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/d87d0b9b639520ef6954b0ebfea015b0_0.png)

Welcome to our lab on Ka nearest neighborighs here we're going to be working with a data set that's going to be a customer churn data set。

 so we've been talking about customer churn now we will look at an actual data set where we will have customer data usage of long distance。

 data usage， monthly revenue， etc in terms of the different features available and we want to predict the likelihood of customer churning or not churn。



![](img/d87d0b9b639520ef6954b0ebfea015b0_2.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_3.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_4.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_5.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_6.png)

We're going to be using this subset of customers who have phone accounts and since the data include a mix of numeric。

 categorical as well as ordinal variables， we'll have to load this data and do some prepro and then use the can nearest neighbors to predict whether or not the personal churn。



![](img/d87d0b9b639520ef6954b0ebfea015b0_8.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_9.png)

So after completing this lab， you should have a working understanding of how to prepro a variety of variables in order to apply k nearest neighbors and understand how to choose K and how to evaluate model performance。



![](img/d87d0b9b639520ef6954b0ebfea015b0_11.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_12.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_13.png)

So the first thing that we're going to do is we're going to import the data this time it's actually going to be in this Python file and we're going to import churn data。

 which will be the data that we want to import。

![](img/d87d0b9b639520ef6954b0ebfea015b0_15.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_16.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_17.png)

Then for question one， we just want to import the data， examine the columns and data。

 we want to remove certain columns that we have listed here and take an initial look at the data for both numeric and nonnumeric features。



![](img/d87d0b9b639520ef6954b0ebfea015b0_19.png)

So we have our churn data， which is going to be a panda's data frame itself。

 we're going to set DF equal to that just with these columns drop。

 so we just call dot drop and we're dropping these columns which we don't need and what we're trying to perform here。



![](img/d87d0b9b639520ef6954b0ebfea015b0_21.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_22.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_23.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_24.png)

The next thing that we want to do is look at Df。describe here we're just rounding everything to two decimal places so we don't have too many scientific notation and know large decimals。

 but we see for our columns months， gigabytes per month or months is how many months we've had them as a customer。

 gigabytes per month， their monthly payments， how satisfied they are， and the churn value。

 which should be either 001。

![](img/d87d0b9b639520ef6954b0ebfea015b0_26.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_27.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_28.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_29.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_30.png)

And when we look at this we see that the number of months is around 32。

 We can look at the minimum and maximum from 1 to 72。

 there's a pretty large standard deviation compared to the mean。

 so you get to start to get an idea of these numerical values， same with the gigabytes per month。

 The monthly amount that's paid， also has a large standard deviation。

 seems that each of these have fairly large standard deviation。

 The satisfactions is going to be a scoring between one and five。



![](img/d87d0b9b639520ef6954b0ebfea015b0_32.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_33.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_34.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_35.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_36.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_37.png)

And then our churn values just values between zero and 1， where about 27% actually churn。



![](img/d87d0b9b639520ef6954b0ebfea015b0_39.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_40.png)

Then we do DF。 describe and we include objects。And here we're looking at all of our categorical or those initially brought in us strings。

 And we see for each one of these the number of unique values。

 what's the top value and then how often that top value is showing up。

 And we see that we have a lot of binary features here with a lot of these twos some of them。

 you know， the different offers has six。 The top one being none is a little bit problematic。

 but we'll just assume that there's some type of encoding and there not being any type of offer。



![](img/d87d0b9b639520ef6954b0ebfea015b0_42.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_43.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_44.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_45.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_46.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_47.png)

And then for fiber optic is just going to be the internet type。

 and then we see that for month to month for contract。

 and we can dive into the different types of objects and categories that are available to us。



![](img/d87d0b9b639520ef6954b0ebfea015b0_49.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_50.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_51.png)

For question two， we want to identify which variables are binary。

Which ones are categorical and not ordial， which ones are categorical and ordinal。

 and which ones are numeric？

![](img/d87d0b9b639520ef6954b0ebfea015b0_53.png)

And then each one of the non numeric features will need to have to encode in some form in order to feed it into our machine learning model。



![](img/d87d0b9b639520ef6954b0ebfea015b0_55.png)

So we're going to start by identifying the number of unique values in each variable so that we can find that binary versus categorical and not binary。

 then we're going to list out the categorical numerical binary and ordinal。

 we're going to note that the variable months it can be treated as numeric。

 the number of months that someone has been as a customer we're going to treat it as ordinal and we'll see how we do that towards the end of as we go through the solution。

 and then for the other categorical variables we want to make sure that we just encode them either ordinly or ones in zeros。



![](img/d87d0b9b639520ef6954b0ebfea015b0_57.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_58.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_59.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_60.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_61.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_62.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_63.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_64.png)

So the first thing that we want to do is see the number of unique， all we have to do is we're on DF。

 and unique， so we see the number of unique values。

 something like months should have quite a lot internet type has you know only four as we saw before。

 we see a bunch of twos and then monthly which is their monthly payments can have a large range of values of unique values。



![](img/d87d0b9b639520ef6954b0ebfea015b0_66.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_67.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_68.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_69.png)

We're then going to see which one of those only have two， so we're just filtering it down DF Unis。



![](img/d87d0b9b639520ef6954b0ebfea015b0_71.png)

Such that there's only two values， which is what we see here。

 and then we pull out the index and when we run that we see that we get the different columns for which we only had two unique values。



![](img/d87d0b9b639520ef6954b0ebfea015b0_73.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_74.png)

Then for all of our categorical variables， we're saying besides for these binaries。



![](img/d87d0b9b639520ef6954b0ebfea015b0_76.png)

But they're still categorical， we're assuming those are the ones with at least two values。

 up till six values， so greater than two and less than or equal to6。



![](img/d87d0b9b639520ef6954b0ebfea015b0_78.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_79.png)

And we see the values that these are the columns that have at least two values and less than six unique values。



![](img/d87d0b9b639520ef6954b0ebfea015b0_81.png)

And with that， we are running this。

![](img/d87d0b9b639520ef6954b0ebfea015b0_83.png)

L comprehension。

![](img/d87d0b9b639520ef6954b0ebfea015b0_85.png)

To look at four I in each one of our categorical variables， that's that list we just defined。

 we want both I， as well as the unique values for that column。 So when we run this， we see for offer。

 each one of the six unique values offer A， B， C， D， E， and none for the Internet type。

 each of the unique values， so on and so forth。

![](img/d87d0b9b639520ef6954b0ebfea015b0_87.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_88.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_89.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_90.png)

So we're going to say off the top that our ordinal variables here are going to be contract and satisfaction。

 contract， meaning that one year is more than month to month and two years is more than one year。

 but the difference isn't necessarily all going to be equal to one another。 So there's an ordering。

 but that ordering maybe does not mean much。 We're going to end up encoding those as 0，1，2。

 and then satisfaction is just going to be the values 1 through 5。



![](img/d87d0b9b639520ef6954b0ebfea015b0_92.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_93.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_94.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_95.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_96.png)

We then look at months， we see that we have the unique values for months。

 we're going to include that as our ordinal variables。

 so we're just going to append that into our list and what we're doing here is creating lists of our ordinal variables。

 of our binary variables and as of our overall categorical variables。



![](img/d87d0b9b639520ef6954b0ebfea015b0_98.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_99.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_100.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_101.png)

So now we have our ordinal variables。With contract， satisfaction and months。



![](img/d87d0b9b639520ef6954b0ebfea015b0_103.png)

We're then going to pull out our numeric variables， and that's going to be all of our columns。DF。

t columns and just subtract out our ordinal variables and our categorical variables and our binary variables。



![](img/d87d0b9b639520ef6954b0ebfea015b0_105.png)

So some of them may have been numeric before， so it would have been unable to just say pull out those D types。

 those data types， So instead we take all the categories that we just defined。

 we subtract them all out and we end up with just our numeric variables。

 And if we look now we can see that our numeric variables。



![](img/d87d0b9b639520ef6954b0ebfea015b0_107.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_108.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_109.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_110.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_111.png)

Are just monthly。The monthly payments and the gigabytes per month。



![](img/d87d0b9b639520ef6954b0ebfea015b0_113.png)

We can then look at a histogram of each one of our different numeric variables。

 we see that gigabytes per month is pretty heavily skewed to the lower end with some outliers out towards 80 and then monthly has fairly normal。

 maybe a b left skewed except for that large one low values all the way to the left。



![](img/d87d0b9b639520ef6954b0ebfea015b0_115.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_116.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_117.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_118.png)

And then what we're going to do here with our month variable is we're going to call cut and what that's going to do is it's going to create bins。

 so we're going to replace months。

![](img/d87d0b9b639520ef6954b0ebfea015b0_120.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_121.png)

With bins， five different bins， and I'll show you what this looks like in just a second。



![](img/d87d0b9b639520ef6954b0ebfea015b0_123.png)

I do want you to note， well， let's look at it first before I make that note now if we look at Df。

t months。

![](img/d87d0b9b639520ef6954b0ebfea015b0_125.png)

We have five different bins of equal stretch， where it goes from about 0。9 to 15。2， 15。2 to 29。4。

 so on and so forth up until the largest value。

![](img/d87d0b9b639520ef6954b0ebfea015b0_127.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_128.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_129.png)

In five different equal cuts。Now these are going to be useful to be named as they are。

 generally speaking， if you want to create bins， you can also pass in。



![](img/d87d0b9b639520ef6954b0ebfea015b0_131.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_132.png)

Your own labels， and you just have to make sure， you know， you can do something like labels equals。

Lu。

![](img/d87d0b9b639520ef6954b0ebfea015b0_134.png)

Low medium and so on。 Make sure there's  five to match up with the five bins。

 We can't do that now because we replace months in place。 But if you do create this。

 you do use this pandas dot cut， do note that you can actually pass in the actual labels as well as where you want the cuts to happen here by default。

 it'll create these names and equal cuts。

![](img/d87d0b9b639520ef6954b0ebfea015b0_136.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_137.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_138.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_139.png)

Allright， that's our first portion of just grouping out each one of our different categorical versus binary versus ordinal versus numerical variables and the next section we'll go about actually encoding those all into numerical values and scaling them to ensure that we could feed them into our Can nearest neighbors model。



![](img/d87d0b9b639520ef6954b0ebfea015b0_141.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_142.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_143.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_144.png)

![](img/d87d0b9b639520ef6954b0ebfea015b0_145.png)