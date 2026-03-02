# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p39 38_均值与期望关系.zh_en -BV1r483zbEzN_p39-

![](img/1b08de46b6d14142bd57b17638dd041c_0.png)

Okay， we've been talking about continuous random variables。 So now for continuous random variables。



![](img/1b08de46b6d14142bd57b17638dd041c_2.png)

ConContinuous。Con continue us。

![](img/1b08de46b6d14142bd57b17638dd041c_4.png)

Random variables， we are going to be talking about means。



![](img/1b08de46b6d14142bd57b17638dd041c_6.png)

And variance。

![](img/1b08de46b6d14142bd57b17638dd041c_8.png)

And we're not going to call it a mean。 we're going to call it something slightly similar to a mean。

 We're going to talk about expected。

![](img/1b08de46b6d14142bd57b17638dd041c_10.png)

![](img/1b08de46b6d14142bd57b17638dd041c_11.png)

Value。Right， expected value。 Now， the expected value。

 just like when we were looking at probability mass function。

 what do we do in a probability mass function right when we were looking at expected value， right。

 So for a discrete。

![](img/1b08de46b6d14142bd57b17638dd041c_13.png)

![](img/1b08de46b6d14142bd57b17638dd041c_14.png)

![](img/1b08de46b6d14142bd57b17638dd041c_15.png)

Right， discrete。Brandom variable， expected value。

![](img/1b08de46b6d14142bd57b17638dd041c_17.png)

Was the summ， right over of。

![](img/1b08de46b6d14142bd57b17638dd041c_19.png)

The probability masses over there are times x over your distribution over your mass function。

 right so you would do this。 So when we do it for continuous random variables。

 for continuous random variables。

![](img/1b08de46b6d14142bd57b17638dd041c_21.png)

![](img/1b08de46b6d14142bd57b17638dd041c_22.png)

![](img/1b08de46b6d14142bd57b17638dd041c_23.png)

![](img/1b08de46b6d14142bd57b17638dd041c_24.png)

Our expected value。Is similar， it just gets replaced instead of a summation with an integral。



![](img/1b08de46b6d14142bd57b17638dd041c_26.png)

![](img/1b08de46b6d14142bd57b17638dd041c_27.png)

And we'll have x times the density function。In order to get the expected value。

 now why is that important？

![](img/1b08de46b6d14142bd57b17638dd041c_29.png)

It's hard for us to get our head around why we're doing this。

 what this means right it's much easier to look and say， hey。

 you know I have you know if I have some sort of like I'm going to roll a six sided dice right so I have my distribution looks something like this。

 right？

![](img/1b08de46b6d14142bd57b17638dd041c_31.png)

![](img/1b08de46b6d14142bd57b17638dd041c_32.png)

![](img/1b08de46b6d14142bd57b17638dd041c_33.png)

![](img/1b08de46b6d14142bd57b17638dd041c_34.png)

One， two， three， four， five， six， right？

![](img/1b08de46b6d14142bd57b17638dd041c_36.png)

And this is 1，2，3，456 right It's easy for me to say， okay。

 well Im going all of these probabilities are 16。 they're equal。

 so I'm going to then add the sum of these。 I'm going to add one， I'll write it here。

 I'm going add one times16 plus2 times 16 plus all the way up to6 times 16 I can factor the 16 out and I can add 1 plus2 plus 3 plus 4 plus5 plus6 and I'll get 3。

5 because what you're doing is you're adding the value as you're weighting it across that frequency and you end up getting with like an expectation or average value somewhere in the middle we can count that。

 we can kind of understand what that looks like when we get into a continuous distribution。

 we can no longer count so but we can look at the analogy and we can say well I'm doing exactly the same thing。

 I'm just replacing the summation with an integral。



![](img/1b08de46b6d14142bd57b17638dd041c_38.png)

![](img/1b08de46b6d14142bd57b17638dd041c_39.png)

![](img/1b08de46b6d14142bd57b17638dd041c_40.png)

