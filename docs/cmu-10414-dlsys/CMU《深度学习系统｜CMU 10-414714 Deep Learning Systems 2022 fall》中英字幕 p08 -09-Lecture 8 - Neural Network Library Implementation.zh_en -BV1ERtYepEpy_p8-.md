# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p08 -09-Lecture 8 - Neural Network Library Implementation.zh_en -BV1ERtYepEpy_p8-

Okay， hellello， well。 We back to D systems action implementation。 So this is lecture 8。😊。

In today's lecture， we're going to walk you through on some of the detailed implementations of neural networks through our iPad notebook and it's going to cover a lot of the contents of specific implementations of what we discussed in the last lecture。



![](img/072ef523f9f644aa75180307e72efe95_1.png)

Again， this is going to be an implementation section。

 So I'm going to use iPad and notebook instead slide to walk you through some of the specific content here。

As a first app， you will need to run this code block。



![](img/072ef523f9f644aa75180307e72efe95_3.png)

In here。 So if you write for the first time， you want to un this particular code block that clones up this lecture8 rap onto your local。

 And then after that， you will be able to do some of a local modifications to continue right。

 And in the next time， you can just comment this so that you will get kind of a persistent drive of needle rap in here。

 and we can take a look on the right hand side that is already needle being cloned in here。



![](img/072ef523f9f644aa75180307e72efe95_5.png)

![](img/072ef523f9f644aa75180307e72efe95_6.png)

And this is going to be the code that we're going to use for today's lecture。



![](img/072ef523f9f644aa75180307e72efe95_8.png)

So if you have in the future， we're gonna release homework2 and the same rapple can be used。

 you can also use this homework through repple for completing this piece of code。

 Another thing I want to mention today is that for this lecture。

 I do have a readily implemented automatic differentiation of needle。

 So if you want to but the lecture age rapple do not contain a implementation。

 So you will need to copy and paste your own implementation of automatic differentiation on to put the corresponding volume file in order to run some of this demonstration in here。



![](img/072ef523f9f644aa75180307e72efe95_10.png)

![](img/072ef523f9f644aa75180307e72efe95_11.png)

![](img/072ef523f9f644aa75180307e72efe95_12.png)

So before we get started， let's first do a bit of refresh of needle since lecture 4 and homework 1。

 So we know that in all cases， we will be able to you know define needle tensor in here。

 and here W is a needle tensor。

![](img/072ef523f9f644aa75180307e72efe95_14.png)

![](img/072ef523f9f644aa75180307e72efe95_15.png)

And one of the things we want to quickly go over is how do we。

 how can we go and update weight in neural network training and you know。

 a lot cases we talk about how can we do you know， forward neural network computations。

 as well as taking gradient research certain parameters。



![](img/072ef523f9f644aa75180307e72efe95_17.png)

![](img/072ef523f9f644aa75180307e72efe95_18.png)

But once we have those gradient， there's always a question of how can we go ahead and update the weight values according to the gradient or according to some stochastic gradient update rules。

 So let's try to do that。

![](img/072ef523f9f644aa75180307e72efe95_20.png)

![](img/072ef523f9f644aa75180307e72efe95_21.png)

Assume that now we have a weight vector here has W and gradient vector here S G。

 And one thing we can do is we can go ahead and you know， first of all， check。



![](img/072ef523f9f644aa75180307e72efe95_23.png)

![](img/072ef523f9f644aa75180307e72efe95_24.png)

The weight vector in here， we can find that， you know， by default。

 when we create a needle cancersor in here， they require gradient field。

Of this needle tensor equals true。 That means that。You know。

 we are actually tracking the computational graph and gradient as we in order to compute gradient as we start to run some of computations。

 So let's assume that we're going to run us to a gradient step for for several steps。

 So one thing we can do is we will be able to say take a gradient vector we can take a learning rate and run this for here。

😊。

![](img/072ef523f9f644aa75180307e72efe95_26.png)

![](img/072ef523f9f644aa75180307e72efe95_27.png)

![](img/072ef523f9f644aa75180307e72efe95_28.png)

What this followed does is effectively we run install category and discent operations。

And one of the things is they want to。Noting here is that， you know。

 I'm doing like negative learning rate。 So this is because the lecture H rap itself is does not contain the subtraction operator。

 But， you know， if you have already implemented as part。 if you need a rapple。

 you will be able to actually go ahead and directly write W equals sub W subtracting learning rate times gradient。

 So as a still category in W。

![](img/072ef523f9f644aa75180307e72efe95_30.png)

As we talk about in last lecture。There's one problem with this particular implementation。



![](img/072ef523f9f644aa75180307e72efe95_32.png)

![](img/072ef523f9f644aa75180307e72efe95_33.png)

So what is the problem？The problem is that every W itself， actually。

Contains a competition because W have this required gradient field being written。AlSo， so， you know。

 we can look at W dot operator。 In this case， W dot operator correspond to element wise a。



![](img/072ef523f9f644aa75180307e72efe95_35.png)

![](img/072ef523f9f644aa75180307e72efe95_36.png)

And we can also go ahead and look at w do input。

![](img/072ef523f9f644aa75180307e72efe95_38.png)

Which is another。Needle dot， which is not a needle value。

 And you can find that also Chris want to analyze that。

 you can even go ahead and trade know W dot input dot input dot。



![](img/072ef523f9f644aa75180307e72efe95_40.png)

![](img/072ef523f9f644aa75180307e72efe95_41.png)

So what's happening。So what's happening is that， you know， in every iteration， right。

 we are creating， So whenever we are doing these operations。

 we are creating a computationalal graph node。😊，That whose operation is otherwisewise at right。

 And then we are saying that， we need to do W plus。

 And this is learning array times negative learning array times gradienting here。

And we do another plus operation here， another thing here。 So effectively。

 we are creating this train of computational graphs as we start to go ahead and write this way up the rules。

😊。

![](img/072ef523f9f644aa75180307e72efe95_43.png)

![](img/072ef523f9f644aa75180307e72efe95_44.png)

And then， you know， in the end， the W， we kind of holds。



![](img/072ef523f9f644aa75180307e72efe95_46.png)

And the， the end of communication graph。 So， of course， in this case。

 we do get the latest value of W。

![](img/072ef523f9f644aa75180307e72efe95_48.png)

