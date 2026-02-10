# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P16：15_回归中的推断.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

![](img/460c13fb4424491050f6a048994e992c_0.png)

Hi and welcome to the lecture on Infer and regression。Before we begin talking about inference。

 let's just revisit our model so that it's fresh in our mind。



![](img/460c13fb4424491050f6a048994e992c_2.png)

![](img/460c13fb4424491050f6a048994e992c_3.png)

Our motto was that the response Y I is the intercept beta n plus the slope。

 beta 1 times the predictor x1 plus an error term。 The error term epsilon I is what we're labeling it。

 we're going to assume is normally distributed mean 0 with a variant sigma squared。



![](img/460c13fb4424491050f6a048994e992c_5.png)

![](img/460c13fb4424491050f6a048994e992c_6.png)

![](img/460c13fb4424491050f6a048994e992c_7.png)

![](img/460c13fb4424491050f6a048994e992c_8.png)

For the time being， we're going to assume that the true model is known and this will be the basis for most of this class。



![](img/460c13fb4424491050f6a048994e992c_10.png)

I'm going to assume that you've seen some amount of statistical inference previously。

 so you know what a confidence interval is and what a hypothesis test is。



![](img/460c13fb4424491050f6a048994e992c_12.png)

![](img/460c13fb4424491050f6a048994e992c_13.png)

Let's also remind ourselves that the intercept is estimated at y bar minus beta 1 hat x bar。



![](img/460c13fb4424491050f6a048994e992c_15.png)

And our beta 1 hat is the correlation between the predictor and the response multiplied times the standard deviation of the response over the standard deviation of the predictor。



![](img/460c13fb4424491050f6a048994e992c_17.png)

![](img/460c13fb4424491050f6a048994e992c_18.png)

So let's talk about how we can perform statistical hypothesis tests about our parameters Let's review a couple of concepts from statistical inference。



![](img/460c13fb4424491050f6a048994e992c_20.png)

First， statistics of the form theta hat， minus theta divided by the standard error often have the following properties。

 First of all， they're often normally distributed。And for finite samples。

 if we replace the variance with the estimated variance， they often have a T distribution。

And we'll see this is true in regression context under the assumptions we've made。

This statistic can be used to create hypothesis test of theta being a particular null value versus one of the logical alternatives of it being less than or greater than or not equal to this null value。

 or we can create confidence intervals of the form estimate plus or minus a relevant quantile times the standard error where Q is the relevant quantile and we always take the one over the1 minus alpha over2 quantile。

 for example， if our alpha is 5%， so we want a 95% confidence interval， we take the 97。5 quantile。

And this this is either going to come from a normal distribution or a T distribution。

 so hopefully none of these。Facts are news to you after having had the statistical inference class。

In the regression case， with IID sampling assumptions for our normally distributed errors。

Infer will follow along these lines very similarly to what you saw in that class。

And we're not going to cover at all asymptotics for regression analysis， but suffice it to say it's。

Not mandatory for the errors to be Gaussian for our statistical inferences and regression to hold。

 you can appeal to large sample theory， though it's a little bit more complicated。

So the variance of our regression slope is actually a highly informative formula。

This is variants of beta1 hat and it involves two things。



![](img/460c13fb4424491050f6a048994e992c_22.png)

How variable the points are around the true regression line， Sigma squared。



![](img/460c13fb4424491050f6a048994e992c_24.png)

And how variable my x's are。

![](img/460c13fb4424491050f6a048994e992c_26.png)

Now I think the numerator， how variable the points are around the regression line。

 I think it's somewhat understandable as to why that would that we would get better estimates of our regression slope if that were smaller。



![](img/460c13fb4424491050f6a048994e992c_28.png)

![](img/460c13fb4424491050f6a048994e992c_29.png)

![](img/460c13fb4424491050f6a048994e992c_30.png)

However， it's maybe less intuitive to understand why we want more variants in our predictor。



![](img/460c13fb4424491050f6a048994e992c_32.png)

In order to get lower variances in our regression slope， but let's draw some pictures。



![](img/460c13fb4424491050f6a048994e992c_34.png)

If ourors or predictors are all packed in very tightly closely together。



![](img/460c13fb4424491050f6a048994e992c_36.png)

Then it's clear we're not going to estimate a very good line。

 it could sort of bend around that cloud of points very easily and get equivalent fits。



![](img/460c13fb4424491050f6a048994e992c_38.png)

![](img/460c13fb4424491050f6a048994e992c_39.png)

On the other hand， if we spread our x's out， then we'll get a better fitted regression line。

 we'll get a lower variance for the slope。

![](img/460c13fb4424491050f6a048994e992c_41.png)

Now it turns out the lowest you can make that variance is to push half the observations to one end and the other half of the observations to another end。

 however you're banking quite a bit then on having a line in between those two because you haven't collected any data to evaluate that property。



![](img/460c13fb4424491050f6a048994e992c_43.png)

![](img/460c13fb4424491050f6a048994e992c_44.png)

![](img/460c13fb4424491050f6a048994e992c_45.png)

![](img/460c13fb4424491050f6a048994e992c_46.png)

Here I also give you the variance of the intercept。

 it's maybe a little less informative because intercepts are often a little less of interest than the slopes。



![](img/460c13fb4424491050f6a048994e992c_48.png)

But nonetheless， it has this form right here that we can calculate and write down。



![](img/460c13fb4424491050f6a048994e992c_50.png)

![](img/460c13fb4424491050f6a048994e992c_51.png)

In both these cases， we replace Sigma squared by its logical estimate。

 the one over n minus2 times the sum of the squared residuals we covered that in the last lecture。



![](img/460c13fb4424491050f6a048994e992c_53.png)

It's probably not surprising that our slope or intercept estimate。

 minus the true value divided by their standard error， follows a T distribution。

 and it has n minus two degrees of freedom。

![](img/460c13fb4424491050f6a048994e992c_55.png)

And so this can be used to create confidence intervalables and hypothesis tests。

 and we'll go through some examples here in a couple of slides。

 but first I'm just going to show you that all of these results exactly hold and it's what R is reporting。



![](img/460c13fb4424491050f6a048994e992c_57.png)

![](img/460c13fb4424491050f6a048994e992c_58.png)