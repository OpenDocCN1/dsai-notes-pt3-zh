# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P10：P10 StatsLearning Lect5c 110613.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

We're now going to start a discussion of multiple linear regression。

 which is regression with more than one predictor。

![](img/1f6cc21372892079d1118bb785f83889_1.png)

![](img/1f6cc21372892079d1118bb785f83889_2.png)

WellI should say the word。The term regression is kind of unusual。

 you might be wondering why linear regression， it's a linear model。

 and this is actually it is an unusual term， it's actually historical。

 it comes from the idea of regression towards the mean。

 which is a concept which was discussed in the early 1900s。



![](img/1f6cc21372892079d1118bb785f83889_4.png)

![](img/1f6cc21372892079d1118bb785f83889_5.png)

![](img/1f6cc21372892079d1118bb785f83889_6.png)

![](img/1f6cc21372892079d1118bb785f83889_7.png)

You might want to look that up yourself and later on in the course we'll describe it what regression towards aus。

 but it's resulted in a sort of unusual name for a linear model called。



![](img/1f6cc21372892079d1118bb785f83889_9.png)

![](img/1f6cc21372892079d1118bb785f83889_10.png)

Linear regression。We have to live with this term because it's become sort of time honored。



![](img/1f6cc21372892079d1118bb785f83889_12.png)

So multiple linear regression now extends the simple model till we have more than one predictor。

 like in this our example， we have three predictors。



![](img/1f6cc21372892079d1118bb785f83889_14.png)

![](img/1f6cc21372892079d1118bb785f83889_15.png)

So we want to fit them all together and use them all together to predict the outcome。



![](img/1f6cc21372892079d1118bb785f83889_17.png)

So here's the model。We have an overall。

![](img/1f6cc21372892079d1118bb785f83889_19.png)

Intercept term， and then we have a slope for each of the predictors in the model， which again。

 the betas are the parameters， they're unknown， and the x's are observed。

 and we're trying to use the x's to predict y。

![](img/1f6cc21372892079d1118bb785f83889_21.png)

![](img/1f6cc21372892079d1118bb785f83889_22.png)

So in the advertising examples， particularly we'll have the three predictors， TV， radio。

 and newspaper advertising， and we're going to try to predict sales。



![](img/1f6cc21372892079d1118bb785f83889_24.png)

![](img/1f6cc21372892079d1118bb785f83889_25.png)

And we have the error term for allowing points to deviate around the。



![](img/1f6cc21372892079d1118bb785f83889_27.png)

The function。 And now the function actually is a， it's a called a hyperplane。

 Let's actually flip ahead to slide。

![](img/1f6cc21372892079d1118bb785f83889_29.png)

19 for a moment， I have a picture of this。 So whereas before we had a line， now it's a hyperplane。



![](img/1f6cc21372892079d1118bb785f83889_31.png)

So I've been able to draw it here just for two predictors。



![](img/1f6cc21372892079d1118bb785f83889_33.png)

It's hard to draw for three， but now the lines is now replaced by this flat surface called a plane or hyperplane。

 So here's our data points for each point we have its two predictor values。



![](img/1f6cc21372892079d1118bb785f83889_35.png)

![](img/1f6cc21372892079d1118bb785f83889_36.png)

![](img/1f6cc21372892079d1118bb785f83889_37.png)

Let's say TV a newspaper， and we have its sales on the vertical axis and here's each data point is a red point。



![](img/1f6cc21372892079d1118bb785f83889_39.png)

We're going to what multiple progression does， it fits a hyperplane， a plane。



![](img/1f6cc21372892079d1118bb785f83889_41.png)

To these points， to minimize。

![](img/1f6cc21372892079d1118bb785f83889_43.png)

The square distance between each point and the closest point in the plane。



![](img/1f6cc21372892079d1118bb785f83889_45.png)

Very intuitive in the same way we did it with for line， now the line becomes a plane。



![](img/1f6cc21372892079d1118bb785f83889_47.png)

Okay， so let's now go back to the。

![](img/1f6cc21372892079d1118bb785f83889_49.png)

Okay， so the model， again， so this is it's an equation of hyperplane with its coefficients， okay？



![](img/1f6cc21372892079d1118bb785f83889_51.png)

![](img/1f6cc21372892079d1118bb785f83889_52.png)

Well， before we talk about the least squares estimates and some of the details。

 let's sort of step back for a moment， think about how we might interpret the regression coefficients because now there's more than one of them in a simple model we had only one to deal with now we have a multiple。

 say three coefficients。

