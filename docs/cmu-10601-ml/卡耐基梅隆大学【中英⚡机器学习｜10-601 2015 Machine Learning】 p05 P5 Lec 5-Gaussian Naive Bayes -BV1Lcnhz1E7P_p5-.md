# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p05 P5 Lec 5-Gaussian Naive Bayes -BV1Lcnhz1E7P_p5-

You recognize that some of those questions track very closely the material in the lectures。

 we really do want you to understand maximum likelihood estimation and map estimation it's going to be very helpful for the whole rest of this semester。

Also， I guess I want to say that。I think you all know by now that videos of the lectures are available on the class website。

 we've also recently put some readings。Uppon if you go to the lecture schedule。

Page on our class website。You'll see not only links to the videos， but also links to some readings。

One of the required readings for the coming week is up there， so please take a look at that。嗯。

So so far， really what we've done is look at Bay classifiers that is， how can we？

Instead of learning some deterministic function to predict y from x。

 learn the probabilistic function that maps from x to y or P of y given x。

And we've talked in detail about maximum likelihood and map estimation。

Last time we brought up conditional independence， why。

 because conditional independence gives us if we're willing to make that assumption。

Gives us a way to exponentially reduce the number of probability parameters that we have to learn from our training data。

In order to。Create what we were calling a naive base classifier， which is a way of。

Of predicting P of Y given x for any given x。So conditional independence was one of our key ideas。

For。Reducing the number of parameters we have to estimate from training data and therefore making it even feasible to us to learn probabilistic。

Functions like P of Y given X。Remember before， when we tried to just make no assumptions。

 we noticed that。If we're trying to even estimate a joint distribution with。

I guess we decided 30 or more Boolean X's， we'd need a billion probability parameters and there weren't。

Enough people on earth to populate our joint distribution for 100 features， for example。

So it really is an issue， not just in terms of computational efficiency。

 but in terms of what we call sample complexity， that is。

 how much training data do we need in order to reliably estimate or learn these parameters。😊，嗯。

So that was the point of naive base， what we're going to do。

Today is look a little bit more at naive Base and at text classification using naive Base in the upcoming homework which will be out today。

 you'll get a chance to look at that in some detail。

 we're also going to look at the question of what if our attributes are not discrete valued。

What if they're not boolean， what if they're continuous， like the temperature？

Then what will it take to turn naive base into something that we can use for continuous attributes？

Next lecture we'll move on to some really closely related ideas。

 there's a very widely used algorithm called logistic regression which has a kind of beautiful correspondence to naive Bayes and so next time we'll be looking at that so there's kind of a preview of what's coming up。

But I want to start with。We've seen this。 naiveve Bayes in a nutshell。 Well， maybe it's worth saying。

 Naive Bay in a nutshell just starts with Baye's rule that tells us， given any particular。

Example described by our x's， what is the probability that y will take on any given value？

Based on Baye's rule。And of course， the conditional independence assumption in naive Base tells us that we can replace this joint distribution。

By。No， don't do it。Who knows？By this thing。By the product of the individual probabilities of the F sub I's。

 because we're assuming they are conditionally independent given y。And so， for example。

 if we want to just classify some new example that wasn't part of our training data and we don't know the why。

 then all we have to do is calculate the probability that y equals1 and y equals zero。And then。

 assign。The y label that maximizes that probability。And if you look at this。

 you'll notice that this denominator。Really iss just。嗯。A constant， independent of the YK。

This denominator is actually summing over all the possible values of why。In fact。

 it's equal that denominator is equal to just p of Xi。

Because we're summing over all the possible values of why。So in a sense。

 if we want to maximize the probability， all we really have to worry about is the numerator。

And so we can just assign the Y， which maximizes de numerator。And so that's the key。To naive。

 That's naive face in a nutshell。So last time we trained a。Fortunately successful。

 eight out of10 times on our test examples who are sitting in this aisle row of the class。m but we。

And you saw the details on how we trained that。But we didn't get a chance in class to go through how the details of how we would classify a new example。

 So I just want to start by quickly doing that where I volunteer to be the test example。Okay。

 so it turns out if we want to predict whether I live in Sirrel Hill， I'm not telling you。嗯。

Until later。But I will tell you that my value is D。 Yes， I did drive， in fact， today to CM MU。嗯。G。

 no， I have not shopped at the Sirrel Hill giant Eaglele since September。And B， yes， no。

 my birthday is not before July 1s。so I'm a new test example。

 obviously I was not part of the training data。And so， if we want to。

Predict what's the probability given those features。That S equals one。

 that is that this example does live in Sirrel Hill。Then what I've done here is just written。

 written out the ratio， the Bayes rule。Right， remember。I've just written out。This。

So the probability that squirrel Hill equals one， given my features is just probability the prior probability that squirrel Hill equals one times each of the individual conditional probabilities over this denominator。

Okay so Fu。Do that here。 you see that's exactly what I've got。 here's the prior。

 the squirrel hill equals one times each of the conditional probabilities。

Under the assumption that S equals1。And then the numerator is that very same quantity。Right， this。

Is identical to this。Plus， that same quantity， but now assuming that s equals 0 instead of s equals 1。

诶。So that's exactly what。We said。If we make the conditional independence assumption and apply based as the rule。

 this is exactly what weve said will give us the probability that S equals one given these values。

So from the training data， you can see here that， in fact。

 we have calculated everything that we need， every one of these terms。

Is available from the training that we did last class。And so， for example， what's P of S equals1。

Well， that's just 26 over 102。The probability that d equals1， given s equals1。

That's just three over 26 and so forth。Okay， so I could go through and do all these。

 Let's do one more。 the probability that G equals0 given S equals1。Oh， well， that's zero。

And then there are a bunch of other terms that you could fill in easily。O。

