# CMU《深度学习系统｜CMU 10-414714 Deep Learning Systems 2022 fall》中英字幕 p04 -05-Lecture 4 - Automatic Differentiation.zh_en -BV1ERtYepEpy_p4-

Okay， hello everyone。 welcome back to D Asance。 Everything implementationmentation。

 My name is Tian Qichen。 You can come Q。 It's great to bring this class with they Co together to everybody。

 and hopefully we enjoy journey our building our deep instruments from scratch。😊，So today。

 we' are going to cover a very important part of our entire lecture sequences。

 We' are going to tell you a bit about how do we do automatic differentiation。😊。



![](img/1602e205bab7500955e1fd97cc7097a3_1.png)

So first of all， let's start to recap on you why do we need to do automatic differentiation and different differentiation methods？

Then the second part of lecture we will cover a main method called reverse mode automatic penetration that is being used in modern airplane firms。



![](img/1602e205bab7500955e1fd97cc7097a3_3.png)

So let's start with the first one。So how does automation fit into the general machine learning workflow？

If we recall a previous two classes， we have talked about you know the basic elements of machine learning。

 or you think about the machine learning action， usually you want to think about them in a few perspectives。

First4， we are thinking when you think about hypothesis class that is for a given input X。

 how do you get predictions for the given input？For normal cases in the last few lectures we talk about multi layerer perceptionceptrum and single layer perception dis in the following lecture we're going to talk about different hypothesis class like conversion neural networks。

 transformers and gene neural networks that give us you know for the given input that transform a given input to the prediction。

Of course， for a given given hypothesis class there are still several things that being undetermined。

 specifically， initial hypothesis will be parametermetized by a set parameter seeta。

And we will need to learn a good seat from training data。So the second element in machine learning。

 usually that you will see is a loss function。The loss function defines for a given hypothesis class and parameter seeta。

 how good our prediction is。 and usually we measure it on in terms of， you know， training data set。

 So we will try to effectively try to find a set of c that minimize this loss function on the training data set。

 and then we will use that learn parameter seeta to run prediction on future data set we see。😊。

So loss function is the element that measures how good we are。Finally， for a given loss function。

 we will still need to be able to find a good car that minimizes that loss function。

That's where the third perspective comes in which is optimization method。

Most of the machine learning optimization algorithmerson actually in terms of deep learning。

 usually takes this form of stochastic gradient optimization。

 so effectively we will try to take loss function and try to compute gradient of a loss function with respect to the parameter theta。



![](img/1602e205bab7500955e1fd97cc7097a3_5.png)

![](img/1602e205bab7500955e1fd97cc7097a3_6.png)

Now that gradient function is a direction that helps us to， you know。

 usually it increases the loss function by a  tiny bit。

 and our goal is to decrease it right so you are going to take an negative gradient direction in a small step。

😊，And most of the method we use are usually also called stochastic gradient method。

 That means that we are not trying to take computer gradient over the entire data set。 Instead。

 well try to take a mini batch of samples from the data set。

 and they will try to directly take a small step towards the gradient compute it on that mini batch。

 And this usually cause stochastic gradient method。Of course。

 depending on the particular updated aggress， the update rule can change in this particular case。

 we are trying to show a basic form of to gradient descent。 and in the future lectures。

 well also talk about other forms update， including things like momentum based method and adaptive gradient method。

But in all those cases， the key and the fundamental problem that we need to solve here is how do we compute this gradient of of loss function research vectorta。

 And that is the center of almost all the machine learning machine learning algorithms that。😊。

That we use to learn at for given the asset。And of course。

 there are different ways for us to compute this gradient。

When I was an undergraduate student working on machine learning。

 the basic skill that we need to learn is how do you manually derive right the gradient for loss function？

Luckily today， you don't no longer have to because there are a lot of tools。

 they help you to do that automatically。 And for， to be honest。

 for the given complexity of models you are dealing with today is almost infeasible to derive the gradient by hand。

😊，So today， our goal is trying to talk about some of a methods that help us to get to those gradient a more automatic fashion or pragmatic fashion。

😊。

![](img/1602e205bab7500955e1fd97cc7097a3_8.png)

To begin with。Let's start to think about how what is the easiest way to computer gradient and when we think about gradientding computations。

 the first thing that we might not think about is how do we do that starting from a definition of gradient。

If you recallil a calculus class， you might remember that a partial differentiation of a function。

 so in this case this function F， we are using F to denote the loss functioning here。

AndWe are were interested in part of derivatives or with respect with one over parameters right。

 so a gradient。Of function seeta effectively actually can be can be defined as partial derivatives。

Seta 0，西ta 1 F。你的。I shall seeta 1 have theta。I shall see in。F seeta， right， So， so effectively。

 if we are able to compute the partial derivative of a function with respect to a single parameter axis。

 then we will be able to compute the entire gradient。😊。

So let's start by remembering our calculus class and trying to find what is the definition of Pyth grade。

😊，So this is defined as fault。 right So for given see。

 what we're going to do is we're trying to take a small step。

At the highest direction of of my parameter space。 So in here， E of I。

Is a unidirectional vector that's 0 everywhere and one in one places。

And this is the ice element in here。 So effectively。

 ER I is a unidirectal factor that that points to you know that particular parameter dimension。

And we're trying to take a small step along that damage。

 were trying to then we will compute the difference between F theta plus optional E of I。

 subtracting F of theta。 Okay， then we're going to divide it by the step size we are taking。

So the partial derivative is defined by taking limit of this a to 0 and， and， you know。

 compute the difference and divided by the a。 Okay， so this is a formula that's operationalable。

 So what we can do actually is we can try to computefuse this formula compute the gradient numerically。

