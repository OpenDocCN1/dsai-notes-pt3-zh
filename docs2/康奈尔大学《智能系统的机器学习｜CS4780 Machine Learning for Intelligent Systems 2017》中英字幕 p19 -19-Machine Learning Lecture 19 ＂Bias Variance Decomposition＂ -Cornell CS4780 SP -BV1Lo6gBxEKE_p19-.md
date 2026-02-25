# 康奈尔大学《智能系统的机器学习｜CS4780 Machine Learning for Intelligent Systems 2017》中英字幕 p19 -19-Machine Learning Lecture 19 ＂Bias Variance Decomposition＂ -Cornell CS4780 SP -BV1Lo6gBxEKE_p19-

We will start today with a very short announcement by Darren from Amazon Robbootics， is that correct？

嗯。I just know how to make someone feel welcome very briefly， name Dar。5月20。As we graduated here。

CS and OR， and we're here doing the tech talk this evening。you killed on the board。おちばです。这のび当。你把自己。

Let' talkk a little bit about some of the real world challenges weve face when we design software for robotic systems and we're looking for co- ops。

 so if you're interested in coming to talk to us， find out more about what can do or interested in working with us。

 please join us and there will be。Awesome， thank you， thank you。Okay。Alright。

 I hope you all survived the exam。Looks like actually， flood empty seats。嗯。Today。

 we will talking about the most important topic in machine learning。哎。So。

There are two reasons you should really， really pay attention today。W， because it is super。

 super important。 It will transform the way you think about data science。

 So if you understand today's topic， it' the bias variance trade off。

 is what I usually have as part of the midterms， last lecture midterm， because the snow day， I。

 we didn't get around to it。😊。

![](img/52d3786eed892b9993562d8439ee1991_1.png)

![](img/52d3786eed892b9993562d8439ee1991_2.png)

The bias variance trade off is what distinguishes like children from adults， right。

It's the difference between people just play around with algorithms or people really know what they are doing。

 So please， please， please， please pay attention today。

 It will the next couple weeks will all be from viewed from the lens of the bias variance trade up。

 If I succeed it will shape the way you think about machine learning and data science。😊。



![](img/52d3786eed892b9993562d8439ee1991_4.png)

![](img/52d3786eed892b9993562d8439ee1991_5.png)

The other reason why practical reason why you should pay attention is because we are rolling out the next project in a couple of days。

 and we will only give you one week。

![](img/52d3786eed892b9993562d8439ee1991_7.png)

![](img/52d3786eed892b9993562d8439ee1991_8.png)

Because we don't want you to do it over spring break。



![](img/52d3786eed892b9993562d8439ee1991_10.png)

I don't want to ruin your spring break。The project is all about today's lecture。

 So if you pay attention today， it's a really easy project。 If you know what you have to do。😊。



![](img/52d3786eed892b9993562d8439ee1991_12.png)

Okay。So， bias variance trait off。

![](img/52d3786eed892b9993562d8439ee1991_14.png)

![](img/52d3786eed892b9993562d8439ee1991_15.png)

哎。

![](img/52d3786eed892b9993562d8439ee1991_17.png)

The big picture of the bias variance trade off。Is that what we will look into today is the generalization error。

 So far， But what we've done is we've always minimize the training error and basically hoped。



![](img/52d3786eed892b9993562d8439ee1991_19.png)

That what we do will lead to a low generalization error。Today。

 we will look at the generalization error and decompose it and understand where it comes from。

 And if you understand that， then you're much， much more informed to actually make good decisions about how to get classifiers the generalized well。

😊。

![](img/52d3786eed892b9993562d8439ee1991_21.png)

![](img/52d3786eed892b9993562d8439ee1991_22.png)

![](img/52d3786eed892b9993562d8439ee1991_23.png)

Okay， so the setup is the same as usual。 We have our data points， x1。



![](img/52d3786eed892b9993562d8439ee1991_25.png)

![](img/52d3786eed892b9993562d8439ee1991_26.png)

X， and， Y， N。And so just for because it's easy that it holds it holds generally what we are doing today。

 But it's the derivation is much easier if you do it in a regression setting。

 So what we are saying is why I is element of R。 Okay， so we have a regression function。

 Let's say if you want to predict house pricess or something。😊。



![](img/52d3786eed892b9993562d8439ee1991_28.png)