![](img/1b08de46b6d14142bd57b17638dd041c_41.png)

![](img/1b08de46b6d14142bd57b17638dd041c_42.png)

![](img/1b08de46b6d14142bd57b17638dd041c_43.png)

![](img/1b08de46b6d14142bd57b17638dd041c_44.png)

![](img/1b08de46b6d14142bd57b17638dd041c_45.png)

![](img/1b08de46b6d14142bd57b17638dd041c_46.png)

![](img/1b08de46b6d14142bd57b17638dd041c_47.png)

![](img/1b08de46b6d14142bd57b17638dd041c_48.png)

![](img/1b08de46b6d14142bd57b17638dd041c_49.png)

I'm replacing the probability mass with a probability density and so we can kind of get some intuition as to why that works for an expectation What the expected value is telling you is if if I drew from this sample many。

 many times right on average over a long period of time what would I expect that average to be right what would I expect the typical value from that that distribution look like so if I ran two miles every day over and over go and you cut up all those samples right you would then look and say I would expect on average for him to run his two mile run in in 12 minutes right？



![](img/1b08de46b6d14142bd57b17638dd041c_51.png)

![](img/1b08de46b6d14142bd57b17638dd041c_52.png)

![](img/1b08de46b6d14142bd57b17638dd041c_53.png)

![](img/1b08de46b6d14142bd57b17638dd041c_54.png)

![](img/1b08de46b6d14142bd57b17638dd041c_55.png)

So that's the expected value。

![](img/1b08de46b6d14142bd57b17638dd041c_57.png)

Just another little property here is if I want to look at something for a function， right。

 a function。

![](img/1b08de46b6d14142bd57b17638dd041c_59.png)

Right so what do I mean by a function Well I do my two mile runtime and you multiply it by three and subtract5 right you know what does that look like right so that's a function of if you taken the random variable and you do some algebra to it。

 what does that equal Well the way we change that is we just make it G of x instead of x。



![](img/1b08de46b6d14142bd57b17638dd041c_61.png)

![](img/1b08de46b6d14142bd57b17638dd041c_62.png)

![](img/1b08de46b6d14142bd57b17638dd041c_63.png)

![](img/1b08de46b6d14142bd57b17638dd041c_64.png)

![](img/1b08de46b6d14142bd57b17638dd041c_65.png)

Right。So that expectation just is what's getting multiplied。 So here it's an x。



![](img/1b08de46b6d14142bd57b17638dd041c_67.png)

Here it's a G of x， right。

![](img/1b08de46b6d14142bd57b17638dd041c_69.png)

The other key principle we have is variance， and so the variance of x。



![](img/1b08de46b6d14142bd57b17638dd041c_71.png)

We sometimes write as a。

![](img/1b08de46b6d14142bd57b17638dd041c_73.png)

Variance is a little sigma of x squared and again with the probability mass function。

 we had an observation minus the expected value and that quantity squared times as mass function。

 so here we're going to go back to an integral or integral and we will have x minus the expected value of x。

 that value squared times f of x。

![](img/1b08de46b6d14142bd57b17638dd041c_75.png)

![](img/1b08de46b6d14142bd57b17638dd041c_76.png)

![](img/1b08de46b6d14142bd57b17638dd041c_77.png)

![](img/1b08de46b6d14142bd57b17638dd041c_78.png)

![](img/1b08de46b6d14142bd57b17638dd041c_79.png)

Dx。Now why do we square it， why do we have this operation？



![](img/1b08de46b6d14142bd57b17638dd041c_81.png)

Let's talk a little bit about what this means。

![](img/1b08de46b6d14142bd57b17638dd041c_83.png)

So。If I'm looking at a distribution and I have this kind of like central tendency。

 it's going to typically be around this central value when run time will typically be around 12 minutes for two miles right Well。

 that's great。 But every time I run， I can't get exactly that value。

 So every time I run I'm either a little bit more or a little bit less right。

 kind it kind of varies So what is the what is the on average。

 how far off am I from that that central tendency。😊。



