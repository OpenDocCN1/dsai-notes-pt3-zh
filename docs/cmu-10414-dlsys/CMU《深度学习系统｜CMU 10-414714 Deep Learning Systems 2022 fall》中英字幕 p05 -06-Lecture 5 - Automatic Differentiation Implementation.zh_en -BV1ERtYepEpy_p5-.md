# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p05 -06-Lecture 5 - Automatic Differentiation Implementation.zh_en -BV1ERtYepEpy_p5-

Okay， hellello， everyone， welcome back to deep Inence A implementationm In the last lecture。

 we have talked about how can we derive automatic differentiation from scratch。

 including numerical differentiation method， as well as a reverse mode automatic differentiation。😊。

As part of this lecture， we're going to talk about some of the framework scaffolding that we're going to use to implement not a math differentiation framework。

You will be implementing automated differentiation as part of your homework once。

 so this lecture wouldn't go through the exact implementation。

 but we will go through the underlying code base that we'll be using throughout this entire course of a course and also talk about some of the underlying mechanisms on how different systems are being structured or supporting automatic differentiation。

This lecture is about implementation lecture。 So as part of this course。

 we will find different style of lectures。 There will be you know normal presentations like you see in the past few lectures。

 There will also be implementation lectures。 where we are going to directly go through iPads and notebooks。

 hopefully do a bit of interactive coding to just get us to really familiar with what exactly does it take to implement a deepening framework from scratch。

 Okay， so let's get started。

![](img/499306a950c4659b4ff8778f4f2d8058_1.png)

![](img/499306a950c4659b4ff8778f4f2d8058_2.png)

As the first part， what we're going to do is we're going to run this code block。

 So if you are running for the first time， remember that you want to un this code block and run it。

 I've already run it on my end。 So what it does， it will try to create a folder of 10，7，1。

14 F 22 on your Google Gi。😊，Then you will try to clone a raple that I needed in this lecture onto the Google Drive onto the lecture for folder。

 Then we're gonna to create a symbolic link of that particular folder under content on needles。

 So after doing this， you， you will， you know， open up listings on coab。

 you will find that on left hand side， there is already a needle folder that contains a necessary content。

 Actually， this lecture4 folder can be ignored here。 It was like an artifact of separate cloning。

 So effectively， this is something that you can go ahead and play with。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_4.png)

![](img/499306a950c4659b4ff8778f4f2d8058_5.png)

![](img/499306a950c4659b4ff8778f4f2d8058_6.png)

![](img/499306a950c4659b4ff8778f4f2d8058_7.png)

And because this folder is on your Google Drive。 So you will be able to actually， you know。

 for example open up a file。😊，Moify the file a bit。 and then save it。

 And and the next time when you run coab， you just need to run this code block to get back。

 So it will contain all the necessary changes that you have already made in the in the Google Drive。

 So that is one way for you to do development if you want to do it as you know coab come with the interviewed I as well as an environment and allows you to run Python and so on。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_9.png)

![](img/499306a950c4659b4ff8778f4f2d8058_10.png)

Okay， so that's the first setup。 So this folder effectively contains the necessary files for our first homework。

 And actually， as the homework one being released， you can also safely replace this rapple by the homework one rap。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_12.png)

The next step we are going to do is we're going to set up a Python pass。

 So this is a necessary step to be able to bring some of these available packages。 In this case。

 just content a needle， a Python folder that contains a needle package so that we'll be able to go ahead and directly run an import needle。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_14.png)

![](img/499306a950c4659b4ff8778f4f2d8058_15.png)

Okay。

![](img/499306a950c4659b4ff8778f4f2d8058_17.png)

So now let's take a look at the photos on the left hand side of， you know， what does needle contains。

 what， what is the needle library consist of， right。

 So needle stands for necessary elements of deep learning。



![](img/499306a950c4659b4ff8778f4f2d8058_19.png)

![](img/499306a950c4659b4ff8778f4f2d8058_20.png)

Which means that， you know， you try to encapsulate the main necessary element that we need to。

 to bring in a differently model， to bring in a differently models， right and。



![](img/499306a950c4659b4ff8778f4f2d8058_22.png)

![](img/499306a950c4659b4ff8778f4f2d8058_23.png)

It's also potan。 I that， you know， you can also view it as a swine needle that you can use to sue the sewing needle that you can use to sewe the neural network together。

 So we have a dedicated logo of needle that kind of represent that man。

 So and it's really excited to work with everybody as part of this semester to be able to build up this needle library so that we can build our own discipline library from scratch。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_25.png)

So if we now click the file folder on the left hand side and take a closer look。

 we will find that this needle package， as of now， contains three main files。

 So as the in it file that is defines all the imports that we need in the library the autograph file that contains the definition of the necessary data structures。



![](img/499306a950c4659b4ff8778f4f2d8058_27.png)

![](img/499306a950c4659b4ff8778f4f2d8058_28.png)

An automatic differentiation mechanism。 is the op stop P file that contains the operator definitions needed for our homework assignments。

We can quickly open the file and browse through it note that you know we will。

 we will certainly go with more details in this lecture。

 So don't worry if you don't if you don't know quickly see everything if you have something on your local laptop。

 you are also more than welcome to open up and try after this lecture。 So this。

 if you look at this auto autograd or P this particular file contains about 400 lines code that that include the necessary implementations needed for auto differentiation framework。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_30.png)

![](img/499306a950c4659b4ff8778f4f2d8058_31.png)

Similarly， if you look at the uptop UI， this file contains about 300 lines implementation。

 So you can find that overall， we roughly have about。

 I will see1000 lines code to that that builds up this overall scaffolding infrastructure we needed for for running machine learning models and when as part of this lecture we're gonna do so we're going to walk through this code base as more like interactive code review so that we can get familiar with this overall scaffolding okay。



![](img/499306a950c4659b4ff8778f4f2d8058_33.png)

![](img/499306a950c4659b4ff8778f4f2d8058_34.png)

![](img/499306a950c4659b4ff8778f4f2d8058_35.png)

![](img/499306a950c4659b4ff8778f4f2d8058_36.png)

![](img/499306a950c4659b4ff8778f4f2d8058_37.png)

And before we walk through the code base， one thing that I'm going to do is how about。

 let's go and try to run and try our needle a bit。 So what we can do is we can import needle as needle in here。

 And then youll find that needle is already kind of contains a few of interesting features that you can do that if you have used deeply in Py before it contains several things that allows you to have similar APIs Py。

 for one thing I can do is I can see x dot needle do ten。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_39.png)

1，2，3。E type equals。Load 32。 And if I go and run this code。And if I try x。You'll find that， you know。

 it gives you a needle dot tensor here。 So that's like a basic tensor creation。



![](img/499306a950c4659b4ff8778f4f2d8058_41.png)

