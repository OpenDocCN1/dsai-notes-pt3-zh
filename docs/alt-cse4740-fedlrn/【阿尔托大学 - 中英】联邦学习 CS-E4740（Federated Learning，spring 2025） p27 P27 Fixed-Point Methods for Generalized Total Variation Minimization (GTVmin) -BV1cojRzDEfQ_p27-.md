# 【阿尔托大学 - 中英】联邦学习 CS-E4740（Federated Learning，spring 2025） p27 P27 Fixed-Point Methods for Generalized Total Variation Minimization (GTVmin) -BV1cojRzDEfQ_p27-

![](img/b2c5b925a036cba0a572727e3a47cdd8_0.png)

Okay。So in the next in the next lecture。

![](img/b2c5b925a036cba0a572727e3a47cdd8_2.png)

I will present some federated learning algorithms that are optimization methods to solve this GTV minimization problem and。



![](img/b2c5b925a036cba0a572727e3a47cdd8_4.png)

One common idea or the one core idea behind all these algorithms is to formulate this optimization problem as a fixed point problem。



![](img/b2c5b925a036cba0a572727e3a47cdd8_6.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_7.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_8.png)

So it turns out there's quite convenient ways to translate an optimization problem like this into a fixed point equation with some fixed point operator。



![](img/b2c5b925a036cba0a572727e3a47cdd8_10.png)

So in the sense that whenever a vector or a collection of local model parameters。 So I will。

 I will stack those local model parameters， sometimes I will stack those local model parameters into a single long vector for notation reasons。

And we can then characterize a solution of GTV mean by a fixed point equation using some operator。

And as it turns out， this operator is not unique in general。 It's a design choice。

 So you can find for one and the same G T V G T minimization problem。 You can find very different。

 infinitely different choices for this fixed point operator。



![](img/b2c5b925a036cba0a572727e3a47cdd8_12.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_13.png)

So how， how do you like this approach， how how。How do you feel about translating an optimization problem into a fixed point equation。

Do you find， or do you think， why on earth are we doing this。

 Doesn't it make everything more complicated。Or do you have some intuition why this could be a good idea。



![](img/b2c5b925a036cba0a572727e3a47cdd8_15.png)

What is so nice about translating an optimization problem into a fixed point problem。



![](img/b2c5b925a036cba0a572727e3a47cdd8_17.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_18.png)

Yeah， so so there are some comments regarding the analysis so it can help with analyzing the problem or solving the problem。

 but from a computational perspective， when you want to solve some problem numerically you need an algorithm to solve it like gradient descent。

 So what is a very natural choice for an algorithm to solve such a fixed point equation。

 So you want to find a vector W hat。That satisfies W H equals coincides with operator F applied to W head。

 So how can， how can you solve such a fixed point equation。You just repeat it， you iterate it。

 and then what you get is a fixed point iteration。 and's that's what I love so much。

 So I fell in love with fixed point iterations a few years ago。

 and the law is still very active because once you managed to formulate your problem。

 whatever problem you have typically related to mathematics as a fixed point equation。

 you immediately almost immediately get a recipe for programming and algorithm。

 an numerical algorithm， which is a fixed point iteration。



![](img/b2c5b925a036cba0a572727e3a47cdd8_20.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_21.png)

And it turns out I really enjoy this sometimes it's a bit of a strange hobby though， to think about。

 tell me any algorithm that you know that you find cool。

 let's say back propagation or what other algorithms are there， Q learning。

 reinforcement learning algorithms and I'm almost always able to come up with a nice formulation as a fixed point iteration。



![](img/b2c5b925a036cba0a572727e3a47cdd8_23.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_24.png)

So， this is a very。General principle or design pattern for numeric algorithms。



![](img/b2c5b925a036cba0a572727e3a47cdd8_26.png)

Okay， so for example， when you look at this optimization problem for smooth loss functions。

You could use gradient descent。And it turns out what gradient descent does is it applies a fixed point operator。

 It does of， it's a fixed point iteration。 It's a fixed point iteration。

 gradientient des is a fixed point iteration with this specific choice of operator。

And this operator is parameterized， by the way， by Eta by the learning rate。

 So the learning rate is a parameter of a whole family of of operators， F Eta。

Who characterize solutions of this optimization problem 1。



![](img/b2c5b925a036cba0a572727e3a47cdd8_28.png)

嗯。

![](img/b2c5b925a036cba0a572727e3a47cdd8_30.png)

Yes， but this is， this is just one example。 There are other ways to formulate optimization problems as a fixed point equation。

 Does any one of you know other ways for， for more general optimization problems that are not necessarily differentiable。



![](img/b2c5b925a036cba0a572727e3a47cdd8_32.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_33.png)

But still convicts， or let's say， convicts。So let's say you want to minimize the sum of two functions or two components。

 which are both convets。

![](img/b2c5b925a036cba0a572727e3a47cdd8_35.png)

Then there's something called duality。So duality， convex duality provides。



![](img/b2c5b925a036cba0a572727e3a47cdd8_37.png)

Very clever ways to come up with such a fixed point characterization of convex optimization problems without the need of gradients。

 So you can formulate non smooth optimization problems also as fixed point equations。For example。

 they are called them primal dual optimality conditions。

Or they also go under the name KkD conditions。 So KkD conditions are also an example of a fixed point characterization of an optimization problem in particular if you have constraints。

 if you have constraints， then this gradient just using the gradient zero gradient condition doesn't work。

 you must somehow bring in the constraints and KkD conditions are a way to formulate a constraint optimization problem as a fixed point equation。



![](img/b2c5b925a036cba0a572727e3a47cdd8_39.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_40.png)

![](img/b2c5b925a036cba0a572727e3a47cdd8_41.png)