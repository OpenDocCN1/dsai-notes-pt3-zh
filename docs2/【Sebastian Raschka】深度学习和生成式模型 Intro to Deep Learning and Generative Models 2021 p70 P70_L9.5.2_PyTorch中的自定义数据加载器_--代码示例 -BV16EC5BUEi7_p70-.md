# 【Sebastian Raschka】深度学习和生成式模型 Intro to Deep Learning and Generative Models 2021 p70 P70_L9.5.2_PyTorch中的自定义数据加载器_--代码示例 -BV16EC5BUEi7_p70-

Yeah， let's not talk about Pytor custom data loader。

 So the data loader is a class and Pytorch that lets us， yeah。

 a lot of data more conveniently compared to doing it manually。 I will show you two notebooks。

 One is yeah just the data loader itself with a simple example。

 And then I will show you how we can use it in a yeah， model training context。

So yeah what I should say is I'm actually using MN here and you may wonder why MN because there is already MNT data set and data lot are implemented in Torch Viion which we could technically import which is what we have done in the yeah last couple of videos So the reason is MN is relatively small and yeah in this way I can upload it to GitHub so I can upload this without let's say taking too much space in that repository and it's also for you faster to download and it was just yeah convenient。

Because you are already familiar with it， but of course here Mnes this represents a more general data。

 so think of it as an arbitrary data consisting of PNG files。

So what I've done is I yeah divided Mnest。And do three parts， a training set。

 a validation set and a test set。So I put them here into yeah PN G files， just in each folder。

 there's a set of PN G files， as you can see here。And。I have also corresponding on CV file。

 So here in the CV file， I have the class labels。

![](img/c68c8e32db85801c06d8ca2cb577037a_1.png)

And the file name。Of course， you can also， if you like， you can have only one。

Folder with P And G files and then have a column with validation train and test index。

 so you can also specify it like this。 I mean， how you set it up is up to you。

 I sometimes find it convenient to do it like this。

 Sometimes I only have one gigantic P And G file folder and keep track of what is training。

 What is validation with is test。 I keep track of it with columns in the C file。

 But this is really optional。 I mean， how you want to set up is up to you。 You can set it up。

 however you like， and I will show you how we can then handle that with Pyhar dataset class。



![](img/c68c8e32db85801c06d8ca2cb577037a_3.png)

So back to this notebook I showed you now， I have these files so focus now only on these three folders and these CV files。

 the helper function， I will use them later in this train model notebook。



![](img/c68c8e32db85801c06d8ca2cb577037a_5.png)

So yeah， let's get started。 So usually when I have a new dataset。

 what I do first is I inspect this dataset。 So I sometimes use I use image I O。

 Sometimes I just use the Python image library。 I'm not very consistent。 It doesn't really matter。

 There are multiple libraries and Python that lets you open a P and G file or JPEC file in Python itself。

 and then you can take a look at it。 So here I'm using P。 It's the Python imaging library。

 If you have to install it， I think you have to do install。Hello。Why pillow and not wipe。Pill or PL。

 That is because the Python imaging library， I think it got abandoned at some point。

 and then some people forked it on Gitthub to further maintain it。 And this fork is called pillow。

 But even if you install it as pillow the import is identical you use this one to import it in particular we are only implementing the importing this image class。

So here I'm just looking at the image so here。I'm loading one data point or one image from this Mest train folder。

 why C map binary。 Yeah， because color maps by default is this verris color map。

 which is kind of useful for heat maps。 But yeah here maybe it looks a bit goofy if we have these colors for Ms。

 So here we use just this version。

![](img/c68c8e32db85801c06d8ca2cb577037a_7.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_8.png)

Alright， yeah， also， I find it helpful to just take a look at the image dimension。

 So here it's 28 by 28。 There is no colour channel。 and you can see the values。

 the pixel values are between 0 and。

![](img/c68c8e32db85801c06d8ca2cb577037a_10.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_11.png)

255。

![](img/c68c8e32db85801c06d8ca2cb577037a_13.png)

ItCould be 254。 I'm not actually not quite sure here actually I see the the highest one is 253。



![](img/c68c8e32db85801c06d8ca2cb577037a_15.png)

Alright， so then looks， okay。 so we now know what we are working with。Let's know。lot the CV files。

padas and then I'm load my CV files。 So these are only the first five rows with this head command。