Asked that。Another thing you can do is you can go and perform operations on it。

 When I can see y equals x plus one。 And if I try out y。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_43.png)

You'll find that in here， Y equals not 2，3，4。 Okay， so。

 so you can perform this kind of basic ame operations。 And the the hood actually， why。

 when you call y equals x plus one。 in reality， what it tries to do is actually the cause into another function called y equals。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_45.png)

needle dot X scala。 So this is a specific operator that allows you to add a tensor with a scala value in here。

 And effectively， the operator is being overloaded so that if it detects that you are adding a tensor with a scala value。

 we are just going to call that a scala function。

![](img/499306a950c4659b4ff8778f4f2d8058_47.png)

Okay， so that's like a very basic of what needle can do， right。

 We'll be able to create a needle cancer。 We'll be able to operate on it。



![](img/499306a950c4659b4ff8778f4f2d8058_49.png)

Of course， this Netensor contains several field that looks quite like what an nu array and Pych array Py gentle gives you example example you can try to do a y do shape that gives you the shape of the tensor and y do D type that contains gives you the D type data type of the tensor here。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_51.png)

![](img/499306a950c4659b4ff8778f4f2d8058_52.png)

![](img/499306a950c4659b4ff8778f4f2d8058_53.png)

开。And one of the last operation that we can perform on this is this operation called。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_55.png)

Y dot number排。So， this operation。Help us convert the needle tensor back onto lump。Of course。

 actually， as a part of the first two lectures for first two homeworks。

 we' are actually simply using Nier to back up this needle library。

 So effectively we are not doing a lot of things。 There's a data field within the tensor that directly contains a nu array and we are simply returning that data field back。



![](img/499306a950c4659b4ff8778f4f2d8058_57.png)

![](img/499306a950c4659b4ff8778f4f2d8058_58.png)

![](img/499306a950c4659b4ff8778f4f2d8058_59.png)

![](img/499306a950c4659b4ff8778f4f2d8058_60.png)

But on the other hand， you know， for a general deploy framework。

 and as we start developed this needle library， we' are going to start to implement our own version of un dimensional array library that runs on GP and CPU。

 in those cases， when the data sits on GP can no longer simply have a array counterpart。

 So as a result， there always is a function that converts the data from the on device memory or from underlying arrays back onto array。

 Similarlyly， the needle constructor。 you will be able to pass in an array or list here and effectively the constructing a array the copies of data onto the needle tensor。



![](img/499306a950c4659b4ff8778f4f2d8058_62.png)

![](img/499306a950c4659b4ff8778f4f2d8058_63.png)

So while it's not being so meaningful as the first two lectures because we are using CP array that are back by here。

 this CP is going to be useful in the future。 So that's why when when in our homework and in other cases or right test cases。

 we always call dot to try to get the data back array so that in the future the code will still be functioning for other。

So this is kind of like a basic。Explation of what you can do， right， You can create a tensor。

 You can do some of the tens linear algebras and Ten arithmetics on this needle tensor。



![](img/499306a950c4659b4ff8778f4f2d8058_65.png)

![](img/499306a950c4659b4ff8778f4f2d8058_66.png)

Now， let's take a look at closer look at the code base and。

 and look at what other data structures that backs this needle needle cancer。 Okay。

 so I'm going to open up。

![](img/499306a950c4659b4ff8778f4f2d8058_68.png)

This code part。

![](img/499306a950c4659b4ff8778f4f2d8058_70.png)

There are， there are two main things that backs up this needle tensor。



![](img/499306a950c4659b4ff8778f4f2d8058_72.png)

The first data structure is。

![](img/499306a950c4659b4ff8778f4f2d8058_74.png)

Value。And actually， needle tensor is a subclass of value。 So。

 so let's go up and then let us go and take a look at the tensor。



![](img/499306a950c4659b4ff8778f4f2d8058_76.png)

Deeration。And you'll fine N。行。

![](img/499306a950c4659b4ff8778f4f2d8058_78.png)

Here you will find that， you know， tensor is a subclass of value。 So you can find that there's no。

 besides there's a gradient field。 Actually， there's not an additional field on a tensor class。

 So most of the fields of the tensor are do are from the you know， base class value in here。

 And this is the Python type annotation you have not seen before。

 it annotates what are expected fields within a class。



![](img/499306a950c4659b4ff8778f4f2d8058_80.png)

![](img/499306a950c4659b4ff8778f4f2d8058_81.png)

So let's take a look at what are the necessary fields that we can， we have in this time。 right。

 So the first thing that you want to notice is this cache data field。

 And it is up type N D array array。 And in this case， actually。

 N D array is simply defined as number。啊。And啲。Aray in this case。

 So you can just view n D as numberha array for the purpose of this lecture。But in the future。

 we will change this definition of N to be our own underlying implementations of backend N。受。

This cache data， caches。The data that represents that ten example。

 when we compute y equals x plus one and y equals 2，3，4。

 and then the cache field will cr on to the 2，3，4 nupy race in this case。

However if you look at very carefully at this value class。

 you can find that besides the besides the cache data view， which is used to host the data。

 which is definitely very important。 right， there are others fields that that is not necessary。

 You will not not necessarily expect when you try to create say a class for matrix or vector ortenor。

😊，The first thing you want to notice is that there has the inputs field。

And the input is a list of values。 So in this case。

 the input correspond to the correspond to the input in the computational graph operation。

 So in this case， the value is not only trying to capturing a single in the area or single areas。

 but also try to capture how does that value get computed。And it， you know。

 the way it capture that is it try to use it in two fields。 The first field is the op field。

Contains what is operation that needed to compute this value and input field contains the list of input that are feed into that particular operation。

 and the combination of the two will allow us to know exactly how this value is being computed in this case。



![](img/499306a950c4659b4ff8778f4f2d8058_83.png)

And， you know。If， if you are a bit still bit confused now， you know。

 let's take a look at this computational graph， which is used in our last lecture。

 right so this computational graph represents a sequence of computation needed to compute compute and exponential times。

 exponential plus1 operations。😊。

![](img/499306a950c4659b4ff8778f4f2d8058_85.png)

And in this case。

![](img/499306a950c4659b4ff8778f4f2d8058_87.png)

Each of the V here。Will correspond to an object， a value object。And when I look at operation here。

The operation correspond into exponential addition and mine。And if you look at inputs field。

 So let's take， say， you know， let's take like B， B4。



![](img/499306a950c4659b4ff8778f4f2d8058_89.png)

And you will find that if before correspond to a value object。An input of V4。Would equal a list。



![](img/499306a950c4659b4ff8778f4f2d8058_91.png)

Of V 2 and V 3。Similarly， V2 is also a value。And input of V2。

