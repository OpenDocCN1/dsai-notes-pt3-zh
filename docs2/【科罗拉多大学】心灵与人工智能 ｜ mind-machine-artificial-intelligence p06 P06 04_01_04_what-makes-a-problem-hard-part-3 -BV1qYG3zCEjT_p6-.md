# 【科罗拉多大学】心灵与人工智能 ｜ mind-machine-artificial-intelligence p06 P06 04_01_04_what-makes-a-problem-hard-part-3 -BV1qYG3zCEjT_p6-

![](img/29492af9ae58aa81a0d6361f932bd81c_0.png)

In in the previous two discussions， we've been talking about what makes a problem hard or easy and some of the new ideas that have come up because of the way in which we've started in the last half century because of the way in which we've started to model minds with machines we've been able to develop a more nuanced and expressive language about what makes problems difficult or easy。

 and so we spent the last couple of sessions talking about that， there is much more to say about it。

 but at least for this session where it's kind of a final session on this topic。

 but we'll return to the topic。

![](img/29492af9ae58aa81a0d6361f932bd81c_2.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_3.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_4.png)

As as we discuss more about minds and machines in this particular session。

 what I'd like to do is talk about how computer scientists think about a certain kind of difficulty of problems this ultimately is a rather challenging and perhaps technical subject。

 but for our purposes， I think we can offer an explanation here。

 we can look at an explanation and we can explore these ideas without getting too much into the sort of you know mathematical depths of the subject so what I'd like to do。



![](img/29492af9ae58aa81a0d6361f932bd81c_6.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_7.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_8.png)

Is describe one particular type of difficult problem。



![](img/29492af9ae58aa81a0d6361f932bd81c_10.png)

And use that to introduce another kind of difficult problem。



![](img/29492af9ae58aa81a0d6361f932bd81c_12.png)

As at least as far as computer scientists are concerned。 So let's begin。With a classic puzzle。

 I believe it goes back to at least the beginning of the 20th century and the American puzzle Smith。

 Sam Lloyd wrote about this this puzzle。 I'm not sure if he invented it。

 but regardless of whether he invented it or not he popularized it。

 This is called a Tower of Hanoi puzzle。And you see a picture of it here。 There are three pegs。

And in this case， there are8 disks， I believe。 So you see a tower of8 disks with each of the disks has a hole in the center。

 and they've been stacked on the leftmost peg。 And you see that they go from largest disk at the bottom to smallest disk at the top。

 So what we now want to do then the the， the goal of the puzzle is to transfer these eight discs from the leftmost peg to the rightmost peg。



![](img/29492af9ae58aa81a0d6361f932bd81c_14.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_15.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_16.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_17.png)

And we're going to do that subject to certain rules。

 the rule is you can only take the top disc off a stack and move it onto another peg。And secondly。

 and quite important， you can never move a disk to a stack so that it's resting on a smaller disk than itself。

Okay， so you' got to transfer these eight discs。 You can take a disc off the top of a stack and put it on another peg。

But you can't move a disk onto the top of a smaller disk。

So if you think about how you might start this particular puzzle。

 I was considering actually bringing a physical puzzle and working it for you。

 but I decided it would be kind of unwieldy。 And you know， if I got the thing wrong on camera。

 that would be， I would be embarrassed beyond measure。 So I'm not going do that。

 But here's how you might start this particular puzzle。

 take the smallest disk off the top of that stack at the left and place it on the middle peg。

Now take the second disc off the top of that leftmosts stack because that's now at the top and move it to the right peg。

Now， as a third move， you could take the small disk。

 which we placed on the center peg and move it to the right peg and so forth， In other words。

 what we're going to be doing in order to solve this puzzle is to move the disks one by one from peg to peg subject to the constraint that we can never move a disk onto a smaller disk。



![](img/29492af9ae58aa81a0d6361f932bd81c_19.png)

Now， how hard is this puzzle？This is an interesting question。



![](img/29492af9ae58aa81a0d6361f932bd81c_21.png)

In one sense， the puzzle is actually quite easy， and here's what I mean。



![](img/29492af9ae58aa81a0d6361f932bd81c_23.png)

