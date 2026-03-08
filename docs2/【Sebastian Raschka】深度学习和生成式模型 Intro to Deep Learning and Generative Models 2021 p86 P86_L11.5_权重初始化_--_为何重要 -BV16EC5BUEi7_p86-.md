# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p86 P86_L11.5_权重初始化_--_为何重要 -BV16EC5BUEi7_p86-

![](img/aac6436f051865829f8593f448237e52_0.png)

Yeah， previously， we talked about input normalization。

 but weight initialization matters too to have everything on the right or on a good scale。

 No pun intended here， though。 So now we are briefly motivating why we care about when weight initialization。

 And then I will show you。Two common ways to initialize weights。

 And then we will see how we can do that in Pytorch or whether we even have to bother about that in pytorch。



![](img/aac6436f051865829f8593f448237e52_2.png)

So yeah， previously， we discussed that we want to initialize weights to small random numbers to break a symmetry in the multi layer perceptron。

 So I gave it to you as a question to think about。 And yeah， we discussed this on Piazza。

 if you have still questions about that， there was yeah a good answer on piazza on that。So， yeah。

 but besides having small， random numbers to break the symmetry。

 we also want the weights to be relatively small， right， So that is another thing to think about。

 But it has， yeah， something to do with what I showed you earlier in an earlier video here about input normalization。



![](img/aac6436f051865829f8593f448237e52_4.png)

So just to yeah kind of explain or motivate this a little bit。

 think of the multi layer perception again， where we here have the multivariable channel for yeah updating one particular weight。

 So this is something I just copy and paste it from a previous slide， nothing new here。

But I want you to focus briefly on this part here where we are the derivative of the activation with respect to the activation in the previous。

There， actually we could。Expand that。To嗯。Let's should have written it like this。

SoLet's switch like this song。Z1。2， and then。I'm just expanding it here。

So what the critical part here is。Its this part where we compute the derivative of the activation with respect to the input。

 particularly， for example， if we have something like the logistic sigmoid， right。

 because if we have a logistic sigmoid， if you recall the。



![](img/aac6436f051865829f8593f448237e52_6.png)

Yes， the partial derivative of the logistic sigmoid with respect to its input， so。

The derivative is largest if the input is 0， right？ And also， even if it's 0 is just 025。



![](img/aac6436f051865829f8593f448237e52_8.png)

So， if we have。Something like this year where we have this term。

 we have a number that is always smaller than one， right。 So in this case。

 this can lead to a so called vanishing gradient problem。



![](img/aac6436f051865829f8593f448237e52_10.png)

Because then we multiply a number。With a number smaller than one multiple times。

 if we have many layers。 So， for instance， if we assume this is the largest gradient or partial derivative we can get for the logistic sigmoid function。

 And then if we have 10 layers， we have a multiplication with a value。That is at most，0 to 5。

And that yeah will degrade the other gradients as well substantially， right。

 Because if I go back one more time。 So we have all these， these other terms here， right。

 So the term。

![](img/aac6436f051865829f8593f448237e52_12.png)

Here， here and here， It's all multiplied with this one， right， So this is small。 Then well we。



![](img/aac6436f051865829f8593f448237e52_14.png)

![](img/aac6436f051865829f8593f448237e52_15.png)

We degrade the whole the whole update here， the gradient here， and this is only for two layers。

 if we have more layers， we have more of these terms in in there if we use the logistic sigmoid。



![](img/aac6436f051865829f8593f448237e52_17.png)

So in fact， then we would， if we have 10 layers， we would degrade the value by about 10 to the power of-6。

 so the gradientd will be so small that the network will probably not learn much anymore。



![](img/aac6436f051865829f8593f448237e52_19.png)

So。because of that， it's yeah， usually a good idea to use other types of。Actation functions。

 you can also kind of regulate that with the learning rate。

 But this is one of the motivations why it's important to initialize the weights Yeah， centered at 0。

 for example， if you use a logistic sigmoid function。

 because then you will have at least the maximum gradient， right， so。



![](img/aac6436f051865829f8593f448237e52_21.png)

If I go back， if you have inputs or the net inputs that are small。

 let's say in this range or large in this range， then the gradient will be even smaller， right？

 So this way， you want to have something that is at least you are centered at 0。

 so you can initialize your weights， for example， from a random。



![](img/aac6436f051865829f8593f448237e52_23.png)

normal from a random uniform distribution， for example， for example， in the range0，1。

 But if you use the logistic sigma， for example， it might be better to do it in a range between。

5 and 。5。Or maybe even smaller，-005 and。0。05。So。You can also yeah choose a positive range。 I mean。

 if you have a relu function， it probably doesn't really matter that much。 However。

 this gives you more combinations If your inputs are also negative and positive right。

 so in that way， yeah， you can do either or if you have a relu or you can also yeah just what's very common is to initialize the weights from a random Gaussian distribution with mean0 into small variance。

But these are just some， I would say some suggestions that have been used in the past。 Nowadays。

 it's actually more common to use either。

![](img/aac6436f051865829f8593f448237e52_25.png)

Something like the Xavier Gate initialization or King her initialization so we will talk about this in the next video。



![](img/aac6436f051865829f8593f448237e52_27.png)