# 优达学城（Udacity）：无人驾驶汽车纳米学位项目-十位大牛亲授自动驾驶技术，硅谷前沿科技（计算机视觉⧸车道识别⧸感知控制⧸人工智能⧸谷歌） p05 5. Part 02-Module 01-Lesson 03_Probability [BV1Vd4y1r7QG_p5]

ま。Congratulations on submitting Project 0。 When I solved that last part of the project myself。

 it actually took me several tries to get the card to apart。

 And the process was largely trial and error。 That's because I was uncertain of what effect a command like car dot steerer would have on vehicle behavior。

😊，This is similar to something known as control noise in self drivingriv cars。

 and it turns out that uncertainty is an unavoidable part of almost every component in a self- drivingriving car and managing this uncertainty is a huge part of making a self drivingr car that actually works。

Now， this word uncertainty will mean something very specific when we use it in this nanodree to make sure we're talking about the same thing。

 I'd like you to think about how uncertainty shows up in a selfding car。

Your understanding of this word uncertainty will continue to evolve and mature as you learn more about self driving cars。

 The next section is called Learn objectives for probability。

 And these are sort of a snapshot of what your understanding of this word should mean after this lesson。

Because those learning objectives， they're really just a set of questions that you should be able to answer after this lesson。

 and in fact， we're going to show you these questions again later。

We include them at the beginning of this lesson and other lessons in the nameM degree as a concrete way of demonstrating what it is you'll be learning。

But you are not expected to be able to answer them yet， if you can answer all these questions now。

 then you should feel free to skip ahead to the next lesson。In this in the following units。

 we will talk about probability。 Proability is just the opposite of statistics。

 and there is a yin yang relationship between both。 But differently in statistics。

 we are given data and try to infer possible causes which relates to the data。

 whereas in probability， we are given a description of the causes。And we'd like to predict the data。

 The reason why we now study probability and not statistics。

Is because it gives us the language to describe the relationship between data and the underlying causes。

 So enough of the theory， let's dive in。

![](img/5fd8328e637150d01eaa84e0852cb562_1.png)

And you can debate it， but I think the best answer is no， this is what's called a fear coin。

And that means it really has a 50% cent chance of coming up tails。 So let me， let me spin it again。

And not surprisingly， it actually came up tails this time。

So probability is a method of describing the anticipated outcome of these coin flips。

 Let's talk about a fair coin， the probability。

![](img/5fd8328e637150d01eaa84e0852cb562_3.png)

Of the coin coming up heads is written in this P notation。

 This reads probability of the coin coming of heads。And in a fair coin， the chances are 50%。

 that is in half the coin flips， the coin will come up ahead。



![](img/5fd8328e637150d01eaa84e0852cb562_5.png)

In probability we often buy it 0。5， which is half of 1， so a probability of 1 means it always occurs。

 a probability of 0。5 means it occurs half the time and let me just ask you。

 what do you think for this coin is the probability of tails。



![](img/5fd8328e637150d01eaa84e0852cb562_7.png)

![](img/5fd8328e637150d01eaa84e0852cb562_8.png)

A loaded coin is one that comes up with one of the two much more frequently than the other。 So。

 for example， suppose I have a coin。That always comes up heads。

 What probability will I assess for this coin to come up heads？What be the right number over here。

And the number is one。It's the same as 100% One just means it always comes up in heads。

And given that， what number would you now assess the probability of tails to be？And yes。

 the answer is 0。 and we find a little law here that I want to just point out。

 which is the probability of heads plus the probability of tails equals 1。

And the reason why that's the case is the coin either comes of heads or tails。

 There's no other choice。 So no matter what happens， if I look at heads and tail its combined。

The chances of either of those occurring。Is one because we know it's going to happen。

 So we can use this law to compute the probability of tails for other examples。

So suppose the probability of heads is 0。75。 That is three out of four times you're going to get heads。

 What's the probability of tails。And the answer is 0。25， which is 1 minus0。

75 using the law down here。 and as you can verify， 0。75 plus 0。25 equals 1。

So we just learned something important there's a probability for an outcome。

 I'm going to call it a for now， and we learned that the probability of the opposite outcome。

 which we going to call not a。This over here just means not is。1 minus the probability。

