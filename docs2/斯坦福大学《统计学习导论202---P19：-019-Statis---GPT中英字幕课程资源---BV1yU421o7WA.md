# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P19：-019-Statistical Learning_ 4.5 Discriminant Analysis.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

![](img/e5ace150fb168d19d4e709b956236660_0.png)

We're not going to go into more detail on multinoial regression hour。

 What we're going to do is tell you about a different classification method。

 which is called discriminant analysis， which is also very useful。 And it。

 it it approaches a problem from a really quite different point of view。



![](img/e5ace150fb168d19d4e709b956236660_2.png)

![](img/e5ace150fb168d19d4e709b956236660_3.png)

In disccrmininate analysis， the， the idea is to model the distribution of x in each of the classes separately。

And then use what's known as Bays theorem to flip things around to get the probability of Y given x。

In this case， for disc linear discriminant analysis。

 we're going to use Gaussian distributions for each class。

And that's going to lead to linear or quadratic discriminant analysis。

 So those are the two popular forms。

![](img/e5ace150fb168d19d4e709b956236660_5.png)

But as you'll see， this approach is is quite general， and other distributions can be used as well。



![](img/e5ace150fb168d19d4e709b956236660_7.png)

But we'll focus on normal distributions。So what is Baybe's theorem for classification？

So it sounds pretty scary， but not too bad。 So， of course， Thomas Bayys was a famous mathematician。😰。



![](img/e5ace150fb168d19d4e709b956236660_9.png)

And his name now today represents a burgeoning subfield of statistical and probilistic modeling。

 but here we're going to focus on a very simple result， which is known as Bay theorem。



![](img/e5ace150fb168d19d4e709b956236660_11.png)

![](img/e5ace150fb168d19d4e709b956236660_12.png)

And it says that the probability of y equals k given x equals x。 So you've got the ideas。

 you've got two two variables。 in this case， we've got Y and X。

And we we looking at aspects of the joint distribution。

So this is what we offer the probability of y equals k given x。

And base theorem says you can flip things around。 You can write that as the probability that x is x。

 given y equals K。That's the first piece on the， on the top there。



![](img/e5ace150fb168d19d4e709b956236660_14.png)

Multiplied by the marginal probability or prior probability that y is K。And then， divided by。

The marginal probability that x equals x。So this is just a formula from probability theory。

But it turns out it's really useful and theres the basis for discriminant analysis。



![](img/e5ace150fb168d19d4e709b956236660_16.png)

And so。We write things slightly differently in the case of discriminant analysis。

So this probability y equals k。

![](img/e5ace150fb168d19d4e709b956236660_18.png)

Is。Written as P k。So， if there's。If there's three classes， they're gonna be three values for pi。

 just the probability for each of the classes。 But here we've got。



![](img/e5ace150fb168d19d4e709b956236660_20.png)

Cls little K。 So that's pi K。Probability that。X is x given y equals k。 Well。

 if x is is a quantitative variable。We read what we write for that is the density。

 So that's a probability density function for x in class K。



![](img/e5ace150fb168d19d4e709b956236660_22.png)

![](img/e5ace150fb168d19d4e709b956236660_23.png)

And then the marginal probability of of x is just。This expression over here。

So this is summing over all the classes。Okay。And， and so that's how we use Bay theorem to get to the probabilities of interest。

 which is y equals K given x。Now， at this point， it's still quite general。

 we can plug in any probability densities， but now what we're going to do is go ahead and plug in the Gaussian density。

For F sub K of x。

![](img/e5ace150fb168d19d4e709b956236660_25.png)

嗯。Before we do that， let me just show you a little picture to， to make things clear。

In the left hand plot， whatever have we got here， we've got a plot against x， single variable x。

And in the vertical axis， what we've got is actually pi sub K。And multiplied by f sub K of x。

For both classes， K equals 1 and K equals 2。Now， in this case。So remember， in the previous slide。

 the probability was essentially proportional to pi sub K time times F sub K of x。And in this case。

 the， the pis are the same for both。 So it's really to do with which density is the highest。

And you can see that。The decision boundary of the vertical dash line is at 0。

 And that's a point at which the green density is higher than the purple density。

And so anything to the left or 0， we classify as as green。

And anything to the right would classify as， as purple。Okay。

 and it sort of makes sense that that's what we do there。



![](img/e5ace150fb168d19d4e709b956236660_27.png)

The right end plot has has different prize。So， you。The probability of 2 is 0。7 and， and of。

 of 1 is 0。3。And now again， we've multiple we， we plot in pi sub K。



![](img/e5ace150fb168d19d4e709b956236660_29.png)

Times f sub K of x。Against x。And that bigger p as， has bumped up the purple。

 And what is done is move the decision boundary slightly to the left。



![](img/e5ace150fb168d19d4e709b956236660_31.png)

![](img/e5ace150fb168d19d4e709b956236660_32.png)

And that makes sense， too， again， it's where they intersect。That makes sense as well。

 because we've got more， we've got more purples here。 Actually， I say they pinks。

 It looks purple to me。There's more of them。 So everything else being equal。

 we're going to make less mistakes if we， if we classify it to， to， to purples and to， to greens。



![](img/e5ace150fb168d19d4e709b956236660_34.png)

![](img/e5ace150fb168d19d4e709b956236660_35.png)

Okay， so that's a rope。 that's how these， these prize and。

 and the densities play a role in classification。

![](img/e5ace150fb168d19d4e709b956236660_37.png)

Okay， so， so why discriminant analysis， It seemed like logistic regression was a pretty good tool。

 Well， it is。 but it turns out there's a room for discriminant analysis as well。And so。

It's three points we make here when the classes are well separated。

It turns out that the parameter estimates for logistic regression。A surprisingly unstable。 In fact。

 if you've got a feature that separates the classes perfectly， the coefficients。Go off to infinity。

So it really doesn't do well there。Thetic regression was developed in in。

 in the largely in the biological and medical fields， where you never found such strong predictors。

Now， you can do things to， to， to make logistic regression better behave。

 But it turns out linear discriminants analysis doesn't suffer from this problem and is better behaved in those situations。

Also， if any is small， the sample size is small。And the distribution of the predictorss X is approximately normal in in in each of the classes。

 It turns out the linear regression discriminant model is， again。

 more stable than logistic regression。And finally， if we've got more than two classes。

 we'll see logistic regression gives us nice low dimensional views of the data。 And the other point。

 remember， in the very first section， we show that the Bays rule。

 if you have the right population model， the Bays rule is the best you can possibly do。

So if our normal assumption is right here， then then this Bay rule from Sc analysis from the Bays rule is is the best you can possibly do。

 good point， drum。