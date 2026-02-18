# IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p55 25_过拟合、欠拟合和模型选择.zh_en -BV1NAq6Y9E7z_p55-

If you recall， in the last module， we discuss polynomial regression。In this section。

 we will discuss how to pick the best polynomial order and problems that arise when selecting the wrong order polynomial。

 Consider the following function。 We assume the training points come from a polynomial function。

 plus some noise。

![](img/69a4ee37331dfc3a875e2e141b15be66_1.png)

The goal of model selection is to determine the order of the polynomial to provide the best estimate of the function。

 Y X。

![](img/69a4ee37331dfc3a875e2e141b15be66_3.png)

If we try and fit the function with a linear function。

 the line is not complex enough to fit the data。As a result， there are many errors。

 This is called underfitting， where the model is too simple to fit the data。

 If we increase the order of the polynomial， the model fits better。

 but the model is still not flexible enough and exhibits underfitting。

 This is an example of the eighth order polynomial used to fit the data。

We see the model does well at fitting the data and estimating the function。

 even at the inflection points。Increasing it to a 16th order polynomial。

 the model does extremely well at tracking the training point。

But performs poorly at estimating the function。 This is especially apparent where there is little training data。

 The estimated function oscillates not tracking the function。 This is called overfitting。

 where the model is too flexible and fits the noise rather than the function。

 Let's look at a plot of the mean square error for the training and testing set of different order of polynomials。

 The horizontal axis represents the order of the polynomial。

 The vertical axis is the mean square error。 The training error decreases with the order of the polynomial。



![](img/69a4ee37331dfc3a875e2e141b15be66_5.png)

The test error is a better means of estimating the error of a polynomial。

 The error decreases till the best order of the polynomial is determined。

 Then the error begins to increase。 We select the order that minimizes the test error。 In this case。

 it was 8。 Anything on the left would be considered underfitting。

 Anything on the right is overfitting。If we select the best order of the polynomial。

 we will still have some errors。 if you recall the original expression for the training points。

We see a noise term。 This term is one reason for the error。 This is because the noise is random。

 and we can't predict it。 This is sometimes referred to as an irreducible error。

 There are other sources of errors， as well。For example， our polynomial assumption may be wrong。

 Our sample points may have come from a different function。 For example， in this plot。

 the data is generated from a sine wave。 The polynomial function does not do a good job at fitting the sine wave。



![](img/69a4ee37331dfc3a875e2e141b15be66_7.png)

For real data， the model may be too difficult to fit。

 or we may not have the correct type of data to estimate the function。



![](img/69a4ee37331dfc3a875e2e141b15be66_9.png)

Let's try different order polynomials on the real data using horsepower。

The red points represent the training data， the green points represent the test data。

If we just use the mean of the data， our model does not perform well。

A linear function does fit the data better。A second order model looks similar to the linear function。

A third order function also appears to increase， like the previous two orders。

 Here we see a fourth order polynomial At around 200 horsepower。

 The predicted price suddenly decreases。 This seems erroneous。😊。

Let's use R squared to see if our assumption is correct。



![](img/69a4ee37331dfc3a875e2e141b15be66_11.png)

The following is a plot of the R squared value。 The horizontal axis represents the order of polynomial models。

 The closer the R squared is to one， the more accurate the model is。

Here we see the r squared is optimal when the order of the polynomial is 3。

The r squared drastically decreases when the order is increased to 4。

 validating our initial assumption。

![](img/69a4ee37331dfc3a875e2e141b15be66_13.png)

We can calculate different R squared values as follows。 First。

 we create an empty list to store the values。 We create a list containing different polynomial orders。

 We then iterate through the list using a loop。 We create a polynomial feature object with the order of the polynomial as a parameter。

 We transform the training and test data into a polynomial using the fit transform method。😊。

We fit the regression model using the transform data。

 We then calculate the R squared using the test data and store it in the array。



![](img/69a4ee37331dfc3a875e2e141b15be66_15.png)