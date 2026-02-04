# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P3：P3 StatsLearning Lect3 4a 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/9d35f65df6a7f977cfdd2d88df7444f5_0.png)

Okay we're going to talk about statistical learning and models now。

 I'm going to tell you what models are good for， how we use them。

 and what are some of the issues involved。Okay， so we see three plots in front of us。

These are sales figures from a marketing campaign。As a function of the amount spent on TV ads。

 radio ads and newspaper ads。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_2.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_3.png)

And you can see the at least in the first two is somewhat of a trend。

 and in fact we've summarized the trend by a little linear regression line in each。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_5.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_6.png)

And so we see that there's some relationship， the first two again， look stronger than the third。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_8.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_9.png)

Now， in a situation like this， we typically like to know the joint relationship between the response sales and all three of these together。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_11.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_12.png)

You know we want to understand how they operate together to influence sales。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_14.png)

So you can think of that as wanting to model sales as a function。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_16.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_17.png)

Of TV， radio and newspaper all jointly together。 So how do we do that？



![](img/9d35f65df6a7f977cfdd2d88df7444f5_19.png)

So before we get into the details。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_21.png)

Let's set up some notation。 So your sales is the response or the target that we wish to predict or model。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_23.png)

And we usually refer to it as Y， we use the letter Y to refer to it TV is one of the features or inputs or predictors。

 and we'll call it x1， likewise， radio is x2 and so on。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_25.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_26.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_27.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_28.png)

So in this case， we've got three predictors and we can refer to them collectively by a vector。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_30.png)

As x equal to with three components， x1， x2 and x3 and vectors we generally think of as column vectors。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_32.png)

And so that's a little bit of notation。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_34.png)

And so now in this more compact notation， we can write our model as y equals function of x。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_36.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_37.png)

Plus， error。And this error is just a catchule it captures the measurement errors。

 maybe in y and other discrepancies， our function of x is never going to model y perfectly。

 so there's going to be a lot of things we can't capture with the function and that's caught up in the error。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_39.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_40.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_41.png)

And again， f of x here。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_43.png)

Is now a function of this vector x， which has these three arguments。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_45.png)

three components。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_47.png)

So what is the function f of x good for so with a good F we can make predictions of y at new points x equal to little x。

 so this notation capital x equals little x， you know capital x we think is the variable having these three components and little x is an instance also with three components。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_49.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_50.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_51.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_52.png)

Particular values for newspaper， radio and TV。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_54.png)

With the model we can understand which components of x in general that'll have P components if these P predictors are important to explain in why and which are irrelevant。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_56.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_57.png)

For example， if we model an income as a function of demographic variables。

 seniority and years of your education might have a big impact on income but marital status typically does not。

 and we'd like our model to be able to tell us that。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_59.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_60.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_61.png)

And depending on the complexity of if we may be able to understand how each component Xj affects y in what particular fashion。

 it affects y。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_63.png)

So models have many uses and those amongst them。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_65.png)

Okay， well， what is this function if and is there an ideal if？



![](img/9d35f65df6a7f977cfdd2d88df7444f5_67.png)

So in the plot， we've got a large sample of points from a population。

 there's just a single x in this case and a response Y。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_69.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_70.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_71.png)

And you can see it's a scatter plot so we see there's a lot of point， there's 2，000 points here。

 let's think of this as actually the whole population or rather as a representation of a very large population。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_73.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_74.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_75.png)

U。And so now let's think of what a good function F might be and let's say not just a whole function。

 but let's think what value would we like F to have at say the value of x equals4 So at this point over here。

 we want to query x or F at all values of x， but we wondering what it should be at the value 4。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_77.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_78.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_79.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_80.png)

So you'll notice that at the x equals 4， there's many values of y。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_82.png)

But a function can only take on one value。The function is going to deliver back one value。

 So what is a good value？Well。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_84.png)

One good value is to deliver back the average values of those ys who have x equal to 4。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_86.png)

And that we write in this sort of Matthew notation over here， it says。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_88.png)

The function at the value4 is the expected value of y given x equals 4。

 and that expected value is just a fancy word for average。 It's actually a conditional average。

 given x equals 4。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_90.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_91.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_92.png)

Since we can only deliver one value。Of the function at x equals 4。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_94.png)

The average seems like a good value。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_96.png)

And if we do that at each value of x， so at every single value of x。

 we deliver back the average of the y's that have that value of x， so for example， at x equals 5。😊。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_98.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_99.png)

Again， we want to have the average value in this little conditional slicelicier。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_101.png)

That will trace out this little red curve that we have here。

 and that's called the regression function。 So the regression function gives you the conditional expectation of y given x at each value of x。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_103.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_104.png)

