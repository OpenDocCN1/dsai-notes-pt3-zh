# PatrickLoeber【中英⚡PyTorch入门教程｜PyTorch Tutorials - Complete Beginner Course】 p21 p20 PyTorch Lightning Tutorial - Lightweight PyTorch Wrapper For ML Researchers -BV1B7fJYuE3A_p21-

Hey， guys， welcome to your new Pytor tutorial。 Today， we'll be talking about Pytor lightning。

 Pytorch Lightning is a lightweight Pyot wrapper。 It aims to reduce boiler plate codes so that implementing the algorithm and also improving your model。

 So tweaking and optimizing it can be way faster。 You don't have to remember all the tiny details of the Pytor framework。

 because lightning takes care of all that。😊，And another great feature is that it prints out warnings and gives you helpful machine learning tips or hints if you make mistakes。

 So we will see all that later。 So usually I'm skeptical when it comes to wrapper frameworks that abstract away a lot of things。

 But this time， I can really recommend it。 I still advise that you learn the underlying basics first。

 and if you haven't yet， then you can check out my free Pytorch course here on YouTube。

 The link is in the description。 But if you are already familiar with Pytorch。

 then you can check out Pytoch lightning and see if you like it or not。

 So today I'll be converting one of the codes from my Pytorch course to Pytch lightning。

 So you can get a feel how this framework works and how you can use it。 Allright， let's jump into it。

 So first of all， Pytoch lightning is open source so you can find it here on Github。

 and they also have a website with a nice documentation that you get you started。 I will put。😊。



![](img/9bfd815daaf2c68d52dc66079efb45cc_1.png)

The links in the description as well And now here are some of the details that you no longer have to worry about with Pytorch lightning so you no longer have to worry about when to set your model to training or evaluation mode you don't have to worry about using a device for GPU support and then push your model and all your tensors to the device you can easily turn off GPU or even GPU support with lightning and you can easily scale it up then you also have to no longer care about the zero grad or calling backward and optimize a step you no longer have to worry about using torch no grad or detach and as a bonus you have integrate a tenor board support。

And it also prints out tips or hints， which we will see later。 So let's jump to the code。

 And for this example， we'll be taking one of the codes from my Pytoch tutorial。

 So you can find it on Github and then in this case， we take tutorial number 13。

 So this is a simple feed forward neural net， which is applied to the Mist data set to do diit classification。

 So now let's grab some of the code and write a new code with Pytoch lightning。 So first of all。

 so let me delete this。 And now let's start with a fresh Python script。 and by the way。

 and when you want to install Pytoch lightning， you have two common options。

 the first one is to use Pip。 So you just say Pip install Pytoch lightning。 or if you use Conda。

 then you can grab this command。

![](img/9bfd815daaf2c68d52dc66079efb45cc_3.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_4.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_5.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_6.png)

So I already did this in my terminal。 So Pyto lightning is already installed here。

 So let's go back to the code and copy and paste some of the things。

 So we want to have all the same import statements。



![](img/9bfd815daaf2c68d52dc66079efb45cc_8.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_9.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_10.png)

And as an addition now， we also import Pytorrch lightning。

 So we say import Pytorrch lightning with an underscore S P， L。



![](img/9bfd815daaf2c68d52dc66079efb45cc_12.png)

And now we want to convert our model， our neural net to a lightning model。

 so we grab this code and then we copy and paste it in here and now instead of deriving from N and dot module we now derive from P dot lightning module。

 This will give us the same functions as the original model。

 but it will also give us some more functions， which we will see in a second。

 So now the init function is still the same and the forward function also is still the same。

 So we then need all the hyperparameters。 So let's grab them as well。

 So let's grab the hyperparameters and paste them in here。😊。



![](img/9bfd815daaf2c68d52dc66079efb45cc_14.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_15.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_16.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_17.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_18.png)

HereAnd now we need to implement some more functions。 So let's quickly go to the official website。

 Here。 you see a step by step guide， by the way， And you also have a nice comparison how Pyt code looks versus Pytoch lightning。

 and what it abstracts away。 So as you can see， we also need to define a training step。

 a configure optimizes function and a train data loader。 So let's copy all of these in here。



