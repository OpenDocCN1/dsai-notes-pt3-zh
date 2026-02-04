# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P17：P17 StatsLearning Lect6d 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/4ad34bb77d34130fb154b9a2099c9acb_0.png)

O。Now。We slip one thing by you。 We said in the South Africa， in South Africa。

 the the risk for heart disease is about5% in this category， in this age category。



![](img/4ad34bb77d34130fb154b9a2099c9acb_2.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_3.png)

But in our sample， we've got 160 cases and 302 controls。 So in the sample， we show in a risk of 0。35。



![](img/4ad34bb77d34130fb154b9a2099c9acb_5.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_6.png)

So it seems like the model is going to be off。 It's going to estimate probabilities too high。



![](img/4ad34bb77d34130fb154b9a2099c9acb_8.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_9.png)

Well， this is case control sampling is one of the favorite tools in epidemiology。

 especially when you have a rare disease。

![](img/4ad34bb77d34130fb154b9a2099c9acb_11.png)

You you take all the cases you can find， and then you can just sample from the controls。



![](img/4ad34bb77d34130fb154b9a2099c9acb_13.png)

And the reason is is that for the logistic regression model。



![](img/4ad34bb77d34130fb154b9a2099c9acb_15.png)

It turns out that you can estimate the regression parameters of interest。 These are the。

 the coefficients of the X's in this case。 Ac， that's if the model is correct。



![](img/4ad34bb77d34130fb154b9a2099c9acb_17.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_18.png)

But the constant term will be incorrect。

![](img/4ad34bb77d34130fb154b9a2099c9acb_20.png)

And then you can just go ahead and correct the constant term by simple transformation。



![](img/4ad34bb77d34130fb154b9a2099c9acb_22.png)

And， in fact， for those that are interested， I just give you the transformation。



![](img/4ad34bb77d34130fb154b9a2099c9acb_24.png)

So。Pytdeia is the apparent risk of heart disease。 In this case， in our population， which is 0。35。



![](img/4ad34bb77d34130fb154b9a2099c9acb_26.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_27.png)

And this is， after all， this is just the largerit transformation of that prior probability。



![](img/4ad34bb77d34130fb154b9a2099c9acb_29.png)

Or the apply apparent probability。

![](img/4ad34bb77d34130fb154b9a2099c9acb_31.png)

And here's the larger transformation of the true risk。Which is pi in this case，005。



![](img/4ad34bb77d34130fb154b9a2099c9acb_33.png)

And so we take the load transformation of those two， and we correct the intercept。

 This is the currently estimated intercept， and we correct it by adding in the log odds of the true。



![](img/4ad34bb77d34130fb154b9a2099c9acb_35.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_36.png)

Probability， subtract the parent one。 That corrects the inter Maybe it's worth saying about case control sampling。

 I why the sampling was done this way， one thing we could have done instead or the investigators could have done was to take maybe 1000 people and to follow them for 20 years。

 right and to record their risk factors and then see who gets heart disease and we think about 5% a good heart disease。



![](img/4ad34bb77d34130fb154b9a2099c9acb_38.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_39.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_40.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_41.png)

And that that's a valid wing thing to do。 But the problem is。

 it takes 20 years and maybe more than a few thousand people to get enough。

 actually the thousand people would get what 50 cases， right， But so that's not very practical。

 We need a large sample， and we need many years to do it。 Ca control sampling says， well。

 let's not do things prospectively like that。 Let's rather。



![](img/4ad34bb77d34130fb154b9a2099c9acb_43.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_44.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_45.png)

Find people who we already know have heart disease。Or don't have heart disease。 and then sample。

 sample them。AndNow， in the proportion of this case， you know。

 it will take 160 cases and 302 controls and then record the risk factors。

 So we start with cases and controls and we get lots of cases and we can do this without waiting 20 years。

 We can do it right now。And then we record the risk factors。 That's a good point Rob。 And that's。

 that's a very popular in， in epidemiology。 The the。

 the other issues involved with case control sampling， retrospective sampling。 and。

 but we won't take that up now。 But that's， that's the reason it's so popular。



![](img/4ad34bb77d34130fb154b9a2099c9acb_47.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_48.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_49.png)

On the same issue， you in many modern data sets。

![](img/4ad34bb77d34130fb154b9a2099c9acb_51.png)

We have。You know， we'll have very imbalanced situations。 For example。

 if you're model in the clickthrough rate on an ad on a web page。



![](img/4ad34bb77d34130fb154b9a2099c9acb_53.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_54.png)

The probability of someone clicking is is less than 1%， maybe 0005 or even smaller 0。001。



