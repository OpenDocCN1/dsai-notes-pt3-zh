# 杜克大学《大规模数据科学（预测分析，交流数据科学结果，第2、3课⧸共3课有视频）｜Data Science at Scale》中英字幕 p05 4_推导抽样分布.zh_en -BV1xf421Q7bH_p5-

Well， it can be described by its meaning and its variance。

 and this is true for at least a couple of reasons。

 one is that we did make an assumption that the underlying population is normal and so we could guess that the derived。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_1.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_2.png)

Distribution of T bar minus Spar is normal as well。

 We could also argue by the central limit theorem that no matter what the distribution is。

 as long as we even know samples， it will tend to be described accurately by normal distribution。

 which has these two parameters， mean and mean invari。 So what is the mean of the。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_4.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_5.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_6.png)

Statistic that we're interested in。 well， it's the。

Mean of the T sample minus the mean of the S sample。

 So just and you could really write this just T bar minus S bar。 That one's pretty straightforward。

 The variance of T bar minus S bar。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_8.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_9.png)

Is the variance of our mean T bar plus the variance of our mean S bar。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_11.png)

Emphasizing that that it's the variance of the mean of T， not the variance of the sample itself of T。

 so this is， you know if you repeat the experiment over and over and over again。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_13.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_14.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_15.png)

What you'll。Let's say 10，000 times， so you'll end up with this 10，000 means。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_17.png)

For the patients who were subject to the new treatment。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_19.png)

And the variance of those estimates。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_21.png)

Is what this refers to so it's not the variance of the population or nor is it the variance of the sample itself。

 It's the variance of that values of the mean over many， many experiments。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_23.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_24.png)

So why is the？Variance of the difference of means bar T minus bar S equal to the variance of bar T plus the variance of。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_26.png)

嗯。Bars。Well it's。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_28.png)

Drive from the definition of variance， but it's somewhat intuitive if you think about it。

 There's two populations。 There's two samples that we're taking。

 and the increase in variance of the mes， the more they， know。

 the wider the interval in which we have， the difference between those things is also going to get wider。

 right we could get the maximum number of green jelly beans and the minimum number of red jelly beans。

 And so the difference in memes could get bigger and bigger and bigger， the more they vary。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_30.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_31.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_32.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_33.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_34.png)

Okay， so whether we're adding the variable together， whether we're subing this。

 you always add the variances and also point out that this is another place where we've had to assume that these are independent samples as we did assume。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_36.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_37.png)

Okay， so where are we， Well we're looking for the sampling distribution of bar t minus bar S。

 and we know it's described by its mean invari by the central limit theorem and due to an assumption of normality for the underlying population。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_39.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_40.png)

And we've reexed the。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_42.png)

Variance of this statistic that we're interested in in terms of this sum。

 but we can't compute this value directly。 We don't know the variance of。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_44.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_45.png)

The memes repeated over many experiments。 We don't have access to those many experiments to in which to compute this value。

 So we have to estimate it somehow。 Well， by the central limit theorem。

 we can rewrite this in terms of the population variance。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_47.png)

Divided by the sample size。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_49.png)

And I'll refer to the central limit theorem to see that。

 and then we can estimate the sample excuse me， the population variance by the sample variance。

 which I'venoted by this sigma。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_51.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_52.png)

Sigma hat。 And so we can do that for both values。 And now we have this reexpress in terms that we actually have access to。

 We can compute the sample variance。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_54.png)

For S and we know the size of the sample， and we compute the sample variance for T and we know the size of that sample。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_56.png)

Okay， so。We need a sampling distribution of the difference and means。

 We have the the mean the variance。 We reexed it in terms of quantities that we actually have access to。

 I guess I shouldn't have the bar there anymore。 It should be just。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_58.png)

Ha。TNS。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_60.png)

So back to our original question， what is the estimated standard error。 Remember。

 that was the denominator of this T statistic that we need in order to see。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_62.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_63.png)

How significant this difference is。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_65.png)

Right， remember we're counting sort of in terms of the number of standard errors away from normal。

 So remember the estimated standard error is the same thing as the estimated standard deviation of this statemently distribution that we've now described in terms of mean and variance。

 And so we just take the square root。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_67.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_68.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_69.png)

Of this side and the standard deviation of bar t minus bar s is a square root of。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_71.png)

Of this thing。 All right， So we're getting closer almost there。 Now， the T test is。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_73.png)

The statistic we're interested in bar T minus bar as。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_75.png)

Minus the hypothesized value， which in this case is just zero。

 so we drop it divided by the standard error which we just arrived。

 And if you remember the means when a few slides back。

 we can now can also compute this value and we get this T value。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_77.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_78.png)

If you've done this kind of process before， you might see this as a fairly low number of standard errors away from this is a fairly low critical value。

 which means it's probably not。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_80.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_81.png)

Streakly significant， but we can't judge that right away。 We have to go look it up。

 We also need the notion of degrees of freedom。 and I'm not going to。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_83.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_84.png)

Walk through that process， but I'll。Show the formula for this the is to our an estimate for the due number of degrees in freedom for this。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_86.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_87.png)

T distribution and the t distribution， if you're not familiar with it。

 it basically looks exactly like the Gaussium， but it's got sort of heavier tails。

 but the crucial thing is that it depends on the sample size。

 So it becomes more and more closer and closer to the normal distribution as the sample size increases and it was designed to be sensitive to issues of sample size。

 So if we compute the degrees of region using this monstrosity and we have our critical value。

 We then you know can choose a significance level that we're interested in use one of these handy。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_89.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_90.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_91.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_92.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_93.png)

Tables in the back of a statistics textbook or， of course， now online。

 and the degrees of freedom is actually pretty high in this case。

So we're way down here and we look at this value of 2。

660 and we compare that to our T statistics and we find that 2。660 is greater。

 so we do not have evidence to reject the nullpo at significance level 0。05。

 this result could have been by chance。

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_95.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_96.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_97.png)

And the difference between the two treatments does not seem to be significant。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_99.png)

My opinion of that process is that it's。Pretty painful and I want to show you a different way that is just as rigorous。

 but can be done in 10 lines of code as anyone that has a little bit of programming experience。



![](img/3b7ae4897ef734d3b6bb6e48f8834a53_101.png)

![](img/3b7ae4897ef734d3b6bb6e48f8834a53_102.png)