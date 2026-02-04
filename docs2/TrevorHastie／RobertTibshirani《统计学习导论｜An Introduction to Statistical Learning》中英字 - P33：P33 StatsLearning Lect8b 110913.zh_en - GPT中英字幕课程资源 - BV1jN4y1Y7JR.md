# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P33：P33 StatsLearning Lect8b 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/5b1ef7b1f5affc37f07abcf5e971a807_0.png)

So。You know，As I mentioned earlier， we're talking about best subset selection here for least squares。

 but we can just as well do this for logistic regression or for any other type of model。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_2.png)

And in particular， when we're talking about other types of models。

 we don't usually talk about residual sum squares， instead of we talk about something that's called the deviance。

 which is negative two times the log likelihood。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_4.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_5.png)

And in the case of least squares， the deviance and the residual summa squares are equivalent。

 but for other model types， the deviance is really just a generalization of residual summa squares。

 but here we're going to talk about residual summa squares for simplicity。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_7.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_8.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_9.png)

So， you know in that figure we were looking at a couple slides ago with the credit data。

 we saw that there were all of those gray dots， and I mentioned that there's actually two to the10 gray dots in that picture。

And the idea is that if I have access to P predictors and I want to consider every possible submodel。

 I'm actually looking at2 to the P。😊，Subsets。And that is an absolutely huge number。

 So just to put this in perspective， you know， like 2 to the 10， that's like 1000。So that's okay。

 Fitting 1000 models if you've got a decent computer is no problem。But2 to the 40。

Is a really big number。And so the idea is that。When P is large。

 we're really not going to be able to do best subset selection and 40 predictors isnt large。

 like I work on data where there's easily tens or hundreds of thousands of predictors。

 and so bestet up selection just does not scale for many of the types of problems that people are interested in today。

I think that limit for most packages that do subset selection is about 30 or 40 and beyond that they just say I can't I can't look at all the combinations right so putting aside computational concerns though best subset selection also suffers from statistical problems and the idea is like if I'm considering gosh what is this this is a trillion models if I have 40 predictors and I'm considering a trillion models I'm going to overfi the data I'm just looking at so many models I'm going to choose a model that looks really。

 really great on this data by chance but it's not going to look great on an independent test set that I didn't use in training the model and so I'm going to have a problem with overfitting。

And so for these two reasons， computational and statistical。😊。

Best subset selection isn't really great unless P is extremely small and in this setting。

 we can use stepwise methods， which sort of are the same idea as best subset selection。

 but they look at a more restricted set of models。 So instead of looking at two to the P models。

 they look at more like p squared models and of course，2 p is much more than p squared。

For any P of any reasonable size， for this point， the element is actually pretty some counterintuitive。

 especially people in computer science might think it's always best to do the most exact computation you can if you can do the optimization over all models。

It's usually felt to be better， but Daniel has something that's actually quite somewhat counterintuitive that actually。

To avoid fitting too hard， it's good to actually not look at all possible models。

 but only a subset of the models。 So For stepwise regression。

 which we'll look at stepwise and For stepwise in particular。

Doesn't try to look at all possible models， despite the fact that in cases when P is less than4 so you can look at all possible models。

 it may not be the best thing to do that so for it stepwise on purpose looks only at a subset of the models and that can actually be helpful Yeah so I mean best subset selection what would PB if you're going to use it what would be your limit where if P is larger than that number you wouldn't want to go beyond best subset？

I wouldn't want to use best upset maybe not beyond 10 or 20 say yeah I don't think I would probably even use it for 20 I mean I think I would use best obole said if I've got a handful of predictors and if I've got 10 I wouldn't be using that anymore most likely so the point is it's not always best to do a full search even when you can do it because you pay a price in variance。

So now we're going to talk about these two stepwise methods forward and backward stepwise。

 and these are really pretty similar， but there's just one fundamental difference which is whether you're starting with a model with no predictors or you're starting with a model with all the predictors。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_11.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_12.png)

So in forward stepwise selection， we start with a model that contains no predictors。

 This is just a model with only the intercept。 It's what we were calling the null model M0 earlier。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_14.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_15.png)

And then we're going to add predictors to the model one at a time until all of the predictors are in the model。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_17.png)

So this sounds like best subset selection， but there's actually a really major difference。

 which is that at each step， we're not looking at every single possible model in the universe that contains key predict K predictors。

 we're just looking at the models that contain the K minus1 predictors that we already chose in the previous step plus one more so at the K step。

 we're looking at a much much， much more restricted set of models than we are in best subset selection。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_19.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_20.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_21.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_22.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_23.png)

In particular at each step， we're just going to choose the variable that gives the biggest improvement to the model we just had a moment earlier。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_25.png)

So the idea behind forward stepwise selection is that once again we start with this model M0。

 it's the null model， and it just contains an intercept。

 so you're just going to predict the mean for every observation。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_27.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_28.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_29.png)

And then we're going to try to create a model M1 and the model M1 is going to just contain one more predictor than M0。

 So we're just going to take M0 and we're going to look for the best predictor to add that's going to lead to the smallest RSS or the largest r squared。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_31.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_32.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_33.png)

So that gives us M1。And now in order to get M2， we're going to take M1。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_35.png)

And we're going to consider adding every predictor that we can we're going to consider adding all p minus1 possible predictors to M1。

 and we're going to see which of those p minus1 predictors gives us the best model M2。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_37.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_38.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_39.png)