So， you know， we will be able to pick a see I， pick。

 pick EI and optional compute F theta plus EI and subtracting that I F。 Okay， and divide by optional。

 And if you pick a small enough optional， as' gonna approximately gives you the gradient。

 So this is also called numerical differentiation method。

 because we are trying to effectively do it by numerically， right， by definition。😊，In practice。

 we really want to approximate the gradient this way。

 There is a more accurate formula show on the second second part。

 So instead of trying to subtracting F theta plus optional EI， subtracting f of theta。

 we are subtracting F theta minus optional E I， and this usually gives you a more accurate estimation。

To see， why is the case。Record that in your calcu stars。

 you will know that F of theta plus delta can be written as F of theta。嗯。Plus。The first all gradient。

 right， so in this case that let's try to do a one dimensional version， so it's easier。And plus。

The 201 F second all gradient。Data squared us。All of。Data。Qu yet。

So if we plug in delta equals optional E of I and delta equals optional minus E of I。

 what we will find is that this formula。It's going to give us effectively it's going to have the second turn in here canceled out because regardless whether whether the noise plus youre plug in no positive optional E of I or minus optional E of I。

 this second order turn is always going to be the same。 As a result。

 if I'm going to use this to approximate my gradient， you will find that you know the error。

 the order of error is in the order of o of optional square while if you use this formula to cross my gradient。

 you will get a higher order error turn of o of action。

 So usually if you really want to do numerical computations of gradient。

 you want to take the second method that gives you a higher at more accurate estimation of the gradient numerically。

So this is a method that actually， you know， we can use to computer gradient。

 but it is not a method that commonly used in practice。The reason is that， you know。

 because in a lot of cases， it will suffer from numerical America because， you know， in this case。

 we really need Epome to be small to compute computer gradient。

The second reason is that remember for each of the I in here。

 we kind of need to run run the computation of theta plus optional I for each of the I exit here。

 right so if have n parameters， effectively we need to run two times an evaluation of F。

 I remember in our neural network that means that I want to run two times an forward evaluations of my function。

 in order to really get a gradient which is really cost So usually this is not formula that's been used in practice because it suffers from the neuro error and less efficient compare compute。

😊，However， it is a formula that's still being very widely used actually in practice for other purposes。

The reason that why we want to use this formula is because it's really straightforward to the computer。

 so it's really easy to get it right。😊，While if you want to learn other automatic penetration methods。

 while it's okay to still understand everything you might implement in some way， you know。

 and we want to verify whether or not we implement correctly。

So numerical differentiation is commonly used to do gradient checking or so it's being used to check if we have an automatic method that computes gradient。

 We want to check with our implementation correct， okay。



![](img/1602e205bab7500955e1fd97cc7097a3_10.png)

I in practice， if we want to do that for each of the c I。

 the numerical gradient computation can still be very costly if we have a lot of imperparness。😊。

So instead， we'll use another form。That is a bit generalized from the numerical gradient computations。

That help us to check the gradient correctness。 The idea is that instead of trying to pick E of I。

 we' are going to pick a data function， a data vector and this vector。

 you can pick it randomly from the union board here。😊，And by the same derivation。

 youll find that this formula holds okay for， for any of the data here。

And so in order to track the gradient， what I will do is our will first plug in。The gradient by。诶系。

Auto gradient。😮，Tool， right， So my autograding tool will be able to supply the green on the left hand side。

 I'm going to pick。A data function， a data vector in here。

 And I'm going to compute F e F seatta pass action data and F seeta minus e data and compute right hand side of a formula。

 I'm going to check if they are close to each other， okay。So we can do that for a few cs。

 randomly sample from unbo and that that sometimes usually sufficient cover all those gradient directions。

 And it's being a very good。You test kit for to check。

 you know whether implementation of automatic differentiation is correct and you want to really learn this formula because you are going to use it also in your homework so that before you really submit your homework solutions。

 you can use this method to check whether or not my gradient computation is correct。

 this is also a method is used by most of the different framework to check their implementation of automatic differentiation。

😊，Okay， so that's numerical gradient numerical gradient and numerical gradient checking。😊。

Although it's not something that we widely use in practice。

 it's a very useful tool for us to confirm the correctness of our implementation of gradient computation。

So let's move on to a second kind of way to computer gradient。

 And this is kind of a typical way that I will do before automatic ination is becoming popularopular。



![](img/1602e205bab7500955e1fd97cc7097a3_12.png)

So effectively actually， what to do is want to do it by hand。 So how do we do it by hand。

 We're going to go and write down the formula of this F function。

 and I'm going to try to derive you know， symbolically what the gradient function looks like。😊。

And of course， in order to do that， I need to apply several gradient derivation rules， right。

 So including this additional rule that derives， know what is the gradient when you want to compute a gradient of sum of two functions。

 What is a gradient of multiplications of two functions and a twin rule。

 What is the gradient when you compose function together。😊。

So were gonna apply those rules to derive gradient。 Of course。

 it's really hard to do that manually for， you know， a complicated model。

 So we're going to do that for a simple case。 And let's assume that we' are only going to do that for a product of0ta。

 So in here， F of theta equals Cta 1 times Cta2 times Cta 3 and timesta okay。😊。

And we're interested in partial derivatives with respect to case。Pze parametering here， C do， okay。

So in order to do that， we what you find is you want to apply the product rule。In here。And。Actually。

 it's， actually， it's not that。 Yeah。 So so it's not even product。

 You can directly try to derive the partial derivative here。 If you look at， you know。

 my result is Cta 1 times Cta 2 times Cta n。 And what is the gradient if we want to take respect。

 take gradient with respect to Cta 2。 The gradient is gonna to be Cta 1。Comalm seat 3。Tos C time。

 Okay， so effectively you want to write it out in a formula。

 you will find that the gradient with with respect to C K is's going be the product of all the parameterss。

 except C K。Okay， so seems that for this particular function。

 it's really easy for us to go and manually derive the gradient。

 So that is also for a lot of past machine learning works。

 That's how many people derive their update rule， not necessarily gradient， but in a similar fashion。

 You want to derive。 you know， what is the local optimized maximum up。

 holding other things to constant and， and， you know， this kind of grid de is quite common。😊，However。

 you will start to look at this formula and if you want to go and directly apply this formula to compute ingredient。

 you'll still find there are several issues in here。😊。

