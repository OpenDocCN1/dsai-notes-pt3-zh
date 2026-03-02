# 约翰霍普金斯大学《计算机科学的统计方法｜Statistical Methods for Computer Science》中英字幕 p18 17_R语言教程.zh_en -BV1r483zbEzN_p18-

![](img/37752e25380dacd3a400858e09ee6586_0.png)

Hello guys， Dr。 Tony Johnson here， I am going to walk you through this tutorial on how we can use computer programming to explore probability。

 and in particular we're going to be using the program that you looked at in module1 with Dr。

 McCulllor， we're going to look at this computer program called R。

So the first thing we want to do is we've got this neat little thing you can do in R。

 you can do this in other languages as well， whereby we can like basically。

Determine what some previous packages and functions that we're going to need in order to do some things we're going to do later and all of that code can be located in one central place and so in here you'll see in Blackboard there's going to be a file called Stat tools。



![](img/37752e25380dacd3a400858e09ee6586_2.png)

![](img/37752e25380dacd3a400858e09ee6586_3.png)

And if you look， stackt tools is basically a bunch of needed。



![](img/37752e25380dacd3a400858e09ee6586_5.png)

Needed packages。

![](img/37752e25380dacd3a400858e09ee6586_7.png)

Um and。Small little functions that you don't want to have to keep doing over and over and over again and this is just for demonstrative purposes。

 you know how you would actually define these and all of this you can find in any R tutorial or any R you could Google it and you can find out how to write functions it's similar to any other language and so I don't suspect that as computer scientists you would have any problems with that。



![](img/37752e25380dacd3a400858e09ee6586_9.png)

![](img/37752e25380dacd3a400858e09ee6586_10.png)

![](img/37752e25380dacd3a400858e09ee6586_11.png)

So what we want to do。It's going to go ahead and run that。

 And so I'm going to go ahead and hit source。 And what this is going to do is this is going to run。



![](img/37752e25380dacd3a400858e09ee6586_13.png)

All my packages here， it's going to open them all up and then it's going to let it's going to source the functions that are now available to me。

 And these are custom functions that are written specifically for whatever task that you're working on at the time。

 they're not globally available， in other words， if Doctor McCllough was to run open his computer and open up R。

 he wouldn't be able to run these functions unless he source this particular file。



![](img/37752e25380dacd3a400858e09ee6586_15.png)

![](img/37752e25380dacd3a400858e09ee6586_16.png)

![](img/37752e25380dacd3a400858e09ee6586_17.png)

![](img/37752e25380dacd3a400858e09ee6586_18.png)

Okay， so what we're talking about now is we're talking about probability if you notice in my environment。

 I only have functions declared。And this first command actually clears the global environment。

 and I think Dr。 McClellallough mentioned that before。

And then after you clear the global environment， you have to make sure that you source the functions that you're going to need。

And so let's talk about some things that are specific to this module。

 so the first thing if we look at we can look at a sample space and so in this case。

 we can assign a sample space by simply utilizing this tool called a data frame。And the data frame。

 we can give it a heading and we could say that here is a coin and it lands or an object okay。

 and it can land up， it can land down up or on its side and when we run that basically what we find is now in my environment this data frame is defined and it's a fact variable with three levels and what are the three levels。

 theyre up down inside。

![](img/37752e25380dacd3a400858e09ee6586_20.png)

![](img/37752e25380dacd3a400858e09ee6586_21.png)

![](img/37752e25380dacd3a400858e09ee6586_22.png)

Now， this is a sample space because there are no other possibilities within this particular data frame。



![](img/37752e25380dacd3a400858e09ee6586_24.png)

and so you can see here it lists out what I get if I were to invoke this idea。

 this variable which is lands and that is the sample space。Okay， so let's look at the next thing。

 what if I wanted to define the sample space for rolling of a die？

Well there is a function called sample， which is really neat。And in this function。

 I can establish that there are six possibilities， okay？All right。

 and so what I can do now is I can sample from these six possibilities 30 times。



![](img/37752e25380dacd3a400858e09ee6586_26.png)

![](img/37752e25380dacd3a400858e09ee6586_27.png)

And so as you can see， if I was to now invoke， die。



![](img/37752e25380dacd3a400858e09ee6586_29.png)

I get a sample and this is me rolling a die 30 times， this is the outcome。All right。

How about flipping a coin where here again， I define the sample space here as heads or tails。