And。All right， so。The first thing is that。And today is going be a little more theoretical。

 So you have to pay attention， not enough to get lost， but it's well worth it。So。These data points。

 X and Y are drawn from some distribution P。 So we have P of x comma Y。

 And how do we get this data set。You get this by drawing end points you know。

 I I D from this distribution。 right， So that's basically the assumption that's what all of machine learning hinges on。

 right， So that's the， for example， you take n emails or something。

 And your distribution is the distribution of incoming emails， right， so。



![](img/52d3786eed892b9993562d8439ee1991_30.png)

So these are basically， you know， the emails into your inbox something。Okay。

 and we would like give an action。 we'd like to predict why。Now。

One thing is important is that for a given vector x， there may not be a unique y。RightSo。

 for example， X may describe a house， right， And so the features could be what the square footage is。

 how many bedrooms you have。 And I don't know how many stores there or whatever， right。

 so you have 10 features of this house。 Well it could be an identical house， you know， a house。

 sorry， a different house It has identical features right that gets sold for a different price。

 So four certain X。 we always have a distribution over y。 right。

 So that's basically just if you deor this， you can say this is P of y given X， you know， P of X。😊。



![](img/52d3786eed892b9993562d8439ee1991_32.png)

Right， and this year， basically for a certain X。 What's the probability of y。Okay。

 so the first thing we will do today is just to remind you of something that we've done in before saying for a certain X。

 you know， in terms of regression， what do you want to predict in classification。

 we have this base optimal classifier。 What do you want to do in regression？ And so I claim you。

 you know， typically a good thing to do is to predict the expected label。 So saying。

 we call this y bar of x。😊。

![](img/52d3786eed892b9993562d8439ee1991_34.png)

Surviv our species says， oh， sorry。Here we go。So for a certain X， this is given X， right。

 given a certain X， which y should you predict， There's many different choices。

 And what you want to predict is the expected Y， right。

And so it's just the integral of all possible y。 Time the probability of in seeing that Y given an x。

 So let me just explain this one more time。 So given a certain x， which y do you want to predict。

 It's ambiguous， right， You could have a feature vector that describes a house。 And， you know。

 sometimes it may be worth 5$50000， sometimes $70000， Who knows， right？ And so。😊，You know。

 a reasonable thing to say is what you want to predict is， you know， the label that I would expect。

 right， So if I would draw basically infinitely many houses on average。

 I would get the following the following value， which is also another way of saying。

 I just integrate out all possible whys and weigh them by the probability that I see this y given X。

😊，Okay， any questions at this point。Raise your hand if that makes sense。Okay， awesome。

 You're still with me。 A， good。 So we call this the expected label。

 We' just gonna So what I'm gonna do now is I'm gonna set up a few things。 And later on。

 we will put them all together。 right， So you just have to remember what these things are。

 So thats the expected label。😊。

![](img/52d3786eed892b9993562d8439ee1991_36.png)

So that is what we want。 right， given an X， we would like to have the expected label。



![](img/52d3786eed892b9993562d8439ee1991_38.png)

Okay， good。Now we can go on。 So let's say we have this data set D。 What do we typically do。

 We are machine learning people， right， at this point， you know， you're one of us。 So what do we do。

 We have some algorithm， some machine learning algorithm。 And what does the algorithm do。

 we stick in the data， the train set and outcomes some function H。 right。

 We call this the hypothesis。 So we call H D。😊。

![](img/52d3786eed892b9993562d8439ee1991_40.png)

![](img/52d3786eed892b9993562d8439ee1991_41.png)

![](img/52d3786eed892b9993562d8439ee1991_42.png)

![](img/52d3786eed892b9993562d8439ee1991_43.png)

![](img/52d3786eed892b9993562d8439ee1991_44.png)

H Steve， this is the classifier that we're learning。

 This is a function that takes an X and outputs some value Y。😊。



![](img/52d3786eed892b9993562d8439ee1991_46.png)

![](img/52d3786eed892b9993562d8439ee1991_47.png)

And what is this， This is the output of some machine learning algorithm a。



![](img/52d3786eed892b9993562d8439ee1991_49.png)

That takes as input， the training data。Okay， so， for example， this could be a perceptionceptron。

 right， You think in the data set D， an outcome sound classifier。

 which in this case is a linear classifier， is just that that's defined by the choice of a that we are using。

