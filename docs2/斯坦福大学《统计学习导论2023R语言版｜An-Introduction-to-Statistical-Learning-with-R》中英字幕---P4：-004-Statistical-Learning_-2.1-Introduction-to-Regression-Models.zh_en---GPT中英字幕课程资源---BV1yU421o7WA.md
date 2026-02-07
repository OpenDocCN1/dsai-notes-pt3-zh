# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P4：-004-Statistical Learning_ 2.1 Introduction to Regression Models.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

![](img/a00342ddf3d95c8628ca779884b28305_0.png)

Okay， we're going to talk about statistical learning and models now。

 I'm going to tell you what models are good for， how we use them。

 and what are some of the issues involved。Okay， so we see three plots in front of us。

These are sales figures from a marketing campaign。As a function of the amount spent on TV ads。

 radio ads， and newspaper ads。And you can see the at least in the first two is somewhat of a trend。

 and in fact we've summarized the trend by a little linear regression line in each。

And so we see that there's some relationship， the first two again look stronger than the third。Now。

 in a situation like this， we typically like to know the joint relationship between the response sales and all three of these together。

You know， we want to understand how they operate together to influence sales。

So you can think of that as wanting to model sales as a function。Of TV。

 radio and newspaper all jointly together。 So how do we do that？



![](img/a00342ddf3d95c8628ca779884b28305_2.png)

So before we get into the details。

![](img/a00342ddf3d95c8628ca779884b28305_4.png)

Let's set up some notation。 So your sales is the response or the target that we wish to predict or model。



![](img/a00342ddf3d95c8628ca779884b28305_6.png)

And we usually refer to it as Y， we use the letter Y to refer to it TV is one of the features or inputs or predictors。

 and we'll call it x1， likewise， radio is x2 and so on。



![](img/a00342ddf3d95c8628ca779884b28305_8.png)

![](img/a00342ddf3d95c8628ca779884b28305_9.png)

![](img/a00342ddf3d95c8628ca779884b28305_10.png)

So in this case， we've got three predictors and we can refer to them collectively via a vector。

As x equal to with three components， x1 x2 and x3 and vectors we generally think of as column vectors。



![](img/a00342ddf3d95c8628ca779884b28305_12.png)

And so that's a little bit of notation。

![](img/a00342ddf3d95c8628ca779884b28305_14.png)

And so now in this more compact notation， we can write our model as y equals function of x。



![](img/a00342ddf3d95c8628ca779884b28305_16.png)

Plus， error。

![](img/a00342ddf3d95c8628ca779884b28305_18.png)

OkayAnd this error is just a catchule to it captures the measurement errors。

 maybe in y and other discrepancies。 our function of x is never going to model y perfectly。

 So there's going to be a lot of things we can't capture with the function and that's caught up in the error。



![](img/a00342ddf3d95c8628ca779884b28305_20.png)

![](img/a00342ddf3d95c8628ca779884b28305_21.png)

![](img/a00342ddf3d95c8628ca779884b28305_22.png)

And again， f of x here。Is now a function of this vector x， which has these three arguments。



![](img/a00342ddf3d95c8628ca779884b28305_24.png)

three components。So what is the function f of x good for so with a good F we can make predictions of y at new points x equal to little x。

 so this notation capital x equals little x， you know capital x we think is the variable having these three components and little x is an instance also with three components。



![](img/a00342ddf3d95c8628ca779884b28305_26.png)

![](img/a00342ddf3d95c8628ca779884b28305_27.png)

![](img/a00342ddf3d95c8628ca779884b28305_28.png)

![](img/a00342ddf3d95c8628ca779884b28305_29.png)

Particular values for newspaper， radio and TV。

![](img/a00342ddf3d95c8628ca779884b28305_31.png)

With the model we can understand which components of X in general it'll have P components if there P predictors are important to explain in why and which are irrelevant。

For example， if we model an income as a function of demographic variables。

 seniority and years of your education might have a big impact on income but marital status typically does not。

 and we'd like our model to be able to tell us that。



![](img/a00342ddf3d95c8628ca779884b28305_33.png)

