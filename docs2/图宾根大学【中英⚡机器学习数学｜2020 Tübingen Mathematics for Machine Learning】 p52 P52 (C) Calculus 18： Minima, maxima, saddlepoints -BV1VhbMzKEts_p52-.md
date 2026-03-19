# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p52 P52 (C) Calculus 18： Minima, maxima, saddlepoints -BV1VhbMzKEts_p52-

![](img/c14dabd2a028380d2fa6823b7ff53bc6_0.png)

The reason why we are so much interested in taking derivatives in this lecture is that of course。

 nearly all machine learning algorithms in the end solve an optimization problem。😊。



![](img/c14dabd2a028380d2fa6823b7ff53bc6_2.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_3.png)

You have a loss function， you have a space of functions you want to pick the best function in this large class of functions to describe your data at hand and typically you specify a loss function and maybe a regularizer and then you want to find the best function which means you for example might want to minimize the loss so in the end we need to solve a minimization problem。



![](img/c14dabd2a028380d2fa6823b7ff53bc6_5.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_6.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_7.png)

And to find the minimum of a function， we typically look at the gradient。



![](img/c14dabd2a028380d2fa6823b7ff53bc6_9.png)

And then we need to define and once we know about the gradient。

 we also need to find out whether we are at the minimum a maximum or a saddle point and this is one I briefly want to outline in this lecture。



![](img/c14dabd2a028380d2fa6823b7ff53bc6_11.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_12.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_13.png)

So consider it's a definition。Consider a function F。

That goes from RN to R in the context of machine learning。

 RN are like are your input points maybe the feature by which you describe your。



![](img/c14dabd2a028380d2fa6823b7ff53bc6_15.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_16.png)

The objects that you're currently interested in that you want to classify， for example。

 molecules or customers or whatever you like。

![](img/c14dabd2a028380d2fa6823b7ff53bc6_18.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_19.png)

So these are objects described in our n and the output in the end is going to be， for example。

 a loss function or so， a real number， and assume this function is differentiable。😊。



![](img/c14dabd2a028380d2fa6823b7ff53bc6_21.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_22.png)

So in machine learning， it's very often the case that the natural loss functions you might want to come up with are not differentiable。

 for example， in classification， the natural loss function is asking。

 did I classify it right or wrong， It's a 01 function。

 a discrete function that is very annoyingly difficult to optimize。 So what we do instead is we pick。



![](img/c14dabd2a028380d2fa6823b7ff53bc6_24.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_25.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_26.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_27.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_28.png)

We pick alternative loss functions that maybe have similar properties。

 but are at least continuous and ideally also differentiable。

 Otherwise we can't really explain or we can't really write down an optimization algorithm and then we optimize the surrogate loss function in hope or can maybe also prove that by optimizing the surrogate loss function。

 we also optimize the true loss function we're interested in。 So this is why I started saying。

 assume this function is differentiable。

![](img/c14dabd2a028380d2fa6823b7ff53bc6_30.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_31.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_32.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_33.png)

![](img/c14dabd2a028380d2fa6823b7ff53bc6_34.png)

And now what is a critical point？

![](img/c14dabd2a028380d2fa6823b7ff53bc6_36.png)

The gradient of f at a point is 0。

![](img/c14dabd2a028380d2fa6823b7ff53bc6_38.png)

Then we call F we call。

![](img/c14dabd2a028380d2fa6823b7ff53bc6_40.png)