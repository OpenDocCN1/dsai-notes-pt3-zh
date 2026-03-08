# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p58 P58_L8.7.2_OneHot编码与多类别交叉熵_--_代码示例 -BV16EC5BUEi7_p58-

Yeah， as promised， let me know show you a brief code example illustrating the concept of the cross entropy in code using payytorch。



![](img/d7633ffbd2ad795f213c96187346d24b_1.png)

So I have prepared a notebook I will share it with you。 You can find the link as usual on canvas。

Or here just on Github。Me execute this just。

![](img/d7633ffbd2ad795f213c96187346d24b_3.png)

Regular boiler platelate。 So here I have a function for implementing the1 hot encoding in Pytorch。

 It looks a little bit arbitrary with this scatter function。



![](img/d7633ffbd2ad795f213c96187346d24b_5.png)

I don't really need to go over this because I think there is no other context where I think this scatter function is really that useful so you don't have to really memorize how this works if you ever need a1 hot encoding yourself you can just copy and paste this function and will do it for you and also。

When we do train a softm regression model later， I will show you also code example for that and the same for multilayer perceptrons and so forth。

 the loss functions in Pythwach， they already do the1 hot encoding for you so you actually never have to worry about it yourself。

But if you ever have to do it yourself here you can just copy and paste this function。

 So this is just yeah how it works。 This is exactly the same example that I showed you on the slides where we have the class labels 0。

1，2 and 2 and I have a total number of class labels here。

 this is the highest class label or the number of classes the same thing。

 So here we have three possible class labels right，0，1 and 2。



![](img/d7633ffbd2ad795f213c96187346d24b_7.png)

![](img/d7633ffbd2ad795f213c96187346d24b_8.png)

Also， note that your class labels should always start with 0。 So in this case， yet。

 what we get back is for the four training examples here，4 rows。

 and each has this indicator whether it's。

![](img/d7633ffbd2ad795f213c96187346d24b_10.png)

![](img/d7633ffbd2ad795f213c96187346d24b_11.png)

This class， the one is denoting the class and 0 is， yeah， it's just the placeholder。

 So for the first training example， this represents class 0， class 1， class 2 and class 2。



![](img/d7633ffbd2ad795f213c96187346d24b_13.png)

Then here's this softmax activation。 Oh， sorry， This is actually the net inputs。 So this is。

AMatri of net inputs。 I created them just arbitrarily。

 So each row is again for each training example。 we have four training examples。

 so we have four rows， and this is how our net inputs might look like。



![](img/d7633ffbd2ad795f213c96187346d24b_15.png)

So these are， if I go maybe to the slides。

![](img/d7633ffbd2ad795f213c96187346d24b_17.png)

These are the net inputs here， these。And then now we have to apply this softm here。

 and then we get these activations。

![](img/d7633ffbd2ad795f213c96187346d24b_19.png)

So yes， just for reference how the softm function looks like。



![](img/d7633ffbd2ad795f213c96187346d24b_21.png)

And heres a code implementation of the softm function。So again。

 there is actually a soft mix in Pywach。 So you actually shouldn't use your own implementation because in the implementation Pywach is yeah。

 more efficient， faster。 it's more optimized， but it's here again to just illustrate how it works。

 So what we have is in the numerator this。

![](img/d7633ffbd2ad795f213c96187346d24b_23.png)

Poential term， so。I'm going to go here E to the power of Z。 And then in the numerator。

 we sum over these exponential terms for all the activations。 If we have three classes。

 it will be a sum over。On3。

![](img/d7633ffbd2ad795f213c96187346d24b_25.png)

So that's what we have here。

![](img/d7633ffbd2ad795f213c96187346d24b_27.png)

Now let's do that。 So we have our Z here。 We have three classes，1，2，3 and four training examples， 1。

2，3，4。So these are then the softm activations that yeah that we get back。

 notice that the columns should sum to one。can just double check that。Inter。



![](img/d7633ffbd2ad795f213c96187346d24b_29.png)

That's one。So you can see they all sum to one。No columns。



![](img/d7633ffbd2ad795f213c96187346d24b_31.png)

Looking good。 Allright， now just to illustrate how we get the class table。

 So if we look at this one again， I mentioned we have an arc mix here。 arcm is you can think of it。

 Maybe I should demonstrate this。

![](img/d7633ffbd2ad795f213c96187346d24b_33.png)

![](img/d7633ffbd2ad795f213c96187346d24b_34.png)

It's giving you the position。off。The highest value。So if I have an example。Let's say toch ten so。1，2。

3，4。 The archrcx would be the highest value。 So in this way， the archrcx should give me 0，1，2，3。

 the value 3。That's weird here。 Okay， what's going on。



![](img/d7633ffbd2ad795f213c96187346d24b_36.png)

Oh， okay， sorry。I that should。Yeah， so yeah， I was just。Not paying attention。 Alright。

 so this gives me the value 3 as expected。 So if I put。



![](img/d7633ffbd2ad795f213c96187346d24b_38.png)