In order to compute each of the partial gradient of seeta with respect to a partial C tape。

You'll find that I will need to do n minus2 my applications。

And I need to do that for each shoulder parameters。

 That means I need to I need to do n times and minus-2。

 which is a quadratic number of mys with with to the input parameters。However。

 if you want to do that smartly， you will find out that if in order to compute the partial gradient with respect to all thezeta。

 I only need to do about n times， my invitation said。The reason why this。

 you know manual symbol derivation will cause so many duplicate computation is because there are some competition that can be reused among those partial derivatives that are not being reused by simply。

 you know， writing down this partial symbol differentiation formula。😊。

Okay so I want everybody to keep that in mind and you want to keep that question on ahead。

 We' are also going to talk about automatic differentiation methods in the next few slides。

 You want to ask what is the relation between this symbol differentiation and forward and backward automatic differentiation Now it is actually a relation and you know。

 in certain cases， you can you can derive automatic differentiation method by view them as a symbol differentiation plus some form of simplification。

 Okay so keep that in mind。 And now let's move on to the first automatic differentiation method。

 But before we do that， let's start to introduce some basic tools that we are going to use in this class。

😊。

![](img/1602e205bab7500955e1fd97cc7097a3_14.png)

And if you have used somewhat different in before， you have might have already heard a term called computational。

So computational graph is in the center of almost all the machine learning frameworks。

 and its also kind of an important tool for us to go and derive automatic differentiation methods。

So for a computational graph effectively is a directed。😊，A sick click graph。

That it' used to represent the computation that is being carried out for a certain function。

For example， this is a computational graph that represents this particular computation。 Of course。

 for a single computation， there could be different ways of computational graph because you know。

 if you are to compute the say， multily of three elements， A， B and C。

 you can multi A and B together， then multi that by C。

 or you can multi B and C together that will correspond to two computational graphs。

 So computational graph also specifies a bit about know the order of executionion in certain sense。😊。

Each of a node in a computational graph represents an intermediate computation。 for example。

 this particular node represents this log computations that takes in the value of VR B1 and outputs value V3 that's getting inputed into another computation B6。

So each one node represents intermediate value in the computation。

 and edge represents the input output relations among those computations。😊。

So each of a computation graph computation node will have input edges that represents input onto them and their output edges represents。

 you where their output goes into。So let's walk through this computational graph on the left hand side and try to manually evaluate this computational graph。

 I're going to do this because it's going be helpful for our future cases on deriving automatic differentiation。

😊。

![](img/1602e205bab7500955e1fd97cc7097a3_16.png)

![](img/1602e205bab7500955e1fd97cc7097a3_17.png)

So on this particular case。😊，Let's assume that I want to I'm interested in。Back all2 and 5。Okay。😊。



![](img/1602e205bab7500955e1fd97cc7097a3_19.png)

And the way that we're gonna to inver the computational graph is， I'm going to place。😊。



![](img/1602e205bab7500955e1fd97cc7097a3_21.png)

Toing here。And5 in here。And then I'm going to walk this graph in this topological order。

So first need to look at V1。 we know that V1 equals x in here， so V1 equals true。

Then I'm going to look at V2。And v2 equals 5。Okay。😊，Then I'm going to look at B3。 in this case。

 v3 takes V1 as input。And compute the logarithm of the result。 And now log up to in here， this。

 this number， you know I I， I do not try to compute it by by hand。 but。

 you can always open up a Python or other tools to compute it。And then。V 4 equals V1， multily V2。

 So in this case， V 4 equals 10。Then V5 is a signine of v2 and sign of 5 equals this number。

 v6 is addition of v3 and V4。It gives us result and finally B7 is V6 subtracting V5 so that's my final result。

Finally， I'm getting a result of why you。Okay。😊，So it might be a good good thing if you have a paper on hand and trying to do it and follow this composition graph chase。

 you kind of get a sense of， you know what it takes to evaluate the composition graph。

 So for a computational graph， what you can do is you can put your value on the input side。

 and then you're gonna to walk the computational graph in topological order for each of node。

 you will try to take the input value， which are already computed because were walking this in topological order。

 and we're going to compute value， output value of that particular node。😊。

And then after you Cha the entire graph， you will be able to get all values on the very end。

So this is a tool being used by most of the deploying frameworks representing represent computations and it's also a very useful tool to derive automatic differentiation。

 Okay， so now we are ready to introduce our first automatic differentiation method。😊。



![](img/1602e205bab7500955e1fd97cc7097a3_23.png)

And this method is called forward mode automatic event。😊。

So let's assume that we're interested in the partial derivatives of the intermediate value。

With respect to the first input， in this case， X。And we to because ofively derive this value for each of a graph node。

 as a name hint want to derive it from a very beginning。😊，So first four。

 let's try to see what is V1 doting here。And by definition。

 we know that we are in V1 dot equals partialsenal V1 partialial x。In this case。

 we know that V1 equals X。 So， so V1 dot effectively equals。And here equals one。

So that's what I want to derive from beginning because， it's really easy to get those answers。

 at least for the called input pyramid。😊，Similarly， v2， we know v2 equals x2。

 So have nothing to do with x1。 So so in this case， v2 dot equals 0。Okay。😊，Now let's look at V3 dot。

😡，We know that v3 dot equals partial V3。