But what is the problem of this approach？The problem is that， you know。

 this particular W also takes the computational graph trace of all those previous computations。

 right， So this is kind of like a common bug that sometimes you know。

 people encounter when you write programs in Py。Im that you're doing iterations over several。

 you know， you are doing since accumulating your loss across several iterations。

Then these kind of competition traces kind of accumulate。



![](img/072ef523f9f644aa75180307e72efe95_50.png)

As a result， the memories of those previous。Graadianient。As a result， you know。

 usually those gradient also contains like an input computational graph， your computer gradient。

 As a result， all those input computational graphs。😊。



![](img/072ef523f9f644aa75180307e72efe95_52.png)

Get retained through this reference。Of W。 and they cannot get released。 So each iteration。

 the memory cost of， of the entire process kind of grows linearly as as the number of iteration grows。

 as a result， you will get auto memory error。 If you write code in this way。

 this kind of like a one of a common bug that you can encounter by writing programs in like an imp development differentiation framework。

Okay， so how can we avoid this。

![](img/072ef523f9f644aa75180307e72efe95_54.png)

So instead， what we really want is， you know， we don't really want。



![](img/072ef523f9f644aa75180307e72efe95_56.png)

We， we don't really want。To。Do these updates while keeping track computation graph。

 Remember that why do we need computational graph be track。

The reason is that we need computational graph to be able to help us to perform the reverseersal automatic differentiation。

 right， so because we know that we might want to compute the gradient with respect to some of the inputs。

 So we want to be able to， you know， build up computational graphs to help us to to track the reversal automatic differentiation。

However， for the weight updates， we know that。Most locations cases we don't care about differentiating with to the weight update rules。



![](img/072ef523f9f644aa75180307e72efe95_58.png)

So as a result， we don' need to compute， we don't need to track the computational graphs。



![](img/072ef523f9f644aa75180307e72efe95_60.png)

So instead， we can try to create what we call detached cancer。In this case， you know。

 W dot data is also a short shortcut for W dot detach。

 which create a detached tensor that create the same content。

But do not contain the corresponding computational graph attached to them。



![](img/072ef523f9f644aa75180307e72efe95_62.png)

So if you look at W dot data don't require gradient。



![](img/072ef523f9f644aa75180307e72efe95_64.png)

诶。Become a force， right， and and this。So what's behind harnessing this data？

We can go ahead and open up the code。

![](img/072ef523f9f644aa75180307e72efe95_66.png)

Often移。And take a look at what's happening here。

![](img/072ef523f9f644aa75180307e72efe95_68.png)

![](img/072ef523f9f644aa75180307e72efe95_69.png)

So if you look at this file。

![](img/072ef523f9f644aa75180307e72efe95_71.png)

And we scroll down。

![](img/072ef523f9f644aa75180307e72efe95_73.png)

To。

![](img/072ef523f9f644aa75180307e72efe95_75.png)

![](img/072ef523f9f644aa75180307e72efe95_76.png)

The w dot data， you can find that。The data function， I simply cause。



![](img/072ef523f9f644aa75180307e72efe95_78.png)

Simply call help到 detaach。

![](img/072ef523f9f644aa75180307e72efe95_80.png)

Where the detach function。Causet tendom make cost。Hel not realize cache data。 Okay。

 so what's happening is actually， is creating a new tensor。That shares underlying cache data。 So。

 so it's not， we are not copying a new ten。 Were creating a new ten that shares the same underlying memory。

With respect or original W。Except that we are removing all the additional view。

 such as inputs and and up field from that particular data that help us to be able to， you know。

 effectively cut down the computational graphs。 So we can also go ahead and take a look in here。

 right， So if you look at。😊。

![](img/072ef523f9f644aa75180307e72efe95_82.png)

![](img/072ef523f9f644aa75180307e72efe95_83.png)

谁。

![](img/072ef523f9f644aa75180307e72efe95_85.png)

So if look at here。And I can try to say。They equals。W data。And let's check， you know， they dot up。

You find that in this case， thet app op actually is now。So you can verify that it's true。

 They don't all now。 So it does not contain op。

![](img/072ef523f9f644aa75180307e72efe95_87.png)

That does not contain inputs。This input empty， right， So， and if you look at， well， it。

 it does contain a cache data。And you find that actually， this cache data field actually is W not。

Cash data as well。 So they do share the underlying data representationations。As a result， you know。

 we are not doing like a deep copy of memory。哎。So you want to perform updates。

 What we can see is we can say instead， you know， now， new W equals W dot data。

 negative learning rate times gradient dot data。 So if we run this。



![](img/072ef523f9f644aa75180307e72efe95_89.png)

And find that I'm going to get a new W value in here。



![](img/072ef523f9f644aa75180307e72efe95_91.png)

In this case， because both W do data and gradient do data are detached。

 we no longer attach a computational graph to them。



![](img/072ef523f9f644aa75180307e72efe95_93.png)

So if you look at required gradient field of this new W。

 you can find that it creates one to force as opposed to true。

 So the the rule that were having here is actually if in eager mode。



![](img/072ef523f9f644aa75180307e72efe95_95.png)

And we are doing ourm computations。If all the inputs do not require gradient， then by default。

 we will not construct an attached sensor that contains a communication graph to automatically create a detached sensor。

 as a result， we can find new w dot inputs also equals empty right so we can also go ahead and track the code that leads to this piece of logic。



![](img/072ef523f9f644aa75180307e72efe95_97.png)

![](img/072ef523f9f644aa75180307e72efe95_98.png)

![](img/072ef523f9f644aa75180307e72efe95_99.png)

If you look at。

![](img/072ef523f9f644aa75180307e72efe95_101.png)

Here we can find that。 Let me see if it's tensor dot make。



![](img/072ef523f9f644aa75180307e72efe95_103.png)

There this is value。 And there is also a。

![](img/072ef523f9f644aa75180307e72efe95_105.png)

![](img/072ef523f9f644aa75180307e72efe95_106.png)

Tsor dot make from up。 So in here， if it's not in lazy mode。 And if in the end。

 if tensor does not require gradient， usually if tensor does not require gradient when initialize it will track if all the inputs require gradient。

 If any of them require gradient， then this canceror will require gradient。



![](img/072ef523f9f644aa75180307e72efe95_108.png)

If it does not require a gradient， what we can do is we can simply create a detached version of the cancer。

That effectively runs the computations and ignore the underlying。

 ignore the previous attached computation graph。 So why does detached pencil more preferred in this case。



