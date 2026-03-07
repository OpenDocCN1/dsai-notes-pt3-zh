# 卡耐基梅隆【中英⚡高级机器学习｜10-715 2015 Advanced Introduction to Machine Learning】 p07 P7 EM_ PCA_7_ - Machine Learning 10-715 Fall 2015 -BV1hiWnzQERQ_p7-

嗯。Never decreases the likelihood function。So it either increases the likelihood function or doesn't change it。

And today we are going to discuss an application for this for estimating the parameters of mixture of Gaussian model。

And after that， we continue with another unervis learning algorithm。

 namely the principle component analysis， algorithm or algorithms。Any questions？

Any questions about the proofs we did last week？So everything is clear so far good。

So just to re up very briefly， this is what we did that we had。ADa set x1 x to XN。

 we had some unknown variables， for example， in clustering。

 these unknown variables were y1 pi to by n。 they just indicate cluster label and in the mixture of Gaussians。

 we had parameters move1 me to mu K， they are the means of the clusters pi1 pi2 pi k， they had the。

Prior probability distribution of the clusters and Sigma 1， Sigma 2， Sigma K。

 they are the covariance matrixrices of the。Gauussians and our goal is to have a design an algorithm that can do a maximum likelihood estimation in this model that is we want to maximize the log likelihood in theta and if we have n instances then our estimate is theta head N。

And。The EM algorithm， how it works， that first you create a Q function that has two argument theta t minus1 and theta t。

And what you do that you take the log of the joint density of the hidden。Random variables by。

 so they are the cluster labels in our case， and we have the data。Those are the x's。

Given the parameters at time step T， this is， So you take the expected。

Value of the s likelihood we just expect to buy。And the posterior distribution with respect to buy is this。

 So in this posterior distribution you use parameters at times5 minus1。So you create this Q function。

 which depends on tta t minus1 and tta t。Oh。跟你。And so that's the E step。 And in the M step， you just。

Use this Q function and you maximize this in the first argument。So it's Q tta T to t minus1。

 you maximize this in theta and that will be t to t。

 and then in the next iteration you put t to T here to the second argument and you continue this iteration。

And we discussed that or we proved， that if you do these steps， then。In the next step。

 the likelihood function is either bigger。Or the same as the likelihood function at times 70。All。

 and we discuss this intuition behind the EM algorithm that you have the likelihood function。

 that' is this black curve， xx is this theta， and what the EM algorithm does that if lower bounds this function with another function calls free energy。

And in the E step。You try to minimize the gap between this free analog function and the likelihood function。

 So you move this。Free energy curve up till it touches the likelihood function。

 it's always smaller or the same as the likelihood function。

And then you maximize the free and energy function。And then。

In this maximum point you fit a new free energy function again you push it up till it reaches the likelihood function and you do theiteration。

 So that's the EM algorithm， the variational method in the variational methods。

 you can even generalize this framework even further。

Where you just do a partial step that is your free energy function will not really touch not necessarily touch the light function。

 You just try to optimize this up till it gets close and in optimization。

Then you do this optimization。 You always assume that the。Q fun， Q distribution function that we。

Used its in a tractable form。 So sometimes depending on the model in the em function。

 we had this Q function we optimized right this P y given the data and tta t -1。

 it might be intractable。In the variational approach。

 you replace this with another function that's close enough to this， but it's in acceptable form。

So those were the main ideas， and now let's see an application。For this model。All right。

 so let's come back to this mixture of Gaussian cases。So we have unlabeled data x 1 x to xn。

We know that there are key classes。😊，So that's known and for simplicity。

 let's assume that we know this prior distribution pi1 pi2 pi 3 pi k。

And we know that the Gaussians have a common variance sigma square。

 and what we don't know is the mean vectors of these Gaussians， and we just want to estimate them。

Okay， so this is just the first step。 Ily， what we want is that。So after we solve this problem。

 we'll discuss how to generalize this even further that you don't know pies。And you even。

 you can even assume that。There's a covariance matrix， sigma。

I for each Gaussian and they can be different。All right， but for now we just start with this simple。

A problem。Okay， so we want to solve this parameter estimation problem。

 so we want to estimate move1 me to MK using the EM algorithm。And。

You already know that the likelihood function， that is the probability of x1 x to x and given the parameters。

We have IID observations， so it's the product for Royal J1 to N。And if you do base rules。

 then we will see that this probability is nothing else just proportional to the product。😊，啊。

Of this sum， therefore use sum for each cluster from one to K。 and this is the Gaussian distribution。

 and this is just the probability of the Gaussian components。 Okay， so we calculated this many times。

 So this is just the likelihood function。 Our goal is to maximize this in move1 mu to mu k。

Any question about this？Okay， so this is what we want to do。

And we want to solve this problem with DM。 So first， we create a Q function。

So what was that Q function？You remember， we need to。Let me come back to that。He we got？So in the E。

 we need to create a cube function the。Sa T to T， and this does just the expectation。

Of this posterior distribution。So this is the posterior of p。

 and I want to calculate the expectation of log P。Why the data given。P라터。And that's it。

 So this is the Q function。So this is the Easter。So let's see how this cube function looks like for the mixture of Gaussian case。

😊，All right， so in our case。Q嗯。Sa T to T and T to T -1。

So we need to calculate this expectation and this expectation is nothing else just the sum because we have IID。

Sample is x1 x so xn， so some from Iu。