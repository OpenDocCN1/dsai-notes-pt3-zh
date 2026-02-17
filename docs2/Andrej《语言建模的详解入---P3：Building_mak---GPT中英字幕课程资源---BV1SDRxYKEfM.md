# Andrej《语言建模的详解入门：构建 makemore》中英字幕（deepseek-R1 - P3：Building makemore Part 3_ Activations & Gradients, BatchNorm.zh_en - GPT中英字幕课程资源 - BV1SDRxYKEfM

H， everyone。Today， we are continuing our implementation of make more。Now in the last lecture。

 we implemented the multiier perceptron along the lines of Benjotel 2003 for character level language modeling。

 so we followed this paper， took in a few characters in the past。

 and used an MLP to predict the next character in a sequence。



![](img/88dd9899d3a9ef459d32c32418af4090_1.png)

![](img/88dd9899d3a9ef459d32c32418af4090_2.png)

So what we'd like to do now is we'd like to move on to more complex and larger neural networks like recur neural networks and their variations like that grew。

 LSTM and so on。Now， before we do that， though， we have to stick around the level of motium perron for a bit longer。

And I'd like to do this， because I would like us to have a very good intuitive understanding of the activations in the neural nut during training and especially the gradients that are flowing backwards and how they behave and what they look like。

 This is going to be very important to understand the history of the development of these architectures。

😊，Because we'll see that recurren neural networks， while they are very expressive in that they are a universal approximator and can。

 in principle， implement all the algorithms， we'll see that they are not very easily optimizable with the first order gradient based techniques that we have available to us and that we use all the time。

And the key to understanding why they are not optimizable easily is to understand the the activations and the gradients and how they behave during training。

 And we'll see that a lot of the variants since recurren neural networks have tried to improve that situation。

 And so that's the path that we have to take。 And let's go started。

 So the starting code for this lecture is largely the code from before。

 But I've cleaned it up a little bit。

![](img/88dd9899d3a9ef459d32c32418af4090_4.png)

So you'll see that we are importing all the torch and matplet utilities。

 We're reading in the words just like before。 These are8 example words。

 There's a total of 32000 of them。 Here's a vocabulary of all the lowercase letters and the special dot token。



![](img/88dd9899d3a9ef459d32c32418af4090_6.png)

![](img/88dd9899d3a9ef459d32c32418af4090_7.png)

![](img/88dd9899d3a9ef459d32c32418af4090_8.png)

Here we are reading the dataset set and processing it and creating three splits， the train。

 dev and the test split。

![](img/88dd9899d3a9ef459d32c32418af4090_10.png)

Now in MLP， this is the identical same MLP except you see that I removed a bunch of magic numbers that we had here。

 and instead we have the dimensionality of the embedding space of the characters and the number of hidden units in the hidden layer。

 and so I've pulled them outside here so that we don't have to go in and change all these magic numbers all the time。



![](img/88dd9899d3a9ef459d32c32418af4090_12.png)

With the same neural net with 11000 parameters that we optimize now over 200000 steps with a batch size of 32。

 and you'll see that I I refactored the code here a little bit， but there are no functional changes。

 I just created a few extra variables， a few more comments， and I removed all the magic numbers。

 and otherwise is the exact same thing。

![](img/88dd9899d3a9ef459d32c32418af4090_14.png)

![](img/88dd9899d3a9ef459d32c32418af4090_15.png)

Then when we optimize， we saw that our loss looked something like this。



![](img/88dd9899d3a9ef459d32c32418af4090_17.png)

We saw that the train and Val loss were about 2。16 and so on。

Here I refactored the code a little bit for the evaluation of arbitrary splits。

 so you pass in a string of which split you'd like to evaluate， and then here。

 depending on train Val or test， I index in and I get the correct split。

 and then this is the for pass of the network and evaluation of the loss in printing it。

So just making it nicer。One thing that you'll notice here is。I am using a decorator torch donograd。

 which you can also look up and read the documentation of But basically what this decorator does on top of a function is that whatever happens in this function。

Is seen by a torch to never require an ingredients。

 So it will not do any of the bookke that it does to keep trackable the gradients in anticipation of an eventual backward pass。

It's almost as if all the tensor that get created here have a requires grad of false。

And so it just makes everything much more efficient because you're telling Torch that I will not call that backward on any of this computation。

 and you don't need to maintain the graph under the hood。So that's what this does。

 and you can also use a context manager with Torchdo Nograd， and you can look those up。



![](img/88dd9899d3a9ef459d32c32418af4090_19.png)

![](img/88dd9899d3a9ef459d32c32418af4090_20.png)

Then here we have the sampling from a model， just as before， just a poor pass of a neural nut。

 getting the distribution， sampling from it， adjusting the context window and repeating until we get the special and token。

 And we see that we are starting to get much nicer looking words sample from the model。

 It's still not amazing。 And they're still not fully name like。

 But it's much better than when we had to with the bigra model。😊。



![](img/88dd9899d3a9ef459d32c32418af4090_22.png)

So that's our starting point。 Now， the first thing I would like to scrutinize is the initialization。



![](img/88dd9899d3a9ef459d32c32418af4090_24.png)

I can tell that our network is very improperly configured at initialization。

 and there's multiple things wrong with it。 But let's just start with the first one。

Look here on the 0 iteration， the very first iteration。We are recording a loss of 27。

 and this rapidly comes down to roughly one or two or so。

 so I can tell that the initialization is almost mess up because this is way too high。

In training of neural nets， it is almost always the case that you will have a rough idea for what loss to expect at initialization。

 and that just depends on the loss function and the problem setup up。In this case。

 I do not expect 27， I expect a much lower number and we can calculate it together。Basically。

 at initialization， what we'd like is that there's 27 characters that could come next for any one training example。

At initialization， we have no reason to believe any characters to be much more likely than others。

And so we'd expect that the probability distribution that comes out initially is a uniform distribution assigning about equal probability to all the 27 characters。

So basically what we'd like is the probability for any character。Would be roughly1 over 27。

That is the probability we should record。 And then the loss is the negative log probability。

 So let's wrap this in a tensor。And then then we can take the log of it。

 And then the negative log probability is the loss we would expect。Which is 3。29， much。

 much lower than 27。And so what's happening right now is that at initialization。

 the neural nu is creating probability distributions that are all messed up。

 Some characters are very confident， and some characters are very not confident。

And then basically what's happening is that the network is very confidently wrong。

And that's what makes it。Record very high loss。 So here's a smaller four dimensional example of the issue。

 Let's say we only have four characters， and then we have logits that come out of the neural land。

 and they are very， very close to 0。

![](img/88dd9899d3a9ef459d32c32418af4090_26.png)

Then when we take the softm of all zeros， we get probabilities。 there are a diffuse distribution。

So sums to one and is exactly uniform。And then in this case， if the label is say2。

 it doesn't actually matter if this， if the label is 2 or 3 or 1 or 0。

 because it's a uniform distribution， we're recording the exact same loss in this case，1。38。

 So this is the loss we would expect for a four dimensional example。And I can see， of course。

 that as we start to manipulate these logits， we're going to be changing the loss here。

So it could be that we lock out and by chance。 This could be a very high number， like， you know。

5 or something like that。 Then in that case， we'll record a very low loss because were assigning the correct probability at initialization by chance to the correct label。

Much more likely， it is that some other dimension will have a high logicit。

 And then what will happen is we start to record much higher loss。

And what can happen is basically the logits come out like something like this， you。

 and they take on extreme values and we record really high loss。For example。

 if we have torch do random of four。 So these are uniform。 So these are normally distributed numbers。

For loop。Then here we can also print the logits。Probilities that come out of it。 and loss。

And so because these logits are near 0 for the most part， the loss that comes out is， is okay。



![](img/88dd9899d3a9ef459d32c32418af4090_28.png)

But suppose this is lifetime times 10 no。You see how， because these are more extreme values。

 it's very unlikely that you're going to be guessing though correct。Bucket。

 and then you are confidently wrong and recording very high loss。If your los are coming up。

 even more extreme。You might get extremely insane losses like infinity， even at initialization。嗯。

So basically， this is not good。 And we want the load just to be roughly 0。

When the network is initialized， in fact， thelogits can don't have to be just 0。

 They just have to be equal。 So， for example， if all thelogits are one。

Then because of the neuroization inside the softm， this will actually come out okay。But by symmetry。

 we don't want it to be any arbitrary positive or negative number。

 We just want it to be all zeros and record the loss that we expect at initialization。

 So let's not concretely see where things go wrong in our example。



![](img/88dd9899d3a9ef459d32c32418af4090_30.png)

Here we have the initialization。

![](img/88dd9899d3a9ef459d32c32418af4090_32.png)

Let me realize in your。And here， let me break after the very first iteration。

 So we only see the initial loss， which is 27。So that's way too high。 and intuitively。

 now we can expect the variables involved， and we see that the loits here if we just print some of these。

We just print the first row， we see that the loads take on quite extreme values。

And that's what's creating the fake confidence in incorrect answers and makes the loss。Get very。

 very high。 So these lotus should be much， much closer to0。



![](img/88dd9899d3a9ef459d32c32418af4090_34.png)

So now let's think through how we can achieve logits coming out of this neural nut to be more closer to 0。



![](img/88dd9899d3a9ef459d32c32418af4090_36.png)

You see here that Los are calculated as the hidden states multiplied by W2 plus B2。So first of all。

 currently we're initializing B2 as random values of the right size。But。Because we want roughly zero。

 we don't actually want to be adding a bias of random numbers， so in fact。

 I'm going to add a time to0 here to make sure that B2 is just basically zero at initialization。

And second， this is H multiplied by Doli2。 So if we want Los to be very， very small。

Then we would be multiplying W2 and making that smaller。So for example， if we scale down W2 by 0。1。

 all the elements。

![](img/88dd9899d3a9ef459d32c32418af4090_38.png)

Dify。Due again， just the very first situation， you see that we are getting much closer to what we expect。

 So roughly what we want is about 3。29。 This is 4。2。I can make this maybe even smaller。



![](img/88dd9899d3a9ef459d32c32418af4090_40.png)

3。32。 Okay， so we're getting closer and closer now。You're probably wondering。

 can we just set this to zero？

![](img/88dd9899d3a9ef459d32c32418af4090_42.png)

Then we get， of course， exactly what we're looking for at an initialization。



![](img/88dd9899d3a9ef459d32c32418af4090_44.png)

And the reason I don't usually do this is because I'm very nervous。

 and I'll show you in a second why you don't want to be setting ws or weights of a neural net exactly to zero。

 you usually want it to be small numbers instead of exactly zero。



![](img/88dd9899d3a9ef459d32c32418af4090_46.png)

For this output layer in the specific case， I think it would be fine。

 but I'll show you in a second where things go wrong very quickly。 if you do that。

 So let's just go with 0。01。

![](img/88dd9899d3a9ef459d32c32418af4090_48.png)

In that case， our loss is close enough。But has some entropy。 It's not exactly 0。

 It's got some little entropy， and that's used for symmetry breaking， as we'll see in a second。

Thelogits are now coming out much closer to 0， and everything is well and good。



![](img/88dd9899d3a9ef459d32c32418af4090_50.png)

So if I just erase these and I'd now take away the brake statement。



![](img/88dd9899d3a9ef459d32c32418af4090_52.png)

We can run the optimization with this new initialization。 And let's just see what。



![](img/88dd9899d3a9ef459d32c32418af4090_54.png)

Losses we record。 Okay， so I'll let it run and you see that we started off good。

 and then we came down a bit。

![](img/88dd9899d3a9ef459d32c32418af4090_56.png)

The plot of the loss now doesn't have this hockey shape appearance。

Because basically what's happening in the hockey stick， the very first few iterations of the loss。

 what's happening during the optimization is the optimization is just squashing down the logits。

 and then it's rearranging the logits。So basically。

 we took away this easy part of the loss function where just the weights were just being shrunk down。

And so therefore we don't get these easy gains in the beginning。

 and we're just getting some of the hard gains of training the actual neural nut。

 and so there's no hockey stick appearance。

![](img/88dd9899d3a9ef459d32c32418af4090_58.png)

![](img/88dd9899d3a9ef459d32c32418af4090_59.png)

So good things are happening in that both number one， loss initialization is what we expect。



![](img/88dd9899d3a9ef459d32c32418af4090_61.png)

And the loss doesn't look like a hockey stick， and this is true for any neural that you might train and something to look out for。



![](img/88dd9899d3a9ef459d32c32418af4090_63.png)

And second， the loss of the amount is actually quite a bit improved。

 Unfortunately I erased what we had here before。 I believe this was 2。12 and this was 2。16。

 so we get a slightly improved result and the reason for that is because we're spending more cycles。

 more time optimizing the neural net actually instead of just spending the first several thousand iterations probably just squashing down the weights。



![](img/88dd9899d3a9ef459d32c32418af4090_65.png)

Because they are so way too high in the beginning andization。



![](img/88dd9899d3a9ef459d32c32418af4090_67.png)

So something to look out for and that's number one。 Now let's look at the second problem。

 let me reinitialize our neural lot and let me reintroduce the brake statement。



![](img/88dd9899d3a9ef459d32c32418af4090_69.png)

![](img/88dd9899d3a9ef459d32c32418af4090_70.png)

So we have a reasonable initial loss。 So even though everything is looking good on the level of the loss and we get something that we expect。

 there's still a deeper problem lurk inside this neural net and its initialization。



![](img/88dd9899d3a9ef459d32c32418af4090_72.png)

So the logicits are now O。 The problem now is with the values of H。



![](img/88dd9899d3a9ef459d32c32418af4090_74.png)

The activations of the hidden states。Now， if we just visualize this vector， answered this tensor H。

 it's kind of hard to see。 But the problem here， roughly speaking is you see how many of the elements are one or negative  one。



![](img/88dd9899d3a9ef459d32c32418af4090_76.png)

Now recall that torch do 10 H。 the 10H function is a squashing function。 It takes arbitrary numbers。

 and it squashes them into a range of negative  one and one， and it does so smoothly。

So let's look at the histogram of H to get a better idea of the distribution of the valleys inside this tensor。



![](img/88dd9899d3a9ef459d32c32418af4090_78.png)

We can do this， first。Well， we can see that H is 32 examples and 200 activations。 in each example。

 we can view it as negative one to stretch it out into one large vector。

And we can then call tool list。To convert this into one large Python list of floats。

And then we can pass this into P O T dot hist for histogram。 And we say we want 50 bins。

 and semicolon to suppress a bunch of output we don't want。



![](img/88dd9899d3a9ef459d32c32418af4090_80.png)

So we see this histogram， and we see that most of the values by far take on value of native one and one。

 So this 10 H is very， very active。And we can also look at。Basically， why that is。

We can look at the pre activationivations that feed into the10 H。

