# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p23 -24-24 - Machine Learning Compilation and Deployment Implementation.zh_en -BV1ERtYepEpy_p23-

Okay， well back to。Deep planning assistance， address implementation。 So hello everyone。

 we are getting close to the last lecture。SoIn this lecture。

 we going to do an implementation lecture on walking through some of the implementation content of the machine learning completion techniques we talked about in last week。

Of course， it's going to be。 a lot of those contents are adapted from the tutorials of Apache TVM。

 So if you want to learn more about TV and related topics， you're more than welcome to track TM。

 Apache do org。 There's another website called M O C dot AI。

That M O C dot AI that contains totals around machine learning compil and some of the latest development。

 So if you' are interested， you should also go and check out that website as well。



![](img/d66cb6f1b4baec2418909ffe906d90b7_1.png)

So to begin with we， we will try to obtain a version of TVM in Colab。

 we're going to use this piping store T O C pack nightly。

 So this a package that compiles some of the latest developments of TVM。

 and we're going to use this as demonstration purposes。



![](img/d66cb6f1b4baec2418909ffe906d90b7_3.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_4.png)

So in the last actually， we talk about the ability to be able to create。



![](img/d66cb6f1b4baec2418909ffe906d90b7_6.png)

loopop level program。And run transformations of the loop level program so that they could correspond to different performers。

And one of the things we are going to do now is we're going to go and try to build a group level program from what we call domain my specific language in here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_8.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_9.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_10.png)

So in this code block。What they try to do is we'll try to create。A computation that contains。

 you know， A and B are two input vectors。 and C is a resulting factor。 And in here。

 we are trying to add two vectors of land 128 together。

 and the computation is being described in here。And then we are going to call this column create prime prime function to get the overall functions。

 And actually and finally， you know， create a module that puts the corresponding function onto name。

 So let's see， you know what the result code looks like。😊。



![](img/d66cb6f1b4baec2418909ffe906d90b7_12.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_13.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_14.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_15.png)

So this is a code that is presented in a format called TBBM script。

And it representss corresponding computation that。That we have on this on this original computation describe。

 So we look at original code。 you find that we're trying to create a function with A。

 B and C as parameters。 right， So in this case， you can find that this particular function contains A B and C33 parameters in here。

 And go here as well and try to be able to create a set of loops that takes in the data from A and B and try to do additions and rise on C。



![](img/d66cb6f1b4baec2418909ffe906d90b7_17.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_18.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_19.png)

So the particular code is this is a pseudo code that looks quite like Python。 In this case。

 we will have iterations over a length of 128。 This formats for Ts I。

 so there will be some specialnotations of particular blocks of computation。And in this case。

 we are trying to effectively take I0， assign I0 to I and we running computation of C equals AI plus B okay。

So。This is the loop level program that we use to be able to build up the computation that takes in to。

To data and try to store that onto the C array here。

So we once we have this this called loop level programs。

 one thing we can do is we will be able to take that R module and try to generate a randomable function by calling build。



![](img/d66cb6f1b4baec2418909ffe906d90b7_21.png)

So in this case， we can call what we call TBMW by passing that IR module and a target in this case。

 by using LBM， which allows us to be able to generate efficient CPU targeting here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_23.png)

And it's going to return me a roundtime module here。

And this quantum module is going to contain a set of randomable functions。



![](img/d66cb6f1b4baec2418909ffe906d90b7_25.png)

So in this case， I'm going to do function equals R T module domain main because if you look at original code。

 this function is called main。 right It's going to suppose to taking three6， A and B and C。

 And what I'm going to do is going to read from A And B。

 I write on the say with this computing logics in here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_27.png)

And hopefully， you know， I'm going to pause a bit。Everybody can guess what's going on。

 right we have this original program that's being represented as this loop Pla Is that contains three inputs。

And a follow loop to compute， take the input computer output。

 And then what we can do is we will call a build to get a roundable function。

 and this is a function that we're going to import。



![](img/d66cb6f1b4baec2418909ffe906d90b7_29.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_30.png)

So this is a function called pack function。That is a special rundown function。That TBM support。

 So it is a function that's used to back。The final result of the compilation in here。

