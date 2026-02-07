# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P35：P35 StatsLearning Lect8de 111713.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/7e52b57fa472fea66be6726d0e22fac3_0.png)

So what I need is actually a way to estimate the test error。For each of these models。

 M0 M1 M2 all the way through MP so that I can choose among them。



![](img/7e52b57fa472fea66be6726d0e22fac3_2.png)

And basically， in order to estimate the test error， I have two approaches。

And one approach is that I can indirectly estimate the test error by somehow computing the training error and then adjusting it。



![](img/7e52b57fa472fea66be6726d0e22fac3_4.png)

And the idea behind this adjustment is that if I can somehow adjust the training error to account for the bias due to overfitting。

Then that can give me。An estimate of。

![](img/7e52b57fa472fea66be6726d0e22fac3_6.png)

Test error that's again based on the training error， but somehow looks more like a test error。



![](img/7e52b57fa472fea66be6726d0e22fac3_8.png)

And the alternative approach is that I can try to directly estimate the test error。

 and I can do that using some of the approaches that are in chapter5 of this book and those involve either crossvalidation or a validation set approach。

 and so that's a really direct approach to estimating the test error where I fit models on part of the data and then I evaluate them on a holdout set。



![](img/7e52b57fa472fea66be6726d0e22fac3_10.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_11.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_12.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_13.png)

So we're now going to talk about both of these approaches。



![](img/7e52b57fa472fea66be6726d0e22fac3_15.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_16.png)

So CP， AIC， BIC， and adjusted R squared all adjust the training error in order to give us an estimate of the test error。



![](img/7e52b57fa472fea66be6726d0e22fac3_18.png)

And they all can be used to select among models with different numbers of variables。



![](img/7e52b57fa472fea66be6726d0e22fac3_20.png)

So we're now going to look at a figure showing us CP。

 BIC and adjusted R squared for the best model of each size that we get using F subset selection on the credit data。

 so we're first going to look at this figure and then we'll talk about how these quantities are defined。



![](img/7e52b57fa472fea66be6726d0e22fac3_22.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_23.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_24.png)

So again， this is on the credit data example。

![](img/7e52b57fa472fea66be6726d0e22fac3_26.png)

And on the X axis here， we have the number of predictors in each of these figures。



![](img/7e52b57fa472fea66be6726d0e22fac3_28.png)

And on the Y axis， we have CP。BIC， which stands for Bayesian Information Criiterion。

And adjusted r squared and again， we'll define all three of these quantities in a minute。

 but the idea is roughly speaking we want these quantities to be small。

 so we prefer a model in which CP， BIC and are as small as possible and actually I misspoke we want adjusted r squared to be as large as possible。



![](img/7e52b57fa472fea66be6726d0e22fac3_30.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_31.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_32.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_33.png)

So if I look at the shape of this curve， I can see that CP is minimized。😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_35.png)

When we look at the model with six predictors。VIC is smallest when we look at the model with four predictors。



![](img/7e52b57fa472fea66be6726d0e22fac3_37.png)

And adjusted r squared is smallest when we look at a model with six predictors again。😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_39.png)

So that suggests that we should use somewhere between four and six predictors。



![](img/7e52b57fa472fea66be6726d0e22fac3_41.png)

And actually， if we look at these figures a little more closely。

 we can see that basically these curves are more or less flat after we get to around three or four predictors。



![](img/7e52b57fa472fea66be6726d0e22fac3_43.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_44.png)

And so on the basis of these figures， I would say， I really don't think we need more than three or max4 predictors to do a good prediction on this credit data。



![](img/7e52b57fa472fea66be6726d0e22fac3_46.png)

So， you know， and I've scribbled all over the slot oops something on this picture it's hard to see here but actually the curve is going upright as we go to the right despite the fact it's flat That's right likeS exactly it's a little hard to see but this is slightly increasing at smallest with four predictors and then it goes up a little bit but you know I don't really think that there's compelling evidence here that that four is really better than three or better than five so if it were me you know I think simpler is always better so I probably choose a model with you know three predictors maximum four predictors agree。



