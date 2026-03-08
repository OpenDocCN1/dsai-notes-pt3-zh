# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p55 P55_L8.5_PyTorch中的逻辑回归_--_代码示例 -BV16EC5BUEi7_p55-

Yeah， before we move on and talk about the multiclass example of logistic regression。

 the so called softmax regression， let's just wrap up everything we here talked about in the previous four videos in a code example。

 So I prepared a code notebook。 You can find it on Github。 I will share the link on canvas。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_1.png)

Where I have implemented two things。 So the first thing is logistic regression from scratch。

 just yeah， from the ground up， low level implementation of logistic regression。

 really like implementing。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_3.png)

The learning rule that we talked about here。And then I will show you how we can do that using the Pythtor utilities。

 the module API that we talked about last week where we have this NN dot linear layer and so forth。

 this is something we would do in practice when we have of course more complicated networks。

 but I thought from scratch implementation is still useful from the learning perspective so you get a better feeling of how logistic regression works。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_5.png)

So let's get started。So， of course， first， my watermark， you can ignore the torch version。

 this torch version doesn't exist。 actually， I yesterday。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_7.png)

Compiled a torch from source to test something。 So this should also work on torch of 1。7。

 So no worries can ignore that。Yeah， so。B的。Po of mat Butlet， which we be using Ny we will be using。

 And then the torch stuff we will be using。 So just some inputs to get them out of the way。

 We will be using some simple toy data set。 That's like， yeah， just。

 I think that is what I gave you also for the homework， to be honest， I have to double check。

 I made multiple of these toy data sets。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_9.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_10.png)

But yeah， that's just a simple binary classification dataset set。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_12.png)

Now here is my logistic regression implementation。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_14.png)

So how does it work？ So I'm using the roughly same way how we would implement that using Pytorch with a module API。

 So here I am implementing forward and backward manually。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_16.png)

These are the two methods where forward is， yeah the forward pass and backward is the gradient descent computing。

Yeah， the gradients of the loss function。I actually let me modify this。

 Let's call that Ro with respect to。 So W R T means with respect to。 I think it makes it clearer。

 So that's。Graing of the loss with respect to the output， and so forth。

We'll just modify it everywhere here。And then。Let's do it step by step here。

 So then here in the init function， this is like the function or method that get ex gets executed when we instantiate a new object from this class。

 What we have is the weights and the bias unit。So the weights we initialize them to0 to zeros。

 So we use the zeros function to initialize them to zeros。 It's a vector， a one， it's a row vector。

 basically a one times nu features vector。 So matrix。 So it's essentially a row vector so。

Numb features is the number of features in the dataset set。

 so the number of weights is equal to the number of features just like an Adeline。

 and we only have one bias unit。Alright， so the forward method， Yeah。

 this is computing the net input， right， So says。The net input can also call it Z。Can。

We could technically call it an a， but you know what we mean right， I mean， I can rewrite this maybe。

Doesn't really matter。I can just leave it like that。 I think I'm under estimating you。

 I think it's probably all clear to you。 I don't have to use these different words。 alright。Sorry。

 so。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_18.png)

The backward method is， yeah computing these gradient terms。

 This is going back to what we've done here。 So here I'm computing the gradient of the loss with respect to the output。

 So this is essentially this part。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_20.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_21.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_22.png)

Here。Then the grain of the loss with respect to the weight is。This part here。

Where I put those two things together， so。This should probably be with respect to D and Z。

 the net input， it maybe be clearer instead of saying output。So this is matrix modification between。

X。And this term， I just rearranged that to make the dimensions match。

 which is why I have the transpose。 you， to be honest， don't have to memorize these details。

 You will probably find out by tinkering with the code if you ever implement something from scratch because here this is really for one weight。

 And here I have that vector implementation for multiple weights， right， because we have。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_24.png)

The number of weights equal to the number of features。 It's a bit more complicated。

 but the concept is the same， so。This line here really is this part here。

I can actually also maybe go to this part here。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_26.png)

This part here， this。Its essentially this one here。

 the gradient of the loss with respect to the weight。And then the same for the bias。

 which would correspond to this part here。Here this is the threshold function predict labels。

 So I'm calling forward that gives me the probabilities a， so a is the probabilities Pros。

 I call them Pro because in the lecture I said also it was a bit complicated when we had Y hat and it was confusing so I。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_28.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_29.png)

Referd to a as the probabilities。That's the sigmoid activation here。

And this is the threshold function where if the probabilities are greater than 0。5。

 return class label 1。 Otherwise， return class label 0。 I could， however。

 also do it as with the net inputs， I could say if the net inputs。

Let's go 0 are greater than 0 than return 1。 Otherwise，0。 This is because。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_31.png)

What we discussed here。So here's the threshold function。 And because。The probabilities with that 。5。

 the net input is 0。 so either we can operate directly on the net input or the probabilities here。

 So you have that with the probabilities， but doesn't really matter that much。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_33.png)