And we can see that the distribution of the pre activationivations are is very， very broad。

 These take numbers between negative 15 and 15， and that's why in a torture of 10 age。

 everything is being squashed and capped to be in the range of negative 1 and1。

 and lots of numbers here take on very extreme values。Now， if you are new to neural networks。

 you might not actually see this as an issue， but if you are vel versed in the dark arts of back propagation and then have an intuitive sense of how these gradients flow through a neural net。

 you are looking at your distribution of 10H activations here and you are sweating。

So let me show you why we have to keep in mind that during bad propagation。

 just like we saw in micrograd， we are doing backward path。

 starting at the loss and flowing through the network backwards。



![](img/88dd9899d3a9ef459d32c32418af4090_82.png)

In particular， we're going to back gate through this Tor dot 10h。

And this layer here is made up of 200 neurons for each one of these examples。

And it implements an element twice 10h， so let's look at what happens in 10H in the backward pass。



![](img/88dd9899d3a9ef459d32c32418af4090_84.png)

We can actually go back to our previous micrograd code in the very first lecture and see how we implemented10H。

We saw that the input here was x， and then we calculate T， which is the 10 H of x。So that's T。

 and T is between negative 1 and 1。 It's the output of the 10h。And then in the backward pass。

 how do we back propagate through a 10 inch？We take out that grad。And then we multiply it。

 This is the chain rule with the local gradient， which took the form of 1 minus t squared。

So what happens if the outputs of your 10 H are very close to negative1 or 1。

 If you plug into t equals 1 here， you're going to get0 multiplying out that grad。

No matter what Atalgrad is， we are killing the gradient。

 and we're stopping effectively the back propagation through this10age unit。Similarly。

 when t is negative1， this will again become0 and out that garage just stops。And intuitively。

 this makes sense because this is a tenation your own。

And what's happening is if its output is very close to one， then we are in the tail of this1age。

And so changing basically the input。Is not going to impact the output of the 10 H too much because it' it's so。

 it's in the flat region of the 10 H。 And so， therefore， there's no impact on the loss。And so indeed。

 the， the weights and the biases along with this 10 H neuron。

 do not impact the loss because the output of the10H unit is in the flat region of the10 H。

 and there's no influence。 We can。 We can be changing them whatever we want。 However we want。

 and the loss is not impacted。 That So that's another way to justify that Indeed。

 the gradient would be basically 0。 It vanishes。Indeed， when t equals 0。

We get one times at that grad。 So when the 10 H takes on exactly value of 0。

Then out that grad is just passed through。So basically what this is doing。

 right is if t is equal to 0， then the 10h unit is sort of inactive。And gradient just passes through。

 But the more you are in the flat tails， the more the gradient is squashed。So in fact。

 you'll see that the gradient flowing through10age can only ever decrease and the amount that it decreases is proportional through a square here。

 depending on how far you are in the flat tails of this10age。

And so that's kind of what's happening here。 And through this。

 the concern here is that if all of these outputs H are in the flat regions of negative11。

 then the gradients that are flowing through the network will just get destroyed at this layer。



![](img/88dd9899d3a9ef459d32c32418af4090_86.png)

Now， there is some redeeming quality here and that we can actually get a sense of the problem here as follows。

I wrote some code here。And basically， what we want to do here is we want to take a look at H。

 take the the absolute value and see how often it is in the in a flat region。 So say。



![](img/88dd9899d3a9ef459d32c32418af4090_88.png)

Gra than 。99。And what you get is the following。 And this is a boolean tensor。

 So in the boolean tensor， you get a white， if this is true and a black， if this is false。

And so basically， what we have here is the 32 examples and the 200 hidden neurons。

 And we see that a lot of this is white。 And what that's telling us is that all these 10 H neurons were very。

 very active， and they're in a flat tail。And so in all these cases。

 the backward gradient would get destroyed。

![](img/88dd9899d3a9ef459d32c32418af4090_90.png)

Now， we would be in a lot of trouble if。For for any one of these 200 neurons。

 if it was the case that the entire column is white。Because in that case。

 we have what's called a dead neuron。 And this could be a 10 Hch neuron where the initialization of the weights in the biases could be such that no single example ever activates this 10 H in the sort of active part of the 10 H。

 If all the examples land in the tail， then this neuron will never learn。 It is a dead neuron。

And so just scrutinizing this and looking for columns of completely white。

 we see that this is not the case。 so I don't see a single neuron that is all of you know white。

And so therefore， it is the case that for every one of these 10 H neurons。

We do have some examples that activate them in the active part of the10 H。

 And so some gradients will flow through， and this neuron will learn。

 and the neuron will change and it will move and it will do something。



![](img/88dd9899d3a9ef459d32c32418af4090_92.png)

But you can sometimes get it yourself in cases where you have dead neurons and the way this manifests is that for a10 inch neuron this would be when no matter what inputs you plug in from your data set。

 this10hch neuron always fires completely one or completely negative one。

 and then it will just not learn because all the gradients will be just zero that。



![](img/88dd9899d3a9ef459d32c32418af4090_94.png)

![](img/88dd9899d3a9ef459d32c32418af4090_95.png)

This is true not just for 10 H， but for a lot of other nonlinearities that people use in neural networks。

 So we certainly use10 H a lot， but sigmoid will have the exact same issue because it is a squashing neuron。

 And so the same will be true for sigmoid， but。But you know。

 basically the same will actually applied to signaloid。The same will also apply to a roll。

So Relu has a completely flat region here， below 0。So if you have a rather neuron。

 then it is a pass through， if it is positive and if the pre activationiv is negative。

 it will just shut it off since the region here is completely flat then during back propagation。

 this would be exactly zeroing out the gradient。

![](img/88dd9899d3a9ef459d32c32418af4090_97.png)

Like all of the gradientding would be set exactly to 0 instead of just like a very。

 very small number， depending on how positive or negative T is。



![](img/88dd9899d3a9ef459d32c32418af4090_99.png)

And so you can get， for example， a dead reonnen and a dead renen would basically look like。

Basically what it is is if a neuron with a reon nonlinearity never activates。

So for any examples that you plug in in the dataset set， it never turns on。

 It's always in this flat region。T thissreella neuron is a dead neuron。

 Its weights and bias will never learn。 They will never get a gradient because the neuron never activated。

And this can sometimes happen at initialization because the weights and advisees just make it so that by chance。

 some neurons are just forever dead。But it can also happen during optimization。

 If you have like a too high of learning rate， for example。

 sometimes you have these neurons that gets too much of a gradient and they get knocked out off the data manifold。

And what happens is that from then on， no example ever activates this neuron。

 so this neuron remains dead forever， so it's kind of like a permanent brain damage in a mind of a network。

And so sometimes what can happen is if your learning rate is very high。

 for example and you have a neural net with re neurons。

 you train the neural net and you get some last loss。 But then actually。

 what you do is you go through the entire training set， and you forward your examples。

 and you can find neurons that never activate。 They are dead neurons in your network。

 And so those neurons will never turn on。 And usually what happens is that during training。

 these re neurons are changing， moving， et cetera。 And then because of a high gradient somewhere by chance。

 they get knocked off。 And then nothing ever activates them。 And from then on， they are just dead。

So that's kind of like a permanent brain damage that can happen to some of these neurons。

These other non nonlinearities， like Liki Blu， will not suffer from this issue as much because you can see that it doesn't have flat tails。

 you'll almost always get gradients。And Ilu is also fairly frequently used。

 it also might suffer from this issue because it has flat parts。



![](img/88dd9899d3a9ef459d32c32418af4090_101.png)

So that's just something to be aware of and something to be concerned about。 And in this case。

 we have way too many activations H that take on extreme values。

 And because there is no column of white， I think we will be okay。

 and indeed the network optimizes and gives us a pretty decent loss。



![](img/88dd9899d3a9ef459d32c32418af4090_103.png)

![](img/88dd9899d3a9ef459d32c32418af4090_104.png)

But it's just not optimal。 And this is not something you want， especially during initialization。

 And so basically what's happening is that this H pre activation that's flowing to 10 H。



![](img/88dd9899d3a9ef459d32c32418af4090_106.png)

![](img/88dd9899d3a9ef459d32c32418af4090_107.png)

It's， it's too extreme。 It's too large。 It's creating very It's creating a distribution that is too saturated in both sides of the 10 H。

 And it's not something you want because it means that there's less training for these neurons because they update less frequently。

 So how do we fix this。

![](img/88dd9899d3a9ef459d32c32418af4090_109.png)

![](img/88dd9899d3a9ef459d32c32418af4090_110.png)

Well， H pre activation is。Mmpcat， which comes from C。 So these are uniform Gaussian。

But then multiply by w1 plus B1。 And H pre act is too far off from 0， and that's causing the issue。

 So we want this pre activationivation to be closer to 0。 very similar to what we had with Los。



![](img/88dd9899d3a9ef459d32c32418af4090_112.png)

So， here。We want actually something very， very similar。Now。

 it's okay to set the biases to very small number。 We can either multiply by 0，0。

1 to get like a little bit of entropy。 I sometimes like to do that， just so that。

There is like a little bit of variation and diversity in the original initialization of these 10 H neurons。

 And I find in practice that that can help optimization a little bit。

And then the weights we can also just like squash。 So let's multiply everything by 。1。



![](img/88dd9899d3a9ef459d32c32418af4090_114.png)

Let's rerun the first batch。

![](img/88dd9899d3a9ef459d32c32418af4090_116.png)

And now let's look at this。 And well， first， let's look here。



![](img/88dd9899d3a9ef459d32c32418af4090_118.png)

You see now， because we multiply w by 。1， we have a much better histogram。

 And that's because the pre activationivations are now between negative 1。5 and 1。5。 And this。

 we expect much much less white。

![](img/88dd9899d3a9ef459d32c32418af4090_120.png)

![](img/88dd9899d3a9ef459d32c32418af4090_121.png)

Okay， there's no white。

![](img/88dd9899d3a9ef459d32c32418af4090_123.png)

So basically that's because there are no neurons that saturated above 0。99 in either direction。

 So this is actually a pretty decent place to be。

![](img/88dd9899d3a9ef459d32c32418af4090_125.png)

![](img/88dd9899d3a9ef459d32c32418af4090_126.png)

Maybe we can go up a little bit。Sorry， I am I changing W1 here， maybe we can go to 02。



![](img/88dd9899d3a9ef459d32c32418af4090_128.png)

Okay， so maybe something like this is a nice distribution。



![](img/88dd9899d3a9ef459d32c32418af4090_130.png)

So maybe this is what our initialization should be。 So let me now erase。



![](img/88dd9899d3a9ef459d32c32418af4090_132.png)

This。And let me， starting with initialization。

![](img/88dd9899d3a9ef459d32c32418af4090_134.png)

Let me run the full optimization without the break。



![](img/88dd9899d3a9ef459d32c32418af4090_136.png)

And let's see what we get。 Okay， so the optimization finished and I rebraend the loss。

 and this is the result that we get。 And then just as a reminder。

 I put down all the losses that we saw previously in this lecture。



![](img/88dd9899d3a9ef459d32c32418af4090_138.png)

So we see that we actually do get an improvement here， and just as a reminder。

 we started off with a validation loss of 2。17 when we started。

By fixing the softmax being confidently wrong， we came down to 2。13。

 and by fixing the 10H layer being way too saturated， we came down to 2。10。

And the reason this is happening， of course， is because our initialization is better。

 and so we're spending more time doing productive training instead of。



![](img/88dd9899d3a9ef459d32c32418af4090_140.png)

Not very productive training because our gradients are set to zero and we have to learn very simple things like the overconfidence of the softmax in the beginning。

 and we're spending cycles just like squashing down the weight matrix。



![](img/88dd9899d3a9ef459d32c32418af4090_142.png)

![](img/88dd9899d3a9ef459d32c32418af4090_143.png)

So this is illustrating basically initialization and its impacts on performance just by being aware of the internals of these neural nets and their activationctuas and their gradients。



![](img/88dd9899d3a9ef459d32c32418af4090_145.png)

Now， we're working with a very small network。 This is just one layer multi layer perception。

 So because the network is so shallow， the optimization problem is actually quite easy and very forgiving。

 So even though our initialization was terrible， the network still learned eventually。

 it just got a bit worse result。 This is not the case in general， though。

 once we actually start working with much deeper networks that have say 50 layers。

 things can get much more complicated。 And these problems stack up。



![](img/88dd9899d3a9ef459d32c32418af4090_147.png)

And so you can actually get into a place where the network is basically not training at all if your initialization is bad enough and the deeper your network is and the more complex it is。

 the less forgiving it is to some of these errors and so something to be definitely be aware of and something to scrutinize。

 something to plot and something to be careful with and。



![](img/88dd9899d3a9ef459d32c32418af4090_149.png)

Yeah， okay， so that's great that that worked for us。

 But what we have here now is all these magic numbers like 02。 Like。

 where do I come up with this and how am I supposed to set these if I have a large neural that with lots and lots of layers。

😊。

![](img/88dd9899d3a9ef459d32c32418af4090_151.png)

And so obviously no one does this by hand， there's actually some relatively principled ways of setting these scales that I would like to introduce to you now。



![](img/88dd9899d3a9ef459d32c32418af4090_153.png)

So let me paste some code here that Ive prepared just to motivate the discussion of this。



![](img/88dd9899d3a9ef459d32c32418af4090_155.png)

So what I'm doing here is we have some random input here X that is drawn from a Gaussian。

 and there's 1000 examples that are 10 dimensional。

 and then we have a weighting layer here that is also initialized using Gaussian。

 just like we did here。

![](img/88dd9899d3a9ef459d32c32418af4090_157.png)

And we these neurons in the hidden layer look at 10 inputs。

 and there are 200 neurons in the hidden layer。And then we have here， just like here， in this case。

 the multiplication x multiplied by W to get the pre activationivations of these neurons。



![](img/88dd9899d3a9ef459d32c32418af4090_159.png)

And basically， the analysis here looks at， okay， suppose these are unit from Gaussian and these weights are unit from Gaussian。

 if I do x times w and we forget for now the bias and the non nonlinearity。

Then what is the mean andern deviation of these Gausss？



![](img/88dd9899d3a9ef459d32c32418af4090_161.png)

So in the beginning here， the input is just a normal Gaussian distribution， mean 0。

 and a standard deviation is1， and a standard deviation， again。

 is just the measure of a spread of the Gaussian。But then once we multiply here and we look at the histogram of why we see that the mean。

 of course， stays the same。 It's about 0， because this is a symmetric operation。

 but we see here that the standard deviation has expanded to 3。

 And the input standard deviation was one。 But now we've grown to 3。

 And so what you're seeing in the histogram is that this Gaussian is expanding。

And so we're expanding this Gaussian from the input， and we don't want that。

 We want most of the neural nets to have relatively similar activations。

 so unit Gaussian roughly throughout the neural net。And so the question is。

 how do we scale these ws to preserve the。To preserve this distribution， to remain a Gasian。