Once we have this pack function， once we can do it is。

 we can try to create a array and start to invoke computation of array arraysing here。So for example。

 I could be able to create aid。

![](img/d66cb6f1b4baec2418909ffe906d90b7_32.png)

And B， I'm going to create a C。 So in this case， C is the empty area。 So C can be arbitrary。

 So let's take block A。Retular a， you can find a is a range， you know，128 and。BS。That contains。

All the elements， one。 as if I'm going to look at CR now。



![](img/d66cb6f1b4baec2418909ffe906d90b7_34.png)

Youll find that， you know， it's quite random， right， this is because effectively， you know。

 we creating MPR from MP memory region。

![](img/d66cb6f1b4baec2418909ffe906d90b7_36.png)

And that particular memory can correspond to any of the data content。Okay。😊，So now。

 once we have both arrays， what we can do is we can go ahead and passing。



![](img/d66cb6f1b4baec2418909ffe906d90b7_38.png)

We， can try to try to try to call that function。 So the fact we can call this function passing A and B and C。

 So what's going to happen iss going to invoke that particular compile function that we have。



![](img/d66cb6f1b4baec2418909ffe906d90b7_40.png)

So in this case。This particular function describes a B and C。

 and it' going to run this particular computation in here。So when we call this function effectively。

 we are passing in， right， the array A to here。Are I be here。And I already here。

 and it's going to read data from A And B and write on to C。 So supposedly。

 if we invoke that particular function。The result， the C array is going to contain a final computing result。

Okay。

![](img/d66cb6f1b4baec2418909ffe906d90b7_42.png)

So。Let's go and take a look here。

![](img/d66cb6f1b4baec2418909ffe906d90b7_44.png)

You can find in this case， a ch one to 0，1，2，3，4， B， ch one to all was。



![](img/d66cb6f1b4baec2418909ffe906d90b7_46.png)

And see Chrisma into the final computer result。 So it's kind of about a course experience of。

 you know， trying to take a loop level program being represented in I module。

 build that and then invoke ch function using。

![](img/d66cb6f1b4baec2418909ffe906d90b7_48.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_49.png)

Youll find that overall process is pretty simple in some sense， right， we effectively。

 we build I module that contains a function definition。 You obtain that function in here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_51.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_52.png)

And then once you obtain the function， you allocate the crisp arrays。



![](img/d66cb6f1b4baec2418909ffe906d90b7_54.png)

And you do the correspondingvocation of function ABc that gives you the final result here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_56.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_57.png)

OK。😊。

![](img/d66cb6f1b4baec2418909ffe906d90b7_59.png)

So this is the basic approach that allows us to be able to start。

I would say take a program and trying to be able to take a program。

 trying to be able to build and write。

![](img/d66cb6f1b4baec2418909ffe906d90b7_61.png)

On that hand。What's been more interesting for us to be able to take a program trying to transform it bit。

And in order to do that， let's create。

![](img/d66cb6f1b4baec2418909ffe906d90b7_63.png)

Instant called schedule。And the schedule is， is a helper function。

 helper class that allows us to run transformations on the code。

 So we know that our original IR module。没系啊。Can be seen as。



![](img/d66cb6f1b4baec2418909ffe906d90b7_65.png)

This is original code， right？ And one of the things we want to do is we want to be able to。You know。

 do some loop transformations。Specifically， one thing we can do is can try to split the loop I。

In order to do that， the first thing I want to do is I will kind of try to get a blog。

That allows me to do S。老s。This can see。It's going to give me a block in here。们去。

Put it up so that we can still see the code。During the transformation。This is original air module。



![](img/d66cb6f1b4baec2418909ffe906d90b7_67.png)

And it will get a block。 after I get a block， what I can do is I can do。The original loop， because。

Yeah。Loops。Of their blocks。effectivelyect， this API is going to try to look at the block and try to look up all the corresponding loops in here and unpack that。

 So it's gonna gives you a array。 So I'm going to unpack it by this。



![](img/d66cb6f1b4baec2418909ffe906d90b7_69.png)

Okay。And then actually， I'm going to copy the schedule creation so that I will be able to。