Yeah， and I can also show you oh， you can see it right here。The dataset is。

 yeah only made it artificially small。 There are only 256 images in each dataset set。

 Mnes is of course， much bigger。 It's usually I think 50000 in the training set and 10000 a test set here。

 I just made it smaller because I'm going to upload this to Github so you can download it And in this way it's not like too much taking up too much space there。

Otherwise， I don't want to upload 50000 small files and stuff， you know， Allright， so here。

Here's our interesting part now that's the data set class in Pythtorch and so in order to do to use the data la we need a data set so there are two parts。

 one is the data and one is the data la so let's talk about the data first because that's what we need for making the data la。

 So here the data is really how we read the data。So this is something you yeah have to set up yourself or a new dataset。

 So here this is from Pytorch Torch U data。 This is yeah something a class from Pytorch。

 and here this is called class inheritance in Python。

 So we are inheriting certain features from dataset so that they are available in all our datasets。

 it's called class inheritance。 It's like a not a Pytorch， but a Python concept。So。

 and then we are defining our own data set。 I'm just calling it my dataset set。

 but you can call it whatever you like。And then like in every class， we have an init method。

 And again， in this constructor and this init method， I'm specifying certain things。

It's basically by the way， arbitrary what I put here， it's not required to put anything here。

 but on what we need here because we have CV files and we have folders， I put both the CV path。

 the path to the CV file， let's say the training CV and the image directory。

 for example here this directory。And there's also a transform for doing a custom image transformation。

 I will show you just a very basic transformation。 Actually， we are not doing any transformation。

I will talk about this in the next lecture。嗯。Yeah， so what's going on here is in the in。 in the unit。

 we are loading the CCV file and keep it attached to the data loaddown。no， we don't need it attached。

One second so。We lot the CV file。 We save the image directory to the self dot image de attribute so we can use it later。

 and then we save the image names as self dot image names。

 and this comes from the CV file from the file name column。 So if I scroll up again。

 this is this column， we just save this column here。

And then we also save the class label column S dot y。These are class labels。

 And then we just store whatever we provide us transform here。

 So this is a setup for the data set when it's created。And here。

 this is how a data point gets loaded。 a single data point。

 Remember that this one was in short you the animation loading a pair of。

Or a data point with its training label， basically， So one image and one label。

 So that's what we are what's loaded with this get item here。Here you have to have this index here。

 I mean there other ways， but I find it convenient with the index。And then we have to specify。

 so what we do is here we specify how we obtain one image and one corresponding label。

So how do we open the image， So image that opens this is similar to what I used。



![](img/c68c8e32db85801c06d8ca2cb577037a_17.png)

Up here。I mentioned it open。

![](img/c68c8e32db85801c06d8ca2cb577037a_19.png)

And then I'm giving it the path。 So the path is。Based on the image directory that I provide here。

 and then。The image name。So the image name is in this column， right， so。Here what I M G is。

 It will be， for example， something like Emnest。Train。Let's say， one dot P， and G。

So here index will select a random once。 it could be that 1 or3 or 5，1，2。123， whatever， so。

This is chosen randomly， so this is how this data set is basically shuffled by always picking the inds in random order。

And then there is an optional transformation that we can apply to the images， for example。

 normalization， rotation and things like that。 and I will show you how that works in the next lecture。

And then we also obtain the corresponding class label。So if index is， let's say one。Then we will。

 or let's say indexes yeah here1， then we would obtain image 513 to PNG and the corresponding label 0。

And then it returns both the image and the label。And that's essentially it。

 There's one more method here。 That's the then。 And this one is the length of the data set。

 So that is how this data set knows when one epoch is finished。

 So here we can simply compute the length by。Getting the shape of this y。

 which is the class label column， so。

![](img/c68c8e32db85801c06d8ca2cb577037a_21.png)

Essentially。Oh， I have not imported anything here。😔。



![](img/c68c8e32db85801c06d8ca2cb577037a_23.png)

I actually should have。De it's not defined，hu。Oh， I sorry， I call a theft train。ok。

So this is our data set。 So this is really specifying how we load a data set or images from the data。



![](img/c68c8e32db85801c06d8ca2cb577037a_25.png)

And now this is the data laer that is also loading data points。

 but this is really for making our mini batches。

![](img/c68c8e32db85801c06d8ca2cb577037a_27.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_28.png)

