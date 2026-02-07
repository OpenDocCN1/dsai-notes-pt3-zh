# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P32：31_线性回归与多元线性回归.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we'll be talking about simple linear regression and multiple linear regression。



![](img/3494ad23be9f9b291ff2846dfc538aa2_1.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_2.png)

Linear regression will refer to one independent variable to make a prediction。

 Multi linear regression will refer to multiple independent variables to make a prediction。



![](img/3494ad23be9f9b291ff2846dfc538aa2_4.png)

Simple linear regression or S， L R is a method to help us understand the relationship between two variables。

 The predictor， independent variable X and the target， dependent variable Y。

 We would like to come up with a linear relationship between the variables shown here。



![](img/3494ad23be9f9b291ff2846dfc538aa2_6.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_7.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_8.png)

The parameter B0 is the intercept。

![](img/3494ad23be9f9b291ff2846dfc538aa2_10.png)

The parameter B1 is the slope。When we fit or train the model， we will come up with these parameters。

This step requires lots of math， so we will not focus on this part。

 Let's clarify the prediction step。

![](img/3494ad23be9f9b291ff2846dfc538aa2_12.png)

It's hard to figure out how much a car costs， But the highway miles per gallon is in the owner's manual。



![](img/3494ad23be9f9b291ff2846dfc538aa2_14.png)

If we assume there is a linear relationship between these variables。



![](img/3494ad23be9f9b291ff2846dfc538aa2_16.png)

We can use this relationship to formulate a model to determine the price of the car。



![](img/3494ad23be9f9b291ff2846dfc538aa2_18.png)

If the highway miles per gallon is 20， we can input this value into the model。



![](img/3494ad23be9f9b291ff2846dfc538aa2_20.png)

To obtain a prediction of $22000。

![](img/3494ad23be9f9b291ff2846dfc538aa2_22.png)

In order to determine the line， we take data points from our data set marked in red here。



![](img/3494ad23be9f9b291ff2846dfc538aa2_24.png)

We then use these training points to fit our model。



![](img/3494ad23be9f9b291ff2846dfc538aa2_26.png)

The results of the trading points are the parameters。



![](img/3494ad23be9f9b291ff2846dfc538aa2_28.png)

We usually store the data points in two data frame， or nupy arrays。



![](img/3494ad23be9f9b291ff2846dfc538aa2_30.png)

The value we would like to predict is called the target that we store in the array Y。

 We store the independent variable in the data frame， or array X。



![](img/3494ad23be9f9b291ff2846dfc538aa2_32.png)

Each sample corresponds to a different row in each data frame， or array。



![](img/3494ad23be9f9b291ff2846dfc538aa2_34.png)

In many cases， many factors influence how much people pay for a car。



![](img/3494ad23be9f9b291ff2846dfc538aa2_36.png)

For example， make or how old the car is in this model。

 This uncertainty is taken into account by assuming a small random value is added to the point on the line。



![](img/3494ad23be9f9b291ff2846dfc538aa2_38.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_39.png)

This is called noise。

![](img/3494ad23be9f9b291ff2846dfc538aa2_41.png)

The figure on the left shows the distribution of the noise。 The vertical axis shows the value added。

 and the horizontal axis illustrates the probability that the value will be added。



![](img/3494ad23be9f9b291ff2846dfc538aa2_43.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_44.png)

Usually， a small， positive value is added。

![](img/3494ad23be9f9b291ff2846dfc538aa2_46.png)

Or small， negative value。Sometimes， large values are added。



![](img/3494ad23be9f9b291ff2846dfc538aa2_48.png)

But for the most part， the values added are near 0。



![](img/3494ad23be9f9b291ff2846dfc538aa2_50.png)

We can summarize the process like this。 We have a set of training points。

 We use these trading points to fit or train the model， and get parameters。



![](img/3494ad23be9f9b291ff2846dfc538aa2_52.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_53.png)

We then use these parameters in the model。 We now have a model。



![](img/3494ad23be9f9b291ff2846dfc538aa2_55.png)