And so intuitively， if I multiply here these。Elements of W by a larger number， likes say by 5。

Then the Gaussian grows and grows in standard deviation。 So now we're at 15。 So basically。

 these numbers here in the output Y take on more and more extreme values。



![](img/88dd9899d3a9ef459d32c32418af4090_163.png)

But if we scale it down like8。2， then conversely， this Gaussian is getting smaller and smaller。

 and it's shrinking。 And you can see that the standard deviation is 0。6。



![](img/88dd9899d3a9ef459d32c32418af4090_165.png)

And so the question is， what do I multiply by here to exactly preserve the standard deviation to be one。

And it turns out that the correct answer mathematically when you work out through the variance of this multiplication here。

Is that you are supposed to divide by the square root of the fan in。

 The fan in is the basically the number of input elements here，10。

 So we are supposed to divide by 10 square root。And this is one way to do the square root。

 you raise it to a power of 0。5 the same as doing a square root。

So when you divide by the square root of 10， then we see that。The output Gausstion。

 it has exactly standard deviation of one。 Now， unsurprisingly。

 a number of papers have looked into how， but to best initialize neural networks。

 And in the case of multiplayly perceptions， we can have fairly deep networks that have these non nonlinearities in between。

 And we want to make sure that the activations are well behaved and they don't expand to infinity or shrink all the way to 0。

 And the question is， how do we initialize the weights so that these activations take con reasonable values throughout the network。



![](img/88dd9899d3a9ef459d32c32418af4090_167.png)

![](img/88dd9899d3a9ef459d32c32418af4090_168.png)

Now， one paper that has studied this in quite a bit detail that is often referenced is this paper by Cming Hehull called the Dlving deep Interactifiers。



![](img/88dd9899d3a9ef459d32c32418af4090_170.png)

Now， in this case， they actually study convolutional neural networks， and they study。

 especially the Relu No nonlineararity and the P Relu No linearity instead of a 10 H No nonlinearity。

 but the analysis is very similar and。

![](img/88dd9899d3a9ef459d32c32418af4090_172.png)

Basically， what happens here is for them， the re longity that they care about quite a bit here。



![](img/88dd9899d3a9ef459d32c32418af4090_174.png)

Is a squashing function where all the negative numbers are simply clamped to 0。

So the positive numbers are a pass through， but everything negative is just set to0。

And because you are basically throwing away half of the distribution。

 they find in their analysis of the forward activations in the neural net that you have to compensate for that with a gain。



![](img/88dd9899d3a9ef459d32c32418af4090_176.png)

And so， here。They find that basically when they initialize their weights。

 they have to do it with a zero min Gasian whose standard deviation is square root of2 over the thanin。

What we have here is we are initializing Gasian with the square root of fanin。

This Nl here is the fannon。 So what we have is square root of one over the fannon。



![](img/88dd9899d3a9ef459d32c32418af4090_178.png)

Because we have the division here。Now， they have to add this factor of two because of the relu。

 which basically discards half of the distribution and clamps at at0。

 and so that's where you get an initial factor。Now， in addition to that。

 this paper also studies not just the sort of behavior of the activations in the forward path of the neural net。

 but it also studies the back propagation， and we have to make sure that the gradients also are well behaved and so because ultimately they end up updating our parameters。

And what they find here through a lot of the analysis that I invite you to read through。

 but it's not exactly approachable。What they find is basically。

If you properly initialize the forward pass， the backward pass is also approximately initialized up to a constant factor that has to do with the size of the number of hidden neurons in an early and a late layer。

And but basically， they find empirically that this is not a choice that matters too much。Now。

 this climbing initialization is also implemented in Pytorch。

 so if you go to Tordot and end up in it documentation， you'll find climbing normal。



![](img/88dd9899d3a9ef459d32c32418af4090_180.png)

And in my opinion， this is probably the most common way of initializing neural networks now。

And it takes a few keyword arguments here。 So another one， it wants to know the mode。

 Would you like to normalize the activations， or would you like to normalize the gradients to to be always Gaussian with zero mean and a unit or one standard deviation。

And because they find in the paper that this doesn't matter too much。

 most of the people just leave it as the default， which is fanin。And then second。

 passing the No nonlinearity that you are using， because depending on the non nonlinearity。

 we need to calculate a slightly different gain。 And so if your nonlinearity is just linear。

 so there's no nonlinearity， then the gain here will be one。

 and we have the exact same kind of formula that we've got up here。



![](img/88dd9899d3a9ef459d32c32418af4090_182.png)

![](img/88dd9899d3a9ef459d32c32418af4090_183.png)

But if thenoll nonlinear guaranteeity is something else。

 we're going to get a slightly different gain。 And so if we come up here to the top。



![](img/88dd9899d3a9ef459d32c32418af4090_185.png)

We see that， for example， in the case of Blu， this gain is a square root of  two。

 And the reason the square root， because in this paper。

You see how the two is inside of the square root。 So the gain is a squared of 2。

In a case of linear or identity， we just get a gain of one。In a case of 10h。

 which is what we're using here， the advised gain is a 5 over 3。And intuitively。

 why do we need a gain on top of the initialization is because 10age。

 just like Relu is a contractive transformation。 So what that means is you are taking the output distribution from this major multiplication。

 and then you are squashing it in some way。 Now， Relu squashes it by taking everything below 0 and clamping it to 0。

10 H also squashes it because it's a contractive operation， it will take the tails。

 and it will squeeze them in。 And so in order to fight the squeezing in。

 we need to boost the weights a little bit so that we renormalize everything back to standard unit standard deviation。

😊。

![](img/88dd9899d3a9ef459d32c32418af4090_187.png)

![](img/88dd9899d3a9ef459d32c32418af4090_188.png)

![](img/88dd9899d3a9ef459d32c32418af4090_189.png)

So that's why there's a little bit of a gain that comes out。



![](img/88dd9899d3a9ef459d32c32418af4090_191.png)

Now I'm skipping through this section a little bit quickly and I'm doing that actually intentionally。

And the reason for that is because。About seven years ago， when this paper was written。

 you had to actually be extremely careful with the activations and ingredients and their ranges and their histograms。

 And you have to be very careful with the precise setting of gains and the scrutinising of the nu nonlinearerities used and so on。

And everything was very finicky and very fragile and very properly arranged for the neural net to train。

 especially if your neural net was very deep。But there are a number of modern innovations that have made everything significantly more stable and more well behaved。

 and has become less important to initialize these networks exactly right。

And some of those modern innovations， for example， are residual connections。

 which we will cover in the future。 the use of a number of normalization layers， like， for example。

 batch normalization layer normalization group normalization we're going to go into a lot of these as well。

 and number three， much better optimizers not just to castastic gradient decent。

 the simple optimizer we're basically using here， but a slightly more complex optimizes like RMSs Pro and especially atom。

 and so all of these modern innovations make it less important for you to precisely calibrate the initialization of the neural net。

All that being said in practice， what should we do in practice when I initialize these neural。

 I basically just normalize my weights by the square root of the fanin。

 so basically roughly what we did here is what I do。



![](img/88dd9899d3a9ef459d32c32418af4090_193.png)

Now， if we want to be exactly accurate here， we and go back in it of timing normal。

 this is how it would implemented。We want to set the standard deviation to be gained over the square root of fanin。

 right， So to set the standard deviation of our weights， we will proceed as follows。



![](img/88dd9899d3a9ef459d32c32418af4090_195.png)

Basically， when we have Tord rannnon。 And let's say I just grade 1000 numbers。

 We can look at the standard deviation of this。 And， of course， that's one。

 That's the amount of spread。 Let's make this a bit bigger， so it' closer to one。

So that's the spread of the Gaussian of zero mean and unit standard deviation。Now， basically。

 when you take these and you multiply by say。2。That basically scales down the Gaussian。

 and that makes its standard deviation 。2。 So basically。

 the number that you multiply by here ends up being the standard deviation of this Gaussian。

So here this is a standard deviation 。2 Gaussian here when we sample RW1。

But we want to set the standard deviation to gain over square root of fan mode， which is fanin。



![](img/88dd9899d3a9ef459d32c32418af4090_197.png)

So in other words， we want to multiply by gain， which for 10 H is 5 over 3。



![](img/88dd9899d3a9ef459d32c32418af4090_199.png)

5 World3 is the game。

![](img/88dd9899d3a9ef459d32c32418af4090_201.png)

And then， times。嗯。Aras are divide。Square root of。The fanin。



![](img/88dd9899d3a9ef459d32c32418af4090_203.png)

And in this example here， the fan in was 10。 And I just noticed that actually here。

 the fanin for W1 is actually an embeine's block size， which， as you will recall， is actually 30。

 And that's because each character is 10 dimensional。 But then we have three of them。

 and we concatenate them。 So actually the fan in here was 30。 and I should have used 30 here。

 probably。 But basically， we want 30 square root。So this is the number。

 This is what our standard deviation we want to be。 and this number turns out to be 0。3。Whereas here。

 just by fiddling with it and looking at the distribution and making sure it looks okay。

 we came up with 0。2。And so instead， what we want to do here is we want to make the standard deviation B。

嗯。5 over3， which is our gain divide。This amount。Ts 。2， square root。

And these brackets here are not that necessary， but I'll just put them here for clarity。

 This is basically what we want。 This is the timing in it in our case， for a 10 H non nonlinearity。

 And this is how we would initialize the neural net。And so we're multiplying by 0。

3 instead of multiplying by 0。2。

![](img/88dd9899d3a9ef459d32c32418af4090_205.png)

![](img/88dd9899d3a9ef459d32c32418af4090_206.png)

And so， we can。We can initialize this way， and then we can train the neural net and see what we got。



![](img/88dd9899d3a9ef459d32c32418af4090_208.png)

Okay， so I train the neural and we end up in roughly the same spot。

 So looking at the validation loss， we now get 2。10 and previously， we also had 2。10。

 and there's a little bit of a difference， but that's just the randomness of the process， I suspect。



![](img/88dd9899d3a9ef459d32c32418af4090_210.png)

![](img/88dd9899d3a9ef459d32c32418af4090_211.png)

But the big deal， of course， is we get to the same spot。

 but we did not have to introduce any magic numbers that we got from just looking at histograms and guessing checking。

 we have something that is semiprincipled and will scale us to much bigger networks and something that we can sort of use as a guide。

 So I mentioned that the precise setting of these initializations is not as important today due to some modern innovations。

 and I think now is a pretty good time to introduce one of those modern innovations and that is batch normalization。



![](img/88dd9899d3a9ef459d32c32418af4090_213.png)

![](img/88dd9899d3a9ef459d32c32418af4090_214.png)

![](img/88dd9899d3a9ef459d32c32418af4090_215.png)

So batch normalization came out in 2015 from a team at Google。

 and it was an extremely impactful paper because it made it possible to train very deep neural nets quite reliably。

 and it basically just worked。So here's what rationalization does and what's implemented。嗯。Basically。

 we have these hidden states H preactide， and we were talking about how we don't want these these pre activation states to be way too small because then the 10 H is not doing anything。

 but we don't want them to be too large because then the 10 h is saturated。



![](img/88dd9899d3a9ef459d32c32418af4090_217.png)

In fact， we want them to be roughly roughly Gaussian。

 so zero mean and a units or one standard deviation， at least at initialization。

So the insight from the ba' paper is， okay， you have these hidden states and you'd like them to be roughly Gaussian。

 then why not take the hidden states and just normalize them to be Gaussian。

And it sounds kind of crazy but you can just do that because standardizing hidden states so that their unit Gaussian is a perfectly differentiable operation as we'll soon see。

 and so that was kind of like the big insight in this paper and when I first read it my mind was blown because you can just normalize these hidden states and if you'd like unit Gaussian states in your network at least initialization you can just normalize them to be unit Gaussian。

So let's see how that works。

![](img/88dd9899d3a9ef459d32c32418af4090_219.png)

So we're going to scroll to our pre activationivs here just before they enter into the10H。Now。

 the idea， again， is， remember， we're trying to make these roughly Gausian。

 And that's because if these are way too small numbers， then the 10 H here is kind of inactive。

But if these are very large numbers， then the 10 h way too saturate it and gradient into the flow。

So we'd like this to be roughly cautionussian。So the insight in batchization again is that we can just standardize these activations。

 so they are exactly Gaussian。So here， H preact。Has a shape of 32 by 200。

32 examples by 200 neurons in the hidden layer。So basically。

 what we can do is we can take H preoc and we can just calculate the mean。

And the mean we want to calculate across the zero dimension。And we want to also keep them as true。

So that we can easily broadcast this。So the shape of this。Is 1 by 200， in other words。

 we are doing the mean over all the elements in the batch。And similarly。

 we can calculate the standard deviation of these activations。And there will also be one by 200。Now。

 in this paper， they have the E。Sort of prescription here。 And see here we are calculating the mean。

 which is just taking the average value。Of any neurons activation。

 And then the standard deviation is basically kind of like this。

 the measure of the spread that we've been using， which is the distance of every one of these values away from the mean and that squared and averaged。

Thats the that's the variance。 And then if you want to take the standard deviation。

 you would square root the variance to get the standard deviation。

So these are the two that we're calculating and now we're going to normalize or standardize these x's by subtracting the mean and dividing by the standard deviation。

So basically， we're taking inch preact。And we subtract。的明。

And then we divide by the standard deviation。This is exactly what these two。

 F TD and mean are calculating。

![](img/88dd9899d3a9ef459d32c32418af4090_221.png)

Oops。Sorry， this is the mean， and this is the variance。

 You see how the sigma is the standard deviation， usually， so this is sigma square。

 which is the variance is the square of the standard deviation。

So this is how you standardize these values。 And what this will do is that every single neuron now in its firing rate will be exactly unit Gaussian on these 32 examples。

 at least of this batch。 That's why it's called batch normalization。

 We are normalizing these batches。

![](img/88dd9899d3a9ef459d32c32418af4090_223.png)

And then we could， in principle， train this， notice that calculating the mean understanding deviation。

 these are just mathematical formulas。 They are perfectly differentiable。

 All this is perfectly differentiable， and we can just train this。The problem is。

 you actually won't achieve a very good result with this。 And the reason for that is。



![](img/88dd9899d3a9ef459d32c32418af4090_225.png)

We want these to be roughly Gaussian， but only at initialization。

 but we don't want these to be to be forced to be Gaussian。 always。

 we'd like to allow the neural net to move this around， to potentially make it more diffuse。

 to make it more sharp， to make some 10 H neurons maybe be trigger more trigger happy or less trigger happy。

 So we'd like this distribution to move around， and we'd like the back propagation to tell us how the distribution should move around。

And so in addition to this idea of standardizing the activations at any point in the network。



![](img/88dd9899d3a9ef459d32c32418af4090_227.png)

