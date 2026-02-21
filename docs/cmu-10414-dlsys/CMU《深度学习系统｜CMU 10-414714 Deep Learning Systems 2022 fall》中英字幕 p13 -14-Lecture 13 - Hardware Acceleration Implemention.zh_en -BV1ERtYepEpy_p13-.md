# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p13 -14-Lecture 13 - Hardware Acceleration Implemention.zh_en -BV1ERtYepEpy_p13-

Okay， hello everyone。 We to the plan system actually implementationation。Today today。

 it's going to be exciting lecture。 So we're going to work together to implement。

 go through implementations of power acceleration libraries。

 and I're going to use the knowledge we learned from the last two lectures to build up some of this implementation that we're going to use for our third homework。

😊。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_1.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_2.png)

So the begin ways， we do need to select coab with the couda support。 So what you need to do。

 So its the bra step is a bit on the top that you can offset。

 but you want to go ahead and select roundtime and change roundtime type to GPU。

 So in this case already do it。 and you can find that I get video T4。

 we're going work together to implement， go through implementation of power acceleration libraries and we're going to use the knowledge we learned from the last two lectures to build up some of these implementation that we're going use for our third homework。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_4.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_5.png)

So to beginaway， we do need to select a coab with the ka support。 So what you need to do。

 So it's the bra step is a bit on the top that you can offset。

 But you want to go ahead and select roundtime and change roundtime type to GPU。

 So in this case already do it。 and you can find that I get Nvidia T 4 GPU。 in this case。

 And we're going to use it for some of our examples。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_7.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_8.png)

Then what you want to do is you want to run this code block specifically if you run for the first time you un this code block that allows you to clone a local copy of needle in this case。

 lecture 14s version comes with comes with a set of you know library implementations that。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_10.png)

A lot。Then you want to go ahead and do pi of Pi band 11。 that gives you a version of pie band。

 this case。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_12.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_13.png)

So。Once we have that， we can go ahead and build a needle kuda library。 In this case。

 the needle kuda library contains。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_15.png)

It so we want to be able to have a Cmic file that allows you to go ahead and build the relevant library in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_17.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_18.png)

So after we have that， we should be able to set。The environment variable。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_20.png)

Here， and then we will be able to use that to build our end network library。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_22.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_23.png)

So before why we are building， one of the things that we can do is let's start to take a look at the new code base that we have and compare know what's the difference between this code base and previous ones。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_25.png)

Look at this。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_27.png)

We can point that， of course， we have our old friends。 We have our friends of Python file。This case。

嗯，谁？

![](img/74d8e5ceeee6b46908d181b8f7c6a055_29.png)

So of course， we will get our old friends that contains a set of Python files that we have。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_31.png)

嗯。Like I here， see makelist and a few other cases right on beside this， we also have let's say。

 we also have a source file folder。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_33.png)

That contains a two additional source files that correspond to the Ka implementation that were having in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_35.png)

And this， and finally， I think the additional thing that we get is this C plus sc out file along with。

A new folderer。比说那个 needle。There's a new photo called backend and the array。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_37.png)

And this is a folder that contains the implementations of the new ND back that tries to replace the original nonpi。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_39.png)

So the main goal of this lecture help us to create acceleration library called an D。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_41.png)

And so that we do not need to deal with So， so， so we do not need to， you know。

So that we do not need to use nu as a as a backend anymore。 The result， actually。

 a lot of our today's content do not have things to do with needle do answer。

 And will'll focus on the back end。ND implementation in here。

And after we build up this array library， we can then use it to power some of the backend array computations in need。

Okay， and there are other files that comes along that you don't have to necessarily take look。

 So I would certainly recommend you take a look at all the implementations in the back and end radar folder and implementation on a source folder as well。

We provide you a see make list and make file that helps you build a library。 So if you're interested。

 you are more than welcome to take look， but it's not required that you have to go and look through every file in there。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_43.png)

可。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_45.png)

So first all， we want to be able to create a backend an array in this case。

 what you can do is you can do from needle importpart backend an array as Nd and we will be able to and we will be able to create an array so Im hope I could do like x equals in one to3。

