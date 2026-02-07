# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P19：P19 StatsLearning Lect6f 111113new.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/c8784b3c2ea7b42964a3d2399601a53d_0.png)

So look let's look again in the simple case when we got one variable，1 x。



![](img/c8784b3c2ea7b42964a3d2399601a53d_2.png)

Again， we're going to get a bit more mathhy now。This is the form。

 the mathematical form of the Gaussian density function。



![](img/c8784b3c2ea7b42964a3d2399601a53d_4.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_5.png)

For class K。When you got a single x。So there's some constant over。



![](img/c8784b3c2ea7b42964a3d2399601a53d_7.png)

The important part that depends on x is in this exponential form over year。



![](img/c8784b3c2ea7b42964a3d2399601a53d_9.png)

And we see。There's a mu subK， which is the mean for the observations in class K。



![](img/c8784b3c2ea7b42964a3d2399601a53d_11.png)

The population， meaning class K and sigma sub K is the variance for that variable in class K。



![](img/c8784b3c2ea7b42964a3d2399601a53d_13.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_14.png)

Now。In the first instance， we can assume that。

![](img/c8784b3c2ea7b42964a3d2399601a53d_16.png)

The variance sigma sub K is actually the sigma the same in each of the classes。



![](img/c8784b3c2ea7b42964a3d2399601a53d_18.png)

Now， that's a convenience。It turns out it's an important convenience。

 And it's going to determine whether the discrimininate function that we get the discriminants analysis gives us linear functions or quadratic functions。



![](img/c8784b3c2ea7b42964a3d2399601a53d_20.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_21.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_22.png)

So。If we plug into base formula。The， the formula we had and two slides back。

 we get a rather complicated expression。

![](img/c8784b3c2ea7b42964a3d2399601a53d_24.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_25.png)

So we've just plugged in this the form of the density in the numerator。

 And there's the sum of the classes in the denominator。



![](img/c8784b3c2ea7b42964a3d2399601a53d_27.png)

And it looks pretty nasty。Well， luckily there's some simplifications and cancellations。



![](img/c8784b3c2ea7b42964a3d2399601a53d_29.png)

嗯。

![](img/c8784b3c2ea7b42964a3d2399601a53d_31.png)

Now。We get this because to classify an observation to a class。

 we don't need to necessarily evaluate the probabilities。 We just need to see which is the largest。



![](img/c8784b3c2ea7b42964a3d2399601a53d_33.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_34.png)

So if we take logs， whenever you see exponentials， the first thing you want to do is take log logs。



![](img/c8784b3c2ea7b42964a3d2399601a53d_36.png)

And if we discard terms that do not depend on K。

![](img/c8784b3c2ea7b42964a3d2399601a53d_38.png)

Then we， so that's amounts to do in a lot of cancellation of things of。



![](img/c8784b3c2ea7b42964a3d2399601a53d_40.png)

Terms that don't count。This is equivalent to assign into the class with the largest discriminant score。

And so that complicated expression boils down to a much simpler expression over here。And notice。

 it involves X。The single variable in this case。 And then it involves the mean and variance for the。

 for the distribution， and it involves the prior。

![](img/c8784b3c2ea7b42964a3d2399601a53d_42.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_43.png)

Okay。

![](img/c8784b3c2ea7b42964a3d2399601a53d_45.png)

And importantly， in this case， this is a linear function of x。 So there's a single coefficient for x。



![](img/c8784b3c2ea7b42964a3d2399601a53d_47.png)

There's a constant。 and then there's a constant term。

 which is consists of these two pieces every year。

![](img/c8784b3c2ea7b42964a3d2399601a53d_49.png)

Okay。And so we get one of those functions for each of the classes。



![](img/c8784b3c2ea7b42964a3d2399601a53d_51.png)

If they are two classes， you can simplify even further。



![](img/c8784b3c2ea7b42964a3d2399601a53d_53.png)

And let's suppose now that the probability of class 1 is equal to the probability of class 2。

 which is 0。05。

![](img/c8784b3c2ea7b42964a3d2399601a53d_55.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_56.png)

Then you can see in this case that the decision boundary。Is exactly at。



![](img/c8784b3c2ea7b42964a3d2399601a53d_58.png)

M 1 plus mu to over 2， so。

![](img/c8784b3c2ea7b42964a3d2399601a53d_60.png)

It's back to this picture。嗯。

![](img/c8784b3c2ea7b42964a3d2399601a53d_62.png)

In the previous slide， in this case， the price were equal。

 These are actually two Gaussian distributions。

![](img/c8784b3c2ea7b42964a3d2399601a53d_64.png)

And the decision boundary here is at zero。 In this case。

 the two means were exactly the equal amount on the opposite side of0。 So the average is at0。



![](img/c8784b3c2ea7b42964a3d2399601a53d_66.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_67.png)

So intuitively， that's， that's the right value for the decision boundary。

 which is the point at which we classify to one class。

 the boundary at which we switch from classify to one class versus the other。



![](img/c8784b3c2ea7b42964a3d2399601a53d_69.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_70.png)

