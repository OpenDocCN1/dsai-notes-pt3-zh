# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P107：18_K最近邻笔记本（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's move on with question number 3。

![](img/6eeeac20ac3d52d82c3850278d81aad6_1.png)

We now have the different subsets of each one of our different features according to their data types。

 whether it's ordinal， categorical， without ordering numerical or binary。



![](img/6eeeac20ac3d52d82c3850278d81aad6_3.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_4.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_5.png)

We're going to use that in order to encode each one of them。

 and we know that we need to encode them because you can't pass in strings into our Scalar models。

 so we need to ensure that each one of them is passed through as a numerical value。



![](img/6eeeac20ac3d52d82c3850278d81aad6_7.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_8.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_9.png)

And then we're going to want to make sure to also scale each one of our numerical values。

 because if we do not scale， as we talked about during lecture。

 we won't be able to feed properly into ourane nearest neighbors without some type of bias or sw。

 according to those larger versus smaller numbers。

![](img/6eeeac20ac3d52d82c3850278d81aad6_11.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_12.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_13.png)

And then finally， once we pre process all our data。

 we're going to save that preprocessed data frame so that we can access it later without having to run through each one of these steps next time。



![](img/6eeeac20ac3d52d82c3850278d81aad6_15.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_16.png)

So we're going to import the label binizer， the label encoder， and the ordinal encoder。



![](img/6eeeac20ac3d52d82c3850278d81aad6_18.png)

Here we're just going to use the label binizer and the label encoder。

 so you see we initiate those objects as LB and LE。



![](img/6eeeac20ac3d52d82c3850278d81aad6_20.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_21.png)

Something I'd like to note is that we're able to use the label encoder for our ordinal values here。

 because our ordinal values are already in alphabetical order。 If they were not。

 we'd want to switch to using the ordinal encoder and go through the steps of ensuring that we're specifying which one of the values go first。

 which one go second and so on。

![](img/6eeeac20ac3d52d82c3850278d81aad6_23.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_24.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_25.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_26.png)

So we're going to initiate each one of those objects and then for each one of our ordinal variables。

 we're going to change that column in place。

![](img/6eeeac20ac3d52d82c3850278d81aad6_28.png)

To the ordinal version of that。 So it's just going to be whatever that string one was is going to be replaced by an integer。



![](img/6eeeac20ac3d52d82c3850278d81aad6_30.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_31.png)

So let's look back at what our ordinal variables were。

So we saw that our ordinal variables were contract， satisfaction and month。



![](img/6eeeac20ac3d52d82c3850278d81aad6_33.png)

And if we think back to our month。

![](img/6eeeac20ac3d52d82c3850278d81aad6_35.png)

It was these values that we have here and that by using PDd dot cut。

 we got the five different bins Now if we look at DF dot month now that we've used the label encoder。

 we see that。

![](img/6eeeac20ac3d52d82c3850278d81aad6_37.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_38.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_39.png)

We have replaced each one of those different bins with either zero。

 one or two or three or four because there's five different bins。



![](img/6eeeac20ac3d52d82c3850278d81aad6_41.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_42.png)

We then look at them as a category just to see how many unique values there are。

 as expected months as five， satisfaction as five， and the unique values for contract are three。

 and that was that month to month versus year versus two year contracts。



![](img/6eeeac20ac3d52d82c3850278d81aad6_44.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_45.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_46.png)

And we see the frequency for those top values as well。



![](img/6eeeac20ac3d52d82c3850278d81aad6_48.png)

We're then going to take each one of our binary variables。

 so all those that only had two options and use the LB。

 that label binizer that will just change them each two zeros and ones。



![](img/6eeeac20ac3d52d82c3850278d81aad6_50.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_51.png)

So that's essentially the one hot encoding just for those that only have two values。



![](img/6eeeac20ac3d52d82c3850278d81aad6_53.png)

And then finally， there may still be categorical variables。



![](img/6eeeac20ac3d52d82c3850278d81aad6_55.png)

Right out of our full initial list that are not ordinal and not binary。



![](img/6eeeac20ac3d52d82c3850278d81aad6_57.png)

And we need to ensure that we one hot and code those as well， so we're going to use that PDd。

get dummies that we've used before， and we're going to specify that we want to use the columns categorical variables。

 which we have now used excluding the ordinal as well as the binary variables。



![](img/6eeeac20ac3d52d82c3850278d81aad6_59.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_60.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_61.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_62.png)

And then when we set drop first equals to true， that's because as we talked about way earlier。

 if we have all them， we have perfect multicolinearity and there's no purpose for most models in terms of having that last feature。

 So if we start off with six different unique features。

 we'll end up with five columns and we'll know what that six column is。

 according to those other five。 So if all the other five are equal to 0。

 then we know that last one would have been equal to 1。

 If any one of those five features was equal to one。

 then we know that that six column would have been 0。 So there's no extra information there。

 So we just drop that first value。

![](img/6eeeac20ac3d52d82c3850278d81aad6_64.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_65.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_66.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_67.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_68.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_69.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_70.png)

We then called DF dot describe just to see each one of our different columns and we see their count。

 their mean their standard deviation and so on。 What we notice is that they're going to be on vastly different scales。

 right， the gigabytes per month， it's going to be around 20。



![](img/6eeeac20ac3d52d82c3850278d81aad6_72.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_73.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_74.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_75.png)

The monthly payment is going to be around 64， and a lot of these are going to be a lot lower besides those two。



![](img/6eeeac20ac3d52d82c3850278d81aad6_77.png)

And as we talked about， we want to ensure that everything's on the same scale。



![](img/6eeeac20ac3d52d82c3850278d81aad6_79.png)

So we're going to use the Min Macac Scalar here。

![](img/6eeeac20ac3d52d82c3850278d81aad6_81.png)

So we're importing the Min Macac Scalar。We're initiating the object。 So now we have M M。

 and then we're just going to transform not all of our variables。

 but our ordinal and our numeric variables。 So those that are。



![](img/6eeeac20ac3d52d82c3850278d81aad6_83.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_84.png)

Integers or those larger values， there's no point in doing a midmac scalealar on values that are just zeros and ones。

 so we' excluding those。

![](img/6eeeac20ac3d52d82c3850278d81aad6_86.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_87.png)

Sore replacing each one of them with their transformed versions of themselves。



![](img/6eeeac20ac3d52d82c3850278d81aad6_89.png)

And now when we run DF dot describe， we see that each one of these are on a similar scale。



![](img/6eeeac20ac3d52d82c3850278d81aad6_91.png)

And you know， values between0 and1， all of our values。

 and we have their different means and their different standard deviations。

 but all on a similar scale。 so now we'll be able to not be skewed by those lower or larger numbers。



![](img/6eeeac20ac3d52d82c3850278d81aad6_93.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_94.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_95.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_96.png)

And then finally， we want to save all of our preprocessed data。

 so we just set output file equal to the name of the file we want to output to。

 we take our data frame， which is our transform data frame called dot2 CSV。

 we don't want to save the index in that file and this will dump it into a CSV file that if we'd like to。

 we can access later。

![](img/6eeeac20ac3d52d82c3850278d81aad6_98.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_99.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_100.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_101.png)

All right that closes out question number three with that we will move into question number four in the next video and start actually using KNN along with our train test split in order to see how well we can predict whether or not a customer churn given our data set。



![](img/6eeeac20ac3d52d82c3850278d81aad6_103.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_104.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_105.png)

![](img/6eeeac20ac3d52d82c3850278d81aad6_106.png)