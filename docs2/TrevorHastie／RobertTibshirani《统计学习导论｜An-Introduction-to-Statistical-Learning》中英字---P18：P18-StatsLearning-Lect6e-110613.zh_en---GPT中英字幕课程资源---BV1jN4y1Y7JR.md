# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P18：P18 StatsLearning Lect6e 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/0606947fe9f72434f22ee1d7ced83186_0.png)

We're not going to go into more detail on multinoial regression hour。

 What we're going to do is tell you about a different classification method。

 which is called discriminants analysis， which is also very useful。

 And it it it approaches a problem from a really quite different point of view。



![](img/0606947fe9f72434f22ee1d7ced83186_2.png)

![](img/0606947fe9f72434f22ee1d7ced83186_3.png)

![](img/0606947fe9f72434f22ee1d7ced83186_4.png)

In disccrimmininate analysis， the， the idea is to model the distribution of x in each of the classes separately。



![](img/0606947fe9f72434f22ee1d7ced83186_6.png)

And then use what's known as Bay theorem to flip things around to get the probability of Y given X。



![](img/0606947fe9f72434f22ee1d7ced83186_8.png)

![](img/0606947fe9f72434f22ee1d7ced83186_9.png)

In this case， for disc linear discriminant analysis。

 we're going to use Gaussian distributions for each clause。



![](img/0606947fe9f72434f22ee1d7ced83186_11.png)

And that's going to lead to linear or quadratic discriminant analysis。

 So those are the two popular forms。

![](img/0606947fe9f72434f22ee1d7ced83186_13.png)

![](img/0606947fe9f72434f22ee1d7ced83186_14.png)

But as you'll see， this approach is is quite general， and other distributions can be used as well。



![](img/0606947fe9f72434f22ee1d7ced83186_16.png)

But we' will focus on normal distributions。

![](img/0606947fe9f72434f22ee1d7ced83186_18.png)

So what is Bayess theorem for classification？So it sounds pretty scary， but not too bad。 So。

 of course， Thomas Bayyes was a famous mathematician。😰。



![](img/0606947fe9f72434f22ee1d7ced83186_20.png)

![](img/0606947fe9f72434f22ee1d7ced83186_21.png)

And his name now today represents a burgeon in subfield of statistical and probilistic modeling。

 but here we're going to focus on a very simple result， which is known as base theorem。



![](img/0606947fe9f72434f22ee1d7ced83186_23.png)

![](img/0606947fe9f72434f22ee1d7ced83186_24.png)

And it says that the probability of y equals k given x equals x。 So you've got the ideas。

 you've got two variables。 in this case， we've got y and X。



![](img/0606947fe9f72434f22ee1d7ced83186_26.png)

![](img/0606947fe9f72434f22ee1d7ced83186_27.png)

![](img/0606947fe9f72434f22ee1d7ced83186_28.png)

And we we looking at aspects of the joint distribution。



![](img/0606947fe9f72434f22ee1d7ced83186_30.png)

So this is what we offer the probability of y equals k given x。

And base theorem says you can flip things around。 You can write that as the probability that x is x。

 given y equals k。

![](img/0606947fe9f72434f22ee1d7ced83186_32.png)

![](img/0606947fe9f72434f22ee1d7ced83186_33.png)

That's the first piece on the top there。

![](img/0606947fe9f72434f22ee1d7ced83186_35.png)

Multiplied by the marginal probability or prior probability that y is K。



![](img/0606947fe9f72434f22ee1d7ced83186_37.png)

And then， divided by。

![](img/0606947fe9f72434f22ee1d7ced83186_39.png)

The marginal probability that x equals x。So this is just a formula from probability theory。



![](img/0606947fe9f72434f22ee1d7ced83186_41.png)

But it turns it's really useful and there's the basis for discriminant analysis。



![](img/0606947fe9f72434f22ee1d7ced83186_43.png)

And so。We write things slightly differently in the case of discriminant analysis。

So this probability y equals k。

![](img/0606947fe9f72434f22ee1d7ced83186_45.png)

Is。Written as Pi K。So， if there's。

![](img/0606947fe9f72434f22ee1d7ced83186_47.png)

If there's three classes， it's going be three values for pi。

 just the probability for each of the classes。 But here， we've got。



![](img/0606947fe9f72434f22ee1d7ced83186_49.png)

Cl little K。 So that's pi K。Probability that。

![](img/0606947fe9f72434f22ee1d7ced83186_51.png)

X is x given y equals k。 Well， if x is a quantitative variable。



![](img/0606947fe9f72434f22ee1d7ced83186_53.png)

We read what we write for that is the density。 So that's a probability density function for x in class K。



![](img/0606947fe9f72434f22ee1d7ced83186_55.png)

![](img/0606947fe9f72434f22ee1d7ced83186_56.png)

And then the marginal probability of of x is just。

![](img/0606947fe9f72434f22ee1d7ced83186_58.png)

This expression over here。So this is summing over all the classes。Okay。



![](img/0606947fe9f72434f22ee1d7ced83186_60.png)

And， and so that's how we use Bay theorem to get to the probabilities of interest。

 which is y equals K given x。

![](img/0606947fe9f72434f22ee1d7ced83186_62.png)

Now， at this point， it's still quite general。 we can plug in any probability densities。

 but now what we're going to do is go ahead and plug in the Gaussian density。



![](img/0606947fe9f72434f22ee1d7ced83186_64.png)

![](img/0606947fe9f72434f22ee1d7ced83186_65.png)

For F sub K of x。嗯。Before we do that， let me just show you a little picture to， to make things clear。