😊，I it could in SVM or something。Any questions？Mmh。Alright。

 so this is what we do in machine learning。 right， We basically come up with these algorithms。 A。

 that's what I do all day。

![](img/52d3786eed892b9993562d8439ee1991_51.png)

Okay， so。Given that we now do this。 So given that we now have a training dataset D that we drew from this distribution P。

 we we have these n data points， we now stick them in our algorithm。 We get R H。 We can now say。

 well， what is the expected error that we get， right， So this is the generalization error。

 This is what we're interested in。 So we can measure the training error on the data set D。

 That's the training error。 But what we really care about is the error that we would get。

 if you see some new data points， right， some new houses， some new emails， etc ce。

 So that's the expected test error。😊。

![](img/52d3786eed892b9993562d8439ee1991_53.png)

![](img/52d3786eed892b9993562d8439ee1991_54.png)

![](img/52d3786eed892b9993562d8439ee1991_55.png)

![](img/52d3786eed892b9993562d8439ee1991_56.png)

![](img/52d3786eed892b9993562d8439ee1991_57.png)

And now here comes an important part。

![](img/52d3786eed892b9993562d8439ee1991_59.png)

Expected test error。

![](img/52d3786eed892b9993562d8439ee1991_61.png)

Given H。

![](img/52d3786eed892b9993562d8439ee1991_63.png)

And this will become。 we understand in a second why why I'm emphasizing this so much， right。

 So given a specific classifiers， you train yourBM now outcomes comes from classifier H。



![](img/52d3786eed892b9993562d8439ee1991_65.png)

![](img/52d3786eed892b9993562d8439ee1991_66.png)

Why does the expected test error given that classifier。



![](img/52d3786eed892b9993562d8439ee1991_68.png)

And that's not very hard to compute。 right， So that's basically just saying， okay， well。

 I'm just looking at any new X， Y that's drawn from the distribution P。 And I measure the error。

 So let's just use the squared loss。 So we say that is basically the expected value。

If you draw x and y from P。😡，offff。Hd of x。Minus y squared。All right， any questions at this point？

Yeah， your question。O。Anybody else。Yeah。Why square us， because for regression。

 that's a very reasonable loss。And it's also the， the proof that I will do in a few minutes is a lot easier when you do the square loss。

Yeah， that was a good question。 Yes， and any other questions。Yeah。

This could in principle be done with any reasonable lot。 Not what I'm saying a principle is true。

 It doesn't pop out as nicely what I'm showing you。 But yeah， we'll get to this in the end。

 You can ask that question again at the beginning， yeah。Okay， any more questions？第。That's。

 that's right。 Yeah， so that the。Yes。

![](img/52d3786eed892b9993562d8439ee1991_70.png)

So this is basically， you know， this is the generalization error given H D。

 That's the important part， right， So for a specific classifier。Right。

 this is the expected test error。Oh yeah we can't compute this。 This， you know。

 we're doing a little theory right now。 right， So this will。

 this will become practical in a few minutes。 right， So that's just， yeah， you can't。

 this would be to estimate this。 you would basically sample infinite many points and then evaluate it that。

 of course， you can't do。 Yeah， you can't do this。😊。



![](img/52d3786eed892b9993562d8439ee1991_72.png)

Okay， but this is what we would like to minimize。And well， how do we compute this， this。

 this is just the definition of expectation。 We just plug that in。 So we just integrate over all X。

 We integrate over all Y。 And let me say。😊，H D of x， minus y。Squared d Y， D X。Thats that's。

 that's the same thing。 It is just， you know。My， my son is doing that right now。

 He's in second grade。All right。And she's not。Allright， so。Any questions？Probilities。Yeah。

 I said he's in second grade。 That's fine。Here we go。 good point。X， command wine。いや。Thank you。

Any more questions？Any corrections。Okay， good。 So this is what we would like to understand better。

 right， This is what we've been looking at right now。😊，But， actually。Let's just take a step back。

 Right， Let's take a step back for a second。We have this data set D。

 and the data set G is drawn from the distribution P。 And now we get our H。

 And now you want to know the test error of H。Right， what we may also be interested in is。

What is actually the test error of this A here。RightSo if you basically just， you know。

 design an algorithm， right， And you actually want to argue about this in principle。

 not for one particular output。H and。So let me put this another way。H is actually a random variable。

 So we have D， like each one of these X and y is a random variable。