![](img/37752e25380dacd3a400858e09ee6586_31.png)

Without any other。Deeclarations， its assumed that there is as likely an outcome of heads as there is of tails。



![](img/37752e25380dacd3a400858e09ee6586_33.png)

And I can do that 30 times， and this is flipping a coin， so this is another simulation。

 and so here again， if I type coin and I want to see it。😊。



![](img/37752e25380dacd3a400858e09ee6586_35.png)

![](img/37752e25380dacd3a400858e09ee6586_36.png)

![](img/37752e25380dacd3a400858e09ee6586_37.png)

Now I get a simulation of flipping a coin 30 times。



![](img/37752e25380dacd3a400858e09ee6586_39.png)

All right， now。There is a neat function。

![](img/37752e25380dacd3a400858e09ee6586_41.png)

That is a part of the Pro package， and the Pro package is one of those packages that we install when we sourced our stackt tools。



![](img/37752e25380dacd3a400858e09ee6586_43.png)

![](img/37752e25380dacd3a400858e09ee6586_44.png)

And this function is called tos coin。 And it's really neat because it will present。



![](img/37752e25380dacd3a400858e09ee6586_46.png)

A toing costs sample space for me right， and so in this case if I toss a coin one time， right。

 it gives me the sample space of possible outcomes。



![](img/37752e25380dacd3a400858e09ee6586_48.png)

![](img/37752e25380dacd3a400858e09ee6586_49.png)

And the sample space of possible outcomes of a twining cause will be heads or tails。



![](img/37752e25380dacd3a400858e09ee6586_51.png)

But now think back to when we were talking about counting in module number one。

 what would be the sample space？

![](img/37752e25380dacd3a400858e09ee6586_53.png)

If I was the Tsa coin three times。

![](img/37752e25380dacd3a400858e09ee6586_55.png)

Well， in that case。I get a different experiment and notice that the sample space now there are eight values in the sample space opposed to the two values before。



![](img/37752e25380dacd3a400858e09ee6586_57.png)

![](img/37752e25380dacd3a400858e09ee6586_58.png)

And these eight values correspond to there are two outcomes and I'm doing that three times and that corresponds to two。



![](img/37752e25380dacd3a400858e09ee6586_60.png)

And basically， I'm doing it n times in this case three times， and that's where I get eight from。



![](img/37752e25380dacd3a400858e09ee6586_62.png)

So that goes back to counting， so my expectation is that in the sample space of three coin tosses。

 there can only be at most eight unique outcomes。Well， lucky for us。

 we can do the same thing with Ro a die right， so in this case。

 we can say roll a die if I roll one dice， one die， excuse me。



![](img/37752e25380dacd3a400858e09ee6586_64.png)

![](img/37752e25380dacd3a400858e09ee6586_65.png)

I get a sample space of six， one through six are the only outcomes， what about two die？



![](img/37752e25380dacd3a400858e09ee6586_67.png)

![](img/37752e25380dacd3a400858e09ee6586_68.png)

Right if I have two die， well now for two die。

![](img/37752e25380dacd3a400858e09ee6586_70.png)

I have 36 outcomes。Right well let's see is that correct， Well let's go back to counting right。

 So if I have six outcomes and I do it in times and this time I'm going to do it two times。

 then my expectation is there will be 36 items in the sample space。



![](img/37752e25380dacd3a400858e09ee6586_72.png)

![](img/37752e25380dacd3a400858e09ee6586_73.png)

![](img/37752e25380dacd3a400858e09ee6586_74.png)

We can also look at sample space in terms of drawing cards， right， so there is a predefined。



![](img/37752e25380dacd3a400858e09ee6586_76.png)

![](img/37752e25380dacd3a400858e09ee6586_77.png)

Variable within the probability or the pro package called cards。

 I would just list the beginning because we don't want to list them all。



![](img/37752e25380dacd3a400858e09ee6586_79.png)

![](img/37752e25380dacd3a400858e09ee6586_80.png)

But in this case， you can see when I use the function head。

 what it does is it gives me the first six values within this variable。



![](img/37752e25380dacd3a400858e09ee6586_82.png)

Now， we would expect that there would be a lot。Of numbers in this in this variable。



![](img/37752e25380dacd3a400858e09ee6586_84.png)

Right， if we were to。

![](img/37752e25380dacd3a400858e09ee6586_86.png)

A sign is variable because we would have two all the way through。The ace。

 which would be 13 for each suit。 and so the total number then would be 52。