Would equal V1 here and the operation V to B2 equals explanation， okay。

So you can find that this value class help us to represent a node in a computational graph。

 as well as it contains， you know， its input input node that needed to compute that computational。😊。

Of course， for example for V1 here， in this case， V Y is simply an input to the computational graph。

 so it does not contain any operations。 In this case， for a case of input or leaf operation。

 the op was going to equal to none and input is going be equal empty。 So in that case。

 they will indicate that it's the input and the array data is going to be cached in the cache data field here。

Okay， so finally， does require gradient field in here。

 and it indicates that whether or not the gradient computations， you know。

 we want to be able to compute gradient with respect to this value。

This sometimes is' useful when you build a neural network and certain power computations don't need to prop the gradient back on true。

 And in that case， required gradient is going to be set to a false。

 When you create a pencil by default。 Actually， it required gradient is always going to be set to true。

Okay， so that's a value of you。And the second class that's important is the。Op class。



![](img/499306a950c4659b4ff8778f4f2d8058_93.png)

In this case， an op class contains operator definition and in in this particular case， actually。

 you know， there are， there are many different definition of ops。 as subclass。

 So when we are looking at a value do， it's not necessary looking at a single object。

 but it can be different subclasses。 each of a subclass is gonna to contain a specific implementation of an。

 I home if we open up op stop Q Y in here。 And I can simply take a look at one specific instance of op for example there's。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_95.png)

Lwise at operation。And in this case， it's a subclass of tensor op。

 which means that this operation returns a tensor， and tensor op is also a subclass of op。

And animal what I add effectively is a is a object there。 For， if I look at。This field。

 And if you look at V 3 dot off field， you will find that V 3 dot off field is an instance of animal。

 Oh， sorry， It's not instance animal site because it's an a Scar。

 So we had another option here called a Scar。

![](img/499306a950c4659b4ff8778f4f2d8058_97.png)

![](img/499306a950c4659b4ff8778f4f2d8058_98.png)

And in this case， these three dot op， actually， this equal。

 This is an instance of an S scholar object。

![](img/499306a950c4659b4ff8778f4f2d8058_100.png)

Okay， so different op are used to represent what kind of computation they want to carry out in this particular computation graph。

The op itself contains two two functions that are to be implemented by each of all。

 There's a compute function that compute that that defines you know for underlying array array computations。

 How do I exactly go and compute that and array computation for this particular and then there's a gradient function that try to go and compute the edge the input partial edge values for given output。

 partial edge value。 if I are still bit confused about this two functions fine we are going to come back and riveted in the following part of lecture。

 So for now， just think about op as indicator。 right。

 So different types of op correspond to different kind operation want to perform。



![](img/499306a950c4659b4ff8778f4f2d8058_102.png)

![](img/499306a950c4659b4ff8778f4f2d8058_103.png)

![](img/499306a950c4659b4ff8778f4f2d8058_104.png)

Okay， so now we have introduced this basic data structure as an option。

 You might still be a bit confused， right， So what exactly are they。 So。

 so one of the things that we let let's So moving next。

 what let's try to do is let's try to go and play and， you know。

 try to construct this computational graph through needle and try to play a bit on say what's really going on in this data structure。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_106.png)

![](img/499306a950c4659b4ff8778f4f2d8058_107.png)

![](img/499306a950c4659b4ff8778f4f2d8058_108.png)

So first of all， let's try to go and create this set of computations。

 so you can find that this set of computation exactly correspond to the computational graph that we had before。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_110.png)

Well v1 equals needle 10 so 0 that creates a V1 and v2 equals exponential V1。 If you scroll up。

 Yeah its V2 equals exponential V1。 And then， you know， V3 equals V 2 the S gala 1。

 V4 equals V 2 times V3。 So in this case， after this。

 you can find that it contains exactly the original computations。 right。 if you look at V 4 here。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_112.png)

![](img/499306a950c4659b4ff8778f4f2d8058_113.png)

![](img/499306a950c4659b4ff8778f4f2d8058_114.png)

Not surprising that you can find before equals2。 Well， in this case， exponential of 0 equals  one。

Sorry， at at one equals 1， at one plus 1 equals 2 and two times 1 equals 2。 Okay。

 so the result is Apple equals equals 2。On the hand， as we noted。

 this tensor field or as a result of value field contains more attributes than the data itself。

 So let's take a look at this。😊，The first thing that we can take a look at is V V 4。Thought inputs。

And you find that a， V for the inputs are two needle tensors。 Actually。

 they are two tensors are two needle values。And in this case。We know that， no。

 as we explained before， right， V for the input is a list of V2 v3。

 right and and we print out it this value。 but we can also try a search if is the case for V for input 0 is V 3。

 in this case， we' will try to check identity。 Whether or not that is exactly V 3。 If we check Oh。

 it's not V 3。 Actually， it should be V 2， right， because it's V 2 v3。 Okay。

 V for the input0 is v2 and V for the input 1 is V is 3。😊，This one， yeah， both sides true right。

 you can find that in this case， V force inputs is need V V 2 V3。

 We can even use it to trace the competition graph。 I can say V V for the inputs。

 it also have certain inputs， right， because V for the inputs is。😊。

Before the input is V 2 and V to the input is V1。 so。

 so we can find that we can go and use this to trace the computation computations。 And， you know。

 we can confirm that if it's a V1。😊，OhYeah， this one is you one。



![](img/499306a950c4659b4ff8778f4f2d8058_116.png)

Another thing we can go。 And so do these are the inputs fields。 So we can find that actually。

 the inputs fields correspondpon to the overall set of。

 let me try to go to the value definition so we can also contrast and compare right， So in this case。

 you can find that。😊，There's the input field here， and this input field indeed creates to the input。

To that particular computation。The second thing that we want to take a look at is the up field here。

嗯对。If you look at we do all。You can find that it's an instance of needle the ops of elementized eized multi。

 So indeed， it is， is a instance of elementized multiplication operator here。

 And if you look at V4 dot input 0。😊，Which is supposed to be V 2， right？ What's。

 what's its operations。Don't have this one。It's an exponential operation。If you look at。

Imputs of this one is should supposed to be be 0。And that's a leaf operation。 And look at this one。

 you can find that this operation。 well， it's not showing anything， but。



![](img/499306a950c4659b4ff8778f4f2d8058_118.png)

Check this。

![](img/499306a950c4659b4ff8778f4f2d8058_120.png)

你 can find it now。Okay。So， so that explains， you know what are the inputs feel to each of a value here。

Then what's the alt field？The second thing you want to notice is there is cache data field。

And in this case， if youre directly playing V4， you will find that V4 equals theten of 2。

 And if you do V4 dot cache data。Well， it equals the non area two。

 if we can even go ahead and track the type。Operation。Go to type of V4 dot。 So it's a nu and theory。

 Okay， so in this case， the V 4 dot cache data stores the compute result。

