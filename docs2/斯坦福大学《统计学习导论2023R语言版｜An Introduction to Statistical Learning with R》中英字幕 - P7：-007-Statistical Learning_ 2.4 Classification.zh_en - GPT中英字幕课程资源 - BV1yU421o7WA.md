# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P7：-007-Statistical Learning_ 2.4 Classification.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Okay， up to now we've talked about estimating regression functions for quantitative response and we see how to do model selection there now we're going to move to classification problems and here we've got a different kind of response variable it's what we call a qualitative variable for example email is one of two classes spam or ham spa Ham being the good email。



![](img/d440f05256ea0c8f0ca076818f8ba20f_1.png)

And if we classify in digits， it's one of the classes 0， one through up to nine。

And so it's a slightly different problem， and our goals are slightly different as well。😊。

And here our goals are to build classifier， which we might call CO of X。

That assigns a class label from our set C to an future unlabeled observation X。

 wheres x is a feature vector。We'd also like to assess the uncertainty in each classification。

 and we'd also like to understand the roles of the different predictors amongst the X's in producing that classifier。

And so we are going to see how we do that in the next number of slides。O。

 to try and parallel our development for the quantitative response。

 I've made up a little simulation example。

![](img/d440f05256ea0c8f0ca076818f8ba20f_3.png)

And we've got1 x，1， y， the y takes on two values。 In this example。

 the values are just coded as 0 and 1。And we've got a big sample of these wivess from a population。

So yeah， each little vertical bar here indicates。In an occurrence of a 0。

The the orange vertical bars as a function of the x's。And at the at the top。

 we've got where the the ones occurred， okay。So this scatter plot is much harder to read。

 you can't really see what's going on。And there's a black curve drawn in the figure。



![](img/d440f05256ea0c8f0ca076818f8ba20f_5.png)

And the black curve was what actually generated the data。

The black curve is actually showing us the probability of a one in the model that I use to generate the data。

And。You know， so so up in this region over year， the high values of x。

 there's a higher probability over1。It's close to 90% of getting a one。

 and so of course we see more blue ones there than we see zeros down there。

And even though it's hard to see， there's a higher density of zeros in this region over year where the probil is。

Is 。4 of being a1 versus versus is 0。 It's 06， okay。So。

We want to talk about what is an ideal classifier C of X。Okay。

 so let's define these probabilities that I was talking about。And we'll call p sub k of x。😡。

This quantity over year， that's a conditional probability。That y is K given x equals x。In this case。

 we've， we just looking at probability of one in the plot。

 We've just shown the probability that y is1 is only two classes， but in general， there'll be， say。

 capital K classes。And there'll be capital K of these conditional probabilities。



![](img/d440f05256ea0c8f0ca076818f8ba20f_7.png)

Now。In classification problems， those conditional probabilities。



![](img/d440f05256ea0c8f0ca076818f8ba20f_9.png)

Completely capture the distribution， the conditional distribution of Y given x， okay。



![](img/d440f05256ea0c8f0ca076818f8ba20f_11.png)

And it turns out that those also deliver the ideal classifier。We call the Bays optimal classifier。

The classifier that classifies to the class for which the conditional probability。

For that element of the class is， is largest。That makes sense。You go to any point。

 So here we've gone to a 0。5。InIn the X space。And you look above it and you see that this。

About 80% probability of the one。And 20% probability of a 0。And now we're going to say， well。

 if you were to classify to one class at that point， which class would you classify to。

 will you going to classify to the majority class？Okay， that's called the Bays optimal classifier。



![](img/d440f05256ea0c8f0ca076818f8ba20f_13.png)

Here's the same example。Except now we've only got a handful of points。 We've got 100 points。Yeah。

Having one one of the two class labels。The story is the same as before。

We can't compute the conditional probabilities exactly， say at the 0。5。

 because in this case we may have one， we have got one1 at5 and no zeros。



![](img/d440f05256ea0c8f0ca076818f8ba20f_15.png)

So we send out a neighborhood， say and gather 10% of the data points and then estimate the conditional probabilities by the proportions in this case of ones and zeros in the neighborhood。

And。Those are indicated by these little bars here， these are meant to represent the probabilities or proportions at this 0。

5。 and again， there's a higher proportion of one0 than zeros。

 I forgot to say that in the previous slide that's the same quantity over year that's indicating the probabilities of the ones and the zeros。

 This is exact in the population and it is estimated with the nearest neighbor average。



![](img/d440f05256ea0c8f0ca076818f8ba20f_17.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_18.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_19.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_20.png)

