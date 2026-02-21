# 华盛顿大学《机器学习（分类，聚类和检索，第3-4课⧸共4课）｜Machine Learning》中英字幕 p173 51_EM算法的收敛、初始化和过拟合.zh_en -BV1Sr421F7N7_p173-

。

![](img/8eeb826f04e4cee7fd707a6af73befc7_1.png)

Let's now spend some time getting into the nitty gritty details of EM and also provide a comparison between EM for mixtures of Gaussians and kines。

Well to begin with， we talked about the converged solution of EM in the series of pie chart plots that we just showed Well the question is do we know that the EM algorithm is going to converge well you can actually recast the E and M steps of the EM algorithm as alternating maximizations of an objective and from this we see that EM is actually a coordinate ascent algorithm and under mild conditions you can prove that EM indeed converges to local mode of the objective。

And in your assignment， you're going to monitor convergence of the EM algorithm by computing the log likelihood of the data。

 given the current estimates of our model parameters and responsibilities Well。

 based on the nonconvex landscape and convergence to the local mode。

 how we think of initializing the EM algorithm can be really critical to the quality of the local mode that we find as well as to the convergence rates of our algorithm。

And there are many ways we can think about initializing EM One is we can think about just randomly selecting some data points as our initial centers and doing hard assignments of observations to the nearest cluster center and then using those assignments to form our initial parameter estimates and then our EM algorithm would iterate from there or another alternative would be to pick the cluster center sequentially like how we described in our K means plus plus algorithm instead of just randomly choosing k different data points all at once。

 or we could think about actually running K means and using the final solution of that as our cluster centers for this initialization scheme and there are also other approaches for example。

 in speech applications it's really popular to do things where you gradually grow the mixture model by splitting and sometimes merging clusters until you have K cluster。

Is formed。Having discussed convergence and initialization。

 let's now spend a little bit of time discussing a potential pitfall of the EM algorithm that we've described and this all stems from the fact that maximum likelihood estimation can overfit the data。

So as an example of this， let's imagine that we just have two clusters。

 the green cluster and the blue cluster， and let's assume that it's some iteration of our algorithm。

Only one observation is assigned to the green cluster and all the other observations are assigned to the blue cluster。

 and when I'm speaking now I'm talking in terms of hard assignments。

 but the same thing that I'm going to talk about holds if we're using soft assignments instead。

Before this single observation in this green cluster。

What's the thing that's going to maximize the likelihood of the data in that cluster well for the green cluster we're simply going to set the mean of the cluster exactly equal to that data point and then we're going to shrink its variance all the way to zero right around that data point。

And for the blue cluster， in this example that I've shown here。

 we're going to shift its mean over and increase its variance to capture all the data points that were shown。

Okay， so this doesn't seem like a great solution here， right。

 because we have this one data point with this tiny， tiny， tiny， tiny， tiny。

 infinitesimally small cluster。Tied right to that data point value。

 and then these two sets of observations， which to me look pretty separable。

 all lumped together in one much more diffuse cluster。But。

The likelihood of this assignment is actually infinite。

 all driven by the fact that the likelihood of the green observation under a Gaussian that's absolutely certain that the only value it can take is the value that was observed is infinite。

And so that's going to completely dominate the overall likelihood of this set of assignments。

 and we're going to see that this is actually the preferred solution。Luckily in practice。

 you almost never get into assignments in this very simplistic case。

Of having just that one green observation in that cluster。

 but this is something that really can happen and you have to think carefully about it。

 especially when you're thinking about ways to initialize your algorithm。

But the problem can actually be much much worse in high dimensions。

 so to think about this let's go back to our document clustering example。

 so here we're going to assume that we have some large vocabulary and every document is represented by maybe just a word count factor or TFIDF factor over that vocabulary and let's imagine that for a given cluster。

Only one document in that cluster， again， I'm talking in terms of hard assignments。

 but things generalize。But if there's only one document in that cluster that has the wordW in it。

Or more generally， if all of the documents in that cluster happen to have the same count of a specific word W。

 then what's the。嗯。Maximum likelihood estimate of the parameters in that cluster for that word w。

 so just looking at that dimension， well， we simply set the mean equal to that observed count。

 either from that one document or all these documents that have the same count。

 and then we shrink the variance to zero about that value。

So this isn't actually that contrived of an example because if we're in a very high dimensional space。

 so a very large vocabulary。We really could imagine cases where all the documents in a given cluster。

 especially if we have enough clusters to partition up our data。

 all the observations in a given cluster might not have a word at all。

 or there might just be one document that has the word so this kind of setup really。

 really can happen in high dimensions and what ends up happening as a result of this is that if in later iterations we go to compute the likelihood of some other document。

That has word W and some other count associated with word W than what this cluster is specified。

 then it's going to have zero likelihood or zero responsibilities assumed by this given cluster because this cluster says nope。

 you can only have this value that I've observed in my document so far。

 and so what we're going to see is that our responsibilities are going to shoot to either zero responsibilities if a document doesn't agree on that just this one dimension。

 this one vocabulary word or it's going to be one if we're in that cluster and have agreement on that dimension。

And I want to actually emphasize that really the way that you end up seeing this in practice is with an underflow issue。

 so you're going to get these covariance matrices and you can't compute their inverse even when you're shrinking the variance is very。

 very small and not even setting them exactly equal to zero。

 so this can be just a practical issue where your code's going to break if you don't correct for this potential issue。

And there's a very simple fix that we can consider。

 which we're going to call either smoothing the parameter estimate or regularizing our EM updates。

 and this simple fix is just not to let our variance parameters go to zero and to do this every time we go to estimate our covariance we're simply going to add a very small diagonal term to that covariance matrix to ensure that none of the variances are zero。

As an alternative approach， you can take a more formal Bayesian approach and place priors over the model parameters。

 so the cluster proportions， the means and covariances of the mixture model。

And what you can view this as is placing what are called pseudo observationsations in each one of the clusters。

 so it's as if you've fixed some set of observations with some values in every cluster and that's going to bias our maximum likelihood estimates to account for those observations and because of that structure。

 it's going to avoid cases where you degenerate by not having any actual observations of a certain value。

And so we can think of this as smoothing our parameter estimates， but in this basing approach。

 you would be smoothing the cluster proportions and the means and the covariances rather than this simple approach that we've specified here where we're just smoothing our covariance estimate。

And you're going to see this type of smoothing when you go to do EM for document clustering in the assignment。



![](img/8eeb826f04e4cee7fd707a6af73befc7_3.png)