# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P18：-018-Statistical Learning_ 4.4 Logistic Regression Case Control Sampling and Mul - GPT中英字幕课程资源 - BV1yU421o7WA

![](img/568e4c391e080b25ebb10533cb90290e_0.png)

O。Now。We slip one thing by you。 We said in the South Africa， in South Africa， the， the。

 the risk for heart disease is about5，5% in this category， in this age category。



![](img/568e4c391e080b25ebb10533cb90290e_2.png)

But in our sample， we've got 160 cases and 302 controls。 So in the sample， we show in a risk of 0。35。

So it seems like the model is going to be off。 It's going to estimate probabilities too high。



![](img/568e4c391e080b25ebb10533cb90290e_4.png)

Well， this is case control sampling is is one of the favorite tools in epidemiology。

 especially when you have a rare disease。

![](img/568e4c391e080b25ebb10533cb90290e_6.png)

You， you take all the cases you can find， and then you can just sample from the controls。



![](img/568e4c391e080b25ebb10533cb90290e_8.png)

And the reason is is that for the logistic regression model。



![](img/568e4c391e080b25ebb10533cb90290e_10.png)

It turns out that you can estimate the regression parameters of interest。 These are the。

 the coefficients of the X's in this case。 Ac， that's if the model is correct。



![](img/568e4c391e080b25ebb10533cb90290e_12.png)

![](img/568e4c391e080b25ebb10533cb90290e_13.png)

But the constant term will be incorrect。

![](img/568e4c391e080b25ebb10533cb90290e_15.png)

And then you can just go ahead and correct the constant term by a simple transformation。



![](img/568e4c391e080b25ebb10533cb90290e_17.png)

And， in fact， for those that are interested， I just give you the transformation。



![](img/568e4c391e080b25ebb10533cb90290e_19.png)

So。Pytdeia is the apparent risk of heart disease。 In this case， in our population， which is 。35。

And this is， after all， this is just the larger transformation of that prior probability。

Or the prior apparent probability。And here's the load transformation of the true risk。

Which is pi in this case，05。And so we take the loaded transformation of those two。

 and we correct the intercept。 This is the currently estimated intercept。

 and we correct it by adding in the log odds of the tro。Probability， subtract the parent one。

 That corrects the intercept。 Maybe it's worth saying about case control sampling。

 I think why the sampling was done this way， One thing we could have done instead or the investigators could have done was to take maybe 1000 people and to follow them for 20 years。

 right， and to record the risk factors and then see who gets heart disease and we think about 5 per cent of good heart disease。

And that that's a valid wing thing to do。 But the problem is it takes 20 years and maybe more than a few thousand people to get enough。

 actually the thousand people would get what50 cases， right。But so that's not very practical。

 We need a large sample， and we need many years to do it。 Case control sampling says， well。

 let's not do things prospectively like that。 Let's rather。

Find people who we already know have heart disease。Or don't have heart disease。 And then sample。

 sample them。AndNow in the proportion of this case。

 you know it will take 160 cases and 302 controls and then record the risk factors。

 So we start with cases and controls and we get lots of cases and we can do this without waiting 20 years。

 We can do it right now。And then we record the risk factor。 that's a good point Dr。 And that's。

 that's a very popular in， in epidemiology。 Yeah， all the。

 the other the issues involved with case control sampling， retrospective sampling。 And。

 but we won't take that up now。 But that's， that's the reason it's so popular。On the same issue。

 you know in many modern data sets。

![](img/568e4c391e080b25ebb10533cb90290e_21.png)

We have。You know， we'll have very imbalanced situations。 For example。

 if you're modeling the clickthrough rate on an ad on a web page。

The probability of someone clicking is is less than 1%， maybe 0005 or even smaller 0。001。



![](img/568e4c391e080b25ebb10533cb90290e_23.png)

Which means if you just take a random sample of， of subject to being exposed to ads。

 you're going to get very， very few ones and a huge amount of zeros， okay。



![](img/568e4c391e080b25ebb10533cb90290e_25.png)

