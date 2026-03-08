# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p52 P52_L8.2_逻辑回归损失函数 -BV16EC5BUEi7_p52-

All right， let's now take a look at how we compute the loss function for the logistic regression model。



![](img/831d43b717c440970f708ed87604d251_1.png)

The so called negative look likelihoodness。So here。

 that's just the slide I already showed you at the end of the previous video。

And I just want to recap some of the main aspects here。

 So there are two things going on in this slide。 So one is how we compute this probability。

 And here at the bottom is what we want this probability to be。

So let's take a look at what we want first in this case。 So we want this probability。

 the class membership probability for class 0 to be。1， to be maximized。If the true label is indeed 0。

 So this is， on the left hand side， this is the class membership probability。 We want this to be。

As high as possible。For equal 0， if the true label is indeed0。RightAnd vice versa。

 we want the class membership probability here for class1。To be as high as possible。

 also approaching one。If the true label is one， right， so。

Given us what we want is we want to maximize the probability for the given label， for the true label。

Now， how is this probability computed。That is what is shown here。 So here again。

 this is how we compute these probabilities， so。The class membership probability for y equals  one。

 So here， this is not really the true label。 You think of， you can think of it as。嗯。

As this one in this function here， so。We compute the class membership probability for y equals  one。

So this one here at the bottom。By just the activation。 So this is simply the activation。

 So the logistic sigmoid。Applied to the。Net input。And for the second case。

 So this one can be computed by one minus the activation。So， this would be。This one here。Okay。

 so this is just like a brief recap。 Now we can actually rewrite this piecewise function here。

 how we compute this class membership probability using this more compact notation。 So this combines。



![](img/831d43b717c440970f708ed87604d251_3.png)

Or this essentially summarizes this piecewise function in one line or one equation。

 So how it works is yeah， let's just plug in some numbers。 or first。

 let's let me clarify what what this a here means。 So this a is yeah the activation。

 it's just instead of writing H of x let's just abbreviate it with a letter a。

 It's like nicer to look at or look simpler。Now let's consider the case where we have the class membership probability for class1。

Given the feature vector x。So， if。Y equals one。Then。Yeah， this term。Remains as a， and。This one。

nothing happens here。 This one becomes one right and1 minus-1 is 0 so。Yeah， this canceled。

Well becomes 0 essentially。 and something to the power of 0 is one， right？ So this whole term here。

Becomes one。 So this whole equation here reduces2 just。嗯。Right， so a is equal to h of x。

So this one here。 So we satisfy this first term here。 So this。

 I'm just showing you right now that this function indeed summarizes the piece of I linear function。

 So now consider the case。Well， oops。Y equals 0， given the feature x to x。So here now consider。

 let me erase this a little bit so we have more space。Okay。So， we are looking now。This one here， so。

Where y is equal to 0。 So if y is equal to 0， then this is a 0。 So this whole。Thing becomes one。And。

we have is this becomes a zero， so this term here becomes one。So what we have， then what remains is。

1 minus a， right， which is this one。 So you can now see that this equation here at the bottom summarizes this piece of by linear function here。

Just a different notation。

![](img/831d43b717c440970f708ed87604d251_5.png)

Now， yeah， what we want is we want to maximize the class membership probabilities。 So。

 and usually in a data set， we not only have one single data point， we have。And data points。

 So this is the size。O。Training。Seid。And yeah， we want to maximize the class membership probabilities for all these examples in the training set。

So you can think of it as， yeah， the probabilities here multiplied。 So the conditional probabilities。

 and we want to find， yeah， the。Model parameters， because。



![](img/831d43b717c440970f708ed87604d251_7.png)

Yeah， it depends here on our model， right。 So the probability here。

 the prediction probability here depends on our model parameters。

 That's how we compute these probabilities。 So we want to find good parameters that maximize the class membership probability for the right class。



![](img/831d43b717c440970f708ed87604d251_9.png)

So this concept is also known as maximum likelihood estimation。

 So the we want to maximize the likelihood， the probability of observing the data given the model parameters。

And yeah， you probably know this from other statistics classes。

 so I don't want to go into too much detail about maximum likelihood estimation here。

 So just assume now we want to maximize this term here。



![](img/831d43b717c440970f708ed87604d251_11.png)

So here what I'm doing is I'm just rewriting this with we have the simpler notation I showed you before。

So if I go back to slides。そ。This notation here at the bottom。



