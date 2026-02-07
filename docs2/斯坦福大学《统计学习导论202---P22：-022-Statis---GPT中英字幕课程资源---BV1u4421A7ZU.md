# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P22：-022-Statistical Learning_ 4.2 Logistic Regression.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

Okay， logistic regression。 So now we're going to get a little bit more May。



![](img/227e8bfba934f8809adfa885c6b526b2_1.png)

Let's for shorthand， write P of x for the probability that y is1 given x。



![](img/227e8bfba934f8809adfa885c6b526b2_3.png)

![](img/227e8bfba934f8809adfa885c6b526b2_4.png)

And。And we're going consider our simple model， a simple model for predicting default。 Yes or no。

 using balance， one of the variables。 So a single variable。



![](img/227e8bfba934f8809adfa885c6b526b2_6.png)

![](img/227e8bfba934f8809adfa885c6b526b2_7.png)

So here's the form of logistic regression。

![](img/227e8bfba934f8809adfa885c6b526b2_9.png)

So that E is the， is the。The， the scientific constant， the， the exponential value。And we raise E to。

 to the power of a linear model。 We've got a beta 0， which is the intercept。

 and beta 1 is the coefficient of x。And。You see that appears in the numerator and in the denominator。

 But there's one plus in the denominator。So it's a somewhat complicated expression， but you can。

 you can， you can see straight away that the values have to lie between 0 and 1。



![](img/227e8bfba934f8809adfa885c6b526b2_11.png)

![](img/227e8bfba934f8809adfa885c6b526b2_12.png)

![](img/227e8bfba934f8809adfa885c6b526b2_13.png)

Because in the numerator， we eat anything is positive。And。And in the new。

 and and the denominator is bigger than the numerator。 So it's always going to be bigger than 0。

And you can show that it's got to be less than one when， when beta 0 plus beta x gets very large。

 this approach is one。 So this is a special construct。

 a transformation of a linear model to guarantee that what we get out is a probability。😊。



![](img/227e8bfba934f8809adfa885c6b526b2_15.png)

So that's called the logistic regression model。

![](img/227e8bfba934f8809adfa885c6b526b2_17.png)

And actually， the name logistic comes from the transformation of this model。

 So this called this is a monotone transformation。 We take log of P of x over 1 minus P of x。



![](img/227e8bfba934f8809adfa885c6b526b2_19.png)

![](img/227e8bfba934f8809adfa885c6b526b2_20.png)

And out pops our linear model。 And that transformation is called the log odds or the logit transformation of the probability。

And this is the model that we're gonna talk about right now。 to summarizemar。

 we're got a linear model stool。

![](img/227e8bfba934f8809adfa885c6b526b2_22.png)

But it's smarting the probabilities on a nonlinear scale。And so back to our picture， again。

 there's the， the， the picture on the right was produced by a logistic regression model。 And。

 and that's why the probabilities lie between 0 and 1。



![](img/227e8bfba934f8809adfa885c6b526b2_24.png)

So。We've written down the model。 How do we estimate the model from。From data。Well。

 the popular way is to use maximum likelihoodli。Maximum likelihood was introduced by Huro。Or me。

 actually。 yes， this last week。 Did you reinvent it I didn't realize it was actually， Yeah。

 because the correct answer is Fisher back in the 1920s， Ronald Fisher， Fisher。



![](img/227e8bfba934f8809adfa885c6b526b2_26.png)

![](img/227e8bfba934f8809adfa885c6b526b2_27.png)

Donald Fisher， a very famous statistician， invented a lot of the tools that we use in。

 in modern applied statistics。 and maximum likelihood is one of them。



![](img/227e8bfba934f8809adfa885c6b526b2_29.png)

Well， the way maximum likelihood works is you've got a data series of observed zeros and ones。



![](img/227e8bfba934f8809adfa885c6b526b2_31.png)

And you've got a model for the probabilities。 And that model involves parameters。 In this case。

 beta 0 and beta。So for any values of the parameters。

 we can write down the probability of the observed data。

And since each observation is meant to be independent of each other one。

 the probability of the observed data is is， is， is the probability of the observed string of zero and ones。

So wherever we observed a1， we write down the probability of a 1， which is P of x。

 So if X I of observation， I was a1。The probability is P of Xi。And we write that down。

And since they're all independent， we just multiply these probabilities。

 And these are the probabilities of a 0， which is  one minus the probability of a  one。



![](img/227e8bfba934f8809adfa885c6b526b2_33.png)

So this is the joint probability of the observed sequence of zeros and ones。



![](img/227e8bfba934f8809adfa885c6b526b2_35.png)

And of course， it involves the parameters。And so the idea of maximum likelihood is pick the parameters to make that probability as large as possible。

 because after all， you did observe the sequence of zeros and ones。



![](img/227e8bfba934f8809adfa885c6b526b2_37.png)

And so， so that's the idea， simpleple to say， not always simple to execute， but luckily。

 we have programs that can do this。 And， for example， in， in R， we've got the GLM function。

 which in a， in a snap over a finger will fit this model for you and estimate the parameters。



![](img/227e8bfba934f8809adfa885c6b526b2_39.png)

