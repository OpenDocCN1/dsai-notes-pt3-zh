# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P11：P11 StatsLearning Lect5d 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/5f52f3351ad4f88ba8e27a6471444e38_0.png)

Welcome back， we're not going to talk about some important questions in arise when you use regression in real problems。



![](img/5f52f3351ad4f88ba8e27a6471444e38_2.png)

So。Well， is at least one of the predictors useful in predicting the response。

 right that's sort of the first order question？

![](img/5f52f3351ad4f88ba8e27a6471444e38_4.png)

Is do the predictors on the whole have anything anything to say about the outcome， If not。

 we probably want to stop there。

![](img/5f52f3351ad4f88ba8e27a6471444e38_6.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_7.png)

But given that there is some effect overall。

![](img/5f52f3351ad4f88ba8e27a6471444e38_9.png)

Which of the predictors are important， are they all important or only some subset？



![](img/5f52f3351ad4f88ba8e27a6471444e38_11.png)

How well does the model fit the data？

![](img/5f52f3351ad4f88ba8e27a6471444e38_13.png)

And also given a set of predictive values， what responsive that value should we predict。

 so what's our prediction of sales given a certain level of advertising in the three modes and how accurate is that prediction so these are all things we can answer from the model。



![](img/5f52f3351ad4f88ba8e27a6471444e38_15.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_16.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_17.png)

Well， at these one， two and four， three will examine by looking at some alternative models。



![](img/5f52f3351ad4f88ba8e27a6471444e38_19.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_20.png)

So。The answer the first question is at least one predictor use。

 does the model overall have any predictive value？

![](img/5f52f3351ad4f88ba8e27a6471444e38_22.png)

We do。

![](img/5f52f3351ad4f88ba8e27a6471444e38_24.png)

We look at the drop in training error， so this is the total sum of squares。

 if we just use the mean to predict， that's the no predictor model。



![](img/5f52f3351ad4f88ba8e27a6471444e38_26.png)

This is the residual sum the squares achieved using all three predictors。



![](img/5f52f3351ad4f88ba8e27a6471444e38_28.png)

嗯。

![](img/5f52f3351ad4f88ba8e27a6471444e38_30.png)

And。We can look at the drop， the present variance explained。



![](img/5f52f3351ad4f88ba8e27a6471444e38_32.png)

Which actually I've got here， whether for that， we defined this earlier， now it's 0。897。



![](img/5f52f3351ad4f88ba8e27a6471444e38_34.png)

So it was about 0。6 something before now by adding the two more predictors we've increased that to 0。

897， so this says that we reduced the variance of sales around its mean。



![](img/5f52f3351ad4f88ba8e27a6471444e38_36.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_37.png)

By almost 90%， by using these three predictors， that seems pretty impressive。



![](img/5f52f3351ad4f88ba8e27a6471444e38_39.png)

To quantify that in a more statistical way we can form。



![](img/5f52f3351ad4f88ba8e27a6471444e38_41.png)

The F ratio， which is defined as follows。

![](img/5f52f3351ad4f88ba8e27a6471444e38_43.png)

It's the drop in training error。Divided by P， P is the number parameters we fit here it's three。

 the three kinds of advertising budgets。

![](img/5f52f3351ad4f88ba8e27a6471444e38_45.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_46.png)

Divided by the mean squared residual。N is the sample size and we subtract off the number of parameters we fit。

 which is P。

![](img/5f52f3351ad4f88ba8e27a6471444e38_48.png)

Plus， one for the intercept。

![](img/5f52f3351ad4f88ba8e27a6471444e38_50.png)

So statistical theory tells us that we can compute the statistic and under the null hypothesis that there's no effect of any of the predictors。



![](img/5f52f3351ad4f88ba8e27a6471444e38_52.png)

This will have a。An F distribution with P and n minus p minus1 degrees of freedom。



![](img/5f52f3351ad4f88ba8e27a6471444e38_54.png)

And again， there are tables of this or your computer program will compute this for you。



![](img/5f52f3351ad4f88ba8e27a6471444e38_56.png)

The ftistic here is huge。And it's P value。

![](img/5f52f3351ad4f88ba8e27a6471444e38_58.png)

I have't recorded here， but it's less than 。0001。 So this says what we kind of believe already looking at the。



![](img/5f52f3351ad4f88ba8e27a6471444e38_60.png)

At the previous tables in the graphs， If there's a strong effect here of the predictors on the outcome。

 they certainly have something to say about the。

![](img/5f52f3351ad4f88ba8e27a6471444e38_62.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_63.png)

The outcome。Okay， when we fit linear regression models。

 one of the things we have to do is decide on what are the important variables to include in the model。

 by the way。