![](img/d66cb6f1b4baec2418909ffe906d90b7_71.png)

Right， just run。 this code block along。

![](img/d66cb6f1b4baec2418909ffe906d90b7_73.png)

是。

![](img/d66cb6f1b4baec2418909ffe906d90b7_75.png)

So after we get the loops。Or we can。 we can go and split it。 So let's see I can do， you know， I 0。

I won。Equs S AH dot split。Its loop of eye， and the factory is。诶。No。More。Okay。And after I do this。

 I will be able to do S dot Mo dot show。

![](img/d66cb6f1b4baec2418909ffe906d90b7_77.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_78.png)

And you will find that I'm going to get another looping here。 right， So effectively， what。

 what its tried to do is to try to do a sequence transformations。



![](img/d66cb6f1b4baec2418909ffe906d90b7_80.png)

And the result is being stored in this SS do mode member here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_82.png)

Okay。She方 ever don't do anything。

![](img/d66cb6f1b4baec2418909ffe906d90b7_84.png)

This is our original loop。In here。And effectively in here。

 what we are doing is we are trying to split right， this entire loop into two loops。

 you can find that， you know， the original loop is being split by 32 by 4 in here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_86.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_87.png)

And。AndThe original axis mapping is still going to contain I。 right now。

 this t do x spatial means that this I is going to be mapped onto I 0，0 plus times 4 plus I 0。

1 times 1 here。That is my final result。So you're going to find that in this case。

 after this transformation， right by running this transformation。

 we'll be able to get a different variance of program。

 And I can go ahead and try different things but I'm hold lot the things I can try as I can see if I change it to8。

😊。

![](img/d66cb6f1b4baec2418909ffe906d90b7_89.png)

You'll find that this effect of this loop。Iterator get changed。 right。

 So if I run this program using different set of schedule transformations。

 I' mean look at a different variant of an underlying program。

This kind of transformation drivenven language is very powerful because it allows us to effectively re the loop nest。

 by running those APIs without having to write the program。

 So in matter like how we normally would do such kind of code transformations what you normally do is you just copy paste the code right and then do some of the manual refrauring。

 which can be very tedious in this case， by having this， you know。

 of effectively program based transformations will will be able to go ahead and you know。

 transformal program different ways。

![](img/d66cb6f1b4baec2418909ffe906d90b7_91.png)

So up here now， well talk about loop splitting。 So there are other ways other than loop splitting。

 For example， one thing I can try to do is I can try to do reorder。路怕。In here。

 so output split the loop， let's go to reorder this original program。 and reorder it。

 we can find that， well， it's the same order， but I can try to go ahead and do I1 and I0。



![](img/d66cb6f1b4baec2418909ffe906d90b7_93.png)

Try again。And you can point that effectively the order of loops changes。

So that's another another way for us to be able to transform a program。Of course。

 there are other ways that we can go for example， I could try to paralyze along certain dimensions by running S A Hdot parallel dot I 0。

Actually， I can do I one out loop dimension。

![](img/d66cb6f1b4baec2418909ffe906d90b7_95.png)

Around that， you can find that effectively try to paralyze out loop dimension as an internal sequential loop。

 And heres a different part of original program。So what we take away here is that by having those pragmatic transformation APIs。

 we'll be able to take original program， right。

![](img/d66cb6f1b4baec2418909ffe906d90b7_97.png)

Use these， what we call schedule transformation parametersitives to allow us to manipulate this loop nest in different ways and as a result。

 different loop nest can result in different performers different performance code and all the ways that allow of automatic program optimization doing if they will try to go ahead and try all different variants of program transformations and then try to find a high performing ones among the set of choices out there。



![](img/d66cb6f1b4baec2418909ffe906d90b7_99.png)

开。

![](img/d66cb6f1b4baec2418909ffe906d90b7_101.png)

So we go through some of these transformations that we had before。Now。

 let's start to think about the more complicated programs。 Imagine that， you know， hey。

 you want to do measure its publication， okay。

![](img/d66cb6f1b4baec2418909ffe906d90b7_103.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_104.png)

So。In a case， I'll major some indication。

