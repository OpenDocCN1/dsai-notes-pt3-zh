# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p07 -08-Lecture 7 - Neural Network Abstractions.zh_en -BV1ERtYepEpy_p7-

Okay， hellello everyone， welcome back to deep learning Systems。Agress an implementation。I'm T。

 Q Chen。 Today I'm going to work with Bley to talk about our lecture So neural network Library abstract。



![](img/318bd9616159378b3647e56c3ec79600_1.png)

So up until now， we have talk about a few of the basic deep learning models like multi layer perceptions。

 as well as the basic automatic differentiation algorithms。 Hopefully， you know。

 now you have started to work on your homework one and having fun building some of these automatic differentiation libraries。

Today we are going to talk about how we can compose the things we build to really form a anine neural network or anine deep learning library。

 until until now， when we talk about the needle library。

 the only thing with dispute so far only contains basic elements like tensors and and automatic differentiation。

 And there are a lot of things we can build on top so that we can build a different color machinery model more easily。

😊，And today's lecture is going to contain two parts in the first part I'm going to quickly describe and discuss with folks on possible programming abstraction we can use to build machine learning models and actually do a bit of history review of the history of deep learning frameworks。

 And the second part I'm going to work with everybody on study some of the high levelvel modular components and how we can effectively decompose machine learning library design onto different architectural components that can then organically work together。

😊。

![](img/318bd9616159378b3647e56c3ec79600_3.png)

That's always the first part。So what is programming obstruction。

 So the programming abstractstruction involves things like an API we use to define computations。

 how we can extend the overall framework to support things like different kind of GPUus and different kind of models。

If you， you have used library like Pyage or Tensorflowlow or library before。

 some of those design choices may seem very obvious for you after you have seen and use them for a while。

But， you know， if we come， if you try to， let's try to， you know， time revine and。

 and try to travel back to the time where those deep library are not yet available。

 And you can find that some of our choices may not become as obvious。

 And it's very interesting to see how they differently frame abstraction evolve over time。

 It's also important to recap and learn through this thought process on how we eventually arrive at the interfaces reality actually。

Because。That help us to know why the abstraction of design this way。 And also， you know。

 as the field of machine learning and also machine learning frameworking evolves。

 there's always a need of， you know， designing new capabilities。 And， and as a result， there are。

 you know， new lesson。 These lessons can be used to help us to design new abstractions in the future as well。

😊。

![](img/318bd9616159378b3647e56c3ec79600_5.png)

诶。And so in the first part， we will do a case study。

Of effectively the history of deep learning framework development。

 And we are going to specifically focus on three past frameworks that are representative in in the history of deep framework development。

The first framework we are going to look at is cafe1。0。

 So this is one of the earlier popular framework that help us to do most of the computer vision tasks on GPSus。

 And you know， even today， it's still being used in quite a few use cases， of course。

 most of the use cases have been switched to the later generation。 later generation frameworks。

second framework we're going to look at is Tensorflow 1。0。

 And this is specifically interesting when we look at the particular design choices that comes into the tensorflow 1。

0 design。 And finally， we're going to look at Py or， you know， today。

 when we' are looking at the library like needle。 The programming extraction we are building really is mirrors what Py is doing。

 So these three frameworks are。Were， you know， quite popular at and dominates the market for a period of time in the history of machine learning frameworks。

 Of course， there are many frameworks being developed along the way that besides this three frameworks So for example。

 there's earlier pioneer in a few C and Toch 7 in Lua。

 and there's also framework I was involved in called Xnet Cafe had a second generation framework called Cafe to Chinaer and more latestly。

 there's a very exciting development from Google that leads to JX。 So due to time。

 we will not study all the frameworks。 but a lot of them also share some of similar traits and we were mentioned And as we do the case study。

And if you are more like interested， you should go ahead and check out those frameworks well and think about。

 you know， what are the design choices in those frameworks， specifically。

 how do you design the interface to， to build neural networks and how are they different from each other and why。

They come come down this comeさ。

![](img/318bd9616159378b3647e56c3ec79600_7.png)

Okay。So， as a first step。Let's first take a look at cafe 1。0。

And it's a typical representation of a first generation deep framework。So嗯。In 2014， the。

 I think 2 Yeah，2014， the image Alex S strategy and Jeff Hton and other and Eli won the first using the neural net to one the image net challenge。

 right， So that's the inception of the deep wave in computer vision。 and later on。

 it's all all different color applications。And one of the earlier pioneers there is this framework called Kuta Com net。

That Alex trajectory build to effect allows us to go ahead and compose neural networks and use that for Android training and Cfe is a system developing Berkeley that tries to effectively fact we formalize some of engineering approaches and then go ahead and you know allows us to build different machine learning models it have becoming very popular and almost。

 I think 80% of the machine differently work then actually use CA。So， of course， today。

 it's no longer been as widely used， but it's very interesting to study the interface of the first generation differently firm。

Specifically。On those frameworks， there is one core core abstraction that being used。

 which is called a layer。So， of course， in cafe， the layer is implemented in say plus plus。

 but I'm just using Python Suu code here to show the general idea。So。😊。

When we are composing neural network together， we will always talk about here as's a linear layer followed by a re layer and then a softmax。

 you can find that layer is kind of like the basic element that you can use to compose them together。

 And this compality is really helpful so that for example I can not only develop re neural network。

 but we can replace on value activations by the signal activation with a few lines code。

 and then that new neural network can be you know， can be trained in the same fashion。

 right So a layer interface defines two key two key functions。

 The first function is we called forward function。😊。



![](img/318bd9616159378b3647e56c3ec79600_9.png)

![](img/318bd9616159378b3647e56c3ec79600_10.png)

![](img/318bd9616159378b3647e56c3ec79600_11.png)

In the forward function， what it try to do is try to take data from input。 in this case。

 It's called bottom and try to propagate the， the data and the computation to the output。 example。

 if my layer is the exponential layer on the left。