![](img/1602e205bab7500955e1fd97cc7097a3_25.png)

Partial X1。While， V3。

![](img/1602e205bab7500955e1fd97cc7097a3_27.png)

Its a function of V1， right， So it's also equals partial log。Of V1， partialial x1。

And by taking Q rule， this will equal v1，01 times partial V1， partial x1。



![](img/1602e205bab7500955e1fd97cc7097a3_29.png)

Okay。And then you will find that this green value take two parts right first part is actually the partial derivative。

😊，Obviously， with respect to B1。

![](img/1602e205bab7500955e1fd97cc7097a3_31.png)

And second part equals v1 dot by definition。So effectively。

 my V3 dot equals V1 dot divided by V1 here。And if you look at V1 dot， the value is 1。

 V1 values is 2， so the V3 dot equals 0。5。ok。😊，Now let's look at V4。😡，Similarly。

 we can apply a multi rule in here。 right， So we know that V4 equals v1 times v2。

 So partial partial x1 v1 times v2 by applying multi rule， we know that equals。



![](img/1602e205bab7500955e1fd97cc7097a3_33.png)

Poial B1， partial X1。Times V2 plus partial V2， partial X1 times V1。Okay。😊，And this is V1 dot。

And this is V2 dot。 Okay， so that's why we are getting this formula in here。And if we look up the V1。

 V2 values on the left hand side and V1 dot V2 dot value here will get。



![](img/1602e205bab7500955e1fd97cc7097a3_35.png)

The partial derivative of the equal was fine。

![](img/1602e205bab7500955e1fd97cc7097a3_37.png)

Similarly， for V5。That's sine， right， So what we're going to do is the the partial derivative of sine is cosine function as equals B2 dot times cosine P2 in this case 0。



![](img/1602e205bab7500955e1fd97cc7097a3_39.png)

And。B 6 and B7 can be derived in the same way。So I would highly encourage everybody to you know。

 open up a pen paper and trying to follow these derivations because it gives you a much better sense of what's going on in this forward mode automatic。

And finally， you can find that as we walk through each of a computational wrap node in the end。

 we're going to get the 7 dots right， the partial derivative of a final node with to the first input。

 and that is a value that we're getting here。😊，So we can point that。

 you know the why we are calling the forward model automatic differentiation。

 And so the idea is that for each of us step。We are trying to starting from a beginning because you know for the parameters。

 it's really easy to get those gradient if the parameter equals the input the parameter that we want to take the differentiation with respect to then the value equals 1 Otherwise the value equals 0 then for each of the intermediate comm of graph node we trying to reducing the gradient values to the partial derivatives of that node with respect to the input。

And the forward mode automatic depend value of its input。

 so so each of step we are doing this recursive computations。

 as long as I know the V dot V dot of my input parameters input nodes。

 then I will be able to compute the V dot of this current node and and so on。

 So after you work through in cloud computational graph， you will get the V dot for all。😊。

And and in this case， you can also find a competition gun comes very handy。

 so you can imagine that you know， how you would want to implement this algorithm using a programming language like Python。

😊，Okay， so this forward mode A D， on the other hand。

 youll find that the forward mode A still comes with a bit of limitations。

 If want to compute the gradient for like a neural network model。



![](img/1602e205bab7500955e1fd97cc7097a3_41.png)

Specifically。😊。

![](img/1602e205bab7500955e1fd97cc7097a3_43.png)

If ever a function that takes n inputs and K outputs。

A forward mod is really good if only a small and case lock。

Because it allows us to be able to compute the gradient values with respect to， you know。

 one of the inputs。In one pass。 So if any is more， but I have a lot of outputs in my， in my function。

 then I will be able to run one pass to be able to get all the gradient of output。

 reach back to that particular input。😊，However， if we have certain input parameters。

 in order to get a gradient， we will need to run un forwardward a passes to get a gradient with respect to each of the input。

Okay。😊，And in a， in a deep learning case， we mostlyly care about。1 output scals， right。

 So we are interested in a scalar output where the loss function is scal in here。

And a lot of input cards。So we kind of need a different method in order to solve this kind of problem differently。

And this is a method that we'll talk about in the second part of today's lecture。

It is called reverse mode automatic differentiation。



![](img/1602e205bab7500955e1fd97cc7097a3_45.png)

Okay。😊，So let's start to derive reverse mode automatic differentiation and if you have a piece of pen paper by your hand or if you can get a slide on your side。

 I would highly recommend you to follow this slide of derivations。

 we're going to derive each step by step and trying to ask yourself。

 can you clearly confirm that it is the case in each step of derivations。

And this is going to be the majority of content， actually， for today's lecture。Okay。😊。

So in order to compute。The gradient of a single scalar output value with respect to a lot of inputs。

We're going to define a different term called air joint。In here。

 where the edge on turn is defined as the partial of derivative which from the output scar with respect to each of intermediate value node。

Just like forward Model A， we will be able to derive it in a more recursive fashion。 in this case。

 as the name hints to order derive it from the end of the computational graph as opposed to a beginning。

 because the way that edge join is being defined。😊，ok。😊。

So let's start from an end and let's ask know what is edge on B7？In this case， by definition。

 A on V7 is partial wide。

![](img/1602e205bab7500955e1fd97cc7097a3_47.png)

Partial V 7。 And we know that y is V 7。 So we， you can find that， yeah。

 the first step is really easy。 The partial derivative， the edge on value is one， in this case。



![](img/1602e205bab7500955e1fd97cc7097a3_49.png)

Okay。😊，Now we have derived partial the adjo value of B 7。 let's look at adjo value of B6。



![](img/1602e205bab7500955e1fd97cc7097a3_51.png)

![](img/1602e205bab7500955e1fd97cc7097a3_52.png)

And we are interested in partial why。

