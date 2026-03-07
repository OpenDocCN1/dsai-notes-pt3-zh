# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p59 P59 Recitation 8 Midterm solutions review Mar 5 -BV1Lcnhz1E7P_p59-

In the midterm or yeah， that's okay， cool。How did you find the midterm， was it like too long。

 too easy， too hard？😊，So the mean score was 60。7。And the standard deviation of the scores was 14。9。

 if you guys were curious， I think the high score was like 88 out of 80。😊，And。So。

So I think for some of the questions like they're really well done。

 so I'm not going to like write down the solutions maybe unless you guys are curious and then for a few that had some like consistent problems we'll go over the solutions for those so the first two parts here。

 Part A and B of question 1。1 they're actually taken directly from homework 2。😊，啊。

So for the first one you apply to the chain rule twice。

 the first time you'll get the probability of x1 given x2 and x3 times the probability of x2 and x3。

 and then you can apply the chain rule again to the second term and it works。Yeah， sure。Briendnda。嗯。

Let' screen。Is that better or should these ones come off again cool？Yeah， actually。

 maybe we'll go through。😊，So you have the probability that。X1， x2 and X3。

And if you p a chain where once， you get the probability of。Next one， given next to。Next three。

Times the probability of x2。Together with X3。And then you can probably the chain one more time to the second term there。

 and then you'll get。The。好。Yeah。う。Yeah。And。Just like a couple comments。

 you can reverse the order of these things before you do this and get still correct。

 and it doesn't actually matter whether or not you think of these as being random variables or as being events。

 if you think of them as being random variables and this is true for every assignment text， 1 x2， x3。

So other questions。Again， the second part it asks you to prove Bays rule does anybody。

I want to suggest how to proceed？So again， it just falls from the general。The V one given next to。

Time is the probability of x2。By the 1 rule， this is just the probability of x19 next to you。

And then things are commutative in the order of the parameter。

 so this is the same as the probability of x2。Next one。

Then you can apply the chain rule one more time。To get that this is the probability of x2。

Do you have the next one？Pro I believe X1？And then if you divide both sides of this sort of atermost equation quality。

By the probability of x2。Then you get Bay。So the first two questions are。

I think you can also find the solutions in homework too。Okay。

 so now for the naive bay modeling questions， we tell you that you're given four random variables。

 Y x1 through x3。And they're all boolean value， so they take the value0 on one。

And so the first question says， is it a good choice to use Gaussian knifeive basease to try to predict Y given the x's？

And。And so what you do when you're doing Gaussian Nivease is you assume that the distribution of each Xi。

 given y is a Gaussian random variable。😊，But since the random variables are all discrete valued。

 it's kind of a strange thing to model them as Gaussians， so the answer is false。

Okay for the next question。It asks you if you need to make conditional independence assumptions。

 including that y is conditionally independent of x1 given an x2。And that's not true。

In the Nive base assumption， you assume that the x1 through Xn are conditionally independent of one another。

 given y， but not that y is conditionally independent of any of the Xi， given another X'。

 just to see Y that would be kind of silly。 So if this was true， then if I knew xq。

 then x1 tells me nothing extra about the value of y So why would I include it in my list of variables that I'm predicting y from。

Everybody's good with this explanation。Okay， so the next question asks。

 how many parameters do you have for the Nive Bays estimator in this problem？啊。

And so in this question， a lot of people had too many parameters because they didn't use the law of total probability to rule out some。

Of the probabilities。So finiteight days， we assume that the probability。Now X1。X two， and X three。

 given why。This was just the probability。K me， we're going to predict the output class that maximized this product。

So this is actually the joint distribution of the probability of y and all three of the x's and so you need to be able to compute probabilities。

 it should be PY over here。So you need to be able to compute the value of each of these factors。

 right？And so for the probability of why？For this one， you need just one parameter。

 probably that y is equal to one。Because you can get the probability that y is 0 by taking1 minus this number。

And then for each of these guys， you need the probability。That Xi is equal to1。

 given that y was equal to 0。And you also need the probability。AnXi。Its equal to zero。Equal to one。

 given that y equals one。So you can get the other probabilitybabilities。

 the probability that X is 0 when y is 0 by taking 1 minus this。

 and the probability that X is 0 given y is 1 by taking 1 minus this。

So you get two parameters for each of x1， x2， x3。Sorry， two parameters and then one parameter for y。

 so that's a total of seven。Does anybodybody have any questions？Pas to。嗯。Right。

 so for each of these random variables you need to know two numbers。

 so the n would be like the number of x's here， so it's2 n and then plus one for the prior on y or the marginal distribution on y。

Its I find like for these things， I think sometimes it's easier to actually work out like which numbers you need to know instead of trying to remember。

Formula for it。It' because I can never remember formulas，So， okay。So then the next question， Part B。

It sayss that NightBS is a special case of a Bayesian network。

And so pretty much everybody got this question right。

 but you also have to justify your answer in one picture or a sentence and a lot of people got this part wrong。

😊，Right， so actually maybe。I'm going to race。Now。Right so the definition for a Bayesian network。

 what it told you is it gave you a way of factorizing the joint probability distribution。

So if you have a Bayesian network over rh of variables x1 through xN。

What it told you is that the joint distribution of X1 through Xn。

You could write this as this product。So you hit one term for each of the random variables。

And it was Xi。Given the parents of XI。And so the question is， can we express the NiveBase。

 like can we construct a graph like a graphical model so that this rule。

 this transformation gives us the NiveBase assumption。😊，And so。If you remember。

 we'll just write down the9 base assumption again， so probably x1 up to xn。Together with why？

This was just。The probably of why。Times。He。Ex one。Yeah。

Can you guys still read this or is it too small？It's good。 Okay。 So this was just the chain rule。

 And then the9 base assumption told us that we could factor this part as。😊，So we get Py。

 and then we get this product。So these two expressions， the factorization that you get from a bays。

ABase net is really similar to the factorization that you get from applying the knifeive base assumption and the thing。

What we'd need to do to make this actually be equal to this would be to make a graph where Y had no parents。

And where each XI had one parent， and it was always why。

So the way you can do this is by making a single node here， which is why。

And then for each of the random variables xN。You just draw one edge from Y。

