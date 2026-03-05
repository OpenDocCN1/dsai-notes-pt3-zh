# 【精译⚡机器学习教程】PatrickLoeber p02 p1 Linear Regression in Python - Machine Learning From Scratch 02 - Python Tutor -BV1F3fJY5E7e_p2-

Hi， everybody。 Welcome to a new tutorial。 This is the second video of the machine learning from Sc tutorial series。

 In this series， we are going to implement popular machine learning algorithms using only built and Python modules and nuy。

 Today， we are going to implement the linear regression algorithm。

 So let's talk about the concept of linear regression first。 So in regression。

 we want to predict continuous values， whereas in classification。

 we want to predict a discrete value like a class label 0 or1。

 So if we have a look at this example plot。 Then we have our data， the blue dots。

 and we want to approximate this data with a linear function。

 That's why it's called linear regression。 So we use a linear function to predict the values。😊。

So we can define the approximation as y hat equals w times x plus B。

 So this is the line equation where w or our weights is the slope and B is the bias or just the shift along the y x's in the 2 D case。

So this is the approximation and now we have to come up with this W and the B and how do we find this？

So for this， we define a cost function。 And in linear regression， this is the mean squared error。

 So this is the。Difference。Between the actual value and the approximated value。

 So the actual value for this， we need training samples。

And then we square this difference and sum over all the samples and then divide by the number of samples。

 So this way， we get the mean error。This is the cost function of the so this is the error。

 and of course， we want to have the error as small as possible。

 So we have to find the minimum of this function。 and how do we find the minimum。 So for this。

 we need to calculate the derivative or the gradient。

 So we calculate the gradient of our cost function with respect to W and with respect to B。

So this is the formula of the gradient。 Please check this for yourself。

 and I will also put some links in the description with some further readings。

 but I will not go into detail now。And now with this gradient we use a technique that is called gradient descent。

 so this is an iterative method to get to the minimum。

 so if we have our object or our cost function here。

 then we start somewhere so we have some initialization of the weights and the bias。

And then we want to go into the direction of the steepest descent。

And the steepest de is also the gradient。 So we want to go into the direction of the into the negative direction of the gradient。

And we do this iteratively until we finally reach the minimum。And with each iteration。

 we have a update rule for the new weights and new bias。

 So the new W is the old W minus alpha times the derivative。

So minus because we want to go into the negative direction。

And then this alpha is the so-called learning rate， and this is an important parameter for our model。

 So the learning rate defines how far we go how far we go into this direction with each iteration step。

 So， for example， if we use a small learning rate， then it may take longer。

 but it can finally reach the minimum， and if we reach if we use a big learning rate then it might be faster。

 but it might also jump around like this and never find the minimum。

 So this is an important parameter that we have to specify and please keep that in mind。

So now that we know our update rules， I've written the formulas for the derivatives again here and。

Then simplify them a little bit。 Please check that for yourself。

 So these are the formulas for the update rules and the derivatives。 And this is all we need to know。

 So now we can get started。 So now let's define a class called linear regression。



![](img/489ee87a38bd1f44914c15f7c7b73e61_1.png)

And this will， of course， has an in it method。Or double will handle score in it。And then it has self。

 and it gets the learning rate。 and I will give this a default value。

 So usually this is a very small value。 So I will give it0001。

 And then I will give it a number of iterations。 So how many iterations we use in our gradient decent method。

 and I will also give this a default value。 So I will say this is 1000。

 and then I will simply store them here。 So I will say self Lr equals Lr and self。And。

Itders equals and its。 And then later， we have to come up with the weights。

 But here at the beginning， I will simply say self weights equals none and self dot bias equals none。

And then we have to define two functions and we will follow the conventions of other machine learning libraries here。

 so we will define a fit method， which takes the training samples and the labels for them。

 So this will involve the training step and the gradient descent。

And then we will define a predict method。So then， when it gets new。Test samples。

 then it can approximate the value and return the value。

 So these are the functions we have to implement。 And before we go on。

 let's have a quick look at the data X and Y。 So how does this look。And for this。

 I've written a little example script， and I use the psychic learn module to generate some example data。

 and I will split the data into training and test samples and also training and test labels。

 So first of all， let's have a look at how this data looks。So here is the plot。

 So this is how our data looks。 And now we want to find a function somewhere here that approximates the value。

And let's have a look at the。Shape of our X and y。 So let's run this。

 And I don't want this plot here anymore。嗯。So if we see that our x is a N D array of size 80 by1。

 and this is because I put in here， I want to have 100 samples。And one feature for each sample。

 And then I will split this。 So our training samples only has 80 samples in it。 So this is a。

ND array of size 80 by  one。 and our training labels is just a 1 D vector of also of size 80。

 So for each training sample， we have one value。So this is how our data looks。

 And now let's continue。 So let's implement the fit method。 So as I said。

 we need to implement the gradient decentscent method here。

 and the gradient decent always needs to start somewhere。 So we need to have some initialization。



![](img/489ee87a38bd1f44914c15f7c7b73e61_3.png)

![](img/489ee87a38bd1f44914c15f7c7b73e61_4.png)

So。Let's do， let's in it our parameters。 And for this first。

 let's get the number of samples and the number of features。

 we can get this by saying this is x dot shape。And then we simply initialize all the weights with0。

 So we can say self weights equals nuy zeros。Of size and feature。And features。 So for each component。

 we put in a0 and self du bias equals 0。 This is just a value。So you can also use random values here。

 but0 is just fine。So let's use 0 here。 and then we use the gradient descent。

 So this is an iterative process。 So we use a fall loop。 So4 I， or actually， we don't need this。

 So for underscore in range and then self dot and its。And now， what we need。