Or you know I can do， you know， X equals N D 1， to3， but the device equals ka。 in this case。

 you can go ahead and track the device is in ka。 And if you will try to read the content。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_47.png)

It's now going to give you N the array 1 to three。 So actually。

 this is the first time we ever created a GPU array。😊，Even though if you may have not noticed it。

 there are a lot of like interesting things that going on when we are starting to build this kind of implementation。

 like example， while we are doing ND creation， we are copy data from our CPU memory nu onto a device memory and then we are printing out。

 we are printing out all the contents。That comes with no values。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_49.png)

So of course， besides creating an DNA， we can also go ahead and do some arithmetics for example I could do y equals x plus1 in this case actually it a scalar a and this is actually the first implementation of a kuda kernel that allows you to be able to take a kuda data and being able to do athmetics on top such as you know and this is like a animalized add。

 we can also do more like a tensor plus tensor in this case， this is double value。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_51.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_52.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_53.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_54.png)

Of， so， so， so one we had。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_56.png)

So that's kind of like a brief introduction of the ND array， what we can do with ND array。Now。

 let's take a look and dig deeper into， you know。What are the necessary elements we use to build up this end implementation。

 So in that case， we want to be able to take a look at the ND dot P I。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_58.png)

It are structure in back and an near。 and let's go through the codee in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_60.png)

So， so before I introduce it， one of the things that would like everybody to step back and think about is。

 how would you implement？

![](img/74d8e5ceeee6b46908d181b8f7c6a055_62.png)

AndD data abstraction。On my hand， we know that， you know， in most of the cases。

 the data structure that we have， right， most of the CPUU memories and GPU memories allows you to have a flat。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_64.png)

Every data structure。That allows you to have you can you a ka me to allocate a continuous region of。

 of memory。And one of the key things we want to do is we want to be able to turn that one dimensional flat memory onto a multi dimensional。

 That's exactly what NDR is doing here。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_66.png)

So if you the main data structure of an array is this N array class。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_68.png)

And this anary class contains a few key fields。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_70.png)

So you can find the key views in this init file in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_72.png)

You can find that it contains shape， strips of that device and handle。So in this case。

 actually all the fields， including shapes right off that5 is are in Python。 find more shape。

 It's going to be a Python tuple right。 It's also going to be a Python tules of that is's going to be a Python integer device。

 It's going to be a data special called backend device。

The only thing that actually are dependent on some of the C plus file is this handle。That。

 and this handle file correspond to。A one dimensional array that pointer that we're going to look at。

 Okay， so， so effectively all represent an in dimensional array。

 all we want to do is we try to take a one dimensional array handle。

And then we are going to add additional fields such shape strips。

 offset and device that represent a particular end。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_74.png)

So now you might be a bit confused， right， So what does it mean to have a handle that's one dimension。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_76.png)

One of the things we can do is let's take a look and trace what happens。 So in know code。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_78.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_79.png)

That we had in here。We used to do things like y equals x plus1。

So one question you want to ask you know， what happens when we do y equals x plus 1。

 what are the necessary functions and implementation that that goes through to implement that okay？



![](img/74d8e5ceeee6b46908d181b8f7c6a055_81.png)

So let's trace through what happens when we do like a GPU excions。So， first four。Or we do x dot nD 1。

2，3。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_83.png)

The first thing that we want to do is we want to be able to create a one dimension， create a end D。

 And in this case， the device is included。 So， so in this case。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_85.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_86.png)

If you look at the Englishization function here。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_88.png)

The initial function tries to goes into this one that says， you know。

 if I'm trying to create from non， actually， in this case。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_90.png)

It is something。 It's not exactly an non， but we want to be able to in it's creating does。

 right So it's creating。你。It's creating。An endD， aump endD， O， and then。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_92.png)

It goes into the in function and cost I read device stop from number。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_94.png)

可。😊。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_96.png)

And by passing in。The data content。 So in this case。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_98.png)

The it first core selfdomt make。To create an linear area structure。

 and it call it then calls from Namhai。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_100.png)

By passing they data and a hand。 Okay， So depending on what depending on you know what。

 what is the corresponding device back， actually， the。

 the selfdom make function from Nai actually dispates to different executionion modes。

 So let's take a look at some of them。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_102.png)

啊，MC。If you look at the。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_104.png)

