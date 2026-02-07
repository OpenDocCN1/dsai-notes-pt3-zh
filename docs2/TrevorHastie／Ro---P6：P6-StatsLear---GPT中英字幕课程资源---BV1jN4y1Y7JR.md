# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P6：P6 StatsLearning Lect3 4d 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， up to now we've talked about estimating regression functions for quantitative response and we've seen how to do model selection there。

 now we're going to move to classification problems and yeah we've got a different kind of response variable it's what we call a qualitative variable for example。

 email is one of two classes spam or ham ham being the good email。



![](img/383e5b1819e17c2205241f3321be146c_1.png)

![](img/383e5b1819e17c2205241f3321be146c_2.png)

![](img/383e5b1819e17c2205241f3321be146c_3.png)

![](img/383e5b1819e17c2205241f3321be146c_4.png)

![](img/383e5b1819e17c2205241f3321be146c_5.png)

And if we classify in digits， it's one of the classes 0， one through up to nine。



![](img/383e5b1819e17c2205241f3321be146c_7.png)

And it says it's a slightly different problem， and our goals are slightly different as well。😊。



![](img/383e5b1819e17c2205241f3321be146c_9.png)

And here our goals are to build classify， which we might call CO of X。



![](img/383e5b1819e17c2205241f3321be146c_11.png)

That assigns a class label from our set C to an future unlabeled observation X。

 where is x is the feature vector。

![](img/383e5b1819e17c2205241f3321be146c_13.png)

![](img/383e5b1819e17c2205241f3321be146c_14.png)

We'd also like to assess the uncertainty in each classification。



![](img/383e5b1819e17c2205241f3321be146c_16.png)

And we'd also like to understand the roles of the different predictors amongst the X's in producing that testifier。



![](img/383e5b1819e17c2205241f3321be146c_18.png)

![](img/383e5b1819e17c2205241f3321be146c_19.png)

And so we are going to see how we do that in the next number of slides。



![](img/383e5b1819e17c2205241f3321be146c_21.png)

Okay， to try and parallel our development for the quantitative response。

 I've made up a little simulation example。

![](img/383e5b1819e17c2205241f3321be146c_23.png)

![](img/383e5b1819e17c2205241f3321be146c_24.png)

And we've got 1 x，1 y， the y takes on two values in this example， the values are justd as0 and 1。



![](img/383e5b1819e17c2205241f3321be146c_26.png)

![](img/383e5b1819e17c2205241f3321be146c_27.png)

And we've got a big sample of these wises from a population。So yeah。

 each little vertical bar here indicates。

![](img/383e5b1819e17c2205241f3321be146c_29.png)

In an occurrence of a0。

![](img/383e5b1819e17c2205241f3321be146c_31.png)

The the orange vertical bars as a function of the x's。



![](img/383e5b1819e17c2205241f3321be146c_33.png)

And at the top， we've got where the ones occurred， okay。



![](img/383e5b1819e17c2205241f3321be146c_35.png)

So this scatterlo is much harder to read， you can't really see what's going on。



![](img/383e5b1819e17c2205241f3321be146c_37.png)

And there's a black curve drawn in the figure。

![](img/383e5b1819e17c2205241f3321be146c_39.png)

And the black curve was what actually generated the data。



![](img/383e5b1819e17c2205241f3321be146c_41.png)

The black curve is actually showing us the probability of a one in the model that I use to generate the data。



![](img/383e5b1819e17c2205241f3321be146c_43.png)

And。know so up in this region over year， the high values of x， there's a higher probability over1。



![](img/383e5b1819e17c2205241f3321be146c_45.png)

![](img/383e5b1819e17c2205241f3321be146c_46.png)

![](img/383e5b1819e17c2205241f3321be146c_47.png)

It's close to codes 90% of getting a one。 And so， of course。

 we see more blue ones there than we'd see zeros down there。



![](img/383e5b1819e17c2205241f3321be146c_49.png)

And even though it's hard to see， there's a higher density of zeros in this region over year where the probabilities。