As specified over here， that's a very basic law of probability。

 which become handy as we go forward so please remember it。



![](img/5fd8328e637150d01eaa84e0852cb562_10.png)

Hey， you're making great progress learning about probability。

 and you now understand how to design a coin flipping robot possibly。

 But I just want to put in the word why you learn so much about coin flipping when you really care about self driving cars。

😊，Probability is the core of how a self driving car runs。

 And before diving into really complicated stuff like mapping and localization。

 we really want to tell you the very basics because the basics of finding out what a coin flip looks like is exactly the same math as building really great maps and localizing and controlling a self driving car。

 So stay tuned， you're making great progress and let's dive deeper。

 In our example we observed heads twice。 So now when I ask you a really tricky question。

 What's the probability of observing heads and heads， if you flip the same unbiased coin twice。

 which means in each flip， we assume the probability of heads is 0。5。 please answer here。😊。



![](img/5fd8328e637150d01eaa84e0852cb562_12.png)

![](img/5fd8328e637150d01eaa84e0852cb562_13.png)

![](img/5fd8328e637150d01eaa84e0852cb562_14.png)

And that was a tricky question。 And you couldn't really know the answer。

 if've never seen probability before， but the answer is 0。25。

 And I will derive it for you using come something called truth table in a truth table。

 you draw every possible outcome of the experiment that you conducted。

 There were two coin flips flip 1 and flip 2 and each at a possible outcome of head head， head tail。



![](img/5fd8328e637150d01eaa84e0852cb562_16.png)

![](img/5fd8328e637150d01eaa84e0852cb562_17.png)

Tail head。 and tail tail。So if we look at this table。

 you can see every possible outcome of these two coin flips。 There happens to be four of them。

 And I would argue because heads and tails are equally likely。

 Each of these outcomes is equally likely because we know that the probability of all outcomes has to add up to 1。

 We find that each outcome has a chance of a quarter or 0。25。

 Another way to look at this is the probability of head the follow ahead。 is the product。

What are the chances of the first outcome to be heads multiplied by the probability of the second outcomes to be hedge。

 The first is 0。5。Ez。😔，Is the second？And if you multiply these two numbers。It gets 0。25。Or a quarter。

Let me now challenge you and give you a loaded coin。 I I flipped twice。 And for this loaded coin。

 I assume the probability of heads is 0。6。 That really changes all the numbers in the table so far。

 But it can apply the same method of truthth tables to arrive at an answer for what's the probability of seeing heads twice under the assumption。



![](img/5fd8328e637150d01eaa84e0852cb562_19.png)

![](img/5fd8328e637150d01eaa84e0852cb562_20.png)

![](img/5fd8328e637150d01eaa84e0852cb562_21.png)

That the probability of heads equals 0。6。And I want to do this in steps。

 So rather than asking the question directly， let me help you derive it by first asking what's the probabilityability of tails。

And the answer is 0。4， because heads comes with a 0。6 and is 0。6 is 0。4。

And now please fill out the entire tooth table， they have four values over here。

 so please compute them for me。And the answer using our product rule is head head comes at 0。

6 times 0。6， which is 0。36 heads followed by tails is 0。6 times 0。4 which is 0。

24 tail followed by heads is again 0。24 and tails followed by tails is。0。16， which is 0。4 times 0。4。

If we add up these numbers over here。Please go ahead and add them up and tell me what the sum of those numbers is。

And not surprisingly， it's one。 That is the truth table always has a probability that is a to one。

 because it considers all possible cases and all possible cases together have a probability of one。

 So we just check this and make sure it's correct。 Read from this table。

 we will find that the probability of H H。

![](img/5fd8328e637150d01eaa84e0852cb562_23.png)

Is 0。36， and you can do the same over here，0。6 times 0。6。



![](img/5fd8328e637150d01eaa84e0852cb562_25.png)

Is 0。36。 So that's our correct answer。 Let's now go to the extreme。

 And this is a challenging probability question。 Suppose the probability of heads is1。

So my coin always comes up with heads， but the probability of head to come ahead。

