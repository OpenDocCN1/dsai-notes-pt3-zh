# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p57 P57 Recitation 6 Graphical models Feb 19 -BV1Lcnhz1E7P_p57-

Okay， so let's get started。嗯。So today I'm just going to cover Gal models which Professor Mitchell just started covering on Wednesday。

And but we didn't really get through that much because we were finishing off the previous material at the beginning of the class。

 so I just want to make sure that you guys have enough to do the assignment。That's due next we。

So let's see。So the first thing I want to cover is just go through review a lot of some of the concepts that will be very useful。

Kind of necessary because you kind of need to know like a good。

Have a good foundation of probability theory to really understand graphical models。

 so I'm trying to go over some of those concepts。So the first thing is suppose I just have two die。

 it excited die， and I roll them。Can you guys see that。Okay。A little bigger。And。

I want to suppose I know the probability， the joint probability。

 the probability of combinations of both dies。So I know the probability that die1 is one and die2 is3 right。

 I know the probability that die1 is6 and die2 is1。 I know all of them。

 I can draw this out in a grid like this。So these are just my event space， my probability space。

 right， this particular event is when die1 gives me three and die2 gives me two。Right。

 this one is die1 is 6 and die2 is6， right， and base E want to。Illustrate the following fact。

If I want to compute the probability of just one of the die being a certain value。Sa。Yeah。And I can。

Over the joint。Yeah。So this is the probability of di1 say being equal to 4。Is this space， right？

Or this is five， my that， but you can see that it's a sum of the individual probabilities over the possibilities of die2。

😊，RightSo that's basically illlartrating your point。 and this is pretty useful because it's a。

It's a pretty fundamental fact from probability theory。

 and we're going to use it to do inference in graphical models。Okay。So。

Before I get to the definition of graphical model， I want to。

Just go over the definition of what of a probabilistic model， a more basic concept。

 which which we've seen a couple of times。 but just to make sure the definition。So。

So a public model is just a collection of random variables that are somehow related to each other。

And。嗯。Tyically you typically describe how one is related to any one random variable is related to the other random variables。

 like this is， for example， a probabilistic model， I have two random variables。

 the first die and the second die。So。And。You can kind of think of it intuitively or one way to think of it intuitively is is as an extension of deterministic models。

 like if I have the if I equation。And I ask like what is the value of y when x is zero。

 you pretty you can tell me that， and these equations like in general， deterministic models。

 systems of equations are very useful for describing things about the world。

 having modeling physical phenomena， a lot of other phenomena。

 and we can use them to tell us a lot about things that may not be necessarily immediately known to us。

APbabilistic model is basically an extension to this where you can think of the variables as being random。

So instead if I ask if x is drawn from a normal。of mean zero and standard deviation variance1。

 then what is the value of y， and that's useful， especially when the phenomena we're trying to describe has uncertainty or randomness and there's a lot of uncertainty in real world phenomena that we like to model。

😊，And capture it when we're doing machine learning。Okay。So。有啥。I can move this up。Let's go here。So。

We use a lot of words like joint prior likelihood posterior。

I just want to make sure we pin down the definition of those words to make sure that you guys understand what we're talking about when we say those things。

So。The joint distribution， suppose I have a probabilistic model with the following rendered variables。

I have x1 through xn， and I have。Theta 1 through theta M。

 let's say right so I just have n plus M random variables and they somehow relate to each other。

 I'm not going to tell you how or why because this is a general definition。The joint is given by。ししし。

So this is the joint probability， right so the joint distribution is the distribution over all of the random variables in your model。

And the drawing probability is a probability of all the random variable in your model taking on in values as a shorthand。

 sometimes people will collect random variables together that are similar and they'll just write。

This xs means all the x's， the thetas means all of the thetas。Okay。

And so suppose now that I've observed some of my random new variables， right。

 suppose I observe all the x's。And in machine learning， that tends to be your data。

 the data points that you observe。Then I can define three other distributions or probabilities that are commonly used。

So。So this is my prior。So the probability of only the things that are unknown is the prior。

Sometimes you also just say， what is the prior on a particular random variable。

 like theta I or theta。2， right， and that's also the probability of theta 2 is the prior on theta 2。

The likelihood is the probability of your data， your observed random variables。

 given the unobserved random variables， the unobserved parameters， the hidden information。

 and this quantity is what you try to maximize over your hidden information when you're doing maximum likelihood estimation。

😊，And the posterior is just the probably distribution of your unknown random variable。

