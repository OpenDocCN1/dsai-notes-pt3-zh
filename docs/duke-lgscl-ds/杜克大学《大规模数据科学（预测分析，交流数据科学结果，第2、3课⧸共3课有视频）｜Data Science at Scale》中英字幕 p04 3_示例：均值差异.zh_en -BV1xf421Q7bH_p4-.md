# 杜克大学《大规模数据科学（预测分析，交流数据科学结果，第2、3课⧸共3课有视频）｜Data Science at Scale》中英字幕 p04 3_示例：均值差异.zh_en -BV1xf421Q7bH_p4-

![](img/f9c7b1f376b11e3d6fb7df79299e8517_0.png)

Consider a cohort of patients with advanced lung cancer。

 and we wish to test the efficacy of a new chemotherapy procedure。

 so we design an experiment where we split the cohort of patients in half。

 half of the patients are treated with the standard chemotherapy procedure and the other half are treated with the new procedure。

 and we measure their survival time in。

![](img/f9c7b1f376b11e3d6fb7df79299e8517_2.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_3.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_4.png)

Days。And we'll collect data that looks perhaps something like this。

 and this is a data set that's been used in other contexts and you can find it on the web if you look around。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_6.png)

So， you'll have。Survival days for those patients who were subject to the test procedure and survival days for those in green for the were subject to the standard chemotherapy procedure and you can take the mean of each of these sets and so the mean of the blue values in the test procedure was 128。

3 days and the mean of the green values for the standard procedure was 115。

9 days and then you can subtract the green from the blue and you get a difference of 12。

4 days and you think， well maybe the test procedure is indeed successful in that the patients are living longer but a skeptic might say well look you know that might happen just by chance。

 how can you really know that that was due to the difference in the test procedure。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_8.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_9.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_10.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_11.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_12.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_13.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_14.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_15.png)

So you can ask is this number significant， how likely is it that we would have attain this result purely by chance and what I'm going to do is show you the classical approach to making this kind of statistical inference and declaring significance。

 and then I want to show you a different approach that I think is more useful day to day for a data scientist。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_17.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_18.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_19.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_20.png)

So the classical method is to derive what we call the sampling distribution， and in order to do that。

 we need to make some assumptions about the population。

 in particularly that the number of survival days follows a normal distributions。

 there's a Gaussian distribution， is is a bell curve that we're likely all familiar with。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_22.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_23.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_24.png)

And that the variances of the two sets of patients are the same。 sorry。

 so it's you're not going to get a wider spread。

![](img/f9c7b1f376b11e3d6fb7df79299e8517_26.png)

Of survival days。

![](img/f9c7b1f376b11e3d6fb7df79299e8517_28.png)

Due to the new treatment versus the standard treatment。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_30.png)

Or at least that the two sample size of the cohorts are the same。

 which is true in this case if the sample sizes are the same。

 then you can show that the statistics that we'll use are pretty robust with respect to different variances。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_32.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_33.png)

Okay， so then we construct a T statistic that looks like this， it's some derived statistic。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_35.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_36.png)

And some hypothesized value for that statistic， and you compute their difference。

 and you divide that by the estimated standard error of that statistic。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_38.png)

And so in our case， the statistic we're interested in is the difference in the means and the hypothesized value under the null hypothesis。

 this is the skeptics point of view that there is no difference between these it would happen purely by chance is that it's zero。

 the mean is the difference in these two means is  zero。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_40.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_41.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_42.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_43.png)

So the intuition for this denominator here is that you're asking how many standard errors？



![](img/f9c7b1f376b11e3d6fb7df79299e8517_45.png)

Off of the hypothesized value is this result and the reason when you talk in terms of the units of standard error is that allows you to compare very different populations and very different experiments in a common way。

 so you sort of normalize the values if you will。

![](img/f9c7b1f376b11e3d6fb7df79299e8517_47.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_48.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_49.png)

So fine， so we have this null hypothesis where t bar minus S bar equals 0。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_51.png)

And we know that the t bar minus S bar is a random variable derived from the sample so that therefore it has a sampling distribution。

 and so any kind of statistic you derive from a sample。

 you can reason about its sampling distribution。

![](img/f9c7b1f376b11e3d6fb7df79299e8517_53.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_54.png)

All right。And we're going to compute this T statistic that has this form that we talked about。

 and so therefore we need to figure out what this denominator is all about。

 we need to see what is the estimated standard error of t bar minus S bar。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_56.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_57.png)

Well， the term standard error is just another name for the standard deviation of the sampling distribution of T bar minus S bar。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_59.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_60.png)

Okay， so I think one of the problems and statistics that I at least find is that the English doesn't always map very well to the concepts and so you end up with a lot of sensibly synonymous terms being used to describe subtly different things and it makes a little more confusing to me at least than it needs to be。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_62.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_63.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_64.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_65.png)

So and this is perhaps one of those examples where the standard error is just another name for the standard deviation of the sampling distribution and you use the term sampling distribution when you're talking about a derived statistic from some sample okay so that means we need to figure out what is the sampling distribution of t bar minus S bar。



![](img/f9c7b1f376b11e3d6fb7df79299e8517_67.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_68.png)

![](img/f9c7b1f376b11e3d6fb7df79299e8517_69.png)