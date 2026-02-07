# mrdbourke《一天学会pytorch深度学习｜Learn PyTorch for deep learning in a day Literally》中英 - P66：103. Training and testing loops for batched data.zh_en - GPT中英字幕课程资源 - BV1kx4y1r79d

Good morning。 Well， might not be morning wherever you are in the world。😊。



![](img/8cc3a09560b2d38162ae54c3bfed248a_1.png)

It's nice and early here。 I am up recording some videos because we have a lot of momentum going with this。

 But look at this。 I took a little break last night。 I have a runtime disconnected。

 But this is just what's going to happen if you're using Google Coab since I use Google Coab Pro。😊。

Completely unnecessary for the course， but I just found it worth it for how much I use Google coabab。

 I get longer idle timeouts。 So that means that my coab notebook will stay persistent for a longer time。

 But， of course， overnight， it's going to disconnect。 So I click reconnect。

 And then if I want to get back to wherever we were。

 because we downloaded some data from Torchvision dot data sets。 I have to rerun all of these cells。

 So a nice shortcut， we've might have seen this before is to just come down to where we were。

 And if all the code above works。 Oh， there we go。 I wrote myself some notes of where we're up to。😊。



![](img/8cc3a09560b2d38162ae54c3bfed248a_3.png)

Let's go run before。 So this is going to run all the cells above。 And we're up to here，3。3。

 creating a training loop and training a model on batches of data。

 So that's going to be a little bit interesting。 And I wrote myself another reminder here。

 This is a little bit of behind the scenes。 The optimizer will update a model's parameters once per batch rather than once per epoch。

 So let's hold myself to that note。 And make sure I let you know。 So we'll go。😊。

Make another title here。Let's go creating a training loop and training a model on batches。Of data。

So something a little bit different to what we may have seen before if we haven't created batches of data using data loader and recall that just up above here。

We've got。Something like 1800 dead， There we go。 So we've split our data into batches rather than our model looking at 60000 images of fashion Mnes data at one time。

It's going to look at 1875 batches of 32， so 32 images at the time。Of the training data set。

And 313 batches of 32 of the test data set。 So let's go to training loop and train our first model。

So I'm going to write out a few steps， actually。Ca we have to do a little bit differently to what we've done before。

 So one， we want to loop through epochs。 So a number of epochs loop through training batches。

 And by the way， you might be able to hear some birds singing。 The sun is about to rise。

 I hope you enjoy them as much as I do。😊，So we're going to perform training steps。

And we're going to calculate， calculate the train loss per batch。

So this is going to be one of the differences between our previous training loops。

And this is going to after number two， we're going to loop through the testing batches。

 so we'll train and evaluate our model at the same。Step or same loop。

And we're going to perform testing steps。And then we're going to calculate the。Test loss per batch。

 as well。Per batch。Wonderful。4， we're going to， of course， print out what's happening。

You may have seen the unofficial Pytorch optimization loop theme song。

And we're going to time it all for fun， of course， because that's what our timing function is for。😊。

So let's get started。😊，There's a fair few steps here， but nothing that we can't handle。

 And remember the motto， if in doubt， code it out。Or there's another one， if in doubt， run the code。

 but we haven't written any code to run just yet。So we're going to import TQDM for a progress bar。

 If you haven't seen TQDM before， it's a very good Python progress bar。

That you can add with a few lines of code。 So this is just the Githaour's open source software。

 One of my favorite pieces of software。And it's going to give us a progress by to let us know how many epochs our training loop has gone through。

😊，It doesn't have much overhead， but if you want to learn more about it。

 please refer to the T Q DM Github。 However， the beautiful thing is that Google Coab has T Q DM built in because it's so good and so popular。

😊，So we're going to import from T QDM do auto。 So there's a few different types of T QDm progress bars。

 do auto is just going to recognize what compute environment we're using。

 and it's going to give us the best type of progress bar for what we're doing。 So， for example。

 Google coab is running a Jupyter notebook behind the scenes。

 So the progress bar for Jupyter notebooks is a little bit different to Python scripts。

So now let's set the seed and start the timer。We want to write all of our training loop in this single cell here。

 and then。Once it starts， once we run this cell， we want the timer to start so that we can time how long the entire cell takes to run。

