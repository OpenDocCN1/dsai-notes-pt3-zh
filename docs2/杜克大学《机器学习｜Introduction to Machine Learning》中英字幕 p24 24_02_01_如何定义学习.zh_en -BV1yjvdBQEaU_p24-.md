# 杜克大学《机器学习｜Introduction to Machine Learning》中英字幕 p24 24_02_01_如何定义学习.zh_en -BV1yjvdBQEaU_p24-

![](img/78047c082ca3f3ac8026ad9bb628792d_0.png)

Previously， we've gone through and we've defined different types of networks。

 We've started introducing what a deep network actually is， what a deep neural network actually is。

 and we've set up and talked about what they can do。

 but we haven't yet really talked about how we can actually learn a deep network in this video today。

 we're going to be talking about how we actually can define learning。

 And this is going to mean how can we define learning mathematically。

 And this will allow us to set this up as a problem and allow us to actually learn a network。



![](img/78047c082ca3f3ac8026ad9bb628792d_2.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_3.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_4.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_5.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_6.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_7.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_8.png)

So if you recall， we had this previous schematic。Where we were showing that we wanted to combine our training set or our training data。

 which is shown here on the left where we have eight different training examples。

 these are independent data examples where we have features or covariates and we have a particular outcome that's shown here in the Ys。

 and what we want to be able to do is create a network。

That can actually predict these outcomes given the features。 So on the right。

 we're showing here the logistic regression model or network where we're just showing we have all these features and they're combining linearly to construct the Z and we give the equation there。

 this is the exact same equation that you've seen several times already。

 and then we're going to convert it into a probability sigma Z and we previously have stated that we're just going to combine our training set and with this network to learn the parameters and we're going to have our learned parameters here。

But we need to talk about how we actually do this， how do we actually learn the parameters given our training data and our network that we want to learn。



![](img/78047c082ca3f3ac8026ad9bb628792d_10.png)

So this fundamental question that we're going to talk about today is how do we actually do this and in particular。



![](img/78047c082ca3f3ac8026ad9bb628792d_12.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_13.png)

Given a large amount of data and a model or network that we want to fit。

 how can we both efficiently and effectively learn the model parameters and we want to have these parameters be effective。

 We want them actually to predict them very accurately。

 but we also want them to be learned efficiently。 we have a finite amount of computational resources。

 We want to use these resources efficiently， and this is going to be a big deal if you want to use this in something like a cell phone or learn these on the fly。



![](img/78047c082ca3f3ac8026ad9bb628792d_15.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_16.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_17.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_18.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_19.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_20.png)

Specifically， let's talk about what it is we're trying to do when we're trying to do learning。

 and so succinctly， we just want to learn parameters that give us the best performance。

All this means is given data， let's find the best parameters B for that data。

 but we're going to run into our first problem here。 we haven't actually defined performance。

 so how can we actually go through and define the performance of this network So we have this network on the right and we say it can make predictions and we're going to find these parameters but how are we actually going to define how well it's actually doing。



![](img/78047c082ca3f3ac8026ad9bb628792d_22.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_23.png)

And so the way this actually happens is we're going to use something called empirical risk minimization and empirical risk minimization is jargon in the machine learning field and we'rell talk about what it actually means but what we're going to have here is we're going to have a loss function and a loss function is going to take two inputs it's going to have a true value or a true outcome。



![](img/78047c082ca3f3ac8026ad9bb628792d_25.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_26.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_27.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_28.png)

And it's also going to have our prediction。

![](img/78047c082ca3f3ac8026ad9bb628792d_30.png)

And this loss function is going to define a penalty on a poor prediction if we have a really great prediction。

 we're not going to really pay a loss， but whenever we have poor predictions。

 we're going to pay a big loss。

![](img/78047c082ca3f3ac8026ad9bb628792d_32.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_33.png)

And what we want to do is minimize average loss。

![](img/78047c082ca3f3ac8026ad9bb628792d_35.png)

And so we still need to define what this loss actually is。



![](img/78047c082ca3f3ac8026ad9bb628792d_37.png)

But we， if we know that we have this loss， all we're going to want to do is just minimize the average loss。

 If a loss is penalty for doing bad， we just want to minimize it。 So mathematically。

 we can state how we actually want to find our parameters B。



![](img/78047c082ca3f3ac8026ad9bb628792d_39.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_40.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_41.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_42.png)

So in this equation here on the bottom， we have that B star。 These are our optimal parameters。

 It going to be the argument of the minimum of one over n， the sum over all of our data points。

 and it's going to be for each data point， we have our loss function。 We have our true label。



![](img/78047c082ca3f3ac8026ad9bb628792d_44.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_45.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_46.png)