![](img/318bd9616159378b3647e56c3ec79600_13.png)

![](img/318bd9616159378b3647e56c3ec79600_14.png)

![](img/318bd9616159378b3647e56c3ec79600_15.png)

What I try to do is it， it will do bottom。嗯。

![](img/318bd9616159378b3647e56c3ec79600_17.png)

Exponential。And we are going to assign that， to。

![](img/318bd9616159378b3647e56c3ec79600_19.png)

Top here。 And in this case， both top and bottom have the memory already pre allocated。

 So effectively just run the computation and copy the data onto the top。Of course。

 this is only running a forward computation。 in order to compute the updates。

 we will still need to do the gradient computations and set the weight onto the and set the weight the gradient。

 use the weight gradient to do the update。 So that's where the backward function comes in。

And usually in cafe。 So the top contains the gradient from the output。



![](img/318bd9616159378b3647e56c3ec79600_21.png)

![](img/318bd9616159378b3647e56c3ec79600_22.png)

And there's a propagate down field that uses to indicate， you know， whether or not I want to take。

 we want to propagate gradient to the input， Because if say I'm V1。

 you don't have to propagate gradient。

![](img/318bd9616159378b3647e56c3ec79600_24.png)

![](img/318bd9616159378b3647e56c3ec79600_25.png)

You don't have to proagate gradient to the input at least in this case， because， you know。

 unless you are doing things like neural neural style where you are。

 you are taking gradient with respect to input。 So this is a kind of propagate down。

 It's just a specific flag that helps us to do certain optimizations。

And bottom is the contains the array that allows to propagate gradient onto。Of course。

 in the back function， it's also going to refer to some of the。

 some of the activations and data from a flower propagation。So。



![](img/318bd9616159378b3647e56c3ec79600_27.png)

When in a backboard function， I example if you are doing things like exponential。I， ideally。

 what you are going to do is effectively you are， you are going to say my bottom。Graient。

It's going to equal。 in this case， I do have a top value， which is exponential。Times。The top。



![](img/318bd9616159378b3647e56c3ec79600_29.png)

Graient。

![](img/318bd9616159378b3647e56c3ec79600_31.png)

明鞋。That is a gradient of exponential。So one thing you notice is that in this interface。

 we are effectively doing bad propagation in place。 So， so for this competition graph， for example。

 there will be a multiply layer。😊。

![](img/318bd9616159378b3647e56c3ec79600_33.png)

A adlier。exponentialponent。

![](img/318bd9616159378b3647e56c3ec79600_35.png)

Layer in here。That compose this together in this way。 and then。In the neural network training。

 first of all， we are going to iterate over all the layers call forward to inter topological order so that you will be able to get all the intermediate activations。

 And then we are going to do reverse topological iterations and call backward function to prop it a gradient back。

😊，After that， each of the layers will contain the gradient with respect to their internal weight。

And then we can cause sometimes the update function or software function to take the gradient and weights and update weight in place so that we can get effective weight updates。

 And in the next iteration， we are going to do that again again。So if you look at this interface。

 right， you can find it is slightly different from what we talk about in our automatic differentiationation lecture。

Instead of taking the computational graph and extend another computational graph that performs the gradientding calculations。

It simply builds up the layer interface as propagated in place。

So what are the advantages and disadvantages of this layer interface。Or， you know。

 another question that I want everybody here to think about is。

 why did the author of Cafe and Kda Kfnet come up with this layer interface。Well， right now。

 if you look at the design choices， maybe， you know。

 it seems not as obvious to you because you are getting more used to the computational graph automatic my differentiation anyway。

But if you don't， imagine that you don't have not learned about any of those concepts。

 And you just learn about the forward propagation and the back propagation in in， in deep learning。

Very likely， you are going to come up with some interface that looks like this one because it's quite natural。

 right you get layers and each of layers， you can do two actions。 You can do four propagation。😊。

And then you can do backward propagation to get a gradient。

 I personally also developed my own libraries at at the time trying to work on some of the deep learning deep learning workflows。

 And I also come up with a similar interface that that contains a forward and backward function。

So it's kind of a quite natural choice。 And if you look at the description of background by Ga Hinton and others。

 and usually you will find that it's also a quite natural choice to end up with in the beginning。😊。

So。This style of interface kind of become popular and become a standard of the first generation of the framework。

So after 2015， you will find that there's a second interface。

 which is a tensorflow interface that that start to have the concept of computational graph instead of layers。

 right， So the， the difference of computational graph in layers is that in the computational graph without simply describing a forward computations。

😊。

![](img/318bd9616159378b3647e56c3ec79600_37.png)

![](img/318bd9616159378b3647e56c3ec79600_38.png)

![](img/318bd9616159378b3647e56c3ec79600_39.png)

And then when we take ingredient， we are going to extend the competition。

And so Tensorflowlow is a typical representatives of this style of API and specific Tensorflow 1。0。

 So if you talk about Tensorflow now， it's already at 2。0。 So， you know。

 a lot of things have changed。 and the Tensorflowlow have already also adopted some of the imperative programming APIs that Pyto uses。

 But we' are going to focus on the Tensorflowlow 1。

0 API because it kind of represent a very interesting way of designing programming instructions for machine learning。

I also want to mention that actually， Tensflow 1 hollow is also not the first framework that come up with the concept competition graph。

 It's only pioneer called Seattle from University of Montreal and you know the concept of computational graph actually was pioneer by Seattle。

 So a lot of the you can see quite a few reflections of the of the API design between Tensorflow and Seattle in in the early days。

So let's take a look at how we are going to take a different model and try to describe that using the computational graph API in K of 1。

 And let's walk it through line byline。

![](img/318bd9616159378b3647e56c3ec79600_41.png)

So to describe a computational graph， first of all， we are going to create a variable in here。

 corresponding to a V1。W whichch， which says， no， it is in in place place folder。

 We do not yet know what the value is， but we want to kind of describe this simulation graph。

