# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P21：20_08 01 t置信区间.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/3a5eb512d8b76830a4d1436f3693b598_0.png)

Hi， my name is Brian Cathho and welcome to the lecture on Tea conference intervals。



![](img/3a5eb512d8b76830a4d1436f3693b598_2.png)

This is part of the Coursera Staistical In class， which is part of our Coursera data science specialization。

 The classes co taught with my co instructorors Jeff Leak and Roger Pang。

 were all in the Department of Biosstatistics at the Johns Hopkins Bloomberg School of Public Health。



![](img/3a5eb512d8b76830a4d1436f3693b598_4.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_5.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_6.png)

In the previous lecture， we discussed creating compete intervals using the central limit theorem。

 All the intervals we discussed took the form of estimate plus or minus a quantile from the standard normal distribution times the estimated standard error of the estimate。



![](img/3a5eb512d8b76830a4d1436f3693b598_8.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_9.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_10.png)

In this lecture， we're going to discuss some methods for small samples。 Notably。

 we're going to talk about student or gossipss tea distribution and tea confidence intervals。



![](img/3a5eb512d8b76830a4d1436f3693b598_12.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_13.png)

These intervals are going to be of the form estimate plus or minus a t quantile times the standard error of the estimate。



![](img/3a5eb512d8b76830a4d1436f3693b598_15.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_16.png)

So the only change is we've changed this Z quantile to a T quantile。



![](img/3a5eb512d8b76830a4d1436f3693b598_18.png)

The tea distribution has heavier tails than the normal distribution。

So these intervals are going to be a little bit wider。

These are some of the handiest intervals in all the statistics。

And if you ever want to rule between when to use a T interval or a Z interval for the cases where both are available。

 simply use the T interval because as you collect more data。

 the T interval will just become more and more like the Z interval anyway。



![](img/3a5eb512d8b76830a4d1436f3693b598_20.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_21.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_22.png)

We're just going to cover the single and two group version of the T interval。

 and our regression class will cover some other T intervals that come in handy as well。

 The T distribution was invented by William Gossett under the pseudonym student in 1908。



![](img/3a5eb512d8b76830a4d1436f3693b598_24.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_25.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_26.png)

He worked for the Guinness Bweery， and in fact， I didn't want him to publish under his real name。

 So he published under the pseudonym students。 So we're often talking about the student's tea distribution or the student's tea test。



![](img/3a5eb512d8b76830a4d1436f3693b598_28.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_29.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_30.png)

The T distribution has thicker tails than the normal。



![](img/3a5eb512d8b76830a4d1436f3693b598_32.png)

Unlike the normal， which is indexed by two parameters， the mean in the variance。

 we really only talk about the t distribution as it is centered around 0 with a standard formula for the scale。



![](img/3a5eb512d8b76830a4d1436f3693b598_34.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_35.png)

It's only indexed by one parameter， the so called degrees of freedom。

 as these degrees of freedom increase， it gets more like a standard normal。



![](img/3a5eb512d8b76830a4d1436f3693b598_37.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_38.png)

The reason for the T distribution is as follows。 If we take X bar。

 subtract off the mean and divide by the estimated standard error for I I D Gaussian data。



![](img/3a5eb512d8b76830a4d1436f3693b598_40.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_41.png)

It in fact， is not Gaussian distributed。

![](img/3a5eb512d8b76830a4d1436f3693b598_43.png)

If we replaced S by sigma， it would be exactly standard normal。 However， when we replace sigma by S。

 it no longer has a distribution as that of a standard normal。 Instead， it has a T distribution。



![](img/3a5eb512d8b76830a4d1436f3693b598_45.png)

As N increases， this distinction is irrelevant。However， for small sample sizes。

 the difference can be quite large。 and so if you use a standard normal for small sample sizes。

 you can get， for example， confidence intervals that are too narrow。



![](img/3a5eb512d8b76830a4d1436f3693b598_47.png)

Our interval winds up to be x bar plus or minus the t quantile with the degrees of freedom n minus1 times the estimated standard error。

 We'll go through some examples， and I hope you'll get the hang of it。



![](img/3a5eb512d8b76830a4d1436f3693b598_49.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_50.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_51.png)

Here， I use our studios manipulate function to show the T distribution as it overlays over the normal distribution for varying degrees of freedom。

 Here I have it for 20 degrees of freedom。 And you can see they're quite similar as I draw the degrees of freedom down。

 you can see that the T distribution gets to the point where it has heavier tails。

 what it always has heavier tails。 and it looks like a normal distribution。

 Where if you were to squash it down。

![](img/3a5eb512d8b76830a4d1436f3693b598_53.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_54.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_55.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_56.png)

Sort of squash it down right there and。The extra mass had to head out in the tails。



