# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P5：-005-Statistical Learning_ 2.1 Introduction to Regression Models.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/578da11020690825d2aee88897d0d56e_0.png)

Okay， we're going to talk about statistical learning and models now。

 I'm going to tell you what models are good for， how we use them。

 and what are some of the issues involved。Okay， so we see three plots in front of us。

These are sales figures from a marketing campaign。As a function of the amount spent on TV ads。

 radio ads， and newspaper ads。

![](img/578da11020690825d2aee88897d0d56e_2.png)

And you can see the at least in the first two is somewhat of a trend。

 and in fact we've summarized the trend by a little linear regression line in each。



![](img/578da11020690825d2aee88897d0d56e_4.png)

And so we see that there's some relationship， the first two again look stronger than the third。



![](img/578da11020690825d2aee88897d0d56e_6.png)

Now， in a situation like this， we typically like to know the joint relationship between the response sales and all three of these together。



![](img/578da11020690825d2aee88897d0d56e_8.png)

You know， we want to understand how they operate together to influence sales。



![](img/578da11020690825d2aee88897d0d56e_10.png)

So you can think of that as wanting to model sales as a function。



![](img/578da11020690825d2aee88897d0d56e_12.png)

Of TV， radio and newspaper all jointly together。 So how do we do that？



![](img/578da11020690825d2aee88897d0d56e_14.png)

So before we get into the details。

![](img/578da11020690825d2aee88897d0d56e_16.png)

Let's set up some notation。 So your sales is the response or the target that we wish to predict or model。

And we usually refer to it as Y， we use the letter Y to refer to it TV is one of the features or inputs or predictors。

 and we'll call it x1， likewise， radio is x2 and so on。So in this case。

 we've got three predictors and we can refer to them collectively via a vector。

As x equal to with three components， x1 x2 and x3 and vectors we generally think of as column vectors。

And so that's a little bit of notation。And so now in this more compact notation。

 we can write our model as y equals function of x。Plus， error。

OkayAnd this error is just a catchule to it captures the measurement errors。

 maybe in y and other discrepancies。 our function of x is never going to model y perfectly。

 So there's going to be a lot of things we can't capture with the function and that's caught up in the error。

And again， f of x here。Is now a function of this vector x， which has these three arguments。



![](img/578da11020690825d2aee88897d0d56e_18.png)

three components。So what is the function f of x good for so with a good F we can make predictions of y at new points x equal to little x。

 so this notation capital x equals little x， you know capital x we think is the variable having these three components and little x is an instance also with three components。



![](img/578da11020690825d2aee88897d0d56e_20.png)

![](img/578da11020690825d2aee88897d0d56e_21.png)

Particular values for newspaper， radio and TV。With the model we can understand which components of X in general it'll have P components if there P predictors are important to explain in why and which are irrelevant。



![](img/578da11020690825d2aee88897d0d56e_23.png)

For example， if we model an income as a function of demographic variables。

 seniority and years of your education might have a big impact on income but marital status typically does not。

 and we'd like our model to be able to tell us that。



![](img/578da11020690825d2aee88897d0d56e_25.png)

![](img/578da11020690825d2aee88897d0d56e_26.png)

![](img/578da11020690825d2aee88897d0d56e_27.png)

And depending on the complexity of if， we may be able to understand how each component Xj affects y in what particular fashion。

 it affects y。

![](img/578da11020690825d2aee88897d0d56e_29.png)

So models have many uses and those amongst them。

![](img/578da11020690825d2aee88897d0d56e_31.png)

Okay， well， what is this function if and is there an ideal if？So in the plot。

 we've got a large sample of points from a population。

 there's just a single x in this case and a response Y。And you can see it's a scatter plot。

 so we see there's a lot of point， there's 2，000 points here。

 let's think of this as actually the whole population。

 or rather as a representation of a very large population。U。



![](img/578da11020690825d2aee88897d0d56e_33.png)

And so now let's think of what a good function F might be。 And let's say not just a whole function。

 but let's think what value would we like F to have at say， the value of x equals4。

 So at this point over here， we want to query x F at all values of x。

 but we wondering what it should be at the value4。

![](img/578da11020690825d2aee88897d0d56e_35.png)

![](img/578da11020690825d2aee88897d0d56e_36.png)

So you'll notice that at the x equals4， there's many values of y。

But a function can only take on one value。The function is going to deliver back one value。

 so what is a good value？Well。One good value is to deliver back the average values of those Ys who have x equal to 4。

And that we write in this sort of Matthew notation over you， it says。

The function at the value 4 is the expected value of y given x equals 4。

 and that expected value is just a fancy word for average。 It's actually a conditional average。

 given x equals 4。Since we can only deliver one value。Of the function at x equals 4。

The average seems like a good value。And if we do that at each value of x。

 so at every single value of x， we deliver back the average of the y's that have that value of x。

 so for example， at x equals5。😊。

![](img/578da11020690825d2aee88897d0d56e_38.png)

Again， we want to have the average value in this little conditional slicelicier。



![](img/578da11020690825d2aee88897d0d56e_40.png)

That will trace out this little red curve that we have here。

 and that's called the regression function。 So the regression function gives you the conditional expectation of y given x at each value of x。



![](img/578da11020690825d2aee88897d0d56e_42.png)

So that in a sense， is the ideal function。

![](img/578da11020690825d2aee88897d0d56e_44.png)

For a for a population， in this case of y and a single x。



![](img/578da11020690825d2aee88897d0d56e_46.png)

