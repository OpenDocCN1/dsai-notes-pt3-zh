# 【麻省理工】计算思维与数据科学导论-｜-MIT-6.0002-Introduction-to-Computational-Thinking，Fall2016-p01-1.-引言，优化问题--BV1zNjGzxEvk_p1-

![](img/2749cb9817f16b7f57eee71e727f7e17_0.png)

The following content is provided under a Creative Commons license。

 Your support will help MiT OpenCoursewareare continue to offer high quality educational resources for free to make a donation or to view additional materials from hundreds of Mit courses。

 Visit mit Opencourseourseware at Ow。mt。edduu。

![](img/2749cb9817f16b7f57eee71e727f7e17_2.png)

All right， welcome to。6 triple0，2。 Or if you were in 600， the second half of 600。



![](img/2749cb9817f16b7f57eee71e727f7e17_4.png)

I'm John Gutag。Let me start with a few administrative things。嗯。What's the workload。

 there are problem sets。They'll all be programming problems much in the style of 6 triple 0，1。

And the goal。Really twofold。 The 6 triple0，1 problem sets were mostly about learning to be a programmer。

A lot of that carries over。 No one learns to be a programmer in half a semester。

So a lot of it is to improve your skills。But also， there's a lot more， I would say。

 conceptual algorithmic material in 6， triple 0，2。 And the problem sets are designed to help cement that。

 as well as just to give you programming experience。Finger exercises， small things。

 If they're taking you more than 15 minutes， let us know they really shouldn't。

 And they're generally designed to help you learn a single concept， usually a programming concept。

Reading assignments in the textbooks。 I've already posted the first reading assignment。

And essentially， they should provide you a very different take on the same material covering in lectures and recitations。

 we've tried to choose different examples for lectures and from the textbooks for the most part。

 so you get to see things in two slightly different ways。

There'll be a final exam based upon all of the above。



![](img/2749cb9817f16b7f57eee71e727f7e17_6.png)

All right， prerequisites， experience writing object oriented programs in Python， preferably Python 3。

5。嗯。If familiarity with concepts of computational complexity， you'll see even in today's lecture。

 we'll be assuming that。Familiarity with some simple algorithms。If you took 6 triple0。

1 or you took the 6 triple0，1 advanced standing exam， you'll be fine。Ods are， you'll be fine anyway。

 but that's the safest way to do it。The programming assignments are going to be a bit easier。

At least that's what students have reported in the past because they'll be more focused on the problem to be solved than on the actual programming。

The lecture content more abstract。The lectures will be。

 and maybe I speaking euphemistically a bit faster paced。



![](img/2749cb9817f16b7f57eee71e727f7e17_8.png)

So hang on to your seats。And the course is really less about programming and more about dipping your toe into the exotic world of data science。

We do want you to hone your programming skills。 There'll be a few additional bits of Python。 Today。

 for example， we'll talk about Lambda abstraction。呃。Inevitably。

 some comments about software engineering， how to structure your code。

More emphasis in using packages。 Hopefully it will go a little bit smoother than in the last problem set in 6 triple0。

1。 And finally， it's the old joke about programming that。

Somebody walks up to a taxi driver in New York City。And says， I'm lost。

 How do I get to Carnegie Hall， The taxi driver turns to the person and says， practice， practice。

 practice。And that's really the only way to learn the program is practice， practice， practice。

The main topic of a course is what I think of as computational models。

How do we use computation to understand the world in which we live？What is a model， to me。

 I think of it as an experimental device。That can help us to either understand something that has happened。

To sort of build a model that explains the phenomena we see every day。

Or a model that will allow us to predict the future， something that hasn't happened。

So you can think of， for example， a climate change model。

 we can build models that sort of explain how the climate has changed over the millennia。

 and then we can build probably a slightly different model that might predict what it will be like in the future。

So essentially， what's happening is。Science。Is moving out of the wet lab。And into the computer。

