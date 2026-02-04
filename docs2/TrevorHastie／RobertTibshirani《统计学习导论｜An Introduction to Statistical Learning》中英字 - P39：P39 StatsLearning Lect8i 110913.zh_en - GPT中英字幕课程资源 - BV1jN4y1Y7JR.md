# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P39：P39 StatsLearning Lect8i 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

So let's talk a bit about。It's like a tuning parameter for Rigeraion in thelaso。

First point is that's important， the Lada very strongly determines the solution over a broad spectrum。

 when lamb does zero， we get fully squares， there's no regularization。When labs infinity。

 we get a zero solution in both cases。Choosing Lambda is extremely important and cross validation is the way that is a good technique for doing that。

 note also that we couldn't use the other methods because the D isn't known。

 What other methods am I talking about CP and AIC and B IC。They all require a number of parameters D。

And it's not clear what D is now， that's actually something interesting to think about。

 I've well suppose Ive I've done a Ri regression with I started with the 45 variables like in the credit data。

I use a certain Lada。Let's go back to that。

![](img/2f5d99af1e693c4aed839b590e8d05aa_1.png)

Just so I can point at something in example。U。

![](img/2f5d99af1e693c4aed839b590e8d05aa_3.png)

Here's our rich example， suppose I decide to use the Lambda。



![](img/2f5d99af1e693c4aed839b590e8d05aa_5.png)

Of， of 100， right， and。

![](img/2f5d99af1e693c4aed839b590e8d05aa_7.png)

I'm here and I ask you， well what's the D for that model， How many parameters have I fit？ Well。

 if I count the number of parameters， the number of non zero coefficients。

 it's still the the full number 11。

![](img/2f5d99af1e693c4aed839b590e8d05aa_9.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_10.png)

Because none of the coefficients are zero， so in a sense。All of my variables are still there。

 so my D number parameters is still is still P 11， but that doesn't somehow seem right right because I've shrunk in the coefficient。

 so they're not fully。

![](img/2f5d99af1e693c4aed839b590e8d05aa_12.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_13.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_14.png)

The number of degrees of freedom isn't as large。

![](img/2f5d99af1e693c4aed839b590e8d05aa_16.png)

So there's a bit of a subtle point here that the number of parameters is not just。

How many parameters I've used， but how I fit them so with Ri regression and Lasso。

 the shrinkage actually affects the very idea of what we mean by number of parameters。



![](img/2f5d99af1e693c4aed839b590e8d05aa_18.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_19.png)

So that was a long way of saying that。For selecting the。嗯。To0 parameter for Rich Gren and Laso。

 it's really important to use a method that doesn't require the value of D because it's hard to know what D is。

So cross validation fits the bill perfectly。We do exactly what we did for the other methods for subset selection。

 for example， we divide the data up into K parts。We fit the model the same k equals 10。

We fit the model on nine parts。Say we apply rich regression for a whole range of lambmbdas。

For the nine parts， and then we record the error on the tenth0th part。

We do that in turn for all 10 parts playing the role of the validation set。

 and then we add up all the errors together and we get a cross validation curve as a function of Lada。

Same for the Laso， so conceptually it's exactly the same as we。

s crossfi exactly the same as we applied it the end for other methods。

So let's see what it looks like here for。For Ri regression。



![](img/2f5d99af1e693c4aed839b590e8d05aa_21.png)

Here's the result of cross validation。um。

![](img/2f5d99af1e693c4aed839b590e8d05aa_23.png)

I'm not sure if was either either five or  ten fold we can check。

Here's cross Foundation as a function of Lada。

![](img/2f5d99af1e693c4aed839b590e8d05aa_25.png)

Again， remember lambda equals small means essentially the least squares model。

 full least squares over here。

![](img/2f5d99af1e693c4aed839b590e8d05aa_27.png)

And lambda equals large means the coefficient have been driven to 0。

 So if this is the cross foundation error as a function。



![](img/2f5d99af1e693c4aed839b590e8d05aa_29.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_30.png)

Of lambda and the minimum is occurring。Around here， around 0。05。



![](img/2f5d99af1e693c4aed839b590e8d05aa_32.png)

Here's， here's the same same thing now。 but well you plot it as a function of lambdaly standardized coefficient。

 So this is。

![](img/2f5d99af1e693c4aed839b590e8d05aa_34.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_35.png)

Here are the coefficients feature of the predictors。

They're profiles and we see how they vary as a function of Lada。



![](img/2f5d99af1e693c4aed839b590e8d05aa_37.png)

So again， over here there fully squares。And here they've been， as they moved to the right。

 they're shrunken。

![](img/2f5d99af1e693c4aed839b590e8d05aa_39.png)

And at the minimum value of the curve， this broken line we get。



![](img/2f5d99af1e693c4aed839b590e8d05aa_41.png)

A bunch of guys， which were essentially zero。

![](img/2f5d99af1e693c4aed839b590e8d05aa_43.png)

But not exactly zero because this is ragging not Laso。

 and then here are the coefficients for the three active variables。



![](img/2f5d99af1e693c4aed839b590e8d05aa_45.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_46.png)

嗯。And here's for the， this is our this is the。

![](img/2f5d99af1e693c4aed839b590e8d05aa_48.png)

Simulated data with n equals 50， I think there were two or three truly non zero coefficients in the population。



![](img/2f5d99af1e693c4aed839b590e8d05aa_50.png)

For the last so， this is now the result of cross validation。



![](img/2f5d99af1e693c4aed839b590e8d05aa_52.png)

We appliedlow the cross validation error versus the L1 norm of the Laso solution divided by the L1 norm of the foli square solution。

 this just to give you a convenient way of scaling the x axis so that it goes from zero to1 right the fo squares estimates。



![](img/2f5d99af1e693c4aed839b590e8d05aa_54.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_55.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_56.png)

It givesive us a value of one。

![](img/2f5d99af1e693c4aed839b590e8d05aa_58.png)

And the zero estimates that 0 give you a value of 0。 And in between。

 we have the the intermediate laso solutions。

![](img/2f5d99af1e693c4aed839b590e8d05aa_60.png)

So here it's cross validation curve。 again， it's got that you shaped on theella mentioned before。

 and its minimum is is it around。

![](img/2f5d99af1e693c4aed839b590e8d05aa_62.png)

Here about0。1。

![](img/2f5d99af1e693c4aed839b590e8d05aa_64.png)

Which is quite severe shrinkage， which is good here right because we know that the true model has only three nonze coefficients。

 and I think it's actually two even better okay two nonze coefficients and very good because here we seem to picked up exactly two nonze coefficients。

 the green and the red and the rest are exactly zero。 So it's in this。



![](img/2f5d99af1e693c4aed839b590e8d05aa_66.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_67.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_68.png)

![](img/2f5d99af1e693c4aed839b590e8d05aa_69.png)

Made up example， it's done exactly the right thing。



![](img/2f5d99af1e693c4aed839b590e8d05aa_71.png)

Correct two non zero features and set everything else exactly equal to zero。



![](img/2f5d99af1e693c4aed839b590e8d05aa_73.png)