We first have to approximate。

![](img/489ee87a38bd1f44914c15f7c7b73e61_6.png)

Or let's have a look at the formula， again。So， the formula for our。

And new weights is the old weight minus the learning rate times the derivative。

And the derivative with respect to W is1 over n。And then we have the sum and the sum over two times X I。

Times， and then。The difference here of this approximated and the actual values。 So let's first。First。

 calculate this approximation。 So we have this formula here。The approximation is。

The weights times our x plus the bias。

![](img/489ee87a38bd1f44914c15f7c7b73e61_8.png)

So let's do this， let's say， and let's call this why。Predicted equals。

 and then we can use NP dot dot。And then x and self dot weight。Plus。Bs。

 so this will multiply the x with the weights。And now that we have the approximation。

 we can calculate the derivative with respect to W。 And this is， let's again。

 have a look at this formula。

![](img/489ee87a38bd1f44914c15f7c7b73e61_10.png)

1 over n。And then。The sum。 and then inside the sum， we have the product of x times this。



![](img/489ee87a38bd1f44914c15f7c7b73e61_12.png)

So， we say。1 over。And samples。 So we already got the number of samples here。And then times。

 and then we have the sum product。 So this is nothing else， but also the dot product。 So N dot dot。

But now we have to be careful。 So what we did here。嗯。

Here we multiply each weight component with the feature vector component and sum it up。

 and we do this for all samples and then get one value for each sample。

 And here we want to get one value for each feature vector component。

 So we multiply each sample with a predicted value and sumit up。So。

 and then we do this for each feature vector component and get one value for each component。

 So this is the other way around。 So this is along the other axis。

 And we can so we have to use x dot transposed here， x dot T。

And this is the dot product of the transposed X。 And then we have y predicted minus the actual y。

 So please check the nuy dot function for yourself。So， this is the。

The of the W and the derivative of the bias is also one。 or again， let's have a look at the formula。

 So this is the same except that we don't have the x here。 So this is one over n。

 and then just the sum。🤢。

![](img/489ee87a38bd1f44914c15f7c7b73e61_14.png)

Of this difference。 And by the way， I。I left the two out。

 So this is just a scaling factor that we can omit。So here one over n。

 and then the sum over the difference。

![](img/489ee87a38bd1f44914c15f7c7b73e61_16.png)

So again， one over number of samples。 And then we can say nuy dot sum and the sum of y predicted minus actual y。

So this， these are our derivatives。 And now we update our weights。

 So we say self weights minus equals self dot learning rate times this。Divative。And self。

 the bias equals self。Minus equals self dot learning rate times。The derivative。And。Yes。

 so this is the gradient descent。And now we need the predict method。 So， again， we approximate。



![](img/489ee87a38bd1f44914c15f7c7b73e61_18.png)

We approximate the values with this formula， so。

![](img/489ee87a38bd1f44914c15f7c7b73e61_20.png)

We already have this here， So this is。The dot product of x and the weights， plus the buyers。And then。

 we simply returned this。So this is the whole implementation that we need， and。I forgot to import Ny。

 of course。 So I say， let's say， import Ny S and P so that we can use this。And now， let's test this。

So。嗯。Let's import this class。 So let's say， from。Linear regression。Import linear regression。

And then create some regresso equals。Linear regression。And then we say regressor dot fit。

 and we want to fit the training samples and the training labels。

And then we can say we can get predicted values equals。Regressor。Dot predict。

 And now we want to predict the。Test。嗯。Samples。And now。

 in order to calculate the or to see how our model performs。

 now we can't we can't use the accuracy measure。 but here we use the mean squared error。 So。

 as I said， this is our cost function， the mean square error that tells us how big。



![](img/489ee87a38bd1f44914c15f7c7b73e61_22.png)

The difference between the actual value and the approximated value is。

 so let's define the mean squared error。 Let's say theef M， E， and this will get。



![](img/489ee87a38bd1f44914c15f7c7b73e61_24.png)

The actual values and the predicted values。And this is。The numpy here， we can use numpy mean。

And then， simply the difference。To the power of two。 So why。True。Minus y predicted to the power of2。

And then we want to return this。So， let's see。Oh， let's say。MSE value equals MSE。Off。W。Test。

And the predicted。Values， and let's print this。So now， if we run this。嗯。See， it's not running。

 Bias is not defined。 So let's say what we。What did we miss here Do bias。And let's run this again。So。

L，27。Oh， sorry。 I copied this and forgot this year， too。 So next try。Now， we see that our。

Performance， so the mean squaredarrow is 783。 So this is pretty high。

 So let's use another learning rate here。 So let's say L R equals。t0，1。And let's run this。

And now we see that our arrow is smaller and let's actually plot this。So。Let's plot。First。

 with the original learning rate， let's see our。How the plot looks。So， now。Our plot looks like this。

 So it's。Almost like the right slope， but not exactly。 And now let's have the other learning rate。

 So let's use this learning rate。 and let's run this。And now our plot looks like this。

 and this looks pretty good， actually。 So this is a pretty good。

Fit a pretty good approximation of this data with a linear function。

 so we see that our implementation is working and I hope you enjoyed this tutorial and see you in the next tutorial。



![](img/489ee87a38bd1f44914c15f7c7b73e61_26.png)

![](img/489ee87a38bd1f44914c15f7c7b73e61_27.png)

Bye。