That are that that correspond to this V4 tensor。 right， So as we print it out。

 you will find that it simply prints out the result of the cache。没个。Okay。

 so that constructs our computational graph。One last thing that you want to。

 we might only take take a look at is， you know， when you take a operation field。

 different operations can contain attributes。 if we look at these3。These three operation。

 in this case， Let's take a look at here。 right These three is。



![](img/499306a950c4659b4ff8778f4f2d8058_122.png)

Addition of a scale operation。

![](img/499306a950c4659b4ff8778f4f2d8058_124.png)

And in here， if you look at these three， you can find these three up equals S scatter。And actually。

 this S scalar contains contains its own fielding here。 And that's a scalar value here。 right。

 So if you look at V3 dot。Nput。And you'll find that it only contains one input。 Actually。

 this if you can also confirm that this input is fee2， right。So， so you know。

 V3 contains one input as V2， and you have a scalar attribute。

That attached to the all that indicates， you know， what kind of scalear scalar values to that we need to add to this particular V3 operation。

And so， as a result， each of all class indicates what an operation want to perform。

 and it also contains， can contain attributes that that indicates。

 you know what kind of parameterization we want to perform that particular operation。Okay。

 so this is the combination graph。 And， you know， to， to show what is because。

 you know when I directly say print。Before儿。You will find that， no， it only prints out a content。

 So that do not exactly show the computational graph that we're having here。

 So let's try to define a function that help us to， you know。

 see a more detailed content of a computational graph。Going here。

 let's define a straight node function。And， and I will print。different things。 First of all。

 I'm going to print I D。You know， I is， is a unique integer in Python， actually， that indicates。

 you know， what is the unique idea of that Python。 So。

 so the I D will help us to kind of ping down exactly。

 what is what is the class what What is the idea of the particular object。

Then we can also print inputs。Of this function。

![](img/499306a950c4659b4ff8778f4f2d8058_126.png)

As。

![](img/499306a950c4659b4ff8778f4f2d8058_128.png)

Id of acts。我ax先。然后到。

![](img/499306a950c4659b4ff8778f4f2d8058_130.png)

So in this case， we are just going to print all the input I。

 and this I is going to effectively help us recognize whether or not one one node equals another one。

We can also print out operation type。Because the type kind of indicates。There。Operation， right。Okay。

 so these three things hopefully will help us to and we can also print holiday data。

So now we define print node。 I can go ahead and try to print。狼后。Before。And you're find that you know。

 its ideas， itss value。And contains this another two inputs， right， itemwise operation data equals 2。

And if I printed。

![](img/499306a950c4659b4ff8778f4f2d8058_132.png)

B2， or B3 here。 You can find that oops down。You can find that， you know。

 the idea of V3 exactly equals this value。 right so we know this is V3。Thats case。 Okay。

 so it's a helpful toolkit that we can use to inspect this underlying computational graph no。

So to summarize upon youon now， we have learned about we have learned the tensor data structure specifically its parent class value。

 and we know that actually needle all tensor not only directly correspond to a plane array that distorts the data。

 it also correspond to cell data structure that records the history computations。

And the different values will form a directly acycl graph that allows us to trace this computation history。

 and this directly acycl graph is can be used for us to compute reverse mode automatic differentiation。

 which we talk about in the last lecture。

![](img/499306a950c4659b4ff8778f4f2d8058_134.png)

Okay， so。

![](img/499306a950c4659b4ff8778f4f2d8058_136.png)

We have already gone through all this。 So moving next， let's start to talk about， you know。

 what does it， what happens when we execute a needle computation。You know， right now。

 we have talk about， you know， hey， where we construct this needle cancer effectively。

 we are trying to construct effectively， we are trying to construct a computational， but。

 but when does that execution happen。

![](img/499306a950c4659b4ff8778f4f2d8058_138.png)

Specifically， you know， if I try to construct two arrays and try to perform viable additional operations。

When does that additional operation happen in our frame？

 So that's the question that we're going to answer in this part of the on the lecture。



![](img/499306a950c4659b4ff8778f4f2d8058_140.png)

![](img/499306a950c4659b4ff8778f4f2d8058_141.png)

And to do that， I'm going to， again， do some of a bit of intact coding here。 So first of all。

 let's say I'm creating two needle tenses in here。 I'm going to do x 1 plus x 2。



![](img/499306a950c4659b4ff8778f4f2d8058_143.png)

And our question is， no what happens when we do x1 plus x 2， right。

 so there are a lot of things that happens in here。 but I'm going to。



![](img/499306a950c4659b4ff8778f4f2d8058_145.png)

So， so what I'm going to do is I'm going to walk you through。



![](img/499306a950c4659b4ff8778f4f2d8058_147.png)

A set of function course。That crisp one to the， the operations that we we run when we。

 when we call X 1 plus X2。 And then， you know， let's take a look at what exactly happens through tracing the code。

 okay。

![](img/499306a950c4659b4ff8778f4f2d8058_149.png)

So first thing， when we call x 1 plus x2。 and here is that we're going to call into an operator overloading function。



![](img/499306a950c4659b4ff8778f4f2d8058_151.png)

So， let me try to move。This is coat here。 so we can see more of the coat side。



![](img/499306a950c4659b4ff8778f4f2d8058_153.png)

And if so the first thing that happens。As that will。



![](img/499306a950c4659b4ff8778f4f2d8058_155.png)

That's。

![](img/499306a950c4659b4ff8778f4f2d8058_157.png)

So in the test of view， there's a。Add overloading。 look at here。

 The first thing is it's going to call it into this function。

And it will track if the other instance is tense。 In this case， we are adding two tenses together。

 So will call needle dot ops， otherwisewise and self and other。😊。

And let's take a look at the definition of the anmos epi。



![](img/499306a950c4659b4ff8778f4f2d8058_159.png)

Look at animalized add function。And fine。 This is the Mwise addd function。 Actually。

 the definition of， of that core。 So in this case， actually。



![](img/499306a950c4659b4ff8778f4f2d8058_161.png)

嗯ops。

![](img/499306a950c4659b4ff8778f4f2d8058_163.png)

嗯。So， in this case。诶。

![](img/499306a950c4659b4ff8778f4f2d8058_165.png)

It's actually calling to tensor of dot core。

![](img/499306a950c4659b4ff8778f4f2d8058_167.png)

![](img/499306a950c4659b4ff8778f4f2d8058_168.png)

Here， okay， so this is what。This is what what what happens when we call into the NY ad construction call。

 so。

![](img/499306a950c4659b4ff8778f4f2d8058_170.png)

![](img/499306a950c4659b4ff8778f4f2d8058_171.png)

