# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P16：P16 StatsLearning Lect6c 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

So。

![](img/42722dde1f8489c8409ee67e80548a03_1.png)

That's a good segue into what do we do when we have more than one variable。

 The two models we've considered so far， just。

![](img/42722dde1f8489c8409ee67e80548a03_3.png)

Perform logistic regression with single variables。 But， of course， if we got its。



![](img/42722dde1f8489c8409ee67e80548a03_5.png)

Collection of variables。 We want to take them all into account。



![](img/42722dde1f8489c8409ee67e80548a03_7.png)

And so in that case， we're going to build a multivariate logistic regression model。



![](img/42722dde1f8489c8409ee67e80548a03_9.png)

So the transformation of the probability is the same as we had before。

 except now we've got a general linear model with an intercept and a coefficient for each of the variables。



![](img/42722dde1f8489c8409ee67e80548a03_11.png)

![](img/42722dde1f8489c8409ee67e80548a03_12.png)

![](img/42722dde1f8489c8409ee67e80548a03_13.png)

And if you invert that transformation， that， again。

 gives you a form for the probability that's guaranteed to be between 0 and 1。



![](img/42722dde1f8489c8409ee67e80548a03_15.png)

Okay， well， we can fit that using GLM in R just like we did before。



![](img/42722dde1f8489c8409ee67e80548a03_17.png)

And we'll throw in our variable balance as well， and income and the student variable。



![](img/42722dde1f8489c8409ee67e80548a03_19.png)

And now we get three coefficients， three standard errors。



![](img/42722dde1f8489c8409ee67e80548a03_21.png)

![](img/42722dde1f8489c8409ee67e80548a03_22.png)

3 standard errors。3 Z statistics， and 3 P values。

![](img/42722dde1f8489c8409ee67e80548a03_24.png)

And the first thing we see is that。

![](img/42722dde1f8489c8409ee67e80548a03_26.png)

As they were in a single variable case， balance and student are significant。



![](img/42722dde1f8489c8409ee67e80548a03_28.png)

Income is not significant。

![](img/42722dde1f8489c8409ee67e80548a03_30.png)

Okay， so it seems like two of the variables are important。



![](img/42722dde1f8489c8409ee67e80548a03_32.png)

But yes something rather striking。 We notice that the coefficient for student is negative。



![](img/42722dde1f8489c8409ee67e80548a03_34.png)

Well， it was positive before。So before， when we dis measured student on its own。



![](img/42722dde1f8489c8409ee67e80548a03_36.png)

It had a positive， coefficient。

![](img/42722dde1f8489c8409ee67e80548a03_38.png)

But when we fit it in the multivariate model， the coefficient' is negative。

Do you think this is an error Rob。

![](img/42722dde1f8489c8409ee67e80548a03_40.png)

don't think so。

![](img/42722dde1f8489c8409ee67e80548a03_42.png)

So how could that happen？While we measured last time we talked about immigration regression models how difficult it its interpret coefficients in a multiple model be wealth regression model because the correlations。



![](img/42722dde1f8489c8409ee67e80548a03_44.png)

![](img/42722dde1f8489c8409ee67e80548a03_45.png)

Between the variables can affect the science。

![](img/42722dde1f8489c8409ee67e80548a03_47.png)

So there's going to be， we're going to see now the role of correlations in the variables。



![](img/42722dde1f8489c8409ee67e80548a03_49.png)

So。Here's a picture there we see credit card balance。



![](img/42722dde1f8489c8409ee67e80548a03_51.png)

And， and。

![](img/42722dde1f8489c8409ee67e80548a03_53.png)

And we see the default rate on， on， on the vertical axis。



![](img/42722dde1f8489c8409ee67e80548a03_55.png)

And。The brown， the students center of。

![](img/42722dde1f8489c8409ee67e80548a03_57.png)

Let's see。 So student status， Brown is yes。

![](img/42722dde1f8489c8409ee67e80548a03_59.png)

And blue is no， okay。

![](img/42722dde1f8489c8409ee67e80548a03_61.png)

So students tend to have higher balances than non students。

 So the marginal default rate is higher than for non students。



![](img/42722dde1f8489c8409ee67e80548a03_63.png)

Okay， because we just saw that， you know， balance as it plays a role。



![](img/42722dde1f8489c8409ee67e80548a03_65.png)

But what we see in this plot on the left is that for each level of balance。



![](img/42722dde1f8489c8409ee67e80548a03_67.png)

Students default less than non students。

![](img/42722dde1f8489c8409ee67e80548a03_69.png)

Okay。So when you just look at student on its own。

![](img/42722dde1f8489c8409ee67e80548a03_71.png)

It's confounded with balance。And， and， and the strong effect of balance makes it look like。

 like students are are worse defaulters， right。

![](img/42722dde1f8489c8409ee67e80548a03_73.png)

![](img/42722dde1f8489c8409ee67e80548a03_74.png)

But this plot sort of explains it all for each level of credit card balance。



![](img/42722dde1f8489c8409ee67e80548a03_76.png)

If we look separately for students and non students， students tend to have a lower default rate。



![](img/42722dde1f8489c8409ee67e80548a03_78.png)

Okay。And so that we can tease out by multiple logistic regression， which takes these。

 these correlations into account。

![](img/42722dde1f8489c8409ee67e80548a03_80.png)

![](img/42722dde1f8489c8409ee67e80548a03_81.png)

Let's move on to another example with more variables。



![](img/42722dde1f8489c8409ee67e80548a03_83.png)

We talked about this example in the in the introduction。

 This is the South African heart diseasease dataset set。



