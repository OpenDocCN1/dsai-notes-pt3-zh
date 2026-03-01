# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p61 16_罕见事件与马尔可夫.zh_en -BV1r483zbEzN_p61-

![](img/a4053166a72df2559ddceb898045d2c4_0.png)

Hello， I'm Dr。 I McCullough， and today we're going to be talking about one of my favorite topics。

 rare Events。

![](img/a4053166a72df2559ddceb898045d2c4_2.png)

So。Hopefully you have got a chance to see my T shirt。All right， so rare events。

 it's a rare event that I wear a tshirt in doing a lecture。

 but seriously rare events they occur a lot of times in statistics， especially in computer science。

 so there are things where we're trying to predict something that is generally unlikely。



![](img/a4053166a72df2559ddceb898045d2c4_4.png)

![](img/a4053166a72df2559ddceb898045d2c4_5.png)

![](img/a4053166a72df2559ddceb898045d2c4_6.png)

The black Swn and so there's certain important statistical implications of that。

 and that's what we're going to be discussing today right so we're going to be talking about Markov's theorem。

 we're going to be talking about a proof for Murphy's law and we'll talk about the chbychev's inequality and then we'll get into the central limit theorem which then kind of motivates。



![](img/a4053166a72df2559ddceb898045d2c4_8.png)

![](img/a4053166a72df2559ddceb898045d2c4_9.png)

![](img/a4053166a72df2559ddceb898045d2c4_10.png)

Normal hypothesis testing and statistics， which is pretty powerful from a modeling perspective。

 So we're going to start with Markov's theorem。

![](img/a4053166a72df2559ddceb898045d2c4_12.png)

![](img/a4053166a72df2559ddceb898045d2c4_13.png)

![](img/a4053166a72df2559ddceb898045d2c4_14.png)

![](img/a4053166a72df2559ddceb898045d2c4_15.png)

So Markov's theorem is as follows。

![](img/a4053166a72df2559ddceb898045d2c4_17.png)

![](img/a4053166a72df2559ddceb898045d2c4_18.png)

So if R is a non negative random variable， then for all a。



![](img/a4053166a72df2559ddceb898045d2c4_20.png)

Greater than 0。

![](img/a4053166a72df2559ddceb898045d2c4_22.png)

The probability。

![](img/a4053166a72df2559ddceb898045d2c4_24.png)

That are。Is greater than or equal to a。

![](img/a4053166a72df2559ddceb898045d2c4_26.png)

Is less than。Or equal to。The expected value of R。

![](img/a4053166a72df2559ddceb898045d2c4_28.png)

Divided by a。So what this is doing is creating an upper bound on the probability。

 It's creating an upper bound on the probability。 And so I'm going to prove out this really quick。

 the Markov theorem。 And then rather than belabor the point。

 we'll just do some examples that will show you the usefulness and applicability of this。

 But I think it's important to understand where it's coming from first。

 So the way we motivate this is we're going to start with an indicator function。 So if I have。😊。



![](img/a4053166a72df2559ddceb898045d2c4_30.png)

![](img/a4053166a72df2559ddceb898045d2c4_31.png)

![](img/a4053166a72df2559ddceb898045d2c4_32.png)

![](img/a4053166a72df2559ddceb898045d2c4_33.png)

![](img/a4053166a72df2559ddceb898045d2c4_34.png)

Right。If I have a。

![](img/a4053166a72df2559ddceb898045d2c4_36.png)

A function like the cumulative distribution function of x。



![](img/a4053166a72df2559ddceb898045d2c4_38.png)

And so I have a random variable， so that's going to go from zero to one because it's a cumulative distribution function。



![](img/a4053166a72df2559ddceb898045d2c4_40.png)

And this is my random variable。 And so I have a value here， a。



![](img/a4053166a72df2559ddceb898045d2c4_42.png)

And so for this indicator function， right？I will have。😔，Situation I here where it is zero and then。

We have a value where this for situation double I where this is one， right。

 so this is an indicator function。

![](img/a4053166a72df2559ddceb898045d2c4_44.png)

![](img/a4053166a72df2559ddceb898045d2c4_45.png)

So in the case。

![](img/a4053166a72df2559ddceb898045d2c4_47.png)

I， right right here in this area。Or。

![](img/a4053166a72df2559ddceb898045d2c4_49.png)

Times this indicator function， which we'll represent as1。

 the probability that R is greater than or equal to a。



![](img/a4053166a72df2559ddceb898045d2c4_51.png)

That is going to equal 0 in this case， when it's down here。



![](img/a4053166a72df2559ddceb898045d2c4_53.png)

For case。

![](img/a4053166a72df2559ddceb898045d2c4_55.png)

Double I right， R times 1。

![](img/a4053166a72df2559ddceb898045d2c4_57.png)

This indicator function is going to equal one in the case where we're operating up here。



![](img/a4053166a72df2559ddceb898045d2c4_59.png)

Okay。So if we just do a little bit more derivation there， that means that R times1。



![](img/a4053166a72df2559ddceb898045d2c4_61.png)

![](img/a4053166a72df2559ddceb898045d2c4_62.png)

Right then the indicator function here。Is less than or equal to R random a variable。