![](img/1602e205bab7500955e1fd97cc7097a3_54.png)

I shall be 6。How do we do that， We know that， you know， V 6 V V7 is function V6， right， so。

 so effectively， we can apply train rule in here， and we know that it will equal partial y partial V 7。



![](img/1602e205bab7500955e1fd97cc7097a3_56.png)

And then， Pado V7。H shall we 6。

![](img/1602e205bab7500955e1fd97cc7097a3_58.png)

Okay。😊，And if you look at the first part， this is the edge on value of V7。



![](img/1602e205bab7500955e1fd97cc7097a3_60.png)

The second part is a partial derivative。Of V 7 with to V6。 in this case。

 because v 7 equals v 6 subtracting v 5， That partial derivative is one。

So I will be able to derive B6。

![](img/1602e205bab7500955e1fd97cc7097a3_62.png)

So far so good。Let's take a look at V5。The eion of v5 is quite similar because the relation of v5 and v6 brings v7 is similar。

 except that the partial derivative of v7 whichs back to V5 is negative one here。Okay。



![](img/1602e205bab7500955e1fd97cc7097a3_64.png)

And。Now let's take a look B4。

![](img/1602e205bab7500955e1fd97cc7097a3_66.png)

In this case。😊，Its we can do it in a similar fashion as well， because now V6 is the function of B4。



![](img/1602e205bab7500955e1fd97cc7097a3_68.png)

And y is the function of V6。

![](img/1602e205bab7500955e1fd97cc7097a3_70.png)

So partial why， partial for。Can be written as partial Y， partial V6， because V6。

Yess the function of V4。I apply， I shall be six。How shall be four thank。



![](img/1602e205bab7500955e1fd97cc7097a3_72.png)

And the first part is adjonct value of V6。Second part is the edgenc is a part of the ratio of V 6 withect P 4。

In this case。Es 1， Okay， so derivation of V 7 edge joint can be done in a similar fashion。

 This become slightly more interesting。 If you look at the part， the edgejo value of V2。



![](img/1602e205bab7500955e1fd97cc7097a3_74.png)

![](img/1602e205bab7500955e1fd97cc7097a3_75.png)

![](img/1602e205bab7500955e1fd97cc7097a3_76.png)

In here， V2 didnt used by both V4 and V5。

![](img/1602e205bab7500955e1fd97cc7097a3_78.png)

睇。😊，So in order to compute the edged value of of V2， namely partial Y， partial V2。



![](img/1602e205bab7500955e1fd97cc7097a3_80.png)

![](img/1602e205bab7500955e1fd97cc7097a3_81.png)

We to be able to take this both pathways into consideration。 So want to。

 so it will equal the 5 edgeent times partial derivative or V 5 with respect to V2。 intuitively。

 it's more like a gradient being passed from this pathway。



![](img/1602e205bab7500955e1fd97cc7097a3_83.png)

![](img/1602e205bab7500955e1fd97cc7097a3_84.png)

And the fourth edge join comes partial V 4 partial B true。

 The gradient being passed back from this password。 We are gonna make a more detailed derivations。

 a formal derivation in the next slide about what why is the case。 Okay， and similarly for V1。You。

 it's also been using two pathways。 You can find that there are， you know。

 adddjunc values and partial derivatives from two pathways being passed back。

So we're going to do a slightly more formal derivation of the two pathway cases in next slide。

 but let's first take a look at particular at this particular reverse mode a tracing here。

 we going to find that you know to summarize the idea is that by defining edge join values。😊。



![](img/1602e205bab7500955e1fd97cc7097a3_86.png)

Willll be able to recursively derive the adjonct value of each of a computation graph node from the very。

😊。

![](img/1602e205bab7500955e1fd97cc7097a3_88.png)

So we we start from V7 which where the adjot value is trivial because you know the adjot value equals 1。

 and then for each sugar node， we will be able to derive the adjo values。

From the edge on value of its next node。Of the node that takes this particular node as input and partial derivatives of this output node which the input。

And as we get the edge on value of v1 by definition。

 the edge on value of v1 is partial y partial x1 and edge on value of v2 is partial y partial x2 and well put it together。

 is effectively equals the gradient。哦。我信。With respect to。



![](img/1602e205bab7500955e1fd97cc7097a3_90.png)

All the input X parameters。 So that's our gradient。

So reverse mode A D really allows us to be able to compute the gradient of the scalar function with respect to all the input values in a single。

Backward， pass。Okay。😊，So we have to talk about the reverse mode automatic differentiation。

 Now let let's take a closer look at the multi password case we just gloss over you know what happens in the multi password case and why do you want to add those partial together if you if others tell you like hey。

 I learned automatic differentiation， you suddenly want to also questionten with this multi password case on how you exactly derive this case where the single input value is being used by multi output values and how do you pass edgeile value。



![](img/1602e205bab7500955e1fd97cc7097a3_92.png)

So let's take this example， where V1 is being used by both V2 and V3。So in this particular case。

We can actually write the output function Y as a function of V2 and V3。On the other hand。

 we also know that V2 and V3， both of them are also function of V1。Okay。

 so in order to take partial derivatives of partial y partial V1。

 what we're going to do is we're going to take So we we will need to take partial derivatives of F with respect to each of these input value。

 B2 and V3。 So first of all， we're going take the partial derivative of with respect to B2 holding B3 as a constant。

And multily that by partial B to partial V one here。

Then we are going to take the partial derivative value holding V2 as a constant。

本 then multiiply that by partial B3 partial V1。And finally， you know。

 we need to add them together to get the final partial derivative。

 So this is the the formal derivativerivation。 And this is so this is kind of like the partial derivative computational rule that you learn in your calculus。

 So as a result， the final adju value of V1 will become the sum of all those adju values of this output times the partial derivatives of the particular output with respect to that。