![](img/383e5b1819e17c2205241f3321be146c_51.png)

![](img/383e5b1819e17c2205241f3321be146c_52.png)

Is 。4 of being a1 versus versus is 0。 It's 06， okay。



![](img/383e5b1819e17c2205241f3321be146c_54.png)

![](img/383e5b1819e17c2205241f3321be146c_55.png)

So。We want to talk about what is an ideal classifier C of X。



![](img/383e5b1819e17c2205241f3321be146c_57.png)

Okay， so let's define these probabilities that I was talking about。



![](img/383e5b1819e17c2205241f3321be146c_59.png)

And we'll call p sub K of x。😡。

![](img/383e5b1819e17c2205241f3321be146c_61.png)

This quantity over year， that's a conditional probability。



![](img/383e5b1819e17c2205241f3321be146c_63.png)

That y is K given x equals x。In this case， we're just looking at probability of one in the plot。

 we've just shown the probability that y is1 is only two classes， but in general， there'll be。

 say capital K classes。

![](img/383e5b1819e17c2205241f3321be146c_65.png)

![](img/383e5b1819e17c2205241f3321be146c_66.png)

![](img/383e5b1819e17c2205241f3321be146c_67.png)

And there'll be capital K of these conditional probabilities。



![](img/383e5b1819e17c2205241f3321be146c_69.png)

Now。In classification problems， those conditional probabilities。



![](img/383e5b1819e17c2205241f3321be146c_71.png)

Completely capture the distribution， the conditional distribution of Y given x， okay。



![](img/383e5b1819e17c2205241f3321be146c_73.png)

And it turns out that those also deliver the ideal classifier。



![](img/383e5b1819e17c2205241f3321be146c_75.png)

![](img/383e5b1819e17c2205241f3321be146c_76.png)

We call the Bays optimal classifier。The classifier that classifies to the class for which the conditional probability。



![](img/383e5b1819e17c2205241f3321be146c_78.png)

For that element of the class is is largest。

![](img/383e5b1819e17c2205241f3321be146c_80.png)

That makes sense。

![](img/383e5b1819e17c2205241f3321be146c_82.png)

You go to any point。 so here we've gone to a 0。5。In the X space。



![](img/383e5b1819e17c2205241f3321be146c_84.png)

And you look above it and you see that this。

![](img/383e5b1819e17c2205241f3321be146c_86.png)

About 80% probability of the one。

![](img/383e5b1819e17c2205241f3321be146c_88.png)

And 20% probability of a 0。And now we're going to say， well。

 if you were to classify to one class at that point， which class would you classify to。

 well you going to classify to the majority class？

![](img/383e5b1819e17c2205241f3321be146c_90.png)

![](img/383e5b1819e17c2205241f3321be146c_91.png)

Okay， that's called the Bays optimal classifier。

![](img/383e5b1819e17c2205241f3321be146c_93.png)

Here's the same example。

![](img/383e5b1819e17c2205241f3321be146c_95.png)

Except now we've only got a handful of points。 We've got 100 points。嗯。



![](img/383e5b1819e17c2205241f3321be146c_97.png)

Having one one of the two class labels。The story is the same as before。



![](img/383e5b1819e17c2205241f3321be146c_99.png)

We can't compute the conditional probabilities exactly， say at 0 0。5。

 because in this case we we have got one1 at five and no zeros。



![](img/383e5b1819e17c2205241f3321be146c_101.png)

![](img/383e5b1819e17c2205241f3321be146c_102.png)

So we send out a neighborhood， say and gather 10% of the data points and then estimate the conditional probabilities by the proportions in this case of ones and zeros in the neighborhood。



![](img/383e5b1819e17c2205241f3321be146c_104.png)

![](img/383e5b1819e17c2205241f3321be146c_105.png)

![](img/383e5b1819e17c2205241f3321be146c_106.png)

And。Those are indicated by these little bars here these are meant to represent the probabilities or proportions at this 0。

5。 and again， there's a higher proportion of one zero than zeros。