And we draw N of them to get the set D。So the set D is also a random variable。

 It's a set of random variables。 So it's itself random variable。And we stick that into some function。

 Let's assume now it's deterministic。 Then we get some age。A is a function of a random variable。

 So it itself is a random variable。Okay。Does that make sense。 Raise your hand if that makes sense。

Okay， awesome。 So there's some distribution， right， If you would do this over and over again。

 take a different train deal set D。John from the same distribution。

 you will get a slightly different function。Sos some distribution over functions。

So what we can do is actually， let us compute the expected test there。

 We can also compute the expected function H that we would get。And that's the following。

 the expected classifier。We call this H bar。It's the following。

 if we just take the expected value of these data sets， D， which are drawn from P to the power of N。

 N times drawing from P。 And let me just call that algorithm， right， So basically that's， you know。

 we call this A of D， right。And that equals。We integrate out all possible training data sets。

 And then we take H D。Probability of the。一定。嗯。Can anyone tell me。

 how would you estimate this function。How would you estimate this value。Any ideas？第。

Sample a whole bunch of points and then make a whole bunch of different。在。Algorithm among them。

And average the outputs。 right， So basically， let's exactly you right， So basically average。

 the H Ds that you get。And so， you know， if you have enough data sets that it becomes exactly this That's the weak law of large numbers。

嗯。Okay， any questions？So this basically says this quantity。 What's H bar。

 H bar is basically if I had infinitely many training sets。On average。That this for every x。

 this is still a function right， for every x that outputs one value。

And that is the average prediction that I get。Right acrossss all classifiers。

 have had infinitely many training sets。Okay， any questions？Yeah， argument is still。Posly based on。

No cons basically。Right。So if you would， if you had classification， Yeah， I think it's luckier。

 right， then you basically would have to kind of take the mode the most common label or something。

 So that's， that's why I said， like it's very nice in regression， right， because it's just average。

 right， You you' have to deal with。You know， how do you， Yeah， That's right。

 How do you combine multiple classifiers。That's right。 Good point。어， yeah。あ。Sorry。Da set， well。

 it it's a random process。 right， So we basically draw n data points。And that gives you A， D， S I D。

Right， so you have some distribution over what this data could look like。Does that make sense。

 That's basically， you know。I mean， the set can also be a random variable。

 There's nothing nothing unusual about it in the same way that a function can be a random variable。

So you can just do this。 You can sample many sets。 right you just sample another and data point you get another set。

And you can compute what's the， you know， which data set would I expect， etctera， I mean， it。

 you know， it's just unusual， but， but it there's nothing。 It's still just a random process。哎。嗯。Okay。

 any more questions。Yeah。Oh， very good point。 Good， good， good。 So， allright， good。

 You guys are too smart。😊，So yeah， yeah。 maybe what she's saying is， you know。

 if I had infinite amount of data， why would I just chop that out into many。

 many little data sets and trade them and average them。

 if I'd not just take one very large data set and fair enough， right？ So in this case。

 we want to argue about something that。In practice， you would just do this， right。

There's one advantage。 Actually， the variance of this will tell you something how uncertain you are。

If you had many different data sets。嗯。In this case， it will help us argue about it。But， yes。

 in practice， you would probably just combine the data set and learn one big classifier。 you know。

 learn one very accurate classifier rather than average many。嗯。Okay， good， good questions， Yeah。后边。

法就是。So this is just， I'm just defining this in some sense。 This will come in handy very later on。

 right， So just I'm just introducing the notion that there can be an basically something like an expected classifier。

 right。第。H bar is not a number。 H bar is a function。And so you're averaging many different functions。

 Each one of these is a function。And you you modify the mile weights。And you sum that up， right， so。

那你这次。I mean， if it's a linear function， But， but， I mean， be careful， right。

 This could be highly non。 This could be decision trees。 this could be something non nonlinear。

It's really， you know， it's really a function。 yeah， last question。Oh， N to the power of N。

 because we saw draw n times。So that's the distribution D， D is drawn from this distribution。

 which is basically just P to the power of N。Which means you draw n data points from P。

 That gives you a set of n points。Yeah， good question。All right。Now。

 I guess you have it all on your sheet。All right。So now comes the next point is that if age is a random variable。