So， we'll go。Train time。 Start on CPU。Equals， we set up our timer before。Beautiful。

Now we're going to set the number of epochs。Now， we're going to keep this small for faster training time so we can run more experiments。

 so。We'll keep this small for faster。Training time。 That's another little tidbit。

 Do you notice how quickly all of the cells ran above。 Well。

 that's because we're using a relatively small data set。In the beginning。

 when you're running experiments， you want them to run quite quickly so that you can run them more often so you can learn more about your data so that you can try different things。

 try different models。So this is why we're using number of epochs equals3。

 We start with three so that our experiment runs in 30 seconds or a minute or so that way。

 if something doesn't work， we haven't wasted so much time waiting for a model to train。Later on。

 we could train it for 100 epochs if we wanted to。So we're going to create a training and test loop。

 So for epoC in TQDM range epochs。Let's get this going。 So for TQDM to work。

 we just wrap our iterator with TQDM and you'll see later on how this tracks the progress。

So I'm going to put out a little print statement here。We'll go epoC。

 and this is just going to say what epoch we're on。There we go here。

That's something that I like to do quite often is put little print statements here and there so that we know what's going on。

 So let's set up the training。 We're going to have to instantiate the train loss。

 We're going to set that to 0 to begin with。 And we're going to cumulatively add some values to the train loss here。

 And then we'll see later on how this accumulates， and we can calculate the training loss per batch。

Let's what we're doing up here， calculate the training loss per batch。

 and then finally at the end of the loop， we will divide our training loss by the number of batches so we can get the average training loss per batch and that will give us the training loss per epoch。

Now that's a lot of talking if that doesn't make sense。 remember， if in doubt， code it out。

 So add a loop to loop through the training batches。So because our data is batchrified now。

 and I've got a crow or maybe a cookaber sitting on the roof。Across from my apartment。

 it's our singing its song this morning。Lovely。So we're going to loop through our training batch data。

 So I've got four batch comma X， Y， because remember our training batches come in the form of X。

 So that's our data or our images and Y， which is label。 You could call this image。

Label or target as Py to would。 But it's convention to often call your features X and your labels Y。

 We've seen this before。And we're going to enumerate the train data loader as well。

We do this so we can keep track of the number of batches we've been through。

 so that will give us batch there。I're going to set Model0 to training mode。

Because even though that's the default， we just want to make sure that it's in training mode。

Now we're going to do the forwardd pass， if you remember。

 what are the steps in App to optimization loop？We do the forward pass。 We calculate the loss。

 Opr 0 grad， loss backwards， optimizer step， step， step。 So let's do that。 Hey， Model 0。

 We'll put the features through there， and then we're going to calculate the loss。😊。

We've been through these steps before， so we're not going to spend too much time on the exact steps here。

But we're just going to prac writing them out。 And， of course， later on， you might be thinking。

 Daniel， how come we haven't functionised this training loop already。

 We've seen to write the same generic code over and over again。 Well。

 that's because we like to practice writing Pytorch code， right。

We're going to functionise them later on。 Don't you worry about that。

 So here's another little step that we have in number4 is we have the training loss。

 And so because we've set that to0 to begin with， we're going to accumulate the training loss values every batch。

 So we're going to just add it up here。 And then later on。

 we're going to divide it by the total number of batches to get the average loss per batch。

So you see how this loss calculation is within the batch loop here。

So this means that one batch of data is going to go through the model。

 and then we're going to calculate the loss on one batch of data。

 And this loop is going to continue until it's been through all of the batches in the train data loader。

 So 1875 steps or whatever there was。So accumulate。Train loss。And then we're going to。

Optimizeizer zero， grad。Optimr dot。Zero grad。And then number four is what loss backward。

Lost backward， we'll do the back propag step， and then finally we've got number five。

 which is optimizer step。So this is where I left my little note above。To。Remind me。

 and to also let you know， highlight that the optimizer will update a model's parameters once per batch rather than once per epoch。

 So you see how we've got a four loop inside our epoch loop here。😊，So the batch loop。

So this is what I meant that the optimizer， this is one of the advantages of using mini batches is not only is it more memory efficient because we're not loading 60000 images into memory at a time。

 We are updating our models' parameters once per batch。

