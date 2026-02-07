# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P23：-023-Statistical Learning_ 4.3 Multivariate Logistic Regression.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

So。

![](img/984d077dbfa0a25dad8f8df340656042_1.png)

That's a good segue into what do we do when we have more than one variable。

 The two models we've considered so far， just。

![](img/984d077dbfa0a25dad8f8df340656042_3.png)

Perform logistic regression with single variables。 But， of course， if we got collection of variables。

 we want to take them all into account。

![](img/984d077dbfa0a25dad8f8df340656042_5.png)

![](img/984d077dbfa0a25dad8f8df340656042_6.png)

And so in that case， we're going to build a multivariate logistic regression model。

So the transformation of the probability is the same as we had before。

 except now we've got a general linear model with an intercept and a coefficient for each of the variables。



![](img/984d077dbfa0a25dad8f8df340656042_8.png)

And if you invert that transformation， that again， gives you a form for the probability that's guaranteed to be between 0 and  one。

Okay， well， we can fit that using GLM in R just like we did before。

And we'll throw in our variable balance as well， and income and the student variable。

And now we get three coefficients， three standard errors。



![](img/984d077dbfa0a25dad8f8df340656042_10.png)

3 standard errors。3 Z statistics， and 3 P values。And the first thing we see is that。

As they were in the single variable case， balance and student are significant。

Income is not significant。Okay， so it seems like two of the variables are important。

But if something rather striking。 We notice that the coefficient for student is negative。



![](img/984d077dbfa0a25dad8f8df340656042_12.png)

Well， it was positive before。So before， when we dis measured student on its own。



![](img/984d077dbfa0a25dad8f8df340656042_14.png)

It had a positive， coefficient。

![](img/984d077dbfa0a25dad8f8df340656042_16.png)

But when we put it in the multivariate model， the coefficient is negative。

Do you think this is an error Rob。don't think so。So how could that happen？

While we measured last time we talked about immigration regression models how difficult it is to interpret coefficients in a multiple model。

 beat wealth regression model because the correlations。Between the variables affect the signs。

So there's gonna be。 we're gonna see now the role of correlations in the variables。



![](img/984d077dbfa0a25dad8f8df340656042_18.png)

So。Here's's a picture there we see credit card balance。



![](img/984d077dbfa0a25dad8f8df340656042_20.png)

And， and。And we see the default rate on， on， on the vertical axis。And。The brown。

 the student center of， let's see。 So student status， Brown is yes。And blue is no， okay。

So students tend to have higher balances than non students。

 So the marginal default rate is higher than for non students。Okay， because we just saw that。

 you know， balance as it plays a role。But what we see in this plot on the left is that for each level of balance。

Students default less than non students。Okay。So when you just look at student on its own。

It's confounded with balance。And， and， and the strong effect of balance makes it look like。

 like students are our worst defaulters， right。But this plot sort of explains the all for each level of credit card balance。

If we look separately for students and non students， students tend to have a lower default rate。Okay。

And so that we can tease out by multiple logistic regression。

 which takes these correlations into account。

![](img/984d077dbfa0a25dad8f8df340656042_22.png)

![](img/984d077dbfa0a25dad8f8df340656042_23.png)

Let's move on to another example， with more variables。We talked about this example in the。

 in the introduction。 This is the South African heart diseasease dataset set。Remember。

 South Africans eat a lot of meat。 Rob apparentlypparently。

 did I ever tell you the story about the South Africans in more than more than once more than once。



![](img/984d077dbfa0a25dad8f8df340656042_25.png)

I think Rob doesn't want to hear the story again。Anyway， they do eat a lot of meat。

 so they did a study in South Africa。It was a retrospective study。

They went and found 160 cases of white males whod had myocardial infarction。

 which is a fancy name for a heart attack。And amongst。



![](img/984d077dbfa0a25dad8f8df340656042_27.png)

The many people who hadn't had a heart attack， they took a sample of 302 controls， right。

 So it's called a case control sample。And for these people。

 they were all white males in the age range 15 to 64。

 and they were from this western Cape region of South Africa。 This was done in the early 1980s。

