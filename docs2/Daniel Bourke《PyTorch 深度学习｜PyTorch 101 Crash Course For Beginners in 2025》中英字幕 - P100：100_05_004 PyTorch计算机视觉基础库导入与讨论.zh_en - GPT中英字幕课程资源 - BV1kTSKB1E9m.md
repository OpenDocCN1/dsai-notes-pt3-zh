# Daniel Bourke《PyTorch 深度学习｜PyTorch 101 Crash Course For Beginners in 2025》中英字幕 - P100：100_05_004 PyTorch计算机视觉基础库导入与讨论.zh_en - GPT中英字幕课程资源 - BV1kTSKB1E9m

Welcome back。 Now， we've discussed a bunch of fundamentals about computer vision problems and convolution on neural networks。

 But rather than talk to more slides， let's start to code them out。

 I'm going to meet you at coab do research dot Google dot com。

 I going to clean up some of these tabs。😊。

![](img/c841474ffa354901fc7610f2d2bfd499_1.png)

And I'm going to start a new notebook。And then I'm going to name this one。

 This is going to be 03 pie torch computer vision， and I'm going to call mine video。

 So just so it has the video tag。Because if we go in here。

 if we go video notebooks of the Pytage deep learning repo， the video notebooks are stored in here。

 They've got the underscored video tag。 So the video notebooks have all of the code I write exactly in the video。

 But there are some reference notebooks to go along with it。 let me just write heading here。

 Pytorage computer vision。😊，And I'll put a resource here， see referenceence notebookbook。Now。

 of course， this is the one that's the ground truth。 It's got all of the。

Code that we're going to be writing。You're going to put that in here。

 explain with text and images and whatnot。 And then finally， as we've got C reference。

Online book and that is at learnpytorch。io at section number three。Plytoch Comp Vi。

I'm going to put that in there。 Now I'm going to turn this into mark down with command M M。

 beautiful。 So let's get started。 I'm going to get rid of this。 Get rid of this。😊。

How do we start this off？ Well， I believe there are some computer vision libraries。

That you should be aware of， computer vision libraries in Pytorrch。

So this is just going to be a text based cell， but the first one is Torch vision。

 which is the base domain library for Pytorrch。Computer vision。So if we look up To vision。

 what do we find？We have Torch vision 0。12。 That's the version that Torch vision is currently up to at the time of recording this。

 So in here。This is very important to get familiar with if you're working on computer vision problems and。

 of course， in the documentation， this is just another tidbit。

 we have torch audio for audio problems。 We have torch text for text。 Torch vision。

 which is what we're working on Torch rack for recommendation systems。

 Torch data for dealing with different data pipelines， Torch serve。

 which is for serving ptorrch models and pytorrch on Xla。

 So I believe that stands for accelerated linear algebra devices。

 You don't have to worry about these ones for now， we're focused on torch vision。 However。

 if you would like to learn more about a particular domain。 This is where you would go to learn more。

 So there's a bunch of different stuff that's going on here。 transforming an augmenting images。

 So fundamentally， computer vision is dealing with things in the form of images。

 even a video gets converted to an image， we have models and pretrained weights。

 So as a reference before。 you can use an existing model that works on in existing computer vision problem for your own problem。

 We're going to cover that in section， I think it's6。😊，For transfer learning。

 And then we have data sets， which is a bunch of computer vision data sets。

 U tells operators a whole bunch of stuff here。 So Pytorch is really。

 really good for computer vision。 I mean， look at all the stuff that's going on here。

 But that's enough talking about it。 Let's just put it in here。😊，Torch vision， this is the main one。

I'm not going to link to all of these， all of the links for these， by the way。

 is in the book version of the course， Py Toch Comp Vision。😊，And we have what we're going to cover。

 finally。Computer vision libraries and Pytorrch， Torch vision， data sets， models， transforms。

 etc cetera。 But let's just write down the other ones。So we have torch vision。Not data sets。

 something to be aware of。So get data sets and data loading functions。For computer vision here。

Then we have Torch vision。So these all come from Torch vision。

