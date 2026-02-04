# mrdbourke《一天学会pytorch深度学习｜Learn PyTorch for deep learning in a day Literally》中英 - P81：136. Creating image DataLoaders.zh_en - GPT中英字幕课程资源 - BV1kx4y1r79d

![](img/255bbae857c3c7b4f016bf873cf0c331_0.png)

Welcome back。 How'd you go In the last video， I issued you the challenge to turn our data sets into data loaders。

 So let's do that together Now。 I hope you gave it a shop。 That's the best way to practice。

 So turn loaded images into data loaders。😊，So we're still adhering to our Pytorch workflow here。

 We've got a custom data set。 We found a way to turn it into tenseors in the form of data sets。

 and now we're going to turn it into a data loader so we can turn our data sets into iterables or batchify our data So let's write down here a data loader。

😊。

![](img/255bbae857c3c7b4f016bf873cf0c331_2.png)

Is going to help us。

![](img/255bbae857c3c7b4f016bf873cf0c331_4.png)

Turn our data sets into iterables。And we can customize the batch size， write this down。



![](img/255bbae857c3c7b4f016bf873cf0c331_6.png)

So our model can see。Batch size。

![](img/255bbae857c3c7b4f016bf873cf0c331_8.png)

Images at a time。So this is very important， as we touched on in the last section computer vision。

 we create a batch size because if we had 100，000 images。



![](img/255bbae857c3c7b4f016bf873cf0c331_10.png)

Chances are if they were all in one data set。

![](img/255bbae857c3c7b4f016bf873cf0c331_12.png)

There's 100，000 images in the Food 101 data set we're only working with about 200。



![](img/255bbae857c3c7b4f016bf873cf0c331_14.png)

If we try to load all 100，000 in one hit， chances are our hardware may run out of memory。

 and so that's why we matchify our images。 So if we have a look at this Nvidia SMI。😊。



![](img/255bbae857c3c7b4f016bf873cf0c331_16.png)

Our GPU only has 16 gig。 I'm using a Tesla T4 right now。 Well has about 15 gig of memory。

 So if we tried to load 100000 images into that whilst also computing on them with a pintto model。

 potentially we're going to run out memory and run into issues。

 So instead we can turn them into a data loader so that our model looks at 32 images at a time and can leverage all of the memory that it has rather than running out of memory。

So let's。Turn our train and test datas into data loaders。

Turn train and test data sets into data loaders。 Now， this is not just for image data。

 this is for all kinds of data in Pythtorch。Images， text， audio， you name it。So import data loader。

 then we're going to create a train data loader。We're going to set it equal to data loader。

 we're going to pass in a data set。So let's set this to train data。Let's set the batchge size。

 what should we set the batch size to， I'm going to come up here and set a li。Capital variable。

 I'm going to use 32 because 32 is a good batch size。 So we'll go 32。 or actually let's start small。

 let's just start with a batch size of one and see what happens。 batch size1 number of workers。

 So this parameter is going to be this is an important one。

 I'm going to I potentially have covered it before， but I'm going to introduce it again。

 is this going to be how many cause or how many CPU core that is used to load your data。

 So the higher the better usually， and you can set this via O CPU count which will count how many CPUus your compute hardware has So I'll just show you how this works import O。

 and this is a Python O module we can do CPU count to find out how many CPUs our Google coab instance has mine has two your number may vary。

 but I believe most coabab instances have two CPUs。 If you're running this on your local machine。

 you may have。

![](img/255bbae857c3c7b4f016bf873cf0c331_18.png)

![](img/255bbae857c3c7b4f016bf873cf0c331_19.png)

![](img/255bbae857c3c7b4f016bf873cf0c331_20.png)

If you're running it on dedicated deep learning hardware， you may even have even more。 right。

 So generally， if you set this to one。It will use one CPU core， but if you set it to OS。cpu count。

 it will use as many as possible。So we're just going to leave this as one right now。

 you can customize this to however you want， and I'm going to shuffle the training data。

Because I don't want my model to recognize any order in the training data， so I'm going to mix it up。

And then I'm going to create the test data loader。Data set equals test data。

And batch size equals one nu workers， I'm going to set this to equal one as well。 Again。

 you can customize each of these their hyperpara to whatever you want。Number of workers。

 generally the more， the better。And then I'm going to set shuffle es false for the test data so that if we want to evaluate our models later on。

 our test data set is always in the same order。So now let's have a look at train data loader。

 see what happens and test data loader。

![](img/255bbae857c3c7b4f016bf873cf0c331_22.png)