In stride， so if look at the make function in here。You can find that in a make function。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_106.png)

It takes in shapes。 it takes in shapes， strides， device and handle。 And if handle is now。

 what it will do is we try to call a rate device array by passing in a size field。

 So effectively the underlying device back and will try to call will try to build a array function that they try to return the array of a cr size。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_108.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_109.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_110.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_111.png)

And the device of array function is being implemented by some of the array and some of the device。

 So in this case。The device goes into this backend device。

It goes into this backend device class and the backend device contains contains a module。

 So the module actually correspond to the implementation。 So when we are trying to do you know。

 device do array Actually， it goes into this get enter function and then goes into self do mod dot dot array in this case。

 and and you can find that example for kuda it goes into N backend ka module or we also have a non implementation。

 actually， that backs this particular computation specifically through nupi。

 And we also have a CPU implementation。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_113.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_114.png)

So now let's take a look at what happens when we call device salary。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_116.png)

So there are different implementations， for example， in the in the non backend。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_118.png)

This is array implementation。 effectively， what you try to do is it tries to give a size and try to allocate a array using floating points。

 So， so to make things simple， actually， our array libraries only assumes the data type equals floating point。

So you don't have to implement the other parts。 Okay。

 so you can find that the array constructed effectively is creating an empty area。 Remember。

 there's also from nu function that copies a， which is the input N data onto the correspondinging handle。

 In this case， just try to copy the array content onto this。

 So this is the implementation of a nu that。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_120.png)

Now， let's take a look implementation combination of a CPU back。bit， so it's another implementation。

 right， if you look at array ray construct。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_122.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_123.png)

This is a pie by module that exposes several implementation。 So if you look at array in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_125.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_126.png)

What you try to do is we try to simply call the initializer of this aligned array data structure。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_128.png)

So when we call a， what effectively it does this it will allocate。

 we will call this a line array with a constructor size。

 and on the hood it will try to allocate a pointer of a crisp element size and a crisp alignment。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_130.png)

So effectively， in the CPU implementation， what you call this。I high CPU back do array。

 they will create the array on the CPU side。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_132.png)

And the second thing is， well you remember that there's a call onto from Nmai。

 So when there's a from Nmi， In fact， it becomes every copy， that copies the data from a。

 which is the input Nai array。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_134.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_135.png)

On to the pointer that's got allocated of that binary。

 So you're going to find that in the case of CPU。Each of the handle field creates one to effectively this pointer to a。

 in case。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_137.png)

There's also a case of GPU。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_139.png)

In the case of GPU， the handle correspond point to a pointer to a code out。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_141.png)

Where we are doing Ka analog to allocate the total number of elements in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_143.png)

And when we are doing distracting， we are doing good are free to free the crisp element。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_145.png)

And we can find that there's a array function。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_147.png)

That construct。They corresponding that that constructs the overall arrays。

 when we call the Kuda back and module array。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_149.png)

And then then there's from Npai function。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_151.png)

That effectively run memory copy by taking the data。诶。And from the and doing， you know。

 kuda man copy from host to device to the allocated to the allocated ka every point。

 So you can find that effectively when we are doing this initializers。

 kind of a lot of things happens， right， So let's come back to the part。 So were doing initializers。

 the first thing they are going do is we are going to call。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_153.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_154.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_155.png)

Self dot make。And that's going to call into this self mode device do array that goes into either the CPU Ny or ka backend that allocates the corresponding array。

 and then we're going to call from Ny， which actually is does a memory copy that copies the data from other onto the corresponding array underscore handle and underscore handle corresponding to the allocated array field that that you use to be able to allocate the corresponding memory and copy the data onto it。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_157.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_158.png)

可以。😊。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_160.png)

So。Here is the overall implementation of this constructing。

 Then we want to come and see what happens when you call， you know Y equals x plus  one。

 So what happens when you do an arithmatic computation here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_162.png)

So what was say is that。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_164.png)

We we do in arithmetic computations， first all， it， going through dispatch to an overloaded operator。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_166.png)

So let's see what is the overloading operator in this case。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_168.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_169.png)

So you can find that。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_171.png)

