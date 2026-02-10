# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P34：33_可视化模型评估.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/2e9361d7776557e801100cc692226f26_0.png)

In this video， we'll look at model evaluation using visualization。



![](img/2e9361d7776557e801100cc692226f26_2.png)

Regression plots are a good estimate of the relationship between two variables。

 the strength of the correlation and the direction of the relationship， positive or negative。



![](img/2e9361d7776557e801100cc692226f26_4.png)

![](img/2e9361d7776557e801100cc692226f26_5.png)

The horizontal axis is the independent variable。 The vertical axis is the dependent variable。



![](img/2e9361d7776557e801100cc692226f26_7.png)

Each point represents a different target point。

![](img/2e9361d7776557e801100cc692226f26_9.png)

The fitted line represents the predicted value。

![](img/2e9361d7776557e801100cc692226f26_11.png)

There are several ways to plot a regression plot。 A simple way is to use re plot from the Seabornourne Library。



![](img/2e9361d7776557e801100cc692226f26_13.png)

First， import seaborn， then use the reddge plot function。

 The parameter X is the name of the column that contains the independent variable or feature。



![](img/2e9361d7776557e801100cc692226f26_15.png)

![](img/2e9361d7776557e801100cc692226f26_16.png)

The parameter Y contains the name of the column that contains the name of the dependent variable or target。

 The parameter data is the name of the data frame。 The result is given by the plot。



![](img/2e9361d7776557e801100cc692226f26_18.png)

![](img/2e9361d7776557e801100cc692226f26_19.png)

![](img/2e9361d7776557e801100cc692226f26_20.png)

The residual plot represents the error between the actual value。



![](img/2e9361d7776557e801100cc692226f26_22.png)

Examining the predicted value and actual value， we see a difference。

 We obtained that value by subtracting the predicted value and the actual target value。



![](img/2e9361d7776557e801100cc692226f26_24.png)

![](img/2e9361d7776557e801100cc692226f26_25.png)

We then plot that value on the vertical axis with an independent variable as the horizontal axis。

 Similarly， for the second sample， we repeat the process。



![](img/2e9361d7776557e801100cc692226f26_27.png)

![](img/2e9361d7776557e801100cc692226f26_28.png)

Subtracting the target value from the predicted value。



![](img/2e9361d7776557e801100cc692226f26_30.png)

Then， plotting the value accordingly。Looking at the plot gives us some insight into our data。

 We expect to see the results to have 0 mean distributed evenly around the X axis with similar variances。

 There is no curvature。

![](img/2e9361d7776557e801100cc692226f26_32.png)

![](img/2e9361d7776557e801100cc692226f26_33.png)

![](img/2e9361d7776557e801100cc692226f26_34.png)

This type of residual plot suggests a linear plot is appropriate。In this residual plot。

 there is a curvature。

![](img/2e9361d7776557e801100cc692226f26_36.png)

The values of the error change with X。 For example， in the region。

 all the residual errors are positive。

![](img/2e9361d7776557e801100cc692226f26_38.png)

![](img/2e9361d7776557e801100cc692226f26_39.png)

In this area， the residuals are negative。In the final location， the error is large。



![](img/2e9361d7776557e801100cc692226f26_41.png)

The residuals are not randomly separated。This suggests the linear assumption is incorrect。



![](img/2e9361d7776557e801100cc692226f26_43.png)

This plot suggests a non linear function。 We will deal with this in the next section。



![](img/2e9361d7776557e801100cc692226f26_45.png)

In this plot， we see that variance of the residuals increases with X。 Therefore。

 our model is incorrect。

![](img/2e9361d7776557e801100cc692226f26_47.png)

![](img/2e9361d7776557e801100cc692226f26_48.png)

We can use seaborn to create a residual plot。 First， import seabornne。



![](img/2e9361d7776557e801100cc692226f26_50.png)

We use the resid plot function。

![](img/2e9361d7776557e801100cc692226f26_52.png)

The first parameter is a series of dependent variable or feature。

The second parameter is a series of dependent variable， or target。



![](img/2e9361d7776557e801100cc692226f26_54.png)

We see， in this case， the residuals have a curvature。



![](img/2e9361d7776557e801100cc692226f26_56.png)

A distribution plot counts the predicted value versus the actual value。

 These plots are extremely useful for visualizing models with more than one independent variable or feature。



![](img/2e9361d7776557e801100cc692226f26_58.png)

![](img/2e9361d7776557e801100cc692226f26_59.png)

Let's look at a simplified example。

![](img/2e9361d7776557e801100cc692226f26_61.png)

We examine the vertical axis。 We then count and plot the number of predicted points that are approximately equal to one。



![](img/2e9361d7776557e801100cc692226f26_63.png)

![](img/2e9361d7776557e801100cc692226f26_64.png)

We then count and plot the number of predicted points that are approximately equal to2。



![](img/2e9361d7776557e801100cc692226f26_66.png)

We repeat the process for predicted points that are approximately equal to 3。



![](img/2e9361d7776557e801100cc692226f26_68.png)

Then we repeat the process for the target values。 In this case。

 all the target values are approximately equal to 2。



![](img/2e9361d7776557e801100cc692226f26_70.png)

The values of the targets and predicted values are continuous。



![](img/2e9361d7776557e801100cc692226f26_72.png)

A histogram is for discrete values。

![](img/2e9361d7776557e801100cc692226f26_74.png)

Therefore， pandas。We'll convert them to a distribution。



![](img/2e9361d7776557e801100cc692226f26_76.png)

The vertical axis is scaled to make the area under the distribution equal to one。



![](img/2e9361d7776557e801100cc692226f26_78.png)

This is an example of using a distribution plot。 The dependent variable or feature is price。

 The fitted values that result from the model are in blue。 The actual values are in red。



![](img/2e9361d7776557e801100cc692226f26_80.png)

![](img/2e9361d7776557e801100cc692226f26_81.png)

We see the predicted values for prices in the range from 40000 to 50000， are inaccurate。



![](img/2e9361d7776557e801100cc692226f26_83.png)

The prices in the region from 10000 to 20000 are much closer to the target value。 In this example。

 we use multiple features or independent variables。 comparing it to the plot on the last slide。



![](img/2e9361d7776557e801100cc692226f26_85.png)

![](img/2e9361d7776557e801100cc692226f26_86.png)

![](img/2e9361d7776557e801100cc692226f26_87.png)

We see predicted values are much closer to the target values。



![](img/2e9361d7776557e801100cc692226f26_89.png)

Here is the code to create a distribution plot。

![](img/2e9361d7776557e801100cc692226f26_91.png)

The actual values are used as parameter。 We want a distribution instead of a histogram。

 so we want the hist parameter set to false。 The color is red。 The label is also included。



![](img/2e9361d7776557e801100cc692226f26_93.png)

![](img/2e9361d7776557e801100cc692226f26_94.png)

The predicted values are included for the second plot。

 The rest of the parameters are set accordingly。

![](img/2e9361d7776557e801100cc692226f26_96.png)