Increasingly， I'm sure you all see this。 Those of you who are science majors。

 an increasing reliance on computation rather than traditional experimentation。As we'll talk about。

 a traditional experimentation will is and will remain important。

 but now it has to really be supplemented by computation。Well，'ll talk about three kinds of models。

 optimization models， statistical models and simulation models。



![](img/2749cb9817f16b7f57eee71e727f7e17_10.png)

So let's talk first about optimization models。

![](img/2749cb9817f16b7f57eee71e727f7e17_12.png)

An optimization model is a very simple thing。We start with an objective function。

That's either to be maximized or minimized。For so for example， if I'm going from New York to Boston。

 I might want to find a route by car or plane or train that minimizes the total travel time。

So my objective function would be the number of minutes spent in transit， getting from A to B。

We then often have to layer on top of that objective function。A set of constraints。

Sometimes empty that we have to obey。So， maybe。The fastest way to get from New York to Boston is to take a plane。

But I only have $100 to spend。 So that option is off the table。

So I have a constraints there on the amount of money I can spend。

Or maybe I have to be in Boston before 5 PM。 And while the bus would get me there for $15。

 it won't get me there before 5。 And so maybe what I'm left with is driving。Something like that。

So objective function， something you're either minimizing or maximizing and a set of constraints that eliminate some solutions。

And as we'll see， there's an asymmetry here。 we handle these two things differently。



![](img/2749cb9817f16b7f57eee71e727f7e17_14.png)

We use these things all the time。嗯。I commute to work using in ways。

 which essentially is solving not very well， I believe。

 an optimization problem to minimize my time from home to here。 When you travel。

 maybe you log in to various advisory programs that try and optimize things for you。



![](img/2749cb9817f16b7f57eee71e727f7e17_16.png)

They're all over the place today， you really。Can't avoid using an optimization algorithm as you。

 as you get through life。All right。Pretty abstract。

 Let's talk about a specific optimization problem called the Napsack problem。

The first time I talked about thenapsack problem， I neglected to show a picture of annapssack。

And it was， I was 10 minutes into it where I realized most of the class had no idea what annapsackack was。

It's what we old people used to call a backpack。And they used to look more like that than they look today。

So the Napsack problem。Involves。Usually， it's told in terms of a burglar。

Who breaks into a house and wants to steal a bunch of stuff。

But has a knapsackack that will only hold a finite amount of stuff that he or she wishes to steal。

And so the burglar has to solve the optimization problem。Of stealing the stuff with the most value。

While obeying the constraint。That it all has to fit in the knapsack。So， we have。

An objective function。I'll get the most for this when I fence it。And a constraint。

 it has to fit in my backpack。And you can。Guess which of these might be the most valuable items here。

So here's in words。Written words， what I just said orally。嗯。There's more stuff than you can carry。

 and you have to choose which stuff to take and which to leave behind。

I should point out that there are two variants of it。There's the 01napsackack problem。嗯。

And the continuous。 So the 0，1。It would be illustrated by something like this。



![](img/2749cb9817f16b7f57eee71e727f7e17_18.png)

So the 01napsack problem means you either take the object or you don't。I take that whole gold bar。

 or I take none of it。The continuous or so calledled fractionalnapsack problem says I can take pieces of it。

So maybe if I taken my gold bar and shaved it into gold dust。I then can say， well。

 the whole thing won't fit in， but I can fit in a path， part of it。



![](img/2749cb9817f16b7f57eee71e727f7e17_20.png)

The continuousnapsack problem is really boring。It's easy to solve。

How do you think you would solve a continuous problem？Suppose you had over here。

 a pile of gold and a pile of silver and a pile of raisins。



![](img/2749cb9817f16b7f57eee71e727f7e17_22.png)

you wanted to maximize your value。 Well， you'd fill up your knapsack with gold。

Until you either ran out of gold or ran out of space。If you haven't run out of space。

 you'll now put silver in until you run out of space。If you still haven't run out of space， well。

 then you'll take as many reasons as you can fit in。