![](img/0606947fe9f72434f22ee1d7ced83186_67.png)

In the left hand plot， whatever have we got here， we've got a plot against x， single variable x。



![](img/0606947fe9f72434f22ee1d7ced83186_69.png)

And in the vertical axis， what we've got is actually pi sub K。



![](img/0606947fe9f72434f22ee1d7ced83186_71.png)

And multiplied by f sub K of x。

![](img/0606947fe9f72434f22ee1d7ced83186_73.png)

For both classes， K equals 1 and K equals 2。

![](img/0606947fe9f72434f22ee1d7ced83186_75.png)

Now， in this case。So remember， in the previous slide。

 the probability was essentially proportional to pi sub K times f sub K of x。



![](img/0606947fe9f72434f22ee1d7ced83186_77.png)

![](img/0606947fe9f72434f22ee1d7ced83186_78.png)

And in this case， the， the pis are the same for both。

 So it's really to do with which density is the highest。



![](img/0606947fe9f72434f22ee1d7ced83186_80.png)

![](img/0606947fe9f72434f22ee1d7ced83186_81.png)

And you can see that。The decision boundary of the vertical dash line is at 0。

 And that's a point at which the green density is higher than the purple density。



![](img/0606947fe9f72434f22ee1d7ced83186_83.png)

![](img/0606947fe9f72434f22ee1d7ced83186_84.png)

And so anything to the left or0， we classify as green。



![](img/0606947fe9f72434f22ee1d7ced83186_86.png)

And anything to the right would classify as， as purple。



![](img/0606947fe9f72434f22ee1d7ced83186_88.png)

Okay， and it sort of makes sense that that's what we do there。



![](img/0606947fe9f72434f22ee1d7ced83186_90.png)

The right end plot has different prize。

![](img/0606947fe9f72434f22ee1d7ced83186_92.png)

So you。The probability of 2 is 07 and， and of， of 1 is 03。



![](img/0606947fe9f72434f22ee1d7ced83186_94.png)

And now again， we've multiple， we plot in pi sub K。



![](img/0606947fe9f72434f22ee1d7ced83186_96.png)

Times f sub K of x。

![](img/0606947fe9f72434f22ee1d7ced83186_98.png)

Against x。And that bigger p as， has bumped up the purple。

 And what is done is move the decision boundary slightly to the left。



![](img/0606947fe9f72434f22ee1d7ced83186_100.png)

![](img/0606947fe9f72434f22ee1d7ced83186_101.png)

And that makes sense， too， again， it's where they intersect。It makes sense as well。

 because we've got more， we've got more purples here。 Actually， I say they pinks。

 It looks purple to me。

![](img/0606947fe9f72434f22ee1d7ced83186_103.png)

![](img/0606947fe9f72434f22ee1d7ced83186_104.png)

There's more of them。 So everything else being equal。 we're going to make less mistakes if we。

 if we classify it to， to， to purples and to， to greens。



![](img/0606947fe9f72434f22ee1d7ced83186_106.png)

![](img/0606947fe9f72434f22ee1d7ced83186_107.png)

Okay， so that's the rope。 that's how these， these p and。

 and the densities play a role in classification。

![](img/0606947fe9f72434f22ee1d7ced83186_109.png)

Okay， so， so why discriminant analysis， It seemed like logistic regression was a pretty good tool。

 Well， it is， but it turns out there's a room for discriminant analysis as well。



![](img/0606947fe9f72434f22ee1d7ced83186_111.png)

![](img/0606947fe9f72434f22ee1d7ced83186_112.png)

And so。

![](img/0606947fe9f72434f22ee1d7ced83186_114.png)

There's three points we make up when the classes are well separated。

It turns out that the parameter estimates for logistic regression。A surprisingly unstable。 In fact。

 if you've got a feature that separates the classes perfectly， the coefficients。



![](img/0606947fe9f72434f22ee1d7ced83186_116.png)

![](img/0606947fe9f72434f22ee1d7ced83186_117.png)

Go off to infinity。So it really doesn't do well there。



![](img/0606947fe9f72434f22ee1d7ced83186_119.png)

The just regression was developed in in in the largely in the biological and medical fields。

 where you never found such strong predictors。

![](img/0606947fe9f72434f22ee1d7ced83186_121.png)

![](img/0606947fe9f72434f22ee1d7ced83186_122.png)

Now， you can do things to， to， to make logistic regression better behave。

 But it turns out linear discriminment analysis doesn't suffer from this problem and is better behaved in those situations。



![](img/0606947fe9f72434f22ee1d7ced83186_124.png)

![](img/0606947fe9f72434f22ee1d7ced83186_125.png)

Also， if n is small， the sample size is small。

![](img/0606947fe9f72434f22ee1d7ced83186_127.png)

And the distribution of the predictors's X is approximately normal in in each of the classes。

 It turns out the linear regression discriminant model is again more stable than logistic regression。



![](img/0606947fe9f72434f22ee1d7ced83186_129.png)

And finally， if we've got more than two classes， we'll see logistic regression gives us nice low dimensional views of the data。

 And the other point， remember， in the very first section， we show that the Bays rule。

 if you have the right population model， the Bays rule is the best you can possibly do。



![](img/0606947fe9f72434f22ee1d7ced83186_131.png)

![](img/0606947fe9f72434f22ee1d7ced83186_132.png)

So if our normal assumption is right here， then then this Bay rule from Sc analysis from the Bay rule is the best you can possibly do。

 good point drum。

![](img/0606947fe9f72434f22ee1d7ced83186_134.png)

![](img/0606947fe9f72434f22ee1d7ced83186_135.png)