It's not that hard to show。 So see if you can show that。

 you basically use this expression for each of the two classes and look to see when。

 when it's the ones bigger than the other， not that hard to do。 I'm confused。

 There was a square term in the previous expression， and it's gone。 Oh， Rob。

 are you causing trouble here again。

![](img/c8784b3c2ea7b42964a3d2399601a53d_72.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_73.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_74.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_75.png)

I was hoping to avoid that nasty， but。

![](img/c8784b3c2ea7b42964a3d2399601a53d_77.png)

Rob's right。 What if， if you expand out the squared term here， there's going to be an x squared。



![](img/c8784b3c2ea7b42964a3d2399601a53d_79.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_80.png)

But， you know， it's got， there's an x squared in the numerator。

 and there's x squares in each of the terms in the denominator。

 And there's no coefficients in front of that x squared that's specific to a class。

 So that's one of the things that cancel out in this ratio。



![](img/c8784b3c2ea7b42964a3d2399601a53d_82.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_83.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_84.png)

You knew that。Rob knew then。

![](img/c8784b3c2ea7b42964a3d2399601a53d_86.png)

All right。So this is with populations。 What happens if we have data。

 we can't draw nice density functions like we've done over year， but we just estimate them。

 So here's a picture where we've actually got data。

 So we've drawn histograms instead of density functions。



![](img/c8784b3c2ea7b42964a3d2399601a53d_88.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_89.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_90.png)

Now， what we do is we actually。

![](img/c8784b3c2ea7b42964a3d2399601a53d_92.png)

We need to estimate the， for the Gaussian rule， We need to estimate the means in the two populations and the common standard deviation。



![](img/c8784b3c2ea7b42964a3d2399601a53d_94.png)

Well， in this case， the means。

![](img/c8784b3c2ea7b42964a3d2399601a53d_96.png)

嗯。The true means。

![](img/c8784b3c2ea7b42964a3d2399601a53d_98.png)

Minus 1。5 and 1。5。Which means the average mean is 0， and the， the probabilities were 005。



![](img/c8784b3c2ea7b42964a3d2399601a53d_100.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_101.png)

But we don't know these。 So we're going to estimate them from the。

 from the observed data and then plug them into the rule。



![](img/c8784b3c2ea7b42964a3d2399601a53d_103.png)

So。This is how we estimate them。 The price we need to estimate。

 So that's just the number in each class divided by the total number。 That's obvious。

 The means in each class， we just compute the sample mean in each of the classes。

 This is a tricky little notation here， This says。

![](img/c8784b3c2ea7b42964a3d2399601a53d_105.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_106.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_107.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_108.png)

1 over N K， that's the number in class K。 And this is a sum over I such that Y I is equal to K。

 So Y I is recording the class label。 So this will just sum those Xs that are in class K。

 And clearly， that's the right thing to do to get the sample mean。



![](img/c8784b3c2ea7b42964a3d2399601a53d_110.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_111.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_112.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_113.png)

The sigma square is a little trickier。We， we assume the the。

 the variance is the same in each of the classes。

![](img/c8784b3c2ea7b42964a3d2399601a53d_115.png)

And so， this is a formula。

![](img/c8784b3c2ea7b42964a3d2399601a53d_117.png)

It's called the pooled variance estimate。So。

![](img/c8784b3c2ea7b42964a3d2399601a53d_119.png)

We subtract from each exc the mean for its class。So this is what we do if we were computing the variance in class K。



![](img/c8784b3c2ea7b42964a3d2399601a53d_121.png)

But we sum all those squared differences。And we sum them over all the classes and then divided by n minus K。



![](img/c8784b3c2ea7b42964a3d2399601a53d_123.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_124.png)

So if， if that doesn't make too too much sense， another way of writing that is。

 is in this form over year， which says we estimate。



![](img/c8784b3c2ea7b42964a3d2399601a53d_126.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_127.png)

The sample variance separately in each of the classes。



![](img/c8784b3c2ea7b42964a3d2399601a53d_129.png)

And then we average them using this formula over year。

So this is just like a weight on each of those variances， which。

 and that weights to do with how many observations we in that class。



![](img/c8784b3c2ea7b42964a3d2399601a53d_131.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_132.png)

Relative to the total number of observations。And then the -1 and the  k。 that's a detailed。

 And it's to do with how many parameters we've estimated for each of these estimates。

 is one parameter。 It's the mean。

![](img/c8784b3c2ea7b42964a3d2399601a53d_134.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_135.png)

![](img/c8784b3c2ea7b42964a3d2399601a53d_136.png)

Rob's falling asleep， too much detail way too much detail。



![](img/c8784b3c2ea7b42964a3d2399601a53d_138.png)

So there we have it， those are the formulas。😊，You plug those back in。 Youll now get estimated。



![](img/c8784b3c2ea7b42964a3d2399601a53d_140.png)

呃。

![](img/c8784b3c2ea7b42964a3d2399601a53d_142.png)

Decision boundary。 And instead of being exactly 0， it's， in this case。

 it's slightly to the left of 0， but pretty close。

![](img/c8784b3c2ea7b42964a3d2399601a53d_144.png)