Rather than waiting for it to see the whole data set with every batch。

 our model is hopefully getting slightly better。So that is because the optimizer dot step call is within the batch loop rather than the epoch loop。

So let's now print out what's happening。Print out what's happening。So if batch。

 let's do it every 400 or so batches， because we have a lot of batches。

 We don't want to print out too often。 Otherwise， we'll just fill our screen with numbers。

 That might not be a bad thing。But 400 seems a good number。 That'll be about 5 print outs。

 if we have 2000 batches。So， print。Looked at。 And， of course。

 you can adjust this to whatever you would like。 That's the flexibility of py torch。

 flexibility of Python as well。 So looked at how many samples have we looked at。

 So we're going to take the batch number， multiply it by x。 The length of x is going to be 32。

 because that is our batch size。Then we're going to just write down here， the total number of。

Items that we've got in our data set and we can access that by going train data loader dot data set。

 So that's going to give us length of the data set contained within our train data loader。

 which is you might be able to guess 60，000 or should be。Now。

We have to because we've been accumulating the train loss。

This is going to be quite high because we've been adding every single time we've calculated the loss。

 We've been adding it to the train loss， the overall value per batch。

 So now let's adjust if we wanted to find out， see how now we've got this line we're outside of the batch loop We want to adjust our training loss to get the average training loss per batch per epoch。

 So we're coming back to the epoch loop here。 a little bit confusing。

 but you just line up where the loops are， and this is going to help you figure out what context you're computing in。

 So now we are in the epoch loop。So， divide。Total train loss by length of train data loader。

Oh this is so exciting training our biggest model yet。 so train loss equals。😊，Or divide equals。

 We're going to reassign the train loss。 We're going to divide it by the length of the train data loader。

 So why do we do this， Well， because we've accumulated the train loss here。

For every batch in the train data loader， but we want to average it out across how many batches there are in the train data loader。

So this value will be quite high until we readjust it to find the average loss per epoch because we are in the epoch loop。

All right， fair few steps going on， but that's all right。 We'll figure this out。

 We'll watch it happening in a minute。 Let's code up the testing loop。So testing。

 what do we have to do for testing？Well， let's set up a test loss variable。

Why don't we do accuracy for testing as well， Did we do accuracy for。Training。

We didn't do accuracy for training， but that's all right。 We'll stick to doing accuracy for testing。

We'll go Model0 dot。A vow will put it in evaluation mode。And we'll turn on our inference mode。

 context manager。With torch dot inference mode。 Now we'll do the same thing for X。

 Y in test data loader。 We don't need to keep track of the batches here again in the test data loader。

 So we'll just loop through X So features， images and labels in our test data loader。

We are going to do the forward pass。Because the test loop we don't have an optimization step。

 we are just passing our data through the model and evaluating the patterns it learned on the training data。

So we're going to pass in X here。This might be a little bit confusing。Let's do this X test， Y test。

That way， we don't get confused with our X above。For the training set。

 now we're going to calculate the loss。Aumulatively might smell that wrong have to sound that out。

What do we have here， So we've got our test loss variable that we just assigned to0 above。😊。

Just up here。 So we're going to do test loss plus equals。 We're doing this in one step here。

 Test pre， Y test。 So we're comparing our test prediction to our Y test labels， our test labels。

Now we're going to back out of the for loop here。Because that's all we have to do the forward pass and calculate the loss for the test data set。

Oh， I said we're going to calculate the accuracy。Silly me。 So calculate accuracy。Let's go， Test act。

And we got plus equals。We can bring in our accuracy function here。

 That's what we downloaded from our helper functions dot pi before。😊，Why true equals y test。

 And then y pre equals test Pre dot arg max dimm equals 1。 Why do we do this？ Well。

 because recall that the outputs of our model， the raw outputs of our model are going to be logits。

And our accuracy function expects our true labels and our predictions to be in the same format。

If our test pre is just logits， we have to call Argms to find the logit value with the highest index。

 and that will be the prediction label。 And so then we're comparing labels。To labels。

 that's what the Agmax does here。So we can back out of the batch loop now。

 and we're going to now calculate。Calculate。The test loss。Average。Per batch。 So let's go here。T loss。

