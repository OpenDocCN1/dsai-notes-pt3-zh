# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P43：42_过拟合-欠拟合与模型选择.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/5910c641c09d78da8a2ee9dab80de3bf_0.png)

If you recall， in the last module， we discuss polynomial regression。



![](img/5910c641c09d78da8a2ee9dab80de3bf_2.png)

In this section， we will discuss how to pick the best polynomial order and problems that arise when selecting the wrong order polynomial。

 Consider the following function。 We assume the training points come from a polynomial function。

 plus some noise。

![](img/5910c641c09d78da8a2ee9dab80de3bf_4.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_5.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_6.png)

The goal of model selection is to determine the order of the polynomial to provide the best estimate of the function Y X。



![](img/5910c641c09d78da8a2ee9dab80de3bf_8.png)

If we try and fit the function with a linear function。

 the line is not complex enough to fit the data。

![](img/5910c641c09d78da8a2ee9dab80de3bf_10.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_11.png)

As a result， there are many errors。 This is called underfitting where the model is too simple to fit the data。

 If we increase the order of the polynomial， the model fits better。

 but the model is still not flexible enough and exhibits underfitting。

 This is an example of the eighth order polynomial used to fit the data。

 We see the model does well at fitting the data and estimating the function。

 Even at the inflection points。

![](img/5910c641c09d78da8a2ee9dab80de3bf_13.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_14.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_15.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_16.png)

Increasing it to a 16th order polynomial， the model does extremely well at tracking the training point。



![](img/5910c641c09d78da8a2ee9dab80de3bf_18.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_19.png)

But performs poorly at estimating the function。 This is especially apparent where there is little training data。

 The estimated function oscillates not tracking the function。 This is called overfitting。

 where the model is too flexible and fits the noise， rather than the function。

 Let's look at a plot of the mean square error for the training and testing set of different order polynomials。

 The horizontal axis represents the order of the polynomial。

 The vertical axis is the mean square error。 The training error decreases with the order of the polynomial。



![](img/5910c641c09d78da8a2ee9dab80de3bf_21.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_22.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_23.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_24.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_25.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_26.png)

The test error is a better means of estimating the error of a polynomial。

 The error decreases till the best order of the polynomial is determined。

 Then the error begins to increase。 We select the order that minimizes the test error。 In this case。

 it was 8。 Anything on the left would be considered underfitting。

 Anything on the right is overfitting。

![](img/5910c641c09d78da8a2ee9dab80de3bf_28.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_29.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_30.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_31.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_32.png)

If we select the best order of the polynomial， we will still have some errors。

 if you recall the original expression for the training points。



![](img/5910c641c09d78da8a2ee9dab80de3bf_34.png)

We see a noise term。 This term is one reason for the error。 This is because the noise is random。

 and we can't predict it。 This is sometimes referred to as an irreducible error。

 There are other sources of errors， as well。

![](img/5910c641c09d78da8a2ee9dab80de3bf_36.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_37.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_38.png)

For example， our polynomial assumption may be wrong。

 Our sample points may have come from a different function。 For example， in this plot。

 the data is generated from a sine wave。 The polynomial function does not do a good job at fitting the sine wave。



![](img/5910c641c09d78da8a2ee9dab80de3bf_40.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_41.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_42.png)

For real data， the model may be too difficult to fit。

 or we may not have the correct type of data to estimate the function。



![](img/5910c641c09d78da8a2ee9dab80de3bf_44.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_45.png)

Let's try different order polynomials on the real data using horsepower。

The red points represent the training data， the green points represent the test data。



![](img/5910c641c09d78da8a2ee9dab80de3bf_47.png)

If we just use the mean of the data， our model does not perform well。



![](img/5910c641c09d78da8a2ee9dab80de3bf_49.png)

A linear function does fit the data better。

![](img/5910c641c09d78da8a2ee9dab80de3bf_51.png)

A second order model looks similar to the linear function。



![](img/5910c641c09d78da8a2ee9dab80de3bf_53.png)

A third order function also appears to increase， like the previous two orders。

 Here we see a fourth order polynomial At around 200 horsepower。

 The predicted price suddenly decreases。 This seems erroneous。



![](img/5910c641c09d78da8a2ee9dab80de3bf_55.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_56.png)

Let's use R squared to see if our assumption is correct。



![](img/5910c641c09d78da8a2ee9dab80de3bf_58.png)

The following is a plot of the R squared value。 The horizontal axis represents the order of polynomial models。

 The closer the R squared is to one， the more accurate the model is。



![](img/5910c641c09d78da8a2ee9dab80de3bf_60.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_61.png)

Here we see the R squared is optimal when the order of the polynomial is 3。



![](img/5910c641c09d78da8a2ee9dab80de3bf_63.png)

The r squared drastically decreases when the order is increased to4。

 validating our initial assumption。

![](img/5910c641c09d78da8a2ee9dab80de3bf_65.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_66.png)

We can calculate different R squared values as follows。 First。

 we create an empty list to store the values。 We create a list containing different polynomial orders。

 We then iterate through the list using a loop。 We create a polynomial feature object with the order of the polynomial as a parameter。

 We transform the training and test data into a polynomial using the fit transform method。😊。



![](img/5910c641c09d78da8a2ee9dab80de3bf_68.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_69.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_70.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_71.png)

![](img/5910c641c09d78da8a2ee9dab80de3bf_72.png)

We fit the regression model using the transform data。

 We then calculate the R squared using the test data and store it in the array。



![](img/5910c641c09d78da8a2ee9dab80de3bf_74.png)