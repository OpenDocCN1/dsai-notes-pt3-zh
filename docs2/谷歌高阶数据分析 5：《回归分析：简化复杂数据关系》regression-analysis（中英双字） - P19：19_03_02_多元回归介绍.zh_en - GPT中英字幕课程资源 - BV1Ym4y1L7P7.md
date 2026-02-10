# 谷歌高阶数据分析 5：《回归分析：简化复杂数据关系》regression-analysis（中英双字） - P19：19_03_02_多元回归介绍.zh_en - GPT中英字幕课程资源 - BV1Ym4y1L7P7

![](img/e695fcd10196a48e19c68f301b39a8e4_0.png)

Previously， we learned about simple， linear regression。 For example。

 the more advertisements a company uses， the more clicks their website receives。

 This is an example of a relationship between variables that can be modeled with simple linear regression。

 because there is only one x variable and one y variable。

 The number of website clicks is a continuous， dependent variable。😊。

The number of advertisements is the independent variable。

But the company might be interested in exploring the characteristics of each advertisement to determine what kinds of advertisements are related to more website clicks。

Perhaps shorter advertisements are correlated with more clicks。

 or maybe advertisements containing a call to action such as donate or subscribescribe are associated with more clicks。

Multiple linear regression can help us answer these kinds of questions。Multiple linear regression。

 also known as multiple regression， is a technique that estimates the linear relationship between one continuous dependent variable and two or more independent variables。

Let's reexamine the equation for a simple linear regression。 y equals beta 0 plus beta 1 times x。

Recall that beta 0 also called the y intercept and that beta 1 is also called the slope。

Let's say that Y represents the website clicks and X represents the number of people that are in the advertisement。

Now let's add in the length of the advertisement into the equation。

 y equals beta 0 plus beta 1 times x1 plus beta 2 times x2。

The X 1 represents the number of people that are in the advertisement。

 and X 2 represents the length of the advertisement。 Note that because we have two X variables now。

 we've added subscripts to differentiate between them。

You'll encounter this notation often in multivariate analysis。

Multiple regression allows us at a basic level to add any number of independent variables that we're considering。

 so a full multiple regression equation might be y equals beta 0 plus beta 1 times x1 plus beta 2 times x2 plus as many variables you have up to beta n times xn where you're interested in n independent variables。

Even though we are just adding more beta coefficients and independent variables。

 we can still reap the benefits of linear regression， just like simple linear regression。

 multiple linear regression can yield highly interpretable and communicable results。

 but because the underlying math is a bit more complex。

 we have to be mindful of how we convey our results and what the coefficients mean。

To ensure we're ethically communicating our results as clearly as possible。

 we'll go over two concepts， one hot encoding and interaction terms。



![](img/e695fcd10196a48e19c68f301b39a8e4_2.png)

One highnd codinging allows us to use categorical independent variables in our multiple linear regression for example。

 we might have print advertisements and digital advertisements。This is a categorical variable。

 and one hot encoding will allow us to incorporate it into our regression model。

 If we want to account for how two independent variables affect the Y variable together。

 we can use something called an interaction term。😊。

Both of these topics are important because they will change how we interpret the coefficients of our model。

 we will learn how to do this together in the upcoming videos。



![](img/e695fcd10196a48e19c68f301b39a8e4_4.png)