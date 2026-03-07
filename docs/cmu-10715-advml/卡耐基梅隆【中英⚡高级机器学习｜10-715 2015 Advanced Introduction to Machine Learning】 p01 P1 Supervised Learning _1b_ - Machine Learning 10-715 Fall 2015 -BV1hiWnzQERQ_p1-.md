# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p01 P1 Supervised Learning _1b_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p1-

That嗯。We are going to continue。Where we stopped last time we are going to discuss maximum upperposterory estimation than na based estimation。

 I will try to be as quick as possible so then AlexX can continue with deep neural networks。嗯。

That's said， so the lecture will be quick if you don't understand everything， that's okay。

And I would say it's intentional。 So it's the point。

 So one thing you shouldn't forget that it's a graduate course。

 So most of your understanding should happen at home so you。Of course， you should。

Understand as much as possible， but it's all fine if you go home。

 look at the slides and you understand the tiny details there。嗯。

There will be more slides that we are not going to cover in the lecture but again that's intentional。

 you can go home look at the slides if you don't understand anything or you don't understand everything then ask us and the TAs and Alex and I will be happy to answer your questions。

嗯。Allright， so last time what we where we stopped that we discussed maximum likelihood estimation for the parameter of a bad distribution。

 So we had this coin flip problem and。😊，We discussed that the frequency is a reasonable。Estimator。

 it turns out that that's the maximum likelihood estimation as well。 and we。

Look at this surfing bound， which。ECharacterize how fast your estimator is converging to the true parameter。

We also discussed the maximum likelihood estimation for the Gaussian distribution。

 and this is where we stopped where。We mentioned that interestingly。

 the maximum likelihood estimation for Sigma squared is。Not an unbiased estimator。

 It's a biased estimator。So the next step to continue is that this estimator it doesn't uses any prior knowledge right it's just you count the relative frequency or from your data you estimate simply the parameters of the Gaussian distribution。

 but what happens if you have some prior knowledge and how could we incorporate that prior knowledge into the estimator？

That's the question and that's what we are going to discuss now。

 and the maximum upperpo estimation is a way for that。🤧So。What we are going to do that。

We assume that before getting any data， we have some prior knowledge。about our estimation problem。

 for example in the coin field problem we want to estimate the probability theta that the coin will be had and imagine we have some prior knowledge about this parameter for example this is the probability of theta that is my prior knowledge and what we want to do that as we collect more and more data I want to update my the probability distribution of theta。

Is that goal clear right so we start from some prior knowledge we collect some data using my prior knowledge and the data I want to estimate。

I want to estimate the parameter and I want to get a new so-cal posterior estimation of the parameter data。

 So what you can see here that D denotes my data and after collecting it。

 this will be my new so- called posterior estimation。😊。

And usually what happens that as you have more and more data。

 the distribution is getting narrower and narrower。😊，All right。So how should we do that？Any question？

So we assume some kind of prior distribution on the parameter the。

 there is an interesting class of prior distribution， which is when we don't assume any prior。

Knowledge about the distribution。 And that's called uniform uninformative prior in our case。 So。

 for example， if on Tita， we have a uniform distribution。

 it means that you don't prefer any parameter over other parameters。

And there's another very interesting and important。😊，ACls of priors that we call conjugate priors。

And they have a nice propity that you start from a。

spececific form of prior distribution speed data you collect some data and then the posterior or distribution will have the same form as your prior distribution so for example if your prior distribution is a Gaussian distribution you collect some data and then if the posterior distribution is again a Gaussian distribution then we say that this was a conjugate prior to your problem。

Why we do that because computational is effective， because then the prior and the posterior is in the same form。

 So you just need to update those parameters。Okay we will see some examples for conjugate priors。

Okay， so to calculate， so again， our goal is to remind you to calculate the maximum of posterior estimator that is you call some data。

 and then you want to calculate that posterior distribution。😊，To achieve our goal。

 we will need the base rule。Wwhich can be derived from this change rule I really hope that you all know these rules that the joint probability of x and y is just the conditional probability of x given y multiplied with the probability of y and the base rule is if you want to calculate the conditional probability distribution of x given y this is how you can do if you know the probability distribution of y given x and the probability of x and probability of y these are unknown right。

Very good。Okay， so how can we do that in our estimation problem？

We want to calculate P Tta given the data， right， We want to estimate these parameters and。

We can use the base rules for that， which you can see here。 And at the end。

 we want to maximize this probability distribution in theta。

 That will be our maximum posteri estimation right。

 So you calculate a posterior distribution and your point estimate would be the the point where theta would get maximum value right So we want to maximize this guy in theta。

 you can。😊，Notice that P， the data of the distribution doesn't depend on theta。

 so we just need to maximize this guy。In data。 So this is the likelihood times the prior。

 So in maximum upper estimations， that's what we do。

 We multiply the likelihood with the prior and maximize this expression in data。嗯。Okay。

 so how does it differ from the likelihood estimation， maximum likelihood estimation？But。

What would be different？In the MLE， the prior is nothing about the prior that goes， so it's just one。

Okay， so that's， that's how maximum outputity estimation is more general than the maximum likelihood estimation。

O， so this is just formally the same thing here， Theta hat MLE is that you maximize the likelihood function in theta and the maximum upper3 estimation is that you maximize the likelihood times the prior in theta。

😊，But right let's see a specific example。😊，Again， the coin flip problem。

 we flip the coin n times and alpha h times we get head， alpha t times we get tail。

And then I can ask， what's the probability of my and the probability of getting a head states The。

 Okay， and then I can ask the question， what's the probability of getting my data。

And coin flips given these parameters and。I hope you all know this is a binnoomeal distribution。

Right， so if we flip the coin n times， then n choose alpha h。

 then the distribution is n choose alpha h。 This is how many times I can get alpha h multiplied with theta to the alpha h times the probability that I get had。

 and one minus theta。 that's the probability I get here。 So I need to put that to the power alpha T。

 So that's the。😊，Binaome distribution。 And let's assume this time that I have some prior knowledge about the parameter data。

O， and one specific prior knowledge I can have is that say I assume that P theta。

Has a bit of distribution with some parameters。 That will be my prior knowledge。

Who has never seen beta distributions in their lives？Everyone is familiar with data distributions。

Who knows beta distributions？Okay， so it's。嗯。Still， I can see some people who。