![](img/37752e25380dacd3a400858e09ee6586_88.png)

We could see。The end of that， if we do instead of head， if we do tail。



![](img/37752e25380dacd3a400858e09ee6586_90.png)

This should work tail and say cards。

![](img/37752e25380dacd3a400858e09ee6586_92.png)

And you can see。The last suit。The 52nd item is going to be spayde。



![](img/37752e25380dacd3a400858e09ee6586_94.png)

So you can imagine then if I was going to draw two cards。

that would be there there would be a lot of different possibilities for that right because there are 52 different outcomes because you have the rank of the card and the suit and if I draw if I draw one card。

 there's one out of 52 if I draw two cards， can you can you calculate what that number would be。



![](img/37752e25380dacd3a400858e09ee6586_96.png)

![](img/37752e25380dacd3a400858e09ee6586_97.png)

![](img/37752e25380dacd3a400858e09ee6586_98.png)

![](img/37752e25380dacd3a400858e09ee6586_99.png)

You should be able to do that。

![](img/37752e25380dacd3a400858e09ee6586_101.png)

All right， there's another type of of。

![](img/37752e25380dacd3a400858e09ee6586_103.png)

Simulation or experiment that is very popular is very common。

 and that is when you're drawing something from out of an urn， okay。

 and there are two ways you can do that。

![](img/37752e25380dacd3a400858e09ee6586_105.png)

You can draw something from an urn where you replace the item。



![](img/37752e25380dacd3a400858e09ee6586_107.png)

And you can draw something from an urn where you do not replace the item。



![](img/37752e25380dacd3a400858e09ee6586_109.png)

And so this urn sample is very useful because we can define that there are three items in the urn。

 and I can define how many items I'm drawing out at a time。



![](img/37752e25380dacd3a400858e09ee6586_111.png)

![](img/37752e25380dacd3a400858e09ee6586_112.png)

![](img/37752e25380dacd3a400858e09ee6586_113.png)

Then I can define whether or not I replace the items。



![](img/37752e25380dacd3a400858e09ee6586_115.png)

Before the next draw， do I replace the items and are the items ordered in that？



![](img/37752e25380dacd3a400858e09ee6586_117.png)

Okay， are they ordered in that and so in this case with replacement。



![](img/37752e25380dacd3a400858e09ee6586_119.png)

I'm going to run this and we can see that here。

![](img/37752e25380dacd3a400858e09ee6586_121.png)

嗯。

![](img/37752e25380dacd3a400858e09ee6586_123.png)

I'm drawing out two items at a time。

![](img/37752e25380dacd3a400858e09ee6586_125.png)

And because I'm replacing the item， it is possible for me to draw the same item。



![](img/37752e25380dacd3a400858e09ee6586_127.png)

Both times。It's possible for me to draw the same item both times。

 Well let's look at without replacing it。

![](img/37752e25380dacd3a400858e09ee6586_129.png)

![](img/37752e25380dacd3a400858e09ee6586_130.png)

Now， without replacement， notice that it is not possible for me to draw the same item。



![](img/37752e25380dacd3a400858e09ee6586_132.png)

![](img/37752e25380dacd3a400858e09ee6586_133.png)

So whereas with replacement， I draw an item。And then I put the items， I record what item I drew。

 so I drew the first item。

![](img/37752e25380dacd3a400858e09ee6586_135.png)

![](img/37752e25380dacd3a400858e09ee6586_136.png)

And then I put everything back， and I draw again。 so it's possible that I could draw a1，1。

 That is with replacement。 without replacement。 However， if I draw a one。

 the only possibility for me to draw on my second draw is a two or a three。



![](img/37752e25380dacd3a400858e09ee6586_138.png)

![](img/37752e25380dacd3a400858e09ee6586_139.png)

![](img/37752e25380dacd3a400858e09ee6586_140.png)

And so you can see that with replacement， the sample space is going to be nine without replacement。

 the sample space is going to be six， so you definitely want to be aware of that。



![](img/37752e25380dacd3a400858e09ee6586_142.png)

![](img/37752e25380dacd3a400858e09ee6586_143.png)

![](img/37752e25380dacd3a400858e09ee6586_144.png)

Kitty， you want to be aware of that。So let's。

![](img/37752e25380dacd3a400858e09ee6586_146.png)

So we're going to go ahead and， so let's clear our environment again。

 so we're going to clear the environment here。