![](img/5f52f3351ad4f88ba8e27a6471444e38_65.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_66.png)

This is not job anymore。Roobt asked me to do this section because it's a little hard for him。



![](img/5f52f3351ad4f88ba8e27a6471444e38_68.png)

Kiting。So。

![](img/5f52f3351ad4f88ba8e27a6471444e38_70.png)

The most direct approach is called all subsets or best subsets regression。

 so basically what you're going to do is you're going to compute the least squared foot for all the possible subsets of the variables and then choose between them based on some criterion that balances the training error with the model size。



![](img/5f52f3351ad4f88ba8e27a6471444e38_72.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_73.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_74.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_75.png)

Now， this might seem like a reasonable thing to do。If you have a small number of variables。



![](img/5f52f3351ad4f88ba8e27a6471444e38_77.png)

But it gets really hard when the number of variables gets large。



![](img/5f52f3351ad4f88ba8e27a6471444e38_79.png)

So if you've got P variables， there's  two to the P subsets。



![](img/5f52f3351ad4f88ba8e27a6471444e38_81.png)

And， you know， that2 to the P grows exponentially with the number of variables。 So， for example。

 when P is 40， the over a billion models。

![](img/5f52f3351ad4f88ba8e27a6471444e38_83.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_84.png)

So we're talking about subsets like a model might have variable 1，3 and 5 in it。

 That's a subset of size 3。And then another model might have a subset of size 4。

 and with 40 variables， there's over a billion such models。

 So that clearly becomes cumbersome searching through such a big model space。



![](img/5f52f3351ad4f88ba8e27a6471444e38_86.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_87.png)

And so what we need instead is an automated approach that searches that finds a subset of them。



![](img/5f52f3351ad4f88ba8e27a6471444e38_89.png)

And so we'll describe two commonly used approaches next。



![](img/5f52f3351ad4f88ba8e27a6471444e38_91.png)

Forward selection is a very attractive approach because it's both tractable and it gives a good sequence of models。

 So this is how it works。

![](img/5f52f3351ad4f88ba8e27a6471444e38_93.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_94.png)

You start with the null model and the null model has no predictors in it。

 but it'll just have the intercept in it， and the intercept is the mean of why。



![](img/5f52f3351ad4f88ba8e27a6471444e38_96.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_97.png)

With no other variables in the model。

![](img/5f52f3351ad4f88ba8e27a6471444e38_99.png)

AndNow what you do is you add variables one at a time。



![](img/5f52f3351ad4f88ba8e27a6471444e38_101.png)

The first variable you add， you do it as follows， you fit P simple linear regression models。

 each with one of the variables in and the intercept。

 and you look at each of them and you add to the null model。

 the variable that results in the lowest residual summer squares。

 So basically you just search through all the single variable models and pick the best one。



![](img/5f52f3351ad4f88ba8e27a6471444e38_103.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_104.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_105.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_106.png)

Now having picked that， you fix that variable in the model。

 and now you search through the remaining p minus1 variables again and find out which variable should be added to the variable you've already picked to best improve the residual summer squares。



![](img/5f52f3351ad4f88ba8e27a6471444e38_108.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_109.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_110.png)

And you continue in this fashion， add in one variable at a time until some stopping is rule is satisfied。

 for example， in all the remaining variables have a P value above some threshold。



![](img/5f52f3351ad4f88ba8e27a6471444e38_112.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_113.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_114.png)

Now， this sounds like it might be computationally quite difficult as well。

 but it turns out it's not there's some clever tricks you can use to do all these evaluations very efficiently。



![](img/5f52f3351ad4f88ba8e27a6471444e38_116.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_117.png)

So in a similar fashion and this is if P' is not too large， you can start from the other end。



![](img/5f52f3351ad4f88ba8e27a6471444e38_119.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_120.png)

So you start with the model with all the variables in the model。

And now you're going to remove them one at a time。

![](img/5f52f3351ad4f88ba8e27a6471444e38_122.png)

And this time you're going to remove each at each step。

 you're going to remove the variable that does the least damage to the model。 In other words。

 you want to remove a variable that's got the least significance。



![](img/5f52f3351ad4f88ba8e27a6471444e38_124.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_125.png)

And that you can actually find from looking at the T statistics for each of the variables。



![](img/5f52f3351ad4f88ba8e27a6471444e38_127.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_128.png)

And， and remove the one with the least significant T statistic。



![](img/5f52f3351ad4f88ba8e27a6471444e38_130.png)

Now you've got a model with P minus-1 variables and you just repeat and you keep on going in that fashion again until you reach some threshold that you've defined。

 perhaps in terms of a P value。

