# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P31：30_模型选择第1部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

![](img/5a9ce2ac4cbb312edc6521164a8b672a_0.png)

So hi and welcome to the lecture on multiple variables in this lecture we're going to talk about the process of model fitting when you have lots of variables in a regression context。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_2.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_3.png)

I'd like to distinguish between multivariable regression and the kinds of things that you'll learn in your prediction class as part of the data science specialization。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_5.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_6.png)

In prediction， we're less concerned with interpretability。

 so we're far more intolerant for complex models， lots of interactions。

 and automated search algorithms and rules to come up with the best prediction with respect to a specific loss function。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_8.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_9.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_10.png)

In contrast in a lot of regression examples we want simple interpretable models。

 that means we're going to place a heavy emphasis on the idea of parsimonian。

 finding the simplest model to explain what we're looking at。

 but so simplest possible but no simpler， that's the idea of parsimonia it has kind of the flavor of Oham's razor which states that all else being equal。

 the simplest solution is probably the right one， well here all else being equal。

 we're going to prefer a simple model rather than a complex one。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_12.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_13.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_14.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_15.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_16.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_17.png)

And that has broad consequences so if a。

![](img/5a9ce2ac4cbb312edc6521164a8b672a_19.png)

Variable in a regression model explains a tiny bit extra amount of variation。

 but really harms the interpretability we're going to omit that variable。

 even if it really does explain a little bit of positive amount of variability。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_21.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_22.png)

啊。So。I also like to bring up this quote by Scott Zieger。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_24.png)

It reallyally helps me think about what I'm going for when I look at models so he likes to think of a model as a lens through which you're looking at the data so in that context your model is neither right nor wrong。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_26.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_27.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_28.png)

Any model that teaches you something valuable about your data is right as long as it teaches you something true。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_30.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_31.png)

And the idea of a lens is just sort of in the same vein that in some cases when you're looking at the world through a lens to find out super fine detail you might need a microscope to find out super high levell detail you might need a telescope and so the idea of a model being something like that where where you're looking at the same thing。

 but the right model might highlight the right feature that teaches you something true。

 so I think that's a very useful way to think about models。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_33.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_34.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_35.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_36.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_37.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_38.png)

For a specific instance， where we're interested in say， a treatment effect or something like that。

 where there really is either a treatment effect or not average across the population that we're interested in。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_40.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_41.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_42.png)

There are uncountably many ways that our model can be wrong and lead us astray。

 lead us to conclude that there is a treatment effect when there's not one or lead us to conclude that there's not a treatment effect when there is one and in this particular。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_44.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_45.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_46.png)

Lure we're going to go through some basics of what happens when we either include unnecessary regressors or exclude important regressors。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_48.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_49.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_50.png)

I'd like to bring up this quote by Donald Rumsfeld。

He was the sort of em battlettled Secretary of Defense from the US and he was widely derided for this specific quote。

  however it's very pertinent to the idea of regression， and it goes something like this。

 there are no knowns， these are things we know that we know。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_52.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_53.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_54.png)

Then there are known unknowns， that is to say there are things that we know we don't know。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_56.png)

But there are also unknown unknowns， there are things we don't know， we don't know。

 and so this quote was again heavily criticized， but for regression it makes a lot of sense。

 known knowns are regressors that we know we should include in our model and we have recorded so we just put them in。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_58.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_59.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_60.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_61.png)

There are known unknowns， and these are things that we know we should include in our regression model。

 but unfortunately we didn't collect them。

![](img/5a9ce2ac4cbb312edc6521164a8b672a_63.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_64.png)

And there are unknown unknowns， and these are things that we should include in our regression model。

 for example， but we didn't collect them or don't have them or don't know whether or not they're important。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_66.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_67.png)

So， you know I think this is a funny little quote， but it gives us an idea of。You know， the various。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_69.png)

Lines of thinking that you have to go through when building a regression model。

So let's talk about some general rules for our known knowns， unknown unknowns and known unknowns。

So what happens if we omit a variable that we should have included and the general result is that results in bias in other words you get if you're interested in a treatment effect or an effective interest for a particular regressor and you've omitted something that's correlated with that regressor then you're potentially going to get bias you're not going to get an accurate estimate of what you want to estimate because of this other variable now one way to prevent that is to try and randomize because if this other variable that you're oting is uncorrelated with the variable that you're interested in。

 then it doesn't matter usually whether you're included or not so randomization is a strategy to try to prevent that from happening that's why AB testing is so powerful and clinical trials are so powerful。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_71.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_72.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_73.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_74.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_75.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_76.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_77.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_78.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_79.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_80.png)

But then I would remind you if there's too many confounded things。

 then even randomization is not going to help you。

![](img/5a9ce2ac4cbb312edc6521164a8b672a_82.png)

So that means that omitting variables that are important obviously has a negative impact on our regression model fit what about including variables that are unimportant is that a bad thing Well we eliminate bias there's no consequence to bias if we include unnecessary variables so if you just generate a bunch of standard normals and throw them into your regression model they have nothing to do with anything they're not going to introduce bias however。

 they are going to they are going to inflate standard errors so introducing unnecessary variables into your regression model inflates the standard errors and we can actually measure how much it would。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_84.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_85.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_86.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_87.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_88.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_89.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_90.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_91.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_92.png)

Increase the actual standard errors， not just the estimated standard errors。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_94.png)

The other thing is some of these model terms like r squared。

 they're not necessarily good ways to adjudicate between looking at different models with different regressors in。

 and the reason with R squared is as you put in a bunch of new regressors。

 it's guaranteed to go up no matter what。

![](img/5a9ce2ac4cbb312edc6521164a8b672a_96.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_97.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_98.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_99.png)

In the sum of the squared errors， the mean squared errors is guaranteed to go down in a regression as to include more regressiongressors。

 so here's an example where I just simulated a bunch of data and I readed the simulation for every number of regressors and just included them into a model and it just shows the R square just going up even though all I'm doing is generating a bunch of random normal vectors and putting them in a regression model。



![](img/5a9ce2ac4cbb312edc6521164a8b672a_101.png)

![](img/5a9ce2ac4cbb312edc6521164a8b672a_102.png)