A5 here， this would return 0 now because now the0th position has the highest value。If you have a tie。

 I honestly don't know what happens when we have a tie。

 what I suspect is it will pick the first value， the lower value。Yep， that's exactly the case。

 So if we have a tie， it will always pick。The lowest value。ok。So。But yeah， in practice。

 it will be very unlikely that you have a tie here， I mean。Might happen， but I mean。

 there could be something like this for the other classes where we have a tie。

 but usually it's it's rare。

![](img/d7633ffbd2ad795f213c96187346d24b_40.png)

Alright， and this is yeah， also only a tie because I put this as a tie。

 Usually it's very rare that you have exactly the same values because that means that the feature vectors look exactly the same。



![](img/d7633ffbd2ad795f213c96187346d24b_42.png)

![](img/d7633ffbd2ad795f213c96187346d24b_43.png)

And the vector that the weight vectors are exactly the same。



![](img/d7633ffbd2ad795f213c96187346d24b_45.png)

Alright。It's converts to class labels。 This is just to double check。



![](img/d7633ffbd2ad795f213c96187346d24b_47.png)

So。These were all true labels from the one encoding。

 is is just to double check that we that this one indeed converts back to this one。



![](img/d7633ffbd2ad795f213c96187346d24b_49.png)

![](img/d7633ffbd2ad795f213c96187346d24b_50.png)

And here these are our predictions。 So we used the arc max to get the column with the highest probability。

 So we get this one。

![](img/d7633ffbd2ad795f213c96187346d24b_52.png)

This one。This one and this one。

![](img/d7633ffbd2ad795f213c96187346d24b_54.png)

And you can see there's one wrong prediction if we would compare those， right，0 and0。

 this is correct，1 and one is correct。Predicted class A 0。 The true label is 2。 This is incorrect。



![](img/d7633ffbd2ad795f213c96187346d24b_56.png)

This one is correct。 So we make one mistake， actually。So it's also， I mean。

 I did this on purpose to show you how this whole thing works， because if we wouldn't make a mistake。

 we would get a loss of zero， which would be kind of boring， I think。



![](img/d7633ffbd2ad795f213c96187346d24b_58.png)

Alright， so yes， again， the cross entropy。 again， recall that there are two sums。

 So if I go back here。 So we have these two sums here， I kind of entangled them a little bit。

 So we have。

![](img/d7633ffbd2ad795f213c96187346d24b_60.png)

![](img/d7633ffbd2ad795f213c96187346d24b_61.png)

This is a sum over the training examples， and this one is the cross entro P for the 100 en codingding。

 So this one is the in。

![](img/d7633ffbd2ad795f213c96187346d24b_63.png)

InNot one here。So let's compute first the cross entro P。For each training example， so。



![](img/d7633ffbd2ad795f213c96187346d24b_65.png)

What I'm doing here is， I'm computing these。

![](img/d7633ffbd2ad795f213c96187346d24b_67.png)

Terms。I actually said that this loss will be zero， but that I don't know why I said that， the loss。

 even though you match the right class ables shouldn't be necessarily be zero except。



![](img/d7633ffbd2ad795f213c96187346d24b_69.png)

If your activations match exactly。Your one hot encoding matrix。

Because remember from the logistic regression lecture。

 we want to maximize the probability for the correct class。

 but it's only maximized if the probability is 100% right so here even this is correct。

 even if 0 is the right class。 this is not 100% probability。

 So here we still have a loss right because it's minus lock 。37 just want to clarify， sorry。



![](img/d7633ffbd2ad795f213c96187346d24b_71.png)

![](img/d7633ffbd2ad795f213c96187346d24b_72.png)

Where were we？Yeah， so here for the training examples， the losses we get is 0。96。88，1。05 and 。83。

 So this is。Computing this one， really the inner loop。 So these correspond。



![](img/d7633ffbd2ad795f213c96187346d24b_74.png)

To these computations here。

![](img/d7633ffbd2ad795f213c96187346d24b_76.png)

Allright， so。That is how we would implement this。Now。

 maybe I can just briefly show you also how that looks like。

 we are just taking the lock of these softm activations and then multiply it by the target。

 And remember the targets are just zeros and ones， right。



![](img/d7633ffbd2ad795f213c96187346d24b_78.png)

嗯。Deeffin it。 That's interesting。 Oh， it's in， sorry， it's。It should be， I'm calling it as y ink。

 which gets passed to Y target。 So let me put like this。 So it's zeros and ones。



![](img/d7633ffbd2ad795f213c96187346d24b_80.png)

So。I can maybe also print it if you are curious。 So this would would be one value。

 and the other one should be zeros。So one value and the other one zeros。 in each row。

 there's only one。Value that is not zero in each row。And then we are summing。

 we are just summing over this。 This is the auto sum here。 So the first row。Would be 068。

So and so second row would be 。88 then 1。05。 This is actually what we see here right So the summing is actually just selecting it's just selecting the yeah the value here。

ok。

![](img/d7633ffbd2ad795f213c96187346d24b_82.png)

Yeah， I'm cleaning this up here because when I upload this。

 so you have the clean version without my weird interjections here。 Allright， so in Pythch。



![](img/d7633ffbd2ad795f213c96187346d24b_84.png)