In a second step， we're going to do is we're going to say B2 equals T F exponential V1。

 that's going to create this relationlay graph node。Then I'm going to do V3 equals V 2 plus 1。

 That's gonna create a V3 node。 Finally， V 4 equals v 2 times v 3。

 And that's going to create my V 4 note here。😊。

![](img/318bd9616159378b3647e56c3ec79600_43.png)

![](img/318bd9616159378b3647e56c3ec79600_44.png)

Up until now。No computation have yet happened。All this。



![](img/318bd9616159378b3647e56c3ec79600_46.png)

Coding here。Simply construct the computational graph on the left hand side。And。You know。

 if you want to ask what is the value of B1 or what， what is value of B2。

 the answer is we don't know。 We don't yet know right because only the API only start to construct this computational graph and。

And that's it。So in order to really go and execute， you know， we want to ask。

 what is the value of B4 there V one is1。

![](img/318bd9616159378b3647e56c3ec79600_48.png)

What you need to do is need to create a session。

![](img/318bd9616159378b3647e56c3ec79600_50.png)

That helps you to send the execution command on。

![](img/318bd9616159378b3647e56c3ec79600_52.png)

And then you're gonna to see session dot around V 4， saying that， hey， I'm interested in value V 4。

 and it's a feed di that that tells the system。 Okay， the value V1 here should be one。😊。



![](img/318bd9616159378b3647e56c3ec79600_54.png)

![](img/318bd9616159378b3647e56c3ec79600_55.png)

![](img/318bd9616159378b3647e56c3ec79600_56.png)

And then after you run a session， you will get the value of the4 bag in here okay。



![](img/318bd9616159378b3647e56c3ec79600_58.png)

So you can find in this API。It's a typical way of what we call a decorative program。

So what does decorlarative programming mean， So it means that it try to declare the computation。

 right， in this case， it first declares the computation that we want in here。



![](img/318bd9616159378b3647e56c3ec79600_60.png)

And then。We， we have a second execution part that takes their declarations and go ahead and send the declarations on the system。



![](img/318bd9616159378b3647e56c3ec79600_62.png)

So， so let's pause a bit。 I think about。Why does Tensorflow design API in this way。

 What are the advantages of this kind of declarative API。And also， remember that， you know。

 this is API designed by Google and Google is very well known for designing scalable distances。

 So that there must be some considerations that comes into designing the neural network API in。

 in this way， right。😊，So。If it pass a bit。I think about you know what are the advantages of this decorative programming API。

The few things you might noticed。 first thing is that。In this code。

 there's a very clear separation that you have a declaration part and declares the complete entire comm graph。

 And you have a run part in here。😊，So。One of the advantage is that when we go and execute。

The computations， we kind of know the entire computational graph already。

 right so we can do certain kind of optimization。 So imagine that in here， let's say。😊。



![](img/318bd9616159378b3647e56c3ec79600_64.png)

I declare this computational graph。

![](img/318bd9616159378b3647e56c3ec79600_66.png)

Instead of saying， hey， I'm interested in getting a value of V 4。

 What if I'm saying that I don't interest in V 4， I'm only interested in V 3。



![](img/318bd9616159378b3647e56c3ec79600_68.png)

What's going happen is that the online system can go and analyze， okay。

 do you have a declaration that contains all the computation graphs。

 but you are only interested in V3， but not V4。 So how about let's go and only execute this part of computation graphs instead of all the components。

 right， So so it gives you opportunity to look at a computational graph and skip some of a computation that are necessary。

😊。

![](img/318bd9616159378b3647e56c3ec79600_70.png)

![](img/318bd9616159378b3647e56c3ec79600_71.png)

And it does happen when， you know， if you have a forward computational graph and you take gradient with respect to that。

Imagine that you only interested in ingredient values。

 but not interested in say computing the loss function values。 actually。

 you can skip the loss function computation in a lot of cases。Another advantage of this is that。

Effectively， having a complete computational graph give you a lot of opportunities for optimization。

😊，Another thing that you might notice that that's the creation of Efdo session。



![](img/318bd9616159378b3647e56c3ec79600_73.png)

And得。

![](img/318bd9616159378b3647e56c3ec79600_75.png)

That program model， effectively means that。The place where you run this communication graph does not have to be on the same local machine that runs this python code。



![](img/318bd9616159378b3647e56c3ec79600_77.png)

And you know， you， you can imagine why。You know why this design is being bought by Google。

 Because in Google， it's really important for them to be able to have the scalable computations and also being able to have。

 you know， the excion part say on on a different machine or on a more powerful machine。

 while we can do some of the development on on a local laptop。 So that was like one consideration。

 imagine I have a local laptop that don't even come with a GPU。

 and have a remote session that contains a GPU。 What you can do is you can go ahead and send the data to the remote。

 There's a remote exc that really go and and run the computational graph and then。😊。



![](img/318bd9616159378b3647e56c3ec79600_79.png)

![](img/318bd9616159378b3647e56c3ec79600_80.png)

It gives you the computational graph results back in value form。

So this complete declarations and the separation of the computational graph from。

The and from the current interactive host APIs kind of helps in that perspective。

 It helps you to be able to organically send values。To a different place where real excion happening。

 but you still do some of a lightweight， you know， debugging and other things on your local process。

Of course， one， one of the things we all know is that， you know， today， Tenor flow。

I would still being widely used， but a lot of people prefer another kind of programming abstraction。

 which is Pyto。And and let's first take a look at， you know what Pyths programming instruction is。

 And let's come back and compare this declarative programming abstraction and。

And the Pys programming obstruction。

![](img/318bd9616159378b3647e56c3ec79600_82.png)

收。In part culture and needle as well， we are also adopting this imperative。

 We're also adopting this programming style。You can point that in order to run these computations。

 we are simply constructing the code like in here。 And we will first declare the needle do tensor。

 and then you compute exponential function， do a plus one。

 and then you might apply the things together。On one hand， you know。

 the combination graph on the left hand side looks similar。 And So what's happening behind the scene。

