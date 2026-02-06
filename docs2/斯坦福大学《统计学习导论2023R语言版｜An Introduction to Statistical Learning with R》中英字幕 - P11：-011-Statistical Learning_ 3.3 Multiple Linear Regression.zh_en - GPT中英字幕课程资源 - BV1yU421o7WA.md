# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P11：-011-Statistical Learning_ 3.3 Multiple Linear Regression.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

we're now going to start our discussion of multiple linear regression。

 which is regression with more than one predictor。

![](img/a0d1fd5e84f742c50c49355627c926f2_1.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_2.png)

I should say the word。The term regression is kind of unusual。

 you might be wondering why linear regression， it's a linear model。

 and this is actually it is an unusual term， it's actually historical。

 it comes from the idea of regression towards the mean which is a concept which was discussed in the early 1900s。



![](img/a0d1fd5e84f742c50c49355627c926f2_4.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_5.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_6.png)

You might want to look that up yourself and later on in the course we'll describe what regression towards the meanus。

 but it's resulted in a sort of unusual name for a linear model called，嗯。Linear regression。

We have to live with this term because it's become sort of time honored。



![](img/a0d1fd5e84f742c50c49355627c926f2_8.png)

So multiple linear regression now extends the simple model till we have more than one predictor。

 like in this our example， we have three predictors。



![](img/a0d1fd5e84f742c50c49355627c926f2_10.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_11.png)

So we want to fit them all together and use them all together to predict the outcome。



![](img/a0d1fd5e84f742c50c49355627c926f2_13.png)

So here's the model。We have an overall。

![](img/a0d1fd5e84f742c50c49355627c926f2_15.png)

Intercept term， and then we have a slope for each of the predictors in the model， which again。

 the betas are the parameters， they're unknown， and the x's are observed and we're trying to use the x's to predict y。



![](img/a0d1fd5e84f742c50c49355627c926f2_17.png)

So in the advertising example， we particularly we' have the three predictors， TV， radio。

 and newspaper advertising， and we're going to try to predict sales。



![](img/a0d1fd5e84f742c50c49355627c926f2_19.png)

And we have the error term for allowing points to deviate around the。



![](img/a0d1fd5e84f742c50c49355627c926f2_21.png)

The function。 and now the function actually is a， it's called a hyperplane。

 Let's actually flip ahead to slide。

![](img/a0d1fd5e84f742c50c49355627c926f2_23.png)

19 for a moment， I have a picture of this， so whereas before we had a line， now it's a hyperplane。



![](img/a0d1fd5e84f742c50c49355627c926f2_25.png)

So I've been able to draw it here just for two predictors。It's hard to draw for three。

 but now we the lines is now replaced by this flat surface called a plane or hyperplane so here's our data points for each point we have its two predictor values。



![](img/a0d1fd5e84f742c50c49355627c926f2_27.png)

Let's say TV a newspaper and we have its sales on the vertical axis here's each data point is a red point。



![](img/a0d1fd5e84f742c50c49355627c926f2_29.png)

We're going what multiple progression does， it fits a hyperplane， a plane。



![](img/a0d1fd5e84f742c50c49355627c926f2_31.png)

To these points， to minimize。

![](img/a0d1fd5e84f742c50c49355627c926f2_33.png)

The square distance between each point and the closest point in the plane。



![](img/a0d1fd5e84f742c50c49355627c926f2_35.png)

Right。Very intuitive in the same way we did it with for a line， now the line becomes a plane。



![](img/a0d1fd5e84f742c50c49355627c926f2_37.png)

Okay， so let's now go back to the。

![](img/a0d1fd5e84f742c50c49355627c926f2_39.png)

Okay， so the model， again， so this is it's an equation of hyperplane with its coefficients， okay？



![](img/a0d1fd5e84f742c50c49355627c926f2_41.png)

Well， before we talk about the least squares estimates and some of the details。

 let's sort of step back for a moment， think about how we might interpret the regression coefficients because now there's more than one of them in a simple model we had only one to deal with now we have a multiple。

 say3 coefficients。How do we interpret them？Together。If the predictors had no correlation。