![](img/568e4c391e080b25ebb10533cb90290e_26.png)

And， and these data sets gets really large。 So the question is， do we need to use all of that 0。

1 data to fit the models？ Well， from what we've told you， no， you can take a sample of the controls。



![](img/568e4c391e080b25ebb10533cb90290e_28.png)

![](img/568e4c391e080b25ebb10533cb90290e_29.png)

And this picture over here just gives an indication of， of the trade off。



![](img/568e4c391e080b25ebb10533cb90290e_31.png)

![](img/568e4c391e080b25ebb10533cb90290e_32.png)

The point is the main point is that ultimately the variance of your parameter estimates has to do with the number of cases that you got。

 which is a smaller class。

![](img/568e4c391e080b25ebb10533cb90290e_34.png)

![](img/568e4c391e080b25ebb10533cb90290e_35.png)

And so what this plot shows is it's showing the variance of the coefficients as a function of the。

 the case control ratio。

![](img/568e4c391e080b25ebb10533cb90290e_37.png)

in fact， the control case ratio。 And what it says is when you've got about 5 or 6 to 1。

 the variance kind of levels off。 Yeah， and， and so there's diminishing returns in in getting even more controls。

 So if you've got a very sparse situation， sample about 5 or6 controls for every case and， and。

 and now you can work with a much more manageable dataset set。 So it's very handy， especially in。

 in modern， extremely large dataset sets。

![](img/568e4c391e080b25ebb10533cb90290e_39.png)

![](img/568e4c391e080b25ebb10533cb90290e_40.png)

So just a comment about what this case control sampling is。

The most obvious way to study the risk factors of a heart disease would be to take a large group of people。

 maybe 1000 or 100，000 people。Fall them for maybe 20 years。

 record their risk factors then see who gets heart disease and who doesn't after 20 years。

 if you're still around if you're still run if we're still around right。 Now。

 that actually is a good way to do things， except it's very expensive and takes a long time。

 You got to get a lot of people。 and you have to wait for many years。

 Ca control sampling as more attractive because what you do is rather than taking people and following them forward in time。

 you you sample people who you know have heart disease。

You sample you also get a comparison sample people who do not have heart disease that controls。

 and then you record their risk factors。 So it's much cheaper and it's much quicker to do。

 And that's why case control sampling is a very commonly used technique in epidemiology。 Okay。

 what if we have more than two classes， can we still do the logistic regression。



![](img/568e4c391e080b25ebb10533cb90290e_42.png)

Well， we can。

![](img/568e4c391e080b25ebb10533cb90290e_44.png)

It， it easily generalises to more than two classes。 So one， and these various ways of doing this。

 and one version， which actually is how we do it in the in the Gmnet package in R， which we。

 you'll be learning more about。

![](img/568e4c391e080b25ebb10533cb90290e_46.png)

![](img/568e4c391e080b25ebb10533cb90290e_47.png)

![](img/568e4c391e080b25ebb10533cb90290e_48.png)

Is we have this exponential form that we saw before， but modified for multiple classes。

So notice in the numerative， you've got to E to the。Linear model。

And this is for the probability that Y is K given x a small K。 And we've got， say。

 capital K classes with K， capital K is bigger than two。And in the denominator。

 we've just got the sum of those exponentials for all the classes。So in this case。

 each class gets a linear model。Its own linear model。

 And then we just weigh them against each other with this exponential function。

 sometimes called the soft max function。Okay。

![](img/568e4c391e080b25ebb10533cb90290e_50.png)

嗯。The Maa students will recognize that some cancellation is possible。YeahIn， in， in this ratio。

And that's true。 and what that means is actually you only need k minus1 linear functions。

As you do in a two class logistic regression， that's somewhat of a detail。

 And it turns out for our limitedinate application， this symmetric。

 this is a more symmetric representation， and it's actually more useful。



![](img/568e4c391e080b25ebb10533cb90290e_52.png)

This multiclass logistic regression is also referred to as multinoial regression。