![](img/1f6cc21372892079d1118bb785f83889_54.png)

![](img/1f6cc21372892079d1118bb785f83889_55.png)

![](img/1f6cc21372892079d1118bb785f83889_56.png)

How do we interpret them？

![](img/1f6cc21372892079d1118bb785f83889_58.png)

Together。If the predictors had no correlation。

![](img/1f6cc21372892079d1118bb785f83889_60.png)

Now words in the data， then we could talk about predict each coefficient separately。



![](img/1f6cc21372892079d1118bb785f83889_62.png)

We can make statements like a unit change in Xj， for example。

 is associated with the beta J change that's is coefficient in the outcome。



![](img/1f6cc21372892079d1118bb785f83889_64.png)

![](img/1f6cc21372892079d1118bb785f83889_65.png)

With all the other。Other variables fixed。

![](img/1f6cc21372892079d1118bb785f83889_67.png)

But。Predictors are not usually uncorrelated in the data， for example here。



![](img/1f6cc21372892079d1118bb785f83889_69.png)

We can expect， and we'll see actually that the various amounts spent on the three kinds of advertising are correlated。



![](img/1f6cc21372892079d1118bb785f83889_71.png)

So。

![](img/1f6cc21372892079d1118bb785f83889_73.png)

These kind of interpretations are difficult in observational data where they are correlated。



![](img/1f6cc21372892079d1118bb785f83889_75.png)

What problem does the correlation cause， well， the variance of all coefficients tend to increase sometimes dramatically。



![](img/1f6cc21372892079d1118bb785f83889_77.png)

In particular， imagine we have two predictors which are almost identical。

Then we can't really separate their coefficients if I have a coefficient on one variable。

 I could just as soon move that coefficient to the other variable and the fit of the model is going to be pretty much the same。



![](img/1f6cc21372892079d1118bb785f83889_79.png)

![](img/1f6cc21372892079d1118bb785f83889_80.png)

![](img/1f6cc21372892079d1118bb785f83889_81.png)

So the variances of the coefficients of those two predictors are going to be very large， right？



![](img/1f6cc21372892079d1118bb785f83889_83.png)

And then interpretation becomes difficult when there's correlation。



![](img/1f6cc21372892079d1118bb785f83889_85.png)

If one can't really say， suppose I were to change XJ。 and if we can think about。

 suppose I was to change， I was to increase the TV advertising by a certain amount。



![](img/1f6cc21372892079d1118bb785f83889_87.png)

![](img/1f6cc21372892079d1118bb785f83889_88.png)

What would be the effect on sales Well， if that happened。

 we might we probably wouldn't be reasonable to assume that the other advertising budgets stay the same。



![](img/1f6cc21372892079d1118bb785f83889_90.png)

![](img/1f6cc21372892079d1118bb785f83889_91.png)

For example， maybe the company has a fixed budget overall， so that if increased TB advertising。

 I would have to decrease the other advertising。

![](img/1f6cc21372892079d1118bb785f83889_93.png)

Or maybe TV advertising is increasing just because the company has more money in general。



![](img/1f6cc21372892079d1118bb785f83889_95.png)

![](img/1f6cc21372892079d1118bb785f83889_96.png)

And decides if wants to spend more on advertising of all kinds。So in both those cases。

 wet really can't really talk about the change of one predictor where the other one's fixed because。



![](img/1f6cc21372892079d1118bb785f83889_98.png)

![](img/1f6cc21372892079d1118bb785f83889_99.png)

The the predictors will tend to move together in in real data。



![](img/1f6cc21372892079d1118bb785f83889_101.png)

And what this means is claims of causality should be avoided。 right， We can't really say that。



![](img/1f6cc21372892079d1118bb785f83889_103.png)

One predictor causes the outcome when there's predictors。



![](img/1f6cc21372892079d1118bb785f83889_105.png)

In the system that are correlated with that given predictor。



![](img/1f6cc21372892079d1118bb785f83889_107.png)

So this becomes a complicated。

![](img/1f6cc21372892079d1118bb785f83889_109.png)

Challenge to try to discuss causality and we're going to avoid that。



![](img/1f6cc21372892079d1118bb785f83889_111.png)

And there's a nice book which actually I was a graduate student。

 and I was one of the books I learned from data analysis and regression by Moslo and Tki。

 two very famous statisticians。

![](img/1f6cc21372892079d1118bb785f83889_113.png)