The overloaded operator here is the add operator right and fall into awise of scar to this operator。

 And effectively， what we try to do is we detect whether or not the other field is is endD array or or a scar。

 So if the other field is endD array， what you try to do as you know。

 you will invoke elementwise function。 otherwise will invoke a scar。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_173.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_174.png)

So in this case， you can find a scalar function is Chrisbonluoto divided scar a the effectively is invoking a scalar function by passing in three things。

 The first thing is the left hand operator handle right the second thing is the other corresponding the other handles in this case in the scalar is just a scalar value and then its the output handle。

The second thing youd realize that in the output L Y scan or add in first course Nt make。

 So in this case， we don't pass in any handles it's want to create。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_176.png)

A new is going to call the array location to create a new empty array of Christmas morning shape。

And then this correspondingboning scalar function elementwise function is going to do the computation to fill out the correspondingboning output array elements by running through the computation。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_178.png)

So。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_180.png)

If you go ahead and look at。The the GPU implementation of Scala app。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_182.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_183.png)

You'll find that。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_185.png)

There is。Salar add function in here that creates going to Scalar add function by defining say plus plus。

 So it just scroll up。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_187.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_188.png)

On the scala， and。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_190.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_191.png)

一四。You find that let's correspond point to this scalar a kernel and you can find that in the scalar ad kernel contains a few arguments。

 The first argument is a Q di that's been passed by the cell dot handle in the previous code。

 It's a scalar value is a second argument。 And thiss output array view in there。And sca at Colel。

 go ahead and invokes that Colel with the Chris morning with the Chris morning S。哎。😮，And then。

What you can find in here is that once you have a scala a kernel。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_193.png)

Let's see。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_195.png)

You will be able to go ahead， and。You know， and， and this is the implementation of a scale a。

 effectively， you can find that the code out one dimensional is ox3 function that will try to compute the correspondinging launching size of grid and block。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_197.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_198.png)

And we will be able to， if I， if I have to divide things up through， you know。

 the number of threads and well be able to launch this through this。

 And this is a typical kuda implementation that we' see in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_200.png)

Now， we can also go ahead and take a CPU implementation， which can be more simpler。

 So if you look at Scalar a kernel in here function here。

 let's correspond on to a Scalar add function。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_202.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_203.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_204.png)

In here that contains a， the， the le hand input。The values are being added。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_206.png)

And output。That that gives that gives you a sequence of， you know， that that gives you the。

 the output content that you want to store into。 And one of things you notice that in all those cases。

When we're doing arithmetic computations， we're explicitly allocating the input and output array。

 and then we are going to iterate over those iterator domains by know taking the input。

 doing additions and writing that onto the output component in here。Okay。😊。

So we have these sc a implementations。 And one of the things you realize that is that。

 in almost all the cases。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_208.png)

ComCom patterns， we are going to allocate the output and then run the computation。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_210.png)

Another thing that you might notice is that when we are passing in the handle， which is the array。

 right， there's always the call of compact。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_212.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_213.png)

And this is because， when we are representing the NDRA in in a multi dimensional fashion。

 theres this field called drys and offset。Which means that， you know， in certain cases， formula。

 if onem trying to do additions of two dimensional matrix。And， and you know。

 depending on where the matrix come from directly passing the one dimension channel may not be right。

 So， so this is something that we can also come back in the next part and you will see a bit more of why is the case。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_215.png)

So we goes through the key data structures of back on the array and trade through GPU implementation。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_217.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_218.png)

Now， the final thing that we want to look at is what happens when you call Y down Ny or you know。

 what happens when you directly print out Y that copies the data back to N。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_220.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_221.png)

So， in this case。You can find that when you call the number排。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_223.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_224.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_225.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_226.png)

Let's say where theumpy operation is。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_228.png)

And what it does is directly called device dot true Nm right copies the data onto Nmi device。

 In this case， you have self to handle， a shape， strides and offset。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_230.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_231.png)

And then let's take a look at CPU implementation of2 N pie。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_233.png)

You can find that effectively it will try to copy the data。On to Leri， by creating。

By by transforming the original strips to lump strides and effectively。

 create a lump array that correspond to such that corresponding to a corresponding layout。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_235.png)

And on a GPU part， it could be a bit more。Slightly more complicated。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_237.png)

