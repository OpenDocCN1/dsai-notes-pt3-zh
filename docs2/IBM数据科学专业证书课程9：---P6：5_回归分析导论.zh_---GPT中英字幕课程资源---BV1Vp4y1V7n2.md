# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P6：5_回归分析导论.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

Hello and welcome In this video， we'll be giving a brief introduction to regression。

 so let's get started。😊。

![](img/959017f0c40a4193ccad48d73973baf7_1.png)

Look at this data set， It's related to CO2 emissions from different cars。 It includes engine size。

 number of cylinders， fuel consumption， and CO2 emission from various automobile models。



![](img/959017f0c40a4193ccad48d73973baf7_3.png)

![](img/959017f0c40a4193ccad48d73973baf7_4.png)

![](img/959017f0c40a4193ccad48d73973baf7_5.png)

The question is， given this data set， can we predict the CO2 emission of a car using other fields such as engine size or cylinders？



![](img/959017f0c40a4193ccad48d73973baf7_7.png)

![](img/959017f0c40a4193ccad48d73973baf7_8.png)

Let's assume we have some historical data from different cars and assume that a car such as in row 9 has not been manufactured yet。

 but we're interested in estimating its approximate CO2 emission after production， Is it possible。



![](img/959017f0c40a4193ccad48d73973baf7_10.png)

![](img/959017f0c40a4193ccad48d73973baf7_11.png)

We can use regression methods to predict a continuous value such as CO2 emission using some other variables。



![](img/959017f0c40a4193ccad48d73973baf7_13.png)

![](img/959017f0c40a4193ccad48d73973baf7_14.png)

Indeed， regression is the process of predicting a continuous value。



![](img/959017f0c40a4193ccad48d73973baf7_16.png)

In regression， there are two types of variables， a dependent variable。

 and one or more independent variables。

![](img/959017f0c40a4193ccad48d73973baf7_18.png)

![](img/959017f0c40a4193ccad48d73973baf7_19.png)

The dependent variable can be seen as the state， target or final goal we study and try to predict。

 and the independent variables also known as explanatory variables can be seen as the causes of those states。



![](img/959017f0c40a4193ccad48d73973baf7_21.png)

That independent variables are shown conventionally by X。



![](img/959017f0c40a4193ccad48d73973baf7_23.png)

And the dependent variable is notated by y。A regression model relates Y or the dependent variable to a function of X。

 I。e， the independent variables。

![](img/959017f0c40a4193ccad48d73973baf7_25.png)

The key point in the regression is that our dependent value should be continuous and could not be a discrete value。



![](img/959017f0c40a4193ccad48d73973baf7_27.png)

However， the independent variable or variables can be measured on either a categorical or continuous measurement scale。



![](img/959017f0c40a4193ccad48d73973baf7_29.png)

So what we want to do here is to use the historical data of some cars using one or more of their features。

 and from that data， make a model。 We use regression to build such a regression estimation model。



![](img/959017f0c40a4193ccad48d73973baf7_31.png)

![](img/959017f0c40a4193ccad48d73973baf7_32.png)

![](img/959017f0c40a4193ccad48d73973baf7_33.png)

Then the model is used to predict the expected CO2 emission for a new or unknown car。



![](img/959017f0c40a4193ccad48d73973baf7_35.png)

![](img/959017f0c40a4193ccad48d73973baf7_36.png)

Basically， there are two types of regression models， simple regression and multiple regression。



![](img/959017f0c40a4193ccad48d73973baf7_38.png)

Simple regression is when one independent variable is used to estimate a dependent variable。

 It can be either linear or non nonlinear。 For example。

 predicting CO2 emission using the variable of engine size。



![](img/959017f0c40a4193ccad48d73973baf7_40.png)

![](img/959017f0c40a4193ccad48d73973baf7_41.png)

![](img/959017f0c40a4193ccad48d73973baf7_42.png)

Lineniarity of regression is based on the nature of relationship between independent and dependent variables。

 When more than one independent variable is present。

 the process is called multiple linear regression。 For example。

 predicting CO2 emission using engine size and the number of cylinders in any given car。 Again。

 depending on the relation between dependent and independent variables。

 it can be either linear or linear regression。

![](img/959017f0c40a4193ccad48d73973baf7_44.png)

![](img/959017f0c40a4193ccad48d73973baf7_45.png)

Let's examine some sample applications of regression。Essentially。

 we use regression when we want to estimate a continuous value。



![](img/959017f0c40a4193ccad48d73973baf7_47.png)

![](img/959017f0c40a4193ccad48d73973baf7_48.png)

For instance， one of the applications of regression analysis could be in the area of sales forecasting。



![](img/959017f0c40a4193ccad48d73973baf7_50.png)

You can try to predict a salesperson's total yearly sales from independent variables such as age。

 education， and years of experience。

![](img/959017f0c40a4193ccad48d73973baf7_52.png)

It can also be used in the field of psychology， for example。

 to determine individual satisfaction based on demographic and psychological factors。



![](img/959017f0c40a4193ccad48d73973baf7_54.png)

![](img/959017f0c40a4193ccad48d73973baf7_55.png)

We can use regression analysis to predict the price of a house in an area based on its size。

 number of bedrooms， and so on。

![](img/959017f0c40a4193ccad48d73973baf7_57.png)

![](img/959017f0c40a4193ccad48d73973baf7_58.png)

We can even use it to predict employment income for independent variables such as hours of work。

 education， occupation， sex， age， years of experience and so on。 Indeed。

 you can find many examples of the usefulness of regression analysis in these and many other fields or domains such as finance。

 health care， retail and more。😊。

![](img/959017f0c40a4193ccad48d73973baf7_60.png)

![](img/959017f0c40a4193ccad48d73973baf7_61.png)

![](img/959017f0c40a4193ccad48d73973baf7_62.png)

![](img/959017f0c40a4193ccad48d73973baf7_63.png)

![](img/959017f0c40a4193ccad48d73973baf7_64.png)

We have many regression algorithms。 Each of them has its own importance and a specific condition to which their application is best suited。

 And while we've covered just a few of them in this course。

 it gives you enough base knowledge for you to explore different regression techniques。

Thanks for watching。