We have to also introduce this additional component in the paper。



![](img/88dd9899d3a9ef459d32c32418af4090_229.png)

Here described a steel in shift。And so basically， what we're doing is we're taking these normalized inputs。

 and we are additionally scaling them by some gain and offsetting them by some bias to get our final output from this layer。

And so what that amounts to us the following。We are going to allow a batch normalization gain。

To be initialized at just a once。And the once will be in the shape of one by and hidden。



![](img/88dd9899d3a9ef459d32c32418af4090_231.png)

And then we also will have a be and bias。Which will be torched at zeros。

And it will also be of the shape and by。

![](img/88dd9899d3a9ef459d32c32418af4090_233.png)

One by and hidden。And then， here。The B in gain will multiply this。

And the be and bias will offset it here。So because this is an interesting to one and this to 0。

At initialization。Each neurons' firing values in this batch will be exactly Uni Gaussian and will have nice numbers。

 no matter what the distribution of the H preact is coming in， coming out。

 it will be Uni Gaussian for each neuron。 And that's roughly what we want。

 at least at initialization。嗯。And then during optimization。

 we'll be able to back propagate into be in game and be in bias and change them。

 So the network is given the full ability to do with this whatever it wants internally。Here。

 we just have to make sure that we。Include these in the parameters of the neural nu。

 because they will be trained with back proation。

![](img/88dd9899d3a9ef459d32c32418af4090_235.png)

So let's initialize this。And then we should be able to train。



![](img/88dd9899d3a9ef459d32c32418af4090_237.png)

And then we're going to also。Copyied this line。Which is the best normalization layer here on the single line of code。

 And we're going to swing down here， and we're also going to do the exact same thing at test time here。



![](img/88dd9899d3a9ef459d32c32418af4090_239.png)

So similar to train time， we're going to normalize and then scale。

 and that's going to give us our train and validation loss。



![](img/88dd9899d3a9ef459d32c32418af4090_241.png)

![](img/88dd9899d3a9ef459d32c32418af4090_242.png)

And we'll see in a second that we're actually going to change this a little bit。

 but for now I'm going to keep it this way。

![](img/88dd9899d3a9ef459d32c32418af4090_244.png)

So I'm just going to wait for this to converge。 Okay， so I allowed the neural net to converge here。

 And when we scroll down， we see that our validation loss here is 2。10， roughly。

 which I wrote down here。

![](img/88dd9899d3a9ef459d32c32418af4090_246.png)

And we see that this is actually kind of comparable to some of the results that we've achieved previously。

Now， I'm not actually expecting an improvement in this case。

 And that's because we are dealing with a very simple neural net that that has just a single hidden layer。



![](img/88dd9899d3a9ef459d32c32418af4090_248.png)

So。

![](img/88dd9899d3a9ef459d32c32418af4090_250.png)

In fact， in this very simple case of just one hidden layer。

 we were able to actually calculate what the scale of W should be to make these pre activationivations already have a roughly gaussian shape。

 So the baization is not doing much here。But you might imagine that once you have a much deeper neural net that has lots of different types of operations。

 and there's also， for example， residual connections which we'll cover and so on。

 it will become basically very， very difficult to tune the scales of your weight matrices。

 such that all the activations throughout the neural net are roughly gaussian。

And so that's going to become very quickly intractable。But compared to that， it's going to be much。

 much easier to sprinkle batchization layers throughout the neural net。



![](img/88dd9899d3a9ef459d32c32418af4090_252.png)

So in particular， it's common to look at every single linear layer like this one。

 this is a linear layer multiplying by a weight matrix and adding the bias。Or， for example。

 convolutions， which we'll cover later and also perform basically a multiplication with the weight matrix。

 but in a more spatially structured format。It's customary to take these linear layer or convolutional layer and append a baization layer right after it to control the scale of these activations at every point in the neural nu。

So we'd be adding these bathroom layers throughout the neural net。

 and then this controls the scale of these activations throughout the neural net。



![](img/88dd9899d3a9ef459d32c32418af4090_254.png)

It doesn't require us to do perfect mathematics and care about the activation distributions for all these different types of neural network Lego building blocks that you might want to introduce into your neural net。

 And it significantly stabilizes the training。 And that's why these layers are quite popular。 Now。

 the stability offered by batch normalization actually comes at a terrible cost。

And that cost is that if you think about what's happening here。

Something terribly strange and unnatural is happening。

It used to be that we have a single example feeding into a neural nut。

 and then we calculate it this activations and its logits。

 And this is a deterministic sort of process。 So you arrive at some loits for this example。

And then because of efficiency of training， we suddenly started to use batches of examples。

 but those batches of examples were processed independently。 and it was just an efficiency thing。

But now suddenly in batch normalization， because of the normalization through the batch。

 we are coupling these examples mathematically and in the forward pass and the backward pass of the neuralent。

So now the hidden seat activations H preact in yourlogits for any one input example are not just a function of that example and its input。

 but they're also a function of all the other examples that happen to come for a ride in that batch。

 And these examples are sampled randomly。And so what's happening is， for example。

 when you look at H pre act that's going to feed into H， the hidden state activations for。

 for example， for， for any one of these input examples。Is going to actually change slightly。

 depending on what other examples there are in the batch。

And depending on what other examples happen to come for a ride。

Hge is going to change suddenly and is going to like jitter。

 if you imagine sampling different examples， because the statistics of the mean and eastern deviation are going to be impacted。

And so you'll get a jitter for H， and you'll get a jitter for Loits。

And you'd think that this would be a bug or something undesirable， but in a very strange way。

 this actually turns out to be good in neural network training。And as a side effect。

 and the reason for that is that you can think of this as kind of like a regularr。

Because what's happening is you have your input and you get your age。

 And then depending on the other examples， this is jing a bit。

And so what that does is that it's effectively padding out any one of these inputet examples。

 and it's introducing a little bit of entropy。 And because of the padding out。

 it's actually kind of like a form of data augmentation， which we'll cover in the future。

 and it's kind of like augmenting the inputet a little bit and jittering it。

 And that makes it harder for the neural net to overfit these concrete specific examples。

 So by introducing all this noise。 It actually like pas out the examples。

 and it regularizes the neural net。 And that's one of the reasons why deceivingly as a second order effect。

 This is actually a regularizer。 And that has made it harder for us to remove the use of batteryalization。

Because basically no one likes this property that the examples in the batch are coupled mathematically and in the forward pass。

 and at least all kinds of like strange results we'll go into some of that in a second as well。

And it leads to a lot of bugs and so on。 And so no one likes this property。

 and so people have tried to deprecate the use of batch normalization and move to other normalization techniques that do not couple the examples of a batch Exles are layer normalization。

 instance normalization， group normalization and so on， and well come some of these later。嗯。

But basically， long story short， batch normalization was the first kind of normalization layer to be introduced。

 It worked extremely well。It happened to have this regularizing effect。Its stabilized training。

And people have been trying to remove it and move to some of the other normalization techniques。

But it's been hard because it just works quite well。

 and some of the reason that it works quite well is again because of this regularizing effect and because it is quite effective at controlling the activations and their distributions。

So that's kind of like the brief story of bashermalization。

 and I'd like to show you one of the other weird sort of outcomes of this coupling。



![](img/88dd9899d3a9ef459d32c32418af4090_256.png)

So here's one of the strange outcomes that I only gloss over previously。



![](img/88dd9899d3a9ef459d32c32418af4090_258.png)

When I was evaluating the loss on the Val set。

![](img/88dd9899d3a9ef459d32c32418af4090_260.png)

Basically， once we've trained a neural nut。We'd like to deploy it in some kind of a setting。

 and we'd like to be able to feed in a single individual example and get a prediction out from our neural net。



![](img/88dd9899d3a9ef459d32c32418af4090_262.png)

But how do we do that when our neural nu now in a forward pass estimates the statistics of the mean understanding deviation of a batch。

 The neural nut expects batches as an input now。 So how do we feed in a single example and get sensible results out。

And so the proposal in the baization paper is the following。



![](img/88dd9899d3a9ef459d32c32418af4090_264.png)

What we would like to do here is we would like to basically have a step after training。

That calculates and sets the bathroom mean and standard deviation a single time over the training set。

And so I wrote this code here in the interest of time。

 and we're going to call what's called Callibrate the baachelor Stats。And basically。

 what we do is Tortra nograd telling P Torch that none of this we will call the do backward on。

 and it's going to be a bit more efficient。We're going to take the training set。

Get the pre activationivs for every single training example。

 and then one single time estimate the mean and standard deviation over the entire training set。

And then we're going to get B and mean and B and standard deviation。

 and now these are fixed numbers estimated over the entire training set。



![](img/88dd9899d3a9ef459d32c32418af4090_266.png)

And here， instead of estimating it。Dynaically。We are going to instead here use B and mean。

And here we're just going to use BM standard deviation。



![](img/88dd9899d3a9ef459d32c32418af4090_268.png)

And so at thus time， we are going to fix these， clamp them and use them during inference。 and now。



![](img/88dd9899d3a9ef459d32c32418af4090_270.png)

You see that we get basically identical result。But the benefit that we've gained is that we can now also forward a single example because the mean and standard deviation are now fixed Ser tensors。



![](img/88dd9899d3a9ef459d32c32418af4090_272.png)

That said， nobody actually wants to estimate this mean and standard deviation as a second stage after neural network training because everyone is lazy。

 And so this batch normalization paper actually introduced one more idea。

 which is that we can estimate the mean and standard deviation in a running manner。

 running manner during training of the neural network。



![](img/88dd9899d3a9ef459d32c32418af4090_274.png)

And then we can simply just have a single stage of training。 And on the side of that training。

 we are estimating the running Ns and deviation。 So let's see what that would look like。



![](img/88dd9899d3a9ef459d32c32418af4090_276.png)

Let me basically take the mean here that we are estimating on the batch and let me call this B a mean on the I iteration。

And then here， this is B and SDD。嗯。B an SD at I。Okay。And the mean comes here， and the SDD comes here。

So so far I've done nothing， I've just moved around and I created these extra variables for the mean standard deviationation。

 and I've put them here so so far nothing has changed。

What we' are going to do now is we' are going to keep a running mean of both of these values during training。

 So let me swing up here and let me create a B N mean underscore running。



![](img/88dd9899d3a9ef459d32c32418af4090_278.png)

And I'm going to initialize it at zeros。And then be an STD running。Which all lies at once。Because。

In the beginning， because of the way we initialized W1 and B1。

 H preact will be roughly unit Gaussian， so the mean will be roughly 0 and extended deviation roughly 1。

 So I'm going to initialize these that way。But then here， I'm going to update these。And in Pytorch。

These mean and standard deviation that are running。

 they're not actually part of the gradient based optimization。

 We're never going to derive gradients with respect to them。 they're updated on the side of training。

And so what we're going to do here is we're going to say with Torrssht nograd。

Telling Pytorch that the update here is not supposed to be building out a graph because there will be no doubt backward。

But this running mean is basically going to be 0。99。9ine times the current value。Plus， 0。

001 times the this value。This new mean。And in the same way， BNSDD running will be。Mostly。

 what it used to be。But it will receive a small update in the direction of what the current standard deviation is。

And as you're seeing here， this update is outside and on the side of the gradient based optimization。

 And it's simply being updated， not using gradient。 scent iss just being updated using Geny。

 like smooth。Sort of。Running mean manner。And so while the network is training and these pre activationations are sort of changing and shifting around during back propagation。

We are keeping track of the typical mean standard deviation， and we'reestimating them once。

And when I run this。Now， I'm keeping track of this in a running manner。And what we're hoping for。

 of course， is that the B and mean underscore running and B and mean_ SDD are going to be very similar to the ones that we calculate here。



![](img/88dd9899d3a9ef459d32c32418af4090_280.png)

And that way we don't need a second stage because we've sort of combined the two stages and we've put them on the side of each other if you want to look at it that way。



![](img/88dd9899d3a9ef459d32c32418af4090_282.png)

![](img/88dd9899d3a9ef459d32c32418af4090_283.png)

And this is how this is also implemented in the batch normalization layer imp pytorrch。

 So during training， the exact same thing will happen。 And then later， when you are using inference。

 it will use the estimated running mean of both the mean estimate deviation of those hidden states。



![](img/88dd9899d3a9ef459d32c32418af4090_285.png)

![](img/88dd9899d3a9ef459d32c32418af4090_286.png)

![](img/88dd9899d3a9ef459d32c32418af4090_287.png)

So let's wait for the optimization to converge。 And hopefully。

 the running meana se deviationation are roughly equal to these two。

 And then we can simply use it here。 And we don't need this stage of explicit calibration at the end。

 Okay， so the optimization finished。

![](img/88dd9899d3a9ef459d32c32418af4090_289.png)

![](img/88dd9899d3a9ef459d32c32418af4090_290.png)

I'll rerun the explicit estimation， and then the B and mean from the explicit estimation is here。



![](img/88dd9899d3a9ef459d32c32418af4090_292.png)

And B And mean from the running estimation。During the during the optimization， you can see as' very。

 very similar。It's not identical， but it's pretty close。And in the same way， B an SDD is this。

 And B an SD running is this。As you can see that once again， they are fairly similar values。

 not identical but pre close。And so then here， instead of the in mean。

 we can use the B and mean running。Instead of BNSDD， we can use BNDD running。

And hopefully the validation laws will not be impacted too much。



![](img/88dd9899d3a9ef459d32c32418af4090_294.png)

Okay， so' basically identical。 and this way we've eliminated the need for this explicit stage of calibration because we are doing it in line over here。



![](img/88dd9899d3a9ef459d32c32418af4090_296.png)

![](img/88dd9899d3a9ef459d32c32418af4090_297.png)

Okay， so we're almost done with batch normalization。

 There are only two more notes that I'd like to make。 Number one。

 I've skipped a discussion over what is this plus epsilon doing here。

 This epsilon is usually like some small fixed number。 for example，1 E negative 5 by default。

 And what it's doing is that it's basically preventing a division by 0。

 In the case that the variance over your batch。Is exactly 0。 In that case， here。

 we normally have a division by 0。 but because of the plus epsilon。

 this is going to become a small number in the denominator instead。

 and things will be more well behaved。 So feel free to also add a plus epsilon here of a very small number。

 It doesn't actually substantially change the result。 I'm going to skip it in our case。

 just because this is unlikely to happen in our very simple example here。



![](img/88dd9899d3a9ef459d32c32418af4090_299.png)

And the second thing I want you to notice is that we're being wasteful here， and it's very subtle。

But right here where we are adding the bias into H pre。



![](img/88dd9899d3a9ef459d32c32418af4090_301.png)

These biases now are actually useless because we're adding them to the H pre Act。

 but then we are calculating the mean。For every one of these neurons and subtracting it。

So whatever bias you add here is going to get subtracted right here。