But you can solve it with what's called a greedy algorithm。

 And we'll talk much more about this as we go forward。

Where you take the best thing first as long as you can。



![](img/2749cb9817f16b7f57eee71e727f7e17_24.png)

And then you move on to the next thing。As we'll see， the 0。

1napsackack problem is much more complicated。Because once you make a decision。

 it will affect the future decisions。

![](img/2749cb9817f16b7f57eee71e727f7e17_26.png)

All right， let's look at an example。And I should probably warn you if you're hungry。

 this is not going to be a fun lecture。So here's。My least favorite。

 because I always want to eat more than I'm supposed to eat。So the point is。

 typicallynapsack problems are not physical knapsacks， but some conceptual idea。

So let's say that I'm allowed 1，500 calories of food。And these were my options。



![](img/2749cb9817f16b7f57eee71e727f7e17_28.png)

I have to go about deciding。Looking at these food， and it's interesting again。

 there's things showing up on your screen that are not showing up on my screen。But。They're harmless。

 things like how my mouse works。Any rate， so I'm trying to take some。Fraction of this food。

And it can't add up to more than 1500 calories。The problem might be that once I take something that's 1485 calories。

 I can't take anything else or maybe 1200 calories， and everything else is more than 300。

So once I take one thing， it constrains possible solutions。 A greedy algorithm， as we'll see。

 is not guaranteed to give me the best answer。

![](img/2749cb9817f16b7f57eee71e727f7e17_30.png)

All right， let's look at a formalization of it。So each item is represented by a pair。😡。

The value of the item and the weight of the item。And let's assume the Napsack can accommodate items with a total weight of no more than W。



![](img/2749cb9817f16b7f57eee71e727f7e17_32.png)

I apologize for the short variable names， but they're easier to fit on a slide。



![](img/2749cb9817f16b7f57eee71e727f7e17_34.png)

Finally， we're going to have a vector L。Of length n。Representing the set of available items。

This is assuming we have n items to choose from。

![](img/2749cb9817f16b7f57eee71e727f7e17_36.png)

So each element of the vector represents an item。Okay， so those are the items we have。

 And then another vector V。

![](img/2749cb9817f16b7f57eee71e727f7e17_38.png)

Is going to indicate whether or not an item was taken。



![](img/2749cb9817f16b7f57eee71e727f7e17_40.png)

So essentially， I'm going to use a binary number to represent the set of items I choose to take。

For item3， say if bit3 is0， I'm not taking the item。If bit3 is one。Then I am taking the item。

So it just shows I can now very nicely represent what I've done by a single vector。Of zeros and ones。

All right， let me pause for a second。Does anyone have any questions about this setup？

It's important to get this set up because what we're going to see now depends upon。

That setting in your head。Okay， so I've kind of used mathematics to describe the backpack problem。

And that's typically the way we deal with these optimization problems。

 We start with some informal description， and then we translate them into a mathematical representation。

So here it is。

![](img/2749cb9817f16b7f57eee71e727f7e17_42.png)

We're going to try and find a vector V。That maximizes the sum。Of V sub I。



![](img/2749cb9817f16b7f57eee71e727f7e17_44.png)

Times I sub I。Now， remember， what I sub I is the value of the item。V sub I is either 0 or one。So。

 if I。Didn't take the item on multiplying its value by 0。 So it contributes nothing to the sum。

If I did take the item， I'm multiplying its value by one。

 So the value of the item gets added to the sum。

![](img/2749cb9817f16b7f57eee71e727f7e17_46.png)

So that tells me the value of V。And I want to get the most valuable V I can get。

Subject to the constraint。That if I look at the items。 weight。And multiply it by V。

The sum of the weights is no greater than W。

![](img/2749cb9817f16b7f57eee71e727f7e17_48.png)

So I'm playing the same trick with the values of multiplying each one by 0 or one。And。

That's my constraint。Make sense。All right。So now we have the problem formalized。s how do we solve it？

Well。The most obvious solution is brute force。I enumerate all possible combinations of items。



