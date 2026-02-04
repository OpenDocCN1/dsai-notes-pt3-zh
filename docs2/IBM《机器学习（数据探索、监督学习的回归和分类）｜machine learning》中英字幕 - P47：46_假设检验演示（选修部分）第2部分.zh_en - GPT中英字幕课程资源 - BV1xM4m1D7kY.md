# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P47：46_假设检验演示（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So， we left off。Trying to find the number of coin flips a person would need to guess correctly。

 for us believe that they can predict better than a 5050 chance whether the next coin flip will be heads or tails。



![](img/9971ad9aa29e3c02756fef2ccc84002f_1.png)

So we saw this CDF and that's going to be the cumulative distribution function and tell us at given a certain number of coin flips。

 what is the area under the curve to give us the probability of that many coin flips or less that's a cumulative distribution function。



![](img/9971ad9aa29e3c02756fef2ccc84002f_3.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_4.png)

So we want to see at what point can we say that it's more extreme in terms of the higher end of getting 95% or less right。

 so if we have 5% left on that right end that saying that that value or greater only has a 5% chance。



![](img/9971ad9aa29e3c02756fef2ccc84002f_6.png)

Whereas that value or less， we'll have a 95% chance of happening given that we have。

05 Fair flips coin。

![](img/9971ad9aa29e3c02756fef2ccc84002f_8.png)

So we use 0。95， we pass in 100 because we have 100 coin flips with a fair coin given our null hypothesis。

 and then we add on so that we know it's that amount or greater and we see that we end up with 59 so。



![](img/9971ad9aa29e3c02756fef2ccc84002f_10.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_11.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_12.png)

The odds， given that we have a fair coin of getting 59 or less is 95%。

 59 or greater would only be 5%。

![](img/9971ad9aa29e3c02756fef2ccc84002f_14.png)

So let's say。We want to make a more specific claim all right so so far so good。

 but let's say I say that I'm not perfect， but I can predict coin housesses 60% of the time。



![](img/9971ad9aa29e3c02756fef2ccc84002f_16.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_17.png)

Which is still good。 It's still valuable。 I can get it right，60% the time compared to the 50，50 flip。

😊，So what do we do in this case？Sure， we can do exactly what we did earlier and when I predict 57 times。

 we would reject the claim that I can get it right better than a 5050 chance。

But I can respond to that and say， wait a minute， 57 is closer to 60 than it is 50。

 maybe I was a little bit off， but。I'm doing all right。

 considering that I get it right 60% of the time。

![](img/9971ad9aa29e3c02756fef2ccc84002f_19.png)

So what do we say to that， the issue here is that there's no longer a single null hypothesis that we must prove or disprove。

 instead we have two competing hypotheses， hypothesis A， theres no predictive power， hypothesis B。

 there is a 60% predictive power。

![](img/9971ad9aa29e3c02756fef2ccc84002f_21.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_22.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_23.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_24.png)

And each one of our curves， when we're working with the binomial distribution will be a normal curve。

 it'll be centered at 50 versus 60 if you think about flipping a coin 100 times。

 you are most likely to get around 50， correct， if you're predicting if you have a 50% chance of getting correct。

 whereas if you have a 60% chance of getting correct， you will get around 60 correct。



![](img/9971ad9aa29e3c02756fef2ccc84002f_26.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_27.png)

So we plot this out mu being the average。

![](img/9971ad9aa29e3c02756fef2ccc84002f_29.png)

So if the first one it's going to be an average of 50。

 we set the variance equal to 10 and get the square root， which is just going to be R。



![](img/9971ad9aa29e3c02756fef2ccc84002f_31.png)

Standard deviation。

![](img/9971ad9aa29e3c02756fef2ccc84002f_33.png)

We are going to plot against the X axis， so we're just going to do NP dot L space1 through 100。

 which gives us values between 1 and 100， how many values do we want between 1100。

 we will have an array of 200 values equally spaced between 100， so 1 1。5 to 2。5 and so on。



![](img/9971ad9aa29e3c02756fef2ccc84002f_35.png)