Okay， so here's just an evaluation function。 So this is not super interesting。

Here I'm predicting the labels， which in turn uses this method here。

 which computes forward and then the threshold function here。So we can call it a threshold。Function。

And then， in order to compute the accuracy， we。Some。Over the correct predictions。

 So every time the class label matches the。The predicted labels here。

Matches the actual class tables every time they match。We sum that up。

 So this is a number of correct predictions and then divide by the size of the training set。

 So it's a value between 0 and 1。 It's the proportion of correct predictions。 Why do I do float here。

 It's because the class labels are integers。 And yeah， in Pythage。

 it's a little bit tricky to compute or compare things like floats， The tables are floats here。

And then this is intertejo。 I think I could have omitted this here。

 It's maybe a little bit complicated。 I could have was think done。

That would also have the same effect。So， but anyways。Okay， anything else。 Yeah。

 this is a sigoid function， which you have seen a lot of times。 So this is this function here。Yeah。

 the loss function。 That's the negative log likelihood， which we have。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_35.png)

Right here at the bottom， that's the。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_37.png)

We'll just take a cost function。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_39.png)

And here's the training function， so here。Again， let me jump back to this one。We are right here now。

 So for every training apoch。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_41.png)

For E in the number of epos， we compute the outputs， which is here。 That's the probabilities。

 the A's。 So this is really this should be an a actually。 So remember。

 this was copied from the add line should have。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_43.png)

Probably adjusted it to an A here。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_45.png)

But you probably know what I mean。 Then we compute the gradients。 So these are under B。Here。

Then we update the weights， which is C this part here。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_47.png)

And this is it。 And this is just for yeah， logging。

 just keeping track of everything like looking at the results and the loss score。

 which can be useful。 So let's actually do that。 let's。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_49.png)

Yeah， do that here。 What I'm doing is I'm converting the nuey。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_51.png)

A race to torch tensrs。 Because if you go up here。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_53.png)

You can see， I。Use nuy here。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_55.png)

So to load the data。 So here I'm just。Converting them to torch tensrs。

 Then I'm initializing my logistic regression model。 So this will be actually step 1 initializing。

And then I am calling train。 trainin would be everything under two here。

And then I'm printing the model parameters， the weights and the bias just to take a look at them。

 and I'm training for 30 epochs。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_57.png)

With a learning rate of 01。So I think that's the mistake I always make I talk through this。

 but I usually forget to execute this。 Okay， now we are。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_59.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_60.png)

Running the code， okay， we got an arrow here。Okay， I I changed the。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_62.png)

Name one second。 Let me fix that。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_64.png)

Let's see。Allright， so it's training， you can see it's blazing fast。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_66.png)

Starts with already a very high accuracy after the first epoch， to be honest。 So it's yeah。

 it's actually training super fast。 The cost is very low。

 But you can see if I do more epochs it goes even lower， the accuracy goes up to 100% here， even。

 But you can see even though the training accuracy already 100%， the loss still goes down。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_68.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_69.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_70.png)

I could have trained more and would go maybe down further。

 but that at that point might not be necessary。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_72.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_73.png)

Might be overfitting。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_75.png)

Wanted to execute this part。Okay， there's some message here。

 I think this message comes from Ny because I recently installed a very recent version of Ny。

 and it must be something in Mepl here。 You can actually ignore that that this is not。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_77.png)

Ar message that is just a warning。 So if you see warning or deprecation warning。

That means things are still working。 so don't worry about them。 But in future。

 if there's an even newer version of a software library in Python， this may not work anymore so。Here。

 this is nothing we are doing wrong。 This is probably something inside Merolib。

 and I'm sure they are already aware and working on that。

 so don't worry about this warning everything still works fine。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_79.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_80.png)

There will be probably a new met but version that addresses this issue at some point。

 but everything is fine。 Yeah， you can see here as how the lock yeah。

 the negative lock likelihood loss looks like。 So it should be the negative。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_82.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_83.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_84.png)

Not likelihood loss to be precise。 And then over the number of epos you can see maybe it will go down further。

 you can see it's actually going steep down。 but whether it's actually helping。

 I don't know because we already get 100% training accuracy。

So let's take a look at the test accuracy， it's only 96%。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_86.png)

For completeness， we will also take a look at the。Yeah， this year。 So yeah。

 we can see actually here on the training set， the decision model looks quite good。

So it's dividing both class class 0 and class 1 on the test that yeah it's not performing so well because there's this one outlier point。

 right， So here。This one is not classified correctly。

 So if this decision body would go a little bit more to the right。

 then we might get this one correct。 but at this point。

 this model only see a training that I doesn't know of this point here on the right hand side。

 So in this case， I think training the model further wouldn't really help because this is already doing a good job here actually maybe putting a little bit more to the right would help actually because then it would be more here。