Input note V1。So in this case， actually we might be helpful to also deploy a notation called partial edge of that particular edge。

 So let's say the partial edge of I2 J in here is defined as the edgejo value of output node J。😊。

And the partial derivatives of the particular output with respect to that input node I。

So effectively， while defining partial join as values attached to each of these computational graph edges。

Where the edgeron value is attached to each of a computational graph， no。

And that's a very natural relation here。 So we'll be able to compute edge join of V1 by summing the partial edge of V1。

2 V2，2 v2 and partial a join of 1，2，3 together。And this notation is helpful for us to know。

 formally write down the automatic differentiation algorithm and use it in our implementation。Okay。

 so so far we have derived automatic differentiation by hand。

 you can see that with a condition graph and a definition of edge。

 we will be able to recursively derive the intermediate grid gradient in a recursive manner by backward traverse in a computational graph。

😊，Now let's start think about how we are going to implement that a using the Python tool or using any of the languages that you like。



![](img/1602e205bab7500955e1fd97cc7097a3_94.png)

So the implementation of a， it's going to look like this。😊，This is one instance of implementation。

 of course there are other ways to implement it， but this is one way lets walk through this particular implementation and you know you want to try to pay attention carefully because this is also what we are going to implement as the first part our homework as a matter of fact is going to be the foundation of everything we do in this class okay。

So first of all， I'm going to create a dictionary that maps each of a conventional graph node。😊。

To a list of partial edge。 So in this case， I'm not trying to map the node to edge。

 but I'm going to map it to a list of partial a so that we can partially accumulate the partial edge on the fly and in dealing our computation。

 okay。So we know that output put will edge on is one and。From our previous derivationals。

Then what we can do is we can reversely traverse my computational graph。For each of the node I。

 the first thing I'm going to do， we know that node to Gr contains a list of partial edges。

 So we're going to sum it together to get my aile。Once once I get the edge on value of V。

 what I'm going to do is I'm going to compute partial join for each of the inputs to I。

 so for each of the K node from the input list of this particular combination graph node。

 we are going to compute partial join of VK to I by computing this formula so we can equals VI times partial V partial VK。

Then we're going to append this partial join to note to grand K values and then we're going to repeat these loops in here。

Remember that we are taking these iterations in a reverse topological。That me sad。

After we start to get to know the eye， we have already visited all the those。😊。

That takes eye as an input。 That means that the partial adjunct list is already being populated that contains all the partial adjunct values。

 They allows us to sum， sum everything together in here。系。And finally， after we run everything。

 we will be able to get the edge of input。 and we can return that to my to my to the to the to the outside。

 Okay， so this is an implementation of reverse mode automatic differentiation。😊，Next。

 what I'm going to tell you is that and I'm going to tell you a variant of this implementation。

Before I'm going to do that， I would like everybody to possibly and think about how you might want to implement this action and specifically what kind of data structure are use to represent VI and VI to J partial agent here。

A natural answer that one can come up with in this case is I'm just going to use the multi dimensional array to saw the。

 the particular computed result in here， which is a very valid answer。😊，However， in practice。

 we are not actually doing that。

![](img/1602e205bab7500955e1fd97cc7097a3_96.png)

Instead， what we're can to do is we're going to run this same algorithm。😊。

But we're going to instead of computing the actual concrete values of each partial edge on I2 J and partial edge on V。

 when we're going to construct a computational graph。Well， if you don't get that what I mean。

 you will get it once we walk through this example。

 So here is a competition graph that we are going to take the automatic deciation with respect to I'm going to run the code on left hand side。



![](img/1602e205bab7500955e1fd97cc7097a3_98.png)

And this particular accommodation graph express the function exponential of B2。And this is the plus。

 plus。Sorry， this particular function is exponential of B1。Plus one。唱。

Exponential of the one you here， right。

![](img/1602e205bab7500955e1fd97cc7097a3_100.png)

So， so， and in order to compute。The reverse mode automatic differentiation that going run this action。



![](img/1602e205bab7500955e1fd97cc7097a3_102.png)

It's a first step。We're going to compute the partial a joint where I equals fourth。

 I'm going to compute the a joint value of V4。 In this case， we know that V4 a join value is 1。

So instead of trying to directly create array， saying that you know V4 value is equals1。

 I'm going to create a computational graph node in here。 And in this case， I identity function。

 So which means that it's just going to take its input and output it。 So in this case。

 V4 actually directly equals one。 Som I'm annotating V4 bar here so that you can understand that hey。

 this the corresponding node that corresponding point to the edge on value of V4。😊，As the next step。

We are going to come to I equals 3。And。

![](img/1602e205bab7500955e1fd97cc7097a3_104.png)

And in this case。And and， and in this case， I'm sorry。 So in next step， actually。

 we are going to first get to I equals 4， but I want to compute。



![](img/1602e205bab7500955e1fd97cc7097a3_106.png)

The inner and want to iterate over all the inputs。 in this case input of before is 2 and 3。

I need to compute a partial edge on the values。In this case。

 we know that I show the edge on the value of V2，2，4。你く。Vve force adjoint times。I shall be 4。

 I shall be  true。In this case， we know that v4 equals v2 times v3。So partial V for partial V two。

Equals。We four bar tos。

![](img/1602e205bab7500955e1fd97cc7097a3_108.png)

V3。Thank hear， right？So we know that this value of partial value of B2，2，4 equals v 4 bar times p3。

Instead of creating a read that correspond to that value。

 while creating a computational graph node that represent that computation， as in this case。

 it represents a computation saying that22 4 equals v for partial join on Sp3。😊，Similarly。

The partial a of V3， in this case， because V3 only have one output。

 so the partial a actually equals ajo value。你个。

![](img/1602e205bab7500955e1fd97cc7097a3_110.png)