Divide equals length test data loader。 So because we were in the context of the loop here of the batch loop。

Our test lost and test accuracy values are per batch and accumulated every single batch。

 So now we're just dividing them by how many batches we had Test data loader and the same thing for the accuracy。

 calculate the a or test a average per batch。 So this is giving us test loss and test accuracy per epoch Test a divided equals length。

Test data loader。 wonderful。 We're so close to finishing this up。

 And now we'll come back to where's our epoch loop。😊。

We can these lines are very helpful in Google Co Lab。 we scroll down。I believe if you want them。

 you can go settings or something like that。 Yes， settings。

 that's where you can get these lines from if you don't have them。 So print out what's happening。

We are going to print F equals n。 Let's get the train loss in here。

Train loss and we'll print that to four decimal places。And then we'll get the test loss， of course。

Test loss and we'll go。 We'll get that to four decimal places as well， and then we'll get the test a。

Test accuracy。 We'll get that to。Four decimal places as well。For F。Wonderful。And then finally。

 one more step is to。 Oh， we've written a lot of code in this video。

 We want to calculate the training time， because that's。😊，Another thing that we want to track。

 we want to see how long our model is taken to train。 So train time end on CPU。

Is going to equal the timer。 And then we're going to。Get the total train time， model 0 so we can。

 we'll set up a variable for this so we can compare our modeling experiments later on。

 We're going to go print train time， start equals。Train time。 Start on CPU。Andd eles。

Train time and on CPU。And finally， the device is going to be string next， Model 0 dot。

Pararameterters， so we're just this is one way of checking where our model zero parameters live。So。

Beautiful。All right。Have we got enough brackets there， I don't think we do。Okay， there we go。Who。

I'll just show you what the output of this is。 So next， model 0 dot parameters。

What does this give us。Oh， can we go device here？哦。What do we have here？Model 0 thought parameters。

 I thought this was a little trick。And then if we go， next。Prameter containing。

I thought we could get。Deeve， oh， there we go。 Excuse me。That's how we get it。

 That's how we get the device that it's on。 So let me just turn this。

This is what the output of that's going to be。CPU， that's what we're after。

So troubleshooting on the fly here。 hopefully all of this code works。

 So we went through all of our steps。 So we're looping through epochs at the top level here。😊。

We loop through the training batches perform the training steps。

 So our training loop forward pass loss calculation， optimizer 0 grad loss backwards。

 calculate the loss per batch， accumulate those。 We do the same for the testing batches except without the optimizer steps。

 and print out what's happening。 and we time it all for fun。 a fair bit going on here。

 But if you don't think there's any errors， Give that a go。 run that code。

 I'm going leave this one on a cliff hanger。 and we're going to see if this works in the next video。

😊。

![](img/8cc3a09560b2d38162ae54c3bfed248a_5.png)

![](img/8cc3a09560b2d38162ae54c3bfed248a_6.png)

我 see以对。😊，Welcome back。Ho， the last video was pretty full on。 We did a fair few stamps。

 but this is all good practice。 The best way to learn P torch code is to write more pin torch code。

 So did you try it out。😊，Did you run this code， Did it work， Did we。

 probably have an error somewhere， Well， let's find out together。 already。

 let's train our biggest model yet in 3，2，1， bomb。😊，Oh， of course we did。 What do we have。

 What's going on。Indentation error。 classic， so。Print out what's happening。

 Do we not have an indent there。Oh， is that not in line with where it needs to be。Excuse me， okay。

Why is this not in light？ So this is strange to me， enter， How did this all get。Off by one。

I'm not sure， but this is just what you'll face。 Like。

 sometimes you'll write this beautiful code that should work。

 But the main error of your entire code is that it's off by a single space。

 I'm not sure how that happened， but we're just gonna。Pull this all in the line。

We could have done this slightly selecting it all， but we're going to do it line by line。

 just to make sure that。Everything's in the right order。😊，Beautiful。And。