![](img/831d43b717c440970f708ed87604d251_13.png)

That's what I'm doing here。 So I'm replacing this。Right。

 this is something you have seen before on the previous slide I just showed you。

 I'm replacing this now with this more compact notation here where。Before I I re it as A。

 I don't know why I expanded it here again。 I I think I just wanted to show you how it's computed。

Where a is we have the logistic regression model， where this is sigma logistic activation function and z is the net input。

All right。So。You can think of it also as the loss function。 then so as the logistic loss。

 which we computers follows the probability over the whole training set。

And I said we want to maximize this， right， We want to maximize the class membership probabilities。

In practice， it's actually easier to maximize the natural lock of this equation。

 which is also called the lock likelihood function。So why is that if we apply the lock here。

 then we can replace the product。By a sum。AndAlso here in this multiplication。

 we can replace it with a sum and numerically on a computer。

 this is just more stable to implement it more stable when we use， for example， gradient descent。

But you can think of it also as maximizing the。Look likelihood also maximizes the likelihood。

 So it's like the same kind of the same thing as if you maximize one， you also maximize the other。

 So in that way， this is why we can do that。So we here at the bottom is the。

Lock and was just taking the lock of this party at the at the top。 So we have now。

Why is the true label times lock the activation。So this is the cast membership probability。So。

Those made for completeness， this would be。Y given X， and， of course， also the model parameters。

 But I'm omitting the model parameters here just for simplicity。And yeah。

 this is the lock likelihoodness。

![](img/831d43b717c440970f708ed87604d251_15.png)

I mean， it's not。Quite the likelihood in us because there's one more modification。 So in practice。

 also， when you recall from the pytorch code that I showed you。

 we have the stochastic gradient descent。And in stochastic， gradient descent。

 let me brother us may be known。Schastic。Grilliant。Sent， we want to minimize。

So this是 the process when we。Minimize something。 If we wanted to maximize something。

 we would have to use stochastic gradient。Escent。That is like。The other way around， we want to。

 we would maximize something。So but we don't want to。

 so if we think of it maybe as a loss function so， or as a function。

 So grain and descent would be like this where we go down this hill。

And gradient essencecent would be。This way， where we go up that hill。Now。

 in Ptor are many other libraries， it just happens just for simplicity。

There's an implementation of gradient descent where we minimize something。 So in that way。

If we would just give it a look likelihood function as the loss function to optimize， then yeah。

 it would actually max minimize this loss， which would actually very bad。

 So we we would get as very small class membership probabilities for the correct labels。

 So what we can do now is just to turn around this problem。 So instead of。嗯。

Maximizing the look likelihood， we can minimize the negative look likelihood。

 just putting a negative here in front。 And then we turn this maximization problem into a minimization problem。

 And then we can just use the stochastic gradienting descent implemented in Pytorch。😊。

So it's just like a little trick we do by flipping around the sign here。

 and another trick we can do in code is that we usually add a one over end scaling factor。

Here to scale yeah over the number of data points in the training set or the batch size。

 the mini batch size。 So last time we also talked about mini batches。 So we can also excuse me。

 so we can also consider the mini batch size here。

![](img/831d43b717c440970f708ed87604d251_17.png)

That it makes the training yeah， numerically more stable。Yeah。

 so youll just have a little checkpoint here to summarize。 So doing logistic regression by that。

 I mean a training logistic regression。Is actually similar to what we have done before in Adeline in Adeline。

 recall， we minimize the mean squared errors。Here， but yeah。

 the difference is that in logistic regression， we maximize the likelihood。

Because it's numerically more stable instead of maximizing the likelihood。

 we can also maximize the lock likelihood。But like I alsoa mentioned。

 the tools that we usually have available are developed for stochastic gradient descent so that we don't have to rewrite those tools。

 we can just yeah turn this maximization problem into a minimization problem so we can minimize the negative look likelihood。

 which is the same as maximizing the look likelihood。



![](img/831d43b717c440970f708ed87604d251_19.png)

So yeah， it was probably a lot of information in this short video In the next video。

 I will talk a little bit more about this training and how the loss function actually looks like I think this will probably clarify some yeah thoughts that you might have。

 So if you have some questions right now maybe don't think about it too hard。

 maybe watch the next video and then if you have questions then yeah maybe think about it more。

 but I think the next video could potentially clarify some points。



![](img/831d43b717c440970f708ed87604d251_21.png)