![](img/4ad34bb77d34130fb154b9a2099c9acb_56.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_57.png)

Which means if you just take a random sample of， of subject to being exposed to ads。

 you're gonna get very， very few ones and a huge amount of zeroes， okay。



![](img/4ad34bb77d34130fb154b9a2099c9acb_59.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_60.png)

And， and these data sets gets really large。 So the question is， do we need to use all of that 0。

1 data to fit the models？ Well， from what we've told you， no， you can take a sample of the controls。



![](img/4ad34bb77d34130fb154b9a2099c9acb_62.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_63.png)

And this picture over here just gives an indication of， of the trade off。



![](img/4ad34bb77d34130fb154b9a2099c9acb_65.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_66.png)

The point is， the main point is that ultimately the variance of your parameter estimates has to do with the number of cases that you got。

 which is a smaller class。

![](img/4ad34bb77d34130fb154b9a2099c9acb_68.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_69.png)

And so what this plot shows is it's showing the variance of the coefficients as a function of the case control ratio。



![](img/4ad34bb77d34130fb154b9a2099c9acb_71.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_72.png)

Or， in fact， a control case ratio。 And what it says is when you've got about 5 or 6 to 1。

 the variance kind of levels off。 Yeah， And， and so there's diminishing returns in in getting even more controls。

 So if you've got a very sparse situation， sample about 5 or6 controls for every case and， and。

 and now you can work with a much more manageable dataset set。 So it's very handy， especially in in。

 in modern， extremely large dataset sets。

![](img/4ad34bb77d34130fb154b9a2099c9acb_74.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_75.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_76.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_77.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_78.png)

So just a comment about what this case control sampling is。

The most obvious way to study the risk factors for a heart disease would be to take a large group of people。

 maybe 100 or 100，000 people。Fall them for maybe 20 years。

 record their risk factors then see who gets heart disease and who doesn't after 20 years。

 if you're still around if you're still run if we're still around right， now。

 that actually is a good way to do things except it's very expensive and takes a long time。

 You got to get a lot of people。 and you have to wait for many years。

 Ca control sampling is more attractive because what you do is rather than taking people and falling them forward in time。

 you you sample people who you know of heart disease。

You sample you also get a comparison sample of people who do not have heart disease that controls。

 and then you record their risk factors。 So it's much cheaper and it's much quicker to do。

 And that's why case control sampling is a very commonly used technique in epidemiology。 Okay。

 what if we have more than two classes， can we still do the logistic regression。



![](img/4ad34bb77d34130fb154b9a2099c9acb_80.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_81.png)

Well， we can。It， it easily generalises to more than two classes。 So one。

 and these various ways of doing this。 and one version。

 which actually is how we do it in the in the Gmnet package in R， which will。

 you'll be learning more about。

![](img/4ad34bb77d34130fb154b9a2099c9acb_83.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_84.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_85.png)

Is we have this， this exponential form that we saw before， but modified for multiple classes。



![](img/4ad34bb77d34130fb154b9a2099c9acb_87.png)

So notice in the numerative， we've got to E to the。



![](img/4ad34bb77d34130fb154b9a2099c9acb_89.png)

linearium model。And this is for the probability that Y is K given x a small K。

 And we've got to say capital K classes with K， capital K is bigger than 2。



![](img/4ad34bb77d34130fb154b9a2099c9acb_91.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_92.png)

And in the denominator， we've just got the sum of those exponentials for all the classes。



![](img/4ad34bb77d34130fb154b9a2099c9acb_94.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_95.png)

So in this case， each class gets a linear model。Its own linear model。

 And then we just weigh them against each other with this exponential function。

 sometimes called the softm function。

![](img/4ad34bb77d34130fb154b9a2099c9acb_97.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_98.png)

Okay。

![](img/4ad34bb77d34130fb154b9a2099c9acb_100.png)

嗯。The Ma of students will recognize that some cancellation is possible。



![](img/4ad34bb77d34130fb154b9a2099c9acb_102.png)

YeahIn， in， in this ratio。And that's true。 And what that means is actually you only need k minus1 linear functions。



![](img/4ad34bb77d34130fb154b9a2099c9acb_104.png)

As you do in a two class logistic regression， that's somewhat of a detail。

 And it turns out for our limitedinate application， this symmetric。

 this is a more symmetric representation， and it's actually more useful。



![](img/4ad34bb77d34130fb154b9a2099c9acb_106.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_107.png)

![](img/4ad34bb77d34130fb154b9a2099c9acb_108.png)

This multiclass logistic regression is also referred to as multiomial regression。



![](img/4ad34bb77d34130fb154b9a2099c9acb_110.png)