V 2 times v4 bar because again， V4 equals v2 times C3。

 So the partial value of V3 equals v 2 times v 4。

![](img/1602e205bab7500955e1fd97cc7097a3_112.png)

Okay， so。That's the second step， that's one i equals4。

 we're going to compute those partial hydrogen values。



![](img/1602e205bab7500955e1fd97cc7097a3_114.png)

Now moving next to I equals3。

![](img/1602e205bab7500955e1fd97cc7097a3_116.png)

In this case， the V3 only have one input node， which is V2 right this additional function。

 So the partial value of V223 exactly equals v3。 That's why were placing an identity function in here。



![](img/1602e205bab7500955e1fd97cc7097a3_118.png)

We me next？So this this is the part that becomes slightly more interesting this is the moneyi pathway case。

Where V2 is being used by both V4 and V V3。 So， so when we are getting to this particular iterations。

 we need to sum the list in here and this list is already being populated when we iterate over V4 and V3 and it contains V22。

3 and V V224。

![](img/1602e205bab7500955e1fd97cc7097a3_120.png)

![](img/1602e205bab7500955e1fd97cc7097a3_121.png)

so we're halfway around this step， what we're going to do is we're going to create a new node that Chris going to V force V2 air join and it's going to add this node and this node together that gives the air join to。

Finally， we want to compute the partial edge join of V1 to 2。And in this case， we know that。

Partial argument of we wanted to authentic because V1 is only being used by by one places the equals。

V 2 bar comes partial V 2， partial V1。And because V2 equals exponential V1。

 what is a gradient exponential function。It's a value of itself， so it equals。

Me too bar becomes exponential。I'll be one。And we also know that exponential V1 exactly equals this vuing here。

 right， So as a result， the V1 bar can be expressed as B2 comes B2 bar in here。

We are kind of saving all of the additional exponential computations by creating this without instead of creating another exponential function。

😊，Okay， so that's how we are going to， that's how we run this reverse mode A computations。

And you can find that in an end， unlike no case when we are deriving it by hand。

Where we are writing down the concrete values of each of the computations。

 we are creating this computational graph。 It's another computational graph that extends the original computational graph。

😊，And this new computational graph。😊，Help us not only contains the forward computation that compute each of the intermediate values。

 but also contains the gradient computation that contains the compute's air drop value。😊。

One amazing part about this computational graph is unlike the manual derivation case where you each of a derivation we can only do it for one specific instance of you know x equals2 and x1 equals 2 and x5 x2 equals5 in this case。

 I can supply any V1 values here but more I can supply v1 equals0 in here run through this computational graph and I will be able to get the edge on the value of v1 when v1 equals0。

😊，If I supply V1 equals 2 here drawing this computational graph。

 I will be able to get the edgent value of V1 when when V1 equals 2。

 so this particular compute graph can be reduced for different kind of input values。And。

Without having torun the automatic differentiation derivations from scratch。So this is just like a。

A few slight interesting advantages。That the reverse mode A algorithm by extending computational graph will bring you。

 and this is also the algorithm that most of the deco framework nowadays uses。

In the last lecture we also talk about that propagation。

 so what the question of might have in mind is what is the difference between the reverseersal AD that we just talked about in this lecture versus the back propagation that we did in the past few lectures。



![](img/1602e205bab7500955e1fd97cc7097a3_123.png)

So roughly， they can be summarized in the in this slide。When we are doing backroation。

 we are constructing the computational graph and we will run the computations forward to get the values。

And then when when we're an interesting ingredient。

 we directly try to run backward operations on the same graph。 Thank you。As a result， effectively。

 you know we are trying to run back reversely canvasverse the original computational graph。

 there is no extra computational graph now being created during the backward computations。Actually。

 this back propation method was the method that Gar H and Alice originally used。

 and it being used in first generation different ins。

 namely Cafe and Ka Com when the one the imagenet challenge and differently takes off backproation was the action that that primarily used in a lot of the machine learning ins。

 except for one， which is C， which called pioneers is a reverse mode my differentiation idea through computational。

So。In the second generation， which when Tensorflow and Pyage came out。

 actually the reverse mode A by extending computation graph approach takes over。 and nowadays。

 most of the deployment framework do not leverage back propagation action that try to directly to back backward operation in place the original computation graph。

Instead， they will always try to construct this new extra gradient part of computations that correspond to the edgegile computation。

And I will only pause here a bit and let everybody think a bit of asking this question。

 why does more than different Inax leverage this reversible AD by extending comm graph？对呀。

There are several reasons behind this。And both in terms of computing gradient。

 as well as how easy it is to optimize the computation。So first all。We know that in certain cases。

 when we are working on machine learning， you might want to， you know。

 do certain loss functions that relates to the gradient But example'm one of a typical loss function that one might ask is I'm interested in minimizing。



![](img/1602e205bab7500955e1fd97cc7097a3_125.png)

V1 bar square。

![](img/1602e205bab7500955e1fd97cc7097a3_127.png)

英雪。Okay。😊，So in this case， what we're trying to do is we want to。Pake。If find a loss function。

 pick a gradient which respect that particular input。

And I want to be able to then take a gradient with respect to a function of that gradient value。

 So in this case， this is a function of a gradient value。In back propagation。

 word it's really hard to do that because the back propagation only define and it tells you how I'm going to do the gradient with respect to the input。

 right， So so it's only going to tell you how do you do the gradient once。

 But what about gradient of gradient。In the reverse mode A D by extending computation graph， though。

If you take close look on the right。You'll find that we are taking a computational graph。

And the result computation is another computational。

So what we can do in here is we can just attach another node called。



![](img/1602e205bab7500955e1fd97cc7097a3_129.png)

You know， square。That in way it takes v1 bar squared in here， which is a computational。