![](img/88dd9899d3a9ef459d32c32418af4090_303.png)

And so these biases are not doing anything， in fact。

 they're being subtracted out and they don't impact the rest of the calculation。

 so if you look at B1。 grad it's actually going to be zero because it's being subtracted out and doesn't actually have any effect。



![](img/88dd9899d3a9ef459d32c32418af4090_305.png)

And so whenever you are using ba normalization layers， then if you have any weight layers before。

 like a linear or a con or something like that， you're better off coming here and just like not using bias。

 So you don't want to use bias。 And then here， you don't want to add it because it's that spurious。

 Instead， we have this ba normalization bias here。 And that baization bias is now in charge of the biasing of this distribution。

 Instead of this B one that we had here originally。



![](img/88dd9899d3a9ef459d32c32418af4090_307.png)

![](img/88dd9899d3a9ef459d32c32418af4090_308.png)

And so basically， the baization layer has its own bias。

 and there's no need to have a bias in the layer before it。

 because that bias is going to be subtracted out anyway。



![](img/88dd9899d3a9ef459d32c32418af4090_310.png)

So that's the other small detail to be careful with。

 Sometimes it's not going to do anything catastrophic。 This B1 will just be useless。

 It will never get any gradient。 It will not learn。 It will stay constant， and is just wasteful。

 but it doesn't actually really impact anything otherwise。 Okay。

 so I rearrange a code a little bit with comments。 And I just wanted to give a very quick summary of the batchization layer。



![](img/88dd9899d3a9ef459d32c32418af4090_312.png)

![](img/88dd9899d3a9ef459d32c32418af4090_313.png)

We are using batchization to control the statistics of activations in the neural net。

It is common to sprinkle batch formalization layer across the neural net。

 and usually we will place it after layers that have multiplications， like for example。

 a linear layer or a convolutional layer， which we may cover in the future。



![](img/88dd9899d3a9ef459d32c32418af4090_315.png)

Now， the batch normalization internally has parameters for the gain and the bias。

 and these are trained using batch propagation。It also has two buffers。

The buffers are the mean and the standard deviation。

 the running mean and the running mean of the standard deviation。

And these are not trained using back application。 These are trained using this Janki update of kind of like a running mean update。

So。These are sort of the parameters and the buffers of ba layer。



![](img/88dd9899d3a9ef459d32c32418af4090_317.png)

And then really what it's doing is it's calculating the mean understanding deviation of the activations that are feeding into the bathroom layer。

Over that batch。Then it's centering that batch to be unit Gaussian。

And then it offsetting and scaling it by the learned bias and gain。



![](img/88dd9899d3a9ef459d32c32418af4090_319.png)

And then on top of that， it's keeping track of the mean standard deviation of the inputs。

And it's maintaining this running mean standard deviation。

And this will later be used at inference so that we don't have to re the meanest standard deviation all the time。

And in addition， that allows us to basically forward individual examples at Du time。



![](img/88dd9899d3a9ef459d32c32418af4090_321.png)

So that's the ba generalization layer， it's a fairly complicated layer。

 but this is what it's doing internally。

![](img/88dd9899d3a9ef459d32c32418af4090_323.png)

Now， I wanted to show you a little bit of a real example。 so you can search Resnet。

 which is a residual neural network， and these are context of neural networks used for image classification。

And， of course， we haven't come resnets in detail。 So I'm not going to explain all the pieces of it。

 But for now， just note that the image feeds into a resnet on the top here。 And there's many。

 many layers with repeating structure all the way to predictions of what's inside that image。

This repeating structure is made up of these blocks。

 and these blocks are just sequentially stacked up in this deep neural network。Now the code for this。

 the block， basically that's used and repeated sequentially in series。

 is called this bottleneck block， bottleneck block。And there's a lot here， this is all Pytorch。

 and of course we haven't covered all of it， but I want to point out some small pieces of it。

Here in in it is where we initialize the neural net。

 So this code of block here is basically the kind of stuff we're doing here。

 We're initializing old layers。

![](img/88dd9899d3a9ef459d32c32418af4090_325.png)

![](img/88dd9899d3a9ef459d32c32418af4090_326.png)

And in the forward， we are specifying how the neural lot acts once you actually have the input。

 So this code here is along the lines of what we're doing here。



![](img/88dd9899d3a9ef459d32c32418af4090_328.png)

![](img/88dd9899d3a9ef459d32c32418af4090_329.png)

And now these blocks are replicated and stacked up serially。

 and that's what residual usual network would be。And so notice what's happening here， co1。

 these are convolutional layers。And these convolution layers basically they're the same thing as a linear layer。

 except convolution layers don't apply。 convolution layers are used for images。

 and so they have spatial structure， and basically this linear multiplication and bias offset are done on patches。

Instead of a math， instead of the full input。So because these images have structure。

 spatial structure， convolutions just basically do Wx plus B。

 but they do it on overlapping patches of the input。



![](img/88dd9899d3a9ef459d32c32418af4090_331.png)

![](img/88dd9899d3a9ef459d32c32418af4090_332.png)

But otherwise， it's W X plus B。Then we have the normal layer。

 which by default here is initialized to be a bash norm in 2D。

 so two dimensional batchche normalization layer。And then we have a non nonlinearity like Relu。

 So instead of here they use Relu， we are using 10 H in this case。



![](img/88dd9899d3a9ef459d32c32418af4090_334.png)

But both are just non nonlinearities and you can just use them relatively interchangeably for very deep networks。

 res typically empirically work a bit better。

![](img/88dd9899d3a9ef459d32c32418af4090_336.png)

So see the motif that's being repeated here， we have convolution， ba normalization， re， convolution。

 ba normalization， re， etcter， and then here this is a residual connection that we haven't covered yet。



![](img/88dd9899d3a9ef459d32c32418af4090_338.png)

But basically， that's the exact same pattern we have here， we have a weight layer。

 like a convolution or like a linear layer。Bash normalization， and then 10 H。

 which is a nu nonlineararity。 But basically a weight layer。

 a normalization layer and nu nonlineararity。 And that's the motif that you would be stacking up when you create these deep neural networks。

 exactly as is done here。

![](img/88dd9899d3a9ef459d32c32418af4090_340.png)

![](img/88dd9899d3a9ef459d32c32418af4090_341.png)

And one more thing I'd like you to notice is that here when they are initializing the com layersers。

 like cov1 by one， the depth for that is right here。And so it's initializing an NN。 co2D。

 which is a convolutional layer in Pytorch， and there's bunch of keyword arguments here that I am not going to explain yet。

 but you see how there's bias equals false。The bicycles false exactly for the same reason as bias is not used。

 In our case。 You see how I erase the use of bias， and the use of bias is spurious because after this weight layer。

 there's a bamalization， and the baization subs that bias and that has its own bias。

 So there's no need to introduce these spurious parameters。

 It wouldn't hurt performance is just useless。

![](img/88dd9899d3a9ef459d32c32418af4090_343.png)

![](img/88dd9899d3a9ef459d32c32418af4090_344.png)

![](img/88dd9899d3a9ef459d32c32418af4090_345.png)

And so because they have this motif of calm bar， they don't need a bias here as there's a bias inside here。

So。By the way， this example here is very easy to find。 Just do a resonnet Pytorrch。

And it's this example here。So this is kind of like the stock implementation of a residual neural network in Pytorch。

 and you can find that here， but of course I haven't covered many of these parts yet。



![](img/88dd9899d3a9ef459d32c32418af4090_347.png)

And I would also like to briefly descend into the definitions of these pyro layers and the parameters that they take。

 Now， instead of a convolutional layer， we're going to look at a linear layer。



![](img/88dd9899d3a9ef459d32c32418af4090_349.png)

![](img/88dd9899d3a9ef459d32c32418af4090_350.png)

Because that's the one that we're using here。 this is a linear layer。

 and I haven't covered convolutions yet， but as I mentioned。

 convolutions are basically linear layers， except on patches。



![](img/88dd9899d3a9ef459d32c32418af4090_352.png)

So a linear layer performs a Wx plus B， except here they're calling the WA transpose。



![](img/88dd9899d3a9ef459d32c32418af4090_354.png)

So the ca is W X plus B very much like we did here to initialize this layer。

 you need to know the fan in， the fan out。 and that's so that they can initialize this W。

 This is the fan in and the fan out。

![](img/88dd9899d3a9ef459d32c32418af4090_356.png)

![](img/88dd9899d3a9ef459d32c32418af4090_357.png)

![](img/88dd9899d3a9ef459d32c32418af4090_358.png)

So they know how big the weight matrix should be。You need to also pass in whether whether or not you want a bias。

 And if you set it to false， then no bias will be inside this layer。

 And you may want to do that exactly like in our case。

 if your layer is followed by a normalization layer， such as batchorm。



![](img/88dd9899d3a9ef459d32c32418af4090_360.png)

![](img/88dd9899d3a9ef459d32c32418af4090_361.png)

So this allows you to basically disable buy。Now in terms of the initialization。

 if we swing down here， this is reporting the variables used inside this linear layer。

 And our linear layer here has two parameters。 The weight and the bias。 in the same way。

 they have a weight and the bias。

![](img/88dd9899d3a9ef459d32c32418af4090_363.png)

![](img/88dd9899d3a9ef459d32c32418af4090_364.png)

![](img/88dd9899d3a9ef459d32c32418af4090_365.png)

And they're talking about how they initialize it by default。So by default。

 Py metize your weights by taking the fanin。And then doing one over fanin square root。

And then instead of a normal distribution， they are using a uniform distribution。



![](img/88dd9899d3a9ef459d32c32418af4090_367.png)

So it's very much the same thing， but they are using a one instead of 5 over 3。

 So there's no gain being calculated here。 The gain is just one。

 but otherwise is exactly one over the square root of fanin， exactly as we have here。



![](img/88dd9899d3a9ef459d32c32418af4090_369.png)

So one over the squared of k is the scale of the weights。

 but when they are drawing the numbers they're not using a Gaussian by default。

 they are using a uniform distribution by default， and so they draw uniformly from negative squared of k to squared of k。



![](img/88dd9899d3a9ef459d32c32418af4090_371.png)

![](img/88dd9899d3a9ef459d32c32418af4090_372.png)

![](img/88dd9899d3a9ef459d32c32418af4090_373.png)

But its the exact same thing and the same motivation from for with respect to what we've seen in this lecture。

 And the reason they're doing this is if you have a roughly Gaussian input。

 this will ensure that out of this layer， you will have a roughly Gaussian output。 and use。

 you basically achieve that by scaling the weights by one over the squared of fanin。



![](img/88dd9899d3a9ef459d32c32418af4090_375.png)

![](img/88dd9899d3a9ef459d32c32418af4090_376.png)

So that's what this is doing。And then the second thing is the batch formalization layer。

 So let's look at what that looks like in Pytorarch。



![](img/88dd9899d3a9ef459d32c32418af4090_378.png)

So here we have a one dimensional best normalization layer exactly as we are using here。

And there are a number of keyword arguments going into it as well。

 So we need to know the number of features for us。 that is 200。

 and that is needed so that we can initialize these parameters here。 The gain。

 the bias and the buffers for the running mean and standard deviation。



![](img/88dd9899d3a9ef459d32c32418af4090_380.png)

Then they need to know the value of Epsilon here。And by default， this is 1 negative5。

 You don't typically change this too much。Then they need to know the momentum。And the momentum here。

 as they explain， is basically used for these running mean and running standard deviation。

So by default， the momentum here is 0。1。 The momentum we are using here in this example is 0。001。And。



![](img/88dd9899d3a9ef459d32c32418af4090_382.png)

Basically， rough， you may want to change this sometimes。 And roughly speaking。

 if you have a very large batch size。Then typically what you'll see is that when you estimate the mean and deviation。

For every single batch size， if it's large enough， you're going to get roughly the same result。



![](img/88dd9899d3a9ef459d32c32418af4090_384.png)

And so therefore， you can use slightly higher momentum like 01。But for a batch size as small as 32。

 the mean understanding standard deviation here might take on slightly different numbers because there's only 32 examples we are using to estimate the mean understanding deviation。

 So the value is changing around a lot。 And if your moment is 0。1。

 that that might not be good enough for this value to settle and converge to the actual mean standard deviation over the entire training set。

And so basically， if your batch size is very small， momentum of 0。

1 is potentially dangerous and it might make it so that the running mean and air deviation is thrashing too much during training and it's not actually converging properly。

Aine equals true determines whether this batch normalization layer has these learnable aine parameters。

 the the gain and the bias。 And this is almost always kept to true。

 I'm not actually sure why you would want to change this to false。

Then track running stats is determining whether or not baization layer of Pytorrch will be doing this。



![](img/88dd9899d3a9ef459d32c32418af4090_386.png)

And one reason you may， you may want to skip the running stats is because you may want to。

 for example， estimate them at the end as a stage 2 at the like this。 And in that case。

 you don't want the baization layer to be doing all this extra compute that you're not going to use。



![](img/88dd9899d3a9ef459d32c32418af4090_388.png)

![](img/88dd9899d3a9ef459d32c32418af4090_389.png)

![](img/88dd9899d3a9ef459d32c32418af4090_390.png)

And finally， we need to know which device we're going to run this rationalization on。

 a CPU or a GP and what the data type should be， half precision， single precision， double precision。

 and so on。So that's the batch normalization layer。

 otherwise they link to the paper is the same formula we've implemented。

 and everything is the same exactly as we've done here。



![](img/88dd9899d3a9ef459d32c32418af4090_392.png)

Okay， so that's everything that I wanted to cover for this lecture。Really。

 what I wanted to talk about is the importance of understanding the activations and gradients and their statistics in neural networks。

 and this becomes increasingly important， especially as you make your neural networks bigger。

 larger and deeper。

![](img/88dd9899d3a9ef459d32c32418af4090_394.png)

We looked at the distributions basically at the output layer and we saw that if you have two confident misredictions because the activations are too messed up at the last layer。

 you can end up with these hockey stick losses and if you fix this you get a better loss at the end of training because your training is not doing wasteful work。

Then we also saw that we need to control the activations。

 We don't want them to you know squash to zero or explode to infinity and because that you can run into a lot of trouble with all of these nonlinearities in these neural nets。

 and basically you want everything to be fairly homogeneous throughout the neural net。

 you want roughly gaussian activations throughout the neural net。



![](img/88dd9899d3a9ef459d32c32418af4090_396.png)

Then we talked about， okay， if we want roughly Gaussian activations。

 how do we scale these weight matrices and biases during initialization of the neural mud so that we don't get。

 you know， so everything is as controlled as possible。



![](img/88dd9899d3a9ef459d32c32418af4090_398.png)

![](img/88dd9899d3a9ef459d32c32418af4090_399.png)