![](img/37752e25380dacd3a400858e09ee6586_148.png)

And。

![](img/37752e25380dacd3a400858e09ee6586_150.png)

When we do， they want to make sure that we source。

![](img/37752e25380dacd3a400858e09ee6586_152.png)

As matter of fact， I'll just copy this here because after I cleared the environment。

 I cleared out all the functions too， so I want to make sure I source my function again。



![](img/37752e25380dacd3a400858e09ee6586_154.png)

![](img/37752e25380dacd3a400858e09ee6586_155.png)

Make sure we got our functions back。I'm not sure exactly when we're going to use them。

 but I know it's going to be soon， so I want to make sure all my functions are there。



![](img/37752e25380dacd3a400858e09ee6586_157.png)

![](img/37752e25380dacd3a400858e09ee6586_158.png)

Okay， so here's a sample space where I'm going to look at all the cards in a deck and I'm going to。

Mine is will subtract the jokers。

![](img/37752e25380dacd3a400858e09ee6586_160.png)

And so as I expect。S now is 52 observations。And there are going to be two variables right。

 and so what are those factors， there are two factors， the rank is a factor with 13 levels。



![](img/37752e25380dacd3a400858e09ee6586_162.png)

![](img/37752e25380dacd3a400858e09ee6586_163.png)

![](img/37752e25380dacd3a400858e09ee6586_164.png)

And the suit is a factor with four levels， club， diamonds， and that kind of thing。



![](img/37752e25380dacd3a400858e09ee6586_166.png)

All right， so now let's talk about set union intersection in difference。

 So we were looking at in the lecture。 we looked at sets。 we looked at union and intersection。

 So how do we do that in R Well， once we have the sample space defined what we can do now is we can go here and we can say I want to see the subset of S where the suit is equal to hearts。

 And if I do that you can see I get a new variable。



![](img/37752e25380dacd3a400858e09ee6586_168.png)

![](img/37752e25380dacd3a400858e09ee6586_169.png)

![](img/37752e25380dacd3a400858e09ee6586_170.png)

![](img/37752e25380dacd3a400858e09ee6586_171.png)

![](img/37752e25380dacd3a400858e09ee6586_172.png)

This variable A。

![](img/37752e25380dacd3a400858e09ee6586_174.png)

And is the observations of。Only hearts。OkayIt's the observation of only heart now there are only going to be 13 values here。

These numbers are the indices of where those values were found in the original sample space。



![](img/37752e25380dacd3a400858e09ee6586_176.png)

But note that there are only 13 values here。I would just look at another set。

What if I want to look at the samples， the subset？Of the sample space。

 which is we're going to call B。And I want the rank now to be in the interval five to eight。

And that's why I'm using this。Nice little function here， just press sign in。

 And when I do that here notice I get only values from  five to 8， but I get them for each suit。



![](img/37752e25380dacd3a400858e09ee6586_178.png)

![](img/37752e25380dacd3a400858e09ee6586_179.png)

![](img/37752e25380dacd3a400858e09ee6586_180.png)

Okay， each suit， there are 16 observations here。So now I have two sets defined。

 and so the question now would be， okay， which set？Um what can I do with these， well。

 one thing I could do is I can do union。So what do you think the union of set A and set B would be？

Okay， so we're looking at set A and set B and we're looking at the union， Well。

 if you think about it， set A is only hearts， set B is five through8 of every suit， so the union。



![](img/37752e25380dacd3a400858e09ee6586_182.png)

![](img/37752e25380dacd3a400858e09ee6586_183.png)

![](img/37752e25380dacd3a400858e09ee6586_184.png)

It's going to be whatt。

![](img/37752e25380dacd3a400858e09ee6586_186.png)

Look at what we have。The union is going to be all the hearts。



![](img/37752e25380dacd3a400858e09ee6586_188.png)

And。Clubs， diamonds and spade。Because the union is taking both sec together。Well。

 how about the intersection， what would the intersection be？



![](img/37752e25380dacd3a400858e09ee6586_190.png)

Well， if you guessed the intersection would be five through eight and only hearts。

 then you were correct。Okay， you are correct。 Now there are some other things we can do called set difference。

 Okay， and the syntax here set diF A comma B。Set di a a comma B。

 meaning that I'm going to start with set A， and I'm going to subtract set B。 And when I do that。

 I get。

![](img/37752e25380dacd3a400858e09ee6586_192.png)