![](img/a00342ddf3d95c8628ca779884b28305_34.png)

![](img/a00342ddf3d95c8628ca779884b28305_35.png)

And depending on the complexity of if， we may be able to understand how each component Xj affects y in what particular fashion。

 it affects y。

![](img/a00342ddf3d95c8628ca779884b28305_37.png)

So models have many uses and those amongst them。

![](img/a00342ddf3d95c8628ca779884b28305_39.png)

Okay， well， what is this function if and is there an ideal if？



![](img/a00342ddf3d95c8628ca779884b28305_41.png)

So in the plot， we've got a large sample of points from a population。

 there's just a single x in this case and a response Y。And you can see it's a scatter plot。

 so we see there's a lot of point， there's 2，000 points here。

 let's think of this as actually the whole population。

 or rather as a representation of a very large population。



![](img/a00342ddf3d95c8628ca779884b28305_43.png)

U。

![](img/a00342ddf3d95c8628ca779884b28305_45.png)

And so now let's think of what a good function F might be。 And let's say not just a whole function。

 but let's think what value would we like F to have at say， the value of x equals4。

 So at this point over here， we want to query x F at all values of x。

 but we wondering what it should be at the value4。So you'll notice that at the x equals4。

 there's many values of y。But a function can only take on one value。

The function is going to deliver back one value， so what is a good value？Well。

One good value is to deliver back the average values of those Ys who have x equal to 4。

And that we write in this sort of Matthew notation over you， it says。

The function at the value 4 is the expected value of y given x equals 4。

 and that expected value is just a fancy word for average。 It's actually a conditional average。

 given x equals 4。Since we can only deliver one value。Of the function at x equals 4。

The average seems like a good value。

![](img/a00342ddf3d95c8628ca779884b28305_47.png)

And if we do that at each value of x， so at every single value of x。

 we deliver back the average of the y's that have that value of x， so for example， at x equals5。😊。



![](img/a00342ddf3d95c8628ca779884b28305_49.png)

![](img/a00342ddf3d95c8628ca779884b28305_50.png)

Again， we want to have the average value in this little conditional slicelicier。

That will trace out this little red curve that we have here。

 and that's called the regression function。 So the regression function gives you the conditional expectation of y given x at each value of x。

So that in a sense， is the ideal function。For a for a population， in this case of y and a single x。



![](img/a00342ddf3d95c8628ca779884b28305_52.png)

So let's talk more about this regression function， it's also defined for a vector x。

 so if x has got three components， for example， it's going to be the conditional expectation of y given the three particular instances of the three components of x。



![](img/a00342ddf3d95c8628ca779884b28305_54.png)

![](img/a00342ddf3d95c8628ca779884b28305_55.png)

So if you think about that。Let's think of x as being two dimensional because we can think in three dimensions。

 so let's say x lies。

![](img/a00342ddf3d95c8628ca779884b28305_57.png)

![](img/a00342ddf3d95c8628ca779884b28305_58.png)

On the table。Two dimensional x and Y stands up vertically。



![](img/a00342ddf3d95c8628ca779884b28305_60.png)

So the idea is the same， want to we've got a whole continuous cloud of y's and x's。

 we go to a particular point x with two coordinates。

 x1 and x2 and we say what's a good value for the function at that point well we're just going to go up in the slice and average the y's above that point and we'll do that at all points in the plane。



![](img/a00342ddf3d95c8628ca779884b28305_62.png)

![](img/a00342ddf3d95c8628ca779884b28305_63.png)

![](img/a00342ddf3d95c8628ca779884b28305_64.png)

![](img/a00342ddf3d95c8628ca779884b28305_65.png)

![](img/a00342ddf3d95c8628ca779884b28305_66.png)

We said it's the ideal or optimal predictor of why with regard for the function and what that means is。

Actually， it's with regard to a loss function。 and what it means is that particular choice of the function F of x will minimize the sum squared errors。

 which we write in this fashion。

![](img/a00342ddf3d95c8628ca779884b28305_68.png)

![](img/a00342ddf3d95c8628ca779884b28305_69.png)

