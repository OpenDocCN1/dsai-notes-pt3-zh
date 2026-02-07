# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P35：-035-Statistical Learning_ 6.2 Stepwise Selection.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

。So。As I mentioned earlier， we're talking about best subset selection here for least squares。

 but we can just as well do this for logistic regression or for any other type of model。

And in particular， when we're talking about other types of models。

 we don't usually talk about residual sum squares， instead we talk about something that's called the deviance。

 which is negative two times the log likelihood。And in the case of least squares。

 the deviance and the residual summa squares are equivalent， but for other model types。

 the deviance is really just a generalization of residual summa squares。

 but here we're going to talk about residual summa squares for simplicity。



![](img/069bee4acc884d500153f5d7b4c79f23_1.png)

So， you know in that figure we were looking at a couple slides ago with the credit data。

 we saw that there were all of those gray dots， and I mentioned that there's actually two to the10 gray dots in that picture。

And the idea is that if I have access to P predictors and I want to consider every possible submodel。

 I'm actually looking at2 to the P。😊，Subsets。And that is an absolutely huge number。

 So just to put this in perspective， you know， like 2 to the 10， that's like 1000。So that's okay。

 Fitting 1000 models。 If you've got a decent computer is no problem。But，2 to the 40。

Is a really big number。And so the idea is that。WhenWhen P is large。

 we're really not going to be able to do best subset selection and 40 predictors isn't large。

 like I work on data where there is easily tens or hundreds of thousands of predictors。

 and so bestet sub selection just does not scale for many of the types of problems that people are interested in today。

I think that limit for most packages that do subset selection is about 30 or 40 and beyond that。

 they just say I can't I can't look at all the combinations right so putting aside computational concerns though best subset selection also suffers from statistical problems and the idea is like if I'm considering gosh what is this this is a trillion models if I have 40 predictors and I'm considering a trillion models I'm going to overfit the data I'm just looking at so many models I'm going choose a model that looks really。

 really great on this data by chance， but it's not going to look great on an independent test set that I didn't use in training the model And so I'm going have a problem with overfitting。

And so for these two reasons， computational and statistical。😊。

Best subset selection isn't really great unless P is extremely small and in this setting。

 we can use stepwise methods， which sort of are the same idea as best subset selection。

 but they look at a more restricted set of models。 so instead of looking at 2 to the P models。

 they look at more like p squared models and of course，2 p is much more than p squared。😊。

For for any P of any reasonable size。 for this point， element is actually some counterintuitive。

 especially people in computer science might think it's always best to do the most exact computation you can。

 if you can do the optimization over all models。It's usually felt to be better。

 but Daniel says something that's actually quite a somewhat counterintuitive that actually。

To to avoid fitting too hard， it's good to actually not look at all possible models。

 but only a subset of the models。 So For stepwise regression。

 which we'll look at stepwise and For stepwise in particular。

Doesn't try to look at all possible models， despite the fact that in cases when P is less than Four you can look at all possible models。

 it may not be the best thing to do that so for stepwise on purpose looks only at a subset of the models and that can actually be helpful Yeah so I mean best subset selection what would PB if you're going to use it and what would be your limit where if P is larger than that number you wouldn't want to go beyond best subset。

And wouldnt want to use best upset maybe not beyond 10 or 20 say yeah I don't think I would probably even use it for 20 I mean I think I would use best absolute set if I've got a handful of predictors and if I've got 10 I wouldn't be using that anymore most likely now so the point is it's not always best to do a full search even when you can do it because you pay a price in variance。

So now we're going to talk about these two stepwise methods forward and backward stepwise。

 and these are really pretty similar， but there's just one fundamental difference which is whether you're starting with a model with no predictors or you're starting with a model with all the predictors so in forward stepwise selection we start with a model that contains no predictors this is just a model with only the intercept it's what we were calling the null model M0 earlier。



![](img/069bee4acc884d500153f5d7b4c79f23_3.png)

And then we're going to add predictors to the model one at a time until all of the predictors are in the model。

So this sounds like best subset selection， but there's actually a really major difference。

 which is that at each step， we're not looking at every single possible model in the universe that contains key predict K predictors。

 We're just looking at the models that contain the K minus-1 predictors that we already chose in the previous step plus one more。

 So at the K step， we're looking at a much， much， much more restricted set of models than than we are in best subset selection。



![](img/069bee4acc884d500153f5d7b4c79f23_5.png)

![](img/069bee4acc884d500153f5d7b4c79f23_6.png)

![](img/069bee4acc884d500153f5d7b4c79f23_7.png)

![](img/069bee4acc884d500153f5d7b4c79f23_8.png)

![](img/069bee4acc884d500153f5d7b4c79f23_9.png)

In particular at each step， we're just going to choose the variable that gives the biggest improvement to the model we just had a moment earlier。