![](img/1602e205bab7500955e1fd97cc7097a3_131.png)

靓。😊，You can go and apply the same automatic differentiation algorithm on this computational graph that will give you the gradient of gradient values with respect to B1。

😊，So in some sense， you are getting this， you know。

 grading or greeting for free by building this reverse mode A by extending computation。😊。

And this is really cool。 This is a really cool part of this reverse mode A algorithmg of combination graph。

 And you are going to do it on your homework as well。 And the really exciting part is。 you know。

 once you implement this automatic algorithmg， and you kind of get gradient of gradient for free。😊。

The second reason why we typically use this。Comutal graph reverseal A by extending condition graph approach is that you will find that output of a gradient graph is still a comm graph。

 So in order to evaluate this condition graph， all I need to care about is I just need to run this graph forward。

😊，As a result， there's more opportunities to go and optimize these computations， for example。

 in this case， for example， I could fold these two node together and these two node together because their identity functions that will make the gradient computation assymmetric。

 It' no longer there's no longer one to one correspondence from the forward computation to the gradient computations。

 but the gradient computation can become more efficient。

 So it also brings lot more opportunities for underlying machine learning infir to do certain optimizations for the gradient computation。

😊，Okay， so。Upen now， this is a main thing that we we focus on this lecture if you want to get one takeaway。

 it's a picture， and you really want to understand making sure you understand everything。

 how do we get to this reverse on a by extending computational graph approaching here。



![](img/1602e205bab7500955e1fd97cc7097a3_133.png)

So up on now， we have to talk about the automatic differentiation by deriving them using scale of there。

😊，In practice。When we are dealing with neural networks。

 all our intermediate values are multi dimensionsal tensors。And actually。

 it's not that hard to generalize our reverse mode A D onto multi dimensionsal array and tensors。

 we do， we do that as we generalize the definition of ageure。So for a matrix like z。

 which is a two dimensional matrix or for for a tensor value。

 were going to define the edge join of that matrix or tensor。I， another matrix。Whose element。

 each of element quis points to the edgejo value with respect to that particulardicular element。

 because the edgejo value with respect to a single scale size will define。As a result。

 we will be able to use that to define adile value of the tensor， right。

Then what we can do is we can use the scalar automatic differentiation rule to design to to derive the automatic definition rules for this matrix computation and test computation。

 for the forward evaluation， we know that Z I J equals sum of K X， I K times W K J。😊。

Then we'll be able to derive the edge on value for a particular element， the X IK in here。😊。

And we know that particular X IK is being used by a lot of Z values， by a lot of the IJs。

So we want to be able to those edge on value and partial together。 And finally， we know that equals。

 you know， sum of a JWKJ times ZI J bar here。U you derive it in a scalop form。

 you can write a back quantum matrix form and you will find that this relation holds where the edgeron value of x equals edgeg value of z times W transcript。

 And that is the common rule that we use to in neural networkural computations to derive the gradient of a linear lake。

Okay， so now the reverse mode idea on tenors can be generalized as a result， you'll find that we are。

 you know the implementation effectively remained the same in the four tensors and multidiaries。



![](img/1602e205bab7500955e1fd97cc7097a3_135.png)

We already talked about the pros and constant back and mod。



![](img/1602e205bab7500955e1fd97cc7097a3_137.png)

And handling a gradient ingredient as well。

![](img/1602e205bab7500955e1fd97cc7097a3_139.png)

So finally， this is the bonus slide when we， we have talked about so far reverse mode A on tensors。

 However， when we are going to write programs， sometimes， you know。

 not all intermediate values are tens， sometimes we might want to put tens in a data structure or other forms。

 For example， we could have， we could have a dictionary where， you know， each of a value。😊，Of。

 of the dictionary， crisp to cancer that we might want to take differentiation with respect to。

We can actually generalize the definition of agent。Or into those data types and the structures。

Of course， the definition you can't generalize the definition example in this case， for a dictionary。

 we can generalize it by in this case， we want to make sure that the dictionary P itself is always not a tensor。

 so it's always a value that we can' take differentiationpreciation with respect to。

But its value can be tenus， so we can define edgeron as another dictionary that contains the same set of a keys。

But the value corresponding to the corresponding edgedent value。

So for each of forward computations like dictionary lookup。

 we'll be able to define a backward computation on gridding computations that effectively construct another dictionary that contains the edge of value。

😊，So the key takeaway here is that for different data types。

 we will be able to define ajo on computations as long as we can have have a definition for its a on value and the ag on propagation rule。

😊，The same。The same reverse mode automatic penetration action should work for those cases。

This is kind of a more general case called differentiable programming that we are not going to cover in this lecture and for this class as well。

 you know if you are interested in this concept， you are more than welcome to go and search related lecture literatures on differentiable programming。

 you will be able to find some of related material in here。

We may want to have support for certain type of data structure in our assignments。

 So So specifically， we might want to add support for Tple values。

 That means that we want to support for a value that contains， you know。

 twople of multiple tensors and want to be able to define edge on for that particular twople value。

 So that is that that will be part of our implementation of the homework。O。😊。

So thanks everybody for coming to today's lecture in today's lecture weve learned about you know why do you want to do differentiations and a set of tools for us to be able to both track the gradient of automatic differentiation implementation as well as implementing reverse mode AD that give us the gradient values of all the inputs in one backward pass finally。

 we also talk about how we can build this reverse mode AD everything by extending computational graph so that we can use the same tool to obtain gradient or gradient and getting a lot of benefit on lowlevel optimization。

😊，In the next lecture， we're going to cover more of the implementation details on that you' are going to use in your homework to implement the everything that we described in this lecture。

That's the end of today's lecture， thanks for coming and I will see you in next lecture。😊。



![](img/1602e205bab7500955e1fd97cc7097a3_141.png)