![](img/383e5b1819e17c2205241f3321be146c_108.png)

![](img/383e5b1819e17c2205241f3321be146c_109.png)

I forgot to say that in the previous slide that's the same quantity over year。

 that's indicating the probabilities of the ones and the zeros。

 This is exact in the population and it is estimated with the nearest neighbor average。



![](img/383e5b1819e17c2205241f3321be146c_111.png)

![](img/383e5b1819e17c2205241f3321be146c_112.png)

![](img/383e5b1819e17c2205241f3321be146c_113.png)

So here we've done the nearest neighbor classifying in one dimension and we can draw a nice picture but of course this works in multiple dimensions as well。

 just like it did for regression so suppose we， for example。

 have two x's and they placed in they lie in the floor and we have a target point say this point over yeah and we want to classify a new observation it falls at this point well we can spread out a little say circular neighborhood and gather a bunch of observations who fall in this neighborhood and we can count how many in class1 how many in class two and assign to the majority class and of course this can be generalized to multiple dimensions。



![](img/383e5b1819e17c2205241f3321be146c_115.png)

![](img/383e5b1819e17c2205241f3321be146c_116.png)

![](img/383e5b1819e17c2205241f3321be146c_117.png)

![](img/383e5b1819e17c2205241f3321be146c_118.png)

![](img/383e5b1819e17c2205241f3321be146c_119.png)

![](img/383e5b1819e17c2205241f3321be146c_120.png)

![](img/383e5b1819e17c2205241f3321be146c_121.png)

![](img/383e5b1819e17c2205241f3321be146c_122.png)

![](img/383e5b1819e17c2205241f3321be146c_123.png)

Then all the problems we had with nearest neighbors for regression。

 the cursor dimensionality when the number of dimensions get large， also happens here。

 in order to gather enough points when the dimensions really high。

 we have to send out a bigger and bigger sphere to capture the points and things start to break down because it's not local anymore。



![](img/383e5b1819e17c2205241f3321be146c_125.png)

![](img/383e5b1819e17c2205241f3321be146c_126.png)

![](img/383e5b1819e17c2205241f3321be146c_127.png)

![](img/383e5b1819e17c2205241f3321be146c_128.png)

So some details typically will measure the performance of the classifier using what we call the misclassification error rate。



![](img/383e5b1819e17c2205241f3321be146c_130.png)

![](img/383e5b1819e17c2205241f3321be146c_131.png)

And here it's written on the test data set， the error is just the average mistakes。

 number of mistakes we make。

![](img/383e5b1819e17c2205241f3321be146c_133.png)

![](img/383e5b1819e17c2205241f3321be146c_134.png)

Okay， so it's average number of times that。

![](img/383e5b1819e17c2205241f3321be146c_136.png)

The classification， so C hat at a point Xi is not equal to the class label。

 Y I averaged over a test set。

![](img/383e5b1819e17c2205241f3321be146c_138.png)

![](img/383e5b1819e17c2205241f3321be146c_139.png)

It's just the number of mistakes。So that's when we count a mistake in a one for a0 and a 0 for a one as equal。



![](img/383e5b1819e17c2205241f3321be146c_141.png)

![](img/383e5b1819e17c2205241f3321be146c_142.png)

There are other ways of classifying an error where you can have a cost which gives higher cost to some mistakes than others。

 but we won't go into that here。

![](img/383e5b1819e17c2205241f3321be146c_144.png)

So that base classifier。

![](img/383e5b1819e17c2205241f3321be146c_146.png)

The one that used the true probabilities to decide on the classification rule。

Is the one that makes the least mistakes in the population。



![](img/383e5b1819e17c2205241f3321be146c_148.png)

And that makes sense if you look at our population example over year， by classifying to1 over year。

 we're going to make mistakes on about 20% of the population of the conditional population at this value of x。

 but we'll get it correct， 80% of the time。

![](img/383e5b1819e17c2205241f3321be146c_150.png)

![](img/383e5b1819e17c2205241f3321be146c_151.png)

![](img/383e5b1819e17c2205241f3321be146c_152.png)

