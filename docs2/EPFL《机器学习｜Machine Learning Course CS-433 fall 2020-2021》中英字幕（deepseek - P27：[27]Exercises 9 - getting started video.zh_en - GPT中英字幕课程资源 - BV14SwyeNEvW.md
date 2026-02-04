# EPFL《机器学习｜Machine Learning Course CS-433 fall 2020-2021》中英字幕（deepseek - P27：[27]Exercises 9 - getting started video.zh_en - GPT中英字幕课程资源 - BV14SwyeNEvW

![](img/ec25e3737b3891841a696ec6fc2619e2_0.png)

Hello， I'm Yermo and I will be your Lier this week and in today's exercise what we're going to be learning is a bit more about neural networks in particular we're going to be dropping a bit more on trying to see how back propagation works and some inner workings of the weight space of the neural networks。

 but before we see a bit of these exercise， the idea is that before what we saw is that how to use Pytorch to implement complex neural networks with many layers。

 complex loss functions， different activations， so PyTtorch is actually a very useful tool for both researchers and engineers that allows to abstract most of the most of the hard work that you need to do to compute these gradients of neural networks。

 but in today's exercise。We are going to try to do the hard work and it is important that we do this because if we implement back proag at least once in our life。

 this will help us understand a bit better how these neural networks work so the exercise of this week will consist of two parts a first part which is a bit more practical in which we are going to compute fit forward we implement a fit forward computations of simple single hidden layer neural network and the back propag as well and a second part in which we're going to to do a bit of analysis of these network。

So okay， in the first part of the exercise， we're going to be working with a very， very simple model。

 which consists of a simple neural network with one hidden layer with five neurons and an input layer with four dimensions。

And this neural network will be implementing a forward pass that will output one scalar y hat。

And so in the first exercise， what we ask you to do is just simply follow the computations in this network to get this Wi hat。

 so the first exercise consists of using a nuy so no Pythr this time implement the fit forward path of this neural network and this is basically just rewriting this equations in NI。

Now， in the notebook， what you will see is that first you will have to copy the code that you already have for the sigmoid from the logistic regression lecture in which we had the sigmoid and the gradient of the sigmoid。

And then。Implement a fit forward word pass。 And what you have is some simple test that allows you to see if you have implemented it correctly。

 So what were doing is we're giving some example weight values and some input vector。

 And if your function is implemented correctly。 then the scaler that you should get for this specific weight and this specific input should be close to this expected value。

Now， in the second part of the exercise， what we're going to be doing is just compute the gradient of this network with respect to the weights。

 which is what we need for training this new network。And in particular。

 we're going to do it for this specific trace of loss。

So the idea is that you're going to reproduce the EC steps that we have in the lectures for computing the backropag。

 which is nothing else but the chain rule on these loss over the weights in the network。

So the first part of the exercise will just consist of you developing the expression for the gradients first for the weights in the hidden layer and then for the weights in the first layers so from the input to the hidden layer and then from the hidden layer to the output。

And for doing this the only thing that you need to do is just apply the chain rule so you first take your loss and then here the Y hatt is basically the output of your network。

 so what you need to do is like compute the partial derivative of the loss with respect to Y hat then the partial derivative times the partial derivative of y hat with respect to to the weights and for doing this as you saw in class the easy way to go is again creating this variable Z1 that allows you to simplify a bitta computation so just be a bit careful with the computations and you should get it in the end。

So okay， once we have these expressions， what we ask you to do is to write again those expressions in NI and compute the back propag over this network and as we had before。

 we're going to give you some weight values as examples for this network。

And if everything goes correctly， you should get the right values for the gradient。

 so if you implement this function correctly， then your your test will pass and you will know that you have implemented things correctly。

Okay that is the practical part of of today's exercise the second part is a bit more theoretical in particular what we're going to see is that even though neural networks are actually very hard to analyze we can sometimes get some intuitions from modeling them with some of the tools that we have in class so in this exercise the setup consists of talking about an abstract neural network so we are not even the architecture of this neural network what we know at least is that we can write all the weights of this neural network into a vector W。

And what we're going to be investigating is a bit what are the properties of the neural network in the weight space。

 so the space of all possible weights。And for doing that。

 what we're going to do is assume some structure on the loss so as you know for neural networks。

 the loss landscape or the optimization is not complex。

 so it means that it's very very hard to analyze。But what sometimes researchers do to try to get some understanding of how this works is to approximate the loss as if it was convex at a given point and in particular what we will do is like say that we can approximate these loss as if it was quadratic around a certain point and the certain point that we would pick is actually the optimal point so this is nothing less than doing a taillor expansion of the loss around the optimal set of weights and what you see is that in this second order Tayloror expansion we don't have any gradient term and this is because we are assuming that we are around the optimal weights and the gradient at the optimalimum we know it would be zero so this taillor decomposition only has order two has only a quadratic term in terms of the hessian and the hessian here is just the secondary effect of the loss with respect to the weights so it's a matrix。

And so the exercise asks you what would happen if now we augment these loss with some regularization term that looks similar to the rich regression term。

And the question is， if we just add here this regularization， how will value start changing？

And now the nice thing about this assumption is that we have abstracted all the non convexity of the program into something that is indeed a convex loss。

At least when you're close to W star， and we can use the complex tools that we have learned and we can derive the exact minimum of this quadratic function。

And what you will see is that once you derive that minimum by making the gradient equal to0。

 you will see that the solution will have this form。

 so the solution of the regularized problem will be the same solution as you would have if you didn't have the regularization term times sum matrix and this matrix will depend on the value of mu。

 but will also depend on the egg and deposition of the hesian。

So once we have derived this expression， the next part of the exercise just deals about trying to understand a bit the intuition behind this term。

 and the first part will go into basically analyzing the eigenvalues of this matrix。

Which we ask you to see that。Are actually a diagonal matrix with re scale liigenvalues by this factor of mu。

So you need to just derive this expression for each of the of the elements in this matrix and you will see that these are the actual solutions and once we have seen this this。

This final exercise just tries to understand what this means in a practical case。 So in particular。

 what we will assume is that we have different eigenvalues in the in the hesian and the question is。

Depending on the size of the secondigenvalue， how much will the。

The regularization term effect and in particular， what we ask you to show is that for the largest eigenvalues。

 nothing would essentially happen， so we would get more or less the same component of the vector in that eigen space。

 but the regularization would really kick in in the directions where you have very small eigenvalues So in this exercise。

 which is want you to to show this more or less formally that this is indeed the case and basically build an intuition around this concept。

So， okay， that's。All about this week's exercise， if you have any questions just feel free to do it in the chat。

 thank you very much。

![](img/ec25e3737b3891841a696ec6fc2619e2_2.png)