![](img/a4053166a72df2559ddceb898045d2c4_64.png)

That will imply that we have r times the expected value。



![](img/a4053166a72df2559ddceb898045d2c4_66.png)

Of。

![](img/a4053166a72df2559ddceb898045d2c4_68.png)

Wan。

![](img/a4053166a72df2559ddceb898045d2c4_70.png)

Right， expected value。Which is less than or equal to the expected value of。



![](img/a4053166a72df2559ddceb898045d2c4_72.png)

Or。In the other case here we have。Or times the probability。



![](img/a4053166a72df2559ddceb898045d2c4_74.png)

That R is greater than or equal to a。

![](img/a4053166a72df2559ddceb898045d2c4_76.png)

Is less than or equal to。

![](img/a4053166a72df2559ddceb898045d2c4_78.png)

The expected value of R。And that gives us then the probability that R greater than or equal to a。



![](img/a4053166a72df2559ddceb898045d2c4_80.png)

![](img/a4053166a72df2559ddceb898045d2c4_81.png)

Is less than or equal to the expected value of R。

![](img/a4053166a72df2559ddceb898045d2c4_83.png)

Divided by a。 Now I haven't really proven that。 so I'm going to do the proof right here。



![](img/a4053166a72df2559ddceb898045d2c4_85.png)

And so if I were to say the expected value of R。

![](img/a4053166a72df2559ddceb898045d2c4_87.png)

Equals the expected value of R given。

![](img/a4053166a72df2559ddceb898045d2c4_89.png)

Given that R is greater than or equal to a。

![](img/a4053166a72df2559ddceb898045d2c4_91.png)

Times the probability that R is greater than or equal to a。



![](img/a4053166a72df2559ddceb898045d2c4_93.png)

And then I add the expected value of R。

![](img/a4053166a72df2559ddceb898045d2c4_95.png)

Times， sorry， the expected value of R。

![](img/a4053166a72df2559ddceb898045d2c4_97.png)

Given。Given that R is less than a。

![](img/a4053166a72df2559ddceb898045d2c4_99.png)

Times the probability that R is less than a。

![](img/a4053166a72df2559ddceb898045d2c4_101.png)

J。

![](img/a4053166a72df2559ddceb898045d2c4_103.png)

So this is for condition you case1， this is for condition sorry this is for condition case two。

 this is for condition case1。

![](img/a4053166a72df2559ddceb898045d2c4_105.png)

![](img/a4053166a72df2559ddceb898045d2c4_106.png)

Okay。So this is when R is greater， the random of variable is greater than this threshold A。

 this is when it's less than that threshold A。

![](img/a4053166a72df2559ddceb898045d2c4_108.png)

So then we have the expected value of R。

![](img/a4053166a72df2559ddceb898045d2c4_110.png)

Is greater than or equal to。

![](img/a4053166a72df2559ddceb898045d2c4_112.png)

A。

![](img/a4053166a72df2559ddceb898045d2c4_114.png)

Times the。Probability。That R。

![](img/a4053166a72df2559ddceb898045d2c4_116.png)

Is greater than or equal to。Hey。

![](img/a4053166a72df2559ddceb898045d2c4_118.png)

Okay。And so if you look at this right， here we have the expected value of R。

 so it's essentially a one when we have a times the probability that we are greater that we're greater than this value。



![](img/a4053166a72df2559ddceb898045d2c4_120.png)

![](img/a4053166a72df2559ddceb898045d2c4_121.png)

![](img/a4053166a72df2559ddceb898045d2c4_122.png)

Okay， and so what that gives us then is if I divide both sides by that constant a， then I have。



![](img/a4053166a72df2559ddceb898045d2c4_124.png)

![](img/a4053166a72df2559ddceb898045d2c4_125.png)

The probability。Divided by a， both sides is greater than or equal to the probability that r is greater than or equal to a。

 and the reason why we can do that without flipping it is because I had that condition that a is greater than 0。

 and so then you'll see that this probability r is greater than a is less than expected value of r divided by a。



![](img/a4053166a72df2559ddceb898045d2c4_127.png)

Okay。And then the corollary to that is so the corollary。



![](img/a4053166a72df2559ddceb898045d2c4_129.png)

Is。If or。

![](img/a4053166a72df2559ddceb898045d2c4_131.png)

So if R is a non negative random variable， then for all C。



![](img/a4053166a72df2559ddceb898045d2c4_133.png)

Greater than0。

![](img/a4053166a72df2559ddceb898045d2c4_135.png)

The probability。That。😔，Or。

![](img/a4053166a72df2559ddceb898045d2c4_137.png)

Is greater than or equal to c times the expected value of R。



![](img/a4053166a72df2559ddceb898045d2c4_139.png)

![](img/a4053166a72df2559ddceb898045d2c4_140.png)

Is less than or equal to one over c。

![](img/a4053166a72df2559ddceb898045d2c4_142.png)

So that's just by extension。Okay， so now we're going to switch in the next video to looking at some example problems of the Mark office。



![](img/a4053166a72df2559ddceb898045d2c4_144.png)

![](img/a4053166a72df2559ddceb898045d2c4_145.png)