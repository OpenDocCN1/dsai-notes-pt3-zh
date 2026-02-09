# 约翰霍普金斯大学数据科学课程6：《统计推断课程（约翰霍普金斯大学）》｜statistical-inference｜ - P39：38_13 03 关于自举的笔记.zh_en - GPT中英字幕课程资源 - BV1oG41197es

![](img/0a37e72411670233119c62225af1c1fa_0.png)

So the Botrap principle is if you have a statistic that estimates some population parameter that you're interested in。



![](img/0a37e72411670233119c62225af1c1fa_2.png)

But you don't know that statistics sampling distribution。



![](img/0a37e72411670233119c62225af1c1fa_4.png)

Then the bootstrap principle is simply to use the distribution。Defined by the observed data。



![](img/0a37e72411670233119c62225af1c1fa_6.png)

To investigate that sampling distribution， an estimate of that sampling distribution。



![](img/0a37e72411670233119c62225af1c1fa_8.png)

The bootstrap principle actually doesn't require simulation in the same way that if we want to know what's the distribution of the average of 50 die rolls。



![](img/0a37e72411670233119c62225af1c1fa_10.png)

![](img/0a37e72411670233119c62225af1c1fa_11.png)

Well， we could maybe mathematically figure that out， good luck。

 but it's easier to do that with simulation， so we never kind of figure out what's the limit of what you get。



![](img/0a37e72411670233119c62225af1c1fa_13.png)

When you roll the dye infinitely many times because we can approximate that so well with Monte Carlo。



![](img/0a37e72411670233119c62225af1c1fa_15.png)

![](img/0a37e72411670233119c62225af1c1fa_16.png)

We're also only going to cover a couple of aspects of。What you can do with your bootstrap resamp。

 it's a rich subject and we're mostly going to cover creating a conference interval and estimating standard error。

 so we'll go over those two things。

![](img/0a37e72411670233119c62225af1c1fa_18.png)

But let's go over the general procedure again， what you do is you take your observed data and you simulate complete data sets by drawing from the observed data with replacement。



![](img/0a37e72411670233119c62225af1c1fa_20.png)

And this is approximately drawing and for each of the simulated data sets you calculate the statistic of interest。

 and this is approximately drawing from the sampling distribution of that statistic。

 at least as far as the data approximates the real population distribution。



![](img/0a37e72411670233119c62225af1c1fa_22.png)

![](img/0a37e72411670233119c62225af1c1fa_23.png)

![](img/0a37e72411670233119c62225af1c1fa_24.png)

![](img/0a37e72411670233119c62225af1c1fa_25.png)

So just as a reminder， we're going to calculate the statistic for each simulated data set。



![](img/0a37e72411670233119c62225af1c1fa_27.png)

And then we're going to use these simulated statistics to either define a confidence interval or to take the standard deviation of this distribution in order to calculate a standard error。

So let's go through the bootsottrap algorithm in a little bit of detail for calculating a conference interval or bootstrap standard error for the median from a set of N observations。

So the data that we have is a vector of length n。

![](img/0a37e72411670233119c62225af1c1fa_29.png)

Then what we're going to do is resample N observations with replacement from the observed data。



![](img/0a37e72411670233119c62225af1c1fa_31.png)

To basically get a resampled complete data set。Remember。When you sample from the observed data。

 you're going to sample with replacement。

![](img/0a37e72411670233119c62225af1c1fa_33.png)

If you didn't do it with replacement， then you would basically。

 after having simulated sampled N of them， you would just have a copy of the data set again just with the order permed。



![](img/0a37e72411670233119c62225af1c1fa_35.png)

Instead it's important to sample with replacement， which means that you likely get some observations repeated。

On multiple times， which is fine， this is part of bootstrap re samplingling。



![](img/0a37e72411670233119c62225af1c1fa_37.png)

When you get a resampled data set。

![](img/0a37e72411670233119c62225af1c1fa_39.png)

In our example， we're going to take the median， or if you're using a different statistic。

 you'll simply take that statistic of the simulated data。



![](img/0a37e72411670233119c62225af1c1fa_41.png)

Then you're going to repeat this step over and over。

 I say B times here where B is the number of bootstrap re samplesles。