![](img/2749cb9817f16b7f57eee71e727f7e17_50.png)

Better to say。I generate all subs。Of the items that are available。

 I don't know why it says subjects here。But we should have said items， Let me fix that。



![](img/2749cb9817f16b7f57eee71e727f7e17_52.png)

This is called the power set。So the power set of a set includes the empty subset。



![](img/2749cb9817f16b7f57eee71e727f7e17_54.png)

It includes the set that includes everything。And every。Thing in between。So subsets of size 1。

 subsets of size 2， etca。So now I've generated all possible sets of items。

I can now go through and sum up the weights and remove all those sets that way more than I'm allowed。

And then from the remaining combinations， choose anyone whose value is the largest。



![](img/2749cb9817f16b7f57eee71e727f7e17_56.png)

I say choose anyone because there could be ties， in which case I don't care which I choose。So。

It's pretty obvious that this is going to give you a correct answer。

You're considering all possibilities， and choosing a winner。Unfortunately。

 it's usually not very practical， what we see here。



![](img/2749cb9817f16b7f57eee71e727f7e17_58.png)

Heres。That's what the power set is。 if you have 100 vector。Not very practical， right。

 Even for a fast computer generating that many possibilities is going to take a rather long time。



![](img/2749cb9817f16b7f57eee71e727f7e17_60.png)

So kind of disappointing。 We look at it and say， well， we've got a brute forest algorithm。

 It will solve the problem。But。It'll take too long。 We can't actually do it。

 H00 It' a pretty small number， right， We often end up solving optimization problems。

 where N is something closer to 1000， sometimes even 1 million。Clearly。

 brute force isn't going to work。So that raises the next question。 Are we just being stupid。

Is there a better algorithm that I should have showed you， I shouldn't say we。

 am I just being stupid。Is there a better algorithm that would have given us the answer？

The sad answer to that is no。For the Napsackack problem。And indeed， many optimization problems。

Are inherently exponential。What that means is there is no algorithm that provides an exact solution to this problem。

Whose worst case running time is not exponential in the number of items。

It is an exponentially hard problem。It。There is no really good solution。But。

That should not make you sad。Because while there's no perfect solution。

We're going to look at a couple of really， very good solutions。

That will make this poor woman a happier person。So let's start with the greedy algorithm。

 I already talked to you about greedy algorithms。So， it could hardly be simpler。



![](img/2749cb9817f16b7f57eee71e727f7e17_62.png)

We say while thenapsack is not full， put the best available item into thenapsackack。



![](img/2749cb9817f16b7f57eee71e727f7e17_64.png)

When it's full， we're done。You do need to ask a question。What does best mean。

Is the best item the most valuable。

![](img/2749cb9817f16b7f57eee71e727f7e17_66.png)

Is it the least expensive in terms of， say， the fewest calories。In my case。

 or is it the highest ratio of value to units？Maybe I think a calorie in a glass of beer is worth more than a calorie in a bar of chocolate。

Maybe vice versa。Which gets me to a concrete example。So you're about to sit down to a meal。

You know how much you value the various different foods。For example。

 maybe you like donuts more than you like apple。You have a calorie budget。

 And here we're going to have a fairly austere budget。 It's only one meal。

 It's not the whole day of 750 calories， And we're going to have to go through menus and choose what to eat。

 That is， as we've seen a knapsackack problem。

![](img/2749cb9817f16b7f57eee71e727f7e17_68.png)

They should probably have an Apsack solver at every McDonald's and Burger King。So。



![](img/2749cb9817f16b7f57eee71e727f7e17_70.png)

Here's a menu I just made up。Of wine， beer， pizza， burger， fries， Coke， apples， and a donut。

And the value。I might place on each of these and the number of calories that actually are in each of these。



![](img/2749cb9817f16b7f57eee71e727f7e17_72.png)

And we're going to build a program。That will find an optimal menu。And if you don't like this menu。

 you can run the program and change the values to be whatever you like。Well。

 as you saw off you took6 triple01， we liked to start。With an abstract data type。

 like to organize our program around data abstractions。