![](img/7e52b57fa472fea66be6726d0e22fac3_48.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_49.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_50.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_51.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_52.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_53.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_54.png)

Great， so now we're going to talk about MalOCP and once again this is an adjustment to the training R squared。

 the training RSS that gives us an estimate for the test RSS， and it's defined in this formula。

 so let's say we're looking at a model with D predictors。😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_56.png)

So then we're going to calculate the RSS for that model with D predictors。

 and we're going to add to the RSS2 times D。

![](img/7e52b57fa472fea66be6726d0e22fac3_58.png)

Where again these is the number of predicts times sigma hat squared。

 where sigma hat squared is an estimate of the variance associated with each error epsilon。😊。

And the linear model。And so the idea is we can calculate CP for those models M0 M1 M2 through MP that we were looking at a few minutes ago。

 and we can just choose the model with the smallest CP。



![](img/7e52b57fa472fea66be6726d0e22fac3_60.png)

So like if we're looking at the model M3。

![](img/7e52b57fa472fea66be6726d0e22fac3_62.png)

Then that model contains three predictors in an intercept， so that model has d equals 4。



![](img/7e52b57fa472fea66be6726d0e22fac3_64.png)

And we can calculate the RSS for the Model M3， and we just calculate sigma hat squared。

 there's a formula for that。It gives us a CP。

![](img/7e52b57fa472fea66be6726d0e22fac3_66.png)

And out of all these models m0 and MP， we're just going to choose the one for which the CP is smallest because that's the one that we believe is going to have the smallest tests at RSS just to clarify a bit about the Sigma hat squared。

 first of all， if P is bigger than N we're going to have a problem right because。



![](img/7e52b57fa472fea66be6726d0e22fac3_68.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_69.png)

Well typically sigma hat squared， the same values， the same estimates is used for all models being compared。

 so usually what I do is you fit the full model， all P predictors。

 and you take the mean square residual for that model to give a sigma hat squared。



![](img/7e52b57fa472fea66be6726d0e22fac3_71.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_72.png)

So that's the way you do it， and of course， that's going to create a problem in P bigger than N because that full model was not defined and the error will be zero。



![](img/7e52b57fa472fea66be6726d0e22fac3_74.png)

So already we see that CP is restricted to cases where you've got n bigger than P。



![](img/7e52b57fa472fea66be6726d0e22fac3_76.png)

That's right。And even a P is close to N， you're going to have a problem because you're asking the sigma squared might be。

Far too low。So that's Mallow CP， and then another very closely related idea is called the AIC criterion。

 so the AIC stands for a kiki information criterion。

 akeki was the name of the guy who came up with this idea。😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_78.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_79.png)

And the way that this is defined is negative2 log L plus 2 times d。

 where D is once again the number of predictors in the model that I'm looking at。

 so for M3 d equals 4。

![](img/7e52b57fa472fea66be6726d0e22fac3_81.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_82.png)

And now capital L here is the maximized value of the likelihood function for the estimated model。😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_84.png)

So this looks a little bit complicated， and in fact it's written in this very general way because AIC is a quantity that we can calculate from many different model types。

 not just linear models， but also logistic regression and so on。



![](img/7e52b57fa472fea66be6726d0e22fac3_86.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_87.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_88.png)

But it turns out that in the case of a linear model。Negative 2 log L。



![](img/7e52b57fa472fea66be6726d0e22fac3_90.png)

Is just equal to RSS over sigma hat squared。

![](img/7e52b57fa472fea66be6726d0e22fac3_92.png)

So if you look at that and you plug in RSS over sigma hatt squared for negative 2 log L。

 then what you realize is that AIC。

![](img/7e52b57fa472fea66be6726d0e22fac3_94.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_95.png)

And mallow CP are actually proportional to each other。