So。For doing that， we need。The data set。So。Here what I'm doing is I'm setting up the training dataset。

 So the training dataset has the CB file MnesT underscore train dot CB and the folder MnesT train。

This is this folder here and this C file。

![](img/c68c8e32db85801c06d8ca2cb577037a_30.png)

Let me， before I explain this in more detail， also show you the validation data set。

 so here's the same thing for the validation set， but notice that the folder names are different and the C file names are different and here is the same for the test set。



![](img/c68c8e32db85801c06d8ca2cb577037a_32.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_33.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_34.png)

Now。See， there is another thing going on Trans。 and this is our custom transformation。

 We don't do anything here except converting the image to a Pytorch tensor。

 So there is the Torch vision library， which has this transforms package or sub library。

 and there are different。Methods for augmenting and transforming images here。

 I'm using something called2 tensor， and this one will convert an image to a Pyrch tensor。

 but it will also normalize the images by dividing them by 255 automatically。I actually find this。

 I don't know， I would like if it wouldn't do this automatically because it's maybe something we don't want to do。

 but in any case yeah it does so what I mean is it would be cool to have the choice。

 whether we do it or not maybe there's a new function that has or gives you the choice。

 but it's actually not a bad idea to normalize images in that way it's maybe good so people avoid making mistakes because yeah training a network on unnmalized images is usually a bad idea。



![](img/c68c8e32db85801c06d8ca2cb577037a_36.png)

Okay。Yes， so this is how we then set up along。Training data。 Now we have created a dataset。

 a training dataset using our my dataset class that we defined here。

 So here this is just defining the class。 and here we are actually using it。

 And now we are setting up the data model。 So that's the main part。



![](img/c68c8e32db85801c06d8ca2cb577037a_38.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_39.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_40.png)

Which。Takes in this training dataset。 And here we also specify the batch size。

We specify whether we shuffle or not after each epoch。

 So this is shuffling or essentially before each epoch， and there is also a parameter nu workers。So。

It would be great to have a whiteboard here or something。 I don't have one。But think about it。

Yes this。 So if we Python is single threaded， usually。 So there's one mainy Python process。

 one process running。 So there's usually， let's say data processing。And then there's our model。

 And this， let's say。We give our data to the GPU。 and then， on the GPU。

 there happens to model training， and then。嗯。It then it goes back to。Data processing again。And then。

It's basically a repeating loop。 So we are going from data processing to the GPU where we do the model training and then data processing。

 GPU model training。 And this would also be true for CPU。

 The main point is that this is sequential because Python is usually one single process。

 one main process， however。Data processing。Can be slow。 I mean， it can take， let's say。

10 seconds or 5 seconds to load the images。说。It would be more efficient if we have the data processing decoupled。

From giving the data to the GPU and the model training， if those happen like in parallel， right。

 So we could have actually multiple。CPUus， via multiple CPUUus。 We can do the data processing。

 and then the data is already ready in the memory。 and the GPU just has to read it and do the model training。

 It has never， never has to wait until the next batch is processed。So in that sense。

 we can use multi processing of our CPU to prepare the next batch of images for the GPU。

 so the GPU doesn't have to wait。For that we can use the number of workers greater than0 if we have0 then only one main python process is used for both for everything for the whole pipeline。

 if we set it to one， then it would create one sub process to load the data which makes it more efficient and two is even better。

I noticed when I run it here， actually， I get problems recently with recent versions。

 I think this is because Ms is so fast to load that it will just load too many things at once。

 And then it has too many open files waiting for the GPU to be processed。

 So I get nowadays an error when I run it on Mnes。 But if I have any other data set other than Mnes。

 that is usually not a problem。 because M this is really just as simple。 I think that's the problem。

 So I set it to0。 But in your projects， you may want to set it to a higher number。 And for example。

 in my research projects， I usually use two3 without problems。



![](img/c68c8e32db85801c06d8ca2cb577037a_42.png)

嗯Yeah。Or I should also explain what drop last means。So if you have a number that is， let's say。

 not divisible by 32， then there will be a last batch that is smaller than 32， right。

 And if drop last is true， it will be dropped。You don't have to do this。 I mean。

 like you don't have to drop this。 but I noticed sometimes in my research code that if I have。

 let's say， batch sizes of 512。 and then the last batch is only 11 examples。

 this last batch can be extremely noisy and sometimes harm the model performance as a bad update at the end of the epoch。

 So personally in my projects I found usually dropping the last mini batch。