And what's the difference between this imperative automatic differentiation API versus the dec of computational graph API。



![](img/318bd9616159378b3647e56c3ec79600_84.png)

Instead， besides computing the computational graph， while we do V1， we concrete specify。

 this is value1 here。

![](img/318bd9616159378b3647e56c3ec79600_86.png)

![](img/318bd9616159378b3647e56c3ec79600_87.png)

And you know， and then in the next step， not only I create a computational graph node。



![](img/318bd9616159378b3647e56c3ec79600_89.png)

We are also computing exponential of B1。 No， exponential one is really hard to compute。

 But let's imagine 0。 And we will know that this one here。😊。



![](img/318bd9616159378b3647e56c3ec79600_91.png)

And we added， it's going be two。And at this point， we will know that this is going to be。



![](img/318bd9616159378b3647e56c3ec79600_93.png)

2英。So at each of a time stem。Not only we are constructing a computational web， but also。

 we are also computing the data along the way。 and we have introduced needle implementation as well。

 We know that， you know， in certain cases， we are going。

 we are eagerly evaluating that in other cases， we are doing this lazy tense approach where you don't necessarily have to eagerly evaluate that。

 But you know， you， you will be able to lazily evaluate the computations and get the data out。😊。

So the difference between this imperative automatic differentiation I or in other cases。

 called define and run， right， So define by wrong。 So， so as you define computations。

 you also go ahead and running the result。

![](img/318bd9616159378b3647e56c3ec79600_95.png)

It allows us to execute the computations as we construct the computational graph。

And also allows us to easily mixing the python control flow and construction at the same time。 For。

 we could write code like this， but we can say that if V4 do number high is bigger than0。5。

 I'm going to do V 5 equals v 4 times 2。 Otherwise V 5 equal v 4。

 So you can find that depending on the values of my intermediate computations， we could choose to。😊。



![](img/318bd9616159378b3647e56c3ec79600_97.png)

Dynaically construct my computational graph in one way or another。

 So people also commonly refer to this as a dynamic computational graph construction。

 as opposed to in a case of tensorflow API， it's called static computational graph construction。

This imperative automatic differentiation API is also now first being brought up by Pyotch。

 The earlier pioneer here is a framework called trainer that first introduce this concept defined by a wrong。

 And it's really Pyotch really take that idea and know， further develops it。

 make it and you know that becomes one of the most widely used thepre frameworkally。

So let's also pause a bit and try to compare the contrast。

 What is the difference of this improvable versus the decorative。

Programming style that we had in Tensor flow。 You will point that there are a few things that pops up。

 First all。In terms of。The optimization opportunity is actually in know programming Tensor flow when possible。

Gives a more opportunity for optimization。Foramp， if I'm going to go ahead program。

Our our things in this way。Effectively， if we are doing eager mode computations。

 every time if we compute this， we， we will have to go ahead and really get the value of get this value out。

So it will miss opportunities like Fho in the future。 if we look at this entire computational graph。

 maybe we can fuse those computation together because in an interactive environment。

 it's really hard to know whether or not this value is going to be referred by another component right Also if we do this and say hey。

 I'm only interested in V3， Of course， the V4 computation already getting a you cannot do things like that code ins in here。

😊，收。So， you know， it really， in terms of like optimization opportunities。The， the Tensorflow 1。

0 API actually is better。 You know says that is why， you know， in a lot of cases。

 people still prefer Tensorflow 1。0 in production because of case。 And also， you know。

 if you look at some of the machinery inference frameworks。😊，Or deployment frameworks。

 A lot of deployment frameworks still tries to take this computationalal graph declaration。

 execution approach， because that gives them more opportunities for things like memory reuse and other optimization as well。

😊，However， you know， why do people still want to use Pyth CPI， This is because。You know。

 it's much more friendly in certain cases， and it allows more organic mixing。😊，Of p。

Which is what we call host language。As well as underlying computational， computational。

 become view computation graph is another programming language。 effectively， if you look at。



![](img/318bd9616159378b3647e56c3ec79600_99.png)

Here， the first component， effectively， is what we call a tensorflow programming language that tries to describe the computational graph though。

And then， you know， you can only declare and then run the computation。

 So imagine that you want to do things like。If V 4 is bigger than 0。5。

 we are going to do one color of computation， otherwise another。Intens flow。

 you have to introduce a special kind of node like T F dot A F or T F dot。Yes， it's also loops。

Within the Tensor block communication group， in order to do some kind of computations。

 which is a bit cumbersome。Also， internal debugging。In lot of cases。

 one we go ahead and build neural networks， right， it's not necessarily that you' are going to get it right all the time。



![](img/318bd9616159378b3647e56c3ec79600_101.png)

So it could be very possible that you are going to take V 2。 And we're gonna to ask you。

 what's the value of V 2。 So， so people commonly will do things like print。



![](img/318bd9616159378b3647e56c3ec79600_103.png)

![](img/318bd9616159378b3647e56c3ec79600_104.png)

李 two英 here。But at this time point， we do not know what's the value of V2， right。

 because you don't even know what's the value of V1 in here。 So， so it's， so， you know。

 it's really when it's really hard to kind of debug the programming。



![](img/318bd9616159378b3647e56c3ec79600_106.png)

In Pyage or in a imperative A D API， you can directly go ahead and insert the print。



![](img/318bd9616159378b3647e56c3ec79600_108.png)

![](img/318bd9616159378b3647e56c3ec79600_109.png)

B2 here， because， you know， as we execute to this time point， the value of B2 is already known。

 if it realize underlying cache。That gives the opportunity to be able to， you know。

 interact with the bug。The ability to mix in the python code and the computational graph construction is also very helpful。

 there are advanced models like that this model called stochastic depths where you know in each of the iterations。

 we're gonna randomly flip a coin and trying to constructed you know neural networks of different depths。

 And that's really hard to be expressed in a static computational graph construction work。

 because you know， effectively， every time you computational graph is changing depending on the runtime executionions of the values。