![](img/42722dde1f8489c8409ee67e80548a03_85.png)

Remember South Africans eat a lot of meat， Rob， apparently。

 did I ever tell you the story about the South Africans in more than once more than once。



![](img/42722dde1f8489c8409ee67e80548a03_87.png)

![](img/42722dde1f8489c8409ee67e80548a03_88.png)

I think Rob doesn't want to hear the story again。

![](img/42722dde1f8489c8409ee67e80548a03_90.png)

Anyway， they do eat a lot of meat， so they did a study in South Africa。



![](img/42722dde1f8489c8409ee67e80548a03_92.png)

It was a retrospective study。They went and found 160 cases of white males who had myocardial infarction。

 which is a fancy name for a heart attack。

![](img/42722dde1f8489c8409ee67e80548a03_94.png)

![](img/42722dde1f8489c8409ee67e80548a03_95.png)

And amongst。

![](img/42722dde1f8489c8409ee67e80548a03_97.png)

The many people who hadn't had a heart attack， they took a sample of 302 controls， right。

 So it's called a case control sample。

![](img/42722dde1f8489c8409ee67e80548a03_99.png)

And for these people， they were all white males in the age range 15 to 64。

 and they were from this western Cape region of South Africa。 This was done in the early 1980s。



![](img/42722dde1f8489c8409ee67e80548a03_101.png)

![](img/42722dde1f8489c8409ee67e80548a03_102.png)

![](img/42722dde1f8489c8409ee67e80548a03_103.png)

So， in this region。The overall prevalence was very high for heart disease，5。1%。

 which is very high risk。

![](img/42722dde1f8489c8409ee67e80548a03_105.png)

![](img/42722dde1f8489c8409ee67e80548a03_106.png)

So。In this study， we have measurements on 7 predictors or in this case， known as risk factors。



![](img/42722dde1f8489c8409ee67e80548a03_108.png)

And they shown in the scatter plot matrix， which I'll show you right here。



![](img/42722dde1f8489c8409ee67e80548a03_110.png)

So remember the scatterpl matrix is a very nice way of plotting every variable against every other variable。

And now， because it's a classification problem， we can code into the plot， the heart disease status。

And so the brown red points here are those cases that had heart disease and the blue points or the controls。

And look at the top plot， for example， if you high in tobacco usage。

And your systolic blood pressure is high。You tend to， to be a brown point。

 So those are the people who tend to have had heart attacks。

So each of these plots shows a pairwise plot of two of the risk factors and codes in the heart disease status。

 If forgot one risk factor， what was that is caught with a funny accent but they've all got that。

 okay， so。Very good， Rob。I'm doing all the hard work and he's just sitting me thinking of jokes。

The coffee is good， too。There's one funny variable here， Family history。 Well。

 it's a categorical variable。 Its out to be an important risk factor。

Apart from being South African or not。If you have a family history of heart disease the the。

 the risk is， is high。And you can see that it's a 0，1 variable in this case。

 And you probably can see there's more browns in the， in the。

 the right hand category than the left hand category。嗯。So， in this case。



![](img/42722dde1f8489c8409ee67e80548a03_112.png)

We're not really trying to predict the probability of getting a heart disease。

 what we're really trying to do is to understand the role of the risk factors in the risk of heart disease。



![](img/42722dde1f8489c8409ee67e80548a03_114.png)

![](img/42722dde1f8489c8409ee67e80548a03_115.png)

![](img/42722dde1f8489c8409ee67e80548a03_116.png)

And actually， this study was an intervention study aimed at educating the public on healthier diets。

 but that's a whole nother story， did it work？

![](img/42722dde1f8489c8409ee67e80548a03_118.png)

I think it might have whipped a little bit， but this is。

 this crowd is really hard to get them away from the meat。

You know what they call a barbecue in South Africa， Brylesce？Okay。

Every South African loves you brightly， And they Bong。So here's a result of GOM。

For the heart disease data。And yeah， I actually show you some of the code used to fit it。

we get we'll get into the code session later， but it's just interesting to see that it's it's pretty easy to do。

 There's a call to GM。嗯。We tell it， the responses。Is C， H D。

 which is the name of the the response variable。And Twiddle means to be modeled as。

 and dot means all the other variables in the data frame， which in this case is hot。

 So that's data frame that's got all the variables in the in the study。And the response here is C。

 H D。 And we tell it the， the family's binomial， which just tells it to fit the logistic regression model。

And then we fit that model， save it in the object called Heartfi。

 and then we do a summary of heartfi。 and this is and we get printed out the summary。

 which is the same summ that we've seen before。And so now we get coefficients for each of the variables in this column。

We get standard errors， C values and P values。And， yeah， the story is a little bit mixed。 right。

 We're not too interested in the intercept。 Tobacco usage is significant。Low density lipopprotein。

 That's a cholesterol measure。That's significant。Remember， there's a good and bad cholesterol。

This is the bad cholesterol。Family history， very significant。And age is significant。

 We know the risk of heart disease goes up with age。Now， interesting the obesity。

And alcohol usage are not significant here。Which seems little surprising， Rob。Mmhm。

But this is a case， again， of having correlated variables。 If we look in the previous plot。You see。

 you see there's a lot of correlation between variables。So age and tobacco usage are correlated。嗯。

Alcohol usage and L，D，L。seem to be negatively correlated。LDL is the good cholesterol。

So there's lots of correlations。 And so those are going to play a role。And so， for example。

 we've got LDO is significant in the model。 And once LDO is in the model。

 perhaps alcohol usage is not needed anymore because it's been taken care of。

 These variables act as surrogates for each other。