![](img/1b08de46b6d14142bd57b17638dd041c_85.png)

![](img/1b08de46b6d14142bd57b17638dd041c_86.png)

![](img/1b08de46b6d14142bd57b17638dd041c_87.png)

![](img/1b08de46b6d14142bd57b17638dd041c_88.png)

![](img/1b08de46b6d14142bd57b17638dd041c_89.png)

![](img/1b08de46b6d14142bd57b17638dd041c_90.png)

Well， how would you measure that， Well you take your observation and you subtract it from whatever that central tendency is that tells you a distance。



![](img/1b08de46b6d14142bd57b17638dd041c_92.png)

Well， if I have this you know this is my number line of possible values and this represents my expected value right well for every observation I have above the mean I got one below the mean right and maybe I have a couple that are like really close here to make up for one that's a little bit farther away right so I have these values that are spread out。



![](img/1b08de46b6d14142bd57b17638dd041c_94.png)

![](img/1b08de46b6d14142bd57b17638dd041c_95.png)

![](img/1b08de46b6d14142bd57b17638dd041c_96.png)

![](img/1b08de46b6d14142bd57b17638dd041c_97.png)

![](img/1b08de46b6d14142bd57b17638dd041c_98.png)

If I take the difference so here's the mean and I take x minus the expected value all these numbers here are positive。

 all these numbers are negative when I add them all together they sum to zero well that doesn't tell me anything。



![](img/1b08de46b6d14142bd57b17638dd041c_100.png)

![](img/1b08de46b6d14142bd57b17638dd041c_101.png)

![](img/1b08de46b6d14142bd57b17638dd041c_102.png)

So what I need to do is I need to make sure that the negatives and the positives don't cancel each other out。

 So there's two ways to do that。 One way would be to use an absolute value。



![](img/1b08de46b6d14142bd57b17638dd041c_104.png)

![](img/1b08de46b6d14142bd57b17638dd041c_105.png)

But if we recall from calculus， if you have an absolute value。

 that function looks has like a sharp point here and it's not continuous。

 so I can't use calculus for an absolute value。

![](img/1b08de46b6d14142bd57b17638dd041c_107.png)

![](img/1b08de46b6d14142bd57b17638dd041c_108.png)

So what I need to do is square it as a way to make them all positive。

 I suppose you could take it to the fourth power， there's probably other interesting things you can do。

 but the old dead guys that came up with statistics decided if you squared it。

 it creates a nice smooth parabolic shape that you can then do integration you can use calculus with。

 and so that's why variants exists。

![](img/1b08de46b6d14142bd57b17638dd041c_110.png)

![](img/1b08de46b6d14142bd57b17638dd041c_111.png)

![](img/1b08de46b6d14142bd57b17638dd041c_112.png)

![](img/1b08de46b6d14142bd57b17638dd041c_113.png)

![](img/1b08de46b6d14142bd57b17638dd041c_114.png)

And that's why we square it。But the problem is now you've squared that difference。 it has no meaning。

 when you see this really， really large number， you have no way of wrapping your head around what it is or know what it's supposed to be。

 So we end up with the idea that the standard deviation is the square root of the variance and so the standard deviation is telling us essentially roughly the average distance。



![](img/1b08de46b6d14142bd57b17638dd041c_116.png)

![](img/1b08de46b6d14142bd57b17638dd041c_117.png)

![](img/1b08de46b6d14142bd57b17638dd041c_118.png)

![](img/1b08de46b6d14142bd57b17638dd041c_119.png)

![](img/1b08de46b6d14142bd57b17638dd041c_120.png)

Observations。Observations。

![](img/1b08de46b6d14142bd57b17638dd041c_122.png)

Fo。😔，From。😔，The expected value。That's essentially what the standard deviation is doing。

 so that gives us some sort of intuitive number to wrap our head around。



![](img/1b08de46b6d14142bd57b17638dd041c_124.png)

![](img/1b08de46b6d14142bd57b17638dd041c_125.png)

Okay so。