So here we've done the nearest neighbor classifying in one dimension we can draw a nice picture。

 but of course this works in multiple dimensions as well， just like it did for regression。

 So suppose we， for example， have two x's and they placed in they lie in the floor and we have a target point say this point over yeah and we want to classify a new observation who falls at this point well we can spread out a little say circular neighborhood and gather a bunch of observations who fall in this neighborhood and we can count how many in class1。

 how many in class2 and assign to the majority class and of course this can be generalized to multiple dimensions。



![](img/d440f05256ea0c8f0ca076818f8ba20f_22.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_23.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_24.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_25.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_26.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_27.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_28.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_29.png)

Then all the problems we had with nearest neighbors for regression。

 the cursor dimensionality when the number of dimensions get large also happens here。

 in order to gather enough points when the dimensions really high。

 we have to send out a bigger and bigger sphere to capture the points and things start to break down because it's not local anymore。



![](img/d440f05256ea0c8f0ca076818f8ba20f_31.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_32.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_33.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_34.png)

So some details typically will measure the performance of the classifier using what we call the misclassification error rate。

And year it's written on the test data set， the error is just the average mistakes。

 number of mistakes we make。Okay， so it's average number of times that。The classification。

 so C hat at a point X I is not equal to the class label。 Y I averaged over a test set。

It's just the number of mistakes。So that's when we count mistake in a one for a0 and a0 for a one as equal。

There are other ways of classifying an error where you can have a cost which gives higher cost to some mistakes than others。

 but we won't go into that here。So that base classifier。



![](img/d440f05256ea0c8f0ca076818f8ba20f_36.png)

The one that used the true probabilities to decide on the classification rule。

Is the one that makes the least mistakes in the population。



![](img/d440f05256ea0c8f0ca076818f8ba20f_38.png)

And that makes sense if if you look at our population example over year。

 by classifying to one over year， we're going to make mistakes on about 20% of the population of the conditional population at this value of x。

 but we'll get it correct， 80% of the time。

![](img/d440f05256ea0c8f0ca076818f8ba20f_40.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_41.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_42.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_43.png)

And so that's why it's obvious we want to classify to the largest class。

 well make the fewest mistakes。

![](img/d440f05256ea0c8f0ca076818f8ba20f_45.png)

Later on， in the course， we're going to talk about support vector machines。

 and they build structured models for the classify C of X。

And we also both structured models for representing the probabilities themselves。

 and there we discuss methods like logistic regression and generalized additive models。嗯。

The high dimensional problem is。Worse for。For modeling the probabilities than it is for actually building the classifier。

 for the classifier， you just have to， the classifier just has to be accurate with regard to which of the probabilities is largest。

 whereasas if we really interested in the probabilities themselves。

 we're going be measuring them on a much finer scale。



![](img/d440f05256ea0c8f0ca076818f8ba20f_47.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_48.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_49.png)

Okay， we'll end up with a two dimensional example of nearest neighbors。

So this is that represents the truth。We've got an X1 and an x2。

 and we've got a points from some population。And the purple dotted line is what's called the Bays decision boundary。

 since we know the truth here we know what the true probabilities are everywhere in this domain。

 and I've sort of indicated all the points in the domain by the little dots in the figure。

And so if you classify according to the true probabilities。All the points。

 all the region colored orange would be classified as the one class。

And all the region colored blue would be classified as the， as the blue course。

 And the dotted lines called the decision boundary。 And so that's a contour of the place where。

 in this case， there are two classes。 It's a contour of where the probabilities are equal for the two classes。

 So it's the undecided region called the decision boundary。Okay。

 so we can do nearest neighbor aaging in two dimensions。So of course。

 what we do here is at any given point when we want to classify。

Let's say we picked this point over here。 We'll spread out a little。



![](img/d440f05256ea0c8f0ca076818f8ba20f_51.png)

Neighborhood， in this case， until we find the 10 closest points to the target point。



![](img/d440f05256ea0c8f0ca076818f8ba20f_53.png)

And we'll estimate the probability at this center point here by the proportion of blues versus oranges。

And you do that at every point。And if you use those as the probabilities。

 you get this somewhat wly black curve as the estimated decision boundary。

And you can see it's actually apart from the somewhat ugly wigglyss。

It gets reasonably close to the true decision boundary， which is the， again， the purple dashed line。

Or curve。

![](img/d440f05256ea0c8f0ca076818f8ba20f_55.png)

