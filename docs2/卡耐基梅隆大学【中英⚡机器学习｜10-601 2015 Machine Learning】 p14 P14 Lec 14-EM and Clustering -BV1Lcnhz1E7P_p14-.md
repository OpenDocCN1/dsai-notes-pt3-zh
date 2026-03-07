# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p14 P14 Lec 14-EM and Clustering -BV1Lcnhz1E7P_p14-

嗯。How is midterm。Maybe fair， not fair。I thought it was pretty fair。 We worked hard on that。With。

Pretested it。 I always judge a midterm， both by how well it tests the the material。

 but also by how many clarification questions have to be corrected during the midterm itself。

 at least we scored good on the second measure so。We hope to have that graded by the end of the week。

 and we'll announce on Piazza， how to get that back to you。Okay， so back to content。Today。

 we're going to talk a little bit more about EM。Which has to do with how we train machine learning systems。

 especially Baynet oriented。Machine learning systems。

 when we don't really have fully observed data when some of the variables of some of the training examples are missing。

So we'll talk a little bit about that。 And then we're going to talk about。

How this actually gives us an algorithm for totally unsupervised clustering。

 So it turns out clustering sounds like a different problem than we've been working on。

 but it turns out we don't need a new algorithm to do clustering。 E M is a perfectly acceptable。😊。

One perfectly acceptable algorithm for doing clustering。 So we'll look at that。

 And then we'll look at。 remember when we're talking about learning training base nets。

 we mentioned that there are different。😊，Sort of four different versions of that problem。

 depending on whether the structure of the base net is given in advance or not。

 and also whether the variables are fully observed or not。

And so I guess so far we've looked at the case where the structure is given and the variables are fully observed or not。

 that's EM。But we'll also look today at the worst case， the fourth quarter。Fourth quadrant of that。

 where neither the structure。Well， I guess we'll look at where the structure is not given。

 but the data is observed。And then you can extrapolate from there how to get to the evil fourth quadrant。

We'll talk a little bit about that， so that's the plan for today。So I want to begin。By。Just again。

 reviewing EM。E M is an algorithm。 We think of it as applying to base nets。 Remember。

 we had this base net we were thinking about before where we had variables like， do you have the flu。

Do you have an allergy？Do you have a nasal problem of some kind？And。To you。Have a headache。

And are you sneezing？So simple little medical phase net。And。We talked about when we talked about E M。

 we looked at the example where some of those are observed。 Four of those are observed。

 all color in the ones that are observed here。And one of them， N is not observed。

 And then we brought up E M as a way of。Training in general based nets when only some of the values of some of the training examples are observed。

 And we said that informally， the idea is。We go through the E process where informally。

 the idea is that on the E step， we will estimate the values。

 We'll get the probability distribution over the values of those unobserved things like N。

 And then on the M step， we'll use those inferred values。Of the unobserved variables。

To estimate the parameters of our basenet， and we'll iterate that process。 and as we mentioned。

 this is guaranteed to lead to at least a local maximum in the expected log likelihood of the full data and here I'm using x to refer to this set of observeded variables and Z。

 the set of unobserved variables。So it' is kind of nice that we have this guarantee that we'll be able to get parameter estimates and also assigned values to those unobserved variables。

That correspond to a maximum。We'd like to say maximum likelihood of the full data。

 But since we don't really observe the， we have to say it's the expected likelihood。

So then a little bit more precisely。The E step， as I mentioned。

 is to use the observed data X and the current parameter estimates to calculate the probability distribution over the unobserved variable Z。

And then on the M step。To choose the new theta based on the old theta that we already have。I'm sorry。

To choose a new theta based on the old theta that we already have by finding the theta prime that maximizes this Q function。

 which is just that expected data likelihood。And we went through an example。嗯。Here。

 we're assuming that the sinus variable is not observed。Well。

 we went through an example where on the E step， we noted that using our standard rules for Baynet inference。

 we could estimate the value。Of the S variable， given the other observed values on the Cafe training example。

 And that was simply this expression。Which， by the way。

 should look very familiar from the midterm if you answered that particular question correctly。嗯。

And then， on the M step。We'll use those inferd。Probability distributions over the unobserved S variable。

To estimate a new。Vectctor of parameters for the base net。

 And here is showing just the example of the parameter that happens to predict the probability that S equals。

One， given。That its two immediate parents have the values I and J。

And the interesting thing here is that， you know， we derive this by。

Working through the arithmetic on what it takes to maximize that expected。Full data log likelihood。

 But once we finish the arithmetic， we get this expression。

 which looks remarkably similar to our maximum likelihood estimate that we would have used in the case that we had fully observed data。

There we would simply have counted Delta here as a little indicator function。 That's one。

 If its arguments are true and 0 otherwise。 So this just says we count over all K training examples。

 the number of cases where。F， A and S take on this particular set of values。Normalized by。

The number of cases where F and A take on their values。

 So this tells us the proportion of times of when this is true， for which this is also true。

 S equals 1。And。Here， what we have instead is simply the same denominator。

And almost the same numerator， except that we don't really know whether S K equals1。

 All we really know is the probability that it equals one， the expected value。

Which for a boolean variable， which can only be 0 and 1。

 its expected value is the probability that it equals one。

And so this numerator is just as though we were waiting each example， K， the case example。

With suppose the expected value is 07， the probability that S equals 1 is 07。Then。

 this will turn into。A count of 07， instead of a count of one。

And when we get to estimating the other。Praameter about f equaling zero。Well。

 I guess that's 1 minus it。 but that would just correspond to this being 03 of an example counting toward S equals 0。

Yes。If you use this formula for all the data， even including the label data。

 it will just like the M steps like the E step。If we use， say that last sentence， for all the data。

 including the data， Yes， yes。Yes， so the point was， we use this numerator for all of the data。

 including the labeled data。 And so there we assume that if we have a labeled example where we really can observe the value of S。

 then we assume if we observe S equals 1， then its expected value is one。In which case。

 this turns into exactly the same value as this would。So in fact， in general。

 it turns out here's a very nice thing to know if you have a baes net。

And all of the random variables are Boolean。