And since we're just going to choose the model for which。



![](img/7e52b57fa472fea66be6726d0e22fac3_97.png)

CP is smallest， that's equivalent to choosing the model for which AIC is smallest。



![](img/7e52b57fa472fea66be6726d0e22fac3_99.png)

So AIC and CP are actually really the same thing for linear models， but for other types of models。

 these things are not the same and AIC is a good approach。



![](img/7e52b57fa472fea66be6726d0e22fac3_101.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_102.png)

So we've talked about CP and AIC。And another very related idea here is the BIC。

 where B stands for Bayesian， so this is the Bayesian information criterion。

 and it's like the AIC and this MallowCP， but it comes from sort of a Bayesian argument。😊。

And once again， we've got a very similar formula， we calculate the residual sum of squares。



![](img/7e52b57fa472fea66be6726d0e22fac3_104.png)

And then we add an adjustment term， which is the log of the number of observations， times D。

 which is once again the number of predictors in the model I'm looking at， so like M3。

 since it has three predictors in an intercept， M3 has d equals4。



![](img/7e52b57fa472fea66be6726d0e22fac3_106.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_107.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_108.png)

And once again， sigma hat squared is an estimate of the error of variance。

 which may or may not be available depending on whether n is greater than p or less than p。😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_110.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_111.png)

And so once again with BIC， we're estimating the test set RSS。



![](img/7e52b57fa472fea66be6726d0e22fac3_113.png)

or rather the average tests at RSS across the observations and so we want it to be as small as possible。

 so we're going to choose the model with the smallest BIC。



![](img/7e52b57fa472fea66be6726d0e22fac3_115.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_116.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_117.png)

So what's the difference between BIC and AIC？

![](img/7e52b57fa472fea66be6726d0e22fac3_119.png)

Well， remember AIC， had it would look just like this， but in AIC。

 this term was actually 2D sigma hat squared， right？😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_121.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_122.png)

So the only difference between AIC and BIC is the choice of log n versus 2。



![](img/7e52b57fa472fea66be6726d0e22fac3_124.png)

VIC has this login here。And。

![](img/7e52b57fa472fea66be6726d0e22fac3_126.png)

And AIC has it too。And so in general。If n is greater than7。Then log n is greater than two。

And so what that means is that if you have more than seven observations in your data。

 BIC is going to put more of a penalty on a large model， and in other words。

 BIC is going to tend to choose smaller models than AIC is。😊。



![](img/7e52b57fa472fea66be6726d0e22fac3_128.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_129.png)

So BIC is going to give you the selection of models that have fewer variables than either CP or AIC。



![](img/7e52b57fa472fea66be6726d0e22fac3_131.png)

So we see that these three ideas， BICC， CP， and AIC are really almost identical。

 they just have slightly different formulas。

![](img/7e52b57fa472fea66be6726d0e22fac3_133.png)

They we want to minimize them， and they all require an estimate。



![](img/7e52b57fa472fea66be6726d0e22fac3_135.png)

First Sigma hat squared， which again is not available necessarily。



![](img/7e52b57fa472fea66be6726d0e22fac3_137.png)

If it's only going to be available if n is greater than P。



![](img/7e52b57fa472fea66be6726d0e22fac3_139.png)

So the last of these approaches that I'm going to talk about that sort of indirectly adjusts the training error to get an estimate of the test error is the adjusted R squared。



![](img/7e52b57fa472fea66be6726d0e22fac3_141.png)

And so we saw in chapter three the idea of the r squared。 and remember。

 r squared was defined just as a little refresher。

![](img/7e52b57fa472fea66be6726d0e22fac3_143.png)

R squared is defined as1 minus the residual summa squared。



![](img/7e52b57fa472fea66be6726d0e22fac3_145.png)

Divided by the total sum of squares。

![](img/7e52b57fa472fea66be6726d0e22fac3_147.png)

Where。In case we need a reminder， the total sum of squares is just the。



