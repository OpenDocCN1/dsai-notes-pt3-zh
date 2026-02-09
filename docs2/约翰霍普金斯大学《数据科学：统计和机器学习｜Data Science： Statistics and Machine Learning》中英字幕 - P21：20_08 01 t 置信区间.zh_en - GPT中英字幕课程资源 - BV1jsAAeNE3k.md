# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P21：20_08 01 t 置信区间.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

![](img/0978c53e039e6206f40e10d22418f19c_0.png)

Hi， my name is Brian Caho and welcome to the lecture on Tea conference intervals。

 This is part of the Coursera Staistic inference class。

 which is part of our Coursera data science specialization。

 The class is co taught with my co instructorors， Jeff Leeak and Roger Pang。

 We all in the Department of Biosstatistics at the Johns Hopkins Bloomberg School of Public Health。😊。



![](img/0978c53e039e6206f40e10d22418f19c_2.png)

In the previous lecture， we discussed creating compete intervals using the central limit theorem。

 All the intervals we discussed took the form of estimate plus or minus a quantile from the standard normal distribution times the estimated standard error of the estimate。

In this lecture， we're going to discuss some methods for small samples。 Notably。

 we're going to talk about student or gossipss， tea distribution and tea confidence intervals。

These intervals are going to be of the form estimate plus or minus a t quantile times the standard error of the estimate。

So the only change is we've changed this Z quantile to a T quantile。

The T distribution has heavier tails than the normal distribution。

So these intervals are going to be a little bit wider。

These are some of the handiest intervals in all the statistics。

And if you ever want to rule between when to use a T interval or a Z interval for the cases where both are available。

 simply use the T interval because as you collect more data。

 the T interval will just become more and more like the Z interval anyway。

We're just going to cover the single and two group version of the T interval。

 and our regression class will cover some other T intervals that come in handy as well。

 The T distribution was invented by William Gossett under the pseudonym student in 1908。



![](img/0978c53e039e6206f40e10d22418f19c_4.png)

![](img/0978c53e039e6206f40e10d22418f19c_5.png)

He worked for the Guinness Bweery， and in fact， I didn't want him to publish under his real name。

 So he published under the pseudonym students。 so we're often talking about the student's tea distribution or the student' tea test。

The T distribution has thicker tails than the normal。Unlike the normal。

 which is indexed by two parameters， the mean in the variance。

 we really only talk about the t distribution as it is centered around  zero with a standard formula for the scale。

It's only indexed by one parameter， the so called degrees of freedom。

 as these degrees of freedom increase， it gets more like a standard normal。



![](img/0978c53e039e6206f40e10d22418f19c_7.png)

The reason for the T distribution is as follows。 If we take X bar。

 subtract off the mean and divide by the estimated standard error for II D Gaussian data。It in fact。

 is not Gaussian distributed。If we replaced S by sigma， it would be exactly standard normal。 However。

 when we replace sigma by S， it no longer has a distribution as that of a standard normal。 Instead。

 it has a T distribution。As N increases， this distinction is irrelevant。However。

 for small sample sizes， the difference can be quite large。

 and so if you use a standard normal for small sample sizes， you can get， for example。

 confidence intervals that are too narrow。

![](img/0978c53e039e6206f40e10d22418f19c_9.png)

Our interval winds up to be x bar plus or minus the t quantile with the degrees of freedom n minus1 times the estimated standard error。

 we'll go through some examples and I hope you'll get the hang of it。



![](img/0978c53e039e6206f40e10d22418f19c_11.png)

Here， I use our studios manipulate function to show the T distribution as it overlays over the normal distribution for varying degrees of freedom。

 Here I have it for 20 degrees of freedom。 And you can see they're quite similar。

 as I draw the degrees of freedom down。 You can see that the T distribution gets to the point where it has heavier tails。

 Well it always has heavier tails， and it looks like a normal distribution。

 Where if you were to squash it down。Sort of squash it down right there and。

The extra mass had to head out in the tails。It's a little bit hard to see the impact because so much of this plot is devoted to the peaked part of the distributions where they're actually fairly similar。



![](img/0978c53e039e6206f40e10d22418f19c_13.png)

Let's plot the quantiles。So what I'm showing in this plot now。

Are the quantiles of the T distribution by the quantiles of the normal distribution starting at the 50th percentile。

 So， for example， we start at 0 and since。At the 50th percentile。

 since both distributions are symmetric about  zero。

 you see that 0 is the 50th percentile so this plot goes through the 000。

 I don't plot percentiles lower than the 50th percentile because the distributions are symmetric and that information is redundant。

What I've drawn here。Our reference lines at the 97。5 quantno。 This will always be around 1。

96 for the standard normal distribution， but can be quite a bit larger for the T distribution。

 For example， right now with。Two degrees of freedom。We get a T quantntile that is over four。Now。

Let me emphasize， though， with two degrees of freedom。

 that would mean in our T interval that you only had three data points in order to estimate your variance。

 which is not too many。Let's bump it up to。

![](img/0978c53e039e6206f40e10d22418f19c_15.png)

20 degrees of freedom。And now what we see is that the T quantiles are much closer to the normal quantiles right here in this light blue reference line is an identity line。

 If the t quantiles were exactly identical to the normal quantiles。

 they would just follow on that line I have again at 1。96 and the relevant t quantile。I show the。

Reference lines here， so this distance right here is exactly the distinction between the two intervals。

Where now with the T interval we're going to have a quantile that's slightly larger than  two。

 whereas for the z quantile we're going to have one that's slightly smaller than two this can make a fairly sizable difference in the intervals and often can make the difference between the interval containing zero versus the interval not containing zero。

And nonetheless， this is why we use the T distribution， this plot， this quantile plot is such that。

This。T interval。The T quantile is always going to be above this blue reference line。

 which is effectively saying that the T constructed confidence interval will always be wider than the normal interval。

 which make sense we have an extra parameter that we're assuming we're estimating the standard deviation。

 and so it would make sense that that uncertainty would cause us to have wider intervals。



![](img/0978c53e039e6206f40e10d22418f19c_17.png)

Let's go through a couple notes about the T interval。

So the T interval technically assumes that the data are IID normal。

 though it's very robust to this assumption。Basically。

 whenever the distribution is roughly symmetric in mound shaped。

 the T interval will work fairly well。If you have paired observations， for example。

 when you measure something once and then the is the same unit a few days later or for a second measurement and we'll go through some examples。

You can use the T interval to analyze this kind of data by taking differences or differences on the log scale。

For large degrees of freedom， the T quantiles become exactly like that of the standard normal quantile so the T interval converges to that of the normal interval。

 the same one that you would obtain with the central limit theorem。Because of this。I。

 instead of saying， instead of between picking between the T interval and the normal interval。

 I always say just use the T interval。For distributions that are skewed。

The spirit of the T interval assumptions are violated。



![](img/0978c53e039e6206f40e10d22418f19c_19.png)

And so you could either work on this data on the log scale。

 where logging will often take care of the skewness of the data。Or you can use other procedures。

For example， creating bootstpped confidence intervals。Nonetheless。

 it simply doesn't make sense to use the T interval for skewed distributions because it in a lot of ways it doesn't make sense to center intervals for skewed distributions at the mean。

Also， I would add for highly discrete data， like binary or Poson data。 Other intervals are available。

 and it's probably preferable to use them to the T interval。