Then what we could actually do is we could kind the expected error。Of our algorithm。哎。

Right no longer conditioning on H。 right Earl on we basis that if we tell our data。

 we train a classifier H。 And we want to know what is the generalization error of this classifier。

 right。That's a little unsatisfing because if you invent a new algorithm， right。

 you don't want to know what's the expected error of one particular output of your algorithm， right。

 You want to know， how well does your algorithm do。Okay， and that's a。 So A' is rid kind of。

SVMs in general， right， That's what what A is。And some procedure to come up with classifiers。

And how do we do this， Well， we say we basically have to integrate out H as well， basically say。

 okay， we go over all our data point X and Y。 We want to know。

 what is the error on this on such a point and expectation。But we are also drawing As at R。

 So saying we also have D drawn from P to the N。And then we say。

 what's the error of H D of x minus y squared。So。One more time。

 Let me just walk you through it one more time。 The expected error of our algorithm A。

It's computer the following way。 So first， I draw a data set D， a training data。

 The first thing you do is you draw a training data set。When you train your algorithm。

 then you get an HD。😡，Then you take the text test test point X and y and compute the error。孩子。

And how large is that error and expectation？ So if you would do that 10 million times。

 So 10 million times you get a new train data set， train a new classifier。

 then draw one more point pair point pair X and Y tested on those。Well， what's your average error。

 That's the generalization era of the algorithm。Any questions。Yeah。Maybe too fast yeah。

It is little trying to get better。 So you can approximate this by splitting。

 and we will later ondo this。That's right。So this is basically the same thing that we had before。

But now we also have this integral over D。 So we integrate out every possible training data set that you could have。

Probability of X， Y。Probability of D。D y D X。디디。Yeah。Okay， good。Any questions？Allright。

 And this is exactly the term that people now decompose。And so this。

 I claim this is what we are really interested in。 right。

 when we make a choice about which algorithm to choose or when we design new algorithms， etcter。

 right， What we would like to know is for a certain data distribution P， How well are we going to do。

😊，没。And you want to pick the algorithm at the lowest such error。Okay， yeah。哇一直。

Not independent with the probability of D。No， x the test point。All right， so these。

 these are n data points drawn from P。 And that's the n plus one data point drawn D F from P。

 So it's totally fine。 They are independent。Alright， good。 Who's ready？ Raise your hand。

Some are very reluctant Okay， so now you turn around。😊，So we have now decompose this era。

 And it's important understand， every single step。Because the next few lectures will all hinge on this lecture。

嗯。Now， it looks a little scary a little intimidating。 Don't worry， it's really， really easy。😰。

Itch is the very， basically we do the same trick。 We have two tricks， and we do them twice， each one。

O。Before we get started， any questions？Alright， so we want to decompose this expression here。

 So that's basically says we integrate out O X， Y or D。 What's H D of x minus y， So if I basically。😊。

No， take a random train data， train my algorithm， get H D。 What's its error and expectation。Now。

 maybe I I I raised this year on the right， I get some real estate。Alright。

 so here's the trick I'm doing。I just take this expression here， and I。Theubtract and add H bar of X。

 Anyone remember what was H bar of X。The expected caifier， right， it's right。 So I just take this。

 I say， okay， well， that's the same thing。And over X， Y， and D。We I take H D of x。Minus h bar of x。

Plus， H bar of x。Mus y。And then I grabbed the whole thing。Okay， does that， people believe me。

so I'm just adding something and abstracting it right away。 Like， clearly。

 I'm not doing anything here。But now I can do something beautiful。 I can just。😊。

Put parentheses around here。And around here。I that' still， I'm still not doing anything。O。😊。

Any questions。20。So。The trick is now I can actually you know。

 Comp out the square and look at the individual terms。

So what we want to do is we want to analyze and get to the bottom of where does this error come from。

 right。Why do we have such a， A high error？ And so if I now complete the square。

Then first with the first term。So this is the following。E of。Over。H of x。嗯。One second。

That's actually a mistake here。 It shouldnn't be H bar。I I just have， there's just a plus B squared。

 It's a squared plus B squared plus 2 A B， right， This is my A。This is might be。Okay， this is。

 you know。You're still in middle school yet。So this is a squared plus B squared。Yes。Plus， A B，2 A B。

不。H D of x minus h bar of x times h bar of x minus y。Okay， this is a。Squared， this is B squared。

