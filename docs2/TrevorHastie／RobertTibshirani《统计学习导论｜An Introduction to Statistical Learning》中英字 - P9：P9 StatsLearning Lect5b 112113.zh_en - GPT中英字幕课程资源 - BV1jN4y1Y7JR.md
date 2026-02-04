# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P9：P9 StatsLearning Lect5b 112113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/c79f2a20989630290bcb63c318f08444_0.png)

Welcome back。We just finished talking about confidence intervals in the previous segment。

 and now we'll talk about hypothesis testing， which is a closer related idea。



![](img/c79f2a20989630290bcb63c318f08444_2.png)

![](img/c79f2a20989630290bcb63c318f08444_3.png)

We want to ask a question about a specific value of a parameter like， is that coefficient zero？



![](img/c79f2a20989630290bcb63c318f08444_5.png)

And the statistics as known is hypothesis testing， so hypothesis testing。



![](img/c79f2a20989630290bcb63c318f08444_7.png)

Is a test of a。Of a relationship between， it's a test of a certain value of a parameter。



![](img/c79f2a20989630290bcb63c318f08444_9.png)

In particular， here， the hypothesis test we'll make is that is that parameter zero， is a slope zero？



![](img/c79f2a20989630290bcb63c318f08444_11.png)

So what's called the null hypothesis is that there's no relationship between x and Y。



![](img/c79f2a20989630290bcb63c318f08444_13.png)

In words in other words， beta 1。Equs zero， right？

![](img/c79f2a20989630290bcb63c318f08444_15.png)

That's this equivalent statement， the alternative hypothesis is that relationship there is some relationship between x and y in other words。

 beta 1 is not zero。

![](img/c79f2a20989630290bcb63c318f08444_17.png)

And beta 1 could be。Positive or negative。Okay。So mathematically， this corresponds to。

Beta 1 being0 is the nupa is beta 19 equals 0。Good。



![](img/c79f2a20989630290bcb63c318f08444_19.png)

So that's often the question you want to ask， that's here the first question you want to ask about the predictors。



![](img/c79f2a20989630290bcb63c318f08444_21.png)

So to testest an hypothesis。We。Forth called a T statistic。

 we take the estimated slope divided by a standard error。



![](img/c79f2a20989630290bcb63c318f08444_23.png)

![](img/c79f2a20989630290bcb63c318f08444_24.png)

This will approximately have a t distribution with M minus-2 degrees of freedom under assuming that the hypothesis is true。



![](img/c79f2a20989630290bcb63c318f08444_26.png)

Now what is a T distribution， you don't have to worry too much about that。

 it's basically you look this up in a table or nowadays you look in software or compute it for you。

 it's basically a normal random variable except for small numbers of samples and it's a little bit different。



![](img/c79f2a20989630290bcb63c318f08444_28.png)

![](img/c79f2a20989630290bcb63c318f08444_29.png)

![](img/c79f2a20989630290bcb63c318f08444_30.png)

In any case， you ask the computer to compute。

![](img/c79f2a20989630290bcb63c318f08444_32.png)

The P value based on this statistic。

![](img/c79f2a20989630290bcb63c318f08444_34.png)

嗯。P value is the probability of getting the value of T。



![](img/c79f2a20989630290bcb63c318f08444_36.png)

At least as large as you got。In absolute value。Okay。



![](img/c79f2a20989630290bcb63c318f08444_38.png)

So for the advertising data using again just TV。

![](img/c79f2a20989630290bcb63c318f08444_40.png)

Here are the results， here the slope and intercept of that line， we saw the least squares line。

 standard errors。

![](img/c79f2a20989630290bcb63c318f08444_42.png)

Here are the T statistics， that's just the coefficient divided by the standard error。



![](img/c79f2a20989630290bcb63c318f08444_44.png)

The one we care most about is for TV， the intercept isn't really very interesting。

 that's telling us what happens。

![](img/c79f2a20989630290bcb63c318f08444_46.png)

What's the sales when the TV is zero， TV's budget is zero？



![](img/c79f2a20989630290bcb63c318f08444_48.png)

But the one I care most about here is this guy。 So this， this is， this is measuring the effect of。



![](img/c79f2a20989630290bcb63c318f08444_50.png)

TV advertising on sales。 And the T statistic is huge。 Okay， It's much。 turns out the in order to be。



![](img/c79f2a20989630290bcb63c318f08444_52.png)