And the answer is one to see this， we know that probability of tails is0。

 all the probability goes to heads。1 times 1 is 1，1 times 0 is 0。0 times 1 is 0， and0 times 0 is 0。

 and it's easy to verify that all these things add up to1。Our， head heads。Is just one。



![](img/5fd8328e637150d01eaa84e0852cb562_27.png)

The truthth table gets more interesting when we ask different questions。

 Suppose you flip our coin twice。But we care about that exactly one of the two things is heads。

 and thereby were exactly the other ones tails for a fair coin。

 Would you think the probability would be that if I flip it twice that we see heads exactly once。



![](img/5fd8328e637150d01eaa84e0852cb562_29.png)

And the answer shall be 0。5， and it is a nontra question。 Let's do the truth table。

 So for flip number one， we have the outcomes heads， heads。



![](img/5fd8328e637150d01eaa84e0852cb562_31.png)

![](img/5fd8328e637150d01eaa84e0852cb562_32.png)

Tianto。😔，In for flip 2。Hads tail。 heads some tail。These are all possible outcomes。

And we know for the fair coin， each outcome is equally likely。 That is exactly a quarter。Given that。

 we now have to associate a tooth table with the question we asking。

 So where exactly is in the outcome head represented once， please check the corresponding cases。And。

 yes， it's in the second case。 and the third case， the extreme cases of heads。

 heads and tail tail don't satisfyati this condition。

 So the trick now has been to take the 025 probability of these two cases and add them up。

 which gives us 0。25 plus 0。250。5。Which is the number that's correct for this inquiry。

Let me now make it really， really challenging for you。 I take a fair coin and flip it three times。

 And I want to know the probability that exactly。

![](img/5fd8328e637150d01eaa84e0852cb562_34.png)

One of those three flips。

![](img/5fd8328e637150d01eaa84e0852cb562_36.png)

Comes of hits。And this answer is tricky。 We will derive it through the tooth table。

 Now there's eight possible cases。 Flip 1 can come with heads or tail， samee for flip 2， heads， tail。

 head tail and the same for flip 3。 And if we look at this every possible combinations represented。

 For example， this is heads tail tail。 Now， each of those outcomes has the same probability of an eighth。



![](img/5fd8328e637150d01eaa84e0852cb562_38.png)

![](img/5fd8328e637150d01eaa84e0852cb562_39.png)

![](img/5fd8328e637150d01eaa84e0852cb562_40.png)

Because there's eight cases。 So8 times an eighth sums up to1。

 in how many cases do we have exactly one H， It turns out that is true for only three cases。



![](img/5fd8328e637150d01eaa84e0852cb562_42.png)

![](img/5fd8328e637150d01eaa84e0852cb562_43.png)

The H could be in the first position in the second position。Or in the third position。

So three out of8 cases have a single age。 Each of those carries an ather of probability。

 So if we sum those cases up， they carry a total of 3/8th of a probability， which is the same as 0。

375。

![](img/5fd8328e637150d01eaa84e0852cb562_45.png)

![](img/5fd8328e637150d01eaa84e0852cb562_46.png)

Now， that was a challenging question。 I'm going to make it even more challenging for you now。

 where I give you a loaded coin with a probability of 8 to 0。6。

 And I expect this will take your while on a piece of paper to really calculate this probability over here。



![](img/5fd8328e637150d01eaa84e0852cb562_48.png)

But you can do exactly the same thing you go through the tooth table。

You apply the multiplication I showed before to calculate the probability of each outcome。

 Theyre not the same anymore。 H， H， H is clearly more likely than T T T。 And when you've done this。

 add the corresponding fear up。

![](img/5fd8328e637150d01eaa84e0852cb562_50.png)

![](img/5fd8328e637150d01eaa84e0852cb562_51.png)

And tell me what the answer is。And my answer is 0。288。 How do I get there。

 let's look at the three critical cases， H T T。

![](img/5fd8328e637150d01eaa84e0852cb562_53.png)

Is 0。6 for H times 0。4 for tails times another 0。4 for tails again。 And they gives me 0。096。 Now。

 it turns out this case over here has the same probability。 because all we do is we order it0。

4 times。0。6。Times 0。4。 and we know that in multiplication， the order doesn't matter。