If it's smaller then the pitch size is sometimes good。Alright， let's take a look now。

 So here we are initializing all the data orders for。



![](img/c68c8e32db85801c06d8ca2cb577037a_44.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_45.png)

Training set for the validation set， and the test set。



![](img/c68c8e32db85801c06d8ca2cb577037a_47.png)

And here I'm just， yeah I'm iterating through it to just make sure that it works。

 So here I'm simulating how we would train a model。 So we have， let's say。

 just two epochs and then we iterate through the batches here。For our training order。

 this is actually what you have seen before。 We have used the built in endless data set。



![](img/c68c8e32db85801c06d8ca2cb577037a_49.png)

He am transferring it to the device。 So the device， if you have a GPU， it will be the first GPU。

 otherwise it will be the CPU。So yeah， it will just iterate sea。



![](img/c68c8e32db85801c06d8ca2cb577037a_51.png)

So just give the batch size。 so it will create。

![](img/c68c8e32db85801c06d8ca2cb577037a_53.png)

1，2，3，4，5，6，7，8 mini batches。

![](img/c68c8e32db85801c06d8ca2cb577037a_55.png)

And that is it， let me change this to one and see what happens。 So I don't always get this error。

 but with Amist。

![](img/c68c8e32db85801c06d8ca2cb577037a_57.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_58.png)

Yep， see， I get something。Called。

![](img/c68c8e32db85801c06d8ca2cb577037a_60.png)

Like this。

![](img/c68c8e32db85801c06d8ca2cb577037a_62.png)

I think this is because there are too many open files。Doesn't say so explicitly。

Because the weird thing is， I don't get this error when I run this on data sets that are not Mnes。

 There's something about Mnes。 I think it's。

![](img/c68c8e32db85801c06d8ca2cb577037a_64.png)

And this is just as simple。It's a little bit weird， to be honest。Also。

 I can't remember in the past getting this error about anyways。



![](img/c68c8e32db85801c06d8ca2cb577037a_66.png)

Could also be my computer because I compiled Pythr from scratch。

 but I also get this error on my other machine， so。



![](img/c68c8e32db85801c06d8ca2cb577037a_68.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_69.png)

Anyways。So。

![](img/c68c8e32db85801c06d8ca2cb577037a_71.png)

Let's go back to this one。 Yeah。 and here we can also just print the shape of one of the batches here。



![](img/c68c8e32db85801c06d8ca2cb577037a_73.png)

So the shape is 32。 Then the color channel is only one color channel。

 So because it's big and white and then 28 pixels high，28 pixels white。

Here's just printing it as a vector。 if we reshape it。32 times 784。

 So this is what our multilayer perceptron needs as an input。

 So convolal networks can work with this input directly。 Multilayer perceptrons cannot。

 They can only work with this。

![](img/c68c8e32db85801c06d8ca2cb577037a_75.png)

Just just for reference how it looks like the to tensor。 You can see it's normalized。

 You should be able。 maybe we can't。It's just， see if it's。Cause it's abbreviating it。



![](img/c68c8e32db85801c06d8ca2cb577037a_77.png)

can print it。Here you can see the highest value 。999 because it's 253 divided by 255。



![](img/c68c8e32db85801c06d8ca2cb577037a_79.png)

Alright， so this is how the data load works。 Let me now show you the model training code here。

Uing the custom data。

![](img/c68c8e32db85801c06d8ca2cb577037a_81.png)

So here I'm now using a hybrid of what I showed you two videos ago when I use helper functions。

 helper scripts and Jupyter notebook。So here I have set up several helper files that I may reuse in different projects。

 and this helps me keeping the notebook kind of small。 So if I make a new notebook。

 let's say I call it notebook。2， I can make some changes to this notebook， for example。

 some settings， but I don't have to copy and paste all the code。 It's in that way， easier to read。

 especially if you want to， let's say modify some function as a bug in the accuracy function。

 Then you don't have to go back to every file here and change the code。

 You only have to change it in one of the files and the p files。 So I can just maybe open them。



![](img/c68c8e32db85801c06d8ca2cb577037a_83.png)