![](img/d66cb6f1b4baec2418909ffe906d90b7_106.png)

One of the things that we want to do in here is let's try to define a matrix communication program。不。

And then trying to go ahead and build that the vanilla matrix some location。



![](img/d66cb6f1b4baec2418909ffe906d90b7_108.png)

Okay， so it can be a bit long， but let me walk you through each line here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_110.png)

So first four， we're going to try to create a describe the matrix exploration code as。

 you know want to get go into the reduction of work K。 There are two inputs。



![](img/d66cb6f1b4baec2418909ffe906d90b7_112.png)

A B as a placeholder and six computation equals you know， AM M K times B KM here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_114.png)

And we， we are going to iterate over， you know，1 thousand24 over 1 thousand24 over 102。



![](img/d66cb6f1b4baec2418909ffe906d90b7_116.png)

So if we go ahead and do that and try to create the module in here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_118.png)

关曲。I to create a different code blocks so we can clearly see what the code looks like。



![](img/d66cb6f1b4baec2418909ffe906d90b7_120.png)

是哦。

![](img/d66cb6f1b4baec2418909ffe906d90b7_122.png)

If they go and do that。嗯。And we we are going to create a function here， right that contains。

AB and C S arguments。I think do。I am module a show。



![](img/d66cb6f1b4baec2418909ffe906d90b7_124.png)

So this is effectively a matrix of religion program that contains A， B and C。As three arguments。

 pretty allocated。And what I try to do is trying to iterate over three iterators。

 and then they will try to effectively map three theators to M and K。And run this iteration normally。

 run this reduction。So this is syn test called Tens IR。

 so there are some special meanings in this program。effectivelyffectively describe a reduction。

 So one of the things you might notice is that in this program。



![](img/d66cb6f1b4baec2418909ffe906d90b7_126.png)

There's a， there's this called Exor remap。If the says that the effectively means M in here equals I 0。

N here equals I 1 and K here equals I 2。 So it's just assignment。 but also creates annotation。

 So this S， SR means that the M and K are what we call spatial x so that they are effectively。

 they assign in corresponding to the。Locationations of the A areas。 Well， the key here。

 Chris will call a reduction。Reduction axis or reduce axis because， you know。

 we are trying to accumulate over， okay。And in here。

 the t dot in it actually crisp point to the condition where effectively if if we encounter this loop for the first time。

 it's going to initialize the crisp morning locations using you know zero。

 otherwise it's going to do this accumulation operation here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_128.png)

So this is the IR module that we can create by running this is what I called cancer expression domain specific language that describes a matrix of location and creates the ch functions。



![](img/d66cb6f1b4baec2418909ffe906d90b7_130.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_131.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_132.png)

So after we have this tensor expression language and crisp volume functions。



![](img/d66cb6f1b4baec2418909ffe906d90b7_134.png)

One of the things that we can do is we can try to go ahead and build it。

And try out the corresponding executionion efficiencies。



![](img/d66cb6f1b4baec2418909ffe906d90b7_136.png)

So we already have code to do it。 And here， so I'm just going to copy the code。



![](img/d66cb6f1b4baec2418909ffe906d90b7_138.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_139.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_140.png)

So effectively， first of all， it's going to go and try to build。The IR module。In this line。

I we build it， we're going to create。3 array， right。

 We are going to create two random array of initialized by random number and a C array。I。

 we could also try to go and confirm that if the implementation correct。

 So I'm going to create a lump equals。狼排的reon。也。一南排阔。Now we are going to create a nu A。

And B high in here say in here。 Okay， and we can go ahead and invoke this。So。

We're going to invoke this array。 It's going to store the result on the C。

 so we can try to compare C dot N。

![](img/d66cb6f1b4baec2418909ffe906d90b7_142.png)

嗯。A男排。In this case， AM M K times B Nampai major civilization location。



![](img/d66cb6f1b4baec2418909ffe906d90b7_144.png)

Have you run this。You know' I be able to find that。



![](img/d66cb6f1b4baec2418909ffe906d90b7_146.png)

Well， it's a very small number most of the things are zero because they are very close to each other。

 that means that you know yes， it's indeed implementing things correctly。