![](img/069bee4acc884d500153f5d7b4c79f23_11.png)

So the idea behind forward stepwise selection is that once again we start with this model M0。

 it's the null model and it just contains an intercept。

 so you're just going to predict the mean for every observation。

And then we're going to try to create a model M1， and the model M1 is going to just contain one more predictor than M0。

 So we're just going to take M0， and we're going to look for the best predictor to add that's going to lead to the smallest RSS or the largest r squared。



![](img/069bee4acc884d500153f5d7b4c79f23_13.png)

![](img/069bee4acc884d500153f5d7b4c79f23_14.png)

So that gives us M1。And now in order to get M2， we're going to take M1。



![](img/069bee4acc884d500153f5d7b4c79f23_16.png)

And we're going to consider adding every predictor that we can we're going to consider adding all p -1 possible predictors to M1。

 And we're going to see which of those P minus-1 predictors gives us the best model M2。



![](img/069bee4acc884d500153f5d7b4c79f23_18.png)

![](img/069bee4acc884d500153f5d7b4c79f23_19.png)

And to get M3， we look at M2， we consider adding all p minus2 predictors that aren't in M2。

 we choose the best one， and that gives us M3 and so on。

So the really key thing here is that in this step， this is different from what we were doing in the best subset selection case。

 because here we're not looking at every possible model containing K predictors instead we're just looking at every possible model that contains one more predictor than mK minus-1 we're going to take the model we just got and we're just going to add one predictor to it to get a slightly bigger model。



![](img/069bee4acc884d500153f5d7b4c79f23_21.png)

![](img/069bee4acc884d500153f5d7b4c79f23_22.png)

![](img/069bee4acc884d500153f5d7b4c79f23_23.png)

![](img/069bee4acc884d500153f5d7b4c79f23_24.png)

So just like in best subset selection， we're going to get p plus1 models from M0 to MP。

 but the difference is that these models are nested。

SoM1 contains the predictor in M0 plus1 more M2 contains M1 plus one more predictor M3 contains the predictors in M2 plus1 more。

 and so on。 these models are nested in a way that wasn't the case for a best subset selection。



![](img/069bee4acc884d500153f5d7b4c79f23_26.png)

So after we get these P+1 models， we are going to choose among them， and as I mentioned earlier。

 we can't use RSS or R squared to choose among these P+1 models because they all have different sizes。

 and in a few minutes we'll talk about some approaches like crossvalidation and AIC and BIC to choose among these P+1 models。



![](img/069bee4acc884d500153f5d7b4c79f23_28.png)

![](img/069bee4acc884d500153f5d7b4c79f23_29.png)

![](img/069bee4acc884d500153f5d7b4c79f23_30.png)

![](img/069bee4acc884d500153f5d7b4c79f23_31.png)

![](img/069bee4acc884d500153f5d7b4c79f23_32.png)

So。We've said that。That forward stepwise selection has a computational advantage over best subset selection。



![](img/069bee4acc884d500153f5d7b4c79f23_34.png)

And just to really reiterate why that's true in best upset selection。

We're considering two to the P models， which as we said， is like a trillion when p equals 40。

But in contrast， in forward stepwise selection。For M0， we're just considering one model。

And to get M1， we're considering adding P different predictors， so we're considering P models。For M2。

 we're considering adding P -1 additional predictors。 So that's P -1 models。



![](img/069bee4acc884d500153f5d7b4c79f23_36.png)

And so on。And so actually， when we do forward to stepwise selection。

 we're considering around p squared models。😊。

![](img/069bee4acc884d500153f5d7b4c79f23_38.png)

![](img/069bee4acc884d500153f5d7b4c79f23_39.png)

And so P squared is much less than2 to the P。 So we're considering far fewer predictors when we do forward stepwise。

 And here's another picture to help see what's going on。 Don't see if I can draw it。

 But we think of the RS picture。

![](img/069bee4acc884d500153f5d7b4c79f23_41.png)

![](img/069bee4acc884d500153f5d7b4c79f23_42.png)

It a function of model size， remember this is RSS。

![](img/069bee4acc884d500153f5d7b4c79f23_44.png)

And for best subset。Member of it。

![](img/069bee4acc884d500153f5d7b4c79f23_46.png)

Of course， we said the career keeps going down。It might flatten out。



![](img/069bee4acc884d500153f5d7b4c79f23_48.png)

嗯。But so this is for a subset， you saw that before。



![](img/069bee4acc884d500153f5d7b4c79f23_50.png)

For Ford stepwise， it's also going to have the same shape but。It's not going to go down。

' going to be it might be it's going to be above that curve you so I'll start in the same place because for one variable it's going to pick the。

The same best variable， but it's going to be typically above。



![](img/069bee4acc884d500153f5d7b4c79f23_52.png)

