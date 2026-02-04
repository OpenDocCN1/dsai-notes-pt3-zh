# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P85：36_正则化进一步详细信息第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's think about the regularization of our coefficients from a probabilistic vantage point。



![](img/9f31ba5dad2834e3a700b87acadd73c1_1.png)

Think about it from the base perspective， regular will be imposing certain prior distributions on our regression coefficients。

 so we're trying to come up with these regression coefficients and we're going to assume there's some prior distributions that we're going to try to update we're going to try to update the posterior of what we think those coefficients should be。



![](img/9f31ba5dad2834e3a700b87acadd73c1_3.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_4.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_5.png)

So it's imposing certain knowledge of that distribution of our coefficients before coming up with the actual relationship between our coefficients and our x and Y values。



![](img/9f31ba5dad2834e3a700b87acadd73c1_7.png)

Ultimately， we're going to be trying to find that optimal coefficients given our X and Y data。

And in basin fast， this can be reformulated as a probability of the y of our outcome variable。

 given beta。

![](img/9f31ba5dad2834e3a700b87acadd73c1_9.png)

Times our prior understanding of what beta should be。



![](img/9f31ba5dad2834e3a700b87acadd73c1_11.png)

So again， we are saying if we are trying to find the probability of our coefficients given our data。

 we can use base formula to recalibrate this。

![](img/9f31ba5dad2834e3a700b87acadd73c1_13.png)

So that we are finding the probability of getting our target， given some set of parameters。

 our coefficients multiplied by our prior distribution of our prior betas。



![](img/9f31ba5dad2834e3a700b87acadd73c1_15.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_16.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_17.png)

So now our solution is going to be dependent on how we define these priors from which our betas are being drawn。



![](img/9f31ba5dad2834e3a700b87acadd73c1_19.png)

We're essentially defining that prior distribution function G when we choose our form of regularization。

 whether that's ridge or lassso。

![](img/9f31ba5dad2834e3a700b87acadd73c1_21.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_22.png)

And for L2 for Ridge， we will be imposing a Gaussian prior on each one of those coefficients。



![](img/9f31ba5dad2834e3a700b87acadd73c1_24.png)

So we would be assuming that our coefficients are drawn from a normal distribution。



![](img/9f31ba5dad2834e3a700b87acadd73c1_26.png)

While if we're using L1 or Laso， we will be imposing Llaallaian prior。

 and we'll see these distributions on the next slide。

 but again the idea being that they were likely pulled from particular distributions。

 each one of our betas， so we're imposing this prior distribution on each one of our betas depending on whether we use L2 or L1 regularization。



![](img/9f31ba5dad2834e3a700b87acadd73c1_28.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_29.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_30.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_31.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_32.png)

So looking at these prior distributions again reveals the difference in behavior。



![](img/9f31ba5dad2834e3a700b87acadd73c1_34.png)

For both， we are imposing a distribution centered at zero。

 so we're saying zero is most likely value for our coefficients。



![](img/9f31ba5dad2834e3a700b87acadd73c1_36.png)

But the Laso has a much sharper and higher peak at zero。

 since it is more likely to zero out some of our coefficients。



![](img/9f31ba5dad2834e3a700b87acadd73c1_38.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_39.png)

Then to tie this back to the Atlanta value that we introduce in regards to having these prior distributions。



![](img/9f31ba5dad2834e3a700b87acadd73c1_41.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_42.png)

That lambmbda actually will mean a smaller variance for a prior distribution。



![](img/9f31ba5dad2834e3a700b87acadd73c1_44.png)

So if we have a smaller variance， if you think about this distribution being shrunk down。

 that means that values are more likely to be close to zero。



![](img/9f31ba5dad2834e3a700b87acadd73c1_46.png)

And therefore， a higher lambda。Which shrinks the variance means smaller coefficients because those coefficients are more likely to be close to zero。



![](img/9f31ba5dad2834e3a700b87acadd73c1_48.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_49.png)

Now let's recap everything that we understand in regards to regularization the goal here is always going to be to optimize our complexity trade off so that we can minimize error on our holdoutset on an outside set of data。



![](img/9f31ba5dad2834e3a700b87acadd73c1_51.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_52.png)

So we reduce our complexity by penalizing it in our cost function。

 we can work through different values for our regularization term， that lambda term。

 to adjust the penalty， and fine tune how much we want to reduce complexity。



![](img/9f31ba5dad2834e3a700b87acadd73c1_54.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_55.png)

Introducing regularization will increase bias， but reduce variance。



![](img/9f31ba5dad2834e3a700b87acadd73c1_57.png)

And it's often going to be worth that trade off。Often we'll find that the starting model is way too sensitive to small changes。

 so adding bias， but again， decreasing variance will help us find a more balanced and generalizable model。



![](img/9f31ba5dad2834e3a700b87acadd73c1_59.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_60.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_61.png)

We have options， again Ridge or Lasso， L2 or L1 and can validate the choice of model as well as the strength of our lambda termsms。

 We saw this in our notebook how we can iterate through different possible solutions for each one of our hyperparmeters or for each one of our models and we also talked about some pros and cons such as the feature selection and the added interitibility with Lasso and how Ridge will penalize outliers more heavily and how itll also run at a faster clip than Lasso。



![](img/9f31ba5dad2834e3a700b87acadd73c1_63.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_64.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_65.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_66.png)

The goal of regularization is always going to be about finding this right bias and variance trade off。



![](img/9f31ba5dad2834e3a700b87acadd73c1_68.png)

We need a model that are again， sufficiently complex to capture the actual relationship between x and y。

 so the bias can't be too high， but also can't be so complex that we are overfit to our training set。



![](img/9f31ba5dad2834e3a700b87acadd73c1_70.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_71.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_72.png)

So we can't have that variance that's too high where we have this perfect relationship between x and y。

 and a slight change in x will have a huge effect on our outcome variable y。



![](img/9f31ba5dad2834e3a700b87acadd73c1_74.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_75.png)

So to make clear how this all worked， we discussed the analytical approach where we know that smaller coefficients will necessarily lead to more complex to less complex models。

 Small coefficients have less complex models， the geometric approach which showed us under the hood。

 how we find the optimal solutions， given the constraints of regularization。

 and how that leads to different resulting coefficients for ridge and Lasso， right。

 if we look back to our geometric example， we saw that where it intersected both the penalty for the coefficients and our Os cost function that it would be more likely to zero out with Lassso because of those edges versus ridge which had a more circular。



![](img/9f31ba5dad2834e3a700b87acadd73c1_77.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_78.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_79.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_80.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_81.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_82.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_83.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_84.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_85.png)

Penalty for each one of our beta coefficients。Then finally， we discussed the probabilistic approach。

 which explain Lasso and Ridge in the framework of a Bay problem where we would be imposing specific priors on that distribution。



![](img/9f31ba5dad2834e3a700b87acadd73c1_87.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_88.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_89.png)

And the distribution being the distribution of those coefficients that we're trying to learn。



![](img/9f31ba5dad2834e3a700b87acadd73c1_91.png)

So that closes out our discussion of the details behind regularization and how we can take different approaches to understanding how regularization actually works。



![](img/9f31ba5dad2834e3a700b87acadd73c1_93.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_94.png)

This concept of regularization will be key throughout your machine learning journey。

 as throughout every single model well be using some form of regularization between in order to find the right balance between bias and variance。

 and that closes out course  two and I look forward to seeing you in course3， thank you。



![](img/9f31ba5dad2834e3a700b87acadd73c1_96.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_97.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_98.png)

![](img/9f31ba5dad2834e3a700b87acadd73c1_99.png)