![](img/d66cb6f1b4baec2418909ffe906d90b7_148.png)

Another thing that we can do is we can try to call function do to。Evaluator。And in this case。

 it's trying to evaluate it will give me an evaluator。That allows me to evaluate time。

 So I wont be able to do evaluator A B。

![](img/d66cb6f1b4baec2418909ffe906d90b7_150.png)

I think there are other arguments to tell me about later。



![](img/d66cb6f1b4baec2418909ffe906d90b7_152.png)

K。So， that's a device。And numberer equals 3。 So it。

 this means that we're going to run it three times recall the averaging here。嗯。比赛。Hco。



![](img/d66cb6f1b4baec2418909ffe906d90b7_154.png)

云。So it's going to take a bit of a challenge to run the evaluation。And after runs。

 you'll find that it will tell you effectively how long is it。Okay to run this。 I think in this case。

 we have not do any transformation。 right， so it， it takes about three seconds。 So it's， it's a。

 it's a unit of7。 So you can find。 It takes about 3。71 second。



![](img/d66cb6f1b4baec2418909ffe906d90b7_156.png)

Okay。

![](img/d66cb6f1b4baec2418909ffe906d90b7_158.png)

So now we have this original program， of course， one of the key things we can try to do is we can try to reorganize the loop a bit。



![](img/d66cb6f1b4baec2418909ffe906d90b7_160.png)

So in this case。啊。

![](img/d66cb6f1b4baec2418909ffe906d90b7_162.png)

I'm going to do。I soon come up to my living coat tiling。



![](img/d66cb6f1b4baec2418909ffe906d90b7_164.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_165.png)

So what you can do is you can first go ahead and create a schedule。You'll get surrounding your loops。

 So remember that。

![](img/d66cb6f1b4baec2418909ffe906d90b7_167.png)

I first got a block， C。

![](img/d66cb6f1b4baec2418909ffe906d90b7_169.png)

And then we'll be able to get the surrounding loops。



![](img/d66cb6f1b4baec2418909ffe906d90b7_171.png)

It case。

![](img/d66cb6f1b4baec2418909ffe906d90b7_173.png)

If you look at the original code。哎呀，猫就的受哦。

![](img/d66cb6f1b4baec2418909ffe906d90b7_175.png)

Now original code contains three running loop， right， So I 0， I1， and I 2。

 I'm going to get block thing here。

![](img/d66cb6f1b4baec2418909ffe906d90b7_177.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_178.png)

Get I'm going to re name as Y X King here。 And then I'm going to try to do equally blocking。

 So effectively I'm going to split the Y and x， I'm going to reor it by a while X O K， Y X I。

 So if you have learned about some of our previous lecturers might get familiar with。

 it's a bit like a register register blocking in this case。



![](img/d66cb6f1b4baec2418909ffe906d90b7_180.png)

Go around it。 You can find that effectively。 we are splitting the loops。 right now。

 the loops become5。

![](img/d66cb6f1b4baec2418909ffe906d90b7_182.png)

Dops， instead of qua loops。Where is this。2 of outer loop and inner loop get split onto two loops component that gets spread in outputer and inner。

And we'll still get a reduction dimension K here。

![](img/d66cb6f1b4baec2418909ffe906d90b7_184.png)

Okay。

![](img/d66cb6f1b4baec2418909ffe906d90b7_186.png)

So we can try to go ahead and try and see， you know， what are the possible。

Speed up that you might get using this implementation。 so can go and build it again。

A run a tell about later。Otop after transformations。



![](img/d66cb6f1b4baec2418909ffe906d90b7_188.png)

Yeah point out in this case。I just split a loop a bed。



![](img/d66cb6f1b4baec2418909ffe906d90b7_190.png)

Well get quite decent speedup， right， You get a three point。 By the way。

 this schedule mode is the module after the transformation。

 you can find that we are reducing the over running time from。Almost 3 seconds on to 0。

3710 times faster。 than original computation。 So that tells you like no。

 if you go and change your loop optimize organizations a bit where you can get quite a bit of speedups。

 actually， in this case。

![](img/d66cb6f1b4baec2418909ffe906d90b7_192.png)

