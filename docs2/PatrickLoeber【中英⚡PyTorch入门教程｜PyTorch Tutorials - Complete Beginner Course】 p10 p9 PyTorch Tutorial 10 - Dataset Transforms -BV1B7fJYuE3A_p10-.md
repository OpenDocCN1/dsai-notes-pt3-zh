# PatrickLoeber【中英⚡PyTorch入门教程｜PyTorch Tutorials - Complete Beginner Course】 p10 p9 PyTorch Tutorial 10 - Dataset Transforms -BV1B7fJYuE3A_p10-

Hi everybody。 welcomee back to your new Pytorarch tutorial。

 This time we want to talk about transforms for our data In the last tutorial。

 we use the built and data and data loader classes。

 and if we use a built in data like we see here then we see that we can pass the transform argument to this data set。

And then apply some transforms。So in this example， we used to build an endless data set and then we apply the twotenzo transform。

 which will convert images or nuy arrays to Tzos， and Pytorch already has a lot of transforms implemented for us。

 so please have a look at the official documentation which you can find at this link。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_1.png)

And there you can see all the available transforms。And for example。

 there are some forms that can be applied to images。 For example， Santa crop or grayscale or petting。

 And then there are transforms that can be applied to tenzos like the linear transformation or normalize。

 Then there are conversion transforms。 For example， the two pillow image and the totenzo transform。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_3.png)

Then there are also generic transforms where we can use Lambdas or we can write our very own custom class。

And then we can also compose multiple transforms so we can use transforms dot compose and then pass in a list which will apply multiple transforms after each other。

And。Yeah， so in the last tutorial， we implemented a custom wine data set。 Now。

 let's extend this class to support our transforms and write our own transform classes。

 So let's start。

![](img/6d807e3e238aab5bca2f58cef0a9eb81_5.png)

And here， I。Copiied the code from the last tutorial where we have our own custom wine data set。

 which will load the data。 And then we implemented the get item and the length method。

 which will allow indexing and the length function。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_7.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_8.png)

So let's extend this data set。 So now this should also support the transform argument。

 So we put this in our in it and say， transform， oh， sorry。Transform equals。 So this is optional。

 So by default， this is none。 And then in the in it， we store this。

 So we say self dot transform equals transform。And now we also have to make some changes to our get item function。

 So here we want to apply a transform。 if it's available。 So let's say here， sample equals this。

 and then we say if self dot transform。 So if this is not none。 Then we apply this。

 So we say sample equals self dot transform our sample。 and then we simply return our sample。

 So let's return。

![](img/6d807e3e238aab5bca2f58cef0a9eb81_10.png)

Sample。And this is all the change that we need for our data set。 And now let's continue。

 and let's create some custom transform classes， for example， we can write our own to Tenor class。

 So in the last tutorial we already converted it to a Tensor right here in this step but we don't need to do this so we can leave this as a nuy array and then let's implement a to Tenor class。

 which will then be passed to our data set and which will then later。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_12.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_13.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_14.png)

Convert this to a10zo。So the class totenzor。 And the only thing that we need is that we need to implement is the double underscore call method。

 which will get self and a sample。So now this is a callable object。And what we do here is first。

 we unpack our samples。 So we say inputs。And labels or targets。Equal sample。 And then we say， return。

Torch dot from Numpai， and here inputs。And then also torch dot from nuy targets。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_16.png)

So here also， we return。 We still want to return a tuple， like we did here。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_18.png)

And this is all that we need for our totenar transform。 And now we can pass this in here。

 So now we can say our wine data set gets the transform。Transform。Equals。To Tenz are。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_20.png)

Which is a function。And。Now， let's have a look at this。 So let's。Get the first item。

 So let's say first data equals data set of index 0。 And then let's unpick our data， so。First data。

 So let's say features and labels equals first data。 And now let's print the type。

Of the features and also the type of the labels。 So now if we run this。

 then we should see this is now of class torch Tenzzo。 And if we don't pass this in here。

 So if you say this is none， no transform， then we see that it's still a nuy and D array。

 So this is how we write our own Tenor， our own transform and then apply it for our own data set。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_22.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_23.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_24.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_25.png)

And now let's write， for example， another custom transform。 So let's call this mu transform。

 So a multiplication。 And here we imp implement the init method。 So this has self。 and this has a。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_27.png)

Factor argument。 So here we stored this self dot factor equals factor。 And then again。

 we must implement the double underscore call function or call method。

 which gets self and the sample。

![](img/6d807e3e238aab5bca2f58cef0a9eb81_29.png)

And here again， let's unpack our samples。 So let's say inputs and。Inputs and target equal sample。

 And then let's only apply the factor to our features。 So let's say， inputs。

Time is multiplied by our dot factor。And now let's return our inputs。

 our modified inputs and our target still as a tuple。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_31.png)

And so this is the multiplication transform。 And now。Let's apply this。 So let's apply a。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_33.png)

And let's say a compos transform in this case， to see how we can use this。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_35.png)

So。Let's say composed equals。 And here we need tor vision， dot transforms， dot compose。

 And here we put in a list of our transforms， so。

![](img/6d807e3e238aab5bca2f58cef0a9eb81_37.png)

Here， first， we want to have totenor， and then we want to have mal transform。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_39.png)

And。Let's say， so this needs a factor。 So let's say multiplied by 2。

 And now let's create a new data set equals wine data set。

 which gets the transform equals our comp transform。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_41.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_42.png)

Composed， and now again， let's get this。 So get or let's just copy this from here。

And run this to see if this is working。So now here we have a Tenzoa。

 and let's also have a look at the。 So let's print。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_44.png)

The features。

![](img/6d807e3e238aab5bca2f58cef0a9eb81_46.png)

And here， also， print the features。

![](img/6d807e3e238aab5bca2f58cef0a9eb81_48.png)

To see if the multiplication got applied。 So here now we should see that each value got doubled。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_50.png)

And now let's use another factor。 So let's multiply it by4 and run this。

 And now we should see that each of the value should now be multiplied by 4。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_52.png)

![](img/6d807e3e238aab5bca2f58cef0a9eb81_53.png)

And yeah， so this is how we can use the transform for our data sets。 and it's very useful。Yeah。

 most of the time you see the conversion transform to Tensor。

 but also a lot of times when we work with images， you might see some of them。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_55.png)

So， yeah， please check that out on the documentation website。 And I hope you like this tutorial。

 Please subscribe to the channel and see you next time， bye。



![](img/6d807e3e238aab5bca2f58cef0a9eb81_57.png)

哎。