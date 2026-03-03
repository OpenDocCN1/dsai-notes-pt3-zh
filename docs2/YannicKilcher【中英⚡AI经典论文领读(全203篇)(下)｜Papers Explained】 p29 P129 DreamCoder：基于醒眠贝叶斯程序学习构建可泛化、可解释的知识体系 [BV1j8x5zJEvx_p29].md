# YannicKilcher【中英⚡AI经典论文领读(全203篇)(下)｜Papers Explained】 p29 P129 DreamCoder：基于醒眠贝叶斯程序学习构建可泛化、可解释的知识体系 [BV1j8x5zJEvx_p29]

Hi there。 I have a little challenge for you right here。

 Look at these numbers and see if you can figure out what comes where the question mark is。 Now。

 if you look at it a little bit， you'll recognize that this is the sorting algorithm。

 So you're supposed to sort these numbers in ascending order。 and that's going to be the solution。

 And the why I'm showing you this isn't because it's particularly hard or because I'm particularly good at sorting numbers。

 It is because this is。A core feature of human intelligence that we haven't been able to reach with machine learning quite yet。

 We are able to look at very few examples and then generalize to new examples。

 And we do that not by the way machine learning does it by， you know， gradient decent into a model。

 But we do it by coming up with a rule such as hey， this is sorting。

 even if we didn't know what sorting was， we would be able to come up with the rule nevertheless。

 because we would realize， you know， I need to compare the numbers。

 And I need to pick the lowest one first， and then the second lowest one， second and so on。 so。

We humans are able to come up with rules to solve the problem， and in more general sense。

 we're able to come up with a program with an algorithm that solves the problem。And。

That is the point of this paper。

![](img/933be6de9e310e0bba38928691bdf235_1.png)

To solve problems not with pure， brute force machine learning。

 like gradient descent from a dataset set， but with coming up with rules with algorithms to solve the problem。

 Now， this brings its inherent challenges。 It's not a new approach。

 But this paper makes it more scalable than before。 So the paper is called Dream coder。

 growing generalizable， interpretable knowledge with Wake sleepep， Bayesian program learning。

 It's by Kevin Ellis， Catherine Wong， Maxwell Ny， Matya Saulmaa， Luckari， Luccamoal， Luc Hewitt。

 Armando Solar Lezama and Joshua B。 Tenbaum。

![](img/933be6de9e310e0bba38928691bdf235_3.png)

![](img/933be6de9e310e0bba38928691bdf235_4.png)

![](img/933be6de9e310e0bba38928691bdf235_5.png)

So。

![](img/933be6de9e310e0bba38928691bdf235_7.png)

Again， program the paper says itself， we present Dream codeder。

 a system that learns to solve problems by writing programs。

It builds expertise by creating programming languages for expressing domain concepts together with neural networks to guide the search for programs within these languages。

 So the entire model is going to be a system that sees problems， just few of them and。

Comes up with programs that solve these problems。 and it does so in its own language。

 It builds up its own programming language， and then it's able to synthesize programs in this language that solve the。

The problem。And it does so by having a neural network guide that search。 So that's dream coder。

 It includes this wake sleep algorithm， which has been also around for a while， but it's。

 it's kind of a different take on it。 The wake sleep learning algorithm alternatively extends the language with new symbolic abstractions and trains the neural network on imagined and replayed problems。



![](img/933be6de9e310e0bba38928691bdf235_9.png)

So the past ventures into program synthesis have all been not really scalable because either they have some kind of handcrafted programming language that you search over or they have handcrafted rules of how you search and so on。

 This system here is much more general。 and it can solve a vast variety of different tasks。

 So for example， here you can see the different types of tasks that the system can solve。

 There is list processing。

![](img/933be6de9e310e0bba38928691bdf235_11.png)

![](img/933be6de9e310e0bba38928691bdf235_12.png)

![](img/933be6de9e310e0bba38928691bdf235_13.png)

Oh， sorry， that's a bit。Heavy， there's list processing， such as summing lists doubling each element。

 check for evens text editing， learning rexes for stuff。

 and also very creative things like creating graphics creating block towers， regressing symbolically。

 recursive programming and figuring out physical laws。

 we've already looked at paper that figure out physical laws from data。

 But they have been sort of geared towards that。 And this is。



![](img/933be6de9e310e0bba38928691bdf235_15.png)

![](img/933be6de9e310e0bba38928691bdf235_16.png)

![](img/933be6de9e310e0bba38928691bdf235_17.png)

![](img/933be6de9e310e0bba38928691bdf235_18.png)

![](img/933be6de9e310e0bba38928691bdf235_19.png)

The same system that can figure out all of these things。 Now， of course。

 it's going to be configured a little bit differently if you talk about list processing versus figuring out physical laws。

 but it is the same underlying system。

![](img/933be6de9e310e0bba38928691bdf235_21.png)

![](img/933be6de9e310e0bba38928691bdf235_22.png)

