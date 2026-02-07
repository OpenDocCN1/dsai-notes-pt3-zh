# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P76：27_岭回归.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/8c2b416c3c66985b597cdf1515af7bf8_0.png)

So with Rige regression， we're now taking the cost function that we just saw。



![](img/8c2b416c3c66985b597cdf1515af7bf8_2.png)

And adding on a penalty that is a function of our coefficients。 namely。

 is going to be the residual sum of squares， which is our original error。 Plus。

 that lambda value that we choose ourselves multiplied by the weights that we find squared。

 Therefore， the higher these weights are the coefficients are。

 the more we add on to our cost function。 So now， rather than just trying to reduce the error between outcome and prediction。

 We're now trying to reduce error， while also ensuring that our model is not too complex。

 right every time that we increase our coefficients， we are also increasing our cost function。

 which we are ultimately trying to minimize。

![](img/8c2b416c3c66985b597cdf1515af7bf8_4.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_5.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_6.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_7.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_8.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_9.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_10.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_11.png)

Now we want to keep in mind with our original linear regression cost function。

 scaling would not have a large effect on our eventual outcome。



![](img/8c2b416c3c66985b597cdf1515af7bf8_13.png)

But now that we have added on this coefficient weights to our cost function。

 scale will be of utmost importance。 So why is this the case。



![](img/8c2b416c3c66985b597cdf1515af7bf8_15.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_16.png)

This is something that we discussed before imagine we're working with two variables to predict sales for a certain product。



![](img/8c2b416c3c66985b597cdf1515af7bf8_18.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_19.png)

One of our variables is going to be the number of stores。

 and the other x variable is going to be the price of that item。



![](img/8c2b416c3c66985b597cdf1515af7bf8_21.png)

If the price is between $8 and $10。

![](img/8c2b416c3c66985b597cdf1515af7bf8_23.png)

And the number of scores is between 10000 and 20000 stores， the coefficient for price， a $1 change。

 if that's going to be our unit， will have a much larger coefficient in regards to its change in sales compared to a one unit change in stores。



![](img/8c2b416c3c66985b597cdf1515af7bf8_25.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_26.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_27.png)

Therefore， if we end up with a higher price coefficient。

 we'll end up being highly penalized for that coefficient， right。

 we're going to penalize large coefficients using our new ridge regression。 Therefore。

 we need to make sure that we first make sure that all of our different features are on the same scale。

 and we can do that using the standardization technique that we see here to subtracting the mean and dividing by the standard deviation。



![](img/8c2b416c3c66985b597cdf1515af7bf8_29.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_30.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_31.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_32.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_33.png)

So some things do you keep in mind overall when you're working with Ri regressiongression。



![](img/8c2b416c3c66985b597cdf1515af7bf8_35.png)

First of all， the complexity penalty lambmbda is going to be applied proportionally to the square of the coefficient values。

 so recall that as we increase or decrease the lambda。

 what we are doing is increasing or decreasing the effect of the square of each one of the coefficient values。



![](img/8c2b416c3c66985b597cdf1515af7bf8_37.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_38.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_39.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_40.png)

The penalty term has the effect of therefore shrinking our coefficients towards zero。

 not exactly zero like Lasso， but the higher the coefficient is， the more the penalty is。

 so therefore we want to be reducing the size of those coefficients。



![](img/8c2b416c3c66985b597cdf1515af7bf8_42.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_43.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_44.png)

This is going to impose bias on the model， but also reduce variance。

 recall this trade off the idea of regularization is inherently to reduce variance。

 to reduce the complexity of the model。

![](img/8c2b416c3c66985b597cdf1515af7bf8_46.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_47.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_48.png)

Now， we can select the best regular strength Lambda by doing cross validation。

 as we saw in our last notebook， we can increase and decrease Lambda and see how well it performed on holdout sets。



![](img/8c2b416c3c66985b597cdf1515af7bf8_50.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_51.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_52.png)

AndThen finally， as we just mentioned in our last slide。

 it's going to be best practice to scale our features。 For example， using these standard scalar。

 And this will ensure that our penalties aren't impacted by the variable scale。😊。



![](img/8c2b416c3c66985b597cdf1515af7bf8_54.png)

So coming back to our new cost function that we're using for rich regression。

 we have taken the original linear regression cost function and it audited on a penalty reduced complexity of our model。



![](img/8c2b416c3c66985b597cdf1515af7bf8_56.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_57.png)

The penalty shrinks the magnitude of all of our coefficients， as we discussed。

 by adding on this extra weight to our cost function。



![](img/8c2b416c3c66985b597cdf1515af7bf8_59.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_60.png)

And then we want to note that the way that it's actually going to work under the hood is that larger coefficients are even more strongly penalized because of this squaring。



![](img/8c2b416c3c66985b597cdf1515af7bf8_62.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_63.png)

Note that this means that a coefficient of two will be penalized four times as much as a coefficient as1 because1 squared is 1。

2 squared is4。 Similarlyly， if the coefficient was3。

 it would penalized nine times as much as a coefficient of one。

 So the idea to keep in mind is that this will penalize larger weights even more proportionly to the lower weight coefficients。



![](img/8c2b416c3c66985b597cdf1515af7bf8_65.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_66.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_67.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_68.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_69.png)