嗯。And。I look the book now ands' I don't like the book that much overall。

 but there's one wonderful chapter called the woes of regression coefficients that talks about。



![](img/1f6cc21372892079d1118bb785f83889_115.png)

![](img/1f6cc21372892079d1118bb785f83889_116.png)

The problems of interpreting regression coefficients when there's in a multiple regression model。

 that's a very useful chapter to read。

![](img/1f6cc21372892079d1118bb785f83889_118.png)

![](img/1f6cc21372892079d1118bb785f83889_119.png)

And I made this point。 So the first point here I've just made that。



![](img/1f6cc21372892079d1118bb785f83889_121.png)

regressionggress coefficient， what it measures is the change in y per unit change in XJ with all other predictors held fixed。



![](img/1f6cc21372892079d1118bb785f83889_123.png)

But this is not usually a reflection of reality， because usually when you change one predictor。

 the others change as well。

![](img/1f6cc21372892079d1118bb785f83889_125.png)

![](img/1f6cc21372892079d1118bb785f83889_126.png)

I mentioned an example with advertising。So here's a couple of examples which just have you think about and maybe we'll put it on a quiz。

 but here's an example， the first example to have you think about this point。

 supposeupp I measure the total amount of change in your pocket。嗯。And that's why。

 but I also measure two predictors， the number of coins。And the number of pennies， nichels。

 and dimmes， that's x2。Now， by itself， the regression coefficient of Y on the total number of pennies nichols and dimmes would probably be positive。

 the more you have of these， the more likely that you have more change。

But what about if I have x1 in the model？So for a given level of x1。嗯。



![](img/1f6cc21372892079d1118bb785f83889_128.png)

Think about whether the coefficient of x2 will be positive or negative。嗯。

And we'll talk about the answer to this later on， but it's a simple example where you can see now how the presence of one predictor affects the way that we think about。

 interpret the coefficient of another predictor and of course these two predictors are highly correlated by construction。



![](img/1f6cc21372892079d1118bb785f83889_130.png)

![](img/1f6cc21372892079d1118bb785f83889_131.png)

Another example， which is actually from this book， the chapter of this book。From American football。

Why is the number of tackles by a football player in the season？W and HR is height in weight。And。

They imagine that they take data on from this situation， they fit a regression model。And they obtain。

 you know。Beta is 0 but the coefficient of weight is 0。50， coefficient of height is minus 0。10。

Which seems to say that it's better to be short。To make more tackles。

 but so the question we're asking here is， how would you interpret this coefficient of height？

Given the weights in the model。And again， think about this and we'll return to the answer later。



![](img/1f6cc21372892079d1118bb785f83889_133.png)

And。They also mention in that same book。

![](img/1f6cc21372892079d1118bb785f83889_135.png)

There's two quotes， essentially by George Box， who was another famous statistician。



![](img/1f6cc21372892079d1118bb785f83889_137.png)

Essentially， all models are wrong， but some are useful。

I's interesting because it's true that as we saw， like on the very first slide， the regression model。

 a linear model is never exactly right。

![](img/1f6cc21372892079d1118bb785f83889_139.png)

![](img/1f6cc21372892079d1118bb785f83889_140.png)

But， but it's often very useful。 So it's， it's important to remember that。



![](img/1f6cc21372892079d1118bb785f83889_142.png)

The model that you assume is not to take it too seriously， Test out your model。



![](img/1f6cc21372892079d1118bb785f83889_144.png)

Remember that it's going to be wrong， but also remember the fact that despite the fact it be。

 it's an approximation， it can be a very useful approximation in many situations。



![](img/1f6cc21372892079d1118bb785f83889_146.png)

And then this point。

![](img/1f6cc21372892079d1118bb785f83889_148.png)

In their chapter， also paraphrasing George B。Whi really sort of it sums up the what I talked about trying to interpret regression coefficients。

 the only way to find out what will happen when a complex system is disturbed is to disturb the system。



![](img/1f6cc21372892079d1118bb785f83889_150.png)

![](img/1f6cc21372892079d1118bb785f83889_151.png)

Not merely to observe it passively。 Now words， if you you want to make a causal statement about a predictor for an outcome。

 you actually have to be able to take the system and perturb that that particular predictor。



![](img/1f6cc21372892079d1118bb785f83889_153.png)

![](img/1f6cc21372892079d1118bb785f83889_154.png)

![](img/1f6cc21372892079d1118bb785f83889_155.png)

Keeping the other ones fixed。That will allow you to make a causal statement about。