So that gave us a large boost in improvement。 And then I talked about how that strategy is not actually possible for much。

 much deeper neural net， because when you have much deeper neural net with lots of different types of layers。

 it becomes really， really hard to precisely set the weights and the biases in such a way that the activations are roughly uniform throughout the neural net。



![](img/88dd9899d3a9ef459d32c32418af4090_401.png)

So then I introduced the notion of the normalization layer。 Now。

 there are many normalization layers that that people use in practice。 batchsh normalization。

 layer normalization， instance normalization， group normalization。 We haven't covered most of them。

 but I've introduced the first one。 And also the one that I believe came out first。

 And that's called batch normalization。

![](img/88dd9899d3a9ef459d32c32418af4090_403.png)

And we saw how rationalization works。 This is a layer that you can sprinkle throughout your deep neural nut。

 and the basic idea is if you want roughly gaussian activations。

 well then take your activations and take the mean understanding deviation and center your data。

And you can do that because the centering operation is differentiable。But on top of that。

 we actually had to add a lot of bells and whistles。

 And that gave you a sense of the complexities of the ba layer。 because now we're centering the data。

 That's great。 But suddenly， we need the gain and the bias。 And now those are trainable。😊。



![](img/88dd9899d3a9ef459d32c32418af4090_405.png)

![](img/88dd9899d3a9ef459d32c32418af4090_406.png)

And then because we are coupling all the training examples。 now， suddenly the question is。

 how do you do the inference or to to do the inference。

 we need to now estimate these mean and standard deviation once over the entire training set。

 and then use those at inference。

![](img/88dd9899d3a9ef459d32c32418af4090_408.png)

![](img/88dd9899d3a9ef459d32c32418af4090_409.png)

But then no one likes to do stage 2。 So instead we fold everything into the baization layer during training and try to estimate these in the running manner so that everything is a bit simpler。

And that gives us the best normalization layer。

![](img/88dd9899d3a9ef459d32c32418af4090_411.png)

And as I mentioned， no one likes this layer。 It causes a huge amount of bugs。 And intuitively。

 it's because it is coupling examples in the forecast pass of a neural net。

And I've shot myself in the foot with this layer over and over again in my life。

 And I don't want you to suffer the same。So basically try to avoid it as much as possible。

 some of the other alternatives to these layers are， for example。

 group normalization or layer normalization， and those have become more common in more recent deep learning。

 but we haven't covered those yet。But definitely， baization was very influential at the time when it came out in roughly 2015。

 because it was kind of the first time that you could train reliably much deeper neural nuts。

 And fundamentally， the reason for that is because this layer was very effective at controlling the statistics of the activations in a neural nu。



![](img/88dd9899d3a9ef459d32c32418af4090_413.png)

So that's the story so far and that's all I wanted to cover and in the future lecture hopefully we can start going into recurringcur neural net and recurringcurrent neural nets。

 as we'll see， are just very， very deep networks because you unroll the loop and when you actually optimize these neural net。

And that's where a lot of this。Analysis around the activation statistics and all these normalization layers will become very。

 very important for good performance， so we'll see that next time by。



![](img/88dd9899d3a9ef459d32c32418af4090_415.png)

Okay， so I lied。 I would like us to do one more summary here as a bonus。

 and I think it's useful as to have one more summary of everything I've presented in this lecture。

 But also， I would like us to start by torifying our code a little bit。

 So it looks much more like what you would encounter in Ptorrch。

So you'll see that I will structure our code into these modules like a linear module and a batchor module。

 and I'm putting the code inside these modules so that we can construct neural networks very much like we would construct them in Pytorch and I will go through this in detail。



![](img/88dd9899d3a9ef459d32c32418af4090_417.png)

![](img/88dd9899d3a9ef459d32c32418af4090_418.png)

So we'll create our neural net。Then we will do the optimization loop， as we did before。



![](img/88dd9899d3a9ef459d32c32418af4090_420.png)

And then the one more thing that I want to do here is I want to look at the activation statistics both in the forward pass and in the backward pass。

 and then here we have the evaluation and sampling just like before。



![](img/88dd9899d3a9ef459d32c32418af4090_422.png)

So let me rewind all the way up here and go a little bit slower。



![](img/88dd9899d3a9ef459d32c32418af4090_424.png)

So here I am creating a linear layer。You'll notice that torch shot NN has lots of different types of layers。

 and one of those layers is the linear layer。Tot and end linearar takes a number of input features。

 output features， whether or not we should have bias。

 and then the device that we want to place this layer on and the data type。So I will omit these two。

 but otherwise， we have the exact same thing。 We have the fan in， which is the number of inputs。

 fan out， the number of outputs。 and whether or not we want to use a bias。



![](img/88dd9899d3a9ef459d32c32418af4090_426.png)

And internally， inside this layer， there's a weight and a bias， if you'd like it。

It is typical to initialize the weight using， say random numbers drawn from a Gaussian。

 and then here's the coming initialization that we discussed already in this lecture。

 and that's a good default and also the default that I believe Pytor choose。And by default。

 the bias is usually initialized to zeros。Now， when you call this module。

This will basically calculate W times x plus B， if you have N B。

And then when you also call that parameters on this module。

 it will return the tensors that are the parameters of this layer。



![](img/88dd9899d3a9ef459d32c32418af4090_428.png)

Now， next， we have the batch normalization layer。 So I've written that here and。



![](img/88dd9899d3a9ef459d32c32418af4090_430.png)

This is very similar to Pytorch N N dot bashor 1 D layer， as shown here。



![](img/88dd9899d3a9ef459d32c32418af4090_432.png)

So I'm kind of taking these three parameters here， the dimensionality。

 the epsilon that we will use in the division， and the momentum that we will use in keeping track of these running stats。

 the running mean and the running variance。Now P actually takes quite a few more things。

 but I'm assuming some in their settings。 So for us， I find will be true。

 that means that we will be using a gamma and beta after general normalization。

The track running stats will be true， so we will be keeping track of the running mean and the running variance in the bathroom。

Our device by default is the CPU and the data type by default is float。F 32。

So those are the defaults。 Otherwise， we are taking all the same parameters in this bathroom layer。

 So first， I'm just saving them。Now here's something new。

 there's dot training which by default is true， and Pyr andN modules also have this attribute thatt training。

 and that's because many modules and batchor is included in that have a different behavior whether you are training your neural or or whether you are running it in an evaluation mode and calculating your evaluation laws or using it for inference on some test examples。

And Bashm is an example of this because when we are training。

 we are going to be using the mean and the variance estimated from the current batch。

During inference， we are using the running mean and running variance。And so also if we are training。

 we are updating mean and variance， but if we are testing。

 then these are not being updated they're kept fixed。

And so this flag is necessary and by default true， just like intorrch。Now。

 the parameters of batch 1 D are the gamma and the beta here。

And then the running mean and running variants are called buffers in Pytor nomenclature。

And these buffers are trained using exponential moving average here explicitly。

 And they are not part of the back propagation of stochastic gradienting descent。

 So they are not sort of like parameters of this layer。

 And that's why when we calculate when we have a parameters here。 We only return gamma beta。

 We do not return the mean and a variance， this is trained sort of like internally here every forward pass using exponential moving average。

So that's the initialization。

![](img/88dd9899d3a9ef459d32c32418af4090_434.png)

Now in a forward pass， if we are training， then we use the mean and variance estimated by the batch。

Let me block the paper here。We calculated the mean and variance。 Now， up above。

 I was estimating the standard deviation and keeping track of the standard deviation。

Here in the running standard deviation instead of running variance。

 but let's follow the paper exactly here， they calculate the variance。

 which is a standard deviation squared， and that's what's kept track of in the running variance instead of running standard deviation。

But those two would be very， very similar， I believe。If we are not training。

 then we use the running Min areas。We normalize。And then here I am calculating the output of this layer。

 and I'm also assigning it to an attribute called dot out。

Now dot out is something that I'm using in our modules here。

 this is not what you would find in Pytorrch we are slightly devitating from it。

 I'm creating a dot out because I would like to very easily maintain all those variables so that we can create statistics of them and plot them。

 but Pytorrch and modules will not have a dot out attribute。



![](img/88dd9899d3a9ef459d32c32418af4090_436.png)

![](img/88dd9899d3a9ef459d32c32418af4090_437.png)

And finally， here we are updating the buffers using， again， as I mentioned。

 exponential moving average。Provide given the provided momentum， and importantly。

 you'll notice that I'm using the Torscht nograd context manager。

And I am doing this because if we don't use this， then Pytorch will start building out an entire computational graph out of these tensors。

 because it is expecting that we will eventually call it that backward。

But we are never going to be calling that backward on anything that includes running mean and running variance。

 so that's why we need to use this contact manager so that we are not sort of maintaining them using all this additional memory So this will make it more efficient and it's just telling pythtors that they already know backward We just have a bunch of tensors we want to update them。

 that's it。

![](img/88dd9899d3a9ef459d32c32418af4090_439.png)

And then we return。

![](img/88dd9899d3a9ef459d32c32418af4090_441.png)

Okay， now scrolling down， we have the 10h layer。 this is very。

 very similar to Torch do 10h and it doesn't do too much。 It just calculates 10h as you might expect。

 so that's torchdo 10h and there's no parameters in this layer。



![](img/88dd9899d3a9ef459d32c32418af4090_443.png)

![](img/88dd9899d3a9ef459d32c32418af4090_444.png)

![](img/88dd9899d3a9ef459d32c32418af4090_445.png)

But because these are layers， it now becomes very easy to sort of like stack them up into basically just a list。

And we can do all the initializations that we're used to。

 So we have the initial sort of embedding matrix。 we have our layers。

 and we can call them sequentially。

![](img/88dd9899d3a9ef459d32c32418af4090_447.png)

![](img/88dd9899d3a9ef459d32c32418af4090_448.png)

And then again， with Tosha Nograd， there's some initializations here。

 so we want to make the output Somax a bit less confident like we saw。And in addition to that。

 because we are using a six layer multi layer perron here。 So you see how I'm stacking linear10age。

 linear10age， etc cetera。I'm going to be using the game here。

 and I'm going to play with this in a second， so you'll see how when we change this。

 what happens to the statistics。

![](img/88dd9899d3a9ef459d32c32418af4090_450.png)

Finally， the parameters are basically the embedding matrix and all the parameters in all the layers。

 And notice here， I'm using a double list comprehension。 If you want to call it that。

 but for every layer in layers and for every parameter in each of those layers。

 we are just stacking up all those pieces， all those parameters。Now， in total， we have 46。

000 parameters。

![](img/88dd9899d3a9ef459d32c32418af4090_452.png)

And I'm telling patterns that all of them require gradient。



![](img/88dd9899d3a9ef459d32c32418af4090_454.png)

![](img/88dd9899d3a9ef459d32c32418af4090_455.png)

Then here we have everything here。 we are actually mostly used to。 We are sampling batch。

 We are doing forward pass。 The forward pass now is just the linear application of all the layers in order。



![](img/88dd9899d3a9ef459d32c32418af4090_457.png)

![](img/88dd9899d3a9ef459d32c32418af4090_458.png)

Followed by the cross entropy。And then in the backward pass。

 you'll notice that for every single layer， I now iterate over all the outputs。

 and I'm telling Pytorch to retain the gradient of them。

And then here we are already used to all the gradient set to none。

 do the backward to fill in the gradients， do an update using stochastic gradient send。

 and then track some statistics。

![](img/88dd9899d3a9ef459d32c32418af4090_460.png)

![](img/88dd9899d3a9ef459d32c32418af4090_461.png)

And then I am going to break after a single iteration。 Now， here in this cell in this diagram。

 I am visualizing theograms， the histograms of the four pass activations。

 and I am specifically doing it at the 10 H layers。



![](img/88dd9899d3a9ef459d32c32418af4090_463.png)

So iterating over all the layers， except for the very last one。

 which is basically just the softm layer。If it is a 10h layer and I'm using a 10H layer just because they have a finite output。

 negative one to one， and so it's very easy to visualize here。

 so you see negative one to one and it's a finite range and easy to work with。

I take the out tensor from that layer into T， and then I'm calculating the mean。

 the standard deviation and the percent saturation of T。

And the way I define the percent saturation is that T dot absolute value is greater than 0。97。

 So that means we are here at the tails of the 10 H。

 And remember that when we are in the tails of the 10 H， that will actually stop gradients。

 So we don't want this to be too high。

![](img/88dd9899d3a9ef459d32c32418af4090_465.png)

Now。Here， I'm calling Tor shot histogram。 And then I am plotting this histogram。 So basically。

 what this is doing is that every different type of layer and they all have a different color。

 We are looking at how many。

![](img/88dd9899d3a9ef459d32c32418af4090_467.png)

Values in these tensors take on any of the values below on this axis here。

So the first layer is fairly saturated here at 20% so you can see that it's got tails here。

 but then everything sort of stabilizes， and if we had more layers here。

 it would actually just stabilize at around the standard deviation of about 。65。

 and the saturation will be roughly 5%。And the reason that this stabilizes and gives us a nice distribution here is because gain is sets to 5 over3。



![](img/88dd9899d3a9ef459d32c32418af4090_469.png)

Now， here this gain， you see that by default， we initialize with one over squared root of fanin。



![](img/88dd9899d3a9ef459d32c32418af4090_471.png)

![](img/88dd9899d3a9ef459d32c32418af4090_472.png)

But then here， during initialization， I come in and I iterate all the layers。

 And if it's a linear layer， I boost that by the game。Now we saw that one， so basically。

 if we just do not use a game， then what happens。

![](img/88dd9899d3a9ef459d32c32418af4090_474.png)

If I withdrawraw this。You will see that。The standard deviation is shrinking。

And the saturation is coming to 0。And basically， what's happening is the first layer is， you know。

 pretty decent。 but then further layers are just kind of like shrinking down to 0。

 and it's happening slowly， but it's shrinking to 0。 And the reason for that is。

When you just have a sandwich of linear layers alone， then a。

 then initializing our weights in this manner， we saw previously would have conserved the standard deviation of one。

 But because we have this interspersed 10 H layers in there。



![](img/88dd9899d3a9ef459d32c32418af4090_476.png)

![](img/88dd9899d3a9ef459d32c32418af4090_477.png)

![](img/88dd9899d3a9ef459d32c32418af4090_478.png)

![](img/88dd9899d3a9ef459d32c32418af4090_479.png)

The stalin layers are squashing functions， and so they take your distribution and they slightly squash it。

 And so some gain is necessary to keep expanding it， to fight the squashing。

So it just turns out that 5 over three is a good value。 So if we have something too small like one。

 we saw that things will。

![](img/88dd9899d3a9ef459d32c32418af4090_481.png)

![](img/88dd9899d3a9ef459d32c32418af4090_482.png)

Come towards zero， but if it's something too high， let's do two。



![](img/88dd9899d3a9ef459d32c32418af4090_484.png)

Then here we see that。

![](img/88dd9899d3a9ef459d32c32418af4090_486.png)