![](img/2749cb9817f16b7f57eee71e727f7e17_74.png)

So I've got this class food。I can initialize things。 I have a get value， a get cost。Denssity。

 which is going to be the value divided by the cost。And then a string representation。

So nothing here that you should not all be。Very familiar with。

Then I'm going to have a function called build menu。

Which will take in a list of names and a list of values。Of equal length。

And a list of calories that are all the same length。



![](img/2749cb9817f16b7f57eee71e727f7e17_76.png)

And it will build the menu。Okay， so it's going to be a menu of tuples。A menu of foods rather。

 And I build each food by giving it its name， its value and its caloric content。Now I have a menu。

Now comes the fun part。Here is an implementation of a greedy algorithm。



![](img/2749cb9817f16b7f57eee71e727f7e17_78.png)

I called it a flexible greedy。😡，Primarily because of this key function over here。

So you'll notice in red。There's a parameter called key function。

That's going to be map the elements of items to numbers。So。It will。Be used to sort the items。



![](img/2749cb9817f16b7f57eee71e727f7e17_80.png)

So I want to sort them from best to worse。

![](img/2749cb9817f16b7f57eee71e727f7e17_82.png)

And this function will be used to tell me what I mean by best。So maybe key function will just return。

The value， or maybe it will return the weight， or maybe it will return some function of the destin。

Of the density。But the， the idea here is I want to use one greedy algorithm。

Independently of my definition of best。So I use key function to define what I mean by best。

So I'm going to come in， I'm going to sort it from best to worst。

And then for I enlen of items subcopy。

![](img/2749cb9817f16b7f57eee71e727f7e17_84.png)

I'm being good。 I've copied it。 That's why you sort it rather than sort。



![](img/2749cb9817f16b7f57eee71e727f7e17_86.png)

I don't want to have a side effect in the parameter。In general， it's not good hygiene to do that。

And so I'll go through it in order from best to worst。And if the value is less than the maximum cost。

If putting it in would keep me under the cost or not over the cost， I put it in。And I just do that。



![](img/2749cb9817f16b7f57eee71e727f7e17_88.png)

Until I can't put anything else in。So I might skip a few because I might get to the point where there's only a few calories left and the next best item。

Is over that budget。But maybe further down， I'll find one that is not over it and put it in。Okay。

 that's why I can't exit as soon as I reach。As soon as I find an item that won't fit。

And then I'll just return。Just make sense。Does anyone have any doubts about whether this algorithm actually works？

I hope not， because I think it does work。Let's ask the next question。How efficient do we think it is？

What is the efficiency of this algorithm。Well。Let's see where the time goes。



![](img/2749cb9817f16b7f57eee71e727f7e17_90.png)

It'sThe the algorithm we just looked at。So I deleted the comments。

 so we have a little more room in the slide。嗯。

![](img/2749cb9817f16b7f57eee71e727f7e17_92.png)

Who wants to make a guess？By the way， this is the question。 So please go answer the questions。

 We'll see how people do。But we can think about it as well together。嗯。Well。

Let's see where the time goes。The first thing is that the so。



![](img/2749cb9817f16b7f57eee71e727f7e17_94.png)

So I'm going to sort all the items。And。We heard from Professor Grimson how long the sort takes。



![](img/2749cb9817f16b7f57eee71e727f7e17_96.png)

See who remembers。Python uses something called Tim sort。

 which is a variant of something called Quicksort。Which has the same worst case complexity as merge sort。

And so we know that is in log n。We're in。In this case would be the line of items。Okay。So。

We know we have that。

![](img/2749cb9817f16b7f57eee71e727f7e17_98.png)

Then we have a loop。How many times we go through this loop？



![](img/2749cb9817f16b7f57eee71e727f7e17_100.png)

Well， we go through the loop。N times。Once for each item。Because we do end up looking at every item。