It is2 A B。Any questions？第二。Probably， yes， yes， it should be。 It Good point。 Thank you。Yes。

 animal more questions。Okay， so far so good。Now。Okay， this term is cool。 This term is cool。

 Let' term here。😊，I claim is 0。And so maybe I give you and your neighbor two minutes。

To convince each other that this term here on the right actually is 0。

You can look at the derivation on the nodes， right below it。嗯。Okay。好的。

So I understand why we can get rid of the middle term。

 but why can't we make the same argument to get rid of this term。

Because essentially what we're saying is that the thing minus physical should not be a Yeah yeah。

 I understand that， but if you。The argument basically here is that if you take the thing minus its mean and take the expected value of that at zero。

 right， but that's what we're doing here anyways， and X and D are independent。And。

I was going to finish out tonight and sorry let's take。I know。didn see。诶。Like。

 we could split the expectation value of x comedy and then expectation of x， that expectation of D。

And then make the same argument， correct。AndNo， no， no， because it's in a square。 It's a squared。

Okay， raise your hand if you understand why it's zero。Okay， a lot of you。 good， good， good。 Alright。

 So basically， what we are saying is we just take the expected value over x and y of this term and。

 and D。 So I we've got D here。😊，X， Y are not independent， right， That's the data appointment label。

 Of course， you know， they're independent。 Thatll be bad。But D and X and Y， like the X， Y。

 pair and D， they are independent of each other。 So what we can do is we can write this as basically first collect say E of X。

 Y。And then we have E of D。And then in here， you basically。Now， if you just。

You get H of x minus h bar of x。Times this， the second part of the product。H bar of x minus y。

And so the point is that this here is 0。 Why is this 0， Because expected value is linear， right？

 So this here is actually， you know， this is， expected value over D。 This is not。

 this D doesn't appear here anywhere。 This is just a constant， right， So we can write this as E of D。

H D of x。Minus h bar of x。 All， That's the same thing。

 You can just pull this out of the expected value。 What is this， Well， that's exactly h bar of x。

 right， So we get x bar of x minus h bar of x equals 0。 If you multiply this with this term。

 Everything disappears。😊，Okay， any questions about this。We will use the same trick in a。

A few minutes， second time。So that was the， the first trick was to just add this term and subtract it。

 The second trick is to discover that this here， the this cross term must be 0。Okay。

 who's ready to move on？I bere almost there， guys。 You're almost there。 It's so close。 Okay。

 so this year is 0， big fat0， awesome。😊，So now we are left with these two terms。

So we just showed that the error of an algorithm A。Consistists of two terms。Out of sum of two terms。

 the first one is the expected value of H D minus h bar of x。

And the second one is h bar of x minus y。😡，那。That's why squared。 So both of these squared。 Okay。

 so let's move on。Okay， good。So if you look at the first term。

You will already see something wonderful shining through here。😊，嗯。No matter， what is this。

 is H H of x minus h bar of x squared。哎。So it's basically what is H bar x is the main function value。

And H of x is the one of your predicted random variable that is the classifier you just drew。

 And if you square the difference for the random variable， its mean， what you get is the variance。😊。

Right， so this is the variance。Of basically， your prediction。Alright， so this is nice。

 We can interpret this very well。m going get to this in more detail in a minute。😊，嗯。O。

 we still have the second term。 And the second term is h bar of x minus y。

 So let's just look at only this term right now。And decompose that one。Expected by an H。

P of x minus y。Squared。And we have this over X and y。And now we do the same trick again。

 we just do the same thing， right。We add and subtract the mean。Earlier， we sub。

 we had H years we subtracted H bar and added and subtracted H bar。 Now we have Y here。

 So what do we do， We add and subtract Y bar。 So it's exactly the same step。

 same argument you're making。 we say this is H of x。Minus y bar of x。Plus。H of x， sorry，One second。

Thats y bar of x。Y bar of x minus y。And the whole thing square。Okay， guys。Any questions？

Who is still with me？Good good。 You're holding in there。 good stuff。 You're almost there。

They basically saying the second term is interesting， right。

 It's basically the average prediction minus the label， right。So。We can decompose this further。

 That's that' it's interesting in itself。 But let's decompose this further。 So what we do is we。

 you know， add and subtract this average label of an X。

 That's the expected label of an of a for certain x。😊，And let's just be precise over X， Y。

 and there's no more D。 Is that correct。 Yeah， there's no more D。Okay， and if you write this out。

 we get the following。One more time， we get the first thing squared with it， which is。H bar of x。