![](img/0a37e72411670233119c62225af1c1fa_43.png)

You want B to be large so that your Monte Carlo error is small。



![](img/0a37e72411670233119c62225af1c1fa_45.png)

And what I mean by that is remember， if we could， we would just figure out the exact bootstrap distribution without involving any resampling。



![](img/0a37e72411670233119c62225af1c1fa_47.png)

![](img/0a37e72411670233119c62225af1c1fa_48.png)

We would just know exactly what the distribution of the median is from a distribution that places probability 1 over n on each observed data point。



![](img/0a37e72411670233119c62225af1c1fa_50.png)

![](img/0a37e72411670233119c62225af1c1fa_51.png)

Instead we're going to do it via Monte Carlo this process of resampling so you don't want the Monte Carlo error or basically how long you've run your computer to be driving your results。



![](img/0a37e72411670233119c62225af1c1fa_53.png)

The easiest way to fix this is to simply make be fairly large， 10，000 or more simulations。

The medians that you get from this process are approximately drawn from the sampling distribution of the median of N observations。



![](img/0a37e72411670233119c62225af1c1fa_55.png)

We're really sort of。Approxximating the population distribution， but that's okay。

 there's a lot of theory that shows that the bootstrap actually works。



![](img/0a37e72411670233119c62225af1c1fa_57.png)

![](img/0a37e72411670233119c62225af1c1fa_58.png)

When we do this。

![](img/0a37e72411670233119c62225af1c1fa_60.png)

What we can do with our bootstrap reamples is the first thing is you'll always want to draw a density estimate or a histogram of them。



![](img/0a37e72411670233119c62225af1c1fa_62.png)

But you also could calculate their standard deviation。

 which will give you a standard error of the median an estimated standard error of the median。



![](img/0a37e72411670233119c62225af1c1fa_64.png)

![](img/0a37e72411670233119c62225af1c1fa_65.png)

You could take quantiles of your bootstrap resampled medians and say for example， the 2。5th and 97。

5th quantile and those form a so-called bootstrap confidence interval for the median so notice what we've done in this process is we've figured out a very easy way to develop a confidence interval for the median without having to do anything like fancy asymptotics。



![](img/0a37e72411670233119c62225af1c1fa_67.png)

![](img/0a37e72411670233119c62225af1c1fa_68.png)

![](img/0a37e72411670233119c62225af1c1fa_69.png)

Let's go through some quick example code。Remember the father son data。



![](img/0a37e72411670233119c62225af1c1fa_71.png)

Where our X is our sun's heights， remember we assign this。Vectctor X to be the sun's heights。



![](img/0a37e72411670233119c62225af1c1fa_73.png)

I'm going to define B to be 10，000， that's going to be my number of bootstrap resamples。

 and I have already previously defined n as the length of x， the number of observations that I have。



![](img/0a37e72411670233119c62225af1c1fa_75.png)

![](img/0a37e72411670233119c62225af1c1fa_76.png)

So if I want to draw n complete datas with replacement， B complete data sets with replacement from X。

 then I need n times B draws， the R command sample does this where it's X。



![](img/0a37e72411670233119c62225af1c1fa_78.png)

![](img/0a37e72411670233119c62225af1c1fa_79.png)

As the vector that I'm sampling from n times B， the number of times that I want to draw from it and replace equals true。

In this case， if I didn't have replaceplace equalicle true， give me an error because you can't draw。

N times B elements from x， which only has n elements without replacement。



![](img/0a37e72411670233119c62225af1c1fa_81.png)

![](img/0a37e72411670233119c62225af1c1fa_82.png)

This now gives me a vector of n times b samples from x。

 and now I'm going to simply arrange them into a matrix with B rows。



![](img/0a37e72411670233119c62225af1c1fa_84.png)

![](img/0a37e72411670233119c62225af1c1fa_85.png)

And N columns。So every row now。Is a bootstrap resample。And it has n observations。



![](img/0a37e72411670233119c62225af1c1fa_87.png)

So I'm going to go along the rows in the next line and。



![](img/0a37e72411670233119c62225af1c1fa_89.png)

Take the median for each row。When I take my standard deviation of my medians， I get 0。08473。



![](img/0a37e72411670233119c62225af1c1fa_91.png)