And if we know that， what's the order？And log in。Plus， n I guess is order n log n。Right。So。

It's pretty efficient。And we can do this for big numbers， like a million。

log of a million times a million is not a very big number。So。It's very efficient。



![](img/2749cb9817f16b7f57eee71e727f7e17_102.png)

All right， here's some code that uses greedy。啊。Takes in the items， the constraint。

In this case will be the weight。And。Just calls greedy。ButWith the key function and principle we have。



![](img/2749cb9817f16b7f57eee71e727f7e17_104.png)

So， we're going to。Test greedies， I actually think I use 7，50 in the code， but we can use 800。

 It doesn't matter。And here's something we haven't seen before。



![](img/2749cb9817f16b7f57eee71e727f7e17_106.png)

So use greedy by value to allocate and it calls test greedy with food max units and food dot get value。

 Notice it's passing the function。 That's why it's not no closed parentheses after it。

Use greedy to allocate。And then we have something pretty interesting。

What's going on with this Lambda？So， here。We're going to be using greedy by density to allocate。

 I'm actually， sorry， this is greedy by cost。And you'll notice what we're doing is we don't want to pass in。



![](img/2749cb9817f16b7f57eee71e727f7e17_108.png)

The cost， right。Because we really want。The opposite of the cost， right， We want。

 we want to reverse the sort。Because we want the cheaper items to get chosen first。

 the ones that have fewer calories， not the ones that have more calories。As it happens。

 when I define cost， I defined it in the obvious way， the total number of calories。

So I could have gone and written another function to do it。But since it was so simple。

 I decided to do it in line。So let's talk about Lambda and then come back to it。

Lambda is used to create an anonymous function。

![](img/2749cb9817f16b7f57eee71e727f7e17_110.png)

Anonymous in the sense that it has no name。So you start with the keyword lambmbda。

You then give it a sequence of identifiers。And then， some expression。

What Lambda does is it builds a function。That evaluates that expression。

On those parameters and returns the result of evaluating the expression。



![](img/2749cb9817f16b7f57eee71e727f7e17_112.png)

So。Instead of writing death。I have in line， to find a function。



![](img/2749cb9817f16b7f57eee71e727f7e17_114.png)

So if we go back to it here。You can see that what I've done is lambda x。One divided by food。

 get cost。Of x。

![](img/2749cb9817f16b7f57eee71e727f7e17_116.png)

Notice food is the class name here。

![](img/2749cb9817f16b7f57eee71e727f7e17_118.png)

So I'm taking the function get cost from the class food。And I'm passing it the parameter X。

Which is going to be what？

![](img/2749cb9817f16b7f57eee71e727f7e17_120.png)

What's the type of X going to be。I can wait you out。

What does the type of X have to be for this lambda expression to make sense。Well。

Go back to the class， food。What's the type of the argument of get cost。

What's the name of the argument to get cost？ That's an easier question。All right。

 we'll go back and we'll look at it。

![](img/2749cb9817f16b7f57eee71e727f7e17_122.png)

What's the type of the argument to get cost？

![](img/2749cb9817f16b7f57eee71e727f7e17_124.png)

Food， thank you。So I do have speaking of food。We do have a tradition in this class。

That people who answer questions correctly get rewarded with food。Oh。Npoli would have caught that。

All right， so it has to be of type food， right？Because itself in the class food。



![](img/2749cb9817f16b7f57eee71e727f7e17_126.png)

So if we go back to here。This X。Has to be of type food， right？



![](img/2749cb9817f16b7f57eee71e727f7e17_128.png)

And sure enough。When we use it， it will be。 Let's now use it。I should point out that。

Land but can be really handy， as it is here。And。It's possible to write amazing， beautiful。

 complicated Lambda expressions。😊，And back in the good old days of 6 double01。

 people learned to do that。嗯。And then they learned that they shouldn't。

My view on Lambda expressions is if I can't fit it in a single line。

 I just go write death and write a function definition because it's easier to debug。

But for one liner， Sda is great。All right。Let's look at using greedy。