![](img/3a5eb512d8b76830a4d1436f3693b598_58.png)

It's a little bit hard to see the impact because so much of this plot is devoted to the peaked part of the distributions where they're actually fairly similar。



![](img/3a5eb512d8b76830a4d1436f3693b598_60.png)

Let's plot the quantiles。

![](img/3a5eb512d8b76830a4d1436f3693b598_62.png)

So what I'm showing in this plot now。

![](img/3a5eb512d8b76830a4d1436f3693b598_64.png)

Are the quantiles of the T distribution by the quantiles of the normal distribution starting at the 50th percentile。

 So， for example， we start at 0 and since。At the 50th percentile。

 since both distributions are symmetric about zero。

 you see that  zero is the 50th percentile so this plot goes through the 000。

 I don't plot percentiles lower than the 50th percentile because the distributions are symmetric and that information is redundant。

What I've drawn here。Our reference lines at the 97。5th Quanto。 This will always be around 1。

96 for the standard normal distribution， but can be quite a bit larger for the T distribution。

 For example， right now with。

![](img/3a5eb512d8b76830a4d1436f3693b598_66.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_67.png)

Two degrees of freedom。We get a T quantntile that is over four。Now。



![](img/3a5eb512d8b76830a4d1436f3693b598_69.png)

Let me emphasize， though， with two degrees of freedom。

 that would mean in our T interval that you only had three data points in order to estimate your variance。

 which is not too many。

![](img/3a5eb512d8b76830a4d1436f3693b598_71.png)

Let's bump it up to。

![](img/3a5eb512d8b76830a4d1436f3693b598_73.png)

20 degrees of freedom。And now， what we see is that the。

T quantiles are much closer to the normal quantiles right here in this light blue reference line is an identity line。

 If the T quantiles were exactly identical to the normal quantiles。

 they would just follow on that line。 I have again， at 1。96 and the relevant T quantile。I show the。



![](img/3a5eb512d8b76830a4d1436f3693b598_75.png)

Reference lines here， so this distance right here。

![](img/3a5eb512d8b76830a4d1436f3693b598_77.png)

Is exactly the distinction between the two intervals。

Where now with the T interval we're going to have a quantile that's slightly larger than two。

 whereas for the z quantile， we're going to have one that's slightly smaller than two。

 This can make a fairly sizable difference in the intervals and often can make the difference between the interval containing zero versus the interval not containing zero。



![](img/3a5eb512d8b76830a4d1436f3693b598_79.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_80.png)

And nonetheless， this is why we use the T distribution， this plot， this quantile plot is such that。



![](img/3a5eb512d8b76830a4d1436f3693b598_82.png)

This。T interval。The T quantile is always going to be above this blue reference line。

 which is effectively saying that the T constructed confidence interval will always be wider than the normal interval。

 which makes sense we have an extra parameter that we're assuming we're estimating the standard deviation。

 and so it would make sense that that uncertainty would cause us to have wider intervals。



![](img/3a5eb512d8b76830a4d1436f3693b598_84.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_85.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_86.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_87.png)

Let's go through a couple notes about the T interval。

So the T interval technically assumes that the data are IID normal。

 though it's very robust to this assumption。

![](img/3a5eb512d8b76830a4d1436f3693b598_89.png)

Basically， whenever the distribution is roughly symmetric in mound shaped。

 the T interval will work fairly well。

![](img/3a5eb512d8b76830a4d1436f3693b598_91.png)

If you have paired observations， for example， when you measure something once and then is the same unit a few days later or for a second measurement。

 and we'll go through some examples。

![](img/3a5eb512d8b76830a4d1436f3693b598_93.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_94.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_95.png)

You can use the T interval to analyze this kind of data by taking differences or differences on the log scale。



![](img/3a5eb512d8b76830a4d1436f3693b598_97.png)

![](img/3a5eb512d8b76830a4d1436f3693b598_98.png)

For large degrees of freedom， the T quantiles become exactly like that of the standard normal quantile。

 So the T interval converges to that of the normal interval。

 the same one that you would obtain with the central limit theorem。Because of this。I。

 instead of saying， instead of between picking between the T interval and the normal interval。

 I always say just use the T interval。For distributions that are skewed。The spirit of the T interval。

 assumptions are violated。And so you could either work on this data on the log scale。

 where logging will often take care of the skewness of the data。Or you can use other procedures。

For example， creating bootstrarappped confidence intervals。Nonetheless。

 it simply doesn't make sense to use the T interval for skewed distributions because it in a lot of ways it doesn't make sense to center intervals for skewed distributions at the mean。

Also， I would add for highly discrete data， like binary or Poson data。 Other intervals are available。

 and it's probably preferable to use them to the T interval。

