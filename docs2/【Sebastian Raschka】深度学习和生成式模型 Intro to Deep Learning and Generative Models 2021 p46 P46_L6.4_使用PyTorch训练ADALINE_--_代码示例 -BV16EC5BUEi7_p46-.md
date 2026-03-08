# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p46 P46_L6.4_使用PyTorch训练ADALINE_--_代码示例 -BV16EC5BUEi7_p46-

Okay， now in this video， let me explain how we train Analine using the concept of automatic differentiation and Pytorch。



![](img/e58953bf514898ea379c25164069a08e_1.png)

So I prepared a code notebook here where I have three different implementations of Adeline first is the manual implementation that we saw last week then I have an implementation using the Gr function that I just explained in the previous video and then I show you an even more automatic way using the backward function that Pyrge automatically creates based on a forward function and that is also a topic I will then dive in more in the next video so here I want to just show you how it works and the next video I explain a little bit more。

Alright， so starting again with watermark， checking all versions here。



![](img/e58953bf514898ea379c25164069a08e_3.png)

I can also make this a little bit bigger。 So here again。

 this is a yeah adeline model that we talked about extensively last week。

 where we have multiple inputs， the weights， the net input function。

 the activation function is just a yeah identity function。

 and then the threshold function for prediction。

![](img/e58953bf514898ea379c25164069a08e_5.png)

![](img/e58953bf514898ea379c25164069a08e_6.png)

Alright， let's import some libraries we will be using the gra function I explained in the previous video and we will also make use of the functional API。

 Again， the functional API will be a more discussion topic in more detail in the next video。



![](img/e58953bf514898ea379c25164069a08e_8.png)

So we will be working with the IRS data again because it's simple so we can then focus more on the code rather than on the data。

So here we have no load of the data set。 and this is exactly the same as we have done in the previous week week。

 So if you are unsure how this works， this is exactly the same code as last week。

 so you can go to the video from last week。So everything is explained in that video last week。



![](img/e58953bf514898ea379c25164069a08e_10.png)

Allright， so。Also， just to recap， this is exactly the same code that we were using last week。

 So here this is our aine implementation where we first initialized the weights and the bias。



![](img/e58953bf514898ea379c25164069a08e_12.png)

![](img/e58953bf514898ea379c25164069a08e_13.png)

We have our forward function that computes the net inputs， and then the activation。



![](img/e58953bf514898ea379c25164069a08e_15.png)

And then we have the backwardwork function where we computed the gradient by ourselves。

 So what I mean by that is we derived it in the slides， we had slide on how we derived that gradient。

 and then here this would be the equivalent code implementation of that。



![](img/e58953bf514898ea379c25164069a08e_17.png)

![](img/e58953bf514898ea379c25164069a08e_18.png)

Yeah， we have some training and evaluation wrappers just to make things a bit more convenient to look at。

 so we have a loss function that we compute where we can plot the loss function during training。

 So here in our training function again like in last week we have a cost list where we compute the cost which is actually yeah the loss over the epoC。



![](img/e58953bf514898ea379c25164069a08e_20.png)

Or mini batch。 actually。 So let me see。 So what we do is we iterate over the epochs。

 So for each epoch， we shuffle the data set， and then we create the mini batches。



![](img/e58953bf514898ea379c25164069a08e_22.png)

And for each mini batch here， we perform the forward pass that is like predicting yeah。

 the class labels。And then we compute the backward pass。

 So here this is computing the negative gradients， the negative gradient of the loss with respect to the weights and the bias。

And then we update the weights。 So we updated by。Yeah， we have the original weight。

 and we update it by adding the negative gradient multiplied with the learning rate。

Why for some reason， commented that out， yeah， I think it was just too much output。

 And I wanted to keep this notebook short because there will be other codes。

 and it was too long other ways too detailed。 We don't need that level of detail here。 Here。

 we are just printing。

![](img/e58953bf514898ea379c25164069a08e_24.png)

The number of epochs and the loss for each epoch。 So let's。Deefine it。

 So note this is not running any code because it's just setting up the functions here。

And then here we are defining or initializing the model。



![](img/e58953bf514898ea379c25164069a08e_26.png)

