# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P91：2_逻辑回归简介.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Let's start off with our first classification algorithm， logistic regression。So in this section。

 our learning goals will be to introduce logistic regression as a classification algorithm。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_1.png)

Discuss linear regressiong as an example for classification and how it can actually be used versus how logistic regression helps correct what linear regression may get wrong when we trying to do classification。

 as well as touching on the relationship between the two。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_3.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_4.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_5.png)

And then we'll show how we can use logistic regression for an example in order to actually perform classification。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_7.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_8.png)

So we're going to start our discussion on logistic regression with an example here we are reintroducing the customer churn example from telecom。

 where customer churn is a function of the amount of usage in minutes here。

 So here there's going to be one feature， the usage in minutes and a binary outcome。

 either they churned or they did not churn。

![](img/bab4c29f2bbfadd5744f084c789ed6a1_10.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_11.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_12.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_13.png)

Later， we'll add another feature， data usage and another outcome canceled versus went to a competitor。

 but we'll save that for a bit later on。

![](img/bab4c29f2bbfadd5744f084c789ed6a1_15.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_16.png)

We can treat a binary classification problem as a actual regression problem as follows。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_18.png)

First we encode the classes one and zero， where one is going to be those top values， zero。

 those bottom values， and then we can fit a line that best fit， we can fit a regression algorithm。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_20.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_21.png)

When a new unlabeled record comes in and we want to guess the value using the Russian algorithm。

 we pass in those values into our algorithm with our predicted coefficients。

 and if that value is greater than 0。5 then we predict one， that they did churn， if it's less than 0。

5 then we predict 0 that they did not churn。

![](img/bab4c29f2bbfadd5744f084c789ed6a1_23.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_24.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_25.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_26.png)

But what if our data looks like this， and when I say like this compared to before。

 notice that the OLS line is now heavily slanted much more so than before。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_28.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_29.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_30.png)

And when we look at our 0。5 cutoff and where it lands on that line。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_32.png)

We see that the threshold is now further to the right。 Y equals 0。5 is further to the right。

 And we know that if our model is greater than 0。5， we predict churn。 If the model is less than 0。5。

 we predict that they did not churn。

![](img/bab4c29f2bbfadd5744f084c789ed6a1_34.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_35.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_36.png)

So we are predicting here because of the being skewed off to the right， false outcomes。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_38.png)

And a very simple example where the boundary between zero and1 is visually obvious。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_40.png)

So as we see at the leftmost values on the top that were predicted as zero when they should have been one。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_42.png)

This is being skewed because of the regression algorithm trying to fit， given that 0。5 threshold。



![](img/bab4c29f2bbfadd5744f084c789ed6a1_44.png)

So we need a way to weight the samples that are far away much lower than the ones that are closer to our threshold in our objective function。

 and this is where the famous logistic function comes into play。

 which we'll discuss in our next video。

![](img/bab4c29f2bbfadd5744f084c789ed6a1_46.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_47.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_48.png)

![](img/bab4c29f2bbfadd5744f084c789ed6a1_49.png)