In the original case， the cancer calls an MY add。 and that that's going to call into the subclass。

 So Lwise add dot underscore underscore core， and that's going to call this function。



![](img/499306a950c4659b4ff8778f4f2d8058_173.png)

So we're kind of chasing a bit of indirects， but its it's kind of important to go through this and understand what exactly happens in this different framework that we view。

 okay。

![](img/499306a950c4659b4ff8778f4f2d8058_175.png)

And in this particular function， it's going to call a tensor dot make from。



![](img/499306a950c4659b4ff8778f4f2d8058_177.png)

And tensor dot make from op is kind of is a function that creates a computational graph node and attaches all the fielding。

 Okay， so let's go and take a look at tensor dot make from op。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_179.png)

![](img/499306a950c4659b4ff8778f4f2d8058_180.png)

In this particular case， Tea do't make from。

![](img/499306a950c4659b4ff8778f4f2d8058_182.png)

Actually。啊，那边行。

![](img/499306a950c4659b4ff8778f4f2d8058_184.png)

![](img/499306a950c4659b4ff8778f4f2d8058_185.png)

Make from off。 I think it's。Yes， so here is ten domain make from all。It's a static method。So。

 so significant， we are constructing a new tensor。 So a reason we are using tensor do new。

 So this is a separate way in Python that allows to construct an object other than， you know。

 direct constructing function through underscore it。

 The only reason why we are using new here is because we are overloading in it already。

 We are using it for the user facing construction that takes in that takes in the list of nuier array and do certain operations。

 So in here， it's kind of internal constructor that we use to construct tensor object。

And what it does is that it first create a tensor object in here。



![](img/499306a950c4659b4ff8778f4f2d8058_187.png)

And it causes in function to populate the field of the tensor object。

 specifically fields include the op field that correspond to auto operation on perform。

 as well as the input field that contains the list of inputs values to that。

And then it's going to call。 no， you're going to track e lazy mode。

 Were going to explain what lazy mode is later。And then it's going to call a realized cache data。

 which will try to populate the cache data view。 And we're also going to expand this later。

 So let's face first take a look at what's happens in the in it function。



![](img/499306a950c4659b4ff8778f4f2d8058_189.png)

Okay。So in the it function core。

![](img/499306a950c4659b4ff8778f4f2d8058_191.png)

It's actually knit function is defined in a base class。



![](img/499306a950c4659b4ff8778f4f2d8058_193.png)

There is， right。 So this is an function。 You want to differentiate from the function new constructor because it's underscoring it。

 It's the internal function that we use to initialize a value field。



![](img/499306a950c4659b4ff8778f4f2d8058_195.png)

![](img/499306a950c4659b4ff8778f4f2d8058_196.png)

effectivelyffively try to， effectively attach all the all the field onto attach op field input field。

 and also try to compute the number output of the tensor， which most of the tensor。

 most of the operations only contains one number of output。And and it also attached a cache。There's。

 it also try to maintain a global tensor counter that counts you know。

 number of active tensors so far in memory so that the， you know。

 it's a simple mechanism for us to check how many， how many tensors we've created in this right so far。

And it also try to help you to computer require gradient fields。

 So the rule to compute this is that if。Any of the inputs。Of， of this operation requires gradient。

 Then we will need to probably gradient to this so that we can probe it further。 Otherwise。

 we don't need gradient values of this。

![](img/499306a950c4659b4ff8778f4f2d8058_198.png)

So you can find that the in field simply populate that data structure。



![](img/499306a950c4659b4ff8778f4f2d8058_200.png)

But one thing that you might notice is that it does not carry out computation。

 So when we construct this and we call make from op， it goes through it。

 that populates all the field that we just talk about in the last part of lecture in the last part where we talk about the inputs the opt field and other fields。

 But it's not carrying out the addition computation。

 So where does the addition computation is being carried out。



![](img/499306a950c4659b4ff8778f4f2d8058_202.png)

![](img/499306a950c4659b4ff8778f4f2d8058_203.png)

You'll find an addition computation。 when I do x1 plus x2。



![](img/499306a950c4659b4ff8778f4f2d8058_205.png)

Actually， it's being carried out in。

![](img/499306a950c4659b4ff8778f4f2d8058_207.png)

Let's see。

![](img/499306a950c4659b4ff8778f4f2d8058_209.png)

![](img/499306a950c4659b4ff8778f4f2d8058_210.png)

Actually， it's been carried along in this step called Tensor Do realize cache data。O。And so。

 so what does ten or real cache do So effectively as the function says， right， try to。

Carry out a computation and and compute that output value for this given operations， for given input。

And then it also tries to and then， you know， you will try to store the cache data onto the cache data field on this。

Okay。And another thing that you might notice is that there's a lazy multip。

 which means that actually when we are constructing this。

 when we are constructing this particular tensor。If服要用 laser mode。

This ten realized character data will not be called。 And as a result。

 computation actually will not be carried out。 So let's take a look at。 Let's try out。

 actually know what happens if we are doing laser。

![](img/499306a950c4659b4ff8778f4f2d8058_212.png)

So one thing that I can try do。I try to see x dot X。 Now let's see if y。Depo x dot X1 plus x2。

 I'm going to say Y do。对呀。You're going to find actually， you know。

 it's actually correspond to a real tensor value or N the array value。A I do Nido dot allgraang。

Not lazy mode equals true。

![](img/499306a950c4659b4ff8778f4f2d8058_214.png)

I'm going to do it again。You'll find that actually， the cache data is no longer does no longer exist。

 So if you， and you can track actually， if you do y equals x one plus。 Actually。

 you can find that cache data is still now， in this case。



![](img/499306a950c4659b4ff8778f4f2d8058_216.png)

So in the lazy mode， actually， you know， we were not popular cache data until it's needed。

 But when is needed， forever example， if I， if I'm going to see。



![](img/499306a950c4659b4ff8778f4f2d8058_218.png)

W的 they的。

![](img/499306a950c4659b4ff8778f4f2d8058_220.png)

Or if I'm going to say why down Na or any other operations。



![](img/499306a950c4659b4ff8778f4f2d8058_222.png)

It's going to run computation and tri computation to populate the cache without you。 In this case。

 you will try to track wider cache。They die again。

![](img/499306a950c4659b4ff8778f4f2d8058_224.png)

You will find that actually it correspond to a real value that we need。

 So if you look at these definition of tense， you can find that。



![](img/499306a950c4659b4ff8778f4f2d8058_226.png)

What we call data functions for cell dot detaach。

![](img/499306a950c4659b4ff8778f4f2d8058_228.png)

And if you'll call the detaach function。

![](img/499306a950c4659b4ff8778f4f2d8058_230.png)

It's going to call ten do makecon save thet realize cache。 So again， right。

 there's this realize cache data function。 That's that， that's doing all the magic。