So x strain size， This is the same。 I could have used shape。 This is the same same as shape。

 So it's the number of features。It's the same as。Spe。One some features。Then yeah， here's data sets。



![](img/e58953bf514898ea379c25164069a08e_28.png)

input the number of epox 20 learning rate  point01， a random seat so we can reproduce these results。

 So that means if someone else like you runs this code。

 you should get I get exactly the same results。And then the mini batch size。

 how many mini batchs we use in each iteration， not the random seat here is only used for shuffling the data set。

 right， if I go up again， this is being used when we shuffle the data set。

 So if you change the random seat， you might get some different results。



![](img/e58953bf514898ea379c25164069a08e_30.png)

![](img/e58953bf514898ea379c25164069a08e_31.png)

![](img/e58953bf514898ea379c25164069a08e_32.png)

![](img/e58953bf514898ea379c25164069a08e_33.png)

Alright， so let's do this。So this is training and this is super fast。

 so you can see the outputs immediately here， Usually if for deep learning。

 it would take maybe it depends really， but it could take 10 minutes perpo and take an hour perpo depends on the data set。

So let's take a look at the loss。Okay， this is。Converging， it's not converged yet。

 but doesn't really matter because here， the point is really explaining the automatic gradient computation in the next code。

I want to and why I'm showing you this is so that you can compare the automatic way of Pytorch of doing this with this one。

 and you will see it's exactly the same result。So just to show you that our conceptual thing thing that we did manually last week is actually correct。

 And well other way around that Pythro is actually correct。



![](img/e58953bf514898ea379c25164069a08e_35.png)

Alright， so here that's the predictions。

![](img/e58953bf514898ea379c25164069a08e_37.png)

For computing the test and training accuracies。 Also， it's essentially the same concept as last week。

 So nothing new here。

![](img/e58953bf514898ea379c25164069a08e_39.png)

No。After we just reapped yeah， the manual implementation of the airline that we talked about last week。

 now let's do this semi automatically or semi manually using this auto gridd。



![](img/e58953bf514898ea379c25164069a08e_41.png)

A PI from Pytorch。 So there will be only very subtle changes。

 So this one is exactly the same as before。

![](img/e58953bf514898ea379c25164069a08e_43.png)

![](img/e58953bf514898ea379c25164069a08e_44.png)

Now， the only difference is in the train method。

![](img/e58953bf514898ea379c25164069a08e_46.png)

So， let me scroll。To the relevant part。 So notice everything here is the same。



![](img/e58953bf514898ea379c25164069a08e_48.png)

What has changed is now how we compute the gradients here。

So now we use this gra function to compute the gradients of the loss。

With respect to the model weights。And then we retain the graph。

 remember from last video this is if we need again， gradients。

 we need to retain it one more time so because we want to compute the bias here too。

 and then here we don't care because in the next round it will be constructed from scratch the graph so here we don't need to retain the graph。

Why the -1。 So that is because we want to have the negative gradient， because then we。

 we add the negative gradient to the model weight。 We could also just skip this step。 Of course。

 right， we can do it like this and add。On minus here oops。Same thing。

But just to keep it consistent with the implementation that we had before， our manual implementation。

I wanted to make it as similar as possible。Alright， so。

The only difference to before is now that how we compute the gradients notice that there is no backward function。

 now。 If I scroll up again， show it to you again。

![](img/e58953bf514898ea379c25164069a08e_50.png)

In the previous time， we had backward here to compute the gradients where backward was our。



![](img/e58953bf514898ea379c25164069a08e_52.png)

Yeah manual way of computing the gradients。 Now we do it automatically。 See。

 this is actually because of the scrolling is why I commented on the logging because otherwise it would be a lot of stuff to scroll here。



![](img/e58953bf514898ea379c25164069a08e_54.png)

![](img/e58953bf514898ea379c25164069a08e_55.png)

Alright， back to the。Thing here。 So yeah， here here。

 this is the difference instead of using backward with our manual gradients。

 we now use this gra function。

![](img/e58953bf514898ea379c25164069a08e_57.png)

Except that everything should be the same。 I made a small modification here to the logging。