And to get M3， we look at M2， we consider adding all p minus2 predictors that aren't in M2。

 we choose the best one， and that gives us M3 and so on。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_41.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_42.png)

So the really key thing here is that in this step， this is different from what we were doing in the best subset selection case。

 because here we're not looking at every possible model containing K predictors instead we're just looking at every possible model that contains one more predictor than MK minus1 we're going to take the model we just got and we're just going to add one predictor to it to get a slightly bigger model。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_44.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_45.png)

So just like in best subset selection， we're going to get p plus1 models from M0 to MP。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_47.png)

But the difference is that these models are nested。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_49.png)

So MP M1 contains the predictor in M0 plus one more。 M2 contains M1 plus one more predictor。

 M3 contains the predictors in M2 plus one more and so on。

 These models are nested in a way that wasn't the case for a best subset selection。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_51.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_52.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_53.png)

So after we get these P+1 models， we are going to choose among them， and as I mentioned earlier。

 we can't use RSS or R squared to choose among these P+1 models because they all have different sizes。

 and in a few minutes we'll talk about some approaches like cross validationidation and AIC and BIC to choose among these P+1 models。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_55.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_56.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_57.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_58.png)

So。We we've said that。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_60.png)

That For stepwide selection has a computational advantage over best subset selection。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_62.png)

And just to really reiterate why that's true in best upset selection。

We're considering two to the P models， which as we said， is like a trillion when p equals 40。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_64.png)

But in contrast， in forward step by selection。For M0， we're just considering one model。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_66.png)

And to get M1， we're considering adding P different predictors。 So we're considering P models。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_68.png)

For M2， we're considering adding P -1 additional predictors。 So that's P -1 models。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_70.png)

And so on。And so actually， when we do forward stepwise selection。

 we're considering around p squared models。😊。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_72.png)

And so P squared is much less than2 to the P。 So we're considering far fewer predictors when we do forward stepwise。

 And here's another picture to help see what's going on and don't see if I can draw it。

 but if we think of the RSS picture。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_74.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_75.png)

It a function of model size， remember this is RSS。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_77.png)

And for best subset。Member it。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_79.png)

Of course， we said the curve keeps going down。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_81.png)

It might have flattened out。A。But for so this is for a subset。I saw that before。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_83.png)

For Ford stepwise， it's also going to have the same shape， but。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_85.png)

It's not going to go down， going to be it might be it's going to be above that curve you so I'll start in the same place because for one variable it's going to pick the。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_87.png)

The same best variable。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_89.png)

It's going to be typically above。That curve meant doing it very well。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_91.png)

Until the very end， whoops， that wasn't， these are meant to join at the end。

So the point is that For Stepwise is not doing a search among all possible models so for a given model size。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_93.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_94.png)

It's going to have an RSS that might be above， typically will be above that Ford for best subset。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_96.png)

嗯。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_98.png)

So yeah， I mean that relates to the fact that forward stepwise isn't actually guaranteed to find the best possible model out of all two to the P models that best subset considers。

 so like if you look at Rob's picture right here the forward stepwise and best subset curves， oops。

 have the same RSS because they each contain just the null model and then over here these two models are the same because forward stepwise and best subset are each considering the model with all P predictors so those are the same but in between there's this gap and the reason for the gap is because best subset selection is going to find the best model with let's say K predictors。

 but forward stepwise might not， and the reason that it might not is because it could be that the best model containing K predictors is not a superet of the best model containing K minus1 predictors。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_100.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_101.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_102.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_103.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_104.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_105.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_106.png)

So we can actually see an example of that if we look a little more carefully at the credit data。

 so this table shows the results that you get fit if you look for M0， M1， M2，😊。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_108.png)

M3 and M4 on the credit data。 So this is M1。M2， M3， and M4。And so if we do a best subset selection。

 then M1 just contains rating。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_110.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_111.png)

The rating variable， and if we do forward stepwise， M1 just contains the rating variable。

 so it's so far so good。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_113.png)

If we look at M2， then best subsets M2 contains rating and income。

 and same with forward stepwise as M2。

![](img/5b1ef7b1f5affc37f07abcf5e971a807_115.png)

If we look at M3， best subset has rating income student and same thing with For stepwise rating income student。

 but when we get to M4， things suddenly changed because now in the context of a model with four variables。

 the best that we can do is cards， income student and limit。😊。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_117.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_118.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_119.png)

But that is not a model that forward stepwise can give us because remember forward stepwise can only give us a model that contains rating income student and one other variable。

 so forward Stepwise is going to give us rating income student and it's going to add in limit when we ask for the best model with four variables and in contrast。

 best up isn't going to have rating， it's instead going to have cards and it's lost rating。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_121.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_122.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_123.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_124.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_125.png)

And so this M4， the best subset gives us is going to have a smaller residual sum of squares。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_127.png)

It's a different model than we would have gotten with forward stepwise。But you know。

 just because best Up has a better model on the training data doesn't mean that it's really going to be a better model overall in the context of test data。

 which is what we really care about one my point about that so you might wonder why this happens well it only happens when there's correlation between the features。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_129.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_130.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_131.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_132.png)

It's pretty easy to show that if the variables were had no correlation。

 then the variables chosen by the two methods would be exactly the same。

 but because of correlation between the features， which is typically there。

 you can get a discrepancy between best subset and fourth stepwise。



![](img/5b1ef7b1f5affc37f07abcf5e971a807_134.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_135.png)

![](img/5b1ef7b1f5affc37f07abcf5e971a807_136.png)