There is a function called an L， L loss。Which。Takes the lock soft next as input。 So this function。

 the negative lock likelihood loss expects。

![](img/d7633ffbd2ad795f213c96187346d24b_86.png)

![](img/d7633ffbd2ad795f213c96187346d24b_87.png)

The lock of the softm values。 I'm just saying that we will use them in practice。

 We will actually use the cross entropy in practice。

 but I'm yeah trying to explain how these functions and pythrage work。

 So you can see this negative lock likelihood loss is the same as our cross entropy here。



![](img/d7633ffbd2ad795f213c96187346d24b_89.png)

Like， I explained in。

![](img/d7633ffbd2ad795f213c96187346d24b_91.png)

When we go up， I think I had a video on that in logics and cross entropy， so。



![](img/d7633ffbd2ad795f213c96187346d24b_93.png)

Where I mentioned that the negative log likelihood and binary cross entropy equivalent in Pyrage is's actually the negative log likelihood and the multicatery cross entropy equivalent。



![](img/d7633ffbd2ad795f213c96187346d24b_95.png)

![](img/d7633ffbd2ad795f213c96187346d24b_96.png)

In a way， you can also think of it as a multi category 1， the multinial logistic regression。

 and this would be still true。 So they are equivalent。



![](img/d7633ffbd2ad795f213c96187346d24b_98.png)

嗯。But notice it's really important to pay attention to this is that it takes the lock softm input。



![](img/d7633ffbd2ad795f213c96187346d24b_100.png)

So this might be counterintuitive， because。There is Orio Lock inside， right。But。The Pych version。

Does not perform this look here。 It expects that you perform at for pytorch。So。Pytorch， really。

Things you provide this here as input instead of the activation。



![](img/d7633ffbd2ad795f213c96187346d24b_102.png)

Just want to clarify this。 it's important to note because here we give the soft Max input。

Here we give the locks of nexus input。Right， because when I just give the softm input。

 I will get wrong results。 I will get some。🎼I just luckily my glass was empty。 Alright， sorry。

 So you notice that now we have negative values here， right， So this is not what we want。

 So you have to pay attention that this is actually the lock。



![](img/d7633ffbd2ad795f213c96187346d24b_104.png)

sI'm just emphasizing this because it's a common mistake in practice when people implement deep neural networks。

 they accidentally sometimes provide the wrong inputs and then get weird results and then the networks are not a training。



![](img/d7633ffbd2ad795f213c96187346d24b_106.png)

In practice， actually， I recommend using this cross entropy function over the negative Lo likelihood function。

This is numerically more stable。 So if you train a deep neural networks。

 the gradients and everything will be more stable if you use that one。Mathematically。

Everything would be equivalent。If we use negative look likelihood or cross entropy in Pytorarch。

 but numerically like stability wise on the computer， the cross entropy  one is more stable。

So and also for this one。Really pay attention to this one。 It's taking the logics at as input。

 So it's taking our net inputs as input。 So here， again， this is our net input matrix。



![](img/d7633ffbd2ad795f213c96187346d24b_108.png)

![](img/d7633ffbd2ad795f213c96187346d24b_109.png)

![](img/d7633ffbd2ad795f213c96187346d24b_110.png)

When we compute cross entropy， because we use the mathematical formulas。

 we compute first the softmax and then。

![](img/d7633ffbd2ad795f213c96187346d24b_112.png)

From the softm， we compute the cross entropy in Pytorch。

 they do all that work for us inside this function。 They do it for us。

 So here we give it the net inputs。

![](img/d7633ffbd2ad795f213c96187346d24b_114.png)

![](img/d7633ffbd2ad795f213c96187346d24b_115.png)

And you can see。Our function takes the softm， it gets the same results。Its these other functions。

 right， so they should be all identical， but in practice this is more stable。

 I recommend using this one。

![](img/d7633ffbd2ad795f213c96187346d24b_117.png)

![](img/d7633ffbd2ad795f213c96187346d24b_118.png)

And notice that I set reduction to none。

![](img/d7633ffbd2ad795f213c96187346d24b_120.png)

Which means it does not apply the sum or the average， which is this outta one here。



![](img/d7633ffbd2ad795f213c96187346d24b_122.png)

So by default， when you use this cross entropy。It will perform the average you can test it like this。

 see it's the same same value。

![](img/d7633ffbd2ad795f213c96187346d24b_124.png)

If you wanted to， you can also say reduction to。Consider production to some。sorry。Should beX。

So you can see you can also do the sum， it's equivalent。

 but in practice I recommend using the mean because like I said。

 it's more stable in terms of choosing a good learning rate。

 it's easier to find a good learning rate if you use the mean compared to the sum。Right。

 so this is like a core example of how all these types of losses and payroch work。

I recommend you just to play around with that。When we implement a softm regression in a later video。

 I will use this function。 And also when we use later on multi data perceptrons and convolution networks。

 we will be using。

![](img/d7633ffbd2ad795f213c96187346d24b_126.png)

This function。 Alright， so in then in the next video。

 I will go over how we yeah compute the gradients for such mixed regression。



![](img/d7633ffbd2ad795f213c96187346d24b_128.png)