Notice that I use with torch nograd because when we just do some logging here。

 we don't do any model training here， we don't need to construct the graph。

 it would be computationally wasteful to build the graph because otherwise it will create the graph in our forward method So here this one because we have set requires gradient into the true if this is set to true every time this is used。

 it will create this computation graph。

![](img/e58953bf514898ea379c25164069a08e_59.png)

![](img/e58953bf514898ea379c25164069a08e_60.png)

![](img/e58953bf514898ea379c25164069a08e_61.png)

Okay， so。Here， the computation graph gets destroyed because we don't have retain graph to true。

 So every time we do the fall loop here， it makes a new graph。Here we don't call Gr， right？

 So here it would create a graph， but we don't need this graph。

 and it would be just computationally wasteful。 It's just a good habit if we don't need a graph if we don't need to compute gradients here for logging。

 then we can use this with torch no gradient。Context and everything that is indented， so。

Everything that is below here。Does not construct a computation graph。

 It's just to save computational resources。 Here。 it's such a simple code。 It doesn't matter。

 but it does matter for deeper neural networks。

![](img/e58953bf514898ea379c25164069a08e_63.png)

Alright， so defining it。 then again， same as before。

 we initialized the model notice that there's no outlineline 2 instead of aline 1。

 then yeah draining the model。

![](img/e58953bf514898ea379c25164069a08e_65.png)

![](img/e58953bf514898ea379c25164069a08e_66.png)

So we can see again， the loss goes down， up， up， up， and let's take a look the plot。



![](img/e58953bf514898ea379c25164069a08e_68.png)

Should look exactly like before。Let's compute the training accuracy and test accuracy。



![](img/e58953bf514898ea379c25164069a08e_70.png)

Also， the same as before。 you can actually double check。 These are exactly the same numbers as。



![](img/e58953bf514898ea379c25164069a08e_72.png)

The one here。

![](img/e58953bf514898ea379c25164069a08e_74.png)

Alright， so this is now doing things more convenient right So because you can think of it if I scroll up again。

 I don't want to scroll that much， but I think it's useful here in this case。

 So if this forward one would be a very long complicated function using multiple layers and stuff like that。

 You can already see how it's convenient to not implement this backward method by hand by deriving that by hand right I mean it's a good exercise still。

 but it is also very error prone for deep neural networks。

 So it's better to rely on these automatic functions， however。

 there is an even more convenient way to do this that I want to show you now。



![](img/e58953bf514898ea379c25164069a08e_76.png)

![](img/e58953bf514898ea379c25164069a08e_77.png)

![](img/e58953bf514898ea379c25164069a08e_78.png)

![](img/e58953bf514898ea379c25164069a08e_79.png)

![](img/e58953bf514898ea379c25164069a08e_80.png)

So this is usually how people， most people use Pythtor。

 So you can actually use this so called linear layer here。 So this is， as I explained last week。

 this is computing the net input。I have now， an additional step。So here I have this0。

So what's going on here。Usually when we use torch do and n dot linear。

It's thinking we want to implement some multi layer neural network because that's what most people do and deep learning。

And then it will initialize the weights to small random numbers。

 This would be also totally fine for our aline here。 However。

 to make our aline implementation here more comparable to the previous two codes I showed you before where we use0 weights。

 I also want to use 0 weights。 So I'm setting。These weights to 0 here。

 So just to show you what I mean， that mean。Just do this。Alright， let me just use。Like this。

 And then。Should have， of course， signed it to something。

 You can see that these should be small random valuess。 See that。And if I set them to 0。They will be。



![](img/e58953bf514898ea379c25164069a08e_82.png)

Oops。AlrightThis is the problem。 you have to detach it。 It doesn't like it if you have。

Variable defined。 And you want to modify it like in place。Leaf variable means a leaf。

 It's like an end point， and it does like it if you modify it。With an inla operation。

 because it's also  error problems。 This is usually something you don't want to do in a network。

 So it's kind of warning you。So， you have to。Detach it from the graph here。



![](img/e58953bf514898ea379c25164069a08e_84.png)

There we go。 So now I set it to 0。 Also notice I didn't， I didn't do。