![](img/383e5b1819e17c2205241f3321be146c_153.png)

And so that's why it's obvious we want to classify it to the largest class。

 well make the fewest mistakes。

![](img/383e5b1819e17c2205241f3321be146c_155.png)

![](img/383e5b1819e17c2205241f3321be146c_156.png)

Later on， in the course， we're going to talk about support vector machines。

 and they build structured models for the Classify C of X。



![](img/383e5b1819e17c2205241f3321be146c_158.png)

And we also built structured models for representing the probabilities themselves。

 and there we'll discuss methods like logistic regression and generalized additive models。



![](img/383e5b1819e17c2205241f3321be146c_160.png)

![](img/383e5b1819e17c2205241f3321be146c_161.png)

嗯。

![](img/383e5b1819e17c2205241f3321be146c_163.png)

The high dimensional problem is。Worse for。

![](img/383e5b1819e17c2205241f3321be146c_165.png)

For modeling the probabilities than it is for actually building the classifier for the classifier。

 you just have to， the classifier just has to be accurate with regard to which of the probabilities is largest。

 whereasas if we really interested in the probabilities themselves。

 we're going to be measuring them on a much finer scale。



![](img/383e5b1819e17c2205241f3321be146c_167.png)

![](img/383e5b1819e17c2205241f3321be146c_168.png)

![](img/383e5b1819e17c2205241f3321be146c_169.png)

Okay， we'll end up with a two dimensional example of nearest neighbors。

So this is that represents the truth。We've got an x1 and the x2。

 and we've got points from some population。And the purple dotted line is what's called the Bay's decision boundary。

 since we know the truth here we know what the true probabilities are everywhere in this domain。

 and Ive sort of indicated all the points in the domain by the little dots in the figure。

And so if you classify according to the true probabilities。All the points。

 all the region colored orange would be classified as the one class。

And all the region colored blue would be classified as the blue course and the dotted lines called the decision boundary。

 And so that's a contour of the place where in this case there are two classes。

 it's a contour of where the probabilities are equal for the two classes。

 So it's an undecided region called the decision boundary。Okay。

 so we can do nearest neighbor average and in two dimensions。So of course。

 what we do here is at any given point when we want to classify。

Let's say we picked this point over here。 We'll spread out a little。Neighborhood， in this case。

 until we find the 10 closest points to the target point。

And we'll estimate the probability at this center point here by the proportion of blues versus oranges。

And you do that at every point。And if you use those as the probabilities。

 you get this somewhat wgly black curve as the estimated decision boundary。



![](img/383e5b1819e17c2205241f3321be146c_171.png)

And you can see it's actually apart from the somewhat ugly wigglyss。

It gets reasonably close to the true decision boundary， which is the， again， the purple dashed line。



![](img/383e5b1819e17c2205241f3321be146c_173.png)

Or curve。

![](img/383e5b1819e17c2205241f3321be146c_175.png)

Okay in the last slide we used k equals 10， we can use other values of k of k k equals 1 is a popular choice。

 this is called the nearest neighbor classifier and we take literally for each at each target point we find the closest point amongst the training data and classifier to its class。

😊，Okay， so for example， if we took a point over year， which is the closest training point， Well。

 this is it over here。 it's a blue， so we'd classify this as blue。

Right when you're in the sea of blues， of course they the nearest point is always another blue。

 and so you'd always classify as blue。What's interesting is as you get close to some of the orange points。

And what this gives you， you can see the boundary here is。Is a piecewise linear boundary。 Of course。

 the probabilities we estimate is just one and 0。 because there's only one point to average。

 So there's no real probabilities。 But if you think about the decision boundary。

 it's a piecewise linear decision boundary。And it's gotten by looking at bisector of the line separating each pair of points when they have of different colors。

So you get this very。Ragged decision boundary。 You also get little islands。 So， for example。

 there's a blue point in the sea of oranges here。 So there's a little piecewise linear boundary around that blue point。

 Those are the points。The points that are closest to that blue point。

 closer to the blue point than the oranges。Again， we see the true boundary or the best base decision boundary is purple。