![](img/9bfd815daaf2c68d52dc66079efb45cc_20.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_21.png)

And now for the， let's start with the simplest one。

 So the configure optimizers there you simply put in the optimizer that you created。

 So in our original script。 We set up the optimizer here。 So this is the atom optimizer。

 And then you return it。 so we can return this one in one line。 So this will be our optimizer。

 our atom optimizer with the learning rate from our hyperparameters。



![](img/9bfd815daaf2c68d52dc66079efb45cc_23.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_24.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_25.png)

And then we want to in implement the training step。



![](img/9bfd815daaf2c68d52dc66079efb45cc_27.png)

So for the training step， we are doing exactly what we are doing in our training loop。

 and now we don't have no longer have to worry about our fall loops about unpacking our images and labels and then hear the optr0 grabs the backward and the step。

 So we simply grab this part。

![](img/9bfd815daaf2c68d52dc66079efb45cc_29.png)

And paste it in here。 And as you see in the training step function， we get a batch and a batch index。

 So we unpack our batch into x and y。 and then let me copy the code。 So。

This is now our images and our labels。 And then we have to reshape our images。

 and we no longer have to push it to the device。 So we remove all of those things。

And then we do the forward pass。 And here we can actually use self because we are inside of our model class。



![](img/9bfd815daaf2c68d52dc66079efb45cc_31.png)

And then we apply the criterion。 and in our original code。

 we set up the criterion here as N and dot cross entropys。

 But we can also use it instead if we use the functional module。 So for this， we say。



![](img/9bfd815daaf2c68d52dc66079efb45cc_33.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_34.png)

Import torch， dot N， N， dot funk。Chhannel S， F。And then down here， we say our loss equals。

 And now we can call。F dot cross entropy with our outputs and the labels。

And these are all the things。 And for now， we only want to return a dictionary with this loss。

 So Pyto lightning needs this dictionary so that it can show you the loss during the training。

And this is all we need in our training step。And then we also have to implement the train data loader function。

 So what we want to do here is we want to do what we did in the beginning here。

 we set up the training data set and the training data loader。

 So let's copy this and paste this in the function here。 So first our train data set。

 So this is this one。 and then the train data loader。 So this one。



![](img/9bfd815daaf2c68d52dc66079efb45cc_36.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_37.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_38.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_39.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_40.png)

And then we want to return the train data loader or train loader。

 And now this is all we need to start a training。 And now what we want to do is we say if。

Name equals equals， underscore underscore main。Then we have to set up a lightning trainer。

 So for this， we import a trainer。 So we say from Py toch lightning import trainer。

 Then we want to set up a trainer。 So here we say our trainer equals our lightning trainer。

 And for now， I can show you a trick that is very helpful during development。

 So you say fast defron equals true。 This will run a single batch through train。

 and also through validation。 if we have a validation step。 And with this。

 you can test if your model works。 So now we also have to set up our model。 So we say model equals。

 And let's call this lit model to make it clear that this is a lightning model。 So lit。😊。

uralNeAnd here we say let neural net with the hyperparameter。 So it needs the input size。

 It needs the hidden size， and it needs the number of classes。

 which we all have here for our hyperparameters。 Then we have to fit it to our trainer。

 So we say trainer dot fit our model。 And now we can already run it and see if this is working。

 So now。Let's go to the console。 And now let's run this file。 So we say Python lightning dot pi。

Here we get a arrow。 So， of course， I rename the lit neural net。 So I also have to say。

Li neural net here。 And now again， let's run it。And now we see it starting。

 so we see that we have no GPU support。 We also get an overview of our different layers and the parameters。

 Then since I'm running it the first time it's downloading the data set。

And then here is the training。 So it worked。 So it only did one batch because we set fast defffron equals true。

 So let's clear it and test it one more time。 So now it shouldn't download it anymore。

And this was way faster。 And now here， for example， we get one warning。 so it says。

The data loader train data loader does not have many workers， which may be a bottleneck。

 Consider increasing the value of nu workers argument。 try4。

 So this is actually the first tip that can help us to speed up our code。

 So here what we want to do is in our train loader。 We can also give it the argument。

 nu workers equals 4。 And now let's clear this and run it again。And now our warning is gone So now。