So let's talk more about this regression function， it's also defined for a vector x。

 so if x has got three components， for example， it's going to be the conditional expectation of y given the three particular instances of the three components of x。



![](img/578da11020690825d2aee88897d0d56e_48.png)

So if you think about that。Let's think of x as being two dimensional because we can think in three dimensions。

 so let's say x lies。

![](img/578da11020690825d2aee88897d0d56e_50.png)

![](img/578da11020690825d2aee88897d0d56e_51.png)

On the table。Two dimensional x and Y stands up vertically。



![](img/578da11020690825d2aee88897d0d56e_53.png)

So the idea is the same， want to we've got a whole continuous cloud of y's and x's。

 we go to a particular point x with two coordinates。

 x1 and x2 and we say what's a good value for the function at that point well we're just going to go up in the slice and average the y's above that point and we'll do that at all points in the plane。



![](img/578da11020690825d2aee88897d0d56e_55.png)

![](img/578da11020690825d2aee88897d0d56e_56.png)

![](img/578da11020690825d2aee88897d0d56e_57.png)

![](img/578da11020690825d2aee88897d0d56e_58.png)

![](img/578da11020690825d2aee88897d0d56e_59.png)

We said it's the ideal or optimal predictor of why with regard for the function and what that means is。

Actually， it's with regard to a loss function。 and what it means is that particular choice of the function F of x will minimize the sum squared errors。

 which we write in this fashion。Again， expected value of y minus。G of x over all functions。

 G at at each point X， right， So it minimizes the average。



![](img/578da11020690825d2aee88897d0d56e_61.png)

Prediction errors。Now， at each point X， we're going to make mistakes because if we use this function to predict y。

 because there's lots of y's at each point x right and so the errors that we make we call in this case we call them epsilons and those are the irreducible error。



![](img/578da11020690825d2aee88897d0d56e_63.png)

![](img/578da11020690825d2aee88897d0d56e_64.png)

You might know the ideal function F， but of course。

 it doesn't make perfect predictions at each point X， so it has to make some errors， but on average。

 it does well。

![](img/578da11020690825d2aee88897d0d56e_66.png)

![](img/578da11020690825d2aee88897d0d56e_67.png)

![](img/578da11020690825d2aee88897d0d56e_68.png)

For any estimate， if hat of x， and that's what we tend to do， we tend to put these little。Hats。

On estimators to show that they've been estimated from data。

And so F hat of x is an estimate of f of x。We can expand。

The squared prediction error at x into two pieces。There's the irreducible piece。

 which is just the variance of the errors。And there's the reducible piece。

 which is the difference between our estimate f hat of x。And the true function， f of x。Okay。

And that's a squared component， so this expected prediction error breaks up into these two pieces。

So that's important to bear in mind， so if we want to improve our model， it's the first piece。

 the reducible piece that we can improve by maybe changing the way we estimate F of X。Okay。

 so that's all nice。 This is a kind of as up to now， has been somewhat of a theoretical exercise。

 Well， how do we estimate the function F？😊。

![](img/578da11020690825d2aee88897d0d56e_70.png)

![](img/578da11020690825d2aee88897d0d56e_71.png)

So the problem is we can't carry out this recipe of conditional expectation or conditional averaging exactly because。

😊。

![](img/578da11020690825d2aee88897d0d56e_73.png)

At any given x in our data set， we might not have many points to average。

 we might not have any points to average。

![](img/578da11020690825d2aee88897d0d56e_75.png)

In the figure， I've。We've got a much smaller data set now and we've still got the point x equals 4。

 and if you look there， you'll see carefully that the solid point is one point I put on the plot。

 the solid green point。

![](img/578da11020690825d2aee88897d0d56e_77.png)

There's actually no data points whose x value is exactly4。

So how can we compute the conditional expectation or average。Well。

 what we can do is relax the idea of。At the point x to at in a neighborhood of the point X。

 And so that's what the notation here refers to。

![](img/578da11020690825d2aee88897d0d56e_79.png)

N of x or script n of x is a neighborhood of points defined in some way around the target point。

 which is this x equals fourier。

![](img/578da11020690825d2aee88897d0d56e_81.png)

![](img/578da11020690825d2aee88897d0d56e_82.png)

And it keeps a spirit of conditional expectation， it's close to the target point x。

 and if we make that neighborhood wide enough we'll have enough points in the neighborhood to average and we'll use their average to estimate the conditional expectation。

So this is called nearest neighbor or local A it's a very clever idea， it's not my idea。

 it has been invented a long time ago and of course you'll move this neighborhood。

 you'll slide this neighborhood along the X axis and as you compute the averages as you slide in along。

 it'll trace out a curve。😊，So that's actually a very good estimate of the of the function F。

 It's not going to be perfect。Because the little window has a certain width and so as we can see。

 some points of the true F may be lower and some points higher， but on average it does quite well。



![](img/578da11020690825d2aee88897d0d56e_84.png)

So we have a pretty powerful tool for estimating this conditional expectation。

 just relax the definition and compute the nearest neighbor average。

 and it gives us a fairly flexible way of fitting a function。😊。



![](img/578da11020690825d2aee88897d0d56e_86.png)

![](img/578da11020690825d2aee88897d0d56e_87.png)

![](img/578da11020690825d2aee88897d0d56e_88.png)

We'll see in the next section that this doesn't always work。

 especially as the dimensions get larger and we'll have to have ways of dealing with that。



![](img/578da11020690825d2aee88897d0d56e_90.png)

![](img/578da11020690825d2aee88897d0d56e_91.png)