嗯那。And this happens in things like bump natural processing， in some cases。

 where your computation web， if you unroll things around a circumstance。

 it can depends on the number of the the length of input， so。

The flexibility of this imperative automatic position that allows you to organically construct these dynamic computational graphs really gives the researchers much more ability。

 a bigger amount ability to be able to express the ideas easily in Python right so and and that really leads to the adoption of the framework。

😊，So， so you can find that there's indeed some form of tradeoffs between flexibility and ability to optimize。

 you know later there are techniques that that try to get even these kind of imp programming model into into a more you know efficient state and there are efforts like compils just in time compilation and other efforts that help us to move along the way and so so today if you look at the choices of programming obstructions。

 you'll find that this imp automatic still being you know it's being widely preferred in this case。

And it's， it's really interesting combinations of， you know。

 the ease of you the ability to be able to express the models that we're interested in and still being able to leverage underlying acceleration libraries to get the good amount of speedups。

😊，Okay。

![](img/318bd9616159378b3647e56c3ec79600_111.png)

So until now， we have talked about these programming instructions。 we have started three of them。

Cafe， which represents the first generation of different infr that allows you to do， you know。

 forward and backward propagation operations。Tsor floater that gives you the ability to be able to construct。

Comp graph。 and then you excuse them right also we can do like automatic differentiations by extending the computational graph。

I touch， which gives you the ability to be able to， you know。

 imperatively compute intermediate computations。And dynamically， constructed computational。

It will be useful。 We have discussed the pros and cons。

 but it will be useful for all of us to take a moment and and pause a bit and think about what are pros and cons of each of program abstraction。

 And imagine that， you know， you fly back。😊，To the time where in2013。

 there's not yet a lot of choices for defining learning frameworks。

 What kind of interface that you will design。To， to。

 to resolve the problem of both modular constructions of models。

 as well as expressing different kind of optimization algorithm and needs。

 And it would be a very useful sort exercise that I would encourage everybody here to do。



![](img/318bd9616159378b3647e56c3ec79600_113.png)

Okay， so now we have talked about the high level programming abstractions。Let's comeback。

And think about， you know。Imagine that now we have chosen the imperative automatic differentiation on dynamic communication graph as our programming model。

 and you know you have already started to work on needle as as the first part of a framework。

 as first homework that gives you the ability to be able to construct a tensor to amic operations among them as well as composing those tensors。

 then do automatic differentiation。However， you know， we have not yet。

Talk about how can we construct a neural network from， from all those tests。 Of course。

 and we can do that。No， using a lowest level API， we can take the tensors willll be able to。

 you know， do each of layers manually， just like what you did for homework 0。

However they are better approaches than had taken him。



![](img/318bd9616159378b3647e56c3ec79600_115.png)

And one of the things I want to remind everybody is that， you know， coming back to machine learning。

 when we talk about machine learning is's not a single cluster of saying that you kind of have to take。



![](img/318bd9616159378b3647e56c3ec79600_117.png)

Take it。 you have to go ahead and implement implement every product。 So machine learning itself is。

 itself is very modular。Specifically， every machine reaction list come from come with three elements。

 Its a hypothesis class。That allows you to be able to take your input and gives you a prediction。

 There's a loss function that takes the hypothesis。

 the label and try to measure how good your prediction is。And finally， this optimization method that。

 you know， for given loss function， high policies class。

 it is' going to try to find optimize parameters within that space of possible choices。嗯。

This kind of， you can find， at least there are three elements that are really independent from each other。

 right as we start to develop machine learning libraries。

These components are going to translate onto modular components in code that we will be using on composite other。

 And this， even， this is even true before the age of differently。And you know。

 we can pause a bit to think about how can we translate those modular components on code。For example。

 because we have this loss function。 So certainly that's the possibility of being able to machine learning framework to supply loss functions。

 And these have been very useful。 And in another framework that I did before called X boost hopefully some of you also use that framework。

 That's the ability for us to customize loss function So that know when we first developed actually boost。

 we only supported， I think regression analysis and there are people that are interested in survival analysis of time series。

 And they don't have to go ahead and build an entire survival tree boostosing package from scratch。

 they just need to go ahead and customized loss functions to be able to do that。

 So so that's one advantages thinking about those moduleular components you can go ahead and change part of your system hopefully with the minor effort。

 but gives you something that's much more powerful。😊。



![](img/318bd9616159378b3647e56c3ec79600_119.png)

![](img/318bd9616159378b3647e56c3ec79600_120.png)

![](img/318bd9616159378b3647e56c3ec79600_121.png)

![](img/318bd9616159378b3647e56c3ec79600_122.png)

If you think about the context of deep learninging。

 you will find that the deep even more modular in a sense that not only the can have these three components。

 Ipo this class loss function， not optimization method。The hypothesis class itself， is very modular。



![](img/318bd9616159378b3647e56c3ec79600_124.png)

So let's take this as an example of， you know， this is what you will typically see。



![](img/318bd9616159378b3647e56c3ec79600_126.png)

In our in a neural network model。 right， So when you go ahead and and look at different neural network implementations。

 sometimes you will see visualizations in this style or in a similar style。



![](img/318bd9616159378b3647e56c3ec79600_128.png)

So this is a diagram。That describes。

![](img/318bd9616159378b3647e56c3ec79600_130.png)

I would say depending on how you call it， usually we can call it a three layer residual neural network。

And， and it contains three residual blocks。 So the input goes into first residual block。

 then feed into second residual block。 Third one。 Finally， it's going to feed a fully account linear。

 There's a soft mass towards entropy。

![](img/318bd9616159378b3647e56c3ec79600_132.png)