![](img/a00342ddf3d95c8628ca779884b28305_70.png)

Again， expected value of y minus。G of x over all functions。 G at at each point X， right。

 So it minimizes the average。

![](img/a00342ddf3d95c8628ca779884b28305_72.png)

![](img/a00342ddf3d95c8628ca779884b28305_73.png)

Prediction errors。

![](img/a00342ddf3d95c8628ca779884b28305_75.png)

Now， at each point X， we're going to make mistakes because if we use this function to predict y。

 because there's lots of y's at each point x right and so the errors that we make we call in this case we call them epsilons and those are the irreducible error。



![](img/a00342ddf3d95c8628ca779884b28305_77.png)

![](img/a00342ddf3d95c8628ca779884b28305_78.png)

You might know the ideal function F， but of course。

 it doesn't make perfect predictions at each point X， so it has to make some errors， but on average。

 it does well。

![](img/a00342ddf3d95c8628ca779884b28305_80.png)

![](img/a00342ddf3d95c8628ca779884b28305_81.png)

![](img/a00342ddf3d95c8628ca779884b28305_82.png)

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

![](img/a00342ddf3d95c8628ca779884b28305_84.png)

So the problem is we can't carry out this recipe of conditional expectation or conditional averaging exactly because。

😊。

![](img/a00342ddf3d95c8628ca779884b28305_86.png)

At any given x in our data set， we might not have many points to average。

 we might not have any points to average。

![](img/a00342ddf3d95c8628ca779884b28305_88.png)

![](img/a00342ddf3d95c8628ca779884b28305_89.png)

In the figure， I've。We've got a much smaller data set now and we've still got the point x equals 4。

 and if you look there， you'll see carefully that the solid point is one point I put on the plot。

 the solid green point。

![](img/a00342ddf3d95c8628ca779884b28305_91.png)

![](img/a00342ddf3d95c8628ca779884b28305_92.png)

There's actually no data points whose x value is exactly4。

So how can we compute the conditional expectation or average。



![](img/a00342ddf3d95c8628ca779884b28305_94.png)

Well， what we can do is relax the idea of。At the point x to at in a neighborhood of the point X。

 And so that's what the notation here refers to。

![](img/a00342ddf3d95c8628ca779884b28305_96.png)

![](img/a00342ddf3d95c8628ca779884b28305_97.png)

N of x or script n of x is a neighborhood of points defined in some way around the target point。

 which is this x equals fourier。

![](img/a00342ddf3d95c8628ca779884b28305_99.png)

![](img/a00342ddf3d95c8628ca779884b28305_100.png)

And it keeps a spirit of conditional expectation， it's close to the target point x。

 and if we make that neighborhood wide enough we'll have enough points in the neighborhood to average and we'll use their average to estimate the conditional expectation。

So this is called nearest neighbor or local A it's a very clever idea， it's not my idea。

 it has been invented a long time ago and of course you'll move this neighborhood。

 you'll slide this neighborhood along the X axis and as you compute the averages as you slide in along。

 it'll trace out a curve。😊，So that's actually a very good estimate of the of the function F。

 It's not going to be perfect。

![](img/a00342ddf3d95c8628ca779884b28305_102.png)

Because the little window has a certain width and so as we can see。

 some points of the true F may be lower and some points higher， but on average it does quite well。



![](img/a00342ddf3d95c8628ca779884b28305_104.png)

So we have a pretty powerful tool for estimating this conditional expectation。

 just relax the definition and compute the nearest neighbor average。

 and it gives us a fairly flexible way of fitting a function。😊。



![](img/a00342ddf3d95c8628ca779884b28305_106.png)

![](img/a00342ddf3d95c8628ca779884b28305_107.png)

![](img/a00342ddf3d95c8628ca779884b28305_108.png)

We'll see in the next section that this doesn't always work。

 especially as the dimensions get larger and we'll have to have ways of dealing with that。



![](img/a00342ddf3d95c8628ca779884b28305_110.png)

![](img/a00342ddf3d95c8628ca779884b28305_111.png)