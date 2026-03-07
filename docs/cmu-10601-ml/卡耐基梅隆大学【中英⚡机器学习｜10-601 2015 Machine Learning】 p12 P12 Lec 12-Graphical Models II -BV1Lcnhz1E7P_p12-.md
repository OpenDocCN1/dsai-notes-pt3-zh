# 卡耐基梅隆大学【中英⚡机器学习｜10-601 2015 Machine Learning】 p12 P12 Lec 12-Graphical Models II -BV1Lcnhz1E7P_p12-

Sorry for the slight delay， it's funny， but we live， it's not。We live in a very honest campus。

 I panicked about 10 minutes before class because I couldn't find my little magic connector that connects my computer to the projector。

So I brought a whole backup system here with me， we were going to use chalk on the board。

 but when I walked up to the podium there it was from Wednesday。You live in an honest campus。

All right， so we're going to pick up on base nets。I guess one announcement before we get started。

 we are having a midterm next Monday。I think you know that if you've been。

Tracking the schedule for the class。It will be a closed book exam。However。

 you're allowed to bring with you one piece of eight and a half by 11 paper written in as small a font as you care to write in。

On both sides， and yes， you are allowed to bring a magnifying glass。

So my advice is it's a great way to study for an exam to digest the material from the semester and try to boil it down to one page。

 and so I encourage you to do that。TheThe exam will be in class will be 80 minutes。

 so be sure you're here on time。And there's really not much else to say， any questions about that？

Parddon me。How many pages， 400 we don't know yet。There will be。Five， 16 minute questions。

Which adds up to 1880 minutes， and each question will be worth 16 points。

So it'll be easy for you to budget your time。That's part of the design of the exam。

Then Anna it'll cover everything that we've covered through the semester。

With a focus on the things that we think are most important， and if you've been coming to class。

 I'm sure you know which things we think are most important， yes。你是在。Oh yeah。

 it won't just be five true or false questions。嗯对。There will be some structure to each question。

 yeah， with sub partss with sub pointss。Okay。All right， so let's move on with bay nets。嗯。Okay。

 so we looked at this last time and as we discussed。

 the BsNe is simply a notation for representing joint probability distributions over collections of variables in this case here are five random variables。

 these happen to be Boolean valued random variables and so the Baysnet here is a directed acyclic graph。

Among those variables， plus for each variable， a definition of its conditional probability。

 given its immediate parents。In this case， the immediate parents of windsurf are lightning in rain。

 and so you can see for the four possible values that lightning and rain can take on as a pair。

Here are the probabilities of windsurf being true or false。

So for a base net to have a well defined base net。All we have to do is write down the directed acyclic graph and for each random variable describe its conditional probability。

In terms of its immediate parents。 And as we talked about last time， this is a way of。

Specifying a collection of conditional independence assumptions。So I'm going to。嗯。Well。

 so one of the first questions we could ask is how do we do given a base net。

 suppose we're interested。In the probability of some particular。Joint assignment to variables。

Then how can we calculate that given the Bay net？Well， it turns out to be amazingly easy。

 Does anybody remember what factorization of the joint。

Probability distribution on the variables is implied by this graph。Remember， it's just in general。

 this is saying that。Oh no， we're going to get in trouble。Somewhere on this。

Computer is the thing that I touch to turn it into a pen。But， it's invisible。I apologize。

It just appeared。LetSee if that worked。Okay， we've got to a laser pointer。Okay。I need to do it。

Enable editing， thank you。Oh， this is protected， thank you。Yes。There's hope。Okay。

 we're back I apologize Okay， so remember the joint distribution for a collection of random variables。

 we just write down the product for each of the variables of its probability given its parents right so in this case。

 if I just use the first letter of each word to represent，The variable and so forth。

 then the joint probability of this is just， will that be the probability that S equals1。

Because it has no parents times of probability。That L equals zero。Given in what。S equals one。

Times the probability of R equals。Wen。Givenive。S equals one。

Times the probability of what I still need thunder here。Thunder equals zero。Given in。L equals zero。

Times what， what's the remaining one？W equals one given。Right。It's two immediate parents。

So this is really easy to calculate， right， these things turn out to be exactly the entries in our table。

So for example here's the table for windsurf， we can look up the probability that windsurf equals one given this。

 what is it？Po2。Right。It's just。