The strategy for the puzzle is easily expressed。And you can find examples for for instance。

 on YouTube， where you see people solving versions of the puzzle。So here's the strategy。

 I've expressed it on this one slide。 We want to move a tower of n disks from peg1 to peg3 using the center peg as a kind of spare as a place where we can occasionally move disks if we need them Okay so we want to move a tower of n disks from peg1 to peg 3。

Using P 2 is a spare。Now， think about how we could do this and I'm going to express a solution。

 and if you consider it， you'll see that this would work in order to move eight discs from the left peg to the right peg using the second peg as a spare。

First， what we're going to do is move seven disks， we're going to solve the puzzle for seven disks。

 and we're going to move seven discs from peg 1 to peg2。

 that is the center peg using peg3 as a spare。Now， think about the what happens when we do that。

 We're going to move the top 7 disks。 We're never going to touch the bottom disc。 After all。

 who cares if we're moving only the top 7 disks。 We don't need the ace at all。

 and it'll always be bigger than anything else that we're moving。

 So for the time being we'll ignore the ace disc， the one at the bottom we'll just work with the top 7 and we'll move those from peg 1 to peg 2 using peg 3 as a spare。

Once we've done that。Think about what we have at the end of that process。 We have one。

 the bottom eighth disc still there on the left peg。

 we have seven discs on the center peg and the third peg is empty。

Now what we do is take the big disc from peg1 and move it over to Peg3。That's just a simple booth。

And then we solved the seven disk tower a second time， moving things from Peg 2 to peg 3。

 using peg 1 as a spare。This is inherently to wonder the term that computer scientists use for this kind of process is recursive。

 this is a beautifully recursive process， I've expressed it in an abstract way to solve the tower of n disks going from peg1 to peg3。

 first solve the n minus1 tower， going from peg1 to peg2。

 move the bottom disc and then solve the n minus1 tower again。

And you'll see you could try using this strategy， try it first on a tower。

 It's trivial on a tower of size 1 disk。

![](img/29492af9ae58aa81a0d6361f932bd81c_25.png)

There you just move the disk from peg1 to peg3 for a peg1 to peg3， move up two disks。

 you first move the small disk to peg 2， the second disk to peg 3， and then the small disk to peg 3。

So we can solve a puzzle of size1， we can solve a puzzle of size 2。

 using our knowledge of how to solve a puzzle of size2， we can solve a puzzle of size3 and so forth。



![](img/29492af9ae58aa81a0d6361f932bd81c_27.png)

So in some sense， the tower of ano is an easy puzzle。

 we can express the idea of solving it on one slide。 That's all it takes。



![](img/29492af9ae58aa81a0d6361f932bd81c_29.png)

So is this an easy puzzle well in another respect？This is a very hard puzzle。

To solve the tower puzzle with one disk takes one move。 Just one move。

 moves the one disk from peg 1 to peg 3。 If you think about what I was saying before， solving the。

 the tower of size 2 takes three moves。

![](img/29492af9ae58aa81a0d6361f932bd81c_31.png)

Solving a tower of three disks takes seven moves。You have to do the two solution twice with one additional move in between。



![](img/29492af9ae58aa81a0d6361f932bd81c_33.png)

The overall， to solve a tower of N discs requires twice the time to solve the n minus1 disk puzzle plus one additional move。

So as it turns out。Solving a tower of8 disks requires 255 moves， solvinglving a tower of 40 disks。

 and 40 is not a whole lot of disks。 It's just's a big tower， but you could engineer such a puzzle。



![](img/29492af9ae58aa81a0d6361f932bd81c_35.png)

Solving that would take a trillion move。Solving a tower of 60 disks would take a million trillion moves。

 Now， consider what we've just said。 What we just said is that expressing the idea of the solution is easy。

 It is easy to say what the solution path would be。



![](img/29492af9ae58aa81a0d6361f932bd81c_37.png)

But， actually。Enacting that solution， actually implementing it takes， in fact， exponential time。

 the time to enact the solution grows as approximately。



![](img/29492af9ae58aa81a0d6361f932bd81c_39.png)

2 to the N， where n is the number of disks in the original tower。

So solving a tower of size 60 takes about a million trillion moves。In other words。

 we as human beings， and for that matter， machines。

 computers would take a long time to actually print out a solution to the tower of Hanoi problem。

 and if the tower starts out with say，100 disks， we're talking about a problem that would take too long for even the fastest computer to solve in anything like a meaningful time。