![](img/7e52b57fa472fea66be6726d0e22fac3_149.png)

S of y I minus y bar squared。 So y bar is the average response。 Y I is the Ih response。

 and we're just taking the sum of those squared values。And so this was the r squared， and as we know。

 a big r squared indicates a model that really fits the data well， but unfortunately。

 models by you can't compare models of different sizes by just taking the one with the biggest r squared because you can't compare the r squared of a model with three variables to the r squared of a model with eight variables。

 for instance。So the adjusted r squared tries to fix this。

 and the way that it does that is that it makes you pay a price for having a large model。

 so the idea is adjusted r squared adjusts the r squared so that the values that you get are comparable even if the numbers of predictors are different。

😊，So the way that it does this is by adding a denominator。To the。To RSS and to TSS in this ratio。

 so instead of just taking1 minus RSS over TSS， we take1 minus RSS over n minus d minus1。

Divided by TSS over n minus1。Where again， D is the number of variables in the model that we're considering。

And so basically the idea here。Is that when D is large， this denominator is really large。

 and so you're dividing the RSS by a really big number and you're going to end up with a smaller r squared。

So what's happening is that we're going to pay a price for having a large model in the adjusted r squared。

Unlike the classical r squared， where we don't pay no price for having a large model with a lot of features。

So the adjusted r squared， we want it to be large， if it's large and that indicates a model that really fits the data well。



![](img/7e52b57fa472fea66be6726d0e22fac3_151.png)

And again， the idea is that adjusted r squared is something that we can actually compare in a meaningful way regardless of the number of predictors in the model Some just noticed looks like it doesn't require an estimate if Sigma squared。

 that's good and you can also apply it when p' is bigger than n Yeah that's right。

 so that's a really nice advantage of RSS as Rob said we don't need to estimate Sigma squared which can be a problem and in principle we can apply it when P is larger than n。



![](img/7e52b57fa472fea66be6726d0e22fac3_153.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_154.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_155.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_156.png)

So we want a large value of adjusted r squared。😊。

![](img/7e52b57fa472fea66be6726d0e22fac3_158.png)

And and so the adjusted r squared in practice people really like it。

 it tends to work really well so some statisticians don't like it as much as CPAIC and BIC and the reason is because it sort of works well empirically but some statisticians feel that it doesn't kind of have the theoretical backing of some other approaches。

 what do you think about Rob。

![](img/7e52b57fa472fea66be6726d0e22fac3_160.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_161.png)

that's true there is a bias in our field towards things which have more theory behind them and I guess this the example of that but one nice thing about adjusted R squared is like if you're working with someone who's not a statistician like scientists who aren't statisticians are really familiar with R squared and so from when to understand R squared adjusting R squared is just a really small one off and it's kind of easier to explain to someone in a certain sense then AICC or BIC and so that's one really nice thing about it but adjusted R squared you can't really generalize to other types of models so if you have like logistic regression you can't do this so you'll see in the next section we talk about crossfo which is our favorite method。



![](img/7e52b57fa472fea66be6726d0e22fac3_163.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_164.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_165.png)

which you can generalitalize and one major advantages is you don't need to know D。

 so the D in this method in adjusted R squared and CP and AIC is a number of parameters。

 but some methods like Ri regression and the Laso， which we'll also talk about。



![](img/7e52b57fa472fea66be6726d0e22fac3_167.png)

![](img/7e52b57fa472fea66be6726d0e22fac3_168.png)

Again in a few minutes the value of D is not even known so we can't apply any of these methods but cross validation can still be applied yeah that's true so like in this whole discussion I've been talking about least squares models and then I've been occasionally mentioning logistic regression but I could have some totally crazy model that I come up with that like is like something that nobody's ever seen before and it would be totally hopeless to apply an AIC type of idea to it or an adjusted our squared type of idea but I can always perform cross validation or the validation set approach no matter how wacky my model is and that's actually a really nice thing about those two approaches。