We print out what's happening， ready， three， two， one， round two。We're going Okay。

 so this is the progress bar I was talking about。 Look at that。 How beautiful is that Oh。

 we're going quite quickly through all of our samples。 I need to talk faster。😊，Oh， there we go。

 we' got some good results， we' got the test， the train loss， the test loss。

 and the test accuracy is pretty darn good。😊，Oh my goodness， this is a good baseline already。😊，67%。

 So this is showing us it's about 7 seconds per iteration。

 Remember TQ DM is tracking how many epochs we're going through。

 So we have three epochs and our print statement is just saying， hey。

 we've looked at0 out of 60000 samples。 Then we looked at 12000 out of 60000 samples。😊。

And we finished on on epoch2 because it's 0 indexed and we have a train loss of 0。

4550 and test loss 4766 and a test accuracy，834265 and a training time about just over 21 seconds or just under 22。

 So keep in mind that your numbers may not be the exact same as mine。

 they should be in the same realm as mine， but due to inherent randomness of machine learning。😊。

Even if we set the manual seed might be slightly different。

 so don't worry too much about that and what I mean by in the same realm。

 if your accuracy is 25 rather than 83 well then it's probably something's wrong there。

 but if it's 83。6 well then that's not too bad and the same with the train time on CPU this will be heavily dependent how long it takes to train will be heavily dependent on the hardware that you're using behind the scenes。

So I'm using Google Co Laab Pro。 Now that may mean I get a faster CPU than the free version of Google Coabab。

 It also depends on what CPU is available in Google's。

Computer warehouse where Google CoLab is hosting。Of how fast this will be。 So just keep that in mind。

 if your time is 10 times that， then there's probably something wrong。

 If your time is 10 times less than that。 Well， hey。

 keep using that hardware because that's pretty darn good。 So let's keep pushing forward。

 This will be our baseline that we try to improve upon。 So we have an accuracy of 83。5。

 And we have a train time of 20 or so seconds。 So we'll see what we can do with a model on the GPU later and then also later on a convolutional neural network。

😊，So let's evaluate our model。 Where are we up to。What we just did we built a training loop so we've done that that was a fair bit of code。

 but now we're up to we fit the model to the data and make a prediction。

 let's do these two combined hey we'll evaluate our model。😊，So we'll come back。

 Numb four is make predictions。And get model zero results。

Now we're going to create a function to do this because we want to build multiple models and that way we can if we have。

 say model 0，1，2，3， we can pass it to our function to evaluate that model and then we can compare the results later on。

😊，So that's something to keep in mind if you're going to be writing a bunch of code multiple times。

 you probably want to functionise it， and we could definitely do that for our training and lost loops。

 but we'll see that later on。 So let's go de model， So evaluate a given model。

 we'll pass it in a model which will be a torch do N N dot module or of type。

 and we'll pass it in a data loader， which will be of type。😊，Torch。utils。dat data loader。

And then we'll pass in the loss function。So that it can calculate the loss。

 we could pass in an evaluation metric if we wanted to track that too。

 so this will be torch and end dot module as well， and then oh there we go。

Speaking of an evaluation function was passing in our accuracy function as well。😊，And I don't want L。

 I want that。 So we want to returns。A dictionary containing。

The results of model predicting on data loader。So that's what we want。

We're going to return a dictionary of model results that way we could call this function multiple times with different models and different data loaders and then compare the dictionaries full of results depending on which model we passed in here。

So let's set up loss and accuracy equals 00。 we'll start those off。We'll go。

 this is going to be much the same as our testing loop above， except it's going to be functionalised。

 and we're going to return a dictionary。So we'll turn on our context manager for inferencing。

With torched on inference mode， now we're going to loop through the data loader and we'll get the x and Y values。

 So the x will be our data。 The Y will be our ideal labels。

We'll make predictions with the model in other words， do the forward pass。

So we'll go Y pre equals model on X。 Now， we don't have to specify what model it is because we've got the model parameter up here。

 So this is， we're starting to make our functions here or this function generalizable。

 so it could be used with almost any model in any data loader。So we want to accumulate。

The loss and accuracy values per batch， because this is within the batch loop here per batch。

And then we're going to go loss plus equals loss function We'll pass it in the ypre and the y the true label。

 and we'll do the same with the accuracy， so except this time we'll use our accuracy function we'll send in y true equals y and y pre equals ypre do arg max because the raw outputs of our model are logits and if we want to convert them into labels。

 we could take the softmax for the prediction probabilities。

 but we could also take the arg maxax and just by skipping the softmax step。

 the argmax will get the index where the highest value Loitt is。Dim equals1。