And another thing we can try to do is， you know， maybe let's go and try different configurations in here and see what's going on。



![](img/d66cb6f1b4baec2418909ffe906d90b7_194.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_195.png)

So。Let's see。 I'm going to。

![](img/d66cb6f1b4baec2418909ffe906d90b7_197.png)

就。De find。And small。Moju。稳仲 get。Sa太 why。IX。Create a schedule， get a blog。loops。

Don't need this anymore。嗯， why。好X。The looktels。嗯， return天。The transform module in here。

So one thing we could do right in here is we can try to。



![](img/d66cb6f1b4baec2418909ffe906d90b7_199.png)

Get。茉力波。哇。Original I am module。The original private is 32 by 32。嗯。

But we could try different eras here so。啊屎谂条。To long means it should be similar to the original one。

 given that we are just transforming original modules by 32 by 32。



![](img/d66cb6f1b4baec2418909ffe906d90b7_201.png)

嗯。Let's see。 Oh， I just split it， but didn't reorder it so。The order。嗯嗯。买哦。



![](img/d66cb6f1b4baec2418909ffe906d90b7_203.png)

X O KY I。哎。

![](img/d66cb6f1b4baec2418909ffe906d90b7_205.png)

ro this。Right again。Hang up， you can hang a straight point。7，6，7，7，6， right， so。

What if I try to do it in4 by4。You're going to get a different speed， right， this sc floor。

So what if I'm gonna try to do it by 4 by 32。You can find that， you know。

 depends on the ways we are going to change the iterations。

 it's going to give us different kind of execution speed。

Another thing I can go do go and doing is focus on code。And collapse。

 I'm not sure if it's going to give me parallel， but let let me try。 So if I'm going to paralyze it。

Well， seems that parallel computing is not working in here because。Likely。

 the coldab environment is only giving a single virtual CPU。I suppose to。Many merchant C。Okay。😊。

So anyway， so we will be able to run the code transformation。

 try all different configurations that gives us a different variance of programming here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_207.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_208.png)

And each variant on the program is going to have a execution efficiency。

 So one very natural thing that people can try and do is people will be able to try out different variants of program configurations。

😊，And then benchmark the executionion efficiencies of each program variances and pick the best one。

 So that is effectively how most of the automated search framework works。

 So that allows you to be able to take the original program。

 build a setup transformation that gives you know different variants and programs。



![](img/d66cb6f1b4baec2418909ffe906d90b7_210.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_211.png)

Around the benchmarking or a tight environment。And use that to build a set of training data that helps you to predict the potential cost of particular program configurations。

And then use that potential cost to further narrow down the program element。



![](img/d66cb6f1b4baec2418909ffe906d90b7_213.png)

Okay。😊，So besides this， there are other optimizations that we don't have time to talk about。

 but if are interested you should go and check out this machine learning compilation course called Mc。

AI that contains more comprehensive tutorials on all the contents we learned about today。

 including the Tensor IR and set of transformation you will be able to do on top of this。



![](img/d66cb6f1b4baec2418909ffe906d90b7_215.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_216.png)

Okay， so that that is， you know， the loop level programs。

 How can we run the transformation API to build the loop level program。Moving' be next？

Let's quickly look to what end to end model deployment might look like in a machine learning comp。



![](img/d66cb6f1b4baec2418909ffe906d90b7_218.png)

So in this case， were going to use TBBM's a comp module called relay。



![](img/d66cb6f1b4baec2418909ffe906d90b7_220.png)

And the first thing I're going to do is we're going to go ahead and download a RethNe 18 module from the Torch visionion library。



![](img/d66cb6f1b4baec2418909ffe906d90b7_222.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_223.png)

And we're going to use a plot script to trace it onto a local variant。



![](img/d66cb6f1b4baec2418909ffe906d90b7_225.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_226.png)

Then what we're going to do is we're going to also download the image we're going to use and run some of the pre preproing to be able to convert this image onto a torch tensor that we're going to use in here。

 and this is an image that we' are going to use for our deployment workload。



![](img/d66cb6f1b4baec2418909ffe906d90b7_228.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_229.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_230.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_231.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_232.png)