This here equal to because theres a convention in Pythr。

 there are these so called in place operations， these with an underscore。

 they do an operation in place， so there's no return value actually。

It just takes the existing vector and overwrites it。

 This is also done for computational efficiency because imagine you have a very large vector。

And then you want to override it with all zeros。 You would have to memory briefly create two vectors。

 You have the original one， then the0 vector and the0 vector overrites the original one。

 So in a brief moment in time， you would have two vectors in memory and it would take twice as much memory。

 So if you do this with large matrices， it can in certain GPUus be yeah， problem。 I mean。

 it's just wasteful。 So in this case， these underscoreco operations。Modify something in place。

 But yeah， I'm getting sidetric here。 Let's go back to what's going on here。

 So here I'm now defining the forward pass pass。 Oh sorry。

 the weights used in the forward pass using this linear。



![](img/e58953bf514898ea379c25164069a08e_86.png)

Bpper， we talked about this briefly last week， and then。So'm signing it to self dot linear。

 And then I'm using it in the forward method here。 So here I'm computing the net inputs using。

Self dot linear。Then I'm computing the activations。

 the activations that's nothing and identity functions， I'm just overwriting it。

And then I'm returning it。Alright， so here now I'm training it again， notice。

The only things I define are this weight layer here。And this forward what method here。

 I'm not defining anything else。In the train function， this is fundamentally very similar to before。

Except now， see I'm computing the loss here， so I'm computing loss function I'm using here the MSE loss。

 I could use my own lossOS， but like I mentioned if there is a function that is already implemented in Pythtch。

 I recommend using that one over your own implementation because it's usually more efficient。

They use some tricks。 another to also C plus plus code to implement things more efficiently。 So here。

We are using this M Eos。And。Then we are resetting the gradients using zero grad。And calling backward。

 So are multiple steps that are new now that are happening here so。

Calling forward to predict the outputs， the class labels。 So compute outputs。

 then it's actually like the class labels is the net inputs。

Because it's before the threshold function。 Let me scroll up one one time。



![](img/e58953bf514898ea379c25164069a08e_88.png)

So we are come we are here this， this value here。 we are computing this value。



![](img/e58953bf514898ea379c25164069a08e_90.png)

Alright， where was a we're computing this video， Yhead。



![](img/e58953bf514898ea379c25164069a08e_92.png)

Oh， this is the previous one， sorry。Mmhmm。Okay， here。For， so we are computing this my head value。

 Then we compute the prediction arrow。Using the mean Sc arrow here。

Notice that I'm resetting gradients from the previous iteration。

 so this will be running multiple times。And there is。

How Pythrarch works is a dot gra attribute that will be set for these D variables after each iteration。

And we are resetting it。 Otherwise， you would be accumulating the gradients。

So usually it's not the case in deep learning， we usually compute the gradients， update the weights。

 then do the next round， compute the gradients update the way， update the weights。

 but there are some applications where we want to， for example。

 not update the weights after each epo， for example we can do two forward passes and then update the weights so。

This would be possible。 We could， for example， skip0ing the gradient。 we， we could， technically。

 for certain research experiments， accumulate the experiments。

So this is why Pyrch has this implementation to allow certain researchers to do some more flexible research。

 but it also as a normal user， forces us to remember to zero the gradients。

So here the so we are also using， should say， an optimizer。

 stochastic gradient descent that is more automatically than what we have done before。So prediction。

 computing the loss， zeroing the gradients from the previous round。

 calling backward that computes our gradients。And then， updating the weights。

So this is usually a typical Pyt workflow。 That is what people do。

 usually in practice and what we do when we do implement neural networks。In the previous round。

 we had it manually。So， we had。Computed forward。 And then we had our loss function。

 But then we computed here the negative gradients。 And we did stuff here。 the update automatically。

 This is what。In our code information below is equal to optimize the。Step。

So how does Opr know that we want to update the weight and the bias？ Well。

 that is because we feed it with the parameters I will show you。



![](img/e58953bf514898ea379c25164069a08e_94.png)

Here we。

![](img/e58953bf514898ea379c25164069a08e_96.png)