![](img/499306a950c4659b4ff8778f4f2d8058_232.png)

![](img/499306a950c4659b4ff8778f4f2d8058_233.png)

So let's take a look at a real casity function。If you look at realized cache data。



![](img/499306a950c4659b4ff8778f4f2d8058_235.png)

IThink it's been defined here。 So this is a definition of real cache data。



![](img/499306a950c4659b4ff8778f4f2d8058_237.png)

What， what I try to do is first of I， don check if the sale do cache data field is being populated。

You have already been computed。 It will do nothing。 So， so as a result， you know。

 it will only populate the cache data if it have not been populated。



![](img/499306a950c4659b4ff8778f4f2d8058_239.png)

The second thing I try to do is going to so the real competition happens in here。😊。

Where what I try to do is we'll try to first go through all inputs values。

Call X realized cache data so that that particular input value cache that is being populated。 right。

 And then it's going to call sale dot opt dot compute。

 So the compute operation is really being defined in that opt dot compute function。

 That's going to compute the cache data itself。

![](img/499306a950c4659b4ff8778f4f2d8058_241.png)

And then it's going to return the cash。 actually， you don't need this line。 Thank you， so。



![](img/499306a950c4659b4ff8778f4f2d8058_243.png)

They don't return the not cache that to to the to the inputs。To the input core。 right， So。

 so let's take a look at what are specific definitions of opt compute。 In this case。

 if you look at a wide dot。哦。

![](img/499306a950c4659b4ff8778f4f2d8058_245.png)

You can find that Y。O is otherwise ad operation。Go and take a look at here。

 And you can find this is the definition of a computer。So in this case， we are taking two endD array。

 both of the dark has datata from A and B。And in the current situation， actually， A And B。

 N D is simply lump and D。 So we are simply dispatching to arismetics， right。

 So we are just going to the a plus B。 And it's gonna return the N D values that correspond to that final added result。

Okay， so this is how we do arithmetic computation。 So we can find that the idea is that the value。

Contains oil， as result， Teser contains the necessary information to reconstruct that original computational。

That includes inputs and operations。We can either choose to eager eager mode evaluation。

 which means that every time when we construct that value node， we immediately compute。

The result needed stored onto cache data。Or we can choose to do lazy mode computation where we do not immediately populate that particular cache data field。

 and we only populate it if the data is being needed if the user want to print the data or if the user want to you know track shape of the data or do any other things that might be helpful to materialize the computation。

 and then it would trigger it would trigger realized cache data to be able to run the computation。

And this kind of ego mode executionion and laser mode executionion is also very common design patterns in framework like Pythtch。

😊，I default Pythage actually uses eager mode evaluation。That means that whenever we are trying to。

 you know， perform operation like x plus X 1 plus x2。

 it would directly run the computation along with a computational graph construction。

The advantage of ego mode is that， you know， we are running the computational graph construction together with the computation in an interlead fashion。

 So that actually， in case where computational graph construction become a borderneck。😊。

The cost of condition graph construction time can be hidden with the concurrent data computation。

On the other hand， remember that， you know， in a lot of cases。

 combination of graph construction is really cheap because， you know。

 we are only supposed to be constructing like far， if we are going to do construct a neural network transformer or restnet。

The amount of computation we' are going to perform is going to be so huge， such that， you know。

 if a simply lazy construct and communication graph is not going to cost you any the amount of time of construct communication graph negligible。

 So in that case， it actually lazy mode computations can be helpful because you can first lazy construct graph without having to evaluate then you can evaluate them all at once。

 whether to evaluate things all at once is that we'll be able to take a look at bigger computational graph and perform certain operations and optimization。

😊，For example， Pytoch have a TPU backend that goes through what we call Pytoch X O A。

 And in that case， the TPU backend will leverage a mechanism for lazy tenor that does exactly what we are doing here where。

 you know， they are trying to do lazy evaluation and accumulates all the communication together and trying to do that in a batch。

Similarly， when we are doing automatic differentiation。

 we also construct an entire computational record that also brings opportunities for us to perform optimizations。

On that， the laser code is also very useful。So in needle by default。

 we also use eager mode eager computations as in Pyth， but you can also switch on lazy computations。

 hopefully both of them work and you can also explore as part of a project you know what are possibilities you can use in either lazy or eager mode of computation。



![](img/499306a950c4659b4ff8778f4f2d8058_247.png)

![](img/499306a950c4659b4ff8778f4f2d8058_248.png)

![](img/499306a950c4659b4ff8778f4f2d8058_249.png)

So I've talk about the computational graph and well talk about how does this needle tensor Chris computational graph and how how do we compute these set of computations through either laser or mode。

 Now who me next， let's start to talk about some of the subtle points that can come when the tensor data structure is not a plain array but a computational graph。

 the。 And this is also something that usually people overlooked in our cases。 For example。

 in some cases， sometimes you know， people will come and ask me， hey， this py program。 And。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_251.png)

![](img/499306a950c4659b4ff8778f4f2d8058_252.png)

![](img/499306a950c4659b4ff8778f4f2d8058_253.png)

And after I write for separate iterations runs all memory。What happens in here？And so。

 so let's look at one example program that kind of resembles one possible program that you might write。

Let's talk like what can be， what can go wrong。So let's assume that I have X equals needle do cancer。

1。一他。Well， sorry， too。And I'm going to have something called sum of loss function。That's needle。

 not cancer。Say0 for now， because initially the accumulation0。And now I'm going to do something like。

W equal range。啊好觉。三罗垃西裤。Sa， I'm trying to construct a simple loss function by， you know， x。



![](img/499306a950c4659b4ff8778f4f2d8058_255.png)

Here。And this kind of resembles what possible program you might write in a machine learning training room。

In which case， where what you are trying to do， you are simply trying to iterate over several iterations and you are trying to go ahead and and try to accumulate all the loss function together。

系。On the other hand， you know， what happens under the hood is that。You know。

 not only will accumulating loss function。Because we are trying to compute。

 We are trying to also construct computational work。 The sub loss function。

Theres some loss variables。Actually， Chris going to a computational graph。 No， so， so。

 so you will find have some inputs。As early input 0。

 is another combination graph node that contains its early input field。

And you can kind of keep treating it right。 So， so as a result， after we run 100 accumulations。

 we kind of get a combinational graph that looks like this。Where you have like， you know。

 x times x in here。And you are getting a long train。



![](img/499306a950c4659b4ff8778f4f2d8058_257.png)

Of computational graph， this is my final sum loss variable I here。So one hand。

 people might think that， hey， I'm only accumulating a single variable as supposedly it's going to cost as little memory as possible because I'm only leveraging my single variables。

 In reality， we are carrying the entire train of computations across little its。

 And that's going be very costly。 And， and that's kind of one common scenario where， you know。

 when you build a Pythage program and runs out memory。😊，And so how do I avoid this case？