In this case。You can find that。It's going to first for， trying to copy the data from。

From our original host pointer， right on to on to the corresponding device。By。

 by copying actually the entire array onto the Christmas device。

And then it's going to create a nuey dry array based on that particular part。开。

So we have gone through， we have read through some of the code， right， So in this case。

 I would recommend everybody to go through and read the source that kda backend CPU backend。

 these like tool backend implementation。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_239.png)

That implements both how do you do every locations， D location through every and their Dlocator。

 and they are examined by the underscore handle field， as well as the arithmetic implementation。

 such as the， such as the。You know， Adam addition and scala。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_241.png)

We have already gone through the ND film。 So next part。

 let's go through and talk about stride computations。 One thing you might notice is that that's this。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_243.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_244.png)

呃，那 this呃。Element cause drys， right and and and shape and often。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_246.png)

So the question， one question that we have is know， why do we need strike？

The reason being that depending on how do we specify the stride and shape and device。

 we could get different variants of of。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_248.png)

F后， you know。Imagine that we want to take this original array array， which is。

 which is one dimension array that contains6 element。 You want to resha it。

 Let's say you want to resha it to a 2 by 3 array。What you effectively need to do。

Is that you dot not have to really create a two by 3 a new array that is 2 by 3 and copy the data over。

 What you really have to do is just need to be able to call N D ort make by passinging explicit the handle。

 So in this case， we are creating。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_250.png)

A shallow copy of the original nearly that's backed by the same underlying array memory。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_252.png)

And what we need to do is we just specify my strip is 2 by 3 and my strive is equal 3 by1。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_254.png)

So effectively fact， we are still indexing to this original array and my result， Z， I J。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_256.png)

It's gonna equal。你 I read data。I times 3 plus J， where 3 corresponds bond to the first strides and J times 1 corresponds one to the second strides。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_258.png)

So effectively， by specifying the threefielders drys field， you will get a different。In theory array。

 that's reshaped。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_260.png)

Now that only we'll be able to do reshape。 we can do other operations。 For example。

 all the things we can try to do is let's see， you know。

 what if I want to slice it now we have the we have this in the array of， you know，0，1，2，3，4，5。

 right， What if we want to just slice the the second and third row， Okay。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_262.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_263.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_264.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_265.png)

What can we doing here。So。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_267.png)

We want to do a sliding operation。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_269.png)

So let's see if we want to do。B。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_271.png)

一 person we don't make。I want to do a slice。Okay。So because we want to slice， right。

 So the first question we want to ask is know， what is the result of slides， Okay。

 we want to have a2 by2 matrix because， you know， we want to slice things a two by2 matrix， right。

In terms of strides。Actually， we will keep it straight as it is。

But then we want to be able to also specify the offset。

 So remember the offset crisp one to the offset in a read that the first element crisp one to。

 So in this case， the first element is is one。 And in this case， offset should be equal。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_273.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_274.png)

Should equal one个意。The go had riot。You found indeed， you get a slice of a， right， So in this case。

 you can find that this B array U is backed by the underlying handle。That contains six act。

Except that without saying that。My B array is shipped to by two， and then B， I J equals。你对啦。

The first offset。Plus。I， Tom3， which is a strides。Plus J in here。And then that gives us a new。

 completely new array that's been sliced。 In't that amazing， this case。

We'll go ahead and do row sing。 So let's say I'm interested in getting the second row in here。😊。

So what do I do。After， if you want to do low sing， you can find that we're gonna get a one by。3。A瑞。

And then， of course， drives need to be the same， but the offset is going to correspond to the offset of three。

 In this case， this offset equals。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_276.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_277.png)

水。Let we try that。You're going to get the second rule。right。

 so so there are different ways we can go ahead and try to be able to create different values。

And these different values correspond to depending on how we are going to set the shape。

 strips and so on， it's going to give us differences okay。Now we have tried slicing。

 The next thing we can try is we can try transposition。

 So let's say we want to take take take in this case， they or X。And want to be able to pass it。

So originally you can find this two by three。 I want to transfer to transport to to three。掰除。

In this case。If I want to do transportationposition。

We know that the strides should also be transposed。Try this one。Ibro had arrived。

