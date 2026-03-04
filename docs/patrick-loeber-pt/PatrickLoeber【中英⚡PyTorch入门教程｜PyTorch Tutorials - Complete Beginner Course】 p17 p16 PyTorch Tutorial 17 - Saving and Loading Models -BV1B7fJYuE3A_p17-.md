# PatrickLoeber【中英⚡PyTorch入门教程｜PyTorch Tutorials - Complete Beginner Course】 p17 p16 PyTorch Tutorial 17 - Saving and Loading Models -BV1B7fJYuE3A_p17-

Hey， guys， welcome to a new Pytorrch tutorial。 Today。

 I want to show you how we can save and load our model。

 I will show you the different methods and safe options you have to know。

 And also what you have to consider when you are using a GPu。 So let's start。

 These are the only three different methods you have to remember。 So we have torch dot safe。

 Then torch dot load and model dot load state dit。😊，And these are all the methods we must remember。

 And I will show you all of them in detail。 So Torch dot Sa here can use tenors models or any dictionary as parameter for saving。

 So you should know here that we can save any dictionary with it。

 and I will show you how we can use this later in our training pipeline。

So torch dot safe then makes use of Python's pickle module to serialize the objects and saves them。

 So the result is serialized and not human readable。And now for saving our model。

 we have two options。 The first one is the lazy method。 So we just call torch dot save on our model。

 and we also have to specify the path or the file name。 And then later。

 when we want to load our model， we just set up our model by saying model equals torch dot load and then the file name again。

 And then we also want to set our model to evaluation method。 So by saying model dot evil。

 So this is the lazy option。 and the disadvantage of this approach is that the serial serialized data is bound to the specific classes and the exact directory structure that is used when the model is saved。

 So there is a second option， which is the recommended way of saving our model。😊。

If we just want to save our。Model or train model and use it later for interference。

 Then it is enough to only save the parameters。 And as you should remember。

 we can save any dictionary with torch save。So we can save the parameters by calling torch。

a and then model do state di。 So this holds the parameters and then the path。And then later。

 when we want to load our model again first， we have to create the model object。

 and then we call model dot load state dit。 And then inside this， we call torch dot load path。

 So be careful here since load state di doesn't take a only a path。

 but instead it takes the loaded dictionary year。 And then again。

 we set our model to evaluation mode。 So this is the preferred way that you should remember。

 And now let's jump to the code to see the different saving ways in practice。



![](img/c885dfe548f252ed653964b1bd0374b3_1.png)

So here I have a little script where I defined a small model class and here I created our model and now let me show you the lazy method first。

 So first we define our file name so we say file equals and let's call this model do P so it's come and practice to use the ending do p so short for pytorrch and then we save the whole model by saying torch do save and then model and the file So let's save this and let's run the script So let's say Python save load do pi and now if we open up our browser so we can ignore this warning here then we see here we have the model do p file。



![](img/c885dfe548f252ed653964b1bd0374b3_3.png)

![](img/c885dfe548f252ed653964b1bd0374b3_4.png)

![](img/c885dfe548f252ed653964b1bd0374b3_5.png)

In the explorer。

![](img/c885dfe548f252ed653964b1bd0374b3_7.png)

And if we open this， then we see that this is some serialase data， so this is not human readable。



![](img/c885dfe548f252ed653964b1bd0374b3_9.png)

And now if we go back to our code。 So let's load our model so we can comment this out。

 and we also can comment this out。

![](img/c885dfe548f252ed653964b1bd0374b3_11.png)

And then we can load our model by saying， model equals。Equals torch dot load。 and then the file。

 And then remember， we want to set it to evaluation method。So we say model dot evil。

 and then we can use our model。 For example， we can inspect the parameters。

 So let's say for Para in model dot parameters。And then， let's print our parameter。And save this。

 And let's clear this and run our script again。

![](img/c885dfe548f252ed653964b1bd0374b3_13.png)

And let me make this larger for you。 So now if we run our script again。

 then we can see that we loaded our model and we can use the parameters。So this is the lazy option。

 And now， let me show you the preferred way of doing this。

 So instead of just saying torch dot save model here and what we instead want to do is to say torch dot save。

 and then we want to save the state di。 So here we have our model again。

 And then we say torch dot model dot。Tch dot save model， dot state。State diiced。And then。

 let's run this。So let me clear this。And let's open up the Explorer and delete this file here。



![](img/c885dfe548f252ed653964b1bd0374b3_15.png)

