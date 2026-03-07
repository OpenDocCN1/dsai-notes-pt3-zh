# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p07 P7 Lec 7-Linear Regression -BV1Lcnhz1E7P_p7-

So， we。Last time we're talking about logistic regression and we left on this kind of very interesting discussion about。

When should we use naive base， When should we use logistic regression。

 What's the difference between the two in practice。

 So I want to pick up there and then also talk today in addition about linear regression， which is。

Another learning algorithm for computing real valued y's。 up till now。

 we're trying to learn functions from x to y where we have discrete valued y's。Okay。

 so just as a kind of quick。Logistic regression in one slide。嗯。

What we basically talked about last lecture in one slide is this。The idea of logistic regression。

 the way we motivated it was to say， well， what if we make the same set of assumptions up here in the first bullet？

That we make for Gaussian naive base， then let's derive the form of P of y given x。

 and we agreed we derived it， it's this。And then。We derived a gradient ascent algorithm。

For estimating the weights W。Or learning the weights W from the training data。

That followed what principle？What principle were we following in choosing those weights？

RightIt was just a variant of the maximum likelihood principle。

 that is we set ourselves the goal of finding the weights that would make the data most likely and the variant that we used was conditional likelihood instead of likelihood that is instead of making both the x's and the Y's most probable by choosing RW。

 we instead just simplified it to the conditional likelihood so that。

We assume the X's are just given。 We don't have to worry about their probability。

 And so we just chose the W's that maximize the conditional probability of the Y's in our training set。

Given the observed X'es in our training set。And so then we got that nice gradient to central rule。

And in fact， there is the gradient a cent rule。And then we mentioned toward the end that， oh， well。

 we could also， instead of maximum likelihood， try to do a map estimate。Of course。

 anytime we're trying to do a map estimate， we have to make up some kind of prior。

On the parameters that we're trying to。Learn or estimate。And it turns out if we。

Say that the prior we're going to use is that each weight follows a normal distribution。

With mean  zero。And some variance sigma。If each weight does that， and here I've written。

 it is if the whole vector of all weights follows， I can talk about a multi variant。Gussian。

 that is a Gaussian defined over multiple weights。 It just， that's why this I is here。

 It's the identity matrix。That's a detail we don't have to really worry about right now。

 You can think of this as just a set of normal distribution。 We say every weight。

WOI follows just a univariate normal distribution。With mean zero and variance sigma。

And then it turns out， well， the derivation of the gradient sent rule when we just worried about this quantity。

Is up there When we add in the prior， that gives us one more term。It's a very simple term。

It's a term that every time we do a gradient step to update our estimate of WI。

 given the old estimate of WI we add in this quantity。And again。

 this quantity is just the misallocated probability mass， according to our prediction。

But this new term is just a simple term that pushes the weight WI towards zero。If WI is。

 we make these constants positive， then if WI is positive， we're going to subtract。

Some fraction of W I from its old value， push it towards 0。 If W I is negative。

 we're going to add something to it to push it towards 0。 We're pushing it toward the mean。

Of this prior that we put on it。Okay， so that's kind of a quick review of last time。And。嗯。

Let' skip this just saying the same thing。So。Then we started talking about the question of should we use naive Bay。

 Should we use logistic regression， Who cares， What's the difference， This is actually。

Just one example of a more general。Trade off between or question that we can ask about different machine learning algorithms。

 in fact。People often you'll hear the terminology generative classifiers。

Were discriminative classifiers。Generally， if people talk about a generative classifier naive base is an example。

 what they mean is that。That learning method。Assumes that there's some。

Functional form for P of Y and P of x given y。In the case of Gaussian Aive Bays， for example。

 we assume Y is governed by a Bernoulli distribution。And P of x。

 given y is governed by a Gaussian distribution。And then we estimate the parameters of those two things and use Bay's rule to calculate。

Given a new X was the probability distribution over a possible Y？On the other hand， in contrast。

 if we have a discriminative classifier。Such as logistic regression。

 then we just instead assume some form for P of Y given x。And that's what we did。

And then we directly estimate those。So it turns out for any kind of。Probbabilistic model。

 not just naive days。We kind of have this choice。Of which of these two ways to go。

 And you can think of logistic regression in naive Bay as a case study。In that。A set of choices。嗯。

I put this note here just to remind me to remind you。

That there is this kind of difference between how committed。

These two methods are to the conditional independence assumption。Now you phase uses。

The conditional independence assumption， both when it's training。And also。

 when it's using Bayes rules to classify a new example。On the other hand。

If you think about logistic regression。We certainly assumed the conditional independence assumption when we derived what's the form of P of Y given X。

Right we went through that derivation。 We started with。The conditional independence assumption。

However， the training procedure， the gradient asscent procedure that we derived。

Really did not involve any assumptions about。Conditional independence。

So that gradient tocent procedure is just going to find。The best fitting weights W0 through WN。

Given the data。And there's nothing about that training procedure itself that commits to following conditional independence assumption。

Yesス。😊，チプですね。So we'll perform better when there is。ご。Yes。

 so if conditional independence is satisfied， then。

We're going to get good performance from both of these algorithms。

 at least as the amount of training data approaches infinity。If it's not satisfied， then in a way。

 logistic regression has a little bit more flexibility to a little more robustness to overcoming the。

False conditional independence assumption that we're making。Yep。I you say anything about。

which type of classifiedifier is more？お的。Yeah， yeah。 that's good。Overfitting is a funny。Problem。

 I actually， I'll just say this。 Naive B， as we talked about last time。

 is estimating more parameters。Then logistic regression， right， We said last time that if。

We're trying to predict a discrete y from N Boolean x subs that we'll need for Gaussian knife bays4 n。

Plus one for the prior parameters， but for logistic regression， we only need n plus one。

So it's got more parameters， generally， all other things being equal。 you think the more parameters。

 the more prone you are to overfitting。 That's my rule of thumb。

 but all other things are not quite equal in this case。 actually so let's take a more detail。