![](img/318bd9616159378b3647e56c3ec79600_133.png)

That tries to predict in that that help us to do like a multi label classification， a soft。

 soft soft net。

![](img/318bd9616159378b3647e56c3ec79600_135.png)

That that help us to do like classification in a soft mass Los entropy fashion。



![](img/318bd9616159378b3647e56c3ec79600_137.png)

And if you look like these diagrams， you do not yet know like what exactly it does is each of the component correspond because。



![](img/318bd9616159378b3647e56c3ec79600_139.png)

When we build a needle library， the first thing， the only thing we learned is tensors。

And operation among tenss。 But residual block is not a tensor。 right， so we want to。

 we want to expand it a bit。

![](img/318bd9616159378b3647e56c3ec79600_141.png)

Each of reside your block。Can be composed as by input。That get fitted onto a linear layer。



![](img/318bd9616159378b3647e56c3ec79600_143.png)

A yellow， another linear layer。And the idea of residual block is that not only we want to be able to。

 you know， do the do the nonlinear transformation this pathway。

 you can also go ahead and directly add input onto add original input onto this sequence of linear box。



![](img/318bd9616159378b3647e56c3ec79600_145.png)

![](img/318bd9616159378b3647e56c3ec79600_146.png)

And and this is one of the most important breakthroughs in most important developments in the history of deploymenting。

 that help us to build a lot of the deep neural network models specifically in computer vision and it also have other names like highway networks and that and if we look at a recurringcurt neural network is also kind of a similar style where where you know。

 LTs have like a memory cell that memories that memorizes the past。So that's a research of blood。



![](img/318bd9616159378b3647e56c3ec79600_148.png)

And if you look at residual blocking find that， steel， we have those rectangular cells， right。

 that is not consist of cancers and testile operations。



![](img/318bd9616159378b3647e56c3ec79600_150.png)

![](img/318bd9616159378b3647e56c3ec79600_151.png)

So we can go ahead and expand them again。So each more linear layer， in this case。

Is going to contain an input。

![](img/318bd9616159378b3647e56c3ec79600_153.png)

Weight that that contains a linear layer。 in some cases， a linear layer also comes with a bioton。

 in this case， we are simply skipping a bioston force to keep things simple。



![](img/318bd9616159378b3647e56c3ec79600_155.png)

Do you have a linear layer that goes into a max module。

 And what you're going to do I' going to transpose your weight and do matrix application with that with that input and that that gives you the output in here。

 And this linear layer also。

![](img/318bd9616159378b3647e56c3ec79600_157.png)

![](img/318bd9616159378b3647e56c3ec79600_158.png)

Follows the conventional convention by Pyth and other library uses。



![](img/318bd9616159378b3647e56c3ec79600_160.png)

Similarly， a rail layer will take input。

![](img/318bd9616159378b3647e56c3ec79600_162.png)

No， try to take the maximum of input and0。 that gives you output。



![](img/318bd9616159378b3647e56c3ec79600_164.png)

So you can find that we can go ahead and expand， right， We can expand every residualud module。



![](img/318bd9616159378b3647e56c3ec79600_166.png)

In this diagram， and then extend every linear value in this diagram。 And finally。

 you're going to get much more。😊。

![](img/318bd9616159378b3647e56c3ec79600_168.png)

Much more deeper， right， in some sense or or a computational graph that contains many。

 many more operations。And you can find this， this， this this recursive degradation really modular。

 And we are when we are trying to build up your neural networks， we are not thinking in terms of。

 hey， I want to build it in one matrix location or another I thinking about those。😊。

Moular blocks like linear。 Now we are composing those module modular blocks together。

 using settings like residual net， residual module and so on。

 And it' also help us to think about how we can build our。Interverse design。

 by the help us to be able to build up those modules and then compose those modules together at this one important part。

To， to consider when we design interfaces。

![](img/318bd9616159378b3647e56c3ec79600_170.png)

To construct neural networks。If you're interested in learning more about resident there are two papers here that you can go ahead and read and the resident papers is arguing well the most sideted paper actually in the as well。



![](img/318bd9616159378b3647e56c3ec79600_172.png)

So。We are talk about。This compositional idea and the key one of the key data structure here is what called module。

In the next lecture， we're also going to implement the end module if you have used Pythch before。

 you might be familiar with this concept。

![](img/318bd9616159378b3647e56c3ec79600_174.png)

So effectively initial rectangular block here can be viewed as a module。

And this big rectangangleular block is also a module。 So， so when we design modules， effectively。

 it's a way for us to be able to compose things recursively together。😊。



![](img/318bd9616159378b3647e56c3ec79600_176.png)

It follows a common principle called Ten in Tensor art。

So the principle says that you know a module should take usually， you know。

 if it's a sequential part， it takes one tensor as input and it output one tensor In some cases。

 it might take you know two tensors， a few ten and output tensors as well。

The tensor intensor principle really helps us to be able to compose things together。

 so if every module takes tens as input and output the tensor。

 you will be able to take the output tensor and send it to our next module。

 So it helps it to do computations。😊，There are other things we need to support as a part of the end module。



![](img/318bd9616159378b3647e56c3ec79600_178.png)

Specifically， when you look at linear。You can find that we have kind of trainable parameters or weights right that attach to this module。



![](img/318bd9616159378b3647e56c3ec79600_180.png)

And that means that we want to be able to cut you know。

 in order to be able to update the weight in our in our training procedures。

We will need to be able to inspect those modules and get those trainable weight out from those module collections。

Of course， we also need to find a way to initialize the parameters here as well。

So that's kind of like an module。

![](img/318bd9616159378b3647e56c3ec79600_182.png)

If you're thinking loss functions。😊，We can actually view loss functions as a spectral counter module as well。

 usually there's module plus software cross entropy that gives a hypothesis prediction the label。

 and's going to output a scalar value and， you know， tensor of rank0 can be viewed as scalar value。

 So it's also output tensors。

