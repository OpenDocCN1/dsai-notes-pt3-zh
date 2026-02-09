# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P27：26_09 03 t检验.zh_en - GPT中英字幕课程资源 - BV1oG41197es

Consider our example again。 Suppose that n was 16 rather than 100。



![](img/22f1989e38beea36e4732494bcbf90fe_1.png)

![](img/22f1989e38beea36e4732494bcbf90fe_2.png)

Then our test statistic remains the same， it's the sample mean。



![](img/22f1989e38beea36e4732494bcbf90fe_4.png)

Minus the hypothesize mean where remember we're testing H mu equal to 30。



![](img/22f1989e38beea36e4732494bcbf90fe_6.png)

Versus H mu greater than 30。

![](img/22f1989e38beea36e4732494bcbf90fe_8.png)

And then divided by the standard error of the mean where now we have square root 16 rather than square root 100 and recall s was 10。



![](img/22f1989e38beea36e4732494bcbf90fe_10.png)

![](img/22f1989e38beea36e4732494bcbf90fe_11.png)

This test statistic， how many estimated standard errors from the hypothesized mean the sample means follows a t distribution with 15 degrees of freedom in the specific case。



![](img/22f1989e38beea36e4732494bcbf90fe_13.png)

![](img/22f1989e38beea36e4732494bcbf90fe_14.png)

So under the null hypothesis， the probability that is larger than the 95th percentile of the distribution is 5%。

 so we need to calculate that fifth percentile of the T distribution， this can be done with QT。

95 and 15 degrees of freedom which works out to be 1。7531。



![](img/22f1989e38beea36e4732494bcbf90fe_16.png)

![](img/22f1989e38beea36e4732494bcbf90fe_17.png)

![](img/22f1989e38beea36e4732494bcbf90fe_18.png)

![](img/22f1989e38beea36e4732494bcbf90fe_19.png)

Our test statistic， if we actually plug in the 10 and our x bar of 32， works out to be 0。8。



![](img/22f1989e38beea36e4732494bcbf90fe_21.png)

![](img/22f1989e38beea36e4732494bcbf90fe_22.png)

And so we're failing to reject because 0。8 is smaller than 1。75。



![](img/22f1989e38beea36e4732494bcbf90fe_24.png)

Let's also go through a two sided test。Suppose that we wanted to reject the null hypothesis if in fact the mean was too large or too small。

 this doesn't make a lot of sense in our specific scientific setting because we were specifically interested in whether or not this particular population of obese subjects had a respiratory disturbance index larger than 30 are reference value。



![](img/22f1989e38beea36e4732494bcbf90fe_26.png)

![](img/22f1989e38beea36e4732494bcbf90fe_27.png)

![](img/22f1989e38beea36e4732494bcbf90fe_28.png)

![](img/22f1989e38beea36e4732494bcbf90fe_29.png)

![](img/22f1989e38beea36e4732494bcbf90fe_30.png)

However， it's often the case that in scientific settings。

 a two cid test is demanded regardless of whether or not it makes scientific sense。



![](img/22f1989e38beea36e4732494bcbf90fe_32.png)

![](img/22f1989e38beea36e4732494bcbf90fe_33.png)

It's important to understand how to do two sided tests and the fact that there are some instances where you are mandated to do a two sided tests。

 even though it doesn't necessarily make that much sense to consider the other side。



![](img/22f1989e38beea36e4732494bcbf90fe_35.png)

![](img/22f1989e38beea36e4732494bcbf90fe_36.png)

So we want to reject， in this case， if we were to do a two sided test。

 we want to reject whether or not mu is different from 30。



![](img/22f1989e38beea36e4732494bcbf90fe_38.png)

![](img/22f1989e38beea36e4732494bcbf90fe_39.png)

So in other words， we'll reject if our test statistic is either too large or too small。



![](img/22f1989e38beea36e4732494bcbf90fe_41.png)

In this case， because our test statistic is positive， we only need to consider the large side。



![](img/22f1989e38beea36e4732494bcbf90fe_43.png)

![](img/22f1989e38beea36e4732494bcbf90fe_44.png)

What does change， however， is in order to get that 5% in a way that allows our test statistic to be too large or too small。

 we need to split。 The probability is 2。5% in either tail of the distribution be it the T distribution for small sample sizes or the Z distribution for large sample sizes。



![](img/22f1989e38beea36e4732494bcbf90fe_46.png)

![](img/22f1989e38beea36e4732494bcbf90fe_47.png)

![](img/22f1989e38beea36e4732494bcbf90fe_48.png)

![](img/22f1989e38beea36e4732494bcbf90fe_49.png)