![](img/0a37e72411670233119c62225af1c1fa_92.png)

This is an estimated standard error of the median。

![](img/0a37e72411670233119c62225af1c1fa_94.png)

If we want a confidence interval for the median， I'm going to take my vector of resampled medians and I'm going to simply take the quantiles。



![](img/0a37e72411670233119c62225af1c1fa_96.png)

And I want a 95% interval， so I'm going to take the 2。5th and 97。5 quantiles。



![](img/0a37e72411670233119c62225af1c1fa_98.png)

![](img/0a37e72411670233119c62225af1c1fa_99.png)

Gives a fairly tight confidence interval in this case because there's lots and lots of observed data。



![](img/0a37e72411670233119c62225af1c1fa_101.png)

Here's my histogram of bootstraperyamples， and this is just always a good thing to do。

 I did it with G G plot。 and so here you see me assigning G the。



![](img/0a37e72411670233119c62225af1c1fa_103.png)

![](img/0a37e72411670233119c62225af1c1fa_104.png)

Output of the G plot function G plot works on data frame。

 so I define a data frame as my collection of medians。



![](img/0a37e72411670233119c62225af1c1fa_106.png)

![](img/0a37e72411670233119c62225af1c1fa_107.png)

And then my aesthetic， my x variable is the medians， then I'm going to add to my plot。

 I'm going to add a layer that is a histogram。

![](img/0a37e72411670233119c62225af1c1fa_109.png)

![](img/0a37e72411670233119c62225af1c1fa_110.png)

The black means the bars， the outside of the bars are black。

 fill being light blue means the inside of the bars I wanted to be light blue and B with talks about the width of the bins to create my histogram。



![](img/0a37e72411670233119c62225af1c1fa_112.png)

![](img/0a37e72411670233119c62225af1c1fa_113.png)

Then I type G to actually show the plot。

![](img/0a37e72411670233119c62225af1c1fa_115.png)

So this plot is an estimate。Of the sampling distribution of the median。If we had the true。

Population distribution。And we were to sample over and over again。

This would be a very good estimate up to Monte Carlo error。

Of the sampling distribution of the median。 Instead， we don't have the exact population distribution。

 We've replaced it with the bootstrap principle of resampling from the observed data。 And now。

 instead， we just get this approximate。Distribution。

Of this approximate sampling distribution of the median。



![](img/0a37e72411670233119c62225af1c1fa_117.png)

So a couple final notes on the bootstrap。

![](img/0a37e72411670233119c62225af1c1fa_119.png)

The way in which we presented the bootstrap here is the so called non parametric bootstrap。



![](img/0a37e72411670233119c62225af1c1fa_121.png)

The confidence interval that I showed you just taking the 2。5th and 97。

5th percentiles is actually a somewhat poorly performing confidence interval and you can improve on it very easily The one I would recommend is called the biasas corrected and accelerated interval BCA interval and it's very easy to implement in the Botrop package。



![](img/0a37e72411670233119c62225af1c1fa_123.png)

![](img/0a37e72411670233119c62225af1c1fa_124.png)

![](img/0a37e72411670233119c62225af1c1fa_125.png)

In R。

![](img/0a37e72411670233119c62225af1c1fa_127.png)

You simply。Take your bootstrapery samplesamp and pass it through this function and it just gives you the BCA interval。

 it's basically a quick little fix of what quantiles you take to correct for a bias。



![](img/0a37e72411670233119c62225af1c1fa_129.png)

![](img/0a37e72411670233119c62225af1c1fa_130.png)

![](img/0a37e72411670233119c62225af1c1fa_131.png)

What I've done here is I've just given you a very basic introduction to the Boottrap。

 It is an incredibly useful procedure， and it has lots of variations in extremely wide applicability and a lot of intricacies when you try to apply it in settings like when you have time series or when you have a regression model or when you have longitudin or multi-level data。



![](img/0a37e72411670233119c62225af1c1fa_133.png)

![](img/0a37e72411670233119c62225af1c1fa_134.png)

![](img/0a37e72411670233119c62225af1c1fa_135.png)

![](img/0a37e72411670233119c62225af1c1fa_136.png)

![](img/0a37e72411670233119c62225af1c1fa_137.png)