![](img/318bd9616159378b3647e56c3ec79600_184.png)

That that can be used to run predictions in here。And it follows what we call Tensa in scaleal。

 scal of。

![](img/318bd9616159378b3647e56c3ec79600_186.png)

AI convention， right， So we will be able to compose up the the modules for。



![](img/318bd9616159378b3647e56c3ec79600_188.png)

Or getting you know， input prediction。 And then you。

 you compose that prediction with the loss function label。 It gives you a loss function。

With this principle， it gives us a bit more compasibility。

 if we want to do multiple objective functions。Imagine that， you know。

 I want to have a neural network that's able to both give you。

Buning boxes as well as classes in that buning box。 That's one instance of my object prediction。

What would what youre likely going to have're going to have kind of one objective function module that try to。

 you know， predict like bounding box closeness and another objective that predicts the class。

That measures how good your class predictions are。And because we follows a tensing scala out。



![](img/318bd9616159378b3647e56c3ec79600_190.png)

Priinciple， so we can apply those two modules。 and we can just add loss  one and loss two together。

 maybe in a weight of fashion。 so the， the ability we can leverage our， we。

 we can leverage this modular feature to help us to directly as together。

 And then you just call the value do backward to compute the gradient values。



![](img/318bd9616159378b3647e56c3ec79600_192.png)

There's also， that's also another thing that that we wont consider is that in certain cases。

 when you are doing when you're doing training and when you're doing inference。

 that might be a slight difference in terms of， you know what kind of operation on perform。

Wpo in case of the loss function measurement， Of course， in training。

 you do want to compute the output loss functions。But in predictions， maybe you don't have。 So。

 so usually these modules sometimes come with a training or or inference mode so that it allows you to have a slightly different behavior between training and inference。



![](img/318bd9616159378b3647e56c3ec79600_194.png)

Okay。That's loss functions。Besides source function。

 we still need to be able to for given neural network models。

 We want to be able to take in a model and then be able to perform weight updates for them。

 So for a given model， we want to be able to。

![](img/318bd9616159378b3647e56c3ec79600_196.png)

And there are increasingly weighted attached to each four modules。



![](img/318bd9616159378b3647e56c3ec79600_198.png)

Want to be able to first take a list of weight from the model themselves。

 and then want to be able to perform updates of those。



![](img/318bd9616159378b3647e56c3ec79600_200.png)

And this is usually encapsulated in an abstraction called optimizer。



![](img/318bd9616159378b3647e56c3ec79600_202.png)

That takes in a list of ways。 And sometimes you also need to keep track of service date like W momentum in here。



![](img/318bd9616159378b3647e56c3ec79600_204.png)

![](img/318bd9616159378b3647e56c3ec79600_205.png)

So in in this case， it's right， the optimizer will will need to be able to take in the model query。



![](img/318bd9616159378b3647e56c3ec79600_207.png)

How many weights are there。 So the weights will include W 1， W 2， W 3 and W 4。

 and then it will it will perform the updates either in in some of the rules。

 right either SGD or I switch momentum and updates in here。



![](img/318bd9616159378b3647e56c3ec79600_209.png)

![](img/318bd9616159378b3647e56c3ec79600_210.png)

Another thing that optimizer need to do is we need to be able to create and keep track of a states。

 For example， the model themselves only come with the weight。😊。



![](img/318bd9616159378b3647e56c3ec79600_212.png)

But in order to optimize those models。Those ways， well need to create like momentum variables。



![](img/318bd9616159378b3647e56c3ec79600_214.png)

And those momentum variables are been keep are being tracked by the by the optimizers in their internal states as well。

Besides the one of the consideration optimizer is that we want to consider regulation factors in certain cases。

 for example， maybe want to want to think about what is the weight。



![](img/318bd9616159378b3647e56c3ec79600_216.png)

What what is the value of the， you know， we want to apply all two regulations。

 for example to make sure that the weight value of。



![](img/318bd9616159378b3647e56c3ec79600_218.png)

Of the each weight values， L2 norm is not too large。

 So the two weight that we can incorporate this regular addition turns on a framework。

 The first way is we can implement as part of loss function。

 So you just say loss equals loss plus Lada L2 norm of the weight。 So that then certainly possible。



![](img/318bd9616159378b3647e56c3ec79600_220.png)

And in certain cases， you kind of have to do that because in more complicated。

 in more complicated gradient calculations， like in certain cases。

 people might want to be able to compute the。

![](img/318bd9616159378b3647e56c3ec79600_222.png)

![](img/318bd9616159378b3647e56c3ec79600_223.png)

L2 norm of the gradienting value。That case， you kind of need to directly do all of my differentiations and incorporate it as part of your weight loss function。



![](img/318bd9616159378b3647e56c3ec79600_225.png)

Another way is you can simply incorporate your update rule in optimize update。 example。

 if I only care about weight L2 regulations， you can directly change your update rule to incorporate work call wait dicator。



![](img/318bd9616159378b3647e56c3ec79600_227.png)

![](img/318bd9616159378b3647e56c3ec79600_228.png)

That that allows us to do this。 So effectively， this is a way indicator that that correspond point to the L two non regulation that we talk about。

 This is sort of very typical in a lot of the optimizers。



![](img/318bd9616159378b3647e56c3ec79600_230.png)

Besides the weight。updatesd。And optimizers， another thing that we want to think about is how we are going to initialize each of the parameters in in our space。

 right， So the initializations。Do need to consider。

 especially we need to consider the auto magnitude of initialization。

 because if I'm building a very deep neural network。If you are initializing the ways to be too small。

 after the few layers propagations， your values will get en close with0。

If I initializing the the value to be too big， then after fewer layer propagations， my value。

 our value will explode， right will become very big。

So most of neuralne libraries come with a set of co institutionalizational routines that try to control the magnitude of the weight。

 depending on the neuralne architecture so that overall overall that tries to make sure that overall magnitude of values do not change very much。