![](img/29492af9ae58aa81a0d6361f932bd81c_41.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_42.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_43.png)

So。Even though the problem is easy conceptually， it takes an extraordinary amount of time to implement that solution。

 and I haven't shown you this， but it doesn't take much to actually see that it's not that we you might think well。

 if we were more clever， we could come up with a faster solution。

 maybe we came up with this easy solution， but it actually there's a more complex solution to express。

 but it'll take a shorter time， no。

![](img/29492af9ae58aa81a0d6361f932bd81c_45.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_46.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_47.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_48.png)

It really takes。This is the best we can do， this is the best solution you could have。



![](img/29492af9ae58aa81a0d6361f932bd81c_50.png)

And I haven't shown you that， but that is the truth。



![](img/29492af9ae58aa81a0d6361f932bd81c_52.png)

There is no way of improving on the situation that we've got。 If you have a tower of size N。

 it takes approximately two to the N moves， even to print out a solution。 and that becomes。



![](img/29492af9ae58aa81a0d6361f932bd81c_54.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_55.png)

Well， I mean， just impractical， at least for either a person or a computer。

 even the fastest computer。😡。

![](img/29492af9ae58aa81a0d6361f932bd81c_57.png)

So is this a hard or an easy problem？That's I don't know how to quite answer that question without you know。

 sort of going into this sort of detail in one sense， it's an easy problem。

 in another sense it's a very hard problem。

![](img/29492af9ae58aa81a0d6361f932bd81c_59.png)

Now， I mentioned when we were talking about the difficulty of problems earlier。

Yet a different kind of difficult problem this is called you might have heard this term。

 if you're a computer scientist， you definitely heard this term。

 if not you might have heard this term in the sort of you know popular culture。

 the idea of an NP complete problem and while I won't go into complete detail to you know find detail about what this means。

 here's what it means in essence， NP stands for nondeterministic polynomial。



![](img/29492af9ae58aa81a0d6361f932bd81c_61.png)

And a NP complete problem is one where you can guess a solution quickly in polynomial time。

And you can check that you've got a correct solution quickly in polynomial time。But in general。

 there's no way of actually being sure to find that solution except in exponential time。



![](img/29492af9ae58aa81a0d6361f932bd81c_63.png)

Now that may seem like a fine detail， let me show you a very famous example of an NP complete problem it's called the Hamiltonian cycle problem。

 here's the idea。You have a graph， but think of the graph at the top here in this slide。

 it as it happens， it has 20 vertices and edges between those vertices， okay？

The the question of whether this graph has a Hamiltonian cycle is whether we could draw a red line。

Starting at one vertex and moving over edges from vertex to vertex， never visiting this。

 the same vertex twice and end up finally， at the end， back where we started。

I've shown a Hamiltonian cycle in the graph below of this graph。 So in other words。

 we have a graph of 20 vertices， and the question is， does there exist？

A path that will close on itself， which visits each vertex exactly once and only traverses edges that are in the graph。

You， you might have heard of a variant of， of this kind of problem under the name of the traveling salesman problem。

 The traveling salesman problem is one where you have。

In cities to visit and you want to visit them each once and you want to minimize the cost either in mileage or or expenditure in making a complete tour of all the cities。

 It's a similar problem。 This happens to be a somewhat， you know。

 more a slightly more abstract problem。Now， does in general， if somebody hands you a graph。

 does it have a Hamiltonian cycle in it？Again， there's a。

The way to the sort of obvious way to answer a question like that is list all the possible orderings of vertices in the graph。

 list all possible cycles in the graph。And see if any of those cycles。

That is list all the possible orderings of in this case， 20 vertices。

See if any of them correspond to valid edges that can move between the vertices。

 if you find such a thing， the graph has a Hamiltonian cycle。 if you can't find such a thing。

 the graph doesn't have a Hamiltonian cycle。That's a very straightforward path to a solution。

 The only problem is that first step listing all 20 possible cycles。

 we don't know when we make a list of all 20 possible。It' it turns out to be 20 factorial。

 So if you list all the possible ways of ordering 20 vertices， you have a list。

Whose length is 20 factorial。 Many of the elements of that list will not correspond to a cycle because there's no edge between neighboring vertices in that ordering。