![](img/5f52f3351ad4f88ba8e27a6471444e38_132.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_133.png)

So these are two approaches they might seem somewhat ad hoc， but theyre very effective。

 and later we will discuss more systematic criteria for choosing an optimal member in the path of models produced by either forward or stepwise model selection。



![](img/5f52f3351ad4f88ba8e27a6471444e38_135.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_136.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_137.png)

Some of these criteria include something known as Mallow CP， Akaki information criterion， AIC。

 that's abbreviation， and then BIC， which is Bayesian information criterion。



![](img/5f52f3351ad4f88ba8e27a6471444e38_139.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_140.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_141.png)

These all sound like very important methods they named after important people and they're very popular and then there's something called adjusted R squared and one of our favorites is cross validation which you'll be learning about。



![](img/5f52f3351ad4f88ba8e27a6471444e38_143.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_144.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_145.png)

We will talk more about model selection in in， in the later， in later sessions。



![](img/5f52f3351ad4f88ba8e27a6471444e38_147.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_148.png)

Now， there's some other considerations in regression models that we haven't really touched on yet。



![](img/5f52f3351ad4f88ba8e27a6471444e38_150.png)

And the one is qualitative predictors。So some variables are not quantitative but qualitative。

 In other words， they don't take values on a continuous scale。

 but they take values in a discrete set。

![](img/5f52f3351ad4f88ba8e27a6471444e38_152.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_153.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_154.png)

So we call them categorical predictors or factor variables。



![](img/5f52f3351ad4f88ba8e27a6471444e38_156.png)

Were going to see us。A matrix of。

![](img/5f52f3351ad4f88ba8e27a6471444e38_158.png)

Data in the next slide， it's a credit card data， in fact I'll just take you there now。



![](img/5f52f3351ad4f88ba8e27a6471444e38_160.png)

And so here's a bunch of variables。

![](img/5f52f3351ad4f88ba8e27a6471444e38_162.png)

On credit cards and ratings。

![](img/5f52f3351ad4f88ba8e27a6471444e38_164.png)

And we see the current balance on the credit card， the age， number of cards， and so on。

 these are all quantitative variables。

![](img/5f52f3351ad4f88ba8e27a6471444e38_166.png)

Now， in addition to these variables。

![](img/5f52f3351ad4f88ba8e27a6471444e38_168.png)

We have。We have some qualitative variables。 So one of them is gender。 So that takes on values。

 male and female。

![](img/5f52f3351ad4f88ba8e27a6471444e38_170.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_171.png)

Student， so the student status of the cardholderer， whether they are a student or not。

 So these are qualitative values， marital status。

![](img/5f52f3351ad4f88ba8e27a6471444e38_173.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_174.png)

Say married， single or divorced。

![](img/5f52f3351ad4f88ba8e27a6471444e38_176.png)

There's no order really in those， those variables。 Theyre just different categories。



![](img/5f52f3351ad4f88ba8e27a6471444e38_178.png)

And likewise， ethnicity， say Caucasian， African American or Asian， again。

 not in no way an ordered variable。 So how do we deal with such qualitative predictors when we fit in linear regression models。



![](img/5f52f3351ad4f88ba8e27a6471444e38_180.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_181.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_182.png)

So it's， let's consider our example on， on credit cards。 again。

 Imagine investigating the difference in credit card balance between males and females ignoring the other variables。



![](img/5f52f3351ad4f88ba8e27a6471444e38_184.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_185.png)

So what we do is we create a new variable。

![](img/5f52f3351ad4f88ba8e27a6471444e38_187.png)

Let's call it X I， and it's going to well， X， we call it X and the I value is going to be one if the I person is a female and a zero。

 if the I person is a male。

![](img/5f52f3351ad4f88ba8e27a6471444e38_189.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_190.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_191.png)

So we got a name for such a variable。 We call it a dummy variable。

 It's a created variable just to represent this categorical feature。



![](img/5f52f3351ad4f88ba8e27a6471444e38_193.png)

Okay， so for each value of I， we， we score an individual as 01， depending if they female。

 male or female。

![](img/5f52f3351ad4f88ba8e27a6471444e38_195.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_196.png)

And so now if we put such a variable in a model， let's say on its own。😊。



![](img/5f52f3351ad4f88ba8e27a6471444e38_198.png)

We've got the linear regression model with a coefficient for this dummy variable。



![](img/5f52f3351ad4f88ba8e27a6471444e38_200.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_201.png)

Xi。 and let's see what it produces。 Well， since Xi takes on only two possible values，0 or1。

 the model is either going to be beta 0 plus beta 1 plus error。



![](img/5f52f3351ad4f88ba8e27a6471444e38_203.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_204.png)