![](img/072ef523f9f644aa75180307e72efe95_110.png)

The reason is that， you know， in lot of cases， if you attach the computational graph。

 along with your computations， you hold references to those previous computationalal graph node or those value node。

 As a result， these value wouldn't get released until。You know。

 all the previous reference to that value get released。 right so in this case。

 we could end up having a longing of references where a lot of memories that could have been released didn't get released beforehand。

 So as a result， know， when you are trying to build some of computations。

 always ask yourself whether or not， you know， you can try to not recording computational graph。😊。

In Pyto， there's also a context of stop gradient or no gradient that does the that serve similar purposes here okay。



![](img/072ef523f9f644aa75180307e72efe95_112.png)

So besides creating a new w， it's actually helpful to directly try to update Ws font in place with。

 This is because in one of cases， you know， the W is being already referenced as we will see in the later part。

 they are being referenced as part of the parameter fields。

 So it's helpful to directly go ahead and update their values as opposed to create a new variable that then。

 you know， get updated onto the ch morning content。



![](img/072ef523f9f644aa75180307e72efe95_114.png)

So in order to do that， we can do W dot data equal。So effectively。

 you can try to have a set that sets onto to W do data。 And in this case。

 simply copies the Christmas data content on the new W。 Thank you。



![](img/072ef523f9f644aa75180307e72efe95_116.png)

![](img/072ef523f9f644aa75180307e72efe95_117.png)

And if you look at W again， you'll find that in this case， you know。

 the the W actually indeed crisps one to the new updated weights， right Thank you。



![](img/072ef523f9f644aa75180307e72efe95_119.png)

![](img/072ef523f9f644aa75180307e72efe95_120.png)

So this is the way that we normally use。To will write our weight update。



![](img/072ef523f9f644aa75180307e72efe95_122.png)

Okay。So now we have talked about the a refreshment of needle and how we can go ahead and use this in place mutation。

 We can try to be able to take a detaach sensoror， perform operational on them， which again。

 creates a detached sensoror and in place late mutate some of the weight variables in here。😊。



![](img/072ef523f9f644aa75180307e72efe95_124.png)

As the next step， let's start to take a look at another thing that's going to be helpful here in building your homework too and building some modules that have to do is the numerical stability。



![](img/072ef523f9f644aa75180307e72efe95_126.png)

![](img/072ef523f9f644aa75180307e72efe95_127.png)

![](img/072ef523f9f644aa75180307e72efe95_128.png)

So in most cases， and you might have noticed already。 like if you look at here。

 you can find that after several steps of update。 We are getting these values like 0。3999992， right。

 Well， effectively， every time we are all we are doing is we are trying of subtracting 0。1 here。

 So effectively， it should have been 0。4 if Im in this case， you should have been 0。4。

 as opposed to 0。999992。 So why does that happen。

![](img/072ef523f9f644aa75180307e72efe95_130.png)

This is because we are not， you know when， when we're sting the data on， on memory， right。

 We're sting them through a format called floatinging point number。



![](img/072ef523f9f644aa75180307e72efe95_132.png)

In this case， the floatinging point numbers have limited precision， right。

 So usually a firm point number contains two parts。 That's what call9 apart。



![](img/072ef523f9f644aa75180307e72efe95_134.png)

![](img/072ef523f9f644aa75180307e72efe95_135.png)

And times2 to the power of exponential part。So， so effectively， you know。

 if you have a floating point number， you will have theres there's sign bits in here and you have your manor exponent。



![](img/072ef523f9f644aa75180307e72efe95_137.png)

Because， you know， you have limited now bits right to represent this the sun， the， the。

 the matha value and the exponential value。As a result， you know。

 you cannot expect to express every real number in a precise fashion。

 That's result that's why when we're doing arithmetic operations。 in a lot of cases。

 you kind of get this you know arithmetic numerical error。When running computation。



![](img/072ef523f9f644aa75180307e72efe95_139.png)

So imagine that we want to perform softmax， which is commonly used operations in。

 in in deep learning， right， we are also going to use that in our some of homeworks。

 Sometimes it might involve a small variant， like log softmax， as opposed to softmax。



![](img/072ef523f9f644aa75180307e72efe95_141.png)

So， so in order to compute this， of course， one of the easiest ways we can go ahead and say， hey。

 I'm going to。

![](img/072ef523f9f644aa75180307e72efe95_143.png)

Directly computers， right。 So the the soft Maxs being written as formulas we are going to take equal。

 They're gonna normal by the sum of auto values Thank here。



![](img/072ef523f9f644aa75180307e72efe95_145.png)

![](img/072ef523f9f644aa75180307e72efe95_146.png)

So the easiest thing we can do is we can naively follow the formula to compute the soft max example。

 if I'm going to import now I'm pie here。

![](img/072ef523f9f644aa75180307e72efe95_148.png)

And imagine that I'm going to have input array。 It really depends on what the value of input array。

 Finally more， if the input array is like 00 point0，01， going to do softmax naive。



![](img/072ef523f9f644aa75180307e72efe95_150.png)

Yeah， in this case， you can find that effective fact with the code versus that is exponential， right。

 that normalizes do they divided by the sum of all the values， It gives you the right result。系。So嗯。

Instead。What if we put in a bigger value here， for example， if you're putting 100，00。诶 you know one。

If you run this code again， you can find that we are getting not a number。



![](img/072ef523f9f644aa75180307e72efe95_152.png)

And here so so what's happening here。

![](img/072ef523f9f644aa75180307e72efe95_154.png)

Again， it is because the floating mode now have limited precision。



![](img/072ef523f9f644aa75180307e72efe95_156.png)

And it go ahead directly it takes financial with respect of 100。



![](img/072ef523f9f644aa75180307e72efe95_158.png)

This value is going to explode， right， because we， you know， with the number of bits available。

 we are really not able to express this number in the in the memory。可以。

So what can we do to avoid this case？And there's an approach that we can do to avoid thisvol scholar numerical error。



![](img/072ef523f9f644aa75180307e72efe95_160.png)

And the way we do this is you can find that actually doesnt invari here。

 So if you have exponential X I， they will subtracting each of X I by a constant and value C。



![](img/072ef523f9f644aa75180307e72efe95_162.png)

![](img/072ef523f9f644aa75180307e72efe95_163.png)