This。

![](img/37752e25380dacd3a400858e09ee6586_194.png)

So look at what I have， I start with set A， which are all hearts。Right。Then I subtract set B。

 which would be。The hearts between 5 and 8。 And if you notice， those are missing。

Now set diff A comma B。Does not equal set di B comm A。



![](img/37752e25380dacd3a400858e09ee6586_196.png)

And as you can see here again， we start it with， if we start it with B， it's5 through8 of all the。



![](img/37752e25380dacd3a400858e09ee6586_198.png)

Suits。And then I subtract from that。A， which will be all the hearts。 And that's what you get there。

There's one other thing we want to look at and that is the complement we can use set diF to determine the complement and so basically if I take the entire sample space and I subtract out。

One set， let's say A or B， then what that equals is the complement of set A or set B。

 So in this case， the complement of a would be all suits， except for hearts。



![](img/37752e25380dacd3a400858e09ee6586_200.png)

![](img/37752e25380dacd3a400858e09ee6586_201.png)

And I neat， that is so cool。

![](img/37752e25380dacd3a400858e09ee6586_203.png)

Right。So let's look at some other things， okay， what if we wanted to create a probability space。

 we wanted to create a probability space。

![](img/37752e25380dacd3a400858e09ee6586_205.png)

![](img/37752e25380dacd3a400858e09ee6586_206.png)

Okay， so let's。Let's clear our environment again and you don't have to clear the environment every time like I'm doing I'm just doing that because I want I don't want you to be cluttered on this side。

 I only want over here what we're actually working on。



![](img/37752e25380dacd3a400858e09ee6586_208.png)

Okay， so let me go ahead and。Add my source again。And I'm going to make sure I have those running。



![](img/37752e25380dacd3a400858e09ee6586_210.png)

And so here we go。 So our sample space now is going to be to roll a die。

And we're going to row one die， and so the sample space is going to be one through six。



![](img/37752e25380dacd3a400858e09ee6586_212.png)

But in order to build a probability space， I need not only the outcome or the event。

 I need the probability。Or likelihood that that event will occur。 Well。

 one way we can do that is we can say。I want to repeat1 sixth， right， one over six。

 there are six items， I want to repeat that。And I can create this vector P and what this is is this is basically the probability of one event。



![](img/37752e25380dacd3a400858e09ee6586_214.png)

Given a probability space of six。Now what I want to do is I want to put those all together right and I'm going to use a function here called Pro space and so Pro space would take the sample space and it would take the probabilities and it will put it together in this form so you can see。



![](img/37752e25380dacd3a400858e09ee6586_216.png)

![](img/37752e25380dacd3a400858e09ee6586_217.png)

If I get a1， here's the probability of rolling a1。Here's the probability of rolling a four。

And notice that these are all equally likely outcomes， right， they're all equally likely。



![](img/37752e25380dacd3a400858e09ee6586_219.png)

Well， there's another way we could do that。If I just wanted to say the number one through six without specifying S as rh die or whatever。



![](img/37752e25380dacd3a400858e09ee6586_221.png)

![](img/37752e25380dacd3a400858e09ee6586_222.png)

That also works。Well， what if I just do one through6 and I don't tell prop space what the probabilities are。

 it assumes automatically that the probabilities are going to be equally likely。

 So if I had an experiment that had seven outcomes and those outcomes were equally likely。

I have equally proportioned probability space， it knows to do that automatically。Finally。

 if I just wanted to use the row die and I said row die， one die， I mean。

If I execute the makespace option as true。

![](img/37752e25380dacd3a400858e09ee6586_224.png)

Roe Di would do exactly what we've done before， okay。



![](img/37752e25380dacd3a400858e09ee6586_226.png)

Now let's talk a little bit about。Outcomes that are not equally likely， okay。

 if we had an outcome that was not equally likely。

![](img/37752e25380dacd3a400858e09ee6586_228.png)

So suppose there is an unfair coin。 Well， if there is an unfair coin and there's a coin toss。

 we can specify what we know about the likelihood or the probabilities that those coins would land on one side or the other by just simply creating a vector。

Okay。😊。

![](img/37752e25380dacd3a400858e09ee6586_230.png)

And equating props to that vector， and so in this case。

 you can see heads is more likely to occur than tails。



![](img/37752e25380dacd3a400858e09ee6586_232.png)