![](img/c885dfe548f252ed653964b1bd0374b3_16.png)

And now if we run our script again， then we again have the file。

 But now here it only saves the state dictates。 And now if we want to load our model again。

 we first have to define it。

![](img/c885dfe548f252ed653964b1bd0374b3_18.png)

So let's call this loaded model。Loaded model。Equals。

 and then let's also say the model and the number of input features is the same。 So it's 6。

 And then we call loaded model dot load state di。 And inside this。 Remember。

 we have to call torch dot load。 And then the file name。 And then again。

 we set our loaded model to evaluation mode。

![](img/c885dfe548f252ed653964b1bd0374b3_20.png)

And then if we run this。 So let's print the parameterss of the loaded model。 And up here。

 let's also print the parameterss of our normal model。



![](img/c885dfe548f252ed653964b1bd0374b3_22.png)

So this， if we don't do any training here， Then our model is still initialized with some random parameters。

 So let's run the script and let's check if the parameters are the same。



![](img/c885dfe548f252ed653964b1bd0374b3_24.png)

![](img/c885dfe548f252ed653964b1bd0374b3_25.png)

So here， yeah， we see that it worked。 and it first printed the parameters of the model of the normal model。

 and then here of the loaded model。 So these are the same。

 So we see we have a tenzo with the weights。 and we also have a tenzo with the bias。

 and this is the same for both of our model。 So we see that this worked too。 So yeah， again。

 so this is the recommended way of doing it by saying save dot model state diict。

 And then when we load it we call a load state dt method。



![](img/c885dfe548f252ed653964b1bd0374b3_27.png)

![](img/c885dfe548f252ed653964b1bd0374b3_28.png)

![](img/c885dfe548f252ed653964b1bd0374b3_29.png)

And yeah， so here we just save the state di。 So this holds the parameters。

 So let me show you how this state dit looks like。 So when we have our model。

 let's print model dot state。😊。

![](img/c885dfe548f252ed653964b1bd0374b3_31.png)

![](img/c885dfe548f252ed653964b1bd0374b3_32.png)

Dickt， and let's save this。And let's clear this and run the script。

 Then we see here we have our state thick。 So here we have the linear weight。

 which has the tenzo with the weights。 And then we also have the。Bastenzone。

 So this is our state dic。And now let me show you a common way of saving a whole checkpoint during training。

 So as you know， we can save any dictionary here。So let's say we also have a optimizer here。

 So let's say we defined a learning rate。 So let's say this is 0001。 And we also have a optr。

 This is， let's say， torch dot optim。Dots。Let's use stochastic gradient descent。

 And here we want to optimize the model parameters。

 and we will also have to give it the learning rate by saying learning rate equals the learning rate and our optimizer also has a state di。

 So we can also print the optimizer state di。 Now， if we clear this and run this。

 Then we see the state dictionary of the optimizer where we can see， for example。

 the learning rate and the momentum。So now during training。

 let's say we want to stop somewhere at some point during training and save a checkpoint。

 Then we can do it like this， so。

![](img/c885dfe548f252ed653964b1bd0374b3_34.png)

We create our checkpoint， and this must be a dictionary。 So let's create a dictionary。

 And as a first thing， what we want to save is， for example， the epoch。 So let's define the epoch。

 So the key is called epoch。 And let's say we are just， we are an epoch 90。

 And then we want to save the model state。 So we have to give it a key。 let's say model state。

 And here we use model dot state diict。And then we also want to save the optimizer state dick。

 So the key， let's say， optim state。 And then here as a value， we have to call optr state dick。

 So this is our checkpoint。 And now we can call torch dot save。



![](img/c885dfe548f252ed653964b1bd0374b3_36.png)

And then save the whole checkpoint。 So let's say torch checkpoint as， as a file name。

 Let's call this check。Point dot P， T， H。

![](img/c885dfe548f252ed653964b1bd0374b3_38.png)

And now again， let me show you the explorelorr and let's run the script。

So now we clear this and run this。 Then we see we have our checkpoint here。

 And now when we load this， we want to load the whole checkpoint， so。



![](img/c885dfe548f252ed653964b1bd0374b3_40.png)

![](img/c885dfe548f252ed653964b1bd0374b3_41.png)

We can comment this out。 And also， we don't need this， so。



![](img/c885dfe548f252ed653964b1bd0374b3_43.png)

Let's say our loaded checkpoint。 So let's say loaded checkpoint。Equals torch dot load。

 And then the file name was the same as this one。

![](img/c885dfe548f252ed653964b1bd0374b3_45.png)