Youll find that you get a trans post version， you get a trans post version that contains you know，0。

3，1，4 and 2，5。 and that's exactly jas position of original。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_279.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_280.png)

And this is interesting in a sense， that you can get a new version of a array by just swapping your twice and of course。

 swapping your shape。So we can find that。By manipulating the shape strides and offset that field。

 we'll be able to get different views of the same originally that is being presented a differently way。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_282.png)

Okay， so one last thing that I would like to mention is that we can also try the broadcast。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_284.png)

The originally。 So in this case， let's assume that I want to broadcast on the first dimension and then actually directly correspond to having a new shape。

 So I want to originally is a two by 3。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_286.png)

Tsor， and I want to try to make it 2 by 3 by 4。 So I'm adding a new broadcasting dimension in the last dimension here。

So if you want to do broadcasting， what you are trying to do is you are going to create a new array that contains2 by 3 by4 with also a stride field in here。

And。And you can find that one of the key thing here is because we are trying to broadcasting which you repeat that dimension。

 you simply set that drives equals 0。As a result， my， my index， B， I， J。K， it's gonna equal the data。

I times 3 plus J plus k times 0。 So effectively， the K index is not going to give you any offset as a result is a result of broadcast。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_288.png)

So that's also another very useful thing。 if you want to be able to create a array that's being broadcast along one dimension。

 And it's kind of amazing as we're creating a bigger array that's bigger than the total number of element than we had our original array by just adding a dimension that contains zero strips。

😊，Okay。😊。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_290.png)

So again point that by running different ways of， you know。

 by doing different things like a different strip and shape and we're going to get and an offset we're going to get different views of their。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_292.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_293.png)

And in the homework of Earth， you are going to need to implement those different array transpositions and optimization number you want to be able to take to swap certain axiss。

You want to be able to take a read and do array ratetransposition and you want to take a re do slicing。

 of course， take a re do broadcasting。 All those operations you don't have to implement it by you know。

 running， by by actually running and allocating a code and copy the data onto a new position。

 Instead， you are just going to create this new。They are a structure that contains， you know。

 different， contains a same underlying and array by different shape and structure。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_295.png)

Okay。So。Once we have。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_297.png)

This fields。The， the next thing that。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_299.png)

That we want to consider is now we kind of have this money dimensional already。 So you can find that。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_301.png)

We could have final in this case。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_303.png)

The slice array。That is kind of like crisp one to one slice。Depending on how you want to size it。

 or we could have this transpoory。 So in this case， this transpoory rate crystal one to read that is。

That have a different iteration order。 So， so if you read it out in one dimension， it should be 0，3。

1，4，5，2，5， right。So imagine I'm going to add it。 I'm going to take B and add it to say another added by one。

 right， or add it to another two by three tensor。In this case。If we directly pass in B dot handle。

You will notice that when we do elements by add， right， the the underlying。

 the underlying code of M add directly takes in the flat。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_305.png)

看到。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_307.png)

So， let's。购买。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_309.png)

So you can find that fine point here， and simply takes in two arrays， A and B。

 is's going to iterate over that and you're going to add issue of element in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_311.png)

But remember that if you are going to consider strides and offset that。

These things are not necessarily taking into consideration here。

 So when we're having a rate that contains one more strides that that is not。

That does not correspond to a normal iterator order。 R why you have an offset。

 Then we are calling that this array is not being compacted。As a result。

 you cannot simply pass seeing this you know， one dimension array do an addition here。

Another example would be， you know， what if I want to do slicing， say in this case。

 I could try to make a2 by two array by slicing the first element。And so。

 so I'm getting a four by four range here。Imagine I'm do add one to this4 by4 array。 of course。

 we want to be able to pass in handling here。 But however， this handle per to the original。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_313.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_314.png)

嗯。A array that contains6 element。 So if we directly pass the original onto scalar a。

 it's going to add all the six element by that corresponding value。

 Sa I I'm going to do things like Z。😊，Plus one in here。

 And if I'm going to directly pass the original handle。

 then it's going to add all the element besides the element thats are getting sliced。

 So that's becoming a problem。So that is why。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_316.png)

嗯。That comes back to our previous discussions of why there's a compact function。

In the ND implementation。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_318.png)