Now let's take this concept of lambda and that affecting the coefficients in relation to those polynomial graphs that we saw earlier。



![](img/8c2b416c3c66985b597cdf1515af7bf8_71.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_72.png)

So again， the idea here is trying to find that true function， that blue line， given our sample data。



![](img/8c2b416c3c66985b597cdf1515af7bf8_74.png)

So let's say that we are starting with a model that's just polynomial degree 15。



![](img/8c2b416c3c66985b597cdf1515af7bf8_76.png)

And rather than testing different polynomials， polynomials of degree 1， 4 and 15。

 we can introduce this lambda term。

![](img/8c2b416c3c66985b597cdf1515af7bf8_78.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_79.png)

So starting with polynomial of degree 15， we can say that lambda equals 0。1。

 which in this case will be referencing a very high lambda now that's going to be relative according to the coefficients that you have so you will have to play around with the lambda when you're looking at different lambda values in order to see which one actually fits given the data and the coefficients that you're working with。



![](img/8c2b416c3c66985b597cdf1515af7bf8_81.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_82.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_83.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_84.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_85.png)

But here we're going to sue lambda equals 0。1 is very high， and therefore we end up with a high bias。

 we're not able to fit well to the model because we have put too much weight on the coefficients on our regularization term。



![](img/8c2b416c3c66985b597cdf1515af7bf8_87.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_88.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_89.png)

Here in that middle value， we have regular our weights so that it won't be as complex as the full polynomial 15 model。

 but it won't be as simple as the one that had the lambda equal to 0。

1 in regards to that regularization term， right， So it's going to be something closer to the middle。



![](img/8c2b416c3c66985b597cdf1515af7bf8_91.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_92.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_93.png)

And then here， if you're workingrk with polynomial degree equal to 15， our lamb does equal to0。

 and that's essentially just trying to pick the polynomial 15 model without any regularization term。



![](img/8c2b416c3c66985b597cdf1515af7bf8_95.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_96.png)

So these are going to be the regularization costs for each one of the different values that we saw。

 the idea being that how much will that affect the coefficients that we choose So if we look all the way to the left we'll see that that's going to be the lowest values for our coefficients across the board。



![](img/8c2b416c3c66985b597cdf1515af7bf8_98.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_99.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_100.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_101.png)

Right， that's going to be。

![](img/8c2b416c3c66985b597cdf1515af7bf8_103.png)

Higher lambda value means that we want lower coefficients in the middle it'll be somewhere in the middle and all the way out to the right with lambda equal to zero。

 we put no penalty for each one of our coefficient terms and therefore we will have the highest coefficient values between these three graphs that we see。



![](img/8c2b416c3c66985b597cdf1515af7bf8_105.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_106.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_107.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_108.png)

Now what happens in regards to the relationship between the lambmbda values and those standardized coefficients？



![](img/8c2b416c3c66985b597cdf1515af7bf8_110.png)

As we discussed， generally moving to the right as lambda increases。

 the standardized coefficients should decrease， so there should be that inverse relationship。



![](img/8c2b416c3c66985b597cdf1515af7bf8_112.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_113.png)

We do see this ratings increase as the other features that we're working with here are decreasing。

 and that would just be something due to multicolonarity and you see at a certain point then they all start to decrease and they're all decreasing monotonically toward zero once it reaches a certain threshold。



![](img/8c2b416c3c66985b597cdf1515af7bf8_115.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_116.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_117.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_118.png)

So ideally， as you increase alpha a your lambda， alpha is going to be the value that you choose when you're actually working with an SK learn。

 but here we call it Lambda， as we increase lambmbda， we will decrease each one of the coefficients。



![](img/8c2b416c3c66985b597cdf1515af7bf8_120.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_121.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_122.png)

So here we see this complexity tradeoff and it's possible that variance reduction may actually outpace the increase in bias so we can find a better fit model without having to increase bias too much。

 So what do we mean by this What we mean is we can reduce the complexity while still consistently having enough information to show that relationship between X and Y in our training set So we're not increasing bias too much。

 The idea here being that there may not necessarily be a direct linear tradeoff。



![](img/8c2b416c3c66985b597cdf1515af7bf8_124.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_125.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_126.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_127.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_128.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_129.png)

Rather， for the example that we see here， we're able to reduce complexity for some time while barely affecting that bias。



![](img/8c2b416c3c66985b597cdf1515af7bf8_131.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_132.png)

And this may happen if we're starting with an extremely overfit model and we can keep reducing variance without increasing that bias。



![](img/8c2b416c3c66985b597cdf1515af7bf8_134.png)

In order to find eventually that optimalimum value。



![](img/8c2b416c3c66985b597cdf1515af7bf8_136.png)

That's going to allow us to have the lowest mean squared error on our holdout set。



![](img/8c2b416c3c66985b597cdf1515af7bf8_138.png)

So that closes out this video on Rige regression in the next video we will introduce another means of priorization for linear regression。



![](img/8c2b416c3c66985b597cdf1515af7bf8_140.png)

![](img/8c2b416c3c66985b597cdf1515af7bf8_141.png)

Called Lasso regression， I'll see there。

![](img/8c2b416c3c66985b597cdf1515af7bf8_143.png)