We are then going to plot that X。Versus a Y variable， that y is going to be stats。orm。pdf。



![](img/9971ad9aa29e3c02756fef2ccc84002f_37.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_38.png)

Now， PDF is the probability distribution function。

![](img/9971ad9aa29e3c02756fef2ccc84002f_40.png)

If you ever are curious about。What a function does。

 we're just going to run it and we see that's the probability density function at X。

 So for each one of our values of x， we are going to output the probability of getting that value。



![](img/9971ad9aa29e3c02756fef2ccc84002f_42.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_43.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_44.png)

And then for that， we're using the normal distribution with a mean of 50 and a standard deviation of the square root of 1。



![](img/9971ad9aa29e3c02756fef2ccc84002f_46.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_47.png)

And then we do the same thing for 60。And then we plotlop this out。

 we set our x limits to just between 30 and 80， and we see that now looking at this curve。

 we have the values 50 at the middle of the blue curve and 60 at the middle of the orange curve and we see that the odds of getting around 57 is around where these two intersect。



![](img/9971ad9aa29e3c02756fef2ccc84002f_49.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_50.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_51.png)

So 57 correct guesses。

![](img/9971ad9aa29e3c02756fef2ccc84002f_53.png)

If we were to get the cumulative distribution function， now if we were working with 0。5。

 then we want to know the cumulative distribution function of that or greater。

 so we do one minus that value and we see that we have a 6% chance of getting something that extreme given that we're working with。



![](img/9971ad9aa29e3c02756fef2ccc84002f_55.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_56.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_57.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_58.png)

0int5 and then if we're working with 0。6。We have a 30% chance of getting something that extreme。



![](img/9971ad9aa29e3c02756fef2ccc84002f_60.png)

Now， both of these will fail our 5% threshold。

![](img/9971ad9aa29e3c02756fef2ccc84002f_62.png)

So what can we do from here？So one thing that we can do is decrease the confidence。



![](img/9971ad9aa29e3c02756fef2ccc84002f_64.png)

So since we have a claim at 50 and another claim at 60， our first option may be to pick a midpoint。

 which is 55 between 50 and 60。

![](img/9971ad9aa29e3c02756fef2ccc84002f_66.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_67.png)

And we can say if I can predict over 55， then I have predictive power。

 and this would mean that we have decreased our confidence level。



![](img/9971ad9aa29e3c02756fef2ccc84002f_69.png)

So saying here when I'm printing out1 minus byome dot CDf， it's going to be 55 or less， right。

 that's going to be the CDF， one minus that just means。



![](img/9971ad9aa29e3c02756fef2ccc84002f_71.png)

56 or greater。So that's going to be one side that's going to be。

56 or greater than we would reject the 0。5， 54 or less。Means that we're doing worse than 0。

6 by a significant amount。And because we are。Testing to the left of it。

 we do not need to do one minus that value。

![](img/9971ad9aa29e3c02756fef2ccc84002f_73.png)

And for both， we can get a value that extreme at an 87% confidence level。



![](img/9971ad9aa29e3c02756fef2ccc84002f_75.png)

And we can say that I have some predicted power since I got 57 tosses correct， it's not ideal。

 we picked a number which is prone to bias right it's just going to be defined according to whatever I say my confidence level is rather than an actual confidence interval。



![](img/9971ad9aa29e3c02756fef2ccc84002f_77.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_78.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_79.png)

So our second option is to be bias。

![](img/9971ad9aa29e3c02756fef2ccc84002f_81.png)

So it's not necessary that we bias the two hypotheses equally and pick the midpoint the way that we did。

The cutoff point could have been anywhere。

![](img/9971ad9aa29e3c02756fef2ccc84002f_83.png)

Currently our error margins are even at 13%， and the chance that someone has predicted power and we say no is 13% and the chance that someone has no power and we say that they do is also 13%。



![](img/9971ad9aa29e3c02756fef2ccc84002f_85.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_86.png)

And the idea is as we change this cutoff， one error that goes down。

 the chance of getting one of those errors goes down and the other will go up。



![](img/9971ad9aa29e3c02756fef2ccc84002f_88.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_89.png)