You'll find that， you know， actually， the computation does not change。However。

 we can leverage this fact。 We try to scale try to actually， you know。

 change the value of X I so that they， they become a small value， as opposed to a very big value。

 because we are taking an exponential of something， say smaller than0。

 usually it's much more accurate than taking exponential of a very big number。

So we can do is we can try to take save to be maximum of all those x so that we will be able to。

 you know， so that actually after this transformation。

 all the values are going to be in negative and except one that's going to be0。

 So so in order to perform this。 What we can do is we can try to take x。

 I'm going to subtracting x by the maxim values in here。's that's performing this transformation。

 and then we're going to run the same exponential normalization again。😊。



![](img/072ef523f9f644aa75180307e72efe95_165.png)

![](img/072ef523f9f644aa75180307e72efe95_166.png)

![](img/072ef523f9f644aa75180307e72efe95_167.png)

And if we run this， and then can provide a very big number。

And what you will find that is actually gives us a kind of a stable result。

 And it' not no longer going to overflow。 Okay， so similar principles apply to other operators like。



![](img/072ef523f9f644aa75180307e72efe95_169.png)

Lock soft Max operator and lock sum expansion operators。

 both of them are quite widely used as part of nomination process in our end to end flow okay。



![](img/072ef523f9f644aa75180307e72efe95_171.png)

So， so this is the stable computation of softmax。 And you know。

 that is an approach that we can use to implement some of the homeworks。 Of course， in certain cases。

 right， in this case， we kind of need to be aware of the fact that we are computing softm。

 and we are providing a numerically stable implementation of that softmax operations。

For advanced computation graph system， we might be able to also go ahead and detect the computation where such kind of overflow can happen and try to automatically reormalize it to in enable stability。

 But that's kind of an advanced topic。 Maybe you can take as part of our project。

 and we wouldn't require that as part of our homework implementation。



![](img/072ef523f9f644aa75180307e72efe95_173.png)

![](img/072ef523f9f644aa75180307e72efe95_174.png)

Okay。😊，So we've talked about some of the basics。 And now let's start to talk about how we can design a neural network library on top of the on top of our current set implementation。

 Remember that as part of your homework1， we are only implementing a tensor or tensor class。

 as well as resume computations， loan ten， such we can do additional subtractions。

 we are also able to do things like you know， doing automatic differentiation or backwards function。

 which is what implemented as part of your homework。



![](img/072ef523f9f644aa75180307e72efe95_176.png)

![](img/072ef523f9f644aa75180307e72efe95_177.png)

In the last lecture， we also talk about at high level。

 what are the important components of of the neural network library。

 So we we have we know that there's a module that can help us to compose upper models。

 We can also use a module abstractstruction to build loss functions。

We will need to be able to help us initialize the weights using different industrialization functions。

 It's optimized。 that specifies how do we take parameters and of the gradient。

 And there's also a data loading and pre processingcess function。



![](img/072ef523f9f644aa75180307e72efe95_179.png)

So today， we're going to go ahead and implement some of some of those。 And in particular。

 we're going to focus on the end of module。

![](img/072ef523f9f644aa75180307e72efe95_181.png)

![](img/072ef523f9f644aa75180307e72efe95_182.png)

So let's start with module interview。 And I'm going to do a bit of。



![](img/072ef523f9f644aa75180307e72efe95_184.png)

Coolding together with everybody here。

![](img/072ef523f9f644aa75180307e72efe95_186.png)

Because its coding can be fun。 So， so in order to get the module。



![](img/072ef523f9f644aa75180307e72efe95_188.png)

嗯。

![](img/072ef523f9f644aa75180307e72efe95_190.png)

The first thing that we need to get is this parameter class。



![](img/072ef523f9f644aa75180307e72efe95_192.png)

We kindt already have it here。 So we have this parameter class。So in this case。

 this parameter class is a subclass of。Of cancer。And the only reason why we need this permanent class is we just need a way to indicate。

This is a special part of cancer， which is called parameterss。

 And we want to have a way to be able to say that。In certain cases， want to be able to say that。

 you know， W is instance apparently。 so if I parameter have nothing， you know。

 there's nothing special about parent。And you don't even have to specify construct of it。

 It's just the way to know that， you know， hey， this is special kind of cancer called parameter。



![](img/072ef523f9f644aa75180307e72efe95_194.png)

Now， with this special color tensor， we are ready to introduce。😊。



![](img/072ef523f9f644aa75180307e72efe95_196.png)

呃A module class。

![](img/072ef523f9f644aa75180307e72efe95_198.png)

系。So a module class。

![](img/072ef523f9f644aa75180307e72efe95_200.png)

看 case。A few things。啊。The most。Important function of module class is this function called parameters。

And it defines， how are we going to。Go ahead and pull all the parameters from this particular module。

And in order to do that。We need to define an function God gap。And that contains a value。

And I'm going to implement this。 and I'm going to walk you through this。

Afterpt I finished the implementation。 The first thing I'm going to check is if。Yes， it。Value。

I mention。If it's a case， I'm going to do better return。嗯。Yeah。In second case。Yeah。As instance。那这。

Dictionary。In this case。We're going to go ahead。Itated over all this。Items of the dictionary。

I return。对嗯。so我两 to死。Re it was a list。Reult。白士。At terms。比例。And我 going to return。别。

And there's a third case。Where。

![](img/072ef523f9f644aa75180307e72efe95_202.png)

Actually we' are not going to return We're going to return the result。The short case。

 is we're going to attract you。啊。Value is instance of margin。And if it's a module。

W are going to return。对， you懂。嗯。

![](img/072ef523f9f644aa75180307e72efe95_204.png)

And here， what we are going to do is we are going to do return。Yeah。MM。想懂。

So this dipped is a special attribute。Of。Of， of a class， right。

 it try to gives you every member of this class。

![](img/072ef523f9f644aa75180307e72efe95_206.png)

And so effectively， what's happening in here is that we want to allow these terminals to be able to pull up。



![](img/072ef523f9f644aa75180307e72efe95_208.png)

These all the， all the classes that are subpls of parameters and and return that to the to the inputs。

 so so what it， what it you can find what it does here is you try to recursively look into the value called get parameters。



![](img/072ef523f9f644aa75180307e72efe95_210.png)

![](img/072ef523f9f644aa75180307e72efe95_211.png)

And then， you know， trying to be able to find Christmas parameters and return them as the list。