The way we avoid is we're going to call in part of this operation called stop reading or no autogra。

You can also call it detach function。Where the detaach function。Will take a competition graph。

A node and try to detach that combination ground node So that only contains a plain ten of。

But run us again。Look at sun loss。If look at inputs values。

You'll find that its input value will become empty。 So， so what happens to a detach。



![](img/499306a950c4659b4ff8778f4f2d8058_259.png)

So imagine that equals y equals x is。关an。

![](img/499306a950c4659b4ff8778f4f2d8058_261.png)

Yeah。For now， if you look at why。

![](img/499306a950c4659b4ff8778f4f2d8058_263.png)

Y contains this Y actually do have inputs。你 here。But if I'm calling why not。Det。

It's going to be given， give me another tensor。 Hahfe can say this is why detached。

And then if I I can say Y D has。inputs。Its inputs is going to be empty， and its ops going to be not。



![](img/499306a950c4659b4ff8778f4f2d8058_265.png)

The effective detached operation will take a tensor and try to detach combinational graph Or in this case is x。



![](img/499306a950c4659b4ff8778f4f2d8058_267.png)

1 plus one。Why。Here， and after I call detaach function， I will simply get another value。

 This value in here is actually。Let's say excess0 right。 So this is one。 And this simply， you know。

 y don't cache that will equal。 So it simply creates another value。



![](img/499306a950c4659b4ff8778f4f2d8058_269.png)

So this is a very useful operation when you try to， you know。

 when you know that you no longer need to perform automatic differentiations and you only need value。

 So， so you， you will， you want to call det。 or in the case of Py。

 there's also a scope called with no stop with no autograd。

 and that will allow us to perform computations without computing without heat trace of the computation。

Thats kind of an artifact of having a framework that allows us to not only build up the communications。

Comp area content， but also have ability to be able to trace that computational graph to。

 to compute the underlying， you know gradient values。



![](img/499306a950c4659b4ff8778f4f2d8058_271.png)

![](img/499306a950c4659b4ff8778f4f2d8058_272.png)

Okay。So far we have we have talked about the computational graph construction and how do we perform operations。

 If you go and look at op of Py， you will find that there are a lot more definitions of operations。

 So of course not of them implemented。 So you will find segments like begin your solution and your solution here。

 these are places where you are going to implement the specific implementations of those automatic definition functions and and compute functions and these other functions that are after we implement all this who will get kind of like standal alone automatic definition framework that you can use to perform gradient computations。

 even gradient or gradient computation we talk about in the last lecture。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_274.png)

![](img/499306a950c4659b4ff8778f4f2d8058_275.png)

![](img/499306a950c4659b4ff8778f4f2d8058_276.png)

![](img/499306a950c4659b4ff8778f4f2d8058_277.png)

Within the code， they actually， you know， until you now， we are using we call nu array。

 So that's why we are， we are importing nu array every API in here。 And you will。

 you should be able to use like every API or exponential other things to implement the different operations。

 when you take like take look exponential， which I think is。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_279.png)

![](img/499306a950c4659b4ff8778f4f2d8058_280.png)

![](img/499306a950c4659b4ff8778f4f2d8058_281.png)

Here。

![](img/499306a950c4659b4ff8778f4f2d8058_283.png)

So难受。You can find that it calls into array API not exponential。

 So the reason that we are trying to import N as a separate namespace is that in the future lectures。

 we are going to replace underlying N arrays by underlying array language that we implement by ourselves so that we will be able to take leverage of GPU accelerations。

😊，As a result， you know， we are importing array API and you know， in the future。

 you just need to change the input to our own array。

 so it gives you a more flexible implementation that not only works for the current lecture。

 but also works for future lectures。

![](img/499306a950c4659b4ff8778f4f2d8058_285.png)

K。And we have already talked about all this。 So now let's talk about automatic differentiation。

 So upon until now we have not explained how does take to take automatic differentiation When we talk about all the necessary mechanisms。



![](img/499306a950c4659b4ff8778f4f2d8058_287.png)

![](img/499306a950c4659b4ff8778f4f2d8058_288.png)

![](img/499306a950c4659b4ff8778f4f2d8058_289.png)

That are needed to build this needle infrastructure。



![](img/499306a950c4659b4ff8778f4f2d8058_291.png)

They includes the computationalal graph node that Chris onto to a value class。

As well as the op class and Chris Law to what kind of computation want to performed along the way。



![](img/499306a950c4659b4ff8778f4f2d8058_293.png)

So as recover a last lecture， the reverse mode automatic differentiation will need to take an existing computational graph。

 which we will be able to have from that value by tracing the value of the inputs。



![](img/499306a950c4659b4ff8778f4f2d8058_295.png)

![](img/499306a950c4659b4ff8778f4f2d8058_296.png)

I want to be able construct。Another， by extending this comm graph。

 I want to construct another comm graph along a side that correspond to the gradient computations。😊。

That we need in the in our that that we can use， right to perform the differentiation， okay。



![](img/499306a950c4659b4ff8778f4f2d8058_298.png)

![](img/499306a950c4659b4ff8778f4f2d8058_299.png)

So here's the forward mode automatic here's the forward graph that we have here。

 And then now let's take a look at what are the mechanisms we can have to implement this reverseersible automatic。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_301.png)

The main mechanism that we're going to use。

![](img/499306a950c4659b4ff8778f4f2d8058_303.png)

Is。What we call a gradient function。

![](img/499306a950c4659b4ff8778f4f2d8058_305.png)

So remember that in each of the。In each of the operations in here， let's see， let me take a look at。

LY马丽塔。

![](img/499306a950c4659b4ff8778f4f2d8058_307.png)

You can find that every operation contains a compute， which we already explained。

 right compute kind of defines for a given output for a given input data。

 How do you compute our data using underlying array APIs。😊，It also contains a gradient field。

 In this case， the gradient field contains the definition of a given output a join。

 the a join on that particular node。 How do I compute the partial a。Of the input node。Okay。

 and this is the definition of the gradientding function。

One thing you might notice is that if you take a look at this gradient function let just scroll up so that blocking you folks。



![](img/499306a950c4659b4ff8778f4f2d8058_309.png)

Here。啊。If a took look at its gradient function definition。



![](img/499306a950c4659b4ff8778f4f2d8058_311.png)

You can find that instead of having NDRA。As its inputs， it contains output gradient as a tenor node。

As well as the the node correspond to the current output value in the in the forward computation。

 you found that they of of type tensor。As opposed to objectt and dairy。Why is this the case。