And then we're going to make sure that we're still within the context manager here。

 So with torch inference mode， but outside the loop。So that'll be this line here。 We're going to。

Scale the loss and a to find the average loss。Slash act per batch。So loss。Will divide and assign。

To the length of the data loader。 So that'll divide and reassign it to however many batches are in our data loader that we pass into our of our model function。

 Then we'll do the same thing for the accuracy here， length data loader。Beautiful。

 and now we're going to return a dictionary here。 So return。

We can return the model name by inspecting the model。 We'll get an attribute of the model。

 which is its class name。I'll show you how you can do that。😊。

So this is helpful to track if you've created multiple different models and given them different class names。

 you can access the name attribute。So。This only works when model was created with a class。

 So you just have to ensure that your models have different class names if you want to do it like that。

 because we're going to do it like that， we can set the model name to be its class name。

We'll get the model loss， which is just this value here after it's been scaled。

 we'll turn it into a single value by taking dot item and then we'll go model。

 arc or we'll get model underscore a for the model's accuracy We'll do the same thing here。😊，Ac。

 I don't think we need to take the the item because accuracy comes back in a different form。

We'll find out。 they down， code it down。So calculate Model0 results on test dataset and I want to let you know that you can create your own functions here to do almost whatever you want。

 Ive just decided that this is going to be helpful for the models and the data that we're building。

 but keep that in mind that your models， your data sets may be different or will likely be different in the future so you can create these functions for whatever use case you need。

😊，Model0。Results。Equals a vow model。 So we're just going to call our function that we've just created here。

 Model is going to equal model 0。The data loader is going to equal what。The test data loader。

 of course， because we want to evaluate it on the test data set and we're going to send in our loss function。

 which is loss function that we assigned above just before our training loop。So if we come up here。

A loss function is up here。And then if we go back to them。We have our accuracy function。

Is equal to our accuracy function。 We just pass another function in there。 beautiful。

 And let's see if this works。 Model 0 results。 Did you see any typos likely。😊，Or errors in our code。

 How do you think I'm all did。Well， let's find out。Oh， there we go。 We got model accuracy。

 You see how we could reuse this dictionary later on。 So if we had Model 1 results， Model 2 results。

 we could use these dictionaries and compare them altogether。 So we've got our model name。

 our version 0 of the model has an accuracy of 83。42 and a loss of 。47 on the test data loader Again。

 your numbers may be slightly different， they should be in the same realm But if they're not the exact same。

 don't worry too much。 if they're 20 accuracy points less and the loss is 10 times higher。

 then you should probably go back through your code and check if something is wrong。

 And I believe if we wanted to do a progress bar here， could we do that T Q D M。😊，Let's have a look。

 okay。Oh， look at that。Progress bar。 that's very nice。

 So that's nice and quick because it's only on 313 batches。 It goes quite quick。 So now， what's next。

 Well， we've built Model 1， we've got a model 0。 sorry， getting ahead myself。

 We've got a baseline here。 We've got a way to evaluate our model。 What's our workflow。 say。

 So we've got our data ready。 We've done that。 We've picked or built a model。

 We've picked a loss function。 We've built an optimizer。 We've created a training loop。

 We've fit the model to the data。 we've made a prediction。

 We've evaluated the model using loss and accuracy。 We could evaluate it by making some predictions。

 but we'll save that for later on。 As in visualizing some predictions。😊。

I think we're up to improving through experimentation。😊，So let's give that a go， Hey。

 do you recall that we trained Model 0 on the CPU。How about we build Model1 and start to train it on the GPU？

So in the next section， let's create number 5 is setup up device agnostic code。

 So we've done this one together for using a GPU if there is one。

So my challenge to you for the next video is to set up some device agnostic code。

 so you might have to go into coLab if you haven't got a GPU active。

 change runtime type to GPU and then because it might restart the runtime you might have to rerun all of the cells above so that we get our helper functions file back and the data and whatnot。

 So set up some device agnostic code and I'll see in the next video。



![](img/8cc3a09560b2d38162ae54c3bfed248a_8.png)