And for a different kind of wayss in your neural networks。

 like whether it's a bio term that you just add off that with activation value。

Sometimes you might have running some of me and bearings that help renmalize your。

Yeah on neural networks。As well as the weight for like poly connect layers and convolutions。

 there are different ways for us to neutralize。 Usually bias turns can be in to 0。 for example。

 convolutional weight and matrix navigation weight usually use uniform distributions or gaussian distributions。

 which are automatically depends on input and output。

And usually in can be folded in the construction phase of random module。



![](img/318bd9616159378b3647e56c3ec79600_232.png)

Besides the besides the elements that we talked about so far。

 one of the important element that we still need to take care of is the data load。

 So not only we want to be able to build a model， we also want to have an effective data load that feed the model training in an efficient fashion。

And there are different ways we can do data loading。 for example， in， in certain cases。

 we want to be able to per process and augment data set by and randomly shling the input and transform the input。

And， you know， different data augmentations can account for a significant portion of prediction accuracy boost actually different models。

 So， so actually， if you look at most of the machine learning training pipelines。

 the data augment is a huge part of it when people do things like， you know。

 fine transformations on images， rotating， jittering to make sure that we get bigger we get a bigger input space and models being robust to those kind of transformations。

One of the things that you want to notice that this data loading augmentation is also composition in nature。

 right so we could just simplyly build a module that simply do random rotation and then another module that do since the crop sites。

In a， in a sequential manner， and we can compose them together to get a more powerful pipeline。

 So you don't have to design a pipeline that just that that that that's doing both， right。

 So you just need to have a。Single step pipeline。 That' wow。

 another component together to get your all end to end that pipeline。



![](img/318bd9616159378b3647e56c3ec79600_234.png)

Okay， so coming back and summarize。我方的。We have talked about a lot of things in the second part。

 talk about end down module。 It help us to be able to compose up the neural network libraries。

 We can also talk about N down module can help us to build the loss functions in here。



![](img/318bd9616159378b3647e56c3ec79600_236.png)

Bypassing parameters ingredients to optimizer， we will be able to go ahead and try out different color optimization methods。



![](img/318bd9616159378b3647e56c3ec79600_238.png)

![](img/318bd9616159378b3647e56c3ec79600_239.png)

There are different forms of initial addition we can do to make sure that the weight values are being initialized correctly。

 Finally， there are data load and pre processingcesing steps that help us to the data and augment away and feed it to the training pipeline。

And this really， this， this summary really highlights how modular the discipline models are。 right。

 So that is really one the reason why discipline kind of dominates a lot of machine learning fuel in a sense that the cost of trying out new things is really no。

 right So if imagine that I'm care only care about， you know，m doing detections。

The developer and the scientists do not have to go and rebuild the entire restnet or mobile net of scratch。

 You direct， we be able to directly use a backbone of restnet mobilenet。

 put a detection loss function in the end。 and then you will get you。

 you will be able to experiment into a pipeline there。So。

 and if I'm only really interested in developing new optimization method。

 like a ver Adamom for neural network training， we just need to go ahead and replace optimizer part。

So this modular nature is really amazing that help us to be able to build different different solutions together and。

 and also put them together。 so， so everything kind of comp well with each other so that we will be able to。

 you know， customize one part while working together with a restaurant to get the to get an end solution。

😊，And that， that is kind of like one of a cigarette sauce。 Why， you know。

 deep learning and a lot differently firm us actually kind of come back and dominate a lot machine learning。



![](img/318bd9616159378b3647e56c3ec79600_241.png)

Of course， you know there could be other modular components that we have not yet covered today。

 including things like how you can do learning reschedule。

 there are components that might help with things like hyperparal tuning and so on that would certainly love us to as an exercise come back and think about what other possible moduleular components other than the things we talk about today。



![](img/318bd9616159378b3647e56c3ec79600_243.png)

So in the end， I want to， I want to come back and revise the programming abstractstruction。

 And now we have talk about the modular components and how we can use the how we can use different kind of modules。

 right to compose up the different acceleration。 Let's come back and talk reversevis the abstractstruction again。

I'm really trying to think and appreciate， you know， how this kind of layer wise composition helps。

 If look at the cafe 1。0 API， You can find that a layer API in here。😊。



![](img/318bd9616159378b3647e56c3ec79600_245.png)

And this couples two things， couples the gradientding computation。And module composition。So。

In order to for us to find or build a restland in here。Well， it's kind of a bit complicated because。

I can go ahead and introduce a residual layer。But then we will need to be able to define a gradientding computation for residual layer。

 which is kind of non trivial。 right， One of the key observation that we make in need and in the second generation framework。

😊。

![](img/318bd9616159378b3647e56c3ec79600_247.png)

第是。We can separate the grading computations and module composition。In two level of API。

In the case of needle and pyt as well。The computational graph construction and automatic differentiationation of gridding computation。

Is being handled by cancers。And computational graphs mount tense。However。

 in order to modulate compose things together， while introducing this concept of the end module and a module can contain things like residual module that effectively more cause grain than the lower level ten level operation。

So by separating these two concerns of how we want to be able to compute gradient and directly relying on another in library to do that。

We will be able to focus on modular compositions in a much more simpler fashion by simply defining the forward computations of all the intermediate modules and then use automatic differentiation to handle all the gradienting computations。

And that actually really helped us to be able to develop more model easily。😊，And。And you know。

 this might may be obvious now that you have see the designs。

 but it's really interesting to come and reflect， you know。

 how the design decouples things and how this approach help us to be able to not only do automatic differentiation more effectively。

 but also composes the modules in more organic。开。So that is the end of today's lecture。 Thanks。

 everybody for coming。 The next lecture， we are going to really get our hands dirty and implement some of the high level designs we talk about this lecture。

😊，We'll see you in the next lecture then。

![](img/318bd9616159378b3647e56c3ec79600_249.png)