And ultimately， what is that， What does that amount to。

That amounts to you giving the you giving the system a problem。

 And let's say the problem right here is what do we have here。



![](img/933be6de9e310e0bba38928691bdf235_24.png)

![](img/933be6de9e310e0bba38928691bdf235_25.png)

![](img/933be6de9e310e0bba38928691bdf235_26.png)

To sort a list。 Yeah， that's what we came up with at the beginning。

 So here you have the problem of sorting a list。 So you're。

 you're gonna to give the program a few examples like three， like I gave you at the beginning。

 and the， the system is going to come up with a program。



![](img/933be6de9e310e0bba38928691bdf235_28.png)

![](img/933be6de9e310e0bba38928691bdf235_29.png)

![](img/933be6de9e310e0bba38928691bdf235_30.png)

Now， the program ultimately is going to look like the thing down here。

 It's going to come up with a program that implements the list sorting algorithm and is going to do that with by a few principles。

 So principle one， of course， it needs to fit all of the examples。

 it needs to explain all of the examples。 Otherwise is not a correct program and。



![](img/933be6de9e310e0bba38928691bdf235_32.png)

![](img/933be6de9e310e0bba38928691bdf235_33.png)

![](img/933be6de9e310e0bba38928691bdf235_34.png)

Program， sorry， concept 2， is it needs to be easy。 It needs to be very。

 very explainable in the sense of it needs to be very short because there are many different rules that。

 you know， these。

![](img/933be6de9e310e0bba38928691bdf235_36.png)

These lists follow I I can。 I can come up with。 I can literally create this as a hash table。

 I can implement this as a hash table for these three lists。

 and that hash table would solve the problem exactly as well as the sorting algorithm。



![](img/933be6de9e310e0bba38928691bdf235_38.png)

Now， the sorting algorithm is much more compact。 It's simply， it's， well， it's this thing down here。



![](img/933be6de9e310e0bba38928691bdf235_40.png)

And beyond that， what the。What the system does is it builds up a library of concepts。

 So not only not only the system doesn't see the program at the bottom。

 the system actually sees this program right here。 So this is the sorting algorithm in the system language because the system has built up a learned library of concepts over time。

 So as we train the system to solve different tasks on lists， such as you know， sum few things。

 double a few things and so on。 It builds up this library of concepts。



![](img/933be6de9e310e0bba38928691bdf235_42.png)

![](img/933be6de9e310e0bba38928691bdf235_43.png)

![](img/933be6de9e310e0bba38928691bdf235_44.png)

![](img/933be6de9e310e0bba38928691bdf235_45.png)

![](img/933be6de9e310e0bba38928691bdf235_46.png)

So。There are these primitives right here that you give it。

And then it's able to come up with these concepts that we， as programmers might call functions。

 So it's able to come up with a thing that can filter a list。

 It doesn't have it in its initial primitives。 but it's able to discover that because it uses it again and again and again。

 And now it's able to use that function instead of the primitives。 So whereas before， you know。

 it would have it would have used the entire code in this thing。 Now it's just able to say， well。

 I want to use concept for right here。 And that makes the programs that are written much shorter。 so。

😊。

![](img/933be6de9e310e0bba38928691bdf235_48.png)

It uses this to implement the maximum function， which it calls it concept 13。 Of course。

 it has no concept of what we name function。

![](img/933be6de9e310e0bba38928691bdf235_50.png)

And then it's able to use concept 13 and concept4 together to implement the n largest element function。

 right， And once I have the n largest element function I can simply iterate from the beginning。

 right？ I have a list。 I simply iterate over its length。

 So I iterate that and I always use the n largest number， and that will sort my list。

 So you can see that the program that sorts the list is super short in terms of this library we've built up。

 So this this is our challenge for building the system。

 We somehow need a system that is able to come up with programs to solve problems。

 that is able to build up a library and that is able to efficiently search through that selfbuilt up library of concept。

 and dream coder does all of this at the same time。😊。



![](img/933be6de9e310e0bba38928691bdf235_52.png)

![](img/933be6de9e310e0bba38928691bdf235_53.png)

![](img/933be6de9e310e0bba38928691bdf235_54.png)

![](img/933be6de9e310e0bba38928691bdf235_55.png)

So dream codeder has three different stages in which these things are tackled。

 So imagine you have a data set of tasks。 So the tasks here are these X's。 Okay， so X or the tasks。

 now the tasks can either be， as I understand it of a single thing like list sorting， right。

 but they can also be the general class of list problems， which makes more sense in our。

 in our class。 So imagine we have a kind of the， the general。



![](img/933be6de9e310e0bba38928691bdf235_57.png)

![](img/933be6de9e310e0bba38928691bdf235_58.png)

![](img/933be6de9e310e0bba38928691bdf235_59.png)

The general class of list， sorry， the， the general class of list problems。



![](img/933be6de9e310e0bba38928691bdf235_61.png)

Now。