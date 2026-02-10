# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P71：30_模型选择 第1部分.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

So hi and welcome to the lecture on multiple variables in this lecture we're going to talk about the process of model fitting when you have lots of variables in a regression context。



![](img/aee44f9ce805033b40cbfca9ec882876_1.png)

I'd like to distinguish between multivariable regression and the kinds of things that you'll learn in your prediction class as part of the data science specialization。



![](img/aee44f9ce805033b40cbfca9ec882876_3.png)

In prediction， we're less concerned with interpretability。

 so we're far more intolerant for complex models， lots of interactions。

 and automated search algorithms and rules to come up with the best prediction with respect to a specific loss function。

In contrast in a lot of regression examples we want simple interpretable models。

 that means we're going to place a heavy emphasis on the idea of parsimonian。

 finding the simplest model to explain what we're looking at。

 but so simplest possible but no simpler， that's the idea of parsimonia it has kind of the flavor of Oham's razor which states that all else being equal。

 the simplest solution is probably the right one， well here all else being equal。

 we're going to prefer a simple model rather than a complex one。



![](img/aee44f9ce805033b40cbfca9ec882876_5.png)

And that has broad consequences so if a。Variable in a regression model explains a tiny bit extra amount of variation。

 but really harms the interpretability we're going to omit that variable。

 even if it really does explain a little bit of positive amount of variability。



![](img/aee44f9ce805033b40cbfca9ec882876_7.png)

![](img/aee44f9ce805033b40cbfca9ec882876_8.png)

啊。So。I also like to bring up this quote by Scott Zieger who。



![](img/aee44f9ce805033b40cbfca9ec882876_10.png)

It really helps me think about what I'm going for when I look at models so he likes to think of a model as a lens through which you're looking at the data so in that context your model is neither right nor wrong。

Any model that teaches you something valuable about your data is right as long as it teaches you something true。

And the idea of a lens is just sort of in the same vein that in some cases when you're looking at the world through a lens to find out super fine detail you might need a microscope to find out super high levell detail you might need a telescope and so the idea of a model being something like that where where you're looking at the same thing。

 but the right model might highlight the right feature that teaches you something true。

 so I think that's a very useful way to think about models。



![](img/aee44f9ce805033b40cbfca9ec882876_12.png)

For a specific instance， where we're interested in say。

 a treatment effect or something like that where there really is either a treatment effect or not average across the population that we're interested in。



![](img/aee44f9ce805033b40cbfca9ec882876_14.png)

There are uncountably many ways that our model can be wrong and lead us astray。

 lead us to conclude that there is a treatment effect when there's not one or lead us to conclude that there's not a treatment effect when there is one and in this particular lecture。

 we're going to go through some basics of what happens when we either include unnecessary regressors or exclude important regressors。



![](img/aee44f9ce805033b40cbfca9ec882876_16.png)

![](img/aee44f9ce805033b40cbfca9ec882876_17.png)

![](img/aee44f9ce805033b40cbfca9ec882876_18.png)

![](img/aee44f9ce805033b40cbfca9ec882876_19.png)

I'd like to bring up this quote by Donald Rumsfeld。

He was the sort of embattled Secretary of Def from the US and he was widely derided for this specific quote。

  however， it's very pertinent to the idea of regression。And it goes something like this。

 there are no knowns， these are things we know that we know。Then there are known unknowns。

 that is to say that there are things that we know we don't know。But there are also unknown unknowns。

 there are things we don't know， we don't know and so this quote was again heavily criticized。

 but for regression it makes a lot of sense， known knowns are regressors that we know we should include in our model and we have recorded so we just put them in。



![](img/aee44f9ce805033b40cbfca9ec882876_21.png)

![](img/aee44f9ce805033b40cbfca9ec882876_22.png)

![](img/aee44f9ce805033b40cbfca9ec882876_23.png)

There are known unknowns， and these are things that we know we should include in our regression model。

 but unfortunately we didn't collect them。

![](img/aee44f9ce805033b40cbfca9ec882876_25.png)

![](img/aee44f9ce805033b40cbfca9ec882876_26.png)

And therere unknown unknowns， and these are things that we should include in our regression model。

 for example， but we didn't collect them or don't have them or don't know whether or not they're important。



![](img/aee44f9ce805033b40cbfca9ec882876_28.png)

![](img/aee44f9ce805033b40cbfca9ec882876_29.png)

So you know， I think this is a funny little quote， but it gives us an idea of。You know， the various。



![](img/aee44f9ce805033b40cbfca9ec882876_31.png)

Lines of thinking that you have to go through when building a regression model。

So let's talk about some general rules for our known knowns， unknown unknowns and known unknowns。

So what happens if we omit a variable that we should have included and the general result is that results in bias。

 in other words you get if you're interested in a treatment effect or an effective interest for a particular regressor。

And you've omitted something that's correlated with that regressor。

 then you're potentially going to get biased， you're not going to get an accurate estimate of what you want to estimate because of this other variable now one way to prevent that is to try and randomize because if this other variable that you're oting is uncorrelated with the variable that you're interested in。

 then it doesn't matter usually whether you include it or not。

 so randomization is a strategy to try to prevent that from happening。

 that's why AB testing is so powerful， clinical trials are so powerful。



![](img/aee44f9ce805033b40cbfca9ec882876_33.png)

![](img/aee44f9ce805033b40cbfca9ec882876_34.png)

![](img/aee44f9ce805033b40cbfca9ec882876_35.png)

![](img/aee44f9ce805033b40cbfca9ec882876_36.png)

But then I would remind you if there's too many confounded things。

 then even randomization is not going to help you。

![](img/aee44f9ce805033b40cbfca9ec882876_38.png)

So that means that omitting variables that are important obviously has a negative impact on our regression model fit What about including variables that are unimportant is that a bad thing Well we eliminate bias there's no consequence to bias if we include unnecessary variables so if you just generate a bunch of standard normals and throw them into your regression model。

 they have nothing to do with anything they're not going to introduce bias however。

 they are going to they are going to inflate standard errors so introducing unnecessary variables into your regression model inflates the standard errors and we can actually measure how much it would。



![](img/aee44f9ce805033b40cbfca9ec882876_40.png)

![](img/aee44f9ce805033b40cbfca9ec882876_41.png)

Increase the actual standard errors， not just the estimated standard errors。

The other thing is some of these model terms like r squared。

 they're not necessarily good ways to adjudicate between looking at different models with different regressors in。

 and the reason with R squared is as you put in a bunch of new regressors。

 it's guaranteed to go up no matter what。

![](img/aee44f9ce805033b40cbfca9ec882876_43.png)

![](img/aee44f9ce805033b40cbfca9ec882876_44.png)

![](img/aee44f9ce805033b40cbfca9ec882876_45.png)

![](img/aee44f9ce805033b40cbfca9ec882876_46.png)

In the sum of the squared errors， the mean squared errors is guaranteed to go down in a regression as to include more regressiongressors so here's an example where I just simulated a bunch of data and I readed the simulation for every number of regressors and just included them into a model and it just shows the R squared just going up even though all I'm doing is generating a bunch of random normal vectors in putting them in a regression model。



![](img/aee44f9ce805033b40cbfca9ec882876_48.png)

![](img/aee44f9ce805033b40cbfca9ec882876_49.png)