We can go ahead actually try to create some modules to see what is the effect of it。

 So let's assume that I want to see create or call scale。



![](img/072ef523f9f644aa75180307e72efe95_213.png)

啊。Which is。A subclass of module。Adding the scale add modules。

 we are going to define who parameter is in here。The first parameter。Is going to be F。Fact。

 so let me define to。S equals one。你手。😔，闭一口竭啊。Let's say we have self dog。S equals。Or没ter。In it。

你胎 before老坏水去。

![](img/072ef523f9f644aa75180307e72efe95_215.png)

And I have sale do。鼻。Miples parameter matter。音乐 be。以太。Because老 in话下。And then。Okay， so in here。

 besides parameter function， actually， we also want to define。拓房是你。维持。😔，Which simply redirected to。

So。打货。

![](img/072ef523f9f644aa75180307e72efe95_217.png)

OK。So， after running this。

![](img/072ef523f9f644aa75180307e72efe95_219.png)

Here I can define a forward function。As input X， what we' going to do is we're going to return x times the not scale plus。



![](img/072ef523f9f644aa75180307e72efe95_221.png)

这我不懂。We going find that。

![](img/072ef523f9f644aa75180307e72efe95_223.png)

This is effectively a wild neural nets the module。And we will be able to create one instance of it。

By calling scale at。

![](img/072ef523f9f644aa75180307e72efe95_225.png)

And there are a few things we can do with this module。

 So the first thing we can do is we can say scale add do。嗯。If we look at this。

 you can find a returns。A list of two tensess。 As a matter of fact。

 this scale apparatus correspond to this two field， cell dot S and cell dot B。



![](img/072ef523f9f644aa75180307e72efe95_227.png)

And so why does the parameter return this， We look at an implementation。

 Like you can find that effectively， the self dog dictionary of that scale at contains。S。The S value。

 right， and B。That B value in here。 We get this dictionary being passed on to this function that goes into this code pass that unpacks it and called gap parameters。

 And for both cases。The value itself is a parameter。 So get pulled up。

 If I have other values that are not parameters， they wouldn't get pulled up to the to the output in here。

 So this parameter function is a very convenient method for us to pull out requestcursively all the fields that are create into parameters in here。



![](img/072ef523f9f644aa75180307e72efe95_229.png)

![](img/072ef523f9f644aa75180307e72efe95_230.png)

And you will even be able to go ahead and check when you will be able to say that it saw zero。Yes。

As adult as here。W you is true。And it's not one。Yes， S and dot B。 right， So you can find that indeed。

 this parameter correspond to this true field， the S and B。



![](img/072ef523f9f644aa75180307e72efe95_232.png)

Another thing we can do is now we have this module。

 so we'll be able to go ahead and try and apply it。有 know cancer。6球。一台一く。校里去。If you player。

 you can find out the value。

![](img/072ef523f9f644aa75180307e72efe95_234.png)

啊。It's going to be another needle of answer。 Let's see。 Okay， so this should be returned， right。

 So I forget this return value in here。

![](img/072ef523f9f644aa75180307e72efe95_236.png)

Let's go ahead and try again。

![](img/072ef523f9f644aa75180307e72efe95_238.png)

![](img/072ef523f9f644aa75180307e72efe95_239.png)

A you run this。You'll find that it's going to return your needle test。 in this case。

 because scale initially is one。 So it's going to gives you the same ten。

 But if I parameter the initial S to be 2， run again， you can find that you know。

 equals 4 I parameter by 2，1。It's going to。Give me by。 So， so， you know。

 effectively for a module there are two things we can do。



![](img/072ef523f9f644aa75180307e72efe95_241.png)

Well be able to query and reclively query what are the online parameters。

That are containing that module。 The second thing we can do is you gonna go ahead and take some of this input sensorsor and apply that。

 It gives you the output sensoror。

![](img/072ef523f9f644aa75180307e72efe95_243.png)

So now we have defined a scale add。 Another thing that we can do is we will be able to actually recursively define modules with respect to other modules。

 That's a very useful ability。 Thank you。 So let's imagine that。

 we want to define something called multi pass。😊。

![](img/072ef523f9f644aa75180307e72efe95_245.png)

![](img/072ef523f9f644aa75180307e72efe95_246.png)

Yeah I。It's all module。And effectively， what I try to do is try to have a two individual pathways。

 So， so we have the inputs here， X。

![](img/072ef523f9f644aa75180307e72efe95_248.png)

That's going to go through。A scale at pathway。And another。Scall ad pathways。 And in the end。

 we are gonna add these two things together。 And that's my offer。 So this is my multi pathway。 S a。

 of course， you know， realistically doesn't mean anything in here。

 we are only trying to use as a demonstration of you know what。

 how you can go ahead and compose module together。

![](img/072ef523f9f644aa75180307e72efe95_250.png)

And you will be able to use the same way I to developed a residual module in your homework， okay。



![](img/072ef523f9f644aa75180307e72efe95_252.png)

So in order to do that， the first thing we can do in here is we will be able to define your construct class。

In this case， we have two passes0 equals1。S的 plus one equal。Okay。

 so we kind of get to pass in a forward function。

![](img/072ef523f9f644aa75180307e72efe95_254.png)

We can say that。I want to return。T到 pass 0， apply to x。se dot pass one。That's our money scale。

 Mo Mopa scale ad。

![](img/072ef523f9f644aa75180307e72efe95_256.png)

And we will be able to say， M pass。Because smart。啊。Here。And you know， again， in this case。

 I will be able to try MP pass Do。Parameterters。

![](img/072ef523f9f644aa75180307e72efe95_258.png)

Throughness， you can find that we are getting four tensors in here。 So even though in this case。

 this module do not have immediate。

![](img/072ef523f9f644aa75180307e72efe95_260.png)

A child field that contains a parameter。What I try to do is actually what we call more empath of parameters because we know that this module contains some of the sub modules where self dot pass 0 and self dot pass one。

 So theycursively call the parameters of self dot pass 0 and self path dot pass one to get the parameters As a result。

 we are collecting all the parameters of this module recursively。

 And this will be helpful when we are going to introduce optimizers and go ahead and update the weight。

😊。

![](img/072ef523f9f644aa75180307e72efe95_262.png)

![](img/072ef523f9f644aa75180307e72efe95_263.png)