So you can find that in this case。That's the compact function。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_320.png)

And what compact try to do is it will track， first of all， if they eras compact。

And raise compact if it if offset is 0 and it drives directly correspond to the normal row major order that you will normally have。

 So effectively， if you flat and that array is correspond to the hand that you have。

And so if the array is compact， this wouldn't do anything。

 So if you're allocating array and not doing any transpositions on top。

 compact function is going to return the original array。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_322.png)

On the other hand， if it's not compact， what it will try to do is it will try to make a new compact array and call device or compact。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_324.png)

That tries to effectively take original handle right that contains offsized driving shape and trying to create a compact version。

 but really， in this case， we are copying the data onto the corresponding location。

So the compact function is like a lazy function that that try to check whether or not we are compact。

 and if not， we are trying to make it compact。The reason why we introduce things like stridees and offset that。

And then in an operation， where you call compact function。

 it helps you to be able to lazily perform some transmission。

 So you could imagine that I can have a case where I can do slides transpositions。😊，And。

 and broadcasting for for， for example， on module steps， right， and then a certain time point。

 we need to call compact。 So we are realizing that corresponding area。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_326.png)

So in most of our implementations， one point in Ls add。Keeps things simple。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_328.png)

We simply always call on the compact function。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_330.png)

So that makes our implementation simpler。 right， So you just need to be able to always call compact functions。

 So， so in this case， you know， if you call the broadcast tool or transposition or other operations。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_332.png)

The compact function is going to give you a compact version of that。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_334.png)

And。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_336.png)

And you know， the， so， so effectively of implementation， you know。

 you don't have to worry about whether or not I need to deal with the addition of array that is contains difference strides and offset。

On the other hand， we can create a specialized implementation by add myself said。

That does not require a compact。 So we could have an implementation， for example。

 for two dimensional matrix。 We could have a two two dimensional iterator that iterate over I and J。

 create the add one and then return the result。 So it's really an implementation detail。

 A lot of the arithmetic libraries do have operation modules that can take in those you know。

 slide it array into consideration without having to deploy， create a compact version。

And if you are interested， you're also more than welcome to implement that。On the other hand。

 when you use Pywach in other cases， you might find that there are cases where they do explicitly call compact or contiguous。

This is because on certain operations like nature publication。

 it is useful to have a continuous memory access in a lot of cases。And as a result， you know。

 some of and convolution and nationalvocation it's helpful to be able to call compact so that you get a continuoustiguous implementation before you continue。

So in our implementation， we will always encourage you to call compact to。是谁？

You simplify your implementation。But you're also want to welcome to implement arithmetic operations that works for non compactact memory。

 especially you know I Hawaii multi， a lot of the existing implementation do help you to do allow you to have like non compactacted iterators on at least one of the damage。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_338.png)

Okay， so that is how we do memory slicing and contacting。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_340.png)

Now let's come back to example， code。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_342.png)

One of the things that we do know we want to notice you know we can do like a GPU acceleration。

 so let's take a look at the GPU acceleration coding here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_344.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_345.png)

So in this CPR acceleration code， you can find that。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_347.png)

There are different definitions of， of， of coding here。 as a point right now。

 we define Ms add and modify。 and let's see。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_349.png)

What if I want to do。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_351.png)

Yeah what if I want to add an operator， what if I want to add random division for on？

So that I will walk you through how we' are going to do that。 So first of all。

 want to be able to be able to define the two functions。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_353.png)

Mwise def scalar division， right， and then want to go ahead and define the correspondingian kernels of those function。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_355.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_356.png)

Of course， because my my division is going to be very similar to analyze add and multiply。

 I just going to copy。你。A voiceice and multi kernels in here。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_358.png)

That车。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_360.png)

And then。I'm going to change。The signature to El Y's division。devision可能。

We know that the division is。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_362.png)

Yes。食啦，你。Say this a sc。得bitition kernel蚪。Anda。diic发生。that allows us to perform sca division。

And we're going to in scholar division here。Andm amoize。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_364.png)

不个生。开。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_366.png)

So now let's take a look at。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_368.png)

What we can do is we can go ahead and call make， and it will try to go ahead and build。That function。