We provided T see with model parameters。 So there's also a concept。

 If you use these functions like Torch linear， these will be registered as model parameters in this module here。

 so。Here， this will automatically contain the model parameters。 Let me actually show it to you。



![](img/e58953bf514898ea379c25164069a08e_98.png)

So here we have， where was it first scroll up， we haven't actually defined it yet， sorry。



![](img/e58953bf514898ea379c25164069a08e_100.png)

So let me execute this part first， and then I will show you more details。Alright， so。

I already ran this。 so everything should I can actually also add。 it's fine。 So here you can see。

 okay， maybe we can't because it's a generator。So you can see the are。2 entries。

1 is actually the weights， and one is the bias。 So they are registered under the parameters。

 So these are really the values that we have as model dot F dot weights。



![](img/e58953bf514898ea379c25164069a08e_102.png)

Oh， what was it。

![](img/e58953bf514898ea379c25164069a08e_104.png)

How did we say at one second， or linear recorded linear， not F。😔。



![](img/e58953bf514898ea379c25164069a08e_106.png)

So， you can see。These are corresponding to this one。



![](img/e58953bf514898ea379c25164069a08e_108.png)

And this one is corresponding to this one。So this is how the optimizer knows what to update when we call step。



![](img/e58953bf514898ea379c25164069a08e_110.png)

I can maybe also show you model linear。Wait， there should be a gr。So this is the gradient。

It's the gradient from training it。So from the backward pass， and if we call backward an next round。

 it will add to this gradient so it will grow。So。This one。Should actually。Oops， make it 0。

Since executed this。That doesn't work Oh it's， it's because it's defined outside this。

Outside this function here， that's a little bit unfortunate。Yeah。

 it a little bit of tricky to show it to you here。 Maybe I can。



![](img/e58953bf514898ea379c25164069a08e_112.png)

Can do it differently。 I can。

![](img/e58953bf514898ea379c25164069a08e_114.png)

Do it here before。After。Alright， it's actually none。 Oh okay。 No， it's something else。 It's。

 I think the first round。 So yeah， I can see first， it's this and then after 0， this。

 and then it's this and this。You can see how it's computed， then 0 to computer 0。

 if I don't do this one。It will just grow larger and larger。

Can see that maybe not because it's a positive or negative very I you can see how。

 how large it becomes。That's actually not good。So here， the model wouldn't learn anything useful。

 I guess。Let's see。 Yeah， you can see it's not you're learning anything useful。 So let's fix that。

Alright， let's fix this。And run it properly。

![](img/e58953bf514898ea379c25164069a08e_116.png)

Alright。And you can see this is the same as before。



![](img/e58953bf514898ea379c25164069a08e_118.png)

When I compute the test and training accuracy， look at these value values 92。86% and 93。33%。

 And this is exactly the same accuracy。 Let me screw up to O。



![](img/e58953bf514898ea379c25164069a08e_120.png)

![](img/e58953bf514898ea379c25164069a08e_121.png)

Manual implementation exactly。

![](img/e58953bf514898ea379c25164069a08e_123.png)

The same number here。 So you can see Pytorch is performing exactly the same thing we do manually。

 So our manual derivatives are correct。 and vice versa Pytorch is also correct。

 So I will talk about this more in the slides explaining this again。

 But I think if this is still unclear maybe focus on this part。

 So this is really how we use Pytorch like forward compute the loss0 the gradients backward update。



![](img/e58953bf514898ea379c25164069a08e_125.png)

![](img/e58953bf514898ea379c25164069a08e_126.png)

![](img/e58953bf514898ea379c25164069a08e_127.png)

![](img/e58953bf514898ea379c25164069a08e_128.png)

![](img/e58953bf514898ea379c25164069a08e_129.png)

And this is essentially a Pyr in a nutshell。 And we can use this API for all types of models。

 So the only difference is really here when we define the。



![](img/e58953bf514898ea379c25164069a08e_131.png)

Weight parameters and the forward at pass。 So this is the only difference。

 The training loop is essentially always the same。

![](img/e58953bf514898ea379c25164069a08e_133.png)

Alright， then let me stop this video and then go back into the slides and explain to you a little bit more about the Pythtorch API。



![](img/e58953bf514898ea379c25164069a08e_135.png)