Okay。Once we have this。What we are going to do is effectively the first steps in employee。

 So that in relay as a function called。From Pytorch that allows us to be able to take a torch script module and then let's stop input shapes in here。

And it's going to be able to give me a module that correspond to the end neural network computation。



![](img/d66cb6f1b4baec2418909ffe906d90b7_234.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_235.png)

after we get the module， we'll be able to look at it。

 And you can find that effectively its corresponds point to a sequence of operations such as。

 you know， convolutions， ba and Ralu and so on。 So these are sequence of operations that we are going to use to to implement neural network。

 you can also find that second operations contains quite a lot of the。



![](img/d66cb6f1b4baec2418909ffe906d90b7_237.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_238.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_239.png)

Parameterters， right as you know， these are input parameters on through this convol neural network。



![](img/d66cb6f1b4baec2418909ffe906d90b7_241.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_242.png)

Okay。So once we have this relay module， we can do in this case。

 we're going to call a function called relay do build。



![](img/d66cb6f1b4baec2418909ffe906d90b7_244.png)

Let's build this computational graph。It's also going to go ahead and run all the processes。

 lower some of the computations onto the loop program， run loop generations。

 which in our previous case， right take some part of computations and transform them onto libraries and then also build an interpreter that allows us to be able to go ahead and run the corresponding and run an interpreter allows to interpret that final generated graph module。



![](img/d66cb6f1b4baec2418909ffe906d90b7_246.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_247.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_248.png)

Okay。So after we get this library。

![](img/d66cb6f1b4baec2418909ffe906d90b7_250.png)

What we can do is we can go and build a module called the graph Xer。So in this case。

 the graph excutor is going to give us a computational graph version allows us to create that allows us to do things like you know set input array where this input array crs point through the input image that we're going to use our prediction and we're going to call run that give me that run executionions and then finally you can get output to run that to get that output。



![](img/d66cb6f1b4baec2418909ffe906d90b7_252.png)

What we next what can do is we can try to see if the prediction matches what we are expecting。



![](img/d66cb6f1b4baec2418909ffe906d90b7_254.png)

When here， we are going to download the imagenet syn that that corresponds point to the class labels of each of the。



![](img/d66cb6f1b4baec2418909ffe906d90b7_256.png)

Each of the label class in here。

![](img/d66cb6f1b4baec2418909ffe906d90b7_258.png)

We obtaintain image about classes。And then gets the dictionary that correspond more into class to ID。

And then the output is going to be 128 dimension vector in here。 So we're going to take R connects。

That gets the class class index。 and then we're going to translate the class index located key in here。



![](img/d66cb6f1b4baec2418909ffe906d90b7_260.png)

And if you run it， you cant find that prediction is taby cat。



![](img/d66cb6f1b4baec2418909ffe906d90b7_262.png)

You look at original。Image。That we had。

![](img/d66cb6f1b4baec2418909ffe906d90b7_264.png)

你是。It indeed looks like a tab cat。 right， So that gives you a high level overview of overall process of。

 you know what it looks like in terms of running M deployment through a machine learning compilation。



![](img/d66cb6f1b4baec2418909ffe906d90b7_266.png)

Of course， you know， there are more interesting things you can explore， such as， you know。

 what are the internals in terms of if we inest the model， how do we run transformations。

 how do we map some of the computations onto the loop level program。

 and how do we automatically optimize those loop level program。



![](img/d66cb6f1b4baec2418909ffe906d90b7_268.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_269.png)

We don't have time to cover that in today's class， if you're interested again。

 if you go to this website called M Oc。 AI。

![](img/d66cb6f1b4baec2418909ffe906d90b7_271.png)

![](img/d66cb6f1b4baec2418909ffe906d90b7_272.png)

M O C dot AI， there are additional materials about machine learning comp that you that can help you to learn in a more organized fashion about this entire talk。

Okay。

![](img/d66cb6f1b4baec2418909ffe906d90b7_274.png)

So that is the end of today's lecture， thanks everybody for coming and building with us throughout this amazing journey of building deep learning systems from scratch。



![](img/d66cb6f1b4baec2418909ffe906d90b7_276.png)