Okay。So， and we can also go ahead and try。 So in this case， actually， this one， the first parameter。

 we can go ahead and track what the Chris wanted to。



![](img/072ef523f9f644aa75180307e72efe95_265.png)

It actually crisp one to Ms。懂啊。把0到调。And second parameter， ch M pass path zero dot bios and so on。

So now we have this， we will also be able to do things like MP directly apply。呃 tonen needle cancer。

Wan。以太抵口于所以32。Thank you pass。

![](img/072ef523f9f644aa75180307e72efe95_267.png)

The ch output， in this case， youll have two passess for adding together。



![](img/072ef523f9f644aa75180307e72efe95_269.png)

So now we have defined all this， right， the next thing we can go ahead and try to do is to define a loss function。



![](img/072ef523f9f644aa75180307e72efe95_271.png)

![](img/072ef523f9f644aa75180307e72efe95_272.png)

Because， you know。Once we have the modules， we want to be able to compose that together with loss module so we can perform great up。



![](img/072ef523f9f644aa75180307e72efe95_274.png)

![](img/072ef523f9f644aa75180307e72efe95_275.png)

So you want to define loss functions。Let's， you know。

 we know that loss function can be defined as mod。 You already see an in combination in here。



![](img/072ef523f9f644aa75180307e72efe95_277.png)

So in this case。Luse function is some module。That does not contain any parent。In this case。

 this particular loss function while taking two things， you were taking an input。

 which is the output prediction of my overall pathways。

As well as the label one that correspond more to the loss value。

And the way we compute loss functions is we're going to go ahead and compute。

We are going to go ahead and compute effectively the difference between the two。 again。

 the negative one is other effect of us not having subtraction operators。

 If you have a subtraction operator， you will be able to go ahead directly say C equals x minus y。

 And yeah you are relatively this square losingcing here。 So in this case。

 we are simply defining L2 loss that computes the difference between two values。



![](img/072ef523f9f644aa75180307e72efe95_279.png)

![](img/072ef523f9f644aa75180307e72efe95_280.png)

![](img/072ef523f9f644aa75180307e72efe95_281.png)

Once we have a loss function， we'll be able to write y equals a label in here。



![](img/072ef523f9f644aa75180307e72efe95_283.png)

![](img/072ef523f9f644aa75180307e72efe95_284.png)

And then。In this case， right， let's say X equal2。 and you to apply for m pass。



![](img/072ef523f9f644aa75180307e72efe95_286.png)

The end result is4， and then let's assume that we have a label， which is true。



![](img/072ef523f9f644aa75180307e72efe95_288.png)

What we can do is we can go ahead and first compute m pass that gives us the output of the hypothesis。



![](img/072ef523f9f644aa75180307e72efe95_290.png)

And then we're going to use the loss function compute the loss value。 So if we go ahead and write it。

 you will find that the loss value equals 4 because the forward prediction of the value equals equals 4。



![](img/072ef523f9f644aa75180307e72efe95_292.png)

![](img/072ef523f9f644aa75180307e72efe95_293.png)

And then the expected value equals 2， right， difference of the square there， the value equals4。



![](img/072ef523f9f644aa75180307e72efe95_295.png)

And if you go ahead and do loss now backward。

![](img/072ef523f9f644aa75180307e72efe95_297.png)

Were going to。Get the gradient values of each of the weight。 And actually。

 we'll be able to go and verify that。

![](img/072ef523f9f644aa75180307e72efe95_299.png)

So we can go ahead and you know launch things like。



![](img/072ef523f9f644aa75180307e72efe95_301.png)

Parameters equals m pass of parameters。In this case。IActually， you know。

 each of parameters will come with the gradient。 So we'll be able to say that parameters prime 0 dot gradient。

V equals H。

![](img/072ef523f9f644aa75180307e72efe95_303.png)

And if you look at， actually， this also， effectively is the past 0 do scale not grade。

 so y is equals 8， you can go ahead and compute the loss。 So because we know that it the。

 the loss value is4， right， And then， you know， if you think about how we're gonna backproing that。



![](img/072ef523f9f644aa75180307e72efe95_305.png)

![](img/072ef523f9f644aa75180307e72efe95_306.png)

The greening values with respect to x in this case。Its going to equal。That's it。 first of all。

 the gradient value of a loss is going to equal two times Z。 in this case， the value of Z。

Equals2 here。 So as a result。The green value with respect to x equals4。



![](img/072ef523f9f644aa75180307e72efe95_308.png)

Let me see， if that's right。

![](img/072ef523f9f644aa75180307e72efe95_310.png)

Oh， it's really hard to compute this manually。 let's see。The loss value equals4。Because the square。

 So the green value equals two times 2， which also equals 4。



![](img/072ef523f9f644aa75180307e72efe95_312.png)

And。And it's a gradient value， right。 Oh， yes。 And And because my input is X is 2。 right， So again。

 is four times 2。 So the gradient value equal okay， so actually。

 we are indeed getting the right gradient here。 Yes。

 So once we have this gradient we will be able to go ahead and take a loss function and write up there。

😊。

![](img/072ef523f9f644aa75180307e72efe95_314.png)

![](img/072ef523f9f644aa75180307e72efe95_315.png)

![](img/072ef523f9f644aa75180307e72efe95_316.png)

![](img/072ef523f9f644aa75180307e72efe95_317.png)

Uptim later rule， as we will be able to say that for I J in parameters。

 W dot data equals W dot data plus minus certain rate times Wgrad。

 You can find that one thing that's really convenient about in place update is that， you know。

 every time we are doing updates for directly set to gradient values back on to W。

And those ws are still contained right within the original module。

 So the second time when we call forward， they are still going to be in there the same with the same W field。

 So we don't need to be worry about you know how do we pass the new weight value back onto the models。



![](img/072ef523f9f644aa75180307e72efe95_319.png)

Okay。So now we have talk about modules。 The next thing we're going to talk about is how we can。



![](img/072ef523f9f644aa75180307e72efe95_321.png)

Dine an optimizer interface。

![](img/072ef523f9f644aa75180307e72efe95_323.png)

And an optimizer kind of help us to be able to perform updates like stochastic gradient updates and other updates in here。

 And they are two important。

![](img/072ef523f9f644aa75180307e72efe95_325.png)

![](img/072ef523f9f644aa75180307e72efe95_326.png)

Fctions often optimized。The first function is called a re gradient。 So， so first of all。

 an optimizer is going to take in a list of parameters。