And in this case， this is what it produced。The coefficient estimates were -10 for the intercept and 0005。

5 for the slope for balance。 That's beta and beta 0。It also gives you this。

 So they're the coefficient estimates。 It also gives you standard errors for each of the coefficient estimates。

It computes E statistic， and it also gives you P values。 Oh， I think I realized something。

 So you had a picture a couple slides ago of the， the curve。 Yes， and is that how you found the。

 it was wondering how you found the parameters for that curve。 Is that how you found。

 That's exactly right， Rob。

![](img/227e8bfba934f8809adfa885c6b526b2_41.png)

![](img/227e8bfba934f8809adfa885c6b526b2_42.png)

![](img/227e8bfba934f8809adfa885c6b526b2_43.png)

So。

![](img/227e8bfba934f8809adfa885c6b526b2_45.png)

This curve over year。Is the curve corresponding to those estimates that we' just produced in the table。



![](img/227e8bfba934f8809adfa885c6b526b2_47.png)

And you might be surprised because the slope is very smaller。R。Yet it。

 it seemed to produce such a big change in the probabilities。That may be a typo。I certainly hope not。

But let's， let's look a bit closer。 Look at the units of balance。They in dollars， right。

 So we got $2000，$2500。

![](img/227e8bfba934f8809adfa885c6b526b2_49.png)

And so the， the values of the coefficients， which are going to multiply that balance variable。They。

 they sort of take into account the units that are used， right。



![](img/227e8bfba934f8809adfa885c6b526b2_51.png)

So this， this is 00，05。Per dollar。Right， but it would be 5 per thousand dollars。 right， So slopes。

 you have to take the units into account。

![](img/227e8bfba934f8809adfa885c6b526b2_53.png)

And so the Z statistic， which is a kind of standardized slope， does that。

 And then if we look at the P value， we see that the the chance that actually this。

 this balance slope is 0 is very small， less than 0。001。 So both intercept and slope。

 strongly significant in this case。 How do I interpret that P value for the intercept。

 Do I care about that。

![](img/227e8bfba934f8809adfa885c6b526b2_55.png)

![](img/227e8bfba934f8809adfa885c6b526b2_56.png)

We usually don't care so much about the， the P value for the intercept。Yeah。

 the intercepts largely to do with， with the， the preonnderance of， of zeros and ones in the。

 in the data set。And， you know， and that's。And， and so that's less of less importance。

 That's just inherent in the data set。 It's a slope。 that's really important。

What do we do with this model， We can predict probabilities。

And so let's suppose we take a person with a balance of $1，000。



![](img/227e8bfba934f8809adfa885c6b526b2_58.png)

Well， we can estimate their probabilities。 so we just plug in the thousand dollars into this formula over year and notice I've put hats on beta 0 and beta 1 to indicate that they have now been estimated from the data。

 put a hat on the probability。

![](img/227e8bfba934f8809adfa885c6b526b2_60.png)

![](img/227e8bfba934f8809adfa885c6b526b2_61.png)

![](img/227e8bfba934f8809adfa885c6b526b2_62.png)

And yeah， we've plugged in the numbers and we use our calculator or computer and we get 0006。

So somebody with a balance of $1000 has a probability of 0。0，06 of defaulting， in other words。

 pretty small。

![](img/227e8bfba934f8809adfa885c6b526b2_64.png)

What if they got a credit card balance of $2000。

![](img/227e8bfba934f8809adfa885c6b526b2_66.png)

That means they， they owe $2000 rather than $1000。 Well， if we go through the same procedure， now。

 the probabilities jumped up to 0586。 So it's got much higher。



![](img/227e8bfba934f8809adfa885c6b526b2_68.png)

![](img/227e8bfba934f8809adfa885c6b526b2_69.png)

And you can imagine if we put in $3000， we'd get home and higher。

Let's do this again using some of the other variables。 We haven't seen student yet。

 but one of our predictors is student。 and it's a， it's a binary variable in this case。

 It's a yes or no variable is is the， is the。

![](img/227e8bfba934f8809adfa885c6b526b2_71.png)

![](img/227e8bfba934f8809adfa885c6b526b2_72.png)

The credit card owner， a student or not。And so we code that as a 0，1 variable。

 and we fit a simple logistic regression model。 and it gets a。Coeient of 0。4049。



![](img/227e8bfba934f8809adfa885c6b526b2_74.png)

And that's also significant。Okay， let's do it again using the variable student as a predictor。

 This is a binary variable。 Is， is the credit card holder student or not。



![](img/227e8bfba934f8809adfa885c6b526b2_76.png)

And we find we get a coefficient of 。4049 in this case， which is also significant。



![](img/227e8bfba934f8809adfa885c6b526b2_78.png)

So this is another variable in our database and just like before we can evaluate the probability of default is yes。

 given that the card old is a student， it comes out to 04。04。

 and if they're not a student it comes out to be a bit lower 。029 close to 0。03。

And we're going to examine the interactions between student and balance and other variables in a little while。



![](img/227e8bfba934f8809adfa885c6b526b2_80.png)

![](img/227e8bfba934f8809adfa885c6b526b2_81.png)