![](img/c79f2a20989630290bcb63c318f08444_53.png)

To have a。P value of below 0。05， which is quite significant。



![](img/c79f2a20989630290bcb63c318f08444_55.png)

You need a T statistic of about2。 We're at 17。 So it's very， very significant。

 So the P value was very， very small。

![](img/c79f2a20989630290bcb63c318f08444_57.png)

So how do we interpret this， it says the chance of seeing this data。



![](img/c79f2a20989630290bcb63c318f08444_59.png)

Under the assumption that of the null hypothesis， that there's no effect of TV advertising on sales。



![](img/c79f2a20989630290bcb63c318f08444_61.png)

![](img/c79f2a20989630290bcb63c318f08444_62.png)

Is less than 10 to the -4。 So it's very unlikely to have seen this data。 It's possible。

 but very unlikely。

![](img/c79f2a20989630290bcb63c318f08444_64.png)

Under the assumption that TV advertising has no effect。



![](img/c79f2a20989630290bcb63c318f08444_66.png)

Our conclusion therefore， is that TV advertising has an effect。On sales， as we。



![](img/c79f2a20989630290bcb63c318f08444_68.png)

We hope。Okay， so we've seen how to fit a model with a single predictor。



![](img/c79f2a20989630290bcb63c318f08444_70.png)

And how to assess the slope of that predictor， both in terms of confidence intervals。



![](img/c79f2a20989630290bcb63c318f08444_72.png)

And I paused this test。 I did want to add one thing。



![](img/c79f2a20989630290bcb63c318f08444_74.png)

That's important， so we've seen the hypothesis test and before that we saw confidence intervals。



![](img/c79f2a20989630290bcb63c318f08444_76.png)

There's actually a one to one correspondence， in other words， they're doing equivalent things。



![](img/c79f2a20989630290bcb63c318f08444_78.png)

To be more precise， if the hypothesis test fails， if we reject the nu hypothesis and conclude that beta 1 is not zero。

 as we did for TV advertising。

![](img/c79f2a20989630290bcb63c318f08444_80.png)

![](img/c79f2a20989630290bcb63c318f08444_81.png)

Corspondingly， the confidence interval constructed for that data for the parameter will not contain 0。



![](img/c79f2a20989630290bcb63c318f08444_83.png)

Andversely， if their a process test does not reject。



![](img/c79f2a20989630290bcb63c318f08444_85.png)

So we cannot conclude that TV advertising has an effect， its slope may be zero。

 the confidence interval for that parameter will contain zero。

 so really the confidence interval is also doing hypothesis testing for you。



![](img/c79f2a20989630290bcb63c318f08444_87.png)

![](img/c79f2a20989630290bcb63c318f08444_88.png)

That it's also telling you how big the effect is。

![](img/c79f2a20989630290bcb63c318f08444_90.png)

So it's always good to compute confidence intervals as well as do hypothesis tests。



![](img/c79f2a20989630290bcb63c318f08444_92.png)

So for example， here we see。The interval doesn't contain zero。



![](img/c79f2a20989630290bcb63c318f08444_94.png)

Furthermore， we see that a lower limit on the effective。



![](img/c79f2a20989630290bcb63c318f08444_96.png)

TV advertising is 0。042。Which we can interpret is， these are 1。

000 units that we're going to affect sales by 1000 times。



![](img/c79f2a20989630290bcb63c318f08444_98.png)

Oh， so for every 1000 change in。

![](img/c79f2a20989630290bcb63c318f08444_100.png)

TV advertising we'll get a corresponding change in sales。

 So this tells us not only is the effect zero or not， but how big is the effect likely to be。



![](img/c79f2a20989630290bcb63c318f08444_102.png)

![](img/c79f2a20989630290bcb63c318f08444_103.png)

Okay。

![](img/c79f2a20989630290bcb63c318f08444_105.png)

So where are we now， let's see？So we talked about how to assess the slope of an individual predictor。



![](img/c79f2a20989630290bcb63c318f08444_107.png)

How about the， the overall fit of the model， the accuracy of the model？ Well。

 what we can do here is we'll take the。

![](img/c79f2a20989630290bcb63c318f08444_109.png)

There is id summa squares。 remember this is the quantity that we minimize in the first place to get the best estimates of the intercepted slope。

 the least squares estimates。

![](img/c79f2a20989630290bcb63c318f08444_111.png)

![](img/c79f2a20989630290bcb63c318f08444_112.png)

