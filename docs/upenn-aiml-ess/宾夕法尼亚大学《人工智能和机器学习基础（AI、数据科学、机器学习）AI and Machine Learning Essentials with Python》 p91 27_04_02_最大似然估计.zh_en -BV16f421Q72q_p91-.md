# 宾夕法尼亚大学《人工智能和机器学习基础（AI、数据科学、机器学习）AI and Machine Learning Essentials with Python》 p91 27_04_02_最大似然估计.zh_en -BV16f421Q72q_p91-

![](img/810939d2b4116e756cf0a7db5860550b_0.png)

Now， given a particular data set for my pairs of inputs and outputs。

 we would like to estimate the parameters beta0 and beta1 that nature is using to generate the data。

Remember， we're going to assume in this particular point that nature is generating the data points using a logistic function with two particular values for beta 0 and beta 1。

 which we don't know， essentially we are going to observe the data and we would like to estimate beta 0 and beta 1 exclusively from data。

To perform this estimation， we're going to use a criterion called the maximum likelihood criterion。

That allow us to estimate beta0 and beta 1 from that alone。

Let's assume for now that the set of inputs are given。

The likelihood function is defined as the conditional probability of observing a particular set of outputs given the inputs。

This conditional probability。Is given in here for just one pair of points so essentially the conditional probability of observing an output Yi given an input X is given by this expression。

 we're going to assume that these conditional class probabilities are described by logistic functions with parameters theta 0 and theta 1 so these are essentially two genetic values for beta 0 and beta 1。

Now assuming that the points in our data set are generated independently at random from each other。

 we're going to have that the probability of observing a whole data set is going to be equal to the product of these probabilities。

 so this is coming from the definition of independence。Therefore。

 the product of all these conditional class probabilities is what we call the likelihood function。

Notice that this likelihood function depends only on the unknown parameters。

 The 0 and Theta 1 since Xi and Yi are assumed to be given。

So the only thing that's unknown in this part of the equation arezeta 0， azeta 1。The X。

 I and the Y I are known。Now we can easily rewrite this equation。

 taking into account that the expression for the conditional class probabilities are different when the output Yi is 1 and when the output Yi are 0。

 so if we go back to the previous slide， when the output Yi is equal to 1。

 this is the function that we should use。In contrast， when Yi is equal to 0。

 this is the function that we should use。Therefore， we're going to group together all the points y I。

For which the output is equal to 1。And all the points Yi for which the output is equal to 0。

 and we're going to separate the products into two terms， this first product。

 which are essentially the terms in this product for which Yi is equal to1。

 and this second product which are the product for outputs equal to 0 in that product。

Also notice and the conditional class probabilities inside this first product is the one associated with an output1 and the conditional class probability of the second product is the one associated with an output0。

So these two expressions are exactly the same thing。Now， once we have a likelihood function。

 the maximum likelihood estimator is very easy to state。

 essentially our estimates of beta0 beta 1 which remember are unknown to us only nature knows them。

 are going to be the result of maximizing the likelihood function wherezeta0 and theta 1 are unknown parameters and we find the values of those parameters that maxs this function。

This values。Are going to be saved？In beta 0 hat and beta 1 hat。

 and this will be the estimates of the non parameters beta 0 and beta 1。

We're going to quickly illustrate this with one example。So this is the default data set。

 essentially the default data set contains a collection of individuals that have borrowed money from the bank。

And the bank has historical data of individuals that were able to return the money and those that weren' able to return the money。

 in other words they defaulted on the credits。In the plot below， we show as blue circles。

 individuals that were able to successfully return the money while the orange crosses were individuals。

That had to default on their credit。The coordinate of these points are nothing but the balance of those individuals under corresponding income。

So you can see in this plot that income is not very useful to predict defaults。

 however balance is very useful to understand this。

 you can focus on a particular income value so we can make a slicing here。

And you're going to notice that the fraction of points that were able to successfully and unsuccessfully return that money are pretty much the same when we shift this window。

However， if you focus on balance， you can notice that in the low values of balance。

 people are able to return their credits， while in the high values of the balance。

 people are more likely to default on their credit。Therefore， in the following experiment。

 we will only use balance。Has the input to predict the probability of defaulting on your credit。

Using the default data set， we get the following coefficients for our logistic regression。

Essentially the intercept is going to be beta 0， the balance is going to be beta 1。

 This is going to be our estimate of beta0 hat。Our estimate beta 1 hat。

And as we saw in the case of linear regression the values of beta I hat are random variables。

 therefore there is a standard error which is nothing that an approximation of the standard deviation of our estimates beta I hat。

 so we see that the standard deviation of beta 0 hat is 0。

36 and the standard deviation for beta 1 hat is 0。0002。

Once we find the values of Vetaciro hat and beta1 hat using， for example， maximum likelihood。

 we can make predictions about the probability of an individual defaulting if we know her balance。

So in particular， we're going to define P1 hat as a function of the only input balance。

 so this is essentially the only input we're going to be using。

And the shape of this function is exactly a logistic function where beta 0 and beta 1 are substituted by beta 0 hat。

And beta1 hat that we compute from the data set。Now using this function。

 we can make predictions about the probability of defaulting。

 meaning the probability that the output is equal to one。

 which indicates default given the balance of an individual。So， for example。

 if the balance of an individual is $1，000， the probability of defaulting according to the logistic function will be 0。

6%。If the balance of the individual is double that $2，000。

 then the probability of defaulting jumps up to almost 60%。

So this is something that we can look in the previous figure。Essentially in here。

 we have that when an individual has $1，000， the probability of the F is much smaller than when the individual has a $2。

000 balance。

![](img/810939d2b4116e756cf0a7db5860550b_2.png)