In words in the data， then we could talk about predict each coefficient separately。

We can make statements like a unit change in Xj， for example。

 is associated with the betaj change that's this coefficient in the outcome。With all the other。

Other variables fixed。But。Predictors are not usually uncorrelated in the data， for example here。

We can expect and we'll see actually the various amounts spent on the three kinds of advertising are correlated。

So。These kind of interpretations are difficult in observational data where are correlated。

What problem does the correlation cause， well， the variance of all coefficients tend to increase sometimes dramatically。

In particular， imagine we have two predictors which are almost identical。

Then we can't really separate their coefficients if I have a coefficient on one variable。

 I could just as soon move that coefficient to the other variable and the fit of the model is going to be pretty much the same。

So the variances of the coefficients of those two predictors are going to be very large， right？

And then interpretation becomes difficult when there's correlation。

One can't really say suppose I were to change XJ， and we can think about， suppose I was to change。

 I was to increase the TV advertising by a certain amount。What would be the effect on sales Well。

 if that happened， might we probably wouldn't be reasonable to assume that the other advertising budgets stay the same。

For example， maybe the company has a fixed budget overall， so that I increased TV advertising。

 I would have to decrease the other advertising。Or maybe TV advertising is increasing just because the company has more money in general。

And decides if wants to spend more on advertising of all kinds。So in both those cases。

 we really can't really talk about the change of one predictor where the other one's fixed。

The predictors will tend to move together in real data。

And what this means is claims of causality should be avoided。 right， We can't really say that。

One predictor causes the outcome when there's predictors。

In the system that are correlated with that given predictor。So this becomes a complicated。

Challenengge to try to discuss causality and we're going to avoid that。



![](img/a0d1fd5e84f742c50c49355627c926f2_43.png)

And there's a nice book which actually I was now was a graduate student。

 and I was one of the books I learned from data analysis and regression by Mos and Tki。

 two very famous statisticians。

![](img/a0d1fd5e84f742c50c49355627c926f2_45.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_46.png)

嗯。And。I look at the book now and I don't。

![](img/a0d1fd5e84f742c50c49355627c926f2_48.png)

I don't like the book that much overall， but there's one wonderful chapter on called the woes of regressionion coefficients that talks about。



![](img/a0d1fd5e84f742c50c49355627c926f2_50.png)

The problems of interpreting regression coefficients when there's in a multiple regression model。

 that's a very useful chapter to read。

![](img/a0d1fd5e84f742c50c49355627c926f2_52.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_53.png)

And I made this point， so the first point here I've just made that。



![](img/a0d1fd5e84f742c50c49355627c926f2_55.png)

regressiongress coefficient， what it measures is the change in y per unit change in XJ with all other predictors held fixed。

But this is not usually a reflection of reality， because usually when you change one predictor。

 the others change as well。

![](img/a0d1fd5e84f742c50c49355627c926f2_57.png)

I mentioned an example with advertising。So here's a couple of examples which just have you think about and maybe we'll put it on a quiz。

 but here's an example the first example to have you think about this point。

 supposeupp I measure the total amount of change in your pocket。



![](img/a0d1fd5e84f742c50c49355627c926f2_59.png)

嗯。And that's why， but I also measure two predictors， the number of coins。And the number of pennies。

 nichels， and dimmees， that's x2。

![](img/a0d1fd5e84f742c50c49355627c926f2_61.png)

Now， by itself， the regression coefficient of Y on the total number of pennies nichols and dimmes would probably be positive。

 the more you have of these， the more likely that you have more change。



![](img/a0d1fd5e84f742c50c49355627c926f2_63.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_64.png)

But what about if I have x1 in the model？So for a given level of x1。嗯。

Think about whether the coefficient of x2 will be positive or negative。嗯。

And we'll talk about the answer to this later on， but it's a simple example where you can see now how the presence of one predictor affects the way that we think about。

 interpret the coefficient of another predictor， and of course these two predictors are highly correlated by construction。