Wonderful， so we get two instances of torch us dot data dot data loader。 And now we can。😊。

See if we can visualize something from the train data loader， as well as the test data loader。

 I actually maybe we just visualize something from one of them。

 So we're not just double handling everything。 Do we get a length here。



![](img/255bbae857c3c7b4f016bf873cf0c331_24.png)

Wonderful， because we're using a batch size of one。

 our lengths of our data loaders are the same as our data sets。😊，Now， of course。

 this would change if we set， oh， we didn't even set this to the batch size parameter。



![](img/255bbae857c3c7b4f016bf873cf0c331_26.png)

Bge size。Let's come down here and do the same here。Blash size。

So we'll watch this change if we wanted to look at 32 images at a time， we definitely could do that。

 so now we have eight batches because 22 225 divided by 32 equals roughly 8。



![](img/255bbae857c3c7b4f016bf873cf0c331_28.png)

![](img/255bbae857c3c7b4f016bf873cf0c331_29.png)

And then 75 divided by 32 also equals roughly 3。 And remember。

 these numbers are going to be rounded if there are some overlaps。 So let's get rid of。



![](img/255bbae857c3c7b4f016bf873cf0c331_31.png)

![](img/255bbae857c3c7b4f016bf873cf0c331_32.png)

We'll change this back to one。Then we'll keep that there， we'll get rid of these too。



![](img/255bbae857c3c7b4f016bf873cf0c331_34.png)

And let's see what it looks like to plot an image from our data loader。Or at least have a look at it。

Check out the shapes， that's probably the most important point at this time we've already plotted enough things。



![](img/255bbae857c3c7b4f016bf873cf0c331_36.png)

So let's iterate through our train data loader and we'll grab the next one。

 we'll grab the image and the label and we're going to。



![](img/255bbae857c3c7b4f016bf873cf0c331_38.png)

Print out here。 So batch size will now be one。 You can change。The batch size， if you like。

 this is just again， another way of getting familiar with the shapes of our data。😊，So image shape。

Let's go image。t shape and we're going to right down here， this shape is going to be batch size。

 this is what our data loader is going to add to our images is's going to add a batch dimension。



![](img/255bbae857c3c7b4f016bf873cf0c331_40.png)

Colorour channels， height， width。And then print。Let's check out that label shape。

Same thing with the labels， it's going to add a batch dimension。



![](img/255bbae857c3c7b4f016bf873cf0c331_42.png)

Label and let's see what happens。

![](img/255bbae857c3c7b4f016bf873cf0c331_44.png)

Oh， we've forgot the end of the bracket。Beautiful， so we've got image shape。

 Our label shape is only one because we have a batch size of one。 And so now we've got batch size。

1 color channels 3 height width。 And if we change this to 32， what do you think is going to happen。😊。

We get a batch size of 32， still three color channels， still 64， still 64， and now we have 32 labels。

 so that means within each batch we have 32 images and we have 32 labels。



![](img/255bbae857c3c7b4f016bf873cf0c331_46.png)

![](img/255bbae857c3c7b4f016bf873cf0c331_47.png)

We could use this with a model。 I'm going to change this back to one。😊。



![](img/255bbae857c3c7b4f016bf873cf0c331_49.png)

And I think we've covered enough in terms of loading our data sets。 How cool is this。

 We've come a long way。 We've downloaded a custom data set。

 We've loaded it into a data set using image folder。

 turned it into tensesors using our data transform and now batchified our custom data set in data loaders。

😊。

![](img/255bbae857c3c7b4f016bf873cf0c331_51.png)

![](img/255bbae857c3c7b4f016bf873cf0c331_52.png)

We've used these with models before， so if you wanted to you could go right ahead and build a convolutional neural network to try and find patterns in our image tensesors。



![](img/255bbae857c3c7b4f016bf873cf0c331_54.png)

But in the next video， let's pretend we didn't have this data loader。



![](img/255bbae857c3c7b4f016bf873cf0c331_56.png)

This image folder。Class available to us。How could we load our image data set？So that it's compatible。

Like our image data set here， how could we replicate this image folder class？



![](img/255bbae857c3c7b4f016bf873cf0c331_58.png)

So that we could use it with a data loader。Because data load is part of torchutils。 data。

 you're going to see these everywhere， let's pretend we didn't have the Torchvision data sets image folder to help a function。



![](img/255bbae857c3c7b4f016bf873cf0c331_60.png)

![](img/255bbae857c3c7b4f016bf873cf0c331_61.png)

And we'll see in the next video how we can replicate that functionality。😊，I'll see you there。

