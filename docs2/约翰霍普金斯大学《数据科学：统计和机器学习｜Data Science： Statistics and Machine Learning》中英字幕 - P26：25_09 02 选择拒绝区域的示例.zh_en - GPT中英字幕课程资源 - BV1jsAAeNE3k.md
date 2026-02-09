# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P26：25_09 02 选择拒绝区域的示例.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

This test。

![](img/54f29139b8e2f88b56eabe58fa187ead_1.png)

Consider our respiratory disturbance index example again。



![](img/54f29139b8e2f88b56eabe58fa187ead_3.png)

A reasonable strategy would be to reject an the hypothesis of our sample mean respiratory disturbance index was larger than some constant。

 Let's label that constant C。C will take into account the variability of X bar。Typically。

 C is chosen so that the probability of type 1 error rate。

 this probability we label alpha is a low number。5% has emerged as sort of a benchmark in hypothesis testing。

So to repeat， alpha is the type 1 error rate， which， in other words。

 is the probability of rejecting the null hypothesis when， in fact， the null hypothesis is correct。

 a bad thing。 We don't want to make these kinds of mistakes。 But as in our court of law example。

 we don't want to set this rate too low。Because then we would never reject the nu hypothesis。

Let's see if we can choose this constant C。So that the probability that we reject is simply tolerably low。

 say 5%。

![](img/54f29139b8e2f88b56eabe58fa187ead_5.png)

The standard error of the mean is 10。 The assumed standard deviation of the population。

 And here we haven't drawn a distinction as to whether we've estimated。

 or this is just a number that I've given you。The divide of by square root 100 us the square root of the sample size that works out to be one here I just created the setting so it conveniently worked out to be one。



![](img/54f29139b8e2f88b56eabe58fa187ead_7.png)

Under the no hypothesis， where under H n mu is equal to 30。

 the distribution of the sample mean X bar is normal with a mean of 30 and a variance of one。

 which we just calculated as the standard error of the square of the standard error of the mean in the line above。

So we want to choose the constant C so that the probability that x bar is larger than C under the nu hypothesispo is 5%。



![](img/54f29139b8e2f88b56eabe58fa187ead_9.png)

So remember the 95th percentile of the standard normal distribution is 1。

645 standard deviations from the mean， so if we set the constant as 1。

645 standard deviations from the mean under the null hypothesis。

We will have achieved a cut point so that the probability that a randomly drawn mean from this population is larger than this。



![](img/54f29139b8e2f88b56eabe58fa187ead_11.png)

He's 5%。

![](img/54f29139b8e2f88b56eabe58fa187ead_13.png)

![](img/54f29139b8e2f88b56eabe58fa187ead_14.png)

So in this case， it's 30， the hypothesissized mean under the nu hypothesis plus1。

 the standard error of the mean times 1。645， the number of standard deviations from the mean that we're considering。

 which in this case works out to be 31。645。So。Just to reiterate。

 the probability that a normal 30 with a mean of 30 in a variance of  one is larger than this constant is 5%。

So the rule， reject the no hypothesispo when you receive an average larger than 31。

645 has the property that we will reject 5% of the time when the no hypothesispo is true again。



![](img/54f29139b8e2f88b56eabe58fa187ead_16.png)

5ive% of time in the instances where the sample size is exactly 100 and the standard deviation of the population is exactly 10。



![](img/54f29139b8e2f88b56eabe58fa187ead_18.png)

In the previous slide， we reverted the calculation of the rejection region C back to the original units of the data。

 However， I hope you got the gist from the problem that basically whenever you were testing greater than。

 if the sample mean is more than 1。645 standard errors from the mean from the hypothesized mean。

 you would reject and there was nothing particular about 30 and the standard error of the mean of 1。

So。Instead of calculating this constant back on units of the original data。

 we tend to convert our sample mean into however many standard errors from the hypothesized mean it is。

 So take this specific example if our observed sample mean was 32。



![](img/54f29139b8e2f88b56eabe58fa187ead_20.png)

Our hypothesized mean is 30。And our standard error is 10 divided by square root 100 where in a real problem。

 the 10 would be estimated from the data， so it would be the sample standard deviation。



![](img/54f29139b8e2f88b56eabe58fa187ead_22.png)

This works out to be 2。 This is greater than 1。645。 The chance of this occurring is less than 5 per。

 So we're going to reject the nu hypothesis。 I should reiterate the chance of this occurring under the nu hypothesis is less than 5%。

 So we're going to reject the nu hypothesis in favor of the alternative hypothesis。

 So I've just simply written out this rule again here on the final line。

 We're going to reject whenever x bar minus the hypothesisthesized mean the byta by the standard error of the mean is greater Then the appropriate upper quantile that leaves alpha per in the upper tail。



![](img/54f29139b8e2f88b56eabe58fa187ead_24.png)