Show you what I mean。So。😔，Example， help I evaluate。 I have this set all seats。

 determin compute accuracy。 So there's a bug， for example。

 I only have to change it here once I don't have to go back to all my notebooks。

 I find this very helpful if I have a project with multiple model training and model notebook scripts or notebooks and scripts。

 alright。

![](img/c68c8e32db85801c06d8ca2cb577037a_85.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_86.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_87.png)

Me closes again。 We can take a look at individual ones。



![](img/c68c8e32db85801c06d8ca2cb577037a_89.png)

Soう。

![](img/c68c8e32db85801c06d8ca2cb577037a_91.png)

Yeah， yeah importing certain functions from this。Of from these helpalpa filess。



![](img/c68c8e32db85801c06d8ca2cb577037a_93.png)

Then here are my settings。 You can also， like I explain before， have a separate settings style here。

 I have adjust in the notebook itself， random seat， batch size and number of epochs。



![](img/c68c8e32db85801c06d8ca2cb577037a_95.png)

And then I'm using these。To make that deterministic。 And he has just。



![](img/c68c8e32db85801c06d8ca2cb577037a_97.png)

So yeah， I have a get data load function that actually uses the data load from the previous notebook that I showed you。

 I just put it into。

![](img/c68c8e32db85801c06d8ca2cb577037a_99.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_100.png)

This script here。 Now I have my data set here， and I have written a get data la， which will。



![](img/c68c8e32db85801c06d8ca2cb577037a_102.png)

Set it up for me， automatically。

![](img/c68c8e32db85801c06d8ca2cb577037a_104.png)

So that it's basically just a slightly modified version of what I've showed you in the previous notebook where I just have arbitrary paths and stuff。

 and it will return the training order， validation order and test order。



![](img/c68c8e32db85801c06d8ca2cb577037a_106.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_107.png)

And here I'm just testing that they actually work。 So just getting some statistics。 and you can see。

 So if I run this again， you can see that the shuffling works because you can see that these numbers change。

 So these are the first 10 labels。So you can see this。 So every time it will start from scratch。

 because I break here。So you can see these numbers change。However， if I set my random seat。

I always get the same order， see。Can run this again。

Always get the same order because of the random seed， the the random seed。Yeah， makes the。嗯。

Makes it consistent。 Its so， for example， if you run this code。

 you will get the same model and same accuracy I got because you use the same random seat。

 This is useful。 for example， if you do research and you develop some code and want to share it with someone else and other person wants to reproduce your code。



![](img/c68c8e32db85801c06d8ca2cb577037a_109.png)

嗯。

![](img/c68c8e32db85801c06d8ca2cb577037a_111.png)

So yeah， here is the multi layer perceptron。 I yeah simplified this a little bit。

 So I'm using sequential now。 I mean， simplified compared to two videos ago here I'm actually using flatten。

 This is actually new。 I like this a lot。 So this way， we don't have to reshape。



![](img/c68c8e32db85801c06d8ca2cb577037a_113.png)

Our feature vector。 So it will essentially reshape the 28 by 28 to 784 forest us。

So we don't have to do it manually somewhere down here。Yeah， and this is it。

 So here I'm using sequential。 So I don't have to do anything in the forward。

 It will automatically return the logics。 So here this is a multi layer perception with only one hidden layer。

 So this is the first hidden layer。 Then we have a sigmite activation。

 And then we have the output layer。And then we would technically have a softm。

 but we don't need to have the softm because the functional cross entropy loss in Pytch computes the softm for us。

Alright， so this is how it works。 So don't need to set another seat here because I've done it above。



![](img/c68c8e32db85801c06d8ca2cb577037a_115.png)

So here the seat would be for。For the initial random weights， we will also talk about this in a in。

2 lectures。 So not the next lecture， but the lecture。 And after that。

 we will talk about these different ways we can initialise weights。



![](img/c68c8e32db85801c06d8ca2cb577037a_117.png)

We use stochastic gradient descent。

![](img/c68c8e32db85801c06d8ca2cb577037a_119.png)

And here I also， yeah just brought a function for training the model is essentially what you have seen before。

 I just put it into a separate file here。 So if I go to help train Pi。

 I have all the code I have had previously in here。



![](img/c68c8e32db85801c06d8ca2cb577037a_121.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_122.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_123.png)

Because it's essentially always the same code， so you can use that in other projects as well。