That that effectively get passed from module parameterss。So once we have those parameters。

 there are two things we can do。 The first thing is reset gradient。

 So it will simply iterate over all the parameters and reset the p top gradient field to be now。

The second function is is called step function。 So in this case。

And iterates over all the parameters will take the all the weights and perform one step of updates。

 either it to ingredients and or like still with momentum。

 depending on the updated rule we are looking at。So we can go ahead and try to implement a variant of。



![](img/072ef523f9f644aa75180307e72efe95_328.png)

A very non optimize here。

![](img/072ef523f9f644aa75180307e72efe95_330.png)

So， let's imagine that we have。That's， let's go ahead and simples。

 we do S GD is a subclass of optimizer。I will be able to say that the in function。

It it be thats a linear age。And that's a person here。And then it's going to require self dot well。

Well， I'm going for car。

![](img/072ef523f9f644aa75180307e72efe95_332.png)

诶。My parent， parents initializers are so super。

![](img/072ef523f9f644aa75180307e72efe95_334.png)

Optimizer， I kind of forget what's okay， so actually， I can directly it to initialize。

 That's fine because it in this case， the initializer is not as。😊。



![](img/072ef523f9f644aa75180307e72efe95_336.png)

So I can just do the self do。per。

![](img/072ef523f9f644aa75180307e72efe95_338.png)

The costest price。Theyhou God learning radios。Rage。And then the step function。



![](img/072ef523f9f644aa75180307e72efe95_340.png)

We can do。Or。W exc点M。W到 datata equals。啊，W那个 plus。有就。那个 rageage。啊西。W。



![](img/072ef523f9f644aa75180307e72efe95_342.png)

瑞点吧。Okay。So this is going to be that s category optimizer。



![](img/072ef523f9f644aa75180307e72efe95_344.png)

We need to define optimize version here。

![](img/072ef523f9f644aa75180307e72efe95_346.png)

跟住。

![](img/072ef523f9f644aa75180307e72efe95_348.png)

Okay， so now we have implemented this SGD optimizer。 The next thing we can try to do。

 can try to put everything together， try to run things n to M， see， you know。

 how does things work together。 Okay， so you want to do that。

 What we can do is we can try to build this code block that have been written here。



![](img/072ef523f9f644aa75180307e72efe95_350.png)

![](img/072ef523f9f644aa75180307e72efe95_351.png)

![](img/072ef523f9f644aa75180307e72efe95_352.png)

![](img/072ef523f9f644aa75180307e72efe95_353.png)

The first thing that we can try to do is we can try to。Cate。

2 needle tensors where x correspond to my input and y correspond to my label tensor。



![](img/072ef523f9f644aa75180307e72efe95_355.png)

![](img/072ef523f9f644aa75180307e72efe95_356.png)

And then we can create a model that correspond through my hypothesis class that correspond a neural network model。

 in this case， I'm simply using multi Pa scale app in this case。And the loss function in in here。

 we are going to use the L true loss。 So next we're going to do is we're going to create an optimizer in this case。

 you know， S GD is going to be the optimized that we're gonna use。



![](img/072ef523f9f644aa75180307e72efe95_358.png)

![](img/072ef523f9f644aa75180307e72efe95_359.png)

And then we're going to run it through a normal of epos here。So initial an epo。

 what we're going to do is we're going to first call optimize the not reset gradient。



![](img/072ef523f9f644aa75180307e72efe95_361.png)

And then we' are going to call the hypothesis dot model。 So model X that gives you a hypothesis。



![](img/072ef523f9f644aa75180307e72efe95_363.png)

![](img/072ef523f9f644aa75180307e72efe95_364.png)

And then we are going to create a loss function that computes hypothesis and label that gives the loss。



![](img/072ef523f9f644aa75180307e72efe95_366.png)

![](img/072ef523f9f644aa75180307e72efe95_367.png)

And effectively， it is the training loss that we can go ahead and print it out。

 And we're gonna to call loss backward that gives the gradient。 Finally， step give us the， you know。

 one step of SGD update。

![](img/072ef523f9f644aa75180307e72efe95_369.png)

So we can go ahead and try around this code block。

![](img/072ef523f9f644aa75180307e72efe95_371.png)

And you can find actually loss decreases in here， which means that indeed。

 there is a right amount of training epos to help us to be able to， you know。

 build those end to a neural network training。

![](img/072ef523f9f644aa75180307e72efe95_373.png)

![](img/072ef523f9f644aa75180307e72efe95_374.png)

So I'm going to pause here that。I will like everybody to。Think about， you know。

 what is the difference between this piece of code。

Versusus say the code that you have been written in your homework 0， where we are kind of， you know。

 effectively derive the gradient from hand and， you know。

 write up the update rule in C class by scratch。If look at this particular piece of code。

 you can find this very modular。 So we'll be able to imagine that I want to change my hypothesis。

 I just' need to change this line without training any other parts。 it's going to work out of box。

 and I'm going to change my update rules like SD。 I can just go ahead and change this particular line of you know optimize。

 And in the same code structure is going to continue working for a lot of cases。

 And if I'm going to change my loss function， I only have to change this line。



![](img/072ef523f9f644aa75180307e72efe95_376.png)

![](img/072ef523f9f644aa75180307e72efe95_377.png)

So this code is very modular。 They help us to be able to replace different components as we need。

 And that's kind of like amazing part about different firm allow gives ability to be able to。

 you know， to be able to mix and match different module together。

 And one of reason is that we are designing those modules in a way so that they can effectively interact with each other organic。

😊，And if you come back and look at those designs， you can find those designs look so obvious， right。

 They are so simple and elegant。 On the other hand， if you put yourself into， you know。

 the time where。😊，This design does not exist at all in a first generation different in framework。

 You may find that actually， they are not as obvious as seems。

 and it's really important to appreciate this kind ofological design and how they compose together。



![](img/072ef523f9f644aa75180307e72efe95_379.png)

One things I want to notice that， you know， we only implement SGD， right， So on other cases。

We will need to be able to create states in SGD or in optimize as well。

 Well if we want to implement something SGD with momentum。In this case。

We would not only need to record the set of parameters。

But we also want to be able to create the additional。States in here， right。

 so that we can keep track of momentum variables。 So， so， for example。

 we will need to be able to write things like self dot momentums。 let's use you to denote momentums。

 It's equals， you know。