![](img/a0d1fd5e84f742c50c49355627c926f2_66.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_67.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_68.png)

Another example， which is actually from this book， the chapter of this book。From American football。

Why is the number of tackles by a football player in the season？W and HR is height in weight。And。

They imagine that they take data from this situation， they fit a regression model。And they obtain。

 you know。Beta 0 but the coefficient of weight is 0。50， coefficient of height is minus 0。10。

Which seems to say that it's better to be short。To make more tackles but so the question we're asking here is。

 how would you interpret this coefficient of height？Given the weights in the model。And again。

 think about this and we'll return to the answer later。



![](img/a0d1fd5e84f742c50c49355627c926f2_70.png)

And。They also mention in that same book。

![](img/a0d1fd5e84f742c50c49355627c926f2_72.png)

There's two quotes， essentially by George Box， who was another famous statistician。Essentially。

 all models are wrong， but some are useful。But this is。

It's interesting because it's true that as we saw like in the very first slide， the regression model。

 a linear model is never exactly right。But but it' often very useful。 So it'。

 it's important to remember that。The model that you assume is not to take it too seriously。

 test out your model。Remember that it's going to be wrong。

 but also remember the fact that despite the fact it can be。It's an approximation。

 it can be a very useful approximation in many situations。And then this point。In their chapter。

 also paraphrasing George B。Whi really sort of it sums up the what I talked about trying and interpret regression coefficients。

 the only way to find out what will happen when a complex system is disturbed is to disturb the system。



![](img/a0d1fd5e84f742c50c49355627c926f2_74.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_75.png)

Not merely to observe it passively。 Now words， if you want to make a causal statement about a predictor for an outcome。

 you actually have to be able to take the system and perturb that that particular predictor。



![](img/a0d1fd5e84f742c50c49355627c926f2_77.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_78.png)

Keeping the other ones fixed。That will allow you to make a causal statement about。

A variable like X J in its effect on the outcome， It's not good enough simply to observe。



![](img/a0d1fd5e84f742c50c49355627c926f2_80.png)

嗯。

![](img/a0d1fd5e84f742c50c49355627c926f2_82.png)

Some some observations from the system。 we can't use that data to conclude causality。

 So if you want to know what happens when a complex system is perturbed， you have to perturb it。

 You can't simply observe it。 So I think it's a very， very wise thing to remember。



![](img/a0d1fd5e84f742c50c49355627c926f2_84.png)

A wise summary of the。Of the use of models and observational data。



![](img/a0d1fd5e84f742c50c49355627c926f2_86.png)

Okay。So how do we find the least squares estimates for the multiple regressionggressional model。

 what's really very much the same the same tack we took for the simple model， so first of all。

 our predicted our predictions will be given by this equation。

 this is the intercept and now we remember we have one slope parameter for each predictor。

 we put hats on there as we always will when we infer that value from data， the estimates。

 and now what's called the multiple least squares estimates are the values that the minimize the sum of square deviations。



![](img/a0d1fd5e84f742c50c49355627c926f2_88.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_89.png)

Of points around the plane。

![](img/a0d1fd5e84f742c50c49355627c926f2_91.png)

Remember that， let's go。Remember I had to show this picture。



![](img/a0d1fd5e84f742c50c49355627c926f2_93.png)

Here's my data points。Here's my approximating least squares plane。

 and I'm going to choose the orientation and height of this plane to minimize the total square distance between the red points。



![](img/a0d1fd5e84f742c50c49355627c926f2_95.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_96.png)

And their closest point on the hyperplane。

![](img/a0d1fd5e84f742c50c49355627c926f2_98.png)

Those are called the least squares estimates。

![](img/a0d1fd5e84f742c50c49355627c926f2_100.png)

I I' going to call the multiple least square estimates because there's multiple predictors。



![](img/a0d1fd5e84f742c50c49355627c926f2_102.png)

There's actually there is a formula for these coefficients for the estimates。

 it's kind of messy and it's not something that you won ever computes by hand。

 although probably in the early 1960s people used to do these poor guys used to actually compute least squares estimates by hand。