Well， let me do something a bit more extreme because so it's a bit more visible。 Let's try3。



![](img/88dd9899d3a9ef459d32c32418af4090_488.png)

Okay， so we see here that the saturations are going to be way too large。



![](img/88dd9899d3a9ef459d32c32418af4090_490.png)

Okay， so three would create way too saturated activations。



![](img/88dd9899d3a9ef459d32c32418af4090_492.png)

So five over three is a good setting。For a sandwich of linear layers with 10 in activations。

 And it roughly stabilizes the standard deviation at a reasonable point。



![](img/88dd9899d3a9ef459d32c32418af4090_494.png)

![](img/88dd9899d3a9ef459d32c32418af4090_495.png)

Now， honestly， I have no idea where5 over3 came from in Pytorch when we were looking at the coming initialization。

 I see empirically that it stabilizes this sandwich of linear and 10h。

 and that the saturation is in a good range， but I don't actually know if this came out of some math formula。

 I tried searching briefly for where this comes from but I wasn't able to find anything。

 but certainly we see that empirically these are very nice ranges。

 our saturation is roughly 5% which is a pretty good number。

 and this is a good setting of the gain in this context。 Similarlyly。

 we can do the exact same thing with the gradients。 So here is a very same loop if it's a 10h。

 but instead of taking the layer that out， I'm taking the grad。

 and then I'm also showing the mean and thecent deviation。

 and I'm plotting the histogram of these values。

![](img/88dd9899d3a9ef459d32c32418af4090_497.png)

![](img/88dd9899d3a9ef459d32c32418af4090_498.png)

![](img/88dd9899d3a9ef459d32c32418af4090_499.png)

![](img/88dd9899d3a9ef459d32c32418af4090_500.png)

And so youll see that the gradient distribution is fairly reasonable， and in particular。

 what we're looking for is that all the different layers in this sandwich has roughly the same gradient。

 Things are not shrinking or exploding。

![](img/88dd9899d3a9ef459d32c32418af4090_502.png)

So we can， for example， come here and we can take a look at what happens if this gain was way too small。

 so this was 0。5。

![](img/88dd9899d3a9ef459d32c32418af4090_504.png)

![](img/88dd9899d3a9ef459d32c32418af4090_505.png)

Then， you see the。First of all， the activations are shrinking to zero。

 but also the gradients are doing something weird。 The gradients started out here。

 and then now they're like expanding out。

![](img/88dd9899d3a9ef459d32c32418af4090_507.png)

And similarly， if we， for example， have a too high of a gain， select three。



![](img/88dd9899d3a9ef459d32c32418af4090_509.png)

Then we see that also the gradients have there's some asymmetry going on where as you go into deeper and deeper layers。

 the activations are also changing。

![](img/88dd9899d3a9ef459d32c32418af4090_511.png)

And so that's not what we want。 And in this case， we saw that without the use of Bashm。

 as we are going through right now， we have to very carefully set those gains to get nice activations in both the forward pass and the backward pass。

 Now before we move on to batch normalization， I would also like to take a look at what happens when we have no 108 units here。

 So erasing all the 10age non nonlinearities。😊。

![](img/88dd9899d3a9ef459d32c32418af4090_513.png)

![](img/88dd9899d3a9ef459d32c32418af4090_514.png)

![](img/88dd9899d3a9ef459d32c32418af4090_515.png)

![](img/88dd9899d3a9ef459d32c32418af4090_516.png)

![](img/88dd9899d3a9ef459d32c32418af4090_517.png)

But keeping the game at 5 over 3， we now have just a giant linear sandwich。

 So let's see what happens to the activations。

![](img/88dd9899d3a9ef459d32c32418af4090_519.png)

As we saw before， the correct gain here is one。 That is the standard deviation preserving gain。 So 1。

667 is too high。

![](img/88dd9899d3a9ef459d32c32418af4090_521.png)

And so what's going to happen now is the following。



![](img/88dd9899d3a9ef459d32c32418af4090_523.png)

I have to change this to be linear， so we are。

![](img/88dd9899d3a9ef459d32c32418af4090_525.png)

Because there's no more 10H players。And let me change this tool linear here， as well。



![](img/88dd9899d3a9ef459d32c32418af4090_527.png)

So， what we're seeing is。The activations started out on the blue， and have。

By layer 4 become very diffuse。 So what's happening to the activations is this。



![](img/88dd9899d3a9ef459d32c32418af4090_529.png)

And with the gradients on the top layer， the activation， the gradient statistics are the purple。

 And then they diminish as you go down deeper in the layers。 And so basically， you have an asymmetry。

 like in the neural net。 And you might imagine that if you have very deep neural networks。

 say like 50 layers or something like that。 this just this is not a good place to be。

 So that's why before ba normalization， this was incredibly tricky to， to set。 in particular。

 if this is too large of a game， this happens。 And if it's too little of a gain。



![](img/88dd9899d3a9ef459d32c32418af4090_531.png)

![](img/88dd9899d3a9ef459d32c32418af4090_532.png)

![](img/88dd9899d3a9ef459d32c32418af4090_533.png)

Then this happens。 Also， the opposite of that basically happens Here。 We have a。



![](img/88dd9899d3a9ef459d32c32418af4090_535.png)

![](img/88dd9899d3a9ef459d32c32418af4090_536.png)

Shrinkking。And a。Diffusion， depending on which direction you look at it from。



![](img/88dd9899d3a9ef459d32c32418af4090_538.png)

And so certainly， this is not what you want。 And in this case。

 the correct setting of the gain is exactly one。

![](img/88dd9899d3a9ef459d32c32418af4090_540.png)

Just like we're doing at initialization。 And then we see that。



![](img/88dd9899d3a9ef459d32c32418af4090_542.png)

The statistics for the forward and the backward pass are well behaved。



![](img/88dd9899d3a9ef459d32c32418af4090_544.png)

And so the reason I want to show you this is。But， basically， like。

Getting neuralness to train before these normalization layers and before the use of advanced optimizers like atom。

 which we still have to cover and residual connections and so on。

 Tra neurals basically looked like this。 It's like a total balancing act。

 You have to make sure that everything is precisely orchestrated。

 and you have to care about the activations and ingredients gradient and their statistics。

 and then maybe you can train something。 But it was basically impossible to train very deep networks。

 And this is fundamentally the reason for that。 you'd have to be very。

 very careful with your initialization。

![](img/88dd9899d3a9ef459d32c32418af4090_546.png)

The other point here is。You might be asking yourself， by way。 I'm not sure if I covered this。

 Why do we need these 10 H layers at all？ Why do we include them and then have to worry about the game。

And the reason for that， of course， is that if you just have a stack of linear layers。Then certainly。

 we're getting very easily nice activations and so on。 But this is just a massive linear sandwich。

 And it turns out that it collapses to a single linear layer in terms of its representation power。

 So if you were to plot the output as a function of the input， you're just getting a linear function。

 No matter how many linear layers you stack up， you still just end up with a linear transformation。

 All the W X plus B's just collapse into large W X plus B with slightly different Ws as slightly different B。

😊，But interestingly， even though the forward pass collapses to just a linear layer because of back propagation and the dynamics of the backward pass。

 the optimization is really is not identical。 You actually end up with all kinds of interesting。

Dynamics in the backward pass because of the way the chain rule is calculating it。

 And so optimizing a linear layer by itself and optimizing a sandwich of 10 linear layers。

 In both cases， those are just a linear transformation in the forward pass。

 but the training dynamics would be different。 And there's entire papers that analyze， in fact。

 like infinitely layered linear layers and so on。 And so there's a lot of things too that you can play with there。

But basically， the tenalurities allow us to。Turn this sandwich from just a linear。

Function into a neural network that can， in principle， approximate any arbitrary function。



![](img/88dd9899d3a9ef459d32c32418af4090_548.png)

Okay， so now I've reset the code to use the linear tanh sandwich like before。

 and I've reset everything so the gains 5 over 3， we can run a single step of optimization and we can look at the activation statistics of the forward pass and the backward pass。



![](img/88dd9899d3a9ef459d32c32418af4090_550.png)

![](img/88dd9899d3a9ef459d32c32418af4090_551.png)

![](img/88dd9899d3a9ef459d32c32418af4090_552.png)

But I've added one more plot here that I think is really important to look at when you're training your neural nuts and to consider。



![](img/88dd9899d3a9ef459d32c32418af4090_554.png)

And ultimately， what we're doing is we're updating the parameters of the neural net。

 so we care about the parameters and their values and their gradients。

So here what I'm doing is I'm actually iterating over all the parameters available。

 and that I'm only restricting it to the two dimensional parameters。

 which are basically the weights of these linear layers。

 and I'm skipping the biasis and I'm skipping the。Gammas and the betas in the bathroom。

 just for simplicity。

![](img/88dd9899d3a9ef459d32c32418af4090_556.png)

But you can also take a look at those as well。 But what's happening with the weights is instructive by itself。

So here we have all the different weights， their shapes。So this is the embedding layer。

 the first linear layer， all the way to the very last linear layer， and then we have the mean。

 the standard deviation of all these primers。The histogram and you can see that it actually doesn't look that amazing。

 so there's some trouble in paradise， even though these gradients looked okay。

 there's something weird going on here， I'll get to that in a second。



![](img/88dd9899d3a9ef459d32c32418af4090_558.png)

And the last thing here is the gradient to data ratio。 So sometimes I like to visualize this as well。

 because what this gives you a sense of is what is the scale of the gradient compared to the scale of the actual values。

 and this is important because we're going to end up taking a step update。

That is the learning rate times the gradient on the data。

And so if the gradient has too large of magnitude。 If the numbers in there are too large compared to the numbers in data。

 then you'd be in trouble。But in this case， the gradient to data is are low numbers。

 So the values inside grad are 1000 times smaller than the values inside data in these weights。

 most of them。Now， notably， that is not true about the last layer。



![](img/88dd9899d3a9ef459d32c32418af4090_560.png)

And so the last layer， actually here， the output layer is a bit of a trouble maker in the way that this is currently arranged。

 because you can see that the。Last layer here in pink。

Takes on values that are much larger than some of the values inside。insideside the neural lot。

 so the standard deviations are roughly one in negative 3 throughout， except for the last layer。

 which actually has roughly one in negative2 standard deviation gradients。

And so the gradients on the last layer are currently about 100 times greater。 Sorry。

10 times greater than all the other weights inside the neural nut。And so that's problematic。

 because in the simple stochasticity in the sun setup。

 you would be training this last layer about 10 times faster than you would be training the other layers at initialization。



![](img/88dd9899d3a9ef459d32c32418af4090_562.png)

Now， this actually like kind of fixes itself a little bit if you train for a bit longer。

 So for example， if I greater than 1000。Only then do a break。



![](img/88dd9899d3a9ef459d32c32418af4090_564.png)

Let me re initialitialize and then let me do it 1000 steps。And after 1000 steps。

 we can look at the forward pass。

![](img/88dd9899d3a9ef459d32c32418af4090_566.png)

Okay， so you see how the neurons are saturating a bit。



![](img/88dd9899d3a9ef459d32c32418af4090_568.png)

And we can also look at the back path。 but otherwise they look good。 They're about equal。

 and there's no shrinking to 0 or exploding to infinities。



![](img/88dd9899d3a9ef459d32c32418af4090_570.png)

![](img/88dd9899d3a9ef459d32c32418af4090_571.png)

And you can see that here in the weights， things are also stabilizing a little bit。

 So the tails of the last pink layer are actually coming coming in during the optimization。

But certainly， this is like a little bit of troubling。

 especially if you are using a very simple update rule like stochastic gradient and descent instead of a modern optimizer like Adam。



![](img/88dd9899d3a9ef459d32c32418af4090_573.png)

Now I'd like to show you one more plot that I usually look at when I train neural own networks and basically the gradient to data ratio is not actually that informative because what matters at the end is not the gradient to data ratio。

 but the update to the data ratio， because that is the amount by which we will actually change the data in these tensors。



![](img/88dd9899d3a9ef459d32c32418af4090_575.png)

So coming up here。What I'd like to do is I'd like to introduce a new update to data ratio。

It's going to be less and we're going to build it out every single iteration。



![](img/88dd9899d3a9ef459d32c32418af4090_577.png)

And here I'd like to keep track of， basically。The ratio。Every single iteration。So。

Without any ingredientsance。I'm comparing the update。

 which is learning rate times times the gradient。That is the update that we're going to apply to every parameter。

Soci me over the parameters， and then I'm taking the basically standard deviation of the update we're going to apply and divided by the actual content。

 the data of that parameter and its standard deviation。

So this is the ratio of basically how great are the updates to the values in these tensors？

They were going to take a log of it。 And actually， I'd like to take a log 10。



![](img/88dd9899d3a9ef459d32c32418af4090_579.png)

嗯。Just so it's a nicer visualization。 So we're going to be basically looking at the exponents of the。

And down。Of this division here。 And then that item to pop out the float。

And we're going to be keeping track of this for all the parameters and adding it to this UD tensor。



![](img/88dd9899d3a9ef459d32c32418af4090_581.png)

So now let me re initialize and run 1000 iterations。



![](img/88dd9899d3a9ef459d32c32418af4090_583.png)

We can look at the activations， the gradients， and the parameter gradients as we did before。



![](img/88dd9899d3a9ef459d32c32418af4090_585.png)

But now I have one more plot here to introduce。

![](img/88dd9899d3a9ef459d32c32418af4090_587.png)

And what's happening here is where every interval gold parameters。 And I'm constraining it again。

 like I did here to just a weights。

![](img/88dd9899d3a9ef459d32c32418af4090_589.png)

So the number of dimensions in these sensors is too。

And then I'm basically plotting all of these update ratios over time。



![](img/88dd9899d3a9ef459d32c32418af4090_591.png)

So when I plot this。

![](img/88dd9899d3a9ef459d32c32418af4090_593.png)

I plot those ratios， and you can see that they evolve over time during initialization to take on certain values。

 and then these updates that like start stabilizing usually during training。

Then the other thing that I'm plotting here is I'm plotting here like an approximate value that is a rough guide for what it roughly should be。

 and it should be like roughly one in negative 3。And so that means that basically。

 theres some values in the ssor， and they take on certain values。

 and the updates to them at every single iteration are no more than roughly 1000th。

Of the actual like magnitude in those tensors。If this was much larger， like for example， if this was。

If the log of this was like say Ne one， this is actually updating those values quite a lot。

 They're undergoing a lot of change。But the reason that the final rate。

 the final layer here is an outlier is because this layer was artificially shr down to keep the softm uncompetdent。



![](img/88dd9899d3a9ef459d32c32418af4090_595.png)

So， here。

![](img/88dd9899d3a9ef459d32c32418af4090_597.png)

You see how we multiply the weight by 。1。In the initialization to make the last layer prediction less confident。