![](img/072ef523f9f644aa75180307e72efe95_381.png)

Middle dot answer。0。Actually， I can do things like needle dont。0eros like。啊，皮。我屁你。

So it will help us to create a set of momentum variables， that we can use to in our update。

So when we start to create more advanced optimizers。

 we want to be able to keep track of those internal states within the optimizer class。

 that's also one of the interesting part of the optimizer design where we have the module that contains the peri states。

 We have the peri function that collects out the list of parameters。😊，And then we use this。 we。

 we recreate those additional auxiliary states that help us to run the crispbon updates。



![](img/072ef523f9f644aa75180307e72efe95_383.png)

Okay， so that's N to flow。

![](img/072ef523f9f644aa75180307e72efe95_385.png)

In the， next part， I'm going to quickly go over in。 So in this case。



![](img/072ef523f9f644aa75180307e72efe95_387.png)

As part of we need to implement an instruction function for卫星 things like linear transformation。

 other transformations。

![](img/072ef523f9f644aa75180307e72efe95_389.png)

In order to derive the overall magnitude of the random installations。

 one of the things that when need remember is now very deep， linear neural networks。You know。

 every time when you apply a transformation， the order magnitude of the of the of the value can change according to the weight。

And one of the goals in here is we really want to derive in such that your。

If you are going to in things randomly， and your input is also randomly distributed。

Yeah output variance。 It's gonna be。You know， close to your input barriers。



![](img/072ef523f9f644aa75180307e72efe95_391.png)

And there's a there's a derivation from the original paper that effectively says that， you know。

 my output variance is going to equal in second order toon of inputs of each of input and variance of w。

 In this case， let's assume that we are doing Gaussianization of W。

 the variance equals sigma squared。

![](img/072ef523f9f644aa75180307e72efe95_393.png)

And also， let's imagine that if x。Square is axis as a result of a value activation of previous layers。



![](img/072ef523f9f644aa75180307e72efe95_395.png)

We know that the result of the variance of Ra， because you know。

 you get kind of like a the original value on the left right hand side and0 on the left hand side。

 So kind of get the half of variance in there。

![](img/072ef523f9f644aa75180307e72efe95_397.png)

![](img/072ef523f9f644aa75180307e72efe95_398.png)

And our goal is to make sure that the variance of the next layer equals the variance of previous layer。

 So well plug that back and derive， you know， the sigma。 You'll find that， you know。

 you can have a value to set the sigma according to number of input file。

 fan ys of your input weights。

![](img/072ef523f9f644aa75180307e72efe95_400.png)

![](img/072ef523f9f644aa75180307e72efe95_401.png)

If you change your distributions to things like uniform distribution。

 we will need to use a similar rule except that you want to use the variance calculations for uniform distributions。



![](img/072ef523f9f644aa75180307e72efe95_403.png)

![](img/072ef523f9f644aa75180307e72efe95_404.png)

![](img/072ef523f9f644aa75180307e72efe95_405.png)

Okay。😊，So we have talk about the overall modules and ins and how does loss function and everything fit together。

 So the last part， I'm going to quickly note about you know。



![](img/072ef523f9f644aa75180307e72efe95_407.png)

![](img/072ef523f9f644aa75180307e72efe95_408.png)

It's kind of a bonus content or typical value。 So if you open up your code。



![](img/072ef523f9f644aa75180307e72efe95_410.png)

![](img/072ef523f9f644aa75180307e72efe95_411.png)

In the on， on the on the right hand side， actually。

 the lecture is code now contains additional implementation。Of tuil， of a test tu。



![](img/072ef523f9f644aa75180307e72efe95_413.png)

啊。

![](img/072ef523f9f644aa75180307e72efe95_415.png)

谁？

![](img/072ef523f9f644aa75180307e72efe95_417.png)

Of a cancer tuple that correspond to a tu of cancers。

 in this case we not supporting nastystate cancers。



![](img/072ef523f9f644aa75180307e72efe95_419.png)

As well as some operation that creates one to test a table， such as no。

Getting value from T and con two points together， it also allows us to be able to define operators that that whose return value are triple values。



![](img/072ef523f9f644aa75180307e72efe95_421.png)

So if you look at option here。

![](img/072ef523f9f644aa75180307e72efe95_423.png)

Actually， we have this operator card。😊，Fed at Scar。 In fact， it's in the computer。

 it's going to return two value as opposed to one。And output gradient， actually， in this case。

 a tuple。 And in our case， we want to because a is present in both cases。

 we' are going to add those two gradient together。

![](img/072ef523f9f644aa75180307e72efe95_425.png)

诶。So。One thing you will find is that， you know， with the same autograph mechanisms。

 we will be able to create a tensor。

![](img/072ef523f9f644aa75180307e72efe95_427.png)

![](img/072ef523f9f644aa75180307e72efe95_428.png)

Wite through a test operator that gives you a Tea tuple and actually， you know， continue to give you。

Tupal values。 And you know， you will be able to obtain the elements of a tual values。



![](img/072ef523f9f644aa75180307e72efe95_430.png)

So， you know， you are more than welcome to check it out。 And， you know。

 it is a very useful way for us to express the operation that contains multiple return values。😊。



![](img/072ef523f9f644aa75180307e72efe95_432.png)

And， you know， the same mechanism， you， it's amazing to see that same automatic differentiation mechanism actually works out of box in here。

 So for example， I would be able to say that。😊。

![](img/072ef523f9f644aa75180307e72efe95_434.png)

![](img/072ef523f9f644aa75180307e72efe95_435.png)

然后B0 equals the0 plus say one times 2 and B 0。多。Backward。



![](img/072ef523f9f644aa75180307e72efe95_437.png)

And should be able to， you know。Backward。

![](img/072ef523f9f644aa75180307e72efe95_439.png)

It should be able to propagate the gradient back onto X properly。No。

 and if you are more than welcome to go ahead and check it out。 and if you are interested。

 of course not part of the requirement， you are more than interested。

 You are more than welcome to implement automatic differentiations for other data structure values like dictionaries so。

😊。

![](img/072ef523f9f644aa75180307e72efe95_441.png)

Okay， so that's the end of this lecture， thanks everybody for coming and I will see you folks in next few lectures。



![](img/072ef523f9f644aa75180307e72efe95_443.png)

![](img/072ef523f9f644aa75180307e72efe95_444.png)