So you get the same zero point。0，9，6。And by the same logic， the fern also gets me。0。096。

So adding these 0。096es together to get them。Gives me 0。288。

So I didn't have to fill out the entire tooth table， which you might have done in the derivation。

 I I only have to fill out the cases I care about yet they give me the correct result。



![](img/5fd8328e637150d01eaa84e0852cb562_55.png)

So there's to one final exercise。 And now I am throwinging dies。

 And the difference between dice and coins is that there is no six possible outcomes。

 Let me us throw them and say it's a fair dye， which means each of the different sides comes up with a probability。



![](img/5fd8328e637150d01eaa84e0852cb562_57.png)

![](img/5fd8328e637150d01eaa84e0852cb562_58.png)

Of the sixth for any of the numbers they can plug in over here。 What do you think the probability is。



![](img/5fd8328e637150d01eaa84e0852cb562_60.png)

![](img/5fd8328e637150d01eaa84e0852cb562_61.png)

The die comes up with an even number。I'm going to write this this the outcome of the die is。



![](img/5fd8328e637150d01eaa84e0852cb562_63.png)

Even， and you can once again use a truth table to calculate that number。In truthth tables speak。

 there's six outcomes，1 to 6。 Each has the same probability。Over6， half of those numbers are even2。

4 and 6。 So if we add those up， we get three times a6。 the same as a half。 the outcome as 0。5。

Now I'm finally going to make as my final quiz， a really challenging quiz for you。



![](img/5fd8328e637150d01eaa84e0852cb562_65.png)

Suppose we throw a fair die twice。 But we think the probability of a double is。

 But double means both outcomes are identical as the same number。 regardless of what that number is。

 That's actually an important number， because many games involving two dies have different rules when these come up with the same number。

 So it might be important to know what the probability is。



![](img/5fd8328e637150d01eaa84e0852cb562_67.png)

![](img/5fd8328e637150d01eaa84e0852cb562_68.png)

![](img/5fd8328e637150d01eaa84e0852cb562_69.png)

And once again， we can answer this using a tooth table。 Now。

 the tooth table will have 36 different entries，6 for the first throw times 6 for the second row。



![](img/5fd8328e637150d01eaa84e0852cb562_71.png)

And enough space on this tablet to draw all the 36 entries。

So let me just draw the ones that really matter，1，1。



![](img/5fd8328e637150d01eaa84e0852cb562_73.png)

tutu。And so on all the way to a 6，6。 So each one of those has a probability of a 6 for the first outcome times a6 for the second。

 which gives me 1，36。The same logic applies everywhere。 So for all these six outcomes。

 I have a 30 sticks of a chance。This outcome will materialize。 Adding them all up gives me a sixth。

 why。Because I get6 times 36。And I can simplify this back to a6。 That's just the same as 0。166。



![](img/5fd8328e637150d01eaa84e0852cb562_75.png)

6，7。 Also。 So one in six times。 you will get a double。 Now， when you play a game like begemon。

 which is played with two diece， it might not feed like this。

 I can swear I don't get a double of one in six moves。 but is's actually true。 That's right。

 That's the correct probability。 So let me summarize。 you've actually learned quite a bit。

 You learned about probability of an event， just as the outcome of a coin flip。

 You learned that the probability of the opposite event is one minus The probability of the event。

 And you learned about the probability of a composite event， which was the form P times P times。



![](img/5fd8328e637150d01eaa84e0852cb562_77.png)

![](img/5fd8328e637150d01eaa84e0852cb562_78.png)

![](img/5fd8328e637150d01eaa84e0852cb562_79.png)

![](img/5fd8328e637150d01eaa84e0852cb562_80.png)

![](img/5fd8328e637150d01eaa84e0852cb562_81.png)

P， now， technically speaking， this thing over here is called independence， which means nothing else。

But that the outcome of the second coin flip。Didn't really depend on the outcome of the first coin flip in our next unit。

We will talk about dependence。Where there's bizarre dependencies between different outcomes。

 But for the time being， you really managed to get a very basic understanding of probability。

 So let's take the next unit and let's jointly dive much deeper into the rabbit hole of probability。



![](img/5fd8328e637150d01eaa84e0852cb562_83.png)