H bar of x。Minus y bar of x。Squared。Again， this is。诶。Plus， B squared。 So this is a squared。

Now we need b squared。Which is。Y bar of x minus y。Yes。Square。Plus，2， A B。And I claim this is， again。

0。This is 0。哎。Why is this。Let me just draw it here one more time。

It's exactly the same argument as before。 If you take the。

 the expected value of the product of these two， what do we get here， We get H bar of x， sorry。

 Y bar of x and y。We take the expected value of this。The expected value of y is y bar， right。

 So we actually get these two cancels out。😊，So。Do you want me to go let me go。 Sure。

 So how do it's a little So here's the idea。 best to have E of x come on Y。

 So this time they are no longer independent。 We have to be a little careful。

 So what we do is we say first go over X， and then we go over Y given x。Y give an X， this。

 this is how we can basically decompose into two different expected values。that's the same thing。

And then we look at the product of these two terms。That's y bar of x minus y。

And then the second term is h bar of x。Mus y bar。Don't worry about this term here on the right。

But here， what do we get， expectation， Basically say first。

 there's expected value over x and then of a y given x。 That's the trick。And now given an x， right。

 what's the， what's y， Well Y bar of x。In this case， actually a constant， right。

 This this doesn't involve the take the expected value over why。This term here does not contain Y。

 It's y bar of x。 This is the function of X has nothing to do with y， right。

 Don't be fooled by the fact that there's a y in there， right。So this here is a constant， right。

 So this here is just y bar of x minus the expected value， Y given x。Of y。 and what is this。

 That's exactly the definition of y bar of x。 So we get y bar of x minus y bar of x is 0。

 So this thing once again disappears， right， to some good feeling。😊，Any questions？Alright。

 And now we are actually there。This is 0。And this year was only the second term。

 So let's just go all the way back to the beginning。

Let me say it as this the left term plus the right term between decomppositions of these two。

So let's add the left term here。That was E of。X comm D。HD of X。Minus H bar。20之。就是。All right， and now。

Take a deep breath。Because real we just showed。Is that the expected era of an algorithm decomposes into these three terms。

 And let's look at each one of these。So this one here。 What is it， right？

 I already give it away early on。 So we， you know， basically take this particular H D that we drew from the training data set。

And。Compte the difference。 like different。 This is not actually about getting right or wrong。

 This is just how different is the prediction of a given classifier H from the expected classifier。

 right， So this is the variance of the classifier。Does this makes sense。

 This's not about getting it right wrong。 This's just how much do my， if I draw。

 if I take two different training assets and train two different classifiers， how much do they vary。

 right， What's the variance across these predictions。 That's exactly what this is， right。

 This is the prediction of the average classifier。 This is prediction of this particular classifier。

 And I subtract these two and squared。 That's exactly the definition of， of the variance。😊。

Raise the hand that makes sense。Okay， good。What is this thing here， This here is y bar minus y。

 right， What is that。Well， you have a data point。And has a label Y。But the expected label is y bar。O。

So if that's very different， that means your problem really， really hard right。

 because your data does not have the labels that you expect it to have。

 You can't do better than Y R of x。 That's the expected label。 right。

 That's the the label basically that this this feature vector should have， right。

So this here's the noise。Does that make sense。So if you have really noisy data， right。

 that means that the same feature vector， the same description of a house， right。

 could sometimes be worth， you know，100000 sometimes be worth a million。 right， have a lot of。

 That's exactly what this captures， right， for a certain X。 What is the average label that we get。

 What's the expected label we get。 And what is it real， right， if I draw one。Right， so that's the。

 the north。And what is this thing。This is called the bias squared。And what is the bias squared？

The biaspared basically says， if I had。You know， infinitely， many train their right。

 and get the expected classifier。Right。And noise doesn't matter， right。I'm。

 I'm not trying to predict the y for x。 I predict the expected label， right。

 So noise is no longer an issue。How much error would I still get。嗯。And what does that capture。

 That basically captures。How much my classifier is biased towards some other explanation that is not really in the data。

 So， for example， the data could be non nonlinear， right， That's not a linear decision boundary。

 that to say we have regression here。 So it's just not linear。 but I'm fitting a line to it。Right。

 and no matter how much data I have， right， no matter how many classifiers I'm averaging。

 I will always make some mistake。 And that's just because my classifier is biased towards a very specific solution。

 right， and more data will not convince it otherwise。😊，That's the bias of the model。Any questions？