没有。Anyways， this is just an example， of course I just implemented this quickly in a way that I didn't really find you in anything。

 and this is a toy data set anyway， so don't over interpretterpret this okay so the goal here was really to show you if I scroll up again to show you how we implement this from scratch like the most interesting part I would say is the backward function。

 which is a little bit different from the Aline function。

 the rest should be all the same as in the Adeline implementation So it's not that new to you I hope。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_88.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_89.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_90.png)

Now， I want to show you， though， how we yeah use the module API to implement this logistic regression module so here。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_92.png)

This should do exactly the same thing， but now I'm relying on in build or build in pytorrch functions。

 So I'm using this self dot linear here to refer to my torch dot in end dot linear layer。

 This is a layer that computes the net input。However， note that by default。

 this will initialize the weights to small random numbers。 Later on， this will be very useful。

 but it is not that useful to compare it to our model above because if you recall above I initialize my weights and bias to 0。

 So I want to do the same here。 so I can compare the two models。

 So what I'm doing is manually assigning。0 to the weights and buyers unit。嗯。Yeah。

 and then we have the forward method。 So here， the forward method。

 we compute the logicits via the self linearia， which is this。Fly connected layer or linear layer。

 and then we have built in pyr function that computes the sigmoid activation function。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_94.png)

So you can see a logistic regression model is actually super simple。

 actually we can also it would train just fine if we have this one。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_96.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_97.png)

Just for comparison person reasons I have this one， but you can see how simple it is。

 and it will already implement the backward function for us。 We don't have to do it ourselves。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_99.png)

Here we are using the stochastic gradient descent。嗯。Optimizer， so this will update the weights then。

So this will compute the gradients via other the backward and update the weights。

 So we are just specifying what weights we want to train。 This is the model parametersus here。

 Model 2。 So this is。Model 2 or one logistic regression model 2。

 Model 1 was the from scratch implementation。 right。

 so here is just an accuracy function to compute the prediction accuracy。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_101.png)

We are training also for 30 epochs。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_103.png)

Like before， what I'm doing is I am casting theumpy。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_105.png)

R to a tensor。 I've already done that， so it's probably redundant。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_107.png)

And now here' is my training loop in Pytorch。So， for each epoch。I compute the outputs。

 These are the probabilities。 This is from the forward pass。 This is。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_109.png)

These probabilities here。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_111.png)

Then I use this cross entropy， binary cross entropy function。

 and this is essentially why I spent some time in the last lecture， last video here when we had。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_113.png)

When we had this topic here， why I spend some time。

 just telling you that the negative look likelihood and binary cross entropy are equivalent。

 same thing。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_115.png)

Here， I'm saying reduction sum， because that's what we have done here。 It's the sum。

 or we can also do the average。 Actually， if I change this， it will be the average or。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_117.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_118.png)

Mean by the default。 But since we implemented above the sum2， we have the sum here。

 I'm also for comparison reasons use the sum here in practice， I think using the mean is more stable。

For with regard to learning rates and different batch sizes。Yeah。

 and then this is really like what we have done in the last week when we trained Adeline using these automatic things。

 we。Have the following。 we compute the loss。I。Traditionally use the term cost。

 but I think loss is more natural now nowadays than we。Yeah， set the optimizer。0 gra。

 which will yeah reset the gradients from the previous round。

 Otherwise the gradients will accumulate， like I explained last week。

AndThen we compute the gradients for the current round and then update the weights。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_120.png)

And this is essentially it。 Let's run this。Alright，arrow， Model 2 is not defined。 C。

 I always forget to execute things。 Alright， let's execute this one。 and then this one。 Yeah。

 it trains。 Okay， so and you can see if you recall， these have the same values as we've seen before。

 I can just scroll up in a second and just to show you。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_122.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_123.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_124.png)

And also take a look at these weight parameters。Can just copy and paste them。

So yeah you can see they are exactly the same so we learned exactly the same using Pyhar。

 which gives us confidence， I hope that we understand gradient descent correctly and implemented。

 yeah， the gradientd here correctly。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_126.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_127.png)

So it's the same as in Pytorch。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_129.png)

Allright。Yeah， and this is it essentially。 So evaluating the model， same test that accuracy。

Because it's the same weights and bias， so it should be the same decision boundary。

 which we can see here。

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_131.png)

Yeah， so this is how we implement logistic regression。

 I hope that was helpful like understanding a little bit better how these different concepts here in the slides work。

 You may also want to work through this more slowly。 I think that might be also helpful。

 but yeah that's it So the next video we will then talk about how we can generalize these concepts to multiple classes That means like more than two classes。



![](img/54ee9d1a5027fa4bec5b5df80ebc8872_133.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_134.png)

![](img/54ee9d1a5027fa4bec5b5df80ebc8872_135.png)