We use the hat on the Y to denote the model is an estimate。



![](img/3494ad23be9f9b291ff2846dfc538aa2_57.png)

We can use this model to predict values that we haven't seen。



![](img/3494ad23be9f9b291ff2846dfc538aa2_59.png)

For example， we have no car with 20 highway miles per gallon。

We can use our model to make a prediction for the price of this car。 But don't forget。

 Our model is not always correct。

![](img/3494ad23be9f9b291ff2846dfc538aa2_61.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_62.png)

We can see this by comparing the predicted value to the actual value。



![](img/3494ad23be9f9b291ff2846dfc538aa2_64.png)

We have a sample for 10 highway miles per gallon。But the predicted value does not match the actual value。



![](img/3494ad23be9f9b291ff2846dfc538aa2_66.png)

If the linear assumption is correct， this error is due to the noise， but there can be other reasons。



![](img/3494ad23be9f9b291ff2846dfc538aa2_68.png)

To fit the model in Python， first， we import linear model from Psi kit learn。



![](img/3494ad23be9f9b291ff2846dfc538aa2_70.png)

Then create a linear regression object using the constructor。We define the predictor variable。

 and target variable。Then use the method fit to fit the model and find the parameters B 0 and B 1。

The input are the features and the targets。 we can obtain a prediction using the method， predict。

The output is an array。 The array has the same number of samples as the input X。

The intercept B 0 is an attribute of the object， L M。



![](img/3494ad23be9f9b291ff2846dfc538aa2_72.png)

The slope B1 is also an attribute of the object L M。



![](img/3494ad23be9f9b291ff2846dfc538aa2_74.png)

The relationship between price and highway miles per gallon is given by this equation in bold。

Price equals 38423 point 31-821。 73 times highway miles per gallon。

Like the equation we discussed before。Multiple linear regression is used to explain the relationship between one continuous target Y variable and two or more predictor x variables。



![](img/3494ad23be9f9b291ff2846dfc538aa2_76.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_77.png)

If we have， for example， four predictor variables， then B 0 intercept X equals 0， B1。

 the coefficient or parameter of x 1。

![](img/3494ad23be9f9b291ff2846dfc538aa2_79.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_80.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_81.png)

B2， the coefficient of parameter X 2， and so on。

![](img/3494ad23be9f9b291ff2846dfc538aa2_83.png)

If there are only two variables， then we can visualize the values。 Consider the following function。

 The variables， X 1 and X 2 can be visualized on a2 D plane。 Let's do an example， on the next slide。



![](img/3494ad23be9f9b291ff2846dfc538aa2_85.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_86.png)

The table contains different values of the predictor variables， X 1 and X 2。

 The position of each point is placed on the 2 D plane， color coatd accordingly。



![](img/3494ad23be9f9b291ff2846dfc538aa2_88.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_89.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_90.png)

Each value of the predictor variables， x1 and x2 will be mapped to a new value Y Y hat。



![](img/3494ad23be9f9b291ff2846dfc538aa2_92.png)

The new values of why Y hat are mapped in the vertical direction with height proportional to the value that Y hat takes。



![](img/3494ad23be9f9b291ff2846dfc538aa2_94.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_95.png)

We can fit the multiple linear regression as follows。

 We can extract the four predictor variables and store them in the variable Z。



![](img/3494ad23be9f9b291ff2846dfc538aa2_97.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_98.png)

Then train the model as before， using the method train with the features or dependent variables and the targets。

 Col it。We can also obtain a prediction using the method predict。In this case。

 the input is an array or data frame with four columns。

 The number of rows corresponds to the number of samples。

The output is an array with the same number of elements as number of samples。

The intercept is an attribute of the object， and the coefficients are also attributes。

 It is helpful to visualize the equation， replacing the dependent variable names with actual names。

 This is identical to the form we discussed earlier。



![](img/3494ad23be9f9b291ff2846dfc538aa2_100.png)

![](img/3494ad23be9f9b291ff2846dfc538aa2_101.png)