So we'll take what's called the mean squared residual and take the square root。

 this is the average squared deviation that we achieve using the best the least fitting line。



![](img/c79f2a20989630290bcb63c318f08444_114.png)

![](img/c79f2a20989630290bcb63c318f08444_115.png)

Where this is the residual sum of squares。

![](img/c79f2a20989630290bcb63c318f08444_117.png)

And。We compute what's called the R squared or the fraction of variance explained， and here it is。



![](img/c79f2a20989630290bcb63c318f08444_119.png)

It's the total sum squares。mininus the residual sum of squares or the total sum of squares。

 So what is this conceptually， well， if we didn't fit a model at all。

 if we forget about TV advertising， just use the mean of sales as the prediction。

 that's sort of the simplest prediction you can imagine。



![](img/c79f2a20989630290bcb63c318f08444_121.png)

![](img/c79f2a20989630290bcb63c318f08444_122.png)

![](img/c79f2a20989630290bcb63c318f08444_123.png)

This would be our。

![](img/c79f2a20989630290bcb63c318f08444_125.png)

Our error， right， This is， here's our prediction。 Here's the true sales。

 So this is the no model error。

![](img/c79f2a20989630290bcb63c318f08444_127.png)

And now the residualid summa squares of the fitted model is RSS。



![](img/c79f2a20989630290bcb63c318f08444_129.png)

This is how much is going to be lower than this guy right。

 It's going to be lower because we could always achieve this guy just by choosing a slope of0。

 So since we've done these squares， we've optimized over the parameters。

 we know that RSS will be less than TSS， but this quantity measures。

 how much do we reduce the total sum of squares relative to itself。



![](img/c79f2a20989630290bcb63c318f08444_131.png)

![](img/c79f2a20989630290bcb63c318f08444_132.png)

![](img/c79f2a20989630290bcb63c318f08444_133.png)

![](img/c79f2a20989630290bcb63c318f08444_134.png)

And here it can be written in this way or this way。 so this is the fraction of variances explained。



![](img/c79f2a20989630290bcb63c318f08444_136.png)

![](img/c79f2a20989630290bcb63c318f08444_137.png)

And。It can be shown algebraic because this is actually equivalent。



![](img/c79f2a20989630290bcb63c318f08444_139.png)

To the squared correlation between x and Y。 So this is simple correlation between the predictor and the outcome。



![](img/c79f2a20989630290bcb63c318f08444_141.png)

Kind of makes sense， right， the higher the correlation。



![](img/c79f2a20989630290bcb63c318f08444_143.png)

The more that we will explain the variance， and there's actually an exact algebraic relationship that the squared correlation is equal to this fraction of variance explained。



![](img/c79f2a20989630290bcb63c318f08444_145.png)

![](img/c79f2a20989630290bcb63c318f08444_146.png)

![](img/c79f2a20989630290bcb63c318f08444_147.png)

So what do we get for our data？The r squared is 0。61。



![](img/c79f2a20989630290bcb63c318f08444_149.png)

Here it is in other words。We've using TV sales。

![](img/c79f2a20989630290bcb63c318f08444_151.png)

We've the， the budget， excuse me， TV budget。 we reduce the variance。In at in sales。By 61%。



![](img/c79f2a20989630290bcb63c318f08444_153.png)

So that's a very strong predictor。The F statistic we'll talk about in a few minutes。

 it's also a measure of。

![](img/c79f2a20989630290bcb63c318f08444_155.png)

How well the overall model is doing。

![](img/c79f2a20989630290bcb63c318f08444_157.png)

So。This is quite impressive， in business and some kind of physical sciences。

 we see R squares like this in medicine。

![](img/c79f2a20989630290bcb63c318f08444_159.png)

We don't tend to see R squares， you might see r squared of 5%， you might get excited。



![](img/c79f2a20989630290bcb63c318f08444_161.png)

So always one has to remember the domain to have a judge of how good an R squared it is。

 but this is an impressive R squared which you see sometimes in business and finance applications。



![](img/c79f2a20989630290bcb63c318f08444_163.png)

![](img/c79f2a20989630290bcb63c318f08444_164.png)

![](img/c79f2a20989630290bcb63c318f08444_165.png)

So that completes our discussion of regression with a single predictor。

 in the next section we'll move on to the harder problem where we have multiple predictors and we do a multiple regression。



![](img/c79f2a20989630290bcb63c318f08444_167.png)