![](img/a0d1fd5e84f742c50c49355627c926f2_104.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_105.png)

They were good at doing matrix computations， but today we have the luxury of fast computers。



![](img/a0d1fd5e84f742c50c49355627c926f2_107.png)

And you know， in a program like R or any other statistical package。

 we can compute the least scores estimates for very big data sets very quickly。

 so we don't need to worry about the formula that we just need to know what we're doing。

 which is we're finding this the values of the coefficients that minimize the。



![](img/a0d1fd5e84f742c50c49355627c926f2_109.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_110.png)

The sum of squares。

![](img/a0d1fd5e84f742c50c49355627c926f2_112.png)

So here's what we get for。

![](img/a0d1fd5e84f742c50c49355627c926f2_114.png)

The advertising data。

![](img/a0d1fd5e84f742c50c49355627c926f2_116.png)

The top table are the coefficients， standard errors， et cetera。



![](img/a0d1fd5e84f742c50c49355627c926f2_118.png)

Here's these are the least squares estimates。Again。

 there's a lot of terminology here coefficient or parameter。

We'll use those interchangeably and as people do。The intercept， again。

 we're not typically interested in the intercept because that's just telling us whether the。

Setting the other three predictors to zero， whether the。Sales is。The average the average。Sales value。

 so we don't really care about that， but we care about the slopes， which are these guys。

These three values here， so we see， for example。The coefficient of TV is 0。046， standard error。

 the T statistic is the ratio。

![](img/a0d1fd5e84f742c50c49355627c926f2_120.png)

。046 divided by 0。0014。And the T statistic， you remember， I said。

 a T statistic of a bigger than about two is significant at 0。005。



![](img/a0d1fd5e84f742c50c49355627c926f2_122.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_123.png)

P value 。05 P value。 So the P value of 32 is huge， and the P value is。



![](img/a0d1fd5e84f742c50c49355627c926f2_125.png)

Lessson 。0001。Similarly for radio， very big effect。Newspaper。

 newspaper looks like it's not having much effect， right It's too statistic is minus0。18。

Which has got a P value， which is。Large。And P values is close to 1 P values above 0。05 or 0。

1 are not significant。 not they're not。嗯。Evidence against the null hypothesis。

 which is that the coefficient is zero。

![](img/a0d1fd5e84f742c50c49355627c926f2_127.png)

So but let's be a more careful how we interpret this。Remember。

 each of these statements is made conditional on the other two being in the model。 So in particular。

 this this coefficient says given I have the。

![](img/a0d1fd5e84f742c50c49355627c926f2_129.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_130.png)

The amount of money spent on radio and newspaper。Spending money on TV still produces a change in sales。

In the presence of the other two predictors， TV is important。Similarly for radio。

 the presence of TV and radio。Advertising。Excuse me， TV and newspaper advertising， radio advertising。

Can be effective， but newspaper is not in the presence of these two。 So in particular。

 on its own newspaper。Maybe significant， it's coefficient， maybe be significant。

 but in the presence of the other two in the multiple model， it's not showing significance。And。

We can look at the correlations actually here here are the simple correlations between the predictors。

And we see there's some significant correlations。For example。TV and sales。Well。

 TV sales is the outcome， but in particular， let' see， radio and newspaper have a correlation of。



![](img/a0d1fd5e84f742c50c49355627c926f2_132.png)

![](img/a0d1fd5e84f742c50c49355627c926f2_133.png)

。35。So what's likely happened here is that。Any effective newspaper has been soaked up by radio because they're correlated at 035。

So。With radio in the model， newspaper is no longer needed。It doesn't tell us anything more。

It doesn't improve the prediction given we've measured the radio advertising。

And that's because of the correlation being 0。35。On the other hand。

 it looks like TV and radio are pretty uncorrelated。And so their effects are somewhat complementary。



![](img/a0d1fd5e84f742c50c49355627c926f2_135.png)

So that completes our discussion of this example， in the next segment we'll talk about some important questions and arise when you use regression for real data analysis。