So in this region， the overall prevalence was very high for heart disease，5。1%。

 which is very high risk。

![](img/984d077dbfa0a25dad8f8df340656042_29.png)

So。In this study， we have measurements on 7 predictors or， or in this case， known as risk factors。



![](img/984d077dbfa0a25dad8f8df340656042_31.png)

And they shown in the scatter plot matrix， which I'll show you right here。



![](img/984d077dbfa0a25dad8f8df340656042_33.png)

So remember， the scatterpl matrix is a very nice way of plotting every variable against every other variable。

And now， because it's a classification problem， we can code into the plot， the heart disease status。

And so the brown red points here are are those cases that had heart disease and。

 and the the blue points the controls。And look at the top plot， for example。

 if you high in tobacco usage。And your systolic blood pressure is high。You tend to。

 to be a brown point。 So those are the people who tend to have had heart attacks。

So each of these plots shows a pairwise plot of two of the risk factors and codes in the heart disease status。

 You forgot one risk factor， What percentage talking with a funny accent， but they've all got that。

 okay so。Very good， Rob。I'm doing all the hard work， and he's just me thinking of jokes。

The coffee is good too。There's one funny variable here， Family history。 Well。

 it's a categorical variable。 Its out to be an important risk factor。

Apart from being South African or not。If you have a family history of heart disease， the， the。

 the risk is， is high。And you can see that it's a 01 variable in this case。

 And you probably can see there's more browns in the in the the right hand category than the left hand category。

So， in this case。

![](img/984d077dbfa0a25dad8f8df340656042_35.png)

We're not really trying to predict the probability of getting a heart disease。

 what we're really trying to do is to understand the role of the risk factors in you know in the risk of heart disease。



![](img/984d077dbfa0a25dad8f8df340656042_37.png)

![](img/984d077dbfa0a25dad8f8df340656042_38.png)

And actually， the study was was an intervention study aimed at educating the public on healthier diets。

 but that's a whole otherher story。 Does it work。

![](img/984d077dbfa0a25dad8f8df340656042_40.png)

I think it might have whipped a little bit， but this is。

 this crowd is really hard to get them away from the meat。

You know what they call a barbecue in South Africa， Brylace？Okay。

Every South African loves you bright place， and they boughtong。So here's a result of GLM。

For the heart disease data。And yeah， I actually show you some of the code used to fit it。

And we get it。 we'll get into the code session later。 But it's just interesting to see that it's。

 it's pretty easy to do。 There's a call to GM。嗯。We tell it， the responses。Is C， HD。

 which is the name of the the response variable。And Twiddle means to be modeled as。

 and dot means all the other variables in the data frame， which in this case is hot。

 So that's data frame that's got all the variables in the， in the study。And the response here is C。

 H D。 And we tell it the， the family's binomial， which just tells it to fit the logistic regression model。

And then we fit that model， save it in the object called Hearttfit。

 and then we do a summary of heartfit。 and this is and we get printed out the summary。

 which is the same summaries that we've seen before。

And so now we get coefficients for each of the variables in this column。We get standard errors。

 C values and P values。And， yeah， the story is a little bit mixed。 right。

 We're not too interested in the intercept。 Tobacco usage is significant。Low density lipopprotein。

 That's a cholesterol measure。That's significant。Remember there's a good and bad cholesterol。

This is the bad cholesterol。Family history， very significant。And age is significant。

 We know the risk of heart disease goes up with age。Now， interestingly， obesity。

And alcohol usage are not significant here。Which seems little surprising， Rob。Mmhm。

But this is a case， again， of having correlated variables。 If we look in the previous plot。You see。

 you see there's a lot of correlation between variables。So age and tobacco usage are correlated。嗯。

Alcohol usage and LDL seem to be negatively correlated。LDL is the good cholesterol。

So there's lots of correlations。 And so those are going to play a role。And so， for example。

 we've got LDO is significant in the model。 And once LDO is in the model。

 perhaps alcohol usage is not needed anymore because it's been taken care of。

 these variables act as surrogates for each other。