This is because we want to be able to。Take the not only compute value。

 we also want to be able to compute the entire computational graph that keeps the traces in here。

 So effectively integrating computations。 I try to construct new tenss that not only contains new values。

 but also contains the computational graph that that connects things。😊，Okay。

And even take a look at this otherwisewise gradient definition。

This is the output I don to remember that we have， in this case。

 I think this operation company check this operation again。



![](img/499306a950c4659b4ff8778f4f2d8058_313.png)

Now operation correspond to v 4 equals v2 times V 3。 So V4 equals v2 times v 3。

And we know that in gradient calculation rule。We have we new compute  two things。 We new compute B 2。

2，4。Ajo。IV。3，2，4。白种。Remember that the definition of。The I to J， I joined。Yes。Jas adjunct value。

How show VJ how show VI哎。So let's try to plug it back。 If you look at 2，2，4 ajo， the 2，2，4。

 a join equals。The tooth a joinedin。Times partial V4， partial V2。And this will equal the2 surge join。

Soorrry。Its V for I join Part B or Part B two， before force the join times。



![](img/499306a950c4659b4ff8778f4f2d8058_315.png)

V3哎 so similarly， we know that V。3，2，4， partial a join should equal before a join comes B 2。

So that's a derivation。If you'll go and check。

![](img/499306a950c4659b4ff8778f4f2d8058_317.png)

You will find that this crisp one to。Before I joined。Is Chris going to be too， true for ajo。

Which is before I join Thomas。You know， I to S is this is V2。Is3。 I said this is。We two to before I。

 so sorry， this V this， this is before I joined。This is P 2。This is fee 3。This is before I joined。

V2 Tom V2。Before I joined House B3。

![](img/499306a950c4659b4ff8778f4f2d8058_319.png)

Oh sorryrry， Tom speed2， right， So these is I like to inputage on here。

 And it's also might be also helpful to take a look at this input computational graph as well。

So let me go back。

![](img/499306a950c4659b4ff8778f4f2d8058_321.png)

back considering here。Let's take a look at Chris morning， So look at the gradient function。

 Can I find that。This value。Chris fall to this one。

This is going to increase one to this value in here。

 And you can find that is the modification of before I join here timess V3 in here， right。

 and similarly。It V3， I joined Chris on2 before I joined here。And this is V 2。

 Well V2 is it's on this side。 So this is V too。Okay。

 so youre going to find the effective gradient function defines what input， output a joint node。And。

 and the node， in this case， the node here。Directly， crisp bond to V 4。 So， so this is。V 4， No。

 it's too hard to see this， but I can scroll it over。 So you can find that node field here。

 Chris on to V 4。 Alright， So that's why I can say no dot inputs astronomer B V2 be 3。



![](img/499306a950c4659b4ff8778f4f2d8058_323.png)

So we can find that actually gradient function defines a one step rule for us to take the output a joint and derive the input ajo values for each of these inputs。

The once we have this， we should be able to leverage this function to help us to in a recursively traverse a computationalal graph and then compute the final input gradient values of each other them crystal。

😊。

![](img/499306a950c4659b4ff8778f4f2d8058_325.png)

So of course， we are not going to implement that reversal A evolution because that's called your homework。

And but hopefully now we can kind of get all the mechanisms needed to implement that reversely。哎。

One of the thing is that I want to， I want to remind everybody is that。In the greetding function。

 So right now， we have like an output a join as a tensor。

 And then we're going to return a two pool of tensors because we can have multiple inputs in the computation operations。

We also allow sugar in certain cases， when there is one single input data variable in this case。

 gradient can simply reach cancer。But to help us to perform say like a process。

 in a more unified fashion。We will have a function called。Before。Ddge gradient。到了。好。

So gradient as triple。 So in this case， it's always going to return your the is's always going to return your a triple。

 even though like a。They are not ingrading functionally reaching a single value。Okay， so we can try。

 actually， try to run it。 So I， in this case， I'm I can try to put it， say。The output gradient。

 we know that is needle do tenor。What， right Because we know that an output ad joinin of the final output is always。

With wine in here。And in this case， I'm going to plug V4 here because it's V4 node and I'm going to run this。

 and you're going to find that it's going to give me partial I join of two values。



![](img/499306a950c4659b4ff8778f4f2d8058_327.png)

Of this is the partial a of v2， which equals v3。Which v 3 equals2。

 right so which equals2 times v force a joined1。 And this is the partial a join or V3。

 which equals 1 times 1。 So we can confirm that a single step operation is correct， so。

As part of homework， what we need do， we need to be able to recursively traverse this combination graph and trying to bring together all those single step。

😊，Greedium calculations。So that well be able to construct another We will be able to construct a computation。

 gradient computations for each of input。

![](img/499306a950c4659b4ff8778f4f2d8058_329.png)

They also try to code it。And in this case， I think this should be called no be 2， a joined。哎，你睡。

Everyone玩。And if you look at。One thing that I want to， you know， it it should be obvious right now。

 but let me try to， you know， explain again， to print node。



![](img/499306a950c4659b4ff8778f4f2d8058_331.png)

Of these three adjuent。You'll find that actually， this fifth3 edgeron is not a single tensor。

 It's also computational。So that is why， you know， that that is why we can still。

 well still be able to perform gradient gradient computations。 For example。

 you should be able to take this V2 edge and perform some operations on it and then still take gradient operation on it because。

😊，Oh it， you know， it is a computational graph。 No。

 that still contains all the computational graph executionion that allows us to be able to do the analysis and find out the corresponding ingredient values that we need in our final computation。

😊，Okay， so so it also motivates kind of like the difference of the signatures in terms of compute。

 which only specifies how do we want to realize the computation without building a communication graph because that's already part of the data structure。

While the gradient function really not only specifies how do you do computations。

 but also you want to specify it in a way of how do you construct cancer values so that it can be used to construct construct a communicationogram that allows you to do gradient gradient operations would be part of your homework。

 which is kind of fun to implement and get right okay。



![](img/499306a950c4659b4ff8778f4f2d8058_333.png)

So one amazing thing you can find is that even though needle is no。

 only contains about 1 thousand lines of python code。😊。



![](img/499306a950c4659b4ff8778f4f2d8058_335.png)

It contains almost all the fundamental elements that we need building up a different framework。

 including how do you build my dimensional array， How do you build on my differentiation and computational graph tracing mechanisms。

 as well as how do you do the reverse mode through those gradient function。



![](img/499306a950c4659b4ff8778f4f2d8058_337.png)

So it is a fundamental， simple， necessary element that will be used in the following lectures and hopefully we will be using it to also build our own diploma applications from scratch。

That is end of today's lectures。 Thanks， everybody for coming。

 and I will see you in the next few lectures。😊。

![](img/499306a950c4659b4ff8778f4f2d8058_339.png)