And this is how we can do development you， cool environment。 You can add a new function。

 and you can go ahead and try to。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_370.png)

Try to build that new module。Now what we can do is we can go ahead and try to create a array。

This case。And then do x divided I by 2。What thing might point is that actually it caused that you know that's the error here and there's no element division。

In this case。The reason is that although we build this array library。The current。

A ray module being imported in needle is has not been freshed。So， so， you know。

 we kind of need to in this case we if you want to do it in our Python notebook。

 you want to be able to go ahead and restart the environment， you to to be able to do that。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_372.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_373.png)

Let's not do that。 Instead， what I'm going to do is I'm going to create a new test file。Let's see。

 that's name to be test。O。😊，And I'm going to directly add this task file。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_375.png)

So in this case。We I're going to do from needle back on any array。

 and I'm going to do print x divided by3。O。😊，And what I can do is I can now go ahead。

And in a coab environment。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_377.png)

run pon。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_379.png)

Test。你 tried老个。You can find it actually，The deficient result is modification seems that there's the error in my implementations。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_381.png)

Let's come back， and。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_383.png)

Say what's going on。So。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_385.png)

Sow back toda。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_387.png)

S了 do。어떡게。I that still my application？

![](img/74d8e5ceeee6b46908d181b8f7c6a055_389.png)

せで。我标了嘅。

![](img/74d8e5ceeee6b46908d181b8f7c6a055_391.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_392.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_393.png)

And run this again。You can find yeah， it gives you the right divisional result。

 right So here's how we are going to implement this。

 And the reason why it works through this way is because every time we are invoking this Python test Py。

 it's gonna gives you a new Python session that helps you to be able to do settings like that effectively fresher import needle and allows you to do interactive development。

 So this is also recommended way for you to develop some of the libraries you can do on a flight testing through this by creating new Python  file in certain cases indeed a bit more complete than Pyon notebook but however。

 this is a way that you can use to interactively use coab development environment in command tool。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_395.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_396.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_397.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_398.png)

So now so far we have Emily worked on backend and DRA。

 one of the things I do want to notice is that no we we can build it and connect it back to a needle environment。

 for I hope， in this case， we are creating needle tensor as opposed to backend andD tensor。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_400.png)

And let's take a look at the current implementation。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_402.png)

You'll find that in the current implementation， the only difference。The we hiding here is that。

Instead of importing nuious array APIs， importing the backend ND arrays array APIs and we are importing all the information from the backend ND array library and we are using array API do non ND okay。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_404.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_405.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_406.png)

So effectively， what we're doing here is that instead of using N。

 where you redirecting all the array computations to the array API， So similarly on op stop PY。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_408.png)

![](img/74d8e5ceeee6b46908d181b8f7c6a055_409.png)

You can find that that's import back and near S every API。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_411.png)

And all computations， like example， you know， computations of additions and so on。 right。

 all almost often， you know， corresponds point to this new endD。 And now in this case。

 it's no longer a N theory。 Instead， its the N D implemented by the backup。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_413.png)

So were going to find that this is a compositional view in here。

 So we are first want to build up the underlying DNA library。 and then in in the needle part。

 we are just going to use that as as a backend array that drives a lot of the ten computations。

Now this hierarchical view also allows us to be able to focus on implementing that low level array perfectly。

 run through testing before we come back and really get a needle library that allows you to both do automatic differentiationation and the underlying array and computations。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_415.png)

Okay， so we can also do a few more things， including。

 you know doing things like gradientding computation and other cases。

 I don't have time to run through of them today， but you are more than welcome to go ahead and and check it out。

 example in this case， we will go and look at needle Z do cache data It's really back at end do end in this case。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_417.png)

Okay so that is the end of today's lecture。 Thanks everybody for coming。

 hopefully you' enjoy the walkthrough of the new back at the Ne library and it's going to be used as a backbone for your homework 3 and hopefully everybody enjoys doing that。

 And after homework 3， we really get a almost complete version of needle library that contains both automatic differentiation neural network implementations as well as the underlying endearing implementation that backs some of the GP acceleration and CPU acceleration code。

😊，Okay， so thanks folks， I will see you in the next lecture。



![](img/74d8e5ceeee6b46908d181b8f7c6a055_419.png)