Models is get pre trained computer vision。 So when I say pre trained computer vision models。

We're going to cover this more in transfer learning， as I said。

 free trained computer vision models are models that have been already trained on some existing vision data and have trained weights。

 trained patterns that you can leverage for your own problems。😊。

That you can leverage for your own problems。Then we have Torchvision dot transforms。

And then we have functions for manipulating。Your vision。Data， which is， of course， images。

To be suitable for use with an M model。 So remember。

 what do we have to do when we have image data or almost any kind of data for machine learning。

 we have to prepare it in a way so it can't just be pure images。

 So that's what transforms help us out with Transforms helps to turn our image data into numbers so we can use it with the machine learning model。

 And then， of course， we have some， these are the torch u。 This is not vision specific。

 Its entirety of Pytorch specific。 and that's data set。

 So if we wanted to create our own data set with our own custom data we have the base data set class for Pytorrch。

And then we have finally， torch us data。 These are just good to be aware of because you'll almost always use some form of data set slash data loader with whatever piey toch problem you're working on。

 So this creates a。😊，Python， iterable。😡，Over a data set。Wonderful。

 I think these are most of the libraries that we're going to be using in this section。

 Let's import some of them， hay， so we can see what's going on。😊，Let's go import pie torch。

Import pie torch。So import torch。We're also going to get N N， which is stands for neural network。

 What's in N N。 Well in N N， of course， we have lots of layers， lots of loss functions。

 a whole bunch of different stuff。For building neural networks。

 we're going to also import torch vision。And then we're going to go from Torch vision。

Import data sets because we're going to be using datas later on to get a data set to work with。

From Torch Vision。Will import transforms。You could also go from Torch Vi。Dot transforms。Import。

2 tensor。 This is one of the main ones you'll see for computer vision problems。2 tensor。

 You can imagine what it does。But let's have a look。 transforms to Tensor。

Transforming and augmenting images。So look where we are， we're in pytorch。

org svision slash stable slash transforms over here。

 So we're in the torch vision section and we're just looking at transforming and augmenting images。😊。

So transforming what do we have， Transforms a common image transformations of our in the transforms module。

 They can be trained together using compose beautiful。 So if we have two tensor， what does this do？😊。

Convert a pill image or nuy andy array to a tensor。 beautifuliful。

 That's what we want to do later on， isn't it？ Well。

 this is going to be given you a spoiler is we want to convert our images into tensesors so that we can use those with our models。

 But there's a whole bunch of different transforms here。

 and actually one of your extra curriculum is to be to read through each of these packages for 10 minutes。

 So that's about an hour of reading。 but it will definitely help you later on。

 if you get familiar with using the Ptorch documentation。 After all。

 this course is just a momentum builder。 We're going to write heaves a Ptorch code。

 But fundamentally， you'll be teaching yourself a lot of stuff by reading the documentation。

 Let's keep going with this。 Where were we up to。😊，When we're getting familiar with our data。

 MaplotLib is going to be fundamental for visualization。Remember， the data Explorer's motto。

 visualize， visualize， visualize， become one with the data。 So we're going to import mapplotlib。

 pipl as PLT。And then finally， let's check the versions。So， print torch dot version。

Or underscore underscore version and print Torch vision。 So by the time you watch this。

 there might be a newer version of each of these modules out。If there's any errors in the code。

 please let me know。 But this is just a bare minimum version that you'll need to complete this section。

 I believe at the moment， Google Coabab is running 1。11。For torch。 and maybe。Or maybe 1。10。

We'll find out in a second。 It just connected。So we're importing pie torch。Okay， there we go。

So my Ptorrch version is 1。10， and it's got Kuder available， and Torch Vi is 0。11。

 So just make sure if you're running in Google Coabab， if you're running this at a later date。

 you'll probably have at minimum these versions， you might even have a later version。

 So these are the minimum versions required for this upcoming section。

 So we've covered the base computer vision libraries and Pytorch。 We've got them ready to go。

 How about in the next video， we cover getting a data set。😊。



![](img/c841474ffa354901fc7610f2d2bfd499_3.png)

I'll see you there。