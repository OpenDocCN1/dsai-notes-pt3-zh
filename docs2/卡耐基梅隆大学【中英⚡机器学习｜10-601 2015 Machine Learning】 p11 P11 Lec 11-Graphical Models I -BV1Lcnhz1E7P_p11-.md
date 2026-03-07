# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p11 P11 Lec 11-Graphical Models I -BV1Lcnhz1E7P_p11-

Let's start up today。 I want to take about 10 minutes at the beginning to talk about bias andvari。

 and then。Spend the rest of the lecture。Beginning our coverage of graphical models and base nets。

So the reason I want to start though， with bias invari is it's a term that we've kind of used throughout the semester。

 but we haven't really talked about it in any。In quite a precise way， and I want to do that。

 the reason I want to do it at this point in the course is that it fits right in with the last three lectures。

So if you think about。If you translate into simple English statements。

 some of the things we've learned。From the last three lectures on computational learning theory。

You see that we learn things like there is a fundamental relation which we can characterize quantitatively。

Between。The complexity of a set of hypotheses that the learner is considering。And in fact。

 we talked about three ways of talking， of characterizing the complexity of those hypotheses。 First。

 we talked about just how many distinct hypotheses are there。Then we talked about the VC dimension。

Then we talked about the Raammaer complexity。But there are all ways of characterizing how complex the set of hypotheses is that a learner is using is considering。

And so what kind of the fundamental thing that we learned from the last three lectures is that there is a fundamental。

Constraint that any learning system， including your brain and mind。

Must abide by that relates the complexity of that hypothesis space。

To the number of training examples seen。And the probability they are given that many training examples。

Drawn randomly from。P of x。That we will succeed in learning a hypothesis whose true error。

Can be bounded by its error over the training set。That's fundamentally the question we've been talking about。

For three lectures and we looked at in different angles。And it turns out bias invariance。

Is the statistician's language for talking about quite similar notions？

And so I want to just go through that。So some of you， let me ask。Before I put that slide up。

 how many people could have written down the definition of statistical bias？Okay， good。

 so it's good that we're covering this。Here's the。Statisticians definition。Of bias and variance。

So suppose we have some parameter we're trying to estimate like， oh。

 we can go back to our old example of a coin flip and we're trying to estimate the parameter that defines the probability。

That is。Bernoulli variable， the outcome of a coin flip。Will turn out to be heads。

That could be an example。 So given that we have some parameter theta we're trying to estimate。

 and given that we have some algorithm。That。Comes up with an estimate。For that。

 I'll call the estimate theta half。Then the bias of that algorithm or that estimator。

Is defined simply as the difference between the expected value of that estimate。If we were。

The expected value of that estimate and the true value of theta。So for example。

 if I say my estimator given a coin and I want to estimate theta probability of heads。

 if I say my estimator is that I'm going to flip this coin exactly six times。

Count the number of heads， count the number of tails。And estimate。

This will be our maximum likelihood estimate。Estimate theta as simply the count of total number of heads out of 6。

Over the sum of heads and tails that， of course， be6， in our case。Then I could say， well。

 this is my estimator， it's this algorithm that I'm using flipping six times。

And then counting the fraction of heads， that'll be my estimate。For theta。Then。

What bias is defined as is the difference between the true value of theta， suppose， for example。

That theta in fact， equals 0。5。It's the difference between the true value of theta and the expected outcome of that random。

Estimator。I say random estimator。If I define my estimator as going。

 it's the algorithm where I'm going to flip the coin exactly six times。

And then count the fraction of heads。 And that's going to be my estimate。 Then， of course。

 that estimate itself is a random variable。 If I run that experiment over and over。

 each time flipping six times。I could get sometimes three out of three， four out of six。

 two out of six。And。But it's expected value。Averd over many， many such attempts。嗯。

It turns out in the case of this estimator。The expected value。Is exactly theta。

You can prove that we're not going to here today。 It's a good thing to prove to yourself。

It's not a difficult proof。But because of that。We， we'd say that for。This estimator。

Of the Bernoulli variable theta。The bias， the difference between its expected outcome and the true value is 0。

It's zero for this guy。Because the expected value of this estimate is， in fact， theta。Now。

 that's the definition of bias。 varianceance refers to if I run that experiment many times。

What will be the variance， how much will the outcome of the experiment？

The outcome of the draw of this random variable。Vary about its expected value。

And that's what the definition of variance is saying。 Here's the expected value。Of the。Estimate。

 if I were to flip the coin six times， many， many different times。

 the expected value I've already told you is theta in the case of this estimator。But in general。

 for some other estimator， like maybe the map estimator might not be theta。

But the variance is defined simply as how much。On average。

Or what's the expected variance difference between the outcome of the experiment and its expected value？

Okay， so for。For my estimator， which is the MLE estimate。The expected value of theta。Hat。Mmi Lee。

It's datata。And so the bias is zero。And so， then。The ver。The variance becomes then。嗯。So。

 the variance for。Theta MLE。Just becomes。The expected difference between。Its outcome on any。

Give an example。And its expected value， which we just agreed is the。Squared， thank you。

Harder to save than you think。Squared。Okay， so that's the definition of bias invariance。嗯。

It turns out you can also prove that for Theta M LE。The variance is equal to this。

 where these thetas are the true value of theta。But the expected difference。

Squared between our estimate and a true value。Or more generally the estimate and its expected value。

嗯。For Bernoulli variable， Bernoulli theta is that。And so n here。

 what's n n is the number of coin flips I'm doing。So this is。I'll just say。Number of coin flips。

And so this is kind of interesting。 This puts quantitatively。

 what we already have as an intuition in our head that if you want a reliable estimate of theta。😊。

That is an estimate that's going to be very close to its true value。