![](img/c68c8e32db85801c06d8ca2cb577037a_125.png)

You can just， yeah， copy and paste that。 It just keeps the notebook more readable in that way。

 It's not such a long notebook anymore。

![](img/c68c8e32db85801c06d8ca2cb577037a_127.png)

Oops， what do we got here。 Yep， that's what I always forget， defining things。



![](img/c68c8e32db85801c06d8ca2cb577037a_129.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_130.png)

Alright， so it trains， it will train very fast， actually。

 because we only have 256 data points in each data set。Yep， it is training fast。



![](img/c68c8e32db85801c06d8ca2cb577037a_132.png)

Yeah， we get actually pretty high accuracy。 I mean， given that we only have 256 images。

 it's also barely overfitting。 It's actually not yeah， you can see it's 91% and 73。 It's actually。

 it is overfitting。But yeah， the validation， accuracy and test accuracy are almost identical。

 The difference here， why is the difference is's usually just a small random effect， right。

 because of the small data set 156。

![](img/c68c8e32db85801c06d8ca2cb577037a_134.png)

嗯。Yeah， and then I also have functions for plotting the training loss and the accuracy。

s also helpful。

![](img/c68c8e32db85801c06d8ca2cb577037a_136.png)

So yeah， I have the version with a running average。And。😔，Can see the loss goes down。

We get train for1 our epochs。 And here the accuracy goes up。 But then at some point。

 there's more and more overfitting。So I put these plotting functions in help plotting if you ever need them。

 I think I will also personally reuse them in future lectures because then I don't have to make these long notebooks because this code is really always the same。



![](img/c68c8e32db85801c06d8ca2cb577037a_138.png)

So I have it some time defined here， and then I can reuse that。



![](img/c68c8e32db85801c06d8ca2cb577037a_140.png)

You don't have to honestly memorize any of that or。

It's good maybe to understand it if you want to change it。

 but you don't even technically have to understand any of these details。



![](img/c68c8e32db85801c06d8ca2cb577037a_142.png)

So it's also something I wrote one time。 and if I ever need it again， Ill just copy and paste it。



![](img/c68c8e32db85801c06d8ca2cb577037a_144.png)

Because there are too many other things to worry about。

 it's rewriting this is it took me some time I had to there were some bugs and things didn't work。



![](img/c68c8e32db85801c06d8ca2cb577037a_146.png)

That way， you write it once so that it works and then you can just reuse it。



![](img/c68c8e32db85801c06d8ca2cb577037a_148.png)

Alright， so last as a show examples function I wrote。

 so it shows some of images so you can see P means predicted and T means true label or target label。



![](img/c68c8e32db85801c06d8ca2cb577037a_150.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_151.png)

So these are all correct。So here this is。Predicted is2， but the target is6。 I see。

 I think I made an arrow here that can't be right。Maybe it is right， but let me double check。

I haven't planned this。 It's very spontaneous。 so good that we look at it。 I think is， yeah， I sorry。

 it's my mistake。

![](img/c68c8e32db85801c06d8ca2cb577037a_153.png)

Now， I just wrote this code， actually， for this lecture。So。Made a mistake。



![](img/c68c8e32db85801c06d8ca2cb577037a_155.png)

Let's。Do this again。

![](img/c68c8e32db85801c06d8ca2cb577037a_157.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_158.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_159.png)

Hoops should have been targets。Yeah， one I disadvantages because I have the import at the top of this notebook。



![](img/c68c8e32db85801c06d8ca2cb577037a_161.png)

I have to run the whole notebook。😔。

![](img/c68c8e32db85801c06d8ca2cb577037a_163.png)

![](img/c68c8e32db85801c06d8ca2cb577037a_164.png)

But it's faster run。

![](img/c68c8e32db85801c06d8ca2cb577037a_166.png)

Alright， so that looks better now， predicted 6 target2 predicted 5 well。Talt 0。

Some other mistake here。 you can see the model makes some mistakes。

 but I think these are just mistakes because the model hasnt haven't hasn't seen enough numbers because these are should be easy to distinguish。

 I think they are clearly number twos。Okay， so yeah， this is the custom niallora。 So that's it。

 Then for this lecture next week， we will talk about。Regularization， like preventing。Overfitting。

 All right。 Have a good weekend。

![](img/c68c8e32db85801c06d8ca2cb577037a_168.png)