不好意思，马也。なおいす。Now they're all squared， right， theyre only bias actually bias。 Oh， I see。 Well。

 it's because this is actually the noise of that lot， right， This is the variance。 Yeah。

 I guess it's just what we call it。😊，嗯。对。So actually， let me just give you a better explanation。

 because the bias could also be， you could be above or below。 But if you square it， that goes away。对。

No， I mean， you know， basically the， the ultimate error that you're getting。

 right is basically the sum of these three errors。对。Thisこ。No。

 what oh this is more about your understanding。Like you shouldn't actually plug in data in here。

 right。There is for you to understand that the error is actually， you know。

 is the sum of three very precise things。 It's the bias。

 the variance and the noise of your algorithm。's the bias and variances of your algorithm and the noise of the data。

Right， in those three parts。You know， that's all there is to it to the era。

And so what we will do in the next couple of lectures is actually。

 I will talk about how to reduce each one of these， right And you as a data science scientist。

 if you have a classifier that doesn't iss not accurate enough。

 It's your job to determine is your bias high， I your noise high is your variance high。

 and then do exactly the right measure to decrease the value that's actually large， right。

 Each of these is quadratic right， So if you reduce the wrong one。

 And this is actually what you see all the time in practice。

 And people have algorithms that don't work。 and they have a bias problem。

 And what do they do instead， the decrease noise or decrease variance， which is not their problem。

 So you have to basically sharpen your mind， sharpen your eyes for what's really going on and you train a classifier。

 Let me give you I just want to do a little exercise before turning around。

 don't not turn around do not turn around the notes。😊，I want to give you a little bit of。An ally。

 and the solution is in the back here。So。So here's what I want to do。 Imagine you're throwing a dart。

At， at main。I want you to think about for two minutes that we still have。

What do these pictures look like if you are basically， if you have high bias， right， So yout， you。

 you're throwing dart at this at this goal。 You're trying to fit it here。Okay。Let me give you one。

 right。here， this is low one second， No variance。High variances。Low bias。H by。Okay。

 so if I have low variance and low bias。Forget noise of it now。 Like。

 the noise will be if this thing is shaking。 So let's say you in the front row throwing darts at this day。

 right。Just think about it。 Don't do it。If you have low variances and low noise。

 what happens is you actually your very little error， right。

 You're going to throw all the darts right here at the center。Now， here's the question。

 If you have high variances， you know， we can decompose this error now in variances and。Right。

 so what happens when you have high variance， What happens when you have high bias。

 What if it happens if you have both。Discus it for one minute with you neighbor。系 si， ok。

We out of town and so let me just show you what I mean。So if you have low variance， no bias。

 you always hit this exactly。Right。If you have low bias in high variance， what does that mean。

 I'm just， you know， So if you have low bias， this means an expectation you're dead on。Right。

 but your difference rows， they vary a lot。Right， so。It looks like this。

But if I would average all my darts， I would be right here in the center， right。

 and some may be here， right， But， you know， so in expectation， my darts are right here。哎。

But I have hivari。 So sometimes I'm a little bit to the right。

 sometimes I'm a little bit to the left and above a little bit no， right。

 But there's no systematic error， right， I I have no bias Im not biased towards any other goal。

 And just I'm shaking a little bit， right， Just need a drink or something。Yeah。So， yes。

Here's the other scenario。 What if you had。So I wear my low bias high bias and low variance。

 high bias low variance means I'm not varying a lot， right。

 I'm always hitting the same point with laser accuracy。 But unfortunately， you know。

 my glasses a little off。 and I constantly hit this point here， right with amazing accuracy， right。

 I I'm not。😊，And， and my variance is very low， but I'm desped towards what a slightly different solution。

O， that's this error here。And the worst of all words is when you have high bias and high variance。

 That means in expectation you're off and you actually bury a lot。 right。

 So you're basically really going for this goal here， right。

 And you don't even hit that one very well，😊，Okay， awesome， we all see each other on Friday。😊。