And now you have to set up the different。Model and optimizes again。

 so we can get the epoch right away by saying epoch equals loaded at checkpoint。

 So this is a dictionary。 so we can just。

![](img/c885dfe548f252ed653964b1bd0374b3_47.png)

Call。对。Or access the epoch key。 And then for the model。 remember。

 we have to create our model here again。 So let's say model equals。

 and then the model with the number of input features equals 6。

 and the optimizer equals the same as this one So we don't have to use the same learning rate actually。

 So let me just grab this one here and paste it down here。 and for example。

 we can use the learning rate 0。 And then later we can see that we load the correct learning rate into the optimizer。

 So。

![](img/c885dfe548f252ed653964b1bd0374b3_49.png)

![](img/c885dfe548f252ed653964b1bd0374b3_50.png)

![](img/c885dfe548f252ed653964b1bd0374b3_51.png)

Now， let's say model dot load state。Dicks， and then here we give it the checkpoint。

 and then we access the key。 We call it model state。

 So this will load all the parameters into our model。 and the same with our optimizer。

 So we call optimizer dot load state dis。 And then we use the checkpoint。

 And here we call it optim state。 So now we have the loaded model and the optr and also the current epoch。

 So we can continue our training。

![](img/c885dfe548f252ed653964b1bd0374b3_53.png)

And let me show you that this is all correct by saying we want to print the optimizer dot state di。

 So if you notice here， we set the learning rate to 0。 and then we loaded the correct state di。

 So now if we run this。 And as a last thing， we printed the optimizer state di。

 then we see we have the same learning rate as in the initial optimizer。 So this work too。



![](img/c885dfe548f252ed653964b1bd0374b3_55.png)

![](img/c885dfe548f252ed653964b1bd0374b3_56.png)

![](img/c885dfe548f252ed653964b1bd0374b3_57.png)

So this is how we can save and load a whole checkpoint。 And yeah。

 these are all the three ways of saving you have to know。 And now as a last thing。

 I want to show you what you have to consider when you are using a GP during training。

 So if you are doing training and loading both on the CPU then you don't have to make any difference。

 So you can just use it like I did here but now if you save your model on the GP and then later you want to load it on the CPU。

 then you have to do it this way。 So let's say somewhere during your training。

 you set up your coa device and you send your model to the device and then you save it by using the state di。



![](img/c885dfe548f252ed653964b1bd0374b3_59.png)

![](img/c885dfe548f252ed653964b1bd0374b3_60.png)

![](img/c885dfe548f252ed653964b1bd0374b3_61.png)

And then you want to load it to the CPU。 So you have your CPU device。

 then you create your model again， and then you call load state died and then load path。

 And here you have to specify the map location。 And here you give it the CPU device。

 So this is if you want to save on the GP and load on the CPU。Now， if you want to do both on the GPU。

 So you send your model to the Kuda device and saved it。

 and then you also want to load it on the GPU， then you just do it like this。 So you。

Set up your model， you load the state di， and then you send your model to the Kuda device。

And now as a third option。 So let's say you saved your model on the CPU。 So you didn't send。

 you didn't call model to Kuda device somewhere。 But then later， during loading。

 you want to load it to the GP， you have to do it like this。 So first you specify your Coa device。

 Then you create your model。

![](img/c885dfe548f252ed653964b1bd0374b3_63.png)

![](img/c885dfe548f252ed653964b1bd0374b3_64.png)

And then you call model do load state dit and then torch load with the path。

 and then as map location， you specify kuda and then colon and then any GPU device number you want。

 So for example， Kuda colon0。 and then also you have to call model to device So to the kuda device。

 So this will send the model to device to the device and also all the loaded parameter tenszoos to the device。

 So then you can continue with your training or interference on the GPU and of course。

 you also have to send all the training samples to the device that you then use for the forward path。



![](img/c885dfe548f252ed653964b1bd0374b3_66.png)

![](img/c885dfe548f252ed653964b1bd0374b3_67.png)

![](img/c885dfe548f252ed653964b1bd0374b3_68.png)

So yeah， this is what you have to consider when you' are using a GPU。



![](img/c885dfe548f252ed653964b1bd0374b3_70.png)

And now， you know all the different ways of saving and loading your model。 And yeah。

 that's all for now。 I hope you enjoyed this tutorial。 And if you like this。

 please consider subscribing to the channel and see you next time， bye。😊。



![](img/c885dfe548f252ed653964b1bd0374b3_72.png)