This nearest neighbor average。😊，Kind of approximates it in a noisy way。On the other end。

 you can make K really large。😊，Yeah， we've made K 100。And the neighborhood's really large。 It's。

 it's， it's essentially with's 200 points here。 So it's taking half the points to be in any given neighborhood。

 right， So let's suppose。Our test point was over year。 you know。

 we'd be sending out quite a big circle。Gathering 100 points， getting the proportion of blues。

 a proportion of oranges and then making the boundary。 So as K gets bigger。

 this boundary starts smoothing out and getting less interesting。 In this case。

 it's almost like a linear boundary over here and doesn't pick up the nuances of the of the decision boundary。

Whereas with k equals 10， it seemed like a pretty good choice and it kind of approximates the decision boundary pretty well。

Okay， so the choice of k is a tuning parameter and that needs to be selected and yeah we show what happens as you vary k first on the training data and then on the test data so on the training data。



![](img/383e5b1819e17c2205241f3321be146c_177.png)

![](img/383e5b1819e17c2205241f3321be146c_178.png)

![](img/383e5b1819e17c2205241f3321be146c_179.png)

K tends to just keep on decreasing。 It's not actually monotone because we've actually indexed this as one over K。

 because。

![](img/383e5b1819e17c2205241f3321be146c_181.png)

![](img/383e5b1819e17c2205241f3321be146c_182.png)

As1 over k gets big。Let's see。 K large means we get higher bias。 So one of K is small。

 So this is the low complexity region。 This is the high complexity region。



![](img/383e5b1819e17c2205241f3321be146c_184.png)

![](img/383e5b1819e17c2205241f3321be146c_185.png)

![](img/383e5b1819e17c2205241f3321be146c_186.png)

Now， you notice that the training error for one nearest neighbors。

 which is right down at the end here。

![](img/383e5b1819e17c2205241f3321be146c_188.png)

1 over k is1 is0。

![](img/383e5b1819e17c2205241f3321be146c_190.png)

Well， if you think about it， that's what it's got to be。

 If you think about what training error is for the test error。

 it's actually started increasing again。

![](img/383e5b1819e17c2205241f3321be146c_192.png)

![](img/383e5b1819e17c2205241f3321be146c_193.png)

This horizontal dotted line is， is， is the bay error， which is。



![](img/383e5b1819e17c2205241f3321be146c_195.png)

You can't do better than the Bays era in theory。Of course this is a finite test data set。

 but it doesn't it actually just touches on the Bays area。

 it starts decreasing and then at some point it levels off and then starts increasing again。



![](img/383e5b1819e17c2205241f3321be146c_197.png)

![](img/383e5b1819e17c2205241f3321be146c_198.png)

So if we had a validation set available， that's what we'd use to determine K。



![](img/383e5b1819e17c2205241f3321be146c_200.png)

![](img/383e5b1819e17c2205241f3321be146c_201.png)

So that's nearest neighbor classification， very powerful tool。

 it said that about one third of classification problems。

 the best tool will be nearest neighbor classification。😊。



![](img/383e5b1819e17c2205241f3321be146c_203.png)

![](img/383e5b1819e17c2205241f3321be146c_204.png)

On the handwritten zip code problem， the classifying 1written digits nearest neighbor classifierifies do about as well as any other method trade。



![](img/383e5b1819e17c2205241f3321be146c_206.png)

![](img/383e5b1819e17c2205241f3321be146c_207.png)

So it's a powerful technique to have in the tool bag and it's one of the techniques that we'll use for classification。

 but in the rest of the course we will cover other techniques as well。

 in particular there's support vector machines， various forms of logistic regression and linear discriminant analysis。



![](img/383e5b1819e17c2205241f3321be146c_209.png)

![](img/383e5b1819e17c2205241f3321be146c_210.png)

![](img/383e5b1819e17c2205241f3321be146c_211.png)

![](img/383e5b1819e17c2205241f3321be146c_212.png)