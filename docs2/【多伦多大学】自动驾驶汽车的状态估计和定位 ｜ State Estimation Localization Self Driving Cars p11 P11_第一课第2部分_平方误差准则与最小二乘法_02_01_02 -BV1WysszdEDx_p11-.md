# 【多伦多大学】自动驾驶汽车的状态估计和定位 ｜ State Estimation Localization Self Driving Cars p11 P11_第一课第2部分_平方误差准则与最小二乘法_02_01_02 -BV1WysszdEDx_p11-

![](img/f5f5564789e4e7d83678a0c1fca08671_0.png)

In the last video， we saw how we could use the method of least squares to solve for a more correct value of a resistance。

 given a set of noisy measurements。In this video， we'll ask the question。

 what can we do if we suspect that some of our measurements are of better quality than others。

By the end of this video， you'll be able to derive and minimize the weighted least squares criterion that will let us handle measurements of different quality。

😊，And compare this new method to the method of regular or ordinaryin least squares that we discussed in the previous video。

Let's begin。One reason we may want to trust certain measurements more than others is that they may come from a better sensor。

For example， a number of our resistance measurements could have come from a much more expensive multimeter than the others。

Further， from now on， we'll also drop the assumption that we're only estimating one parameter and derive the more general normal equations。

This will allow us to formulate a way to estimate multiple parameters at one time。 For example。

 if we wanted to estimate several resistance values at once。

Let's begin by using the following general notation。

Willll have a set of M measurements that are related to a set of N unknown parameters through a linear model。

Recall that H is R Jacob Kobian matrix， whose form and entries will depend on the particular problem at hand。

One way to interpret the ordinary method of least squares is to say that we are implicitly assuming that each noise term v sub i is an independent random variable across measurements。

And has an equal variance or standard deviation， if you prefer II D。

 as was mentioned in the previous video。If we instead assume that each noise term has a different variance。

 we can define our noise covariance as follows。With this definition。

 we can define a weighted least squares criterion。By expanding this expression。

 we can see what we call this weighted least squares。

Each squared error term is now weighted by the inverse of the variance associated with the corresponding measurement。

In other words， the lower the variance of the noise。

 the more strongly its associated error term will be weighted in the loss function。

We care more about errors which come from low noise measurements。

 since those should tell us a lot about the true values of our unknown parameters。

Before we see how we can minimize this new weighted criterion。

 let's look at what happens if we set all of the noise standard deviations to the same value sigma。

In this case， we can factor out the variance in the denominator。

Since the sigma squared term is constant， it will not affect the minimization。

This means that in the case of equal variances， the same parameters that minimize our weighted least squares criterion will also minimize our ordinary least squares criterion。

 as we should expect。Returning to our weighted least squares criterion。

 we approach its minimization the same way as before we take a derivative。In the general case。

 where we have n unknown parameters in our bold vector X。This derivative will actually be a gradient。

Setting the gradient to the zero vector， we then solve for our best or optimal parameter vector X hat。

This leads to another set of normal equations， this time called the weighted normal equations。

Let's take a look at an example of how this method of weighted least squares works。

We'll take the same data we collected before， but now assume that the last two measurements were actually taken with a multimeter that had a much smaller noise variance。

Be careful here。 The numbers we list are standard deviations。

 which is why they have the units of ohms。In order to use them in our formulation。

 we'll need to square them to get the variances。Defining our variables and then evaluating our weighted least square solution。

We can see that the final resistance value we get is much closer to what the more accurate multimeter measured。

 as expected。Here's a quick summary of the methods of least squares and weighted least squares。

By using weighted least squares， we can vary the importance of each measurement to the final estimate。

It's important to be comfortable working with different measurement variances and also with measurements that are sometimes correlated。

A self driving car will have a number of different and complex sensors on board。

 and we need to make sure that we model our error sources correctly。So there you have it。

 weighted least squares。In this video， we discussed how certain measurements may come from sensors with better noise characteristics and should therefore be weighted more heavily in our least squares criterion。

Using this intuition， we derive the weighted least squares criterion and the associated weighted normal equations that can be solved to yield the weighted least squares estimate of a set of constant parameters。



![](img/f5f5564789e4e7d83678a0c1fca08671_2.png)

In the next video， we'll look at modifying the method of least squares to work recursively。

That is to compute an optimal estimate based on a stream of measurements without having to acquire the entire set beforehand。

This will be very important when we look at state estimation or the problem of estimating quantities that change continuously over time。



![](img/f5f5564789e4e7d83678a0c1fca08671_4.png)