So you have to actually make a list。 It's 20 factorial elements long。

 and then you have to check each and every one of the elements in that list。 Now。

 20 factorial is a very big number。And as the graph gets bigger and bigger。

 say I give you a graph of 100 vertices， then my simple solution requires a first step which involves making a list of 100 factorial elements。

 Again， 100 factorial is the kind of number that it's a beyond astronomical number。

 there is no way that a computer program could write such a list or go over such a list element by element in anything like a meaningful time。

So what have we got here， we have a problem that looks superficially like it might be kind of like the Tower of Hannoi problem。

😡，In order to solve the problem， we have to do a step that is exponential time。

 but there's one important difference here， and it's illustrated by these two graphs on this slide。

Somebody drew on this graph a red line that corresponds， in fact， to a valid Hamiltonian cycle。

It didn't take an exponential time to draw that red line。 unlike the Tower of Hanno problem。

 it doesn't take exponential time。To actually express the solution。In this case。

 it took a very short time to express to guess a solution。

And how long does it take to check that solution， not long at all， just look at the second graph。

 follow the red line， and you'll see， yep， that's a good Hamiltonian cycle。

So guessing a solution is brief。Polynomial time checking a solution is brief。

 but as far as anybody knows。And this is an unsolved problem at present。 As far as anybody knows。

 there is no surefire way to find a Hamiltonian cycle that does not need exponential time。

NP complete problems， you might think from this description that I've just given。

 N complete problems are kind of a mathematical oddity， but it turns out they're not。

 they're all over the place。And they often come up in situations where。

You have to optimize a solution or you have to they're often in situations of ordering and optimization。

 and there are many， many NP complete problems that are。

Quite naturally related to things that we might want to write computer programs to do。

So when a computer scientist runs across an NP complete problem， usually what he or she does is。

Decide that they're not going to be able to solve the problem with certainty。

 but maybe they can come up with a solution that's。What what is sometimes called satisfying。

 it'll satisfy the situation and it'll suffice for the current situation。 So computer scientists。

 when they run into NP complete problems， they often start looking for ways to come up with an approximate solution。

NP complete problems are extremely interesting and they've only been discovered over the last half century or so。



![](img/29492af9ae58aa81a0d6361f932bd81c_65.png)

Okay， so where does all this leave us at this point。

 we've now talked about different ways of thinking about difficult problems。



![](img/29492af9ae58aa81a0d6361f932bd81c_67.png)

First of all， the main thing that the whole point of this discussion has been。

There are many ways in which a problem can be hard or easy。 Some of these are。

Some of these have profound implications。Some of them involved the idea that stating a solution would not be difficult。

 but actually implementing the solution would be difficult。



![](img/29492af9ae58aa81a0d6361f932bd81c_69.png)

In the case of。

![](img/29492af9ae58aa81a0d6361f932bd81c_71.png)

We've been talking about the link between machines and minds in the case of the problems that we looked at earlier。

 learning one's native language or opening one's eyes and seeing objects in the world。

 those prove to be extremely difficult problems， even though in some sense， they feel easy for us。

We open our eyes and we see objects， but it took millions of years of evolution to get to the point where we would have eyes that were capable of doing that。



![](img/29492af9ae58aa81a0d6361f932bd81c_73.png)

We learn our native language without direct instruction。But it takes us years to do it。And again。

 we have a great deal of evolutionary equipment built in that that allows us to， to， to do this。



![](img/29492af9ae58aa81a0d6361f932bd81c_75.png)

That gives us the tools to do it。

![](img/29492af9ae58aa81a0d6361f932bd81c_77.png)

At present。We do not understand entirely the mechanisms either by which we learn our native language or by which we accomplish the vision task。

 these prove to be very hard problems， even though they feel easy for us。



![](img/29492af9ae58aa81a0d6361f932bd81c_79.png)

And。As we continue to talk about minds and machines， this。



![](img/29492af9ae58aa81a0d6361f932bd81c_81.png)

This sort of gap in the notion of difficulty， things that are easy for machines， but hard for people。

 things that seem to be easy for people but are hard to program。

 these will come to the fore over and over again。

![](img/29492af9ae58aa81a0d6361f932bd81c_83.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_84.png)

![](img/29492af9ae58aa81a0d6361f932bd81c_85.png)