![](img/2749cb9817f16b7f57eee71e727f7e17_130.png)

So here's this function， test greed。Takes foods in the maximum number of units。

And it's going to go through。And it's going to test all three greedy algorithms。And we just saw that。

 and then here is the call of it。And so I picked up some names and the values。

 This is just the menu we saw。 I'm going build the menus。 and I'm going to call test readies。



![](img/2749cb9817f16b7f57eee71e727f7e17_132.png)

So let's go look at the code。It does this。So here you have it。Or maybe you don't。

Because every time I switch applications。对。Windows the sides。

 I don't want to show you the screen anyway。It really shouldn't be necessary。Keep changes。

Why I keeps forgetting， I don't know anyway， so here's the code。



![](img/2749cb9817f16b7f57eee71e727f7e17_134.png)

It's all the code we just looked at。 Now let's run it。Well。What we see here。

Is that we use greedy by value to allocate 7 or 50 calories， and it chooses the burger。

 the pizza and the wine。For a total of。A value of 284。happiness points， if you will。

On the other hand， if we use greedy by cost。I get 318。Happiness points and a different menu。

 the apple， the wine， the cold of the beer and the donut， I've lost the pizza and the burger。Yeah。

I guess this is what I。Signed up for when I put my preferences on。嗯。Oh。

 and here's another solution with 318。呃。Apple wine， oh。Yeah， all right。

So I actually got the same solution， but it just found them in a different order。 right。

 Why did it find them in a different order， Because the sort order was different。



![](img/2749cb9817f16b7f57eee71e727f7e17_136.png)

Because in this case， I was sorting by density。So。From this。

 we see an important point about greedy algorithms， right。That we used the algorithm。

And we got different answers。嗯。Why do we have different answers。

The problem is that a greedy algorithm makes a sequence of local optimizations。

Choses the locally optimal answer at every point。And that doesn't necessarily add up to a globally optimal answer。

This is often illustrated。By showing an example of， say， hill climbing。

So imagine you're in a terrain。Looks something like this。And you want to。

Get to the highest point you can get。So you might choose as a greedy algorithm。If you can go up。

 go up。If you can't go up， you stop， right。 So whenever you get a choice， you go up。

And so if I start here。😡，I could。Right in the middle， maybe say all right。It's not up。

 but it's not down either。 So I'll go either left or right。And let's say I go right。

 So I come to here。 and then I'll just make my way up to the top of the hill。

Making a locally optimal decision head up at each point。And I'll get here， and I'll say， well， now。

 any place I go takes me to a lower point。So I don't want to do it， right。

Because the greedy algorithm says， never go backwards。So I'm here and I'm happy。On the other hand。

If I had gone here。😡，For my first step。Then my next step up would take me up， up， up。 I get to here。

And I'd stop。And say， okay。No way to go， but down。 I don't want to go down。 I'm done。

 And what I would find is I'm at a local maximum rather than a global maximum。

And that's the problem with greedy algorithms。That you can get stuck。At a local optimal point。

And not get to the best one。Now， we could ask the question。是。What？Can I just say。

 don't worry about a density， sayy， will always get me the best answer。Well。

 I've tried a different experiment。 Let's say I'm feeling expansive。

 and I'm going to allow myself 1000 calories。

![](img/2749cb9817f16b7f57eee71e727f7e17_138.png)

Well。Here what we see is the winner will be。Greedy by value。Happens to find a better answer。

 424 instead of 413。

![](img/2749cb9817f16b7f57eee71e727f7e17_140.png)

So there is no way to know in advance。Sometimes this definition of best might work。

 Sometimes that might work。 Sometimes no definition of best will work。 And you can't get。

To a good solution， or you can get to a good solution。

 You can't get to an optimal solution with the greedy algorithm。On Wednesday。

 we'll talk about how do you actually guarantee finding an optimal solution。

In a better way than brute force。See you then。

![](img/2749cb9817f16b7f57eee71e727f7e17_142.png)