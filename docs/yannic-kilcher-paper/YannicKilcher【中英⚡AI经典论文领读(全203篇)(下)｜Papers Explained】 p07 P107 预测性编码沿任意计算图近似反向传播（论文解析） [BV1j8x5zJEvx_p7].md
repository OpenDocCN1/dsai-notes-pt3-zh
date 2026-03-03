# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p07 P107 预测性编码沿任意计算图近似反向传播（论文解析） [BV1j8x5zJEvx_p7]

Hi there。 This is an LSTM cell or the computation graph of an LSTM cell。 It is pretty hideous。

 as you can see。 but what I'm about to show you is even more hideous。

 This is the computation graph of the L LSTM cell augmented with error units evincing the connectivity scheme of the predictive coding algorithm。

 So you may see that there are appearing these little red arrows right here。

 that are so-called error units， and these are necessary for an algorithm called predictive coding which is an algorithm that is a biologically plausible alternative to backpro and that's what we're going to look at today。

 specifically this paper， As you can see， it is quite a thorough paper it is called predictive coding approximates back prop along arbitrary。

😊。

![](img/dfb4f60aeefe42e6ccf2c0b558003717_1.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_2.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_3.png)

ut graphs and have you ever heard a more descriptive title of what's in a paper So the authors are Barron Millage。

 Alexander Chance and Christopher Buckley this paper as the title says it looks at this predictive coding algorithm and it shows that this approximates backpro and we'll see that this approximates is in terms of there is an inner iteration in the predictive coding algorithm and the more you run that and under certain assumptions。

 this approximates the back propagation algorithm and the new thing in this paper is a long arbitrary computation graphs so there have been papers before describing predictive coding this algorithm in various subsettings like fully connected layers and so on the fact that it approximates back。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_5.png)

There， however， this paper shows that that's actually the case for arbitrary computation graphs under certain assumptions。

 predictive coding App the back propagation algorithm。 Why is this important。

 Because the back propagation algorithm isn't exactly biologically plausible so。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_7.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_8.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_9.png)

They say right here in the abstract back propagation of error or short backdrop is a powerful algorithm for training machine learning architectures through end to end differentiation recently has been shown that backpro in multilayer perceptron can be approximated using predictive coding。

 a biologically plausible process theory of cortical computation。

 which relies solely on local and heavyian updates。

 So the difference between back propagation and predictive coding is exactly this point that predictive coding relies solely on local and heavyian updates。

 and the keyword I think， is local。 So in in a neural network， you have some sort of input X。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_11.png)

And you ship it through many layers， layer， layer， layer， layer。 And then you have an output Y hat。

 And then you compare that output using a some kind of loss function with your。

With your true output that you want。 And then there is this backwards phase right here。

 And in this backwards phase， you want to derive gradients for each of the layers weights。

 So each of these layers has a weight associated with it， I'm not going into Greek letters again。

 So this is W， I don't know。 W3 W2 is here and so on。

 So what you want to get out as you want to say how do I need to change W。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_13.png)

In order to change my loss for the better， so what you want is this gradient。

 this gradient right here and back propagation does a very natural decomposition namely if you have these hidden states in here。

 so x is transformed to hidden state H0 H1 H2 H3， so that is the latent representation， if you want。

 for example， weight if you want to know how to change weight， or let's say weight 2。

The back propagation algorithm decomposes this into the derivative。

 according to the hidden state at layer 2， multiplied by the derivative of the hidden state by the weight。

 so this is what you would sort of learn in a beginner's course of deep learning。

 this decomposition and of course in this part right here。This part decomposes into。

Dll L for H3 and then H3 by H2。 So this is the standard back propagation algorithm you can clearly see in the formula。

 the computation graph。It goes from the L it flows backward to H3 right so to H3 and then from H3 it flows to H2 and then from H2 it flows to W2 so that's sort of the flow of the gradient backwards through the network and that's pretty cool because it allows us to run gradient descent on arbitrary computation graphs。

 which ultimately enable deep learning， including frameworks like Tensorflow ptorrch or the older ones like Theionno or Luatorrch even autograd things like this。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_15.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_16.png)

It's pretty cool， but it's not really plausible in the brain because neurons are not bidirectional like this。

 neurons generally''m I'm not a neuroscientist or anything。

 but these neurons they have some sort of soma and then you have this axon and then these axon goes into many different of these synapses to to its children and the kind of docs onto the somas of or on the dendrites of the other neurons and this is not bidirectional。

 This is generally here there's unidirectional signal in this direction and there are so-called feedback connections So from these neurons to the dendrites of this neuron but you cannot really send this gradient information you cannot send this sort of vector gradient information and you cannot do so in this sort of sweep so。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_18.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_19.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_20.png)

In the brain， it's probably not the case that the layer propagates forward and then sort of waits for a synchronized backward pass across the network in order to update itself。

 all of this needs to happen much more in parallel much more local so that things are only considering local information of global information right here。

 for example， you need the global gradient in the update of W2 and you need to have that backproagated that's not plausible so predictive coding comes along And today well look mainly actually at how predictive coding works。

 of course this paper is about extending it to arbitrary computation graphs。

 which is cool because they do predictive coding for CNNns。

 RnNs and even LSTMs and if you look at their， so let's first jump into the numerical results。

 If you look at their numerical results， they have lots of these plots where they basically show。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_22.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_23.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_24.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_25.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_26.png)

We did this network， we train it with backpro and then we train it with predictive coding and the lines are just the same and so it's pretty convincing evidence even if you go super duper deep。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_28.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_29.png)

And they do， I think Rn ends with up to 100 layers or 100 time steps unrolled。

 So the empirical evidence that predictive coding approximates backpro is certainly here and we'll look at what predictive coding is how it works and。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_31.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_32.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_33.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_34.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_35.png)

How it works along arbitrary computation graphs， so that's today's paper and I hope you enjoy it if you do don't hesitate to share it out and subscribe。

All right。Alright， so this graphic right here compares the two algorithms in principle On top very much what I've said so far。

 the back propagation algorithm somehow has this signal， it propagates forward。

 and then at some point， there is an output。 And if you want to train it， there is a label。

 you compare that to the output that will give you an error。 and by deri a gradient。

 and that gradient is now back propagated according to the chain rule。

 According to the back propagation algorithm。 you can see it's very much what I've drawn。

 the predictive coding algorithm is a little bit different。

 and it's honestly not super clear from this graphic right here。

 I find this graphic to be to be a bit confusing。 but you can see， first of all。

 there is this introduction of these。

![](img/dfb4f60aeefe42e6ccf2c0b558003717_37.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_38.png)

![](img/dfb4f60aeefe42e6ccf2c0b558003717_39.png)

Of these error nodes in the computation graph right here。

 and there also seems to be the introduction of these new hat， whatever that is。

So so we're sort of first going to dive into the math and then we're going to check out how the algorithm works as such。



![](img/dfb4f60aeefe42e6ccf2c0b558003717_41.png)