Okay in the last slide we used k equals 10， we can use other values of k of k k equals 1 is a popular choice。

 this is called the nearest neighbor classifier， and we take literally for each at each target point we find the closest point amongst the training data and classifier to its class。

😊，Okay， so， for example， if we took a point over year， which is the closest training point。 Well。

 this is it over here。 It's a blue。 So we'd classify this as blue。

Right when you're in the sea of blues， of course they always the nearest point is always another blue。

 and so you'd always classify as blue。😊，What's interesting is as you get close to some of the orange points。

And what this gives you， you can see the boundary here is。Is a piecewise linear boundary。 Of course。

 the probabilities we estimate is just  one and 0。 because there's only one point to average。

 So there's no real probabilities。 But if you think about the decision boundary。

 it's a piecewise linear decision boundary。And it's gotten by looking at the bisector of of the line joining separating each pair of points when they have different colors。

So you get this very。Ragged decision boundary。 You also get little islands。 So， for example。

 there's a blue point in the sea of oranges here。 So there's a little piecewise linear boundary around that blue point。

 Those are the points。The points that are closest to that blue point。

 closer to the blue point than the oranges。Again， we see the true boundary or the best base decision boundary is purple。

This nearest neighbor average。😊，kind of approximates it in a noisy way。On the other end。

 you can make K really large。Yeah we've made K 100。And the neighborhood's really large。 It's， it's。

 it's essentially it's 200 points here。 So it's taking half the points to be in any given neighborhood。

 right， So let's suppose。Our test point was over year。 you know。

 we'd be sending out quite a big circle。Gathering 100 points， getting the proportion of blues。

 a proportion of oranges and then making the boundary。 So as K gets bigger。

 this boundary starts smoothing outing and getting less interesting。 In this case。

 it's almost like a linear boundary over year and doesn't pick up the nuances of the of the decision boundary。

Whereas with K equals 10， it seemed like a pretty good choice and it kind of approximates the decision boundary pretty well。

Okay， so the choice of k is a tuning parameter and that needs to be selected and here we show what happens as you vary k first on the training data and then on the test data so on the training data。



![](img/d440f05256ea0c8f0ca076818f8ba20f_57.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_58.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_59.png)

K tends to just keep on decreasing。 It's not actually monotone because we've actually indexed this as one over K。

 because。

![](img/d440f05256ea0c8f0ca076818f8ba20f_61.png)

As as1 over k gets big。

![](img/d440f05256ea0c8f0ca076818f8ba20f_63.png)

Let's see。 K large means we get high bias。 So one of a K is small。

 So this is the low complexity region。 This is the high complexity region。



![](img/d440f05256ea0c8f0ca076818f8ba20f_65.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_66.png)

Now， you notice that the training error for one nearest neighbours。

 which is right down at the end here。

![](img/d440f05256ea0c8f0ca076818f8ba20f_68.png)

1 over k is1 is0。

![](img/d440f05256ea0c8f0ca076818f8ba20f_70.png)

Well， if you think about it， that's what it's going to be。

 If you think about what training error is for the test error。

 it's actually started increasing again。

![](img/d440f05256ea0c8f0ca076818f8ba20f_72.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_73.png)

This horizontal dotted line is， is， is the bays error， which is。



![](img/d440f05256ea0c8f0ca076818f8ba20f_75.png)

You can't do better than the Bayes era in theory。Of course， this is a finite test data set。

 but it doesn't。 It actually just touches on the bays area， it starts decreasing。

 and then at some point it levels off and then starts increasing again。



![](img/d440f05256ea0c8f0ca076818f8ba20f_77.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_78.png)

So if we had a validation set available， that's what we'd use to determine K。



![](img/d440f05256ea0c8f0ca076818f8ba20f_80.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_81.png)

So that's nearest neighbor classification， very powerful tool。

 It said that about one third of classification problems。

 the best tool will be nearest neighbor classification。😊。



![](img/d440f05256ea0c8f0ca076818f8ba20f_83.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_84.png)

On the handwritten zip code problem， the classifying handwritten digits nearest neighbor classifierifies do that as well as any other method trade。



![](img/d440f05256ea0c8f0ca076818f8ba20f_86.png)

So it's a powerful technique to have in the tool bag and it's one of the techniques that we'll use for classification。

 but in the rest of the course well cover other techniques as well。

 in particular there's support vector machines， various forms of logistic regression and linear discriminant analysis。



![](img/d440f05256ea0c8f0ca076818f8ba20f_88.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_89.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_90.png)

![](img/d440f05256ea0c8f0ca076818f8ba20f_91.png)