![](img/88dd9899d3a9ef459d32c32418af4090_599.png)

That made that artificially made the values inside that tensor way too low。

 And that's why we're getting temporarily at very high ratio。

 But you see that that stabilizes over time once that weight starts to， starts to learn。



![](img/88dd9899d3a9ef459d32c32418af4090_601.png)

![](img/88dd9899d3a9ef459d32c32418af4090_602.png)

But basically， I like to look at the evolution of this update ratio for all my parameters， usually。

 and I like to make sure that it's not too much above one in negative 3， roughly。



![](img/88dd9899d3a9ef459d32c32418af4090_604.png)

So around negative 3 on this log plot。If it's below negative3。

 usually that means that the parameters are not trained fast enough。



![](img/88dd9899d3a9ef459d32c32418af4090_606.png)

So if our learning rate was very low， let's do that experiment。



![](img/88dd9899d3a9ef459d32c32418af4090_608.png)

Let's initialize， and then let's actually do a learning rate of say， 10 negative 3 here。So 0。001。

If your learning rate is way too low。

![](img/88dd9899d3a9ef459d32c32418af4090_610.png)

This plot will typically reveal it。So you see how all of these updates are way too small。

 So the size of the update is basically 10000 times in magnitude to the size of the numbers in that tensor in first place。

 So this is a symptom of training way too slow。

![](img/88dd9899d3a9ef459d32c32418af4090_612.png)

So this is another way to sometimes set the learning rate and to get a sense of what that learning way should be。

 and ultimately this is something that you would keep track of。



![](img/88dd9899d3a9ef459d32c32418af4090_614.png)

![](img/88dd9899d3a9ef459d32c32418af4090_615.png)

If anything， the learning rate here is a little bit on the higher side， because you see that。



![](img/88dd9899d3a9ef459d32c32418af4090_617.png)

Were above the black line of negative3， where're somewhere around negative 2。5。 It's like， okay。 And。

 but everything is like somewhat stabilizing。 And so this looks like a pretty decent setting of。

 of learning rates and so on。 But this is something to look at。 And when things are miscalibrated。

 you will， you will see very quickly。 So， for example。



![](img/88dd9899d3a9ef459d32c32418af4090_619.png)

![](img/88dd9899d3a9ef459d32c32418af4090_620.png)

![](img/88dd9899d3a9ef459d32c32418af4090_621.png)

Everything looks pretty well behaved， right？ But just as a comparison。

 when things are not properly calibrated， what does that look like。



![](img/88dd9899d3a9ef459d32c32418af4090_623.png)

Let me come up here and let's say that for example， what do we do？



![](img/88dd9899d3a9ef459d32c32418af4090_625.png)

Let's say that we forgot to apply this fan in normalization。

 so the weights inside the linear layers are just sample from aGosian in all the stages。



![](img/88dd9899d3a9ef459d32c32418af4090_627.png)

What happens to our， how do we notice that something's off。Well， the activation plot will tell you。

 whoa， your neurons are way too saturated。

![](img/88dd9899d3a9ef459d32c32418af4090_629.png)

The ingredientss are going to be all messed up。

![](img/88dd9899d3a9ef459d32c32418af4090_631.png)

The histogram for these weights are going to be all messed up as well。

 And there's a lot of asymmetry。 And then if we look here。

 I suspect it's all going to be also pretty messed up。 So you see。

 there's a lot of discrepancy in how fast these layers are learning。

 and some of them are learning way too fast。 So negative1， negative 1。5。

 Those are very large numbers in terms of this ratio。 Again。

 you should be somewhere on negative 3 and not much more about that。

 So this is how miscalibrations of your neural neurons are going to manifest。

 And these kinds of plots here are a good way of sort of bringing those miscalibrations sort of。



![](img/88dd9899d3a9ef459d32c32418af4090_633.png)

![](img/88dd9899d3a9ef459d32c32418af4090_634.png)

![](img/88dd9899d3a9ef459d32c32418af4090_635.png)

![](img/88dd9899d3a9ef459d32c32418af4090_636.png)

啊。To your attention and so you can address them。Okay。

 so so far we've seen that when we have this linear 10 H sandwich。

 we can actually precisely calibrate the gains and make the activations。

 the gradients and the parameters， and the updates all look pretty decent。



![](img/88dd9899d3a9ef459d32c32418af4090_638.png)

![](img/88dd9899d3a9ef459d32c32418af4090_639.png)

But it definitely feels a little bit like balancing。Of a pencil on your finger。

And that's because this gain has to be very precisely calibrated。



![](img/88dd9899d3a9ef459d32c32418af4090_641.png)

So now let's introduce batchization layers into the into the mix。

 and let's see how that helps fix the problem。

![](img/88dd9899d3a9ef459d32c32418af4090_643.png)

So， here。

![](img/88dd9899d3a9ef459d32c32418af4090_645.png)

I'm going to take the baachelor one class。And I'm going to start placing it inside。

And as I mentioned before， the standard typical place you would place it is between the linear layer。

 so right after it， but before the nonlinearity， but people have definitely played with that and in fact you can get very similar results even if you place it after the nonlinearity。



![](img/88dd9899d3a9ef459d32c32418af4090_647.png)

And the other thing that I wanted to mention is it's totally fine to also place it at the end after the last linear layer and before the loss function。

 so this is potentially fine as well。And in this case， this would be output would be world cap size。

Now， because the last layer is beroom。We would not be changing the weight to make the optm less confident。

 We'd be changing the gamma。Because gamma， remember， in the ba。

 is the variable that multiplicatively interacts with the output of that normalization。

So we can initialize this sandwich now， we can train。

 and we can see that the activations are going to， of course， look very good。

 and they are going to necessarily look good because now before every single 10 H layer。

 there is a normalization in the bashlor。 So this is unsurprisingly， all looks pretty good。

 It's going to be standard deviation of roughly 。652% and roughly equals standard deviation throughout the entire layers。

 So everything looks very homogeneous。

![](img/88dd9899d3a9ef459d32c32418af4090_649.png)

The gradients look good。 The weights look good， and their distributions。And then the updates。



![](img/88dd9899d3a9ef459d32c32418af4090_651.png)

Also， look pretty reasonable。 We're going above negative 3 a little bit， but not by too much。

 So all the parameters are training at roughly the same rate here。

But now what we've gained is we are going to be slightly less。

Brittle with respect to the gain of these。 So， for example， I can make the gain B say 。2 here。嗯。

Which was much less mark or slower than what we had with the 10 H。But as we'll see。

 the activations will actually be exactly unaffected。And that's because of again。

 this explicit normalization， the gradients are going to look okay。

 the weight gradients are going to look okay， but actually the updates will change。



![](img/88dd9899d3a9ef459d32c32418af4090_653.png)

And so。Even though the forward and backward path to a very large extent look。

 O because of the backward pass of the bashhom and how the scale of the incoming activations interacts in the bashho and its backward pass。

 this is actually changing the。The scale of the updates on these parameters。

 So the gradients of these weights are affected。So we still don't get a completely free pass to pass in arbitrary weights here。

But everything else is significantly more robust。In terms of the forward。

 backward and the weight gradients， it's just that you may have to reune your learning rate if you are changing sufficiently。

 the scale of the activation that are coming into the bashlors。



![](img/88dd9899d3a9ef459d32c32418af4090_655.png)

So here， for example， this we changed the gains of these linear layers to be greater。

 and we're seeing that the updates are coming out lower as a result。



![](img/88dd9899d3a9ef459d32c32418af4090_657.png)

And then finally， we can also， if we are using batch roomss， we don't actually need to necessarily。

 Let me reset this to one， so there's no gain。We don't necessarily even have to normalize by thanin sometimes。

 So if I take out the fanin。 So these are just now random Gaussian。



![](img/88dd9899d3a9ef459d32c32418af4090_659.png)

We'll see that because of Ba， this will actually be relatively well behaved。So。The dishes look。

 of course， in the four path look good。 the gradients look good。The weight updates look okay。

 a little bit of fat tails in some of the layers。And this looks okay as well。 but as as you can see。

 we're significantly below negative 3， So we'd have to bump up the learning rate of this batch so that we are training more properly。

 and in particular， looking at this roughly looks like we have to 10 x the learning rate to get to about  one0 negative 3。

🤧うん。So we'd come here and we would change this to be update of 1。0。



![](img/88dd9899d3a9ef459d32c32418af4090_661.png)

And if then I re initialitialize。🤧。Then we'll see that everything still， of course， looks good。

And now we are roughly here， and we expect this to be an okay training run。



![](img/88dd9899d3a9ef459d32c32418af4090_663.png)

So long story short， we are significantly more robust to the gain of these linear layers。

 whether or not we have to apply the fanin。

![](img/88dd9899d3a9ef459d32c32418af4090_665.png)

And then we can change the game。 but we actually do have to worry a little bit about the update scales and making sure that the learning rate is properly calibrated here。

 But thus the activations of the forward backward path and the updates are all are looking significantly more well behaved except for the global scale that is potentially being adjusted here。



![](img/88dd9899d3a9ef459d32c32418af4090_667.png)

Okay， so now let me summarize。There are three things I was hoping to achieve with this section。

 Number one， I wanted to introduce you to batch normalization。

 which is one of the first modern innovations that we're looking into that helped stabilize very deep neural networks and their training。



![](img/88dd9899d3a9ef459d32c32418af4090_669.png)

And I hope you understand how the best normalization works and how it would be used in a neural network。



![](img/88dd9899d3a9ef459d32c32418af4090_671.png)

![](img/88dd9899d3a9ef459d32c32418af4090_672.png)

Number two， I was hoping to p torify some of our code and wrap it up into these modules。

 so like linear， balor 1D， 10H， etca， these are layers or modules。



![](img/88dd9899d3a9ef459d32c32418af4090_674.png)

![](img/88dd9899d3a9ef459d32c32418af4090_675.png)

And they can be stacked up into neural nets like Lego building blocks。



![](img/88dd9899d3a9ef459d32c32418af4090_677.png)

And these layers actually exist in Pytorch。 And if you import torch N N。

 then you can actually the way I've constructed it。

 you can simply just use Pytorrch by prepending N N dot。



![](img/88dd9899d3a9ef459d32c32418af4090_679.png)

To all these different layers。And。Actually， everything will just work because the API that I've developed here is identical to the API that PyTtor chooses。



![](img/88dd9899d3a9ef459d32c32418af4090_681.png)

And the implementation also is basically， as far as I'm aware， identical to the one in Pyttorch。



![](img/88dd9899d3a9ef459d32c32418af4090_683.png)

And number3， I tried to introduce you to the diagnostic tools that you would use to understand whether your neural network is in a good state dynamically。

 So we are looking at the statistics and histograms and activation of the former path activations。



![](img/88dd9899d3a9ef459d32c32418af4090_685.png)

![](img/88dd9899d3a9ef459d32c32418af4090_686.png)

![](img/88dd9899d3a9ef459d32c32418af4090_687.png)

The backward pass gradient。And then also we're looking at the weights that are going to be updated as part of stoocastic gradientity asscent。

 and we're looking at their means standard deviations， and also the ratio of gradients to data。

 or even better the updates to data。

![](img/88dd9899d3a9ef459d32c32418af4090_689.png)

![](img/88dd9899d3a9ef459d32c32418af4090_690.png)

And we saw that typically we don't actually look at it as a single snapshot frozen in time at some particular iteration。

 typicallyyp people look at this as over time， just like I've done here。

 and they look at these update to data ratios and they make sure everything looks okay。

 and in particular， I said that one0 negative 3 or basically negative3 on the lock scale is a good rough heuristic for what you want this ratio to be and if it's way too high。

 then probably the learning rate or the updates are little too too big and if it's way too small that the learning rate is probably too small。

So that's just some of the things that you may want to play with when you try to get your neural network to work web very well。



![](img/88dd9899d3a9ef459d32c32418af4090_692.png)

![](img/88dd9899d3a9ef459d32c32418af4090_693.png)

Now， there's a number of things I did not try to achieve。

 I did not try to beat our previous performance as an example by introducing the ba layer。 Actually。

 I did try， and I found that I used the learning rate finding mechanism that I've described before。

 I tried to train the bache layer， a ba neural nu， and I actually ended up with results that are very。

 very similar to what we've obtained before。

![](img/88dd9899d3a9ef459d32c32418af4090_695.png)

![](img/88dd9899d3a9ef459d32c32418af4090_696.png)

![](img/88dd9899d3a9ef459d32c32418af4090_697.png)

And that's because our performance now is not bottlenecked by the optimization。

 which is what Basorm is helping with。The performance at this stage is bottlene by what I suspect is the context length of our context。

So currently， we are taking three characterss to predict the fourth one。

 and I think we need to go beyond that。 and we need to look at more powerful architectures like recurren neural networks and transformers in order to further push the like probabilities that we're achieving on this dataset。



![](img/88dd9899d3a9ef459d32c32418af4090_699.png)

And I also did not try to have a full explanation of all of these activations。

 the gradients and the backward path and the statistics of all these gradients。

 And so you may have found some of the parts here unintuitive。

 and maybe you were slightly confused about， okay， if I change the gain here。

 how come that we need a different learning rate。 And I didn't go into the full detail。

 because you'd have to actually look at the backward pass of all these different layers and get an intuitive understanding of how that works。

 And I did not go into that in this lecture。 The purpose really was just to introduce you to the diagnostic tools and what they look like。

 But there's still a lot of work remaining on the intuitive level to understand the initialization。

 the backward pass and how all that interacts。

![](img/88dd9899d3a9ef459d32c32418af4090_701.png)

![](img/88dd9899d3a9ef459d32c32418af4090_702.png)

![](img/88dd9899d3a9ef459d32c32418af4090_703.png)

![](img/88dd9899d3a9ef459d32c32418af4090_704.png)

![](img/88dd9899d3a9ef459d32c32418af4090_705.png)

![](img/88dd9899d3a9ef459d32c32418af4090_706.png)

But you shouldn't feel too bad because honestly， we are getting to the cutting edge of where the field is。

 We certainly haven't， I would say， solved initialization and we haven't solved back propagation And these are still very much an active area of research。

 People are still trying to figure out what is the best way to initialize these networks。

 What is the best update rule to use and so on。 So none of this is really solved。

 and we don't really have all the answers to all the。



![](img/88dd9899d3a9ef459d32c32418af4090_708.png)

![](img/88dd9899d3a9ef459d32c32418af4090_709.png)

To you know all these cases， but at least you know we're making progress and at least we have some tools to tell us whether or not things are on the right track for now。



![](img/88dd9899d3a9ef459d32c32418af4090_711.png)

![](img/88dd9899d3a9ef459d32c32418af4090_712.png)

So。I think we've made positive progress in this lecture。

 and I hope you enjoyed that and I will see you next time。



![](img/88dd9899d3a9ef459d32c32418af4090_714.png)