# 杜克大学《机器学习｜Introduction to Machine Learning》中英字幕 p07 07_01_02_多层感知机数学模型.zh_en -BV1yjvdBQEaU_p7-

So now what we would like to do is take a look at the multi layer perceptron。

And at some of the math that drives。That model， the。

 the aspects of the mathematics are worth going into because they are at the heart of most neural models that we'll be interested in。

 So while we'll be talking specifically about the multi layer perceptron。

 these ideas extend to other types of models。So the key thing that we would like to try to communicate。

Is the idea that the multi layer perceptron is a natural extension of logistic regression。

So you recall that in the logistic regression， we had the data which was represented here by x sub I。

 x sub I 1 through x sub I M， which corresponds to the M components of the Ih data sample。

 so x sub I is the Ih data sample and the logistic regression。

 what we did was we mapped that input data X I to a variablezi I。Through an inner product。

Or a dot product between the data XI。And a vector B。 And then so there was a single， if you will。

 filter that was applied to the data。The idea in the multi layer perceptron is that instead of just projecting the data X I with one。

Template vector， as we did in logistic regression。 What we're going to do is consider K。

Filters or reference vectors， B1 through BK。And we're going to take X and we're going to take the inner product of X I with B1。

 X with B2， and all the way from x to X with Bk inner product with BK。

 and so the idea is that instead of taking the data and taking an inner product with a single vector as we did in logistic regression。

 we're going to do it with K vectors B1 through BK。

 we're going to then add biases in the same way that we did with logistic regression。

And then we will have outputs of each of those operations， which will be Z1 through Z IK。

And so instead of realizing as we did with logistic regression， just a single output。

 here we have K outputs， which are K features from layer1。

Those features are then sent through a logistic function， which is shown on the top right。

 which is a mapping of a real number。A number that can be anywhere from negative infinity to positive infffinity。

 a real number。 we squash it or map it to a number between0 and 1。

 and the reason we do that is that now we're going to be introducing probability on Klant features。

 So the way to think about this is that we have a data X I and then there are K latent features or processes that are responsible or at least from a modeling perspective are represented as being responsible for the data after this the inner product and then going through the logistic function we then have through the sigma。

And that's called a sigmoid function， we then have a mapping for each of those k features to a probability from0 to 1。

 and so that basically represents the degree or the degree to which each of those latent features is represented in the data。

And then that those K latent features or those Klant probabilities are then sent through a logistic regression type model in the same way that we did previously with logistic regression。

 and now we have a single template filter C with which we take the inner product of those latent features。

 we get a variablezeta subi that Greek symbol is calledzeta。

Zta subbi is then again sent through a sigmoid function。

 which tells us the probability of the data being associated with a particular binary label。

 so the key thing to notice about what we're doing with the multi layer perceptron。

Is that instead of taking the data XI， which has M components， XI1 through XIM。

 and then directly using logistic regression to map that to a probability of a binary outcome。

 we have an intermediate step where we introduce K latent features。

And then those K latent features are then subsequently sent through a logistic regression type model to ultimately give us a probability of a binary outcome。

 This added model sophistication through that intermediate or middle layer adds significant modeling flexibility in particular。

 it allows us to consider nonlinear decision boundaries in feature space。And therefore。

 it oftentimes has been shown to be more effective from the standpoint of yielding more effective results。



![](img/9c5a9a277ccba99cf3c45f5b74792c63_1.png)

![](img/9c5a9a277ccba99cf3c45f5b74792c63_2.png)