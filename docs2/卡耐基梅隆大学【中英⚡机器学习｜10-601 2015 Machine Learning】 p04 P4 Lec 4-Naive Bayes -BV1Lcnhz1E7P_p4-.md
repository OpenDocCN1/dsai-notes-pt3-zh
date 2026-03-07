# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p04 P4 Lec 4-Naive Bayes -BV1Lcnhz1E7P_p4-

Okay well let's get started。 first of all， thank you for coming out in the dead of winter in the blizzard。

 It's not really a blizzard come。 It's like a couple inches。

 but it's still fun and exciting to have a snowstorm so thank you for plowing through the snow to come out。

 I hope you're going to be happy you did because by the end of class today you will be a training example。

😊，And the point of today's class is to talk about our first Bayesian classifier。And before I do that。

 I just want to kind of remind you a quick review from last time。

The main point of the last lecture was really that estimating probabilities from data。

Or learning probability terms from data。I don't care whether you use the verbest or learn it's the same thing is really central to any kind of probabilistic approach to machine learning。

And there are， in fact， two。Pincipleles by which we try to estimate probability parameters from data。

 Those are maximum likelihood estimates。 one principle。

 which says that we want to choose the parameters theta。That's what we're trying to learn。

In a way that maximizes the probability of the data。Given theta。The second principle。

 which is very much like that。Says， well， actually we want to choose the theta。

 which is itself most probable given the data。And we know， by Be's rule。

That this quantity equals this quantity。 That's what Bay rule says。And if you look at this。

 you notice that， well， the denominator doesn't really depend on theta so we can ignore that。

So choosing the theta that's most probable is choosing the theta that maximizes the numerator here。

Which if you look at that numerator is just like maximum likelihood estimation。

 except that we also have a prior probability on theta。

 and so the idea of map estimation is that it gives us a chance to bring in some prior knowledge that we do have or prior assumptions that we do have about the value of theta and express them as P of theta。

Then we looked at two。We we took as a case study the problem of estimating theta for a Bernoulli。

Distribution， that is a coin flip。Where we say， well。

 we have a random variable which could turn out to be heads or tails， one or zero。And we'll just say。

Depending on the coin， there is some theta， which is the probability that that coin will turn out to be a heads。

 x equals 1。And。So we said， okay， then。Each flip of the coin yields a boolean value for x。

 If we flip it a bunch of times， we can count。The number of ones and zeros， heads and tails。

In that collection of。Independent flips， which are identically distributed。

 Idently distributed just means they're all following the same theta。 It's the same coin。

And they're independent in the sense that the outcome of one coin flip doesn't really influence the outcome of the next coin flip。

And so it was easy for us to write down an expression for the probability of the data。

If we observe alpha1 heads and alpha0 tails， then it's just。

Theta times the number of heads and one minus theta， of course。

 That's the probability that will get a tails。Times the number of observed tales。

 That's just the probability that we'll get for a collection of。Alpha 1 heads and alpha0 tails。

And then we found that when we did a little bit of calculus to solve for what is the value of theta that makes this the greatest。

 given that we know what alpha 1 and alpha 0 are。😊，Then we found out it was just this。

 So if we flip the coin and we end up with three heads，7 tails。

 then our maximum likelihood estimate is just three out of 10。

Which happily matches our own intuition about what common sense would tell us。

But now we know that it actually follows this principle。

That it's also the value of the that maximizes the probability of the observed data。

 the alpha 1 and alpha 0。And by the way， this term here is often called the data likelihood。

It's so important that it gets its own name， but it's really just the probability of the observed data given theta。

Then we also talked about a second way of doing this。The map estimate。 And again。

 we illustrated this in the case of a coin flip and worked through the arithmetic on that。Actually。

 the arithmetic was remarkably similar。In this case。Again， the probability of the data。

OfThe observed data given in theta just as it was before。 But now in this case， we。

Since we're doing a math estimate。We want to also include a prior on theta。And in the case。

 last time。We agreed that we would use the prior that's of this form。

 it's called a beta distribution。It takes itself two parameters， beta 1 and beta 0。And。

It gives the probability。For any。Theta。To be equal to this quantity。

The prior probability on theta is this quantity。 And you can choose different values of beta 1 and beta 0 to get different values for the probability of theta。

But， and after class， somebody asked me， what is this。B function here。 Sorry。

 I didn't have time to mention that last time， but the B function is just a normalization。

 Remember how if we have a probability distribution， the probability has to sum to one。

Or in the case of a continuous distribution， this is actually a continuous distribution because theta can be any real number。

In that case， the integral under the probability density function has to integrate to one。

 It's the same idea。And what this B function here is。

Is just some quantity that makes sure that the integral under this area。

 this is equal to the integral under this expression。

And so this makes sure that the integral actually does end up being one because we just normalizedize by him。

So for our purposes， we can just think of this as a normalizing constant that makes sure the integral overall possible values of theta of the probability equals one。

 and of course， that constant doesn't even depend on what theta is。

And so when we're solving for theta， we can just ignore that constant if what we're going to do is to try to maximize the profitability。

Okay， so there was our form of prior。 And we chose that on purpose， to have a particular form。

It's called actually， the conjugate Pri。For。This multiomial distribution。

 this binomial distribution that we have。 we chose it because this quantity。

 this part here looks a whole lot like the form of the data likelihood here。

And so when we multiply those together。Remember， what we're going to do now to find our map estimate is find the theta that maximizes the product。

Of the prior and the data likelihood。And when we multiply those together， we get this nice。

Express where。This quantity， and。This quantity。Go together so that we end up with the theta。

The alpha 1 plus beta 1。-1。Times the1 minus theta。Times the alpha 0。And a beta 0 minus1。

So that actually gives us something of。The same kind of form。And so then not surprisingly。

 when we maximize this by picking the theta that maximizes it。

 we got something that looks just like the MLE estimate。Except with some hallucinated。

 additional imaginary heads and tails。Added in。The reason this looks so much like the MLE estimate is because we。

Basically， the mathematical form of this times the data likelihood is just very similar to that data likelihood expression itself。

 except that。Alpha 1 here， for example， is now replaced by alphapha 1。Plus， beta 1。Mus1。