If the person is female and if the person is male， it's just going to be beta 0 plus error。



![](img/5f52f3351ad4f88ba8e27a6471444e38_206.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_207.png)

So beta 1 is telling us。The effect of being female versus the baseline， in this case， of being male。



![](img/5f52f3351ad4f88ba8e27a6471444e38_209.png)

And so that's how we deal with the categorical variable with just two levels。



![](img/5f52f3351ad4f88ba8e27a6471444e38_211.png)

So here we see the results of the regression model using just the single variable gender and the dummy variable 01 that the one represent in female。



![](img/5f52f3351ad4f88ba8e27a6471444e38_213.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_214.png)

And so we see the result and the coefficients 19。73， but it's not significant， the P values 0。66。

 which is not significant。 so contrary to popular wisdom females don't generally have a higher credit card balance than males。



![](img/5f52f3351ad4f88ba8e27a6471444e38_216.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_217.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_218.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_219.png)

The number is 19。73 slightly higher， but it's not significant。



![](img/5f52f3351ad4f88ba8e27a6471444e38_221.png)

So what do we do if you have a variable with more than two levels？



![](img/5f52f3351ad4f88ba8e27a6471444e38_223.png)

So ethnicity is such a variable。 Well， we just make more dummy variables。



![](img/5f52f3351ad4f88ba8e27a6471444e38_225.png)

So ethnicity takes has three levels。

![](img/5f52f3351ad4f88ba8e27a6471444e38_227.png)

So we'll make two dummy variables in this case， and we'll call them x 1 and x2。



![](img/5f52f3351ad4f88ba8e27a6471444e38_229.png)

And so Xi1 is the value for the I individual for dummy variable1。

 we'll call it one if the Ih person's Asian， otherwise0。



![](img/5f52f3351ad4f88ba8e27a6471444e38_231.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_232.png)

And the second D variable will be one if the eighth person is Caucasian and0， if not。



![](img/5f52f3351ad4f88ba8e27a6471444e38_234.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_235.png)

And， of course， if they both zero， the person， the individual will be African American。



![](img/5f52f3351ad4f88ba8e27a6471444e38_237.png)

And so that's the general rule if you've got a categorical variable。



![](img/5f52f3351ad4f88ba8e27a6471444e38_239.png)

With three levels， you make two dummy variables。 If it's got two levels， you make one dummy variable。

 and if it's got K levels， you'll make K-1 dummy variables to represent each of those categories。



![](img/5f52f3351ad4f88ba8e27a6471444e38_241.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_242.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_243.png)

So what does the model look like in this case？Well， we'll have a model now with two coefficients。

 one for each of these dummy variables。

![](img/5f52f3351ad4f88ba8e27a6471444e38_245.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_246.png)

And let's look at the different cases。 So if the person's Asian。They get the beta 1。

If the person's Caucasian， they'll get the beta2。

![](img/5f52f3351ad4f88ba8e27a6471444e38_248.png)

And if the person's African American， they don't have beta 1 or beta 2。

 so the baseline beta 0 represents such an individual。



![](img/5f52f3351ad4f88ba8e27a6471444e38_250.png)

And so what we see now is that beta 1 represents the difference between the baseline beta 0。

 which is African American and the difference between that individual and an Asian。

 so it's the additional effect for being an Asian and beta 2 is the additional effect for being Caucasian。



![](img/5f52f3351ad4f88ba8e27a6471444e38_252.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_253.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_254.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_255.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_256.png)

And as I said， there will be always one fewer dummy variable than the number of levels。



![](img/5f52f3351ad4f88ba8e27a6471444e38_258.png)

So in this case we call。The， the category， African American is known as the baseline level。

cause it doesn't have a parameter representing it， except beta 0。



![](img/5f52f3351ad4f88ba8e27a6471444e38_260.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_261.png)

So here's the linear model， we've picked African American as a baseline。

 and so that actually determines which comparisons we make。 So the coefficient minus- 18。

69 is comparing Asian to African American， and that's not significant and likewise the Caucasian to African American。

 which is also not significant。

![](img/5f52f3351ad4f88ba8e27a6471444e38_263.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_264.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_265.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_266.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_267.png)

Now it turns out the choice of the baseline does not affect the foot of the model。

 the residual sum squares would be the same no matter which category you chose as the baseline。



![](img/5f52f3351ad4f88ba8e27a6471444e38_269.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_270.png)

But the contrasts would change， because that would determine picking the baseline determines which contrasts you make。

 And so the P values potentially will change as you change the baseline。



![](img/5f52f3351ad4f88ba8e27a6471444e38_272.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_273.png)

![](img/5f52f3351ad4f88ba8e27a6471444e38_274.png)