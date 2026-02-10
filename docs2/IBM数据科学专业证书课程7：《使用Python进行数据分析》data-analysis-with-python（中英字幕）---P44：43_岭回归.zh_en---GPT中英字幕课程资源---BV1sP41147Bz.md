# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P44：43_岭回归.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we'll discuss Rige regression。

![](img/a6cca4a4f94af482258155d69ecb4057_1.png)

Rich regression prevents overfitting。

![](img/a6cca4a4f94af482258155d69ecb4057_3.png)

In this video， we will focus on polynomial regression for visualization。

 but overfitting is also a big problem when you have multiple independent variables or features。

 Consider the following fourth order。 polynomial in orange。

 The blue points are generated from this function。

![](img/a6cca4a4f94af482258155d69ecb4057_5.png)

![](img/a6cca4a4f94af482258155d69ecb4057_6.png)

![](img/a6cca4a4f94af482258155d69ecb4057_7.png)

We can use a 10th order polynomial to fit the data。

 The estimated function in blue does a good job at approximating the true function。 In many cases。

 real data has outliers。 For example， this point shown here does not appear to come from the function in orange。

 If we use a 10th order polynomial function to fit the data。

 The estimated function in blue is incorrect。 and is not a good estimate of the actual function in orange。

 If we examine the expression for the estimated function。

 we see the estimated polynomial coefficients have a very large magnitude。

 This is especially evident for the higher order。 Ponomials。

 Ri regression controls the magnitude of these polynomial coefficients。

 By introducing the parameter alpha。😊。

![](img/a6cca4a4f94af482258155d69ecb4057_9.png)

![](img/a6cca4a4f94af482258155d69ecb4057_10.png)

![](img/a6cca4a4f94af482258155d69ecb4057_11.png)

![](img/a6cca4a4f94af482258155d69ecb4057_12.png)

![](img/a6cca4a4f94af482258155d69ecb4057_13.png)

![](img/a6cca4a4f94af482258155d69ecb4057_14.png)

![](img/a6cca4a4f94af482258155d69ecb4057_15.png)

![](img/a6cca4a4f94af482258155d69ecb4057_16.png)

![](img/a6cca4a4f94af482258155d69ecb4057_17.png)

Alpha is a parameter we select before fitting or training the model。

 Each row in the following table represents an increasing value of alpha。



![](img/a6cca4a4f94af482258155d69ecb4057_19.png)

![](img/a6cca4a4f94af482258155d69ecb4057_20.png)

Let's see how different values of alpha change the model。

 This table represents the polynomial coefficients for different values of alpha。

 The column corresponds to the different polynomial coefficients。

 and the rows correspond to the different values of alpha。

 As alpha increases the parameters get smaller。 This is most evident for the higher order。

 polynomial features， but alpha must be selected carefully。



![](img/a6cca4a4f94af482258155d69ecb4057_22.png)

![](img/a6cca4a4f94af482258155d69ecb4057_23.png)

![](img/a6cca4a4f94af482258155d69ecb4057_24.png)

![](img/a6cca4a4f94af482258155d69ecb4057_25.png)

If alpha is too large， the coefficients will approach 0 and underfi the data。 If alpha is 0。

 the overfitting is evident for alpha equal to 0。001。 the overfitting begins to subside。



![](img/a6cca4a4f94af482258155d69ecb4057_27.png)

![](img/a6cca4a4f94af482258155d69ecb4057_28.png)

For alpha equal to 0。01， the estimated function tracks the actual function。 When alpha equals 1。

 we see the first signs of underfitting。

![](img/a6cca4a4f94af482258155d69ecb4057_30.png)

The estimated function does not have enough flexibility At alpha equals to 10。

 We see extreme underfitting。 It does not even track the two points。



![](img/a6cca4a4f94af482258155d69ecb4057_32.png)

![](img/a6cca4a4f94af482258155d69ecb4057_33.png)

In order to select alpha， we use cross validation to make a prediction using ridge regression。

 Im ridge from S。 K， learn linear models。 createate a ridge object using the constructor。

 The parameter alpha is one of the arguments of the constructor。



![](img/a6cca4a4f94af482258155d69ecb4057_35.png)

![](img/a6cca4a4f94af482258155d69ecb4057_36.png)

![](img/a6cca4a4f94af482258155d69ecb4057_37.png)

We train the model， using the fit method。To make a prediction。

 we use the prediction method in order to determine the parameter alpha。

 we use some data for training。 We use a second set called validation data。

 This is similar to test data。 but it is used to select parameters like alpha。

 We start with a small value of alpha。 We train the model。

 make a prediction using the validation data。 Then calculate the R squared and store the values。



![](img/a6cca4a4f94af482258155d69ecb4057_39.png)

![](img/a6cca4a4f94af482258155d69ecb4057_40.png)

![](img/a6cca4a4f94af482258155d69ecb4057_41.png)

![](img/a6cca4a4f94af482258155d69ecb4057_42.png)

![](img/a6cca4a4f94af482258155d69ecb4057_43.png)

![](img/a6cca4a4f94af482258155d69ecb4057_44.png)

Repeat the value for a larger value of alpha。We train the model again。

 make a prediction using the validation data， then calculate the R squared and store the values of R squared。

 We repeat the process for a different alpha value， training the model and making a prediction。



![](img/a6cca4a4f94af482258155d69ecb4057_46.png)

![](img/a6cca4a4f94af482258155d69ecb4057_47.png)

![](img/a6cca4a4f94af482258155d69ecb4057_48.png)

We select the value of alpha that maximizes the r squared。



![](img/a6cca4a4f94af482258155d69ecb4057_50.png)

Note that we can use other metrics to select the value of alpha like mean squared error。

 The overfitting problem is even worse if we have lots of features。

 The following plot shows the different values of R squared on the vertical axis。



![](img/a6cca4a4f94af482258155d69ecb4057_52.png)

![](img/a6cca4a4f94af482258155d69ecb4057_53.png)

![](img/a6cca4a4f94af482258155d69ecb4057_54.png)

The horizontal axis represents different values for alpha。



![](img/a6cca4a4f94af482258155d69ecb4057_56.png)

We use several features from our used car data set and a second order polynomial function。



![](img/a6cca4a4f94af482258155d69ecb4057_58.png)

The training data is in red， and validation data is in blue。



![](img/a6cca4a4f94af482258155d69ecb4057_60.png)

We see as the value for alpha increases， the value of r squared increases and converges at approximately 0。

75。

![](img/a6cca4a4f94af482258155d69ecb4057_62.png)

In this case， we select the maximum value of alpha because running the experiment for higher values of alpha have little impact。



![](img/a6cca4a4f94af482258155d69ecb4057_64.png)

![](img/a6cca4a4f94af482258155d69ecb4057_65.png)

Conversely， as alpha increases， the R squared on the test data decreases。



![](img/a6cca4a4f94af482258155d69ecb4057_67.png)

This is because the term alpha prevents overfitting。



![](img/a6cca4a4f94af482258155d69ecb4057_69.png)

This may improve the results in the unseen data， but the model has worse performance on the test data。

 See the lab on how to generate this plot。

![](img/a6cca4a4f94af482258155d69ecb4057_71.png)

![](img/a6cca4a4f94af482258155d69ecb4057_72.png)