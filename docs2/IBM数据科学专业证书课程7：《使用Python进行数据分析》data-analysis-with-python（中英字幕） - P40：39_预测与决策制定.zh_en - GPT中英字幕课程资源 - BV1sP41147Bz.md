# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P40：39_预测与决策制定.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/230a8abadd3393eebbb648fc37b1e7b6_0.png)

🎼。In this video， our final topic will be on prediction and decision making。

 How can we determine if our model is correct。The first thing you should do is make sure your model results make sense。

 You should always use visualization， numerical measures for evaluation and comparing between different models。

Let's look at an example of prediction。 If you recall， we train the model using the fit method。Now。

 we want to find out what the price would be for a car that has a highway miles per gallon of 30。

Plugging this value into the predict method gives us a resulting price of $13771。30。

This seems to make sense。 for example， the value is not negative， extremely high or extremely low。

 We can look at the coefficients by examining the co F underscore attribute。If you recall。

 the expression for the simple linear model that predicts price from highway miles per gallon。

This value corresponds to the multiple of the highway miles per gallon feature。As such。

 an increase of one unit in highway miles per gallon。

 the value of the car decreases approximately $821。 This value also seems reasonable。

Sometimes your model will produce values that don't make sense。 For example。

 if we plot the model out for highway miles per gallon in the ranges of 0 to 100。

 we get negative values for the price。 This could be because the values in that range are not realistic。

 The linear assumption is incorrect。 or we don't have data for cars in that range。 In this case。

 it is unlikely that a car will have fuel mileage in that range。 So our model seems valid。

To generate a sequence of values in a specified range， import nu pi。

 then use the numppy a range function to generate the sequence。

 The sequence starts at one and increments by one till we reach 100。

 The first parameter is the starting point of the sequence。

 The second parameter is the end point plus one of the sequence。

 The final parameter is the step size between elements in the sequence。 In this case， it's one。

 So we increment the sequence。 one step at a time。 from one to 2 and so on。

We can use the output to predict new values。 The output is a numpy array。

 Many of the values are negative。Using a regression plot to visualize your data is the first method you should try。

 See the labs for examples of how to plot polynomial regression。For this example。

 the effect of the independent variable is evident In this case。

 The data trends down as the dependent variable increases。

 The plot also shows some nonlinear behavior。Examining the residual plot， we see， in this case。

 the residuals have a curvature suggesting nonlinear behavior。

A distribution plot is a good method for multiple linear regression。 For example。

 we see the predicted values for prices in the range from 30000 to 50000 are inaccurate。

This suggests a nonlinear model may be more suitable， or we need more data in this range。

The mean square error is perhaps the most intuitive numerical measure for determining if a model is good or not。

 Let's see how different measures of mean square error impact the model。

The figure shows an example of a mean square error of 3495。

This example has a mean square error of 3652。The final plot has a mean square error of 12870。

 As the square error increases， the targets get further from the predicted points。As we discussed。

 R squared is another popular method to evaluate your model。

 It tells you how well your line fits into the model。 R squared values range from 0 to 1。

 R squared tells us what percent of the variability in the dependent variable is accounted for by the regression on the independent variable。

😊，And R squared of one means that all movements to another dependent variable are completely explained by movements in the independent variables。

In this plot， we see the target points in red and the predicted line in blue and R squared of 0。9986。

 The model appears to be a good fit。 That means that more than 99 per cent of the variability of the predicted variable is explained by the independent variables。

This model has an R squared of 0。9226。 There still is a strong linear relationship。

 Model is still a good fit。 An r squared of 0，8，0，6 O the data。

 We can visually see that the values are scattered around the line。 They are still close to the line。

 and we can say that 80 per cent of the variability of the predicted variable is explained by the independent variables。

😊，And an R squared 0。61 means that approximately 61% of the observed variation can be explained by the independent variables。

An acceptable value for R square depends on what field you are studying and what your use case is。

Falcon Miller，1992， suggests that an acceptable R squared value should be at least 0。1。

Does a lower mean square error imply better fit， Not necessarily。

 M E for an M LR model will be smaller than the ME for an SLR model。

 Since the errors of the data will decrease when more variables are included in the model。

 Polynomial regression will also have a smaller MSE than regular regression in the next section。

 we will look at more accurate ways to evaluate the model。



![](img/230a8abadd3393eebbb648fc37b1e7b6_2.png)