That curve， not doing it very well。

![](img/069bee4acc884d500153f5d7b4c79f23_54.png)

Until the very end， whoops， that wasn't， these are meant to join at the end。

So the point is that Fort Stepwise is not doing a search among all possible models。

 so for a given model size。

![](img/069bee4acc884d500153f5d7b4c79f23_56.png)

![](img/069bee4acc884d500153f5d7b4c79f23_57.png)

It's going to have an RSS that might be above， typically will be above that for Ford for best subset。



![](img/069bee4acc884d500153f5d7b4c79f23_59.png)

嗯。

![](img/069bee4acc884d500153f5d7b4c79f23_61.png)

So yeah， I mean that relates to the fact that forward stepwise isn't actually guaranteed to find the best possible model out of all two to the P models best that best subset considers。

 so like if you look at Rob's picture right here the forward stepwise and best subset curves。

 oops have the same RSS because they each contain just the null model and then over here these two models are the same because forward stepwise and best subset are each considering the model with all P predictors so those are the same but in between there's this gap and the reason for the gap is because best subset selection is going to find the best model with let's say K predictors。

 but forward stepwise might not and the reason that it might not is because it could be that the best model containing K predictors is not a superet of the best model containing K minus1 predictors。



![](img/069bee4acc884d500153f5d7b4c79f23_63.png)

![](img/069bee4acc884d500153f5d7b4c79f23_64.png)

![](img/069bee4acc884d500153f5d7b4c79f23_65.png)

![](img/069bee4acc884d500153f5d7b4c79f23_66.png)

![](img/069bee4acc884d500153f5d7b4c79f23_67.png)

![](img/069bee4acc884d500153f5d7b4c79f23_68.png)

![](img/069bee4acc884d500153f5d7b4c79f23_69.png)

![](img/069bee4acc884d500153f5d7b4c79f23_70.png)

So we can actually see an example of that if we look a little more carefully at the credit data。

 so this table shows the results that you get fit if you look for M0， M1， M2。



![](img/069bee4acc884d500153f5d7b4c79f23_72.png)

M3 and M4 on the credit data。 So this is M1。

![](img/069bee4acc884d500153f5d7b4c79f23_74.png)

M2， M3， and M4。And so if we do a best subset selection， then M1 just contains rating。

The rating variable， and if we do forward stepwise， M1 just contains the rating variable。

 so it so far so good。

![](img/069bee4acc884d500153f5d7b4c79f23_76.png)

If we look at M2， then best subsets M2 contains rating and income。

 and same with forward stepwise as M2。

![](img/069bee4acc884d500153f5d7b4c79f23_78.png)

If we look at M3， best subset has rating income student and same thing with For stepwise rating income student。

 but when we get to M4， things suddenly changed because now in the context of a model with four variables。

 the best that we can do is cards， income， student and limit。😊。



![](img/069bee4acc884d500153f5d7b4c79f23_80.png)

![](img/069bee4acc884d500153f5d7b4c79f23_81.png)

But that is not a model that forward Stepwise can give us because remember。

 forward Stepwise can only give us a model that contains rating income student and one other variable。

 so forward Stepwise is going to give us rating income student and it's going to add in limit when we ask for the best model with four variables and in contrast。

 best subset isn't going to have rating， it's instead going to have cards and it's lost rating。



![](img/069bee4acc884d500153f5d7b4c79f23_83.png)

![](img/069bee4acc884d500153f5d7b4c79f23_84.png)

![](img/069bee4acc884d500153f5d7b4c79f23_85.png)

![](img/069bee4acc884d500153f5d7b4c79f23_86.png)

![](img/069bee4acc884d500153f5d7b4c79f23_87.png)

And so this M4 that best subset gives us is going to have a smaller residual sum of squares。



![](img/069bee4acc884d500153f5d7b4c79f23_89.png)

It's a different model than we would have gotten with forward stepwise。But you know。

 just because best subset has a better model on the training data doesn't mean that it's really going to be a better model overall in the context of test data。

 which is what we really care about one my point about that so you might wonder why this happens well it only happens when there's correlation between the features。



![](img/069bee4acc884d500153f5d7b4c79f23_91.png)

![](img/069bee4acc884d500153f5d7b4c79f23_92.png)

![](img/069bee4acc884d500153f5d7b4c79f23_93.png)

It's pretty easy to show that if the variables were had no correlation。

 then the variables chosen by the two methods would be exactly the same。

 because of the correlation between the features， which is typically there。

 you can get a discrepancy between best subset and fourth stepaway。



![](img/069bee4acc884d500153f5d7b4c79f23_95.png)

![](img/069bee4acc884d500153f5d7b4c79f23_96.png)

![](img/069bee4acc884d500153f5d7b4c79f23_97.png)