![](img/1f6cc21372892079d1118bb785f83889_157.png)

A variable like X J in its effect on the outcome。 It's not good enough simply to observe。



![](img/1f6cc21372892079d1118bb785f83889_159.png)

Of。

![](img/1f6cc21372892079d1118bb785f83889_161.png)

Some some observations from the system。 We can't use that data to conclude causality。

 So if you want to know what happens when a complex system is perturbed， you have to perturb it。

 You can't simply observe it。 So I think it's a very。

 very wise thing to remember a wise summary of the。



![](img/1f6cc21372892079d1118bb785f83889_163.png)

![](img/1f6cc21372892079d1118bb785f83889_164.png)

![](img/1f6cc21372892079d1118bb785f83889_165.png)

Of the use of models and observational data。

![](img/1f6cc21372892079d1118bb785f83889_167.png)

Okay。So how do we find the least squares estimates for the multiple regressiongressional model。

 what's really very much the same the same tack we took for the simple model， so first of all。

 our predictions will be given by this equation， this is the intercept。



![](img/1f6cc21372892079d1118bb785f83889_169.png)

![](img/1f6cc21372892079d1118bb785f83889_170.png)

![](img/1f6cc21372892079d1118bb785f83889_171.png)

![](img/1f6cc21372892079d1118bb785f83889_172.png)

And now we remember we have one slope parameter for each predictor。



![](img/1f6cc21372892079d1118bb785f83889_174.png)

We put hats on there， as we always will， when we infer that value from data， the estimates。

 and now what's called the multiple least squares estimates are the values that the minimize the sum of square deviations。



![](img/1f6cc21372892079d1118bb785f83889_176.png)

![](img/1f6cc21372892079d1118bb785f83889_177.png)

Of points around the plane。

![](img/1f6cc21372892079d1118bb785f83889_179.png)

Remember that， let's go？Remember I had to show this picture？



![](img/1f6cc21372892079d1118bb785f83889_181.png)

Here's my data points。Here's my approximating least squares plane。

 and I'm going to choose the orientation and height of this plane to minimize the total square distance between the red points。



![](img/1f6cc21372892079d1118bb785f83889_183.png)

![](img/1f6cc21372892079d1118bb785f83889_184.png)

And their closest point on the hyperplane。

![](img/1f6cc21372892079d1118bb785f83889_186.png)

Those are called the least squares estimates。I I' going to call the multiple least squares essence because there's multiple predictors。



![](img/1f6cc21372892079d1118bb785f83889_188.png)

There actually there is a formula for these coefficients for the estimates。

 it's kind of messy and it's not something that you won ever computes by hand。

 although probably in the early 1960s people used to do these poor guys used to actually compute least squares estimates by hand。



![](img/1f6cc21372892079d1118bb785f83889_190.png)

![](img/1f6cc21372892079d1118bb785f83889_191.png)

They were good at doing matrix computations， but today we have the luxury of fast computers。



![](img/1f6cc21372892079d1118bb785f83889_193.png)

![](img/1f6cc21372892079d1118bb785f83889_194.png)

And you know， in a program like R or any other statistical package。

 we can compute the least scores estimates for very big data sets very quickly。

 So we don't need to worry about the formula that we just need to know what we're doing。

 which is we're finding this the values of the coefficients that minimize the。



![](img/1f6cc21372892079d1118bb785f83889_196.png)

![](img/1f6cc21372892079d1118bb785f83889_197.png)

The sum of squares。

![](img/1f6cc21372892079d1118bb785f83889_199.png)

So here's what we get for。

![](img/1f6cc21372892079d1118bb785f83889_201.png)

The advertising data。

![](img/1f6cc21372892079d1118bb785f83889_203.png)

The top table are the coefficients， standard errors， et cetera。



![](img/1f6cc21372892079d1118bb785f83889_205.png)

Here's these are the least squares estimates。Again。

 there's a lot of terminology here coefficient or parameter。



![](img/1f6cc21372892079d1118bb785f83889_207.png)

We'll use those interchangeably as people do。

![](img/1f6cc21372892079d1118bb785f83889_209.png)

The intercept， again， we're not typically interested in the intercept because that's just telling us whether the。



![](img/1f6cc21372892079d1118bb785f83889_211.png)

Setting the other three predictors to 0， whether the。Sales is。



![](img/1f6cc21372892079d1118bb785f83889_213.png)

The average， the average。Sales value， so we don't really care about that。

 but we care about the slopes， which are these guys。