So now instead of QT at 0。95， we're going to do QT at 0。975 again with 15 degrees of freedom。

And so we want to reject if our test statistic is larger than this。

so let me draw an example of our t distribution， this will be the 0 Qt。975。

With 15 degrees of freedom， there'll be 2。5% in that tail， and this is the point Q T。

025 with 15 degrees of freedom， and that's 2。5% in that tail。That point right there。

 so we're going to reject if our test statistic is larger than this guy or smaller than。This guy。

However， because the lower quantile is the negative of the positive quantile。

 we can always say that's the same thing as taking the absolute value of our test statistic and rejecting if it is too large。

That point is made right here。So in this case， we failed to reject the one sided test。

And now in this slide we're showing that we fail to reject the two sided test。 however。

 I think youll have probably already noticed that because we've moved further out into the tails of the T distribution with our rejection region。

That if you fail to reject the one sided test， then you will also have failed to reject the two sided test。

Usually we don't calculate the rejection region and perform the hypothesis test in the formal manner in which we've gone through in the slides by hand。

 instead we'll usually pass the data to a function like T dot test and it outputs all the relevant statistics for us for us to understand what's going on with the test。



![](img/22f1989e38beea36e4732494bcbf90fe_51.png)

![](img/22f1989e38beea36e4732494bcbf90fe_52.png)

![](img/22f1989e38beea36e4732494bcbf90fe_53.png)

![](img/22f1989e38beea36e4732494bcbf90fe_54.png)

What's interesting is we already know how to do this because we've used T dot tests in order to perform confidence intervals。

 we just haven't gone through the output to understand what it's doing for a test。



![](img/22f1989e38beea36e4732494bcbf90fe_56.png)

![](img/22f1989e38beea36e4732494bcbf90fe_57.png)

![](img/22f1989e38beea36e4732494bcbf90fe_58.png)

Let's look at in the using R package， the date of father do's son。



![](img/22f1989e38beea36e4732494bcbf90fe_60.png)

And we'd like to test whether the population of。Sunhes。



![](img/22f1989e38beea36e4732494bcbf90fe_62.png)

Was equivalent to the populate population， mean of father's heights。



![](img/22f1989e38beea36e4732494bcbf90fe_64.png)

Now， the observations here were paired。One son's measurement to one father's measurement and so on。

 So it's in this case， we're going to take the difference and we want to test whether the difference in the heights is0 or it's non zero。



![](img/22f1989e38beea36e4732494bcbf90fe_66.png)

![](img/22f1989e38beea36e4732494bcbf90fe_67.png)

![](img/22f1989e38beea36e4732494bcbf90fe_68.png)

You do that with T dot test and you can either pass the difference directly to the function T dot test or you could pass it the two vectors。



![](img/22f1989e38beea36e4732494bcbf90fe_70.png)

![](img/22f1989e38beea36e4732494bcbf90fe_71.png)

And then add the argument paired equals true。

![](img/22f1989e38beea36e4732494bcbf90fe_73.png)

![](img/22f1989e38beea36e4732494bcbf90fe_74.png)

It gives you your T statistic right here， 11。79， it gives you your degrees of freedom right here。

 1077， so we had exactly 1，078 pairs that we took the difference of。



![](img/22f1989e38beea36e4732494bcbf90fe_76.png)

![](img/22f1989e38beea36e4732494bcbf90fe_77.png)

![](img/22f1989e38beea36e4732494bcbf90fe_78.png)

Now 11 is a quite large T statistic。So we reject the no hypothesis in this case。



![](img/22f1989e38beea36e4732494bcbf90fe_80.png)

Also notice that the degrees of freedom are quite large。

 so the distinction between a T test and a Z test in this case is irrelevant。



![](img/22f1989e38beea36e4732494bcbf90fe_82.png)

It very nicely gives us the T confidence interval automatically when we do T dot test。



![](img/22f1989e38beea36e4732494bcbf90fe_84.png)

It's useful almost always to look at the confidence interval in addition to the output of the test。

 simply because the confidence interval bridges this gap between statistical significance and practical significance quite nicely。

 you can see whether the range of values in the confidence interval are of practical significance or not。

 because it's expressed in the units of the data that you're interested in。



![](img/22f1989e38beea36e4732494bcbf90fe_86.png)

![](img/22f1989e38beea36e4732494bcbf90fe_87.png)

![](img/22f1989e38beea36e4732494bcbf90fe_88.png)

![](img/22f1989e38beea36e4732494bcbf90fe_89.png)

![](img/22f1989e38beea36e4732494bcbf90fe_90.png)