And we have our guests right， So this guess， the Sigma Z I here。

 the Sigma Z comes from our logistic regression model。

 and we have the parameters B a little bit hidden here， but Z is dependent our parameters B。

 So our parameters B are actually going to choose what we're guessing for each of these。



![](img/78047c082ca3f3ac8026ad9bb628792d_48.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_49.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_50.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_51.png)

And so what we want to say is now that we have some sort of loss function。

 we just want to find the parameters that give us the minimum average loss。

 and this is our mathematical statement of what it is。



![](img/78047c082ca3f3ac8026ad9bb628792d_53.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_54.png)

But we still need to define what our loss function actually is。



![](img/78047c082ca3f3ac8026ad9bb628792d_56.png)

So our loss function， so just as a reminder， we have sigma Z。



![](img/78047c082ca3f3ac8026ad9bb628792d_58.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_59.png)

It's going to be defined as our predicted probability。 and Y I is our true label or outcome。

 This is something that we have from our training set。



![](img/78047c082ca3f3ac8026ad9bb628792d_61.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_62.png)

And our network is going to change into this probability by combining with our parameters B。

 and this was shown in that network model。

![](img/78047c082ca3f3ac8026ad9bb628792d_64.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_65.png)

And so we can view this loss function， we can view this as a negative log likelihood。

 the log likelihood is widely used in statistics， generally in statistics we're trying to do a maximum log likelihood when we talk about losses。

 we're trying to minimize a loss so we just take the negative of the log likelihood so we say that the loss of our true outcome and our predicted probability is just equivalent to its negative log likelihood and we're just writing it in there minus log P of Yi given our predicted probability。

😊。

![](img/78047c082ca3f3ac8026ad9bb628792d_67.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_68.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_69.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_70.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_71.png)

And the mathematical form here for this negative log likelihood。

 when we're dealing with any binary problem。

![](img/78047c082ca3f3ac8026ad9bb628792d_73.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_74.png)

Is given below here， so we have this loss function of y and our prediction， the sigma Z。



![](img/78047c082ca3f3ac8026ad9bb628792d_76.png)

And it's going to be equal to minus y log of sigma z minus1 minus y log of1 minus sigma z。



![](img/78047c082ca3f3ac8026ad9bb628792d_78.png)

So this is a little bit of an obtuse mathematical form if you've never seen it before。

 so we're going to go through and we're actually going to draw what this equation is actually doing to try to get some understanding about what's going on。



![](img/78047c082ca3f3ac8026ad9bb628792d_80.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_81.png)

![](img/78047c082ca3f3ac8026ad9bb628792d_82.png)

So what we have here is just a visualization of the logistics loss function。

So the logistic across entropy loss here is that equation that we have defined。

 we define this on our previous slide， this is just a reminder of what it is。

 but there's two possible outcomes for what Y is。Why can either be positive or y can be negative right。

 And if it's positive， it's a1 and if it's negative， it's a zero。

 this is just how we've defined decided to define why。So we can visualize the two cases here。

 we can visualize when the case is positive， and we're showing this in the dash blue line。And。

If we look at the trend in the dash blue line here， which is when we have a positive outcome。

 if we're predicting that the probability of a1 is happening every single time。

 we're saying there's 100% chance that there's a1。Then we pay no penalty at all if we get it correct。

But the problem is that if we're overconfident we're actually going to pay a huge penalty。

 So what's going to happen is if we're predicting that it's a one and we're predicting this extremely confidently。

 and it's actually a zero。 We're going to pay a penalty that actually increases to infinity。

 And so we want to guess the correct answer。 but we actually don't want to be overconfident。

 And so this is a nice loss function that's going to penalize overconfi。

 but still encourage us to get it correct。 and it comes from deep properties of statistics。

We can talk about what this goal actually looks like for binary classification right so if we have our optimization goal。

 we're going to minimize the average loss。 So we have this B star here。

 this argument minimum over all possible B of our average loss function here and the average is taken over all data points。

And so if we have a logistic problem where we're using logistic regression or anything where we're doing a binary problem and we're doing it probabilistically。

 we can use this logistic loss， or it's also sometimes called the cross entropy loss。

 and we've just defined it there again， this is the same exact equation you've seen before。

But now we're just going to try to find the B star that minimizes this loss。

 and we're defining the loss just like this。So we need to come up with a way of actually saying。

 well， now we have a precise mathematical statement on what a parameters should be。

 we need to come up with an optimization algorithm that can actually find these parameters。

So just to recap what we've talked about in this video， we have our training set。

We have our model or network that we're trying to learn and we can define this however we want here we're just visualizing the logistic regression model。

 and we have this learn parameters and in order to learn these parameters。

 we're going to define this loss function and we're going to define an average loss and we're going to set up an optimization algorithm to find these parameters and that's what's going to come up in our next videos。



![](img/78047c082ca3f3ac8026ad9bb628792d_84.png)