So for example， if we stuck with the original 95% on a coin being fair。



![](img/9971ad9aa29e3c02756fef2ccc84002f_91.png)

Again， using the inverse， then we would need a cutoff of 58 in order to say that this person has predictive power。



![](img/9971ad9aa29e3c02756fef2ccc84002f_93.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_94.png)

And if we think about 58， getting 58， given that we have。



![](img/9971ad9aa29e3c02756fef2ccc84002f_96.png)

A fair coin， which is our first one。 So we do one minus v。Curve the area of the curve under 58。



![](img/9971ad9aa29e3c02756fef2ccc84002f_98.png)

And we see that there's only a 5% chance of getting 59 or greater。

Given that we have a fair coin and if we had a biased coin or we are able to actually predict have predicted power of 60%。

 the chances of us predicting 58 correct is actually fairly likely compared to the less than 5% chance with the。



![](img/9971ad9aa29e3c02756fef2ccc84002f_100.png)

50，50 chance of getting it correct。

![](img/9971ad9aa29e3c02756fef2ccc84002f_102.png)

So 5% chance someone has no power and we say that they do。

 but there's a 38% chance someone has predicted power， and we say that they don't。

 So depending on the problem。

![](img/9971ad9aa29e3c02756fef2ccc84002f_104.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_105.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_106.png)

This may be exactly what we want， and these two types of errors are going to be called our type1 and type 2 errors which we introduce in lecture。



![](img/9971ad9aa29e3c02756fef2ccc84002f_108.png)

And we have the choice of biasing against one or the other in order to determine what our cutoff should actually be。



![](img/9971ad9aa29e3c02756fef2ccc84002f_110.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_111.png)

So rather than this trade off。The best case scenario would be if we could actually just increase sample size。



![](img/9971ad9aa29e3c02756fef2ccc84002f_113.png)

And when we increase sample size， so we see here we're going do going to do。



![](img/9971ad9aa29e3c02756fef2ccc84002f_115.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_116.png)

We're going to have a thousand rather than just 100 tosses。



![](img/9971ad9aa29e3c02756fef2ccc84002f_118.png)

Originally we had quite a bit of overlap between our two curves。



![](img/9971ad9aa29e3c02756fef2ccc84002f_120.png)

With a larger sample size， there will be much less of an overlap。

So the chances of trying to trade off between one or the other isn't as big of an issue。



![](img/9971ad9aa29e3c02756fef2ccc84002f_122.png)

And we can print for each of these what the cutoff would be。



![](img/9971ad9aa29e3c02756fef2ccc84002f_124.png)

Given on one side， we have a fair coin， the value higher than what value do we need higher than in order to say that there is predictive power versus on the other end。

 if we're using 60%， what value is lower then that we need to reject that hypothesis of 60%。

So on one end， it was 526， so if you can predict 526 or greater。

 I would say that you have predicted power， whereas if you have 574 or less。

 I would reject the null that you have 60% predicted power。



![](img/9971ad9aa29e3c02756fef2ccc84002f_126.png)

So what are our errors now if we pick that midbu point of 550？



![](img/9971ad9aa29e3c02756fef2ccc84002f_128.png)

The chances of getting 550。Given that， you have a。Even chance。Is going to be。



![](img/9971ad9aa29e3c02756fef2ccc84002f_130.png)

Very， very low。 So the chances of just randomly assuming you have a fair coin and that the person has no predictive power。

 it's a very low chance that they would get a value as extreme of 550。 But on the other hand。

 it's very unlikely that if he actually had 60% cent predictive power for you to get the 550 as well。



![](img/9971ad9aa29e3c02756fef2ccc84002f_132.png)

So that gives you a little idea of how you can increase sample size in order to avoid having to have this trade off between type 1 and type 2 errors。



![](img/9971ad9aa29e3c02756fef2ccc84002f_134.png)

That's it for this notebook， look forward to seeing you back at a lecture， Thank you。



![](img/9971ad9aa29e3c02756fef2ccc84002f_136.png)

![](img/9971ad9aa29e3c02756fef2ccc84002f_137.png)