So that in a sense， is the ideal function。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_106.png)

For for a population， in this case of Y and a single x。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_108.png)

So let's talk more about this regression function， it's also defined for a vector x。

 so if x has got three components， for example， it's going to be the conditional expectation of y given the three particular instances of the three components of x。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_110.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_111.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_112.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_113.png)

So if you think about that。Let's think of x as being two dimensional because we can think in three dimensions。

 So let's say x lies。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_115.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_116.png)

On the table。Two dimensional x and Y stands up vertically。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_118.png)

So the idea is the same， want to we've got a whole continuous cloud of y's and x's。

 we go to a particular point x with two coordinates。

 x1 and x2 and we say what's a good value for the function at that point。

 well we're just going to go up in the slice and average the y's above that point and we'll do that at all points in the plane。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_120.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_121.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_122.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_123.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_124.png)

We said it's the ideal or optimal predictor of why with regard for the function and what that means is。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_126.png)

Actually， it's with regard to a loss function and what it means is that particular choice of the function f of x will minimize the sum squared errors。

 which we write in this fashion。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_128.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_129.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_130.png)

Again， the expected value of y minus。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_132.png)

G of x over all functions G。😡，At at each point， X， right， So it minimizes the average。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_134.png)

Prediction errors。Now at each point x we're going to make mistakes because if we use this function to predict y。

 because there's lots of y's at each point x right and so the errors that we make we call in this case we call them epsilons and those are the irreducible error。

You might know the ideal function F， but of course it doesn't make perfect predictions at each point x。

 so it has to make some errors， but on average it does well。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_136.png)

For any estimate， if hat of x， and that's what we tend to do， we tend to put these little。Hats。

On estimators to show that they've been estimated from data。

And so F hat of x is an estimate of f of x。We can expand。

The squared prediction error at x into two pieces。There's the irreducible piece。

 which is just the variance of the errors。And there's the reducible piece。

 which is the difference between our estimate f hat of x。And the true function， F of x。Okay。

And that's a squared component。 So this expected prediction error breaks up into these two pieces。

So that's important to bear in mind， so if we want to improve our model it's this first piece。

 the reducible piece that we can improve by maybe changing the way we estimate F of X。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_138.png)

Okay， so that's all nice， this is a kind of as up to now has been somewhat of a theoretical exercise。

 well how do we estimate the function F？😊。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_140.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_141.png)

So the problem is we can't carry out this recipe of conditional expectation or conditional averaging exactly because。

😊。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_143.png)

At any given X in our data set， we might not have many points to average。

 We might not have any points to average。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_145.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_146.png)

In the figure I've。We've got a much smaller data set now and we've still got the point x equals 4。

 and if you look there， you'll see carefully that the solid point is one point I put on the plot。

 the solid green point。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_148.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_149.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_150.png)

There's actually no data points whose x value is exactly4。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_152.png)

So how can we compute the conditional expectation or average。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_154.png)

Well， what we can do is relax the idea of。At the point X to at in a neighborhood of the point X。

 And so that's what the notation here refers to。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_156.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_157.png)

N of x or script n of x is a neighborhood of points defined in some way around the target point。

 which is this x equals fourier。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_159.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_160.png)

And it keeps a spirit of conditional expectation， it's close to the target point x。

 and if we make that neighborhood wide enough， we'll have enough points in the neighborhood to average and we'll use their average to estimate the conditional expectation。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_162.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_163.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_164.png)

So this is called nearest neighborigh or local A， it's a very clever idea， it's not my idea。

 it has invented a long time ago， and of course you'll move this neighborhood。

 you'll slide this neighborhood along the X axis and as you compute the averages as you slide in along。

 it'll trace out a curve。😊。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_166.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_167.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_168.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_169.png)

So that's actually a very good estimate of the， the of the function F。 It's not going to be perfect。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_171.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_172.png)

Because the little window has a certain width and so as we can see。

 some points of the true F may be lower and some points higher， but on average it does quite well。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_174.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_175.png)

So we have a pretty powerful tool here for estimating this conditional expectation。

 just relax the definition and compute the nearest neighbor average。

 and it gives us a fairly flexible way of fitting a function。😊。



![](img/9d35f65df6a7f977cfdd2d88df7444f5_177.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_178.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_179.png)

We'll see in the next section that this doesn't always work， especially as the dimensions get larger。

 and we'll have to have ways of dealing with that。

![](img/9d35f65df6a7f977cfdd2d88df7444f5_181.png)

![](img/9d35f65df6a7f977cfdd2d88df7444f5_182.png)