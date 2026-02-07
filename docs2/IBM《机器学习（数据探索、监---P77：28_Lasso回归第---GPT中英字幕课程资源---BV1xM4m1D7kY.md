# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P77：28_Lasso回归第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now we introduce another means of regularization for linear regression。

 namely Lasso regressionggression。

![](img/ed7e64690eefb790b2668445a24a42e7_1.png)

The only difference here between this and Ri regression will be how we penalize the cost function using our coefficients。

With Ridge or L2， we use the coefficient squared and with LaSsA。

 we'll be using the absolute value of each one of these coefficients。

What we have here is built off the different norms for vector length。



![](img/ed7e64690eefb790b2668445a24a42e7_3.png)

Or in other words， just two different ways of measuring the magnitude of each one of the coefficients。



![](img/ed7e64690eefb790b2668445a24a42e7_5.png)

So how can we compare and contrast Lasso and Ridge now Lasso is directly proportional to the absolute value of the coefficients rather than with whichdge where it's proportional to the square of the coefficients。

 so don't be ekewed by the outliers。

![](img/ed7e64690eefb790b2668445a24a42e7_7.png)

![](img/ed7e64690eefb790b2668445a24a42e7_8.png)

![](img/ed7e64690eefb790b2668445a24a42e7_9.png)

Now Laso stands for least absolute shrinkage and selection operator。

 essentially using that absolute value to penalize our coefficients。



![](img/ed7e64690eefb790b2668445a24a42e7_11.png)

![](img/ed7e64690eefb790b2668445a24a42e7_12.png)

Similar to Ridge， this will work by giving the user a means to reduce complexity。

 an increase in Lada again will raise that bias but lower our variance or lower our complexity。



![](img/ed7e64690eefb790b2668445a24a42e7_14.png)

![](img/ed7e64690eefb790b2668445a24a42e7_15.png)

![](img/ed7e64690eefb790b2668445a24a42e7_16.png)

And Lasso is more likely than rich to perform feature selection。

 in other words it is more likely to completely zero out certain coefficients and we'll see why geometrically in later video。



![](img/ed7e64690eefb790b2668445a24a42e7_18.png)

![](img/ed7e64690eefb790b2668445a24a42e7_19.png)

![](img/ed7e64690eefb790b2668445a24a42e7_20.png)

So a different regular term here is going to be that L1 norm instead of the L2。

Here we are taking the sum of the absolute values， the larger values are still going to be penalized。

 but again not as strongly before with Rige we squared the coefficients。

 so larger values had even more of a penalty in relation to the coefficients。

The fact of this is it's going to selectively shrink some coefficients compared to Ridge。

 which is more likely to shrink all the coefficients at once。As mentioned before。

 Lasso will therefore actually eliminate certain features and perform feature selection for you。

In practice， it's also worth noting that Lassso is slower to converge than Ridge due to the underlying optimization solution。

 so you want to take into account optimization timing or computation timing。

 which will be faster for Ridge， versus perhaps higher interpretability because once you remove certain features you can get a better idea of which features are actually important。



![](img/ed7e64690eefb790b2668445a24a42e7_22.png)

Now， looking back at the same polynomial regressions that we had looked at before， this time。

 trying to find that underlying function， not using polynomials， not using ridge。

 but rather using Laso。 we will end up being able to optimize our solution by coming up with the right lambda value。

 So a lambda that is too low， which we see all the way out here to the right where it's essentially 0。

 Then we are not regularizing enough， or not adding enough penalty to the absolute value of each one of these coefficients。



![](img/ed7e64690eefb790b2668445a24a42e7_24.png)

![](img/ed7e64690eefb790b2668445a24a42e7_25.png)

![](img/ed7e64690eefb790b2668445a24a42e7_26.png)

![](img/ed7e64690eefb790b2668445a24a42e7_27.png)

![](img/ed7e64690eefb790b2668445a24a42e7_28.png)

![](img/ed7e64690eefb790b2668445a24a42e7_29.png)

All the way to the left， we have the lambmbda too high， we are regularizing too much。

 putting too much penalty for high coefficients and not allowing for enough complexity。

 and then finally that just right value as with riddge will be somewhere in the middle that allow us to find that trade off between bias and variance to ensure that we're able to generalize when we create our models。



![](img/ed7e64690eefb790b2668445a24a42e7_31.png)

![](img/ed7e64690eefb790b2668445a24a42e7_32.png)

![](img/ed7e64690eefb790b2668445a24a42e7_33.png)

![](img/ed7e64690eefb790b2668445a24a42e7_34.png)

![](img/ed7e64690eefb790b2668445a24a42e7_35.png)

So again， we look at the effects of differing values for lambda。



![](img/ed7e64690eefb790b2668445a24a42e7_37.png)

This time， the difference between this and ridge is that it will quickly zero out a lot of the values。

 So here we see one of the coefficients being especially high compared to the rest when we have a higher lambda value。



![](img/ed7e64690eefb790b2668445a24a42e7_39.png)

![](img/ed7e64690eefb790b2668445a24a42e7_40.png)

![](img/ed7e64690eefb790b2668445a24a42e7_41.png)

Then in the middle one， we have that just right where we have actually eliminated。

 let's say about two thirds of our features and only kept around one third of our features。

 so again eliminating many of our features while also reducing some。



![](img/ed7e64690eefb790b2668445a24a42e7_43.png)

![](img/ed7e64690eefb790b2668445a24a42e7_44.png)

![](img/ed7e64690eefb790b2668445a24a42e7_45.png)

And then finally， again， if our lambda is equal to zero。

 then we have no regularization and all the coefficients will remain unaffected。



![](img/ed7e64690eefb790b2668445a24a42e7_47.png)

![](img/ed7e64690eefb790b2668445a24a42e7_48.png)

So looking at the graph that shows the relationship between our features and our lambmbda values。

 we notice that the overall values will decrease。

![](img/ed7e64690eefb790b2668445a24a42e7_50.png)

![](img/ed7e64690eefb790b2668445a24a42e7_51.png)

But if there's high multicollinearity again， we will also see this increase as one feature takes on more explanatory value as others begin to be zeroed out。

 so similar to what we saw with Ridge， whereas our lambda increases。

 our coefficients should shrink some multicollinearity may cause one of those to increase for sort portion until ultimately decreasing as well。



![](img/ed7e64690eefb790b2668445a24a42e7_53.png)

![](img/ed7e64690eefb790b2668445a24a42e7_54.png)

And similar to what we mentioned before， it's possible if we are trying to find the optimal model。

 if we're starting with a very complex model， we can reduce variance by quite some amount without increasing our bias too much。



![](img/ed7e64690eefb790b2668445a24a42e7_56.png)

![](img/ed7e64690eefb790b2668445a24a42e7_57.png)

![](img/ed7e64690eefb790b2668445a24a42e7_58.png)

Again， the goal being to come up with the regularization term。

And thus the right complexity that gives you the lowest error on your holdout set。



![](img/ed7e64690eefb790b2668445a24a42e7_60.png)