Right。There's another way we can do it by using this IID space okay。

 this function again will allow me to set unequally likely outcomes， so in this case I set it equal。



![](img/37752e25380dacd3a400858e09ee6586_234.png)

Just to show you， here， so look at how powerful this is， it gives me the experiment。



![](img/37752e25380dacd3a400858e09ee6586_236.png)

And then it gives me the outcome。Right。However， if I had an experiment and I was going to toss a coin three times and the outcomes were not like they're not equally likely。



![](img/37752e25380dacd3a400858e09ee6586_238.png)

![](img/37752e25380dacd3a400858e09ee6586_239.png)

Watch what happens。Notice that the probability of a head head heads is much higher than the probability of a tail tells's tales because now it's taken into account。



![](img/37752e25380dacd3a400858e09ee6586_241.png)

![](img/37752e25380dacd3a400858e09ee6586_242.png)

，Unequal outcomes of heads and tails。

![](img/37752e25380dacd3a400858e09ee6586_244.png)

![](img/37752e25380dacd3a400858e09ee6586_245.png)

Okay。Let's look at an example， right， let's look at an example。



![](img/37752e25380dacd3a400858e09ee6586_247.png)

So suppose we had two dice that were rolled， What is the probability that the sum of the upturned faces will equal seven？



![](img/37752e25380dacd3a400858e09ee6586_249.png)

Okay。

![](img/37752e25380dacd3a400858e09ee6586_251.png)

The sum of the upturned faces will equal7。

![](img/37752e25380dacd3a400858e09ee6586_253.png)

Okay， so let's go ahead and we're going to clear our space。



![](img/37752e25380dacd3a400858e09ee6586_255.png)

嗯。

![](img/37752e25380dacd3a400858e09ee6586_257.png)

Go ahead and put that back。

![](img/37752e25380dacd3a400858e09ee6586_259.png)

Okay， so the first thing I'm want to do。Is I want to set up the probability space。

 and I'm just going to go ahead and use the make space equals true here。



![](img/37752e25380dacd3a400858e09ee6586_261.png)

![](img/37752e25380dacd3a400858e09ee6586_262.png)

So， here。We rolled two dice。

![](img/37752e25380dacd3a400858e09ee6586_264.png)

We expect that our outcome would have 36。Possibilities。 and here in this case。

 the probability is equally likely outcomes。 and so the probability is calculated as 0。0277778。



![](img/37752e25380dacd3a400858e09ee6586_266.png)

![](img/37752e25380dacd3a400858e09ee6586_267.png)

![](img/37752e25380dacd3a400858e09ee6586_268.png)

![](img/37752e25380dacd3a400858e09ee6586_269.png)

So。Now， what I want to do is I want the subset of this sample space。



![](img/37752e25380dacd3a400858e09ee6586_271.png)

Where and and it labels it for me where x1 plus x2 is equal to7， I want that subspace。

 and so I'm going to define that subset as example one。



![](img/37752e25380dacd3a400858e09ee6586_273.png)

![](img/37752e25380dacd3a400858e09ee6586_274.png)

Here it is， notice it pulled out all the occurrences where6 plus， well x1 plus x2 is equal to 7。



![](img/37752e25380dacd3a400858e09ee6586_276.png)

What I want to do now is I want to sum all of these probabilities。



![](img/37752e25380dacd3a400858e09ee6586_278.png)

Okay。And when I sum all these probabilities， that gives me。



![](img/37752e25380dacd3a400858e09ee6586_280.png)

![](img/37752e25380dacd3a400858e09ee6586_281.png)

the probability that this will occur， then there's another way that I could do this。

I could also take the number of rows。That are in my subset。

 and I can divide it by the total number of rows that are in the sample space。 So in this case。

 we know the sample space has 36 outcomes。

![](img/37752e25380dacd3a400858e09ee6586_283.png)

How many outcomes did my subset have， well you can go down here， you can count one， two， three， four。

 five，6， and so if I do that， I get the identical answer。



![](img/37752e25380dacd3a400858e09ee6586_285.png)

So you can get the answer both ways， you can get it by setting the number of times the event occurs over the total sample space。

 or if you know the probability of the event， you could sum all of the probabilities together。

Let's look at another example。

![](img/37752e25380dacd3a400858e09ee6586_287.png)

Suppose。

![](img/37752e25380dacd3a400858e09ee6586_289.png)

E， you know， I had eight dice where were rolled， right？