![](img/1f6cc21372892079d1118bb785f83889_215.png)

![](img/1f6cc21372892079d1118bb785f83889_216.png)

These three values here， so we see， for example。The coefficient of TV is 0。046， standard error。

 the T statistic is the ratio。

![](img/1f6cc21372892079d1118bb785f83889_218.png)

![](img/1f6cc21372892079d1118bb785f83889_219.png)

。046 divided by 。0014。And the T statistic， you remember， I said。

 a T statistic of a bigger than about two is significant at 0。005。



![](img/1f6cc21372892079d1118bb785f83889_221.png)

![](img/1f6cc21372892079d1118bb785f83889_222.png)

P value 。05 P value。 So the P value of 32 is huge， and the P value is。



![](img/1f6cc21372892079d1118bb785f83889_224.png)

Lessson 。0001。Similarly for radio， very big effect。



![](img/1f6cc21372892079d1118bb785f83889_226.png)

Newspaper， newspaper looks like it's not having much effect， right It's too statistic is minus0。18。



![](img/1f6cc21372892079d1118bb785f83889_228.png)

Which has got our P value， which is。Large。

![](img/1f6cc21372892079d1118bb785f83889_230.png)

And P values is close to1 P values above 0。05 or 0。1 are not significant。're not they're not。



![](img/1f6cc21372892079d1118bb785f83889_232.png)

嗯。Evidence against the null hypothesis， which is that the coefficient is zero。



![](img/1f6cc21372892079d1118bb785f83889_234.png)

So but let's be little more careful how we interpret this。Remember。

 each of these statements is made conditional on the other two being in the model。



![](img/1f6cc21372892079d1118bb785f83889_236.png)

In particular， this， this coefficient says， given I I have the。



![](img/1f6cc21372892079d1118bb785f83889_238.png)

The amount of money spent on radio and newspaper。

![](img/1f6cc21372892079d1118bb785f83889_240.png)

Spending money on TV is still produces a change in sales。

 So's in the presence of the other two predictors， TV is important。



![](img/1f6cc21372892079d1118bb785f83889_242.png)

![](img/1f6cc21372892079d1118bb785f83889_243.png)

Similarly for radio， the presence of TV and radio。Advertising。



![](img/1f6cc21372892079d1118bb785f83889_245.png)

Excuse me， TV and newspaper advertising， radio advertising。



![](img/1f6cc21372892079d1118bb785f83889_247.png)

Can be effective， but newspaper is not in the presence of these two。 So in particular。

 on its own newspaper。

![](img/1f6cc21372892079d1118bb785f83889_249.png)

Maybe significant， it's coefficient， maybe be significant。

 but in the presence of the other two in the multiple model， it's not showing significance。



![](img/1f6cc21372892079d1118bb785f83889_251.png)

![](img/1f6cc21372892079d1118bb785f83889_252.png)

And。😔，We can look at the correlations actually here are the simple correlations between the predictors。



![](img/1f6cc21372892079d1118bb785f83889_254.png)

And we see there's some significant correlations。

![](img/1f6cc21372892079d1118bb785f83889_256.png)

For example。

![](img/1f6cc21372892079d1118bb785f83889_258.png)

TV and sales。Well， TV sales is the outcome。 but in particular， I see。

 radio and newspaper have a correlation of。

![](img/1f6cc21372892079d1118bb785f83889_260.png)

![](img/1f6cc21372892079d1118bb785f83889_261.png)

。35。So what's likely happened here is that。

![](img/1f6cc21372892079d1118bb785f83889_263.png)

Any effective newspaper has been soaked up by radio because they're correlated at 035。



![](img/1f6cc21372892079d1118bb785f83889_265.png)

So。

![](img/1f6cc21372892079d1118bb785f83889_267.png)

With radio in the model， newspaper is no longer needed。It doesn't tell us anything more。



![](img/1f6cc21372892079d1118bb785f83889_269.png)

It doesn't improve the prediction given we've measured the radio advertising。



![](img/1f6cc21372892079d1118bb785f83889_271.png)

And that's because of the correlation being 0。35。On the other hand。

 it looks like TV and radio were pretty uncorrelated。



![](img/1f6cc21372892079d1118bb785f83889_273.png)

And so their effects are somewhat compliment。

![](img/1f6cc21372892079d1118bb785f83889_275.png)

So that completes our discussion of this example in the next segment we'll talk about some important questions and arise when you use regression for real data analysis。



![](img/1f6cc21372892079d1118bb785f83889_277.png)