Here we see the overview。 we now only used one epoch and here we have the loss。

 So now if you want to have a full training， we can also give our trainer。

 the argument max epoch equals， and then the number of epochs that we defined。 epochs。

 So this is one of the hyperparameters。And now let's set this to false again。

 So now this should do a full training。 And now， let's see if this is working。

And now this should take。Max epoox， sorry。Now this should take a little longer。And yeah。

 we see So we get a nice progress bar， and we see our training works and our loss should slowly decrease。

 So this is working。😊，So now let me stop this for now。

 And now the next thing we want to do is to do our evaluation or testing。

 So similar to the training step and training data loader。

 We now also want to add a validation step and a validation data loader。 So let me copy this。

 And let me paste it in here。 And this has to be called validation step。

And here we are doing the same thing actually。 So as in the test train training step。

 So we reshape our images， then we do the forward pass and calculate the loss。

 And this time we use the key well loss or validation loss。

 and now let's set our fast defron to true again。 And let me run it again。 So now if we run it。

 we should get an error。 And yeah， here we get the exception， you have defined validation step。

 but have not passed in a validation data loader。 So now we know what we have to do。

 we also have to use a validation data loader。 So let me copy and paste this。

And this has to be called well data loaddown。 So if you're not sure， you can go to the official。



![](img/9bfd815daaf2c68d52dc66079efb45cc_42.png)

Documentation， and then scroll to the validation loop。 There。 you see the。



![](img/9bfd815daaf2c68d52dc66079efb45cc_44.png)

3 functions that you need。So。Now， first of all， now we have our。Validation data set。

 So here we want to say， or we want to grab。

![](img/9bfd815daaf2c68d52dc66079efb45cc_46.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_47.png)

The next or the test data set。 So in this case， I call the test data set。 but actually。

 you want to have。A split of your data to a training data set。

 a validation data set and a test data set。 So the validation data set is used to get an unbiased evaluation of the model performance while tuning the hyperparameters。

And then the test dataset set is used at the very end to provide an unbiased evaluation with data that the model has never seen before。

 So in this example， we， let's say we only have two splits of our data set。 Now。

 we only use the first two steps training and validation。 So let me copy this and paste it in here。

 And let's rename this to a validation data set。 And then let's grab the validation data loader。



![](img/9bfd815daaf2c68d52dc66079efb45cc_49.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_50.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_51.png)

And rename it to v loader and then return the v loader。And now let's run it again。

 So let's say Python lightning dot pi。And we get anarrow。 So data set equals well data set。

 of course。 And let's clear this and run it again。 and then it should do one pass through training and validation and we see it worked。

 And now we again get the same warning。 So here we use the nu workers equals4。

 So let's clear it and try it again。 So you see it already starts giving us hints when we make some mistakes。

 And now we see it worked。 And now it it's also to suggesting to define a validation epoch end method for accumulating stats。

 So let's go to the documentation and grab this function to see how it looks like。 So。



![](img/9bfd815daaf2c68d52dc66079efb45cc_53.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_54.png)

We copy and paste this。 So this is the function that is executed after each validation epoch。

 And here we want to calculate the average loss。 So actually， in our example。

 we want to do exactly the same。 So we want to call calculate the average loss by saying this is torch stack。

 And then since we。Called the key validation loss。 We can access it here and then calculate the mean over all the。

Losses， and now， for now， let's not worry about this。

 And then we return the average loss as a dictionary。And then we are done。 So now， if we clear it。

Then， we should get a。One pass now no more warning。

And now we have everything that we need for our code。

 So this is all we need with pie touch lightning。And now， let me show you one more hint。

 what we can get。 So， for example， in our validation loader。

 if we accidentally set shuffle equals true and then try to run it。

 we should get a warning or a hint。So yeah， here we see user warning。

 Yourve data load has shuffle equals true。 It is best practice to turn this off for validation and test data loadus。

 So you see， we can actually already improve our code with this framework。And now。

 let's compare this with our。Original code。 So if we have a look at this code in Github。

 then we no longer need this device function functionality。



![](img/9bfd815daaf2c68d52dc66079efb45cc_56.png)

And we no longer needs to have the manual for loop over all epochs and over all the batches。

 we no longer have to care about these two device calls。

 we no longer have to care about the optimizer and the backward pass and also we can leave out the whole validation loop because we can calculate this with this validation step and now for example。

 if you also want a training step， we can easily edit the same way as we are doing with this function and with this function and now for example。

 if you want to use GPus， then we can easily do this by giving our trainer the argument， GPus equals。

 for example， one and when you want to scale it up and have more GPus available， you can also use。



![](img/9bfd815daaf2c68d52dc66079efb45cc_58.png)

2， or let's say4， or you can use even T support。 So it's really easy to switch from CPU to GP and then scale it up。

 And you can also have a distributed backend。 So DP， for example。

You can also easily switch to 16 bit precision。 You can lock the GP memory。

 So a lot of features that you can now very easily test with this framework。

 You just have to use all the different arguments for the trainer。 and， for example。

 one more helpful function that you can try is auto L R。Find equals true。

 This will run a algorithm to find the best learning rate。 So you can try this one。You can also set。

 for example， deterministic equals true。 so this allows it to reproduce your results。

Or you can apply gradient clipping very easily by just passing in the argument。

 Claient gripve equals， and then some value between 0 and  one， I guess。 So for this， you again。

 have to check out the official documentation。

![](img/9bfd815daaf2c68d52dc66079efb45cc_60.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_61.png)

There you find all the different features and use cases。

 And now let me show you the full training and validation。

 So let's remove this And now let's set the argument fast defffron to false again。 So again。

 I'm not having a high number of epochs。 So it's only two because it takes a long time here without the GP。

 but let's run it anyway。

![](img/9bfd815daaf2c68d52dc66079efb45cc_63.png)

So again， we see the progress in our first epoch here and how our loss is decreasing。

 And when this is done， we should a faster progress bar for the validation loop。So now be careful。

 Now here we see the validation loop。 and now our second training epoch starts。 So， yeah。

 this is working。And now the second validation and now it's done。

 and we can see and inspect the final loss。 So this worked。 And now as the last thing。

 let me show you the integrated tenor board support。 So as you can see。

 there is all already a folder， which is called lightning lock。

 So it's already automatically saving some checkpoint。😊，So and now。

 if we want to inspect the different losses during in the tensor board， then what we have to do is。

 for example， if you want to inspect the training， then in our training step。

 we create another dictionary。 and let's call this Tenor board locks equals， and this is an again。

 a dictionary。And here， let's call this train loss as a key and as value。 it's the same loss。

 And then we also append the tensup board loss to our dictionary。

 And we have to give it the key lock。 and then lock。 And this is our tensab board lock。

And now the same in our validation epoch end。 So here we create the tens ofboard blockss。

 And here let's call it average validation loss。 And this is the average。Average loss。

 And then here again， we use the key lock and then the tenor board locks and。Now。

 let's run it one more time to save all those things。So now we have to wait until this is done。

So now our training and validation is done。 So now it should have。

Saavve all of those to the lock directory。 And now we can start the tensor board by saying tensor board minus minus lock。

D equals， and then light ning locks。 And by the way。

 I also have a full tutorial about how you can work with the Tensor board。

 I will also put the link in the description。And with lightning。

 you don't have to install it manually become because it comes with the requirements of lightning。

 So this should automatically work now。 So now if we hit run。 and sorry， this was no underscore。

Minus minus loar equals lightning locks。And now it works。 So now our Tensor board is running here。

 So now if we open up this。

![](img/9bfd815daaf2c68d52dc66079efb45cc_65.png)

Then we should inspect the epochs。 Then we have the average validation loss。

 So since we only use two。Epochs， we don't see a lot of difference here。 So it's only a one line。

 but for the training loss， this is what we looked after each。Training step。

 So here we see a nice graph how our training loss decreased。 So yeah， you see。

 we have automatic tensor board integration。 and it's very easy to work with this tool。 So yeah。

 these are most of the features I wanted to show you。 And let me know in the comments。

 if you like this framework。 And if you also think that it can simplify your development process。

 And if you like this video， then please hit the like button and consider subscribing to the channel。

 this helps me a lot and see next time by。

![](img/9bfd815daaf2c68d52dc66079efb45cc_67.png)

![](img/9bfd815daaf2c68d52dc66079efb45cc_68.png)