![](img/37752e25380dacd3a400858e09ee6586_291.png)

And I want to know the probability that the sum of the upturn faces equal 26。



![](img/37752e25380dacd3a400858e09ee6586_293.png)

How would you go about now and do that， Now， this is not something， this is where it， you know。

 this is a powerful technique because this is not something that you would want to do by hand， right。



![](img/37752e25380dacd3a400858e09ee6586_295.png)

嗯。Let's just look at the number。Of rows we're talking about the number of different outcomes。



![](img/37752e25380dacd3a400858e09ee6586_297.png)

Rolling six dice。

![](img/37752e25380dacd3a400858e09ee6586_299.png)

![](img/37752e25380dacd3a400858e09ee6586_300.png)

This is the number of different outcomes， 1。6 million different outcomes。



![](img/37752e25380dacd3a400858e09ee6586_302.png)

There is no way you're going to write that out。喂。Just no way。

There are nine variables because remember。

![](img/37752e25380dacd3a400858e09ee6586_304.png)

We're looking at。

![](img/37752e25380dacd3a400858e09ee6586_306.png)

1 through 8。And then the probability。So if I'm wanted to look at one of those。I could do hair。



![](img/37752e25380dacd3a400858e09ee6586_308.png)

S。And let's see what happens。So。

![](img/37752e25380dacd3a400858e09ee6586_310.png)

Here is。The probability of rolling all ones。

![](img/37752e25380dacd3a400858e09ee6586_312.png)

Is equally likely to the probability of rolling a two first and then the rest of them being ones。



![](img/37752e25380dacd3a400858e09ee6586_314.png)

Right。They're all equally likely。

![](img/37752e25380dacd3a400858e09ee6586_316.png)

And look at the minus， look at the probability there。



![](img/37752e25380dacd3a400858e09ee6586_318.png)

Okay， that's 5。953 with e to the negative 7， so you're going to move this decimal place over seven times。



![](img/37752e25380dacd3a400858e09ee6586_320.png)

![](img/37752e25380dacd3a400858e09ee6586_321.png)

Pretty amazing。Okay， so let's finish with our experiment。

 I want to now extract the number of rows that meet this requirement， this criteria。



![](img/37752e25380dacd3a400858e09ee6586_323.png)

![](img/37752e25380dacd3a400858e09ee6586_324.png)

Okay， and doing that。Well， there are。

![](img/37752e25380dacd3a400858e09ee6586_326.png)

125，588 rows that meet this criteria。

![](img/37752e25380dacd3a400858e09ee6586_328.png)

Pretty interesting now。It's pretty easy。 I know what to do。

 I'm going to take the number of rows of the event over the total sample space。

 number of rows in the sample space。 and I get。

![](img/37752e25380dacd3a400858e09ee6586_330.png)

![](img/37752e25380dacd3a400858e09ee6586_331.png)

![](img/37752e25380dacd3a400858e09ee6586_332.png)

0。07。

![](img/37752e25380dacd3a400858e09ee6586_334.png)

Well， there is another function that we can use in this regard。

 and it is the prob function where it will calculate the probability for me。



![](img/37752e25380dacd3a400858e09ee6586_336.png)

And all I need to do is give it the sample space。In the first argument。



![](img/37752e25380dacd3a400858e09ee6586_338.png)

And the outcome that I'm looking for in a second， and when I do that。



![](img/37752e25380dacd3a400858e09ee6586_340.png)

I get the same thing。So these are a couple examples from module2 I hope that going over this tutorial was helpful。

 I have included also some further examples that you're going to use that you can try I encourage you to definitely try these and it is in these further examples that you'll be using some of the functions that we have defined over here。

 I believe we'll see these and this module and you'll see them in further modules as well I hope this has been helpful for you and I hope you found it easy to follow along until next time in our next tutorial this is Dr。

 Johnson and I'm signing off。

![](img/37752e25380dacd3a400858e09ee6586_342.png)

![](img/37752e25380dacd3a400858e09ee6586_343.png)

![](img/37752e25380dacd3a400858e09ee6586_344.png)

![](img/37752e25380dacd3a400858e09ee6586_345.png)

![](img/37752e25380dacd3a400858e09ee6586_346.png)

![](img/37752e25380dacd3a400858e09ee6586_347.png)

![](img/37752e25380dacd3a400858e09ee6586_348.png)

![](img/37752e25380dacd3a400858e09ee6586_349.png)