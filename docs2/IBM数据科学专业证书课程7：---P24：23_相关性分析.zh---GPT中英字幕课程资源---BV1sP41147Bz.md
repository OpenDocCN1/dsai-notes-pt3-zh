# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P24：23_相关性分析.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we'll talk about the correlation between different variables。



![](img/b96e852d2c06cc44a3dc35befb917b7b_1.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_2.png)

Correlation is a statistical metric for measuring to what extent different variables are interdependent。



![](img/b96e852d2c06cc44a3dc35befb917b7b_4.png)

In other words， when we look at two variables over time， if one variable changes。

 how does this effect change in the other variable， For example。

 smoking is known to be correlated to lung cancer。 since you have a higher chance of getting lung cancer if you smoke。



![](img/b96e852d2c06cc44a3dc35befb917b7b_6.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_7.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_8.png)

In another example， there is a correlation between umbrella and rain variables where more precipitation means more people use umbrellas。

 Also， if it doesn't rain， people would not carry umbrellas。 Therefore。

 we can say that umbrellas and rain are interdependent and by definition， they are correlated。

 It is important to know that correlation doesn't imply causation。 In fact。

 we can say that umbrella and rain are correlated。 but we would not have enough information to say whether the umbrella caused the rain or the rain caused the umbrella。

 in data science， we usually deal more with correlation。



![](img/b96e852d2c06cc44a3dc35befb917b7b_10.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_11.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_12.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_13.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_14.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_15.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_16.png)

Let's look at the correlation between engine size and price。 This time。

 we'll visualize these two variables using a scatter plot and an added linear line called a regression line。

 which indicates the relationship between the two。

![](img/b96e852d2c06cc44a3dc35befb917b7b_18.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_19.png)

The main goal of this plot is to see whether the engine size has any impact on the price。

 In this example， you can see that the straight line through the data points is very steep。

 which shows that there is a positive， linear relationship between the two variables。

 with increase in values of engine size。 Val of price go up as well。

 and the slope of the line is positive， So there is a positive correlation between engine size and price。



![](img/b96e852d2c06cc44a3dc35befb917b7b_21.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_22.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_23.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_24.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_25.png)

We can use seaborn reddge plot to create the scatter plot。



![](img/b96e852d2c06cc44a3dc35befb917b7b_27.png)

As another example， Now， let's look at the relationship between highway miles per gallon to see its impact on the car price。

 As we can see in this plot， when highway miles per gallon value goes up。

 the value of price goes down。 Therefore， there is a negative linear relationship between highway miles per gallon and price。

 Although this relationship is negative， the slope of the line is steep。

 which means that the highway miles per gallon is still a good predictor of price。

 These two variables are said to have a negative correlation。



![](img/b96e852d2c06cc44a3dc35befb917b7b_29.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_30.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_31.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_32.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_33.png)

![](img/b96e852d2c06cc44a3dc35befb917b7b_34.png)

Finally， we have an example of a weak correlation。 For example。

 both low peak R PMM and high values of peak R PMM have low and high prices。 Therefore。

 we cannot use R PMM to predict the values。😊。

![](img/b96e852d2c06cc44a3dc35befb917b7b_36.png)