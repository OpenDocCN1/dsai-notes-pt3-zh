# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P46：45_岭回归.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we'll discuss Rige regression。

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_1.png)

Rich regression prevents overfitting。

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_3.png)

In this video， we will focus on polynomial regression for visualization。

 but overfitting is also a big problem when you have multiple independent variables or features。

 Consider the following fourth order。 polynomial in orange。

 The blue points are generated from this function。

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_5.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_6.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_7.png)

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

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_9.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_10.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_11.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_12.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_13.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_14.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_15.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_16.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_17.png)

Alpha is a parameter we select before fitting or training the model。

 Each row in the following table represents an increasing value of alpha。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_19.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_20.png)

Let's see how different values of alpha change the model。

 This table represents the polynomial coefficients for different values of alpha。

 The column corresponds to the different polynomial coefficients。

 and the rows correspond to the different values of alpha。

 As alpha increases the parameters get smaller。 This is most evident for the higher order。

 polynomial features， but alpha must be selected carefully。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_22.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_23.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_24.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_25.png)

If alpha is too large， the coefficients will approach 0 and underfi the data。 If alpha is 0。

 the overfitting is evident for alpha equal to 0。001。 the overfitting begins to subside。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_27.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_28.png)

For alpha equal to 0。01， the estimated function tracks the actual function。 When alpha equals 1。

 we see the first signs of underfitting。

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_30.png)

The estimated function does not have enough flexibility At alpha equals to 10。

 We see extreme underfitting。 It does not even track the two points。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_32.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_33.png)

In order to select alpha， we use cross validation to make a prediction using ridge regression。

 Im ridge from S。 K， learn linear models。 createate a ridge object using the constructor。

 The parameter alpha is one of the arguments of the constructor。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_35.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_36.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_37.png)

We train the model， using the fit method。To make a prediction。

 we use the prediction method in order to determine the parameter alpha。

 we use some data for training。 We use a second set called validation data。

 This is similar to test data。 but it is used to select parameters like alpha。

 We start with a small value of alpha。 We train the model。

 make a prediction using the validation data。 Then calculate the R squared and store the values。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_39.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_40.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_41.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_42.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_43.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_44.png)

Repeat the value for a larger value of alpha。We train the model again。

 make a prediction using the validation data， then calculate the R squared and store the values of R squared。

 We repeat the process for a different alpha value， training the model and making a prediction。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_46.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_47.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_48.png)

We select the value of alpha that maximizes the r squared。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_50.png)

Note that we can use other metrics to select the value of alpha like mean squared error。

 The overfitting problem is even worse if we have lots of features。

 The following plot shows the different values of R squared on the vertical axis。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_52.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_53.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_54.png)

The horizontal axis represents different values for alpha。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_56.png)

We use several features from our used car data set and a second order polynomial function。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_58.png)

The training data is in red， and validation data is in blue。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_60.png)

We see as the value for alpha increases， the value of r squared increases and converges at approximately 0。

75。

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_62.png)

In this case， we select the maximum value of alpha because running the experiment for higher values of alpha have little impact。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_64.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_65.png)

Conversely， as alpha increases， the R squared on the test data decreases。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_67.png)

This is because the term alpha prevents overfitting。



![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_69.png)

This may improve the results in the unseen data， but the model has worse performance on the test data。

 See the lab on how to generate this plot。

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_71.png)

![](img/7a1700e9f3f6f5ef9d3aa77f2eb281be_72.png)