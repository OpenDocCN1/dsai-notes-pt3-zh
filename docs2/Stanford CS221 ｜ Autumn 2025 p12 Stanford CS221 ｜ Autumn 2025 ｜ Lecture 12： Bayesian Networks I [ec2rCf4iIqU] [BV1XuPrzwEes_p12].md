# Stanford CS221 ｜ Autumn 2025 p12 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 12： Bayesian Networks I [ec2rCf4iIqU] [BV1XuPrzwEes_p12]

![](img/4f9c544e3dee2e3d52ef198ea9cf7548_0.png)

![](img/4f9c544e3dee2e3d52ef198ea9cf7548_1.png)

So welcome back everyone， so today we're going to switch gears a bit and talk about Beijingian networks。

And to motivate this shift， let's just review what we've done in this class so far。

So when we started， we talked about the ingredients for intelligence。

So agent has to perceive the world， it has to reason with knowledge， it has to act and has to learn。

So where we started was just with machine learning， where we take perceptps and return actions。

So we trained these predictors， they could be linear or they could be deep neural networks。

 but the basic idea was that you just take your whatever you sense an environment and then you just produce a prediction or an action。

And then over the last weeks or so。We looked at state based models for reasoning。

And the idea is that agents in order to be intelligent。

 can't just reactactiveively predict based on the environment， has to do some thinking or planning。

And so along these lines， we looked at search problems。

These are models where the actions have deter the consequences so the agent can think about finding the minimum cost path。

 then we looked at Markov decision processes where the eight actions have stochastic outcomes。

 but the distribution over those outcomes is known， and then you can do things like value iteration。

And then we also looked at games where we know how the world works。

 except where there's an adversary who's trying to out to get us or more generally an unknown opponent strategy and we want to be conservative。

 and then we had to do things like minimax。Okay， so in each of these cases。

We looked at both model free and model based approaches。 So model free approaches。

Essentially says we just need to know just enough to。

To know what actions to take and how much utility it will produce。Okay。

 so examples include classification regression， SARSA Q learning， TD learning。

 these are all approaches to try to directly get at the actions given the state or the environment。

We briefly looked at model based methods as well， and the idea of model based methods is that we're not content just to be able to predict the right action。

 we actually have to understand how the world works。

So when we did search or we did evaluation or minimax。

 these are model based in the sense that we have a model of the world。

 we understand if we take this action， we know what will happen， and then that allows the plan。

 so we take this action， this will happen， and we take that action。

 this will happen and so on and so forth。So in some sense， it's a more powerful way of doing things。

 but it is harder because just being able to know what action to take seems like a simpler problem than understanding how the world works。

So model free methods are direct and cheaper， which is why I think a lot of practical applications people just go to them because they're faster。

But model based methods are more flexible， for example。If you had a model of how the world works。

You can change the reward function on the fly and then you have the transitions the same。

 and then you compute the optimal policy， whereas if you had a Q value。

 that sort of compiles down all the information about the rewards and transitions so you can really the Q value doesn't know am I taking this action because it's more likely to I'm going to get something good or is it because the expected outcome is more。

So if you have model based， it gives you more power。So then there's a question of okay。

 so if we buy into this idea of modeling the world， how should we represent the state of the world？

Seems like a very daunting thing。So that's going to be the topic of Bayesian networks。

 So Bayesian networks is going to be about how you represent the world and how you reason about the world。

In face of uncertainty。Okay， so it's going to be a pretty different shift in the way we think about problems and hopefully itll become clear as we go along。

So to introduce Bayesian networks， we need to first introduce the rules of probability。

 now all of you should have taken probability， so this hopefully should be a review。

 but I will do it in a slightly maybe unorthodox way， which will make it more interesting。Okay。

 so we want to represent the state of the world。Byu a set of variables。And these variables。

 also called random variables， are going to represent attributes of the world。

So as a very simple example， you might have two variables。S。

 which represents whether the sun is shining or not， so one means it is and0 means it's not。And。

Another variable R， which is whether it's rainy or not。Okay。So。So given these two variables。

 we can now characterize what state the world could be in。

And these are called assignments to random variables。 So if you have S equals 0 R equals 0。

 that means it's not sunny and it's not raining。S equals 0 or equals 1， it's not sunny。

 but it is raining， S equals 1 or equals 0， it's sunny。

 but it's not raining and here it's both sunny and rainy。Okay， so these are given two variables。

 you just look at all the possible values that they could take on。

 and those are your possible assignments。So， so next step is that we want to。Make each assignment。

 associate each assignment with a probability。So we think about a joint distribution over a set of random variables as providing a probability for each assignment。

 so maybe the probability of it S equals 0 r equals 0， so no sun， no rain is 0。2。And this might be 0。

08。0。7 and the probability of it sunny being sunny and rainy is 0。2 and 0。02。

 which makes sense because it usually isn't sunny and rainy at the same time。

And because we're in California， the probability of sunny and not rainius is pretty high。

 and I guess if it's not sunny and it's not rainy， it's probably， I know， nighttime or something。

Okay， so what I'm going to do now is I'm going to。You'll represent this in code。

 so I have this class called Prob table， and it basically is a wrapper around a nuI array。

So in this nu prior array is a matrix。And you can think about the first。

In an element of the first axis of the matrix， meaning the rows are the values of S0 and the。

The columns are。So， the values of s and the columns are the values of R。Okay， so just to be very。

 very clear about this。 So you have S。And you have R， you have0，1，01 and。

I think what were the values here？Poin to。2。08。08。70。0。Great。0。7。7 to 1。02 Okay。

 so this is this matrix or tensor， as we'll see later， that represents the joint probabilities。Okay。

 now in this blue， what I've done is I've sort of rolled out this into a matrix because once we have four variables。

 it's going to be really hard to draw four dimensional tensors。

 so basically this is equivalent representation where for every variable assignment I have a probability。

Okay so the probability of sun and rain is 0。02。Alright。

 so this is a joint distribution over all the。The variables。So every assignment gets a number。

 which is a probability。And now， okay， so the first operation is called marginalization。

Marginalization， intuitively。Just collapses it sort of ignores a variable And what I mean by ignoring the variable is that it's going to collapse all assignments that only differ in R。

 So if you have probability of S equals0 that's S equals0 R equals 0 plus S equals0 R equals 1 we don't care what value of r takes because r is being marginalized out So we sort of collapse these two assignments into one and add the probabilities。

 So if that gives us 0。28 and then the probability of s equals1 is you collapse these two assignments which differ in R but don't differ in S。

Okay， so pictorially， this corresponds to combining these first two rows that's probability of s equals0。

 and the second two rows， which is the probability of S equals 1。

And if you marginalize multiple variables， then you're collapsing potentially many more rows。As well。

Okay， so the output of marginalization is。A table that has。Is is smaller。And here comes a cool part。

 So you thought you were done with Iops， but it's coming back now。

 So probability tables are just tensors， right， So this thing on the board is a matrix。

 but is also a tensor。😊，And therefore we can actually use IOops to express computation。

 and it turns out all the laws of probability are essentially all covered by IOs。

Hopefully this will give you a deeper appreciation of Einops。

So just to write out formally what the marginal probability is。

So this says that the probability of S equals S is the summation over R。

 the variable you're marginalizing out of the joint。OkaySo this is for all values of S。

And your summy over all values of R。So if you remember ionops this， if you see something like this。

 then you should be able to just have a one minorr that represents that computation。

And what I'm doing here is， so PSR is this table， the joint distribution。

I have a dot P because it's just that。The PSR is this probability table and the P gives you the underlying tensor。

 and that's what Einstein takes。 So it's a bit of a just notational nuisance， but。

Don't worry about it too much。Okay， and then remember the the description。

Says I label the axes of this tensor。And so the first axis is S， second one is R。

And then the output Tensor has the label S here。 So the way to interpret this is that for all values of S。

I look at this and I sum over R， or in general， the variables that don't show up on the right hand side。

I know IOs is a bit confusing at the first， so maybe I'll just pause and make sure that people understand IOs or marginal probabilities。

All right， so the other major operation in probability is conditioning。So intuitively。

 the way to think about conditioning is that when you condition on a partial assignment like R equals1。

 it's raining means that you're only selecting the assignments that satisfy that condition。Okay， so。

The way we're going to do this is we're going to say， well， look， these are the possible assignments。

R equals1 means I'm only going to pay attention to the rows where r equals 1。

So there's two rows that where r equals 1， S where s is 0 and r is 1 and S equals1 and R is 1。

 the other two rows just don't matter。So in general。

 I'm always going to be conditioning on a particular value here。

 which means I'm selecting a set of rows。Okay。And then。

Then I compute the probability of the conditioning event， which I'm going to call the evidence。

So I observe evidence， I look outside and I see it's raining， okay。

 and so I now I want to condition on that evidence to make other inferences。

So then I have to compute the probability of this evidence。

 which is essentially the sum over all the assignments， probabilities of all the assignments。

That are left after the selection process。 So here I have。01 and 11， which has probability 0。1。Okay。

And then finally， I divide by this probability。嗯。S equals0。

 given R equals1 is a selected joint probability divided by this probability of evidence。

And same for S equals  one。ok。So this you can think about this as a renormalization。

 so first select based on the evidence， so I look at only the assignments that matter。

 but these are really low probabilities because the probability of rain itself is small。

 And so when you condition you're saying like if it rained。

 so that means you're sort of dividing by the evidence so even if the probability of evidences is small。

 you're sort of like blowing up these probabilities so they sum to one。Okay。

 so you can also use Einops to compute this conditional distribution， there's just a few more steps。

 but hopefully this map makes it clear。 So the first thing we're going to do is how do we do this selection。

I'm going to introduce this tensor R1， So this is basically saying if I put in the value of R。

 it's going to tell me whether the constraint is satisfying or not， so I put in zero。

 thats zero because that's false and if I put in one I get，One or true， which means that it's true。

Okay， so then what I'm going to do is take my joint distribution PSR， this thing over here。

And then I'm going to essentially multiply this by R1。Okay。

 and that's going to zero out a bunch of things。 Okay， so now I have two tensors here。

And just to keep track of the axes， so the first tensor is just labeled with S and R and the second one is labeled with R。

And then the output is。I want us。Because I could put R here。

 but R is always going to be one because that's what I selected for。Okay。

 so that gives me this quantity。Which is what I had before。

 so this is the selection of this with this evidence R equals1。Where I simply drop the R。

 so R doesn't show up on the right hand side。Okay， and then it's basically the same thing as before。

 we compute the probability of the evidence。 and the way you do that in inops is you look at。This。

This probability table and which is indexed by S， and then you don't have an output。

 which means that it just sums over all the elements here and that gives you 0。1。

And then finally you just。Divide。Ops。So this when you divide probability of s equals S R equals 1。

 divided by probability r equals 1， you get probability of s equals S condition RNA equals 1。

 and you can see that that gives you 0。8 and 0。2。The question is。

 are you going to represent this last step with any Einstein right now this is just a scalar so you don't really need any。

T fancy。Yeah， so the question is whether this works for discrete or continuous variables so everything we do in this class will have discrete random variables here and you can use eNom if you have continuous variables。

 then you need when you do marginalization you have to do integrals and you know conditioning with conditioning variables becomes a little bit you know diceC because you can condition on basically probability zero events so you have to be careful there。

Okay， so let me summarize。So。You know I think many of you probably have experienced probability and done probability before。

 I think it is important to have the right kind of conceptual intuitions for what all the probabilities represent。

 so joint distribution。We can think about this as a source of truth。 Remember。

 we're modeling states of a world。 So for every。Assignment， which is a save the world。

 I have the probability that is that state occurs。And that everything derives from the joint distribution。

 so marginalization。The intuition is that you're collapsing assignments that only differ in the marginalized variables。

 so you're ignoring some variables， so you're ignoring kind of differences in some variables。

And then conditioning you should think about as your。

You observe something in the world like it's raining and you want to condition on that。

 which means that you select by the evidence。Compute the probability of evidence and you divide。

 and that gives you the renormalized probability of whatever you're interested in condition on that event。

And finally， the probability tables are tensors， so we'll be using inOops to express these computations。

Okay， so。So now I introduce basic probability， let me talk a little bit about probabilistic inference in general。

 here's just another example， so suppose you have four random variables now sunshine。

 rain traffic and whether it's autumn or not now the joint distribution would look like this probability of SRTA。

And what do you do with this joint distribution？Right so what you do with it is that you can ask questions of it。

 for example， if you're interested in knowing what is a probability that it's going to rain。

 given that there's going to be traffic and also it's autumn。

And the task of probabilistic inference is to answer questions such as these。

Based on the joint distribution。So an analogy you should have in your head is that the joint distribution is like a SQL database。

And probabilistic inference is essentially doing SQL queries on that database。

And there's actually a much formal relationship here， which I'm not going to get into。

 but I think that's the mental model。 You have your database with all the facts and you just ask questions。

 know what is the tallest。You know， building with in。In Europe or something like that。Okay。

 so what is the type of question we can answer， they're all going to look like this。

So they're always going to have some evidence that we're conditioning on。

 and their evidence selects a subset of the variables such as T and A and basically assigns them to particular values。

 So in this case， it's traffic and autumn。And given the evidence， we're interested in a query。嗯。Rain。

 for example。So in probability notation， what we're asking for is the probability of rain given the evidence t equals 1 a equals 1。

And notice that not all the variables I mentioned， the variables that are not in either the the evidence or the query are assumed to be marginalized out。

 For example， S here is sunshine。 It's not mentioned。

 So I'm going to remember collapse assignments that have the same that have。

That don't have the same value of S。O。So now let me go through another example Now what we're going to do is we're going to start introducing Bayesian networks so far。

 theres there's nothing Bayesian networks about it because Bayesian networks is built on top of probabilities。

 so we have to understand probabilities first。And the whole point of Beijing networks is that it will make things easier to define joint distributions。

 so that's where we're going。So I'm going to start with an example and let's try to solve it using a Bayesian network。

 later I'm going to define formally what a Bayesian network is。

 but by that time hopefully you'll already understand through examples。

So this is a problem of earthquakes， burglaries， and alarms。So we're going to assume。

That earthquakes and burglaries are independent events， and each happens with probability 0。05。

 so 5% chance， which is actually kind of high， but let's go with that。

So you've installed an alarm in your house and the。Alarm will go off。

If there's an earthquake or a burglary。Okay， and suppose that， you know。

 you're away on a trip somewhere， but of course， your alarm is hooked up to your phone and you see。

 oh， there's an alarm。And suppose that this alarm， doesn't tell you why the alarm is going up。

 it just tells you that there's this alarm。Okay， so then you probably know at this point。

 something's wrong， okay， but you don't know what it is。So now here's the question。嗯。就。

Suppose you then， you know， you pull up the news and you see that， oh。

 there was actually an earthquake。You know， near where you are， your house was。

So how does hearing the news change the probability of the burglary？Okay， so I'm going to ask you。

 I'm going to take a poll on this， so there's three options。The probability of the burglary。

 given that there's an earthquake and alarm goes down。It goes up。Or it stays the same。

So this is what you might be thinking， well intuitively it seems like it should go down。

 but then h they're supposed to be independent。 So if they're independent， why would it go down？

Because what do burglaries and earthquakes have to do with each other， nothing， right？Okay。

 so there's a parent like paradox here， which we're going to resolve。 So just just hand tight。Okay。

So the way we're going to resolve this is to be define a Bayesian network。

 and then everything will become crystal clear。So what we're going to do is define a joint distribution over earthquake。

 burglary and alarm， and then what we want to know is。Which is larger or they're the same？

The probability of a burglary given the alarm only， or the probability of burglary given an alarm。

 and there's an earthquake。Okay， so now I've formally specified。What， what this。

What I'm interested in in terms of probabilistic inference。Okay。

 so then we're going to solve this problem using Bayesian network， so we're going to do two things。

 we're going to construct a joint distribution。And then once we do it。

 then we can do probabilistic inference。Okay。Alright。

 so let's first construct the joint distribution。So we could just write down this huge table directly right so mean it's not that big。

 there's eight possible assignments to three variables two to the third。

 so we can just write them all down。But it's going to be much nicer to do this in a more intuitive way。

 And the more intuitive way has four steps here。First， I'm going to define the variables。

Then I'm going to connect the variables with directed edges。

Then I'm going to write down a local conditional distribution probability for each variable。

 and then finally multiply everything together to get the joint distribution。

 So I'm going to do this in a more modular way。 And I'm going to go through the four steps。

 But that's the， the roadmap here。Okay， so the first step is you define the variables。Okay。

 so what are the variables？Well， there's B， which is I there a burglary， E is there a earthquake。

 and a is there a alarm going off。Okay， done。Usually， that's the easy part。Step two。

 we're going to connect the variables with directed edges， which just suggests direct influence。

And here I want to be a bit careful because the natural thing would be to say it causes。

 but causality is a pretty tricky topic。 so technically Bay networks do not are not automatically implied causality。

So， but if you want， you can think about it as a cause if it helps your intuition。

 just know that it's not completely formal。 Okay， so here are my three variables。

 each variable is a node and and the idea is that well。

 there's burglaries and the earthquakes and then alarm depends on burglary or earthquake right。

 so alarm goes off if B or E， So that's why alarm is sort of derived from B orE。Okay。

 so now we have this。Probability。Now I'm going to， let me just do it on the board here。

So we have it as a reference， so we have probability of B。A and oh， sorry。B E。诶。

And we have these edges here。And then so now for each node， every variable。

 I need to specify how it behaves。And here， I'm going to write down a a local conditional distribution of a node given its parents。

 So here I have the probability of a burglary。 Here， I have the probability of a。No earthquake。嗯。

And then here I have the probability of alarm given burglary earthquake。O。And for each of these。

 I need to specify the probability table。So I'm going to assume based on the problem statement that the probability of a rare ven is epsilon。

 which is 0。05。And so。So the first probability， local distribution is probability of B equals B。

 so the probability of no burglary is 0。95， burglary is 0。05。Okay， the same for earthquake。

 probability of no earthquake is 0。95。 probabilityb of earthquake is 0。05。Okay。

So you can think about each of these tables as sitting on a node。And now here。

Just to explain this a bit。 So now I'm giving you the probability of A， given B and E。 and in code。

 I have this， you can do this this trick， which gives you a compact way of representing this table。

 So instead of specifying every single combination。

 you can write a function that computes every single value and the function here is。

Basically called for every row， and it takes the value of B， value of E and value of A。

 and returns the probability。Okay， so what this is doing is saying。

 let's see if a is equal to the pro B or E。So if it's equal， then it has probability 1。

And if it's not， Eco has probability zero。So for example， if b is 1， e is 0， a is 0。

 that0 is not equal to 1 or 0， so that's a 0， whereas1 is equal to1 or0， so that's a 1。

So that's how all of these probabilities are filled out given this function。Okay。

So now I have these three local conditional distributions， one for each of these variables。

And that's the end of step three。Step 4。Is。Defining the joint distribution is a product of the local conditional distributions。

And here。This means for every possible assignment to B， E and A。

 the joint distribution is defined to be the product of the local conditional distributions。Again。

 whenever you see something like this where there's a bunch of foralls and then some。

 remember each of these is going to be represented tensor and you multiply the tensors together。

 then you can use Esome。And let's just see what's happening。 So I have P， B， P， E。

 and P A given B and E。 and I'm multiplying all these things together。 That's what I and Z does。

 And this strain tells me how all the indexes are going to behave。

 So P B is this tensor corresponds to indexing B， this one corresponds to indexing E。

 and then this one I have B， E and A。Okay， and the output is B， E And A。Okay。

 so I'll just show you what the result looks like， probability of B， E and A。

 I mean the numbers aren't too important， but they're just you know。

 this basically is the product of these three probability tables。And just to sandity check。

 the probability of nothing happening is 09。 So that's reasonable。 Nothing usually happens。

 The probability of。The probability of there's a burglary and an earthquake。

 and your alarm goes off is pretty low。Okay， so let me pause here。

 so these are the four steps and we've defined the joint distribution over all random variables。

 and that characterizes the problems set up precisely。

The next part is once I have this joint distribution。

 this is our database right now I'm going to do equivalent of SQL queries。

 and that's problematic inference。So now we can answer any queries we want， so I'm going to do a few。

 and we're going to look at what the results tell us。So first。

 let's just warm up with something very simple， so let's compute the probability of a burglary。Okay。

 so。Every one of these queries is going to begin with this joint distribution。

 That's our database and， and do a bunch of marginalization conditioning as needed。 So this is。

 you know， fairly straightforward。 I have this joint distribution。 And I erase E and A。

 which means I'm marginalizing out。 And then that gives me。Probability of of B。Okay。

 and you'll notice that。This is the exact same as the local conditional distribution of B that I had earlier。

Which is。Good， I want to take this opportunity to point out that I'm explicitly differentiating between these local conditional distributions。

 which are I'm using a lowercase P。And the marginal distributions， which I use uppercase P。

And the way to think about this is that local conditional distributions are。Just define。

 I just define the local distribution in。I just wrote it down like up here。

And these marginal distributions are。Basically， mathematically derive based on the laws of probability from the joint。

RightSo anytime you see a big P， that means it's derived from the joint。Okay。

 so these are mathematically two different objects。

 It's not maybe obvious at first sight that they should be the same， but。

 they happen to be the same in all cases， which is why sometimes people just mix up to two。

 but I think just if you want to understand rigorously where things are coming from。

 there's the local distributions that define the probabil and then the marginals which are derived。

Okay， so the probability of burglary in this case is 0。05 okay， so it's pretty low。

 that's as advertised。And then now let's do burglary given alarm only。Okay。

 so how do I do conditioning， We've done this before， We first select based on the evidence。

 So evidence says a is equal to1。I'm going to multiply a1 this selection of tensor into the joint distribution。

And furthermore， this joint distribution， and I'm going to multiply this this selection tensor here。

 and then here I'm also going to simultaneously just erase E and A。

Because I marginalize them out because I'm only interested in B。Okay， so you can see。

 kind of see why Einom is so powerful， right， because I'm doing two things here。 I'm。

 I'm both selecting andm also marginalizing at the same time。Okay， so this gives me this tensor。

 So this is a probability of ignoring earthquake， probably of burglary and alarm。

 So notice that the joint distributions are always small values。 Okay。

 because both burglaries and alarms are pretty low probability。

Now I need to convert this into conditional， so what do I do I compute the probability of the evidence。

Which means I'm adding these two things up。A B to nothing。

And then I divide by the probability of the evidence。And that gives me this。Okay。

 so I'm going to take this tensor and I're going to divide by 0。09。

 and usually when you divide by the evidence that bumps up all the scales up all the probabilities because they have to normalize to one。

Notice that these don't sum to one， right。They would sum to one if you well actually yeah these aren't sum to one。

 so when it's only when you divide by the probabilityative evidence， then you get a distribution。

And just to remind you， when you see a probability， when you sum over the left hand side。

 that's when you get to one， the right hand side is you're not summing over that。Okay。

 so the probability that there is a burglary。Given that there's alarm is a little bit over 50%。

This sort of makes sense。 You see the alarm， so you're thinking， well。

 it could be burglary or earthquake or maybe both， so it should be pretty high。

 you should be really worried at this point。Okay， so burgary is much more likely。 Okay。

 so now we come to。The final。You know， everyone's in their seats waiting for the answer here。

 so what's the probability of  Burly given that there's an alarm and earthquake？Okay。

 so here I have two pieces of evidence， so I'm going to define these two selection tensors。

 A1 and E1。And then I'm going to， again， do this mega operation。

 Why I take the joint distribution probability of B， E and A， I take this。ASe Tensor A1 and E1。

And then I'm going to multiply this to zero out the rows where the evidence is not true。

And then I'm going to also drop E and A， and that gives me probability A B， A is1 and E is1。

So let's see what that gives us， it gives us this。And then the rest is the same as before。

 compute the probability of the evidence， which means add these two numbers up。

And then divide by the probability of evidence。To give us the probability of burglary given alarm an earthquake。

And you notice that now the probability of the burglary has indeed decreased。To 0。05。Okay。

 so the people who had kind of followed your intuition were correct。And so now the。

 the question is like， wait， wasn't this this thing about kind of independence here。 So why。

 why does why would。You know， burglaries or knowing about earthquakes affect burglaries。And this is。

The intuitive reason is that if you think about， why did the alarm or alarm sound？Okay。

 it must have been because an earthquake or a burglary。

And when you see the when you observe earthquake。Then this explains away the alarm。Meaning that， oh。

 it's probably the earthquake that's generating the alarm， not the burglary。

So it sort of takes the pressure off of the burglary and puts it on earthquake。

 That's sort of the intuitive reason why it holds。And this。And the reason， well， I mean。

 this is just math。 So it's just true。 But you know。

 in case you're still wondering about why there is this sort of。You know， independence。

 What happens is independence。 And the key thing here is that B and E。Are not。Or are independent。

 if you don't have a， if you don't observe a， these are independent。

But when you observe variables that are downstream of things that are independent and you observe them。

 that makes the variables upstream not independent anymore。Okay。

And so the reason why I think Beijing networks are powerful is that there's all， you know。

 people before， I think they really nail these things down probabilistically。

 they had all these sort of houristic ways of reasoning about uncertainty。

 and they were all sort of inconsistent and broken。

And only when you break kind of mathematical clarity to this， then its sort of then。

It sort of makes sense。Okay， so this idea of explaining a away is actually quite general and powerful and it's sort of a defining feature of a Bayesian network。

嗯。So the general idea is that you have two causes， in this case it's a burgllarary earthquake。

 positively influencing an effect A。So， you， if you condition an effect。

And then you further condition on one of the causes。That reduces the probability of the other cause。

 In other words， E explains away the evidence and you don't need the other cause to explain。

So in symbols， the relationship between the probability of B condition on both other cause and the effect is less than the probability just condition on the effect。

And important and the cool thing is that this is true， even if the causes are independent。Okay。

Just a quick note about notation， I'll just emphasize this again。

I'm using lowercase and uppercase deliberately here， lowercase names。

Are are represent particular values。 So， for example。I think。Up there， I had， let's see。ok。

For example， the probability of a random a variable uppercase equals a particular value。

 which is a lower case， so that's the convention。And then secondly。

 I'm using lowercase P to denote the local conditional probabilities which are given by definition and uppercase P to denote the modules and conditionals which are derived from the joint distribution by the laws of probability。

 so I already mention this and furthermore， if I write p of E， that is the whole probability table。

 and if I write p of E equals a particular value， that is a probability which is a number。对。

All right， to summarize。What we've done so far is we've defined a joint distribution via this four step procedure。

 you define what the random of variables are， what the edges between the random variables are for each node slash variable。

 define a local conditional probability， and then multiply them together to produce a joint distribution。

So this is an intuitive way of defining these joint distributions rather than slavishly going through and writing out every probability。

Now we also did probabilistic inference， which basically said select assignment rows based on the evidence。

 compute the probability of the evidence， and then divide by that probability。

And then so that's mechanically what happens。And then we also saw that explaining away was this really cool phenomena that happens。

 it's a qualitative reasoning pattern that follows from the math。So let's move on。

 let's do another example， this is going to be similar to alarm。

 but it's four nodes instead of three nodes。But hopefully it'll just give you reinforce these ideas if you see it another time。

So here the problem is， I guess a lot of people are sick these days。

 so if you're coughing and you have itchy eyes， what is the probability that you have a cold？

So I should preface this with saying I don't know anything about you know don't trust the medical sciences。

 this is just an example， don't take this as medical advice。Okay。

 so let's model this problem using a Bay network。So step one， define the random variables。

 So what's going on here theres。There's potentially you have a cold。

 either you have a cold or you don't。You have allergies or you don't。

you're coughing or you're not and if you're HyIs or you dot。

 and of course this is a simplification because there's degrees of which you can have these。

 but again this is just a toy example。Step two， connect the variables with directed edges。So again。

 using my very sketchy medical prior knowledge， we say that， well， cold analog allergies。

 let's say they're just independent， so there's nothing connecting them。

And so these are the potential problems and the symptoms are you cough when either you have a cold or allergies。

And you have itchy eyes only when you have allergies。Okay。So this is what it looks like。And。

So now let's step3， write down the local conditional probabilities for every variable。

 So there's four variables here， and we're going to go through each variable and write down。嗯。Co。

Okay。OK是这样。Um so we have probability of C， so for C， I write down， well， you know， colds are。

 you know， 10% chance you have a cold。Allergies， 20% chance you have allergies。here is。

um this is a little bit more complicated， but this is what's a probability that you have a cough given that your state of cold analogergies。

So this is a local conditional distribution where I'm conditioning on C and A。

 and I want to know what the probabilityative H is。So here what I've written down this function as。

 well， if。H matches C or A， then that's going to happen with probability 0。

9 and otherwise with probability 0。1。 So before I just had one and0。

 But now because it's just just to make things a little bit hedge our bets a little bit。

 we're gonna to make them a little bit smoother。 So 0。9 and 0。1。Okay， so for example。

 just to be clear， this entry says that if you have a cold and you have no allergies。

 then the probability you have a cough is 0。9。Okay， and then the fourth variable is I。Given a。

 So this is the probability of H EI's given allergies。

 And I'm just going to assume that it's 09 if the two are agreed。 So probability of。Allergies。

 sorryII is given allergies is 0。9， the probability of not itchiIs given allergies is 0。1。Okay。

 so now I've defined these four local conditional distributions。

I can define the joint distribution by just multiplying them all together and this gives us this pretty horrendous mess。

 but conceptually it's hopefully clear that you just take the local conditional distributions and you multiply them all together and you just have to make sure that you put all the right indices here。

Okay。So for each of these four local conditional distributions。

 you have to write down the variables in the order that it came and just as a convention。

 this is written H given CA and I always write the conditioning variables first and then the variable that the actual variable itself lastshed。

Okay， so that gives me this。Database table of probabilities and you can spot check things here。

 so most of the time 0。6 point of the time nothing's happening and the probability that you have。

Like a lot of things going wrong is much lower。Okay， so now we do probabilistic inference。

 we can ask any question we want， so what is the probability of cold given cough？

And I think I'm going to go through these a little bit faster because it's the same kind of idea。

 but you can go through the lecture notes afterwards。

So you first select based on the evidence and marginalize out the variables that you're not interested in。

 so we're only interested in cold and cough right so allergies and HEIs just forget about it。

 just collapse them。Okay， so this gives us the probability of cough and sorry。

 cold and cough equals one。Compute the probability of the evidence。

 which is just adding these up and then dividing by the probability of the evidence to get a normalized answer。

 So the answer is the probability that you have a cold。Given that you have a cough is 0。28。Okay。

 so let's do another one， let's compute the probability you have a cold given。

 you have a cough and itchy eyes。So now let me ask you this question。So this probability was。28。

What do people think about if you have itchy eyes， does that increase。

 decrease or keep the probability of the cold the same？Okay， so let's look here。

So this is a little bit tricky， so I think a lot of tenuous hands there which is to be expected。

 that's why we have math and you can just we can do it。So here I'll go through this quickly。

 so you select based on the evidence， so you multiply this joint probability by a equals 1 and i equals 1。

And that gives you a probability of over probability of cold and h equals one I equals 1。

 compute the probability of evidence。Summing these two and then dividing。

 And you see that the probability of cold has gone down。Okay。

 so at this point you're thinking like what's going on here， so let me explain。

So why is the probability- actually， let me ask you this question。

 why is the probability of cold lower if you add H itchyI？

So the probability of cold given just cough is 0。27 and the probability of cold given cough and HEIs is 0。

13， so it's almost half。Yeah， exactly。Basically， this is an example of explaining it away again。

So in what was explain way， you have an effect， you have two causes。But， you know。

 the itchy eyes is not a cause。Of this effect， right， There's no edge from I to H。But。

I is connected to A。 So if you observe you have HyIs。

 that actually increases the probability of allergies and now increasing the probability of allergies now explains away the cough and why you're less likely to have a cold。

Okay， so I think this is really neat how you just define the Bayesian network and all these kind of reasoning patterns pop out。

I don't think anyone probably would have like 100 really good confidence to just intuitively think。

 well， if you have HchyIs， how much would the probability of a cough change。

 but if you have the Bayesian network it handles things for you。Okay。

 so to summarize this same recipe here。Joint distribution， once you define it。

 you can do probabilistic inference。We see that explaining ways shows up again。

 now a little bit more complicated。And in general， I think you could imagine， let's say。

100 variable Bayesian network right and you're conditioning on like 17 of the evidence variables and all the variables are sort of interacting with each other。

 and intuitively， you can think about them as propagating evidence。

 if you observe one node that sort of suggest the values of other nodes。

 but then you the other values will also propagate。 So it can be rather you know complicated。

 And in general， computing these quantities is actually know can be empty hard。

 So it's not actually a pretty sophisticated operation here。Okay， so finally。

 we've seen two examples of Beijing networks alarm。And medical diagnosis。

 so let me introduce the general case here。So in the general case， the same four step procedure。

 you define a set of random variables， often I'll denote these as x1 through xn。

I define any directedcyclic graph over the variables， so any graph， but there can't be cycles。

And for each node， I'm XI， I'm going to define a local conditional distribution。

 XI given the parents of XI。And then define the joint distribution by just multiplying all the local conditional distributions together。

Okay， so important reminders because it you know， it's easy to kind of make this mistake。

 you have one local condition distribution per node， not edge。

And also the local conditional distribution depends on all the parents at once。Okay。

 so don't forget to write down probability of C just because there's no edge ver and don't write down probability of H given C times probably H given A。

 That's incorrect。 You have to tie the the parents together。In the literature。

 they call this the parents are married。 So just maybe if that's a helpful way to think about it。

Okay， and then finally， know the difference between local distributions and the joint distribution。

Okay。All right， so then when you do probabilistic inference， you're given this Bayesian network。

 which defines this joint distribution over all n variables， there's some evidence。

Usually written as E equals little E。Where big E is a subset of an X is the variables。 So。

 for example， you can say， I observe that x 3 and x 7 are 0 and1 respectively， for example。

And then you're interested in a set of query variables， which could be any other subset of nodes。

 which like x2 and x4。And anything that's not mentioned， like x1 and x5。

 x6 are assumed to be marginalized out。And the output is this probability table。

 which gives us the probability of every assignment to Q condition on e equals E。Okay。So one。

So Beijing networks actually show up in a bunch of places， usually you don't think about them。

 but I'll just give you some examples。 So for example， our rigorousgress of language models。

 So if we put on Beijing network hats，Then a lot of reive language model is actually a Bayesian network。

 So the random variables are the tokens。 I suppose you're going to generate T tokens。

 so the tokens are x1 through Xt。There's edges from。All previous tokens to a current token。

The local condition of distribution is given by this transformer。Usually in language modeling。

 and then the joint distribution is still the same that's a product of XT given all the previous Xts。

Okay， so if you were to draw the network。For a language model， it would look something like this。

So every， it just happens that every。Variable is connected to all previous variables and so on and so forth。

Okay， so typically， if you have a language model， you just sample forward。

Okay so if you're given a prompt x1， x to x3， and you sample x4。

 given the previous and then sample x5， given x1 to X4， x6， given the past and so on and so forth。

 this is basically what you do in language modeling。But so now the interesting thing is。

 what would probabilistic inference mean here。So the probability inference really means kind of reversing and changing you can the whole idea of probability inference inference。

 you can reason about any subset of variables given other subset of variables。

 So one thing you might want to do is what's the probability of suppose I see a response， x 4， x4， 5。

 x6， I want to figure out what prompt generated that response。

So this has an application in jailbreaking language bottles， so for example。

 you could ask what is a given response， sure， here's how you make a bomb or something dangerous and then you ask you basically problem is figuring out the prompt that leads to the response。

Okay。So this is very uncommon， mostly because it language models are designed to just go forward。

 but it is interesting to note that once you define a joint distribution。

 you can mathematically go in any order you want and going in different orders actually gives you some interesting insights。

 the downside is that this is extremely computationally expensive task。

And it's in general exponentially hard， but this paper has some interesting ideas on how you can make this faster using variational inference。

Okay， I just want to pop that example there so that you can see how this topic might connect you some more modern ideas。

Okay， in the last 10 minutes， I'm going to talk about。Two things。

 one is a different way to think about Bayesian networks。

 and then that's going to allow us to do something called rejection sampling for approximate Bayesian inference。

Okay， so so far we've defined these Bayesian networks as just writing down these local conditional distributions。

And that's fine， that's better than writing down the whole probability table。

 which no one really does for a large number of variables。

But now we're going to define these via probabilistic programs So there's a whole field called probabilistic programming which explores the interaction between programs and distributions。

 So we'll give you a taste of this and the ideas are fairly natural and elegant So let's revisit our old alarm example。

 So we have the burglar burglary earthquake and alarm and I'm going to define a function。

 a program called alarm。That's just going to give me a random sample according to the joint distribution。

So how this is going to work is？I'm going to set B equals to this Bernoulli， 0。05。

 and all Bernoulli does is it just returns one with this probability。So this is backed by MP random。

And then I'm going to set earthquake to be the same， so this is a random function。

 and I'm going to set A equals B or E。And I'm going to just return the assignment， okay？

So if I sample again， I think I might not get anything other than 000 because the remember the probability is。

05， so it's pretty low。But okay， so that's it。RightSo this is actually a formal definition of a Bayesian network。

 It's just unusual because it's just a program， but it's one way you can define。

 And the thing I like about this is it's really transparent what's going on， three lines of code。O。

So now let's do probabilistic inference， so how would you do probabilistic inference using this probabilistic program which represents a Bayesian network and therefore joint distribution。

 suppose you wanted to compute the probability of B given a equals 1。Okay。So。

Because we've written the joint distribution in a program， This gives us a natural way to。

Compue this probabilistic inference， and it's a way called rejection sampling。

And the key idea here is that I'm just going to draw a ton of samples just like this。

I'm going to select the samples that match a piece of evidence。

And I'm going to record a histogram over different queries of the samples as I see。Okay。

 so here I'm going to generalize the evidence， so we've been thinking about evidence as a particular assignment to a variable and a query to be like a particular set of variables。

 but they can be any function really， so the query is going to I'm going to think about is taking a sample and returning。

 so remember a sample looks like this。It's a joint assignment to all the variables。

 and I'm going to just return some value。 In this case。

 I'm going to pluck out B because I'm interested in probability of B。Okay。

 and the evidence is going to be a function that takes a sample。

 and I'm going to return whether it matches the evidence。

 So I'm going to look at peak inside to look at the value of a。 and that equals 1。

 Then I return true。Okay， so this is evidence is a function that tests whether a sample satisfies a particular criteria。

Okay， so now rejection sampling is literally five lines of code， okay。For some definition of five。

 So I'm going to keep track of。Counts。Here， so I'm gonna iterate number of samples times。

 I'm going to draw a sample。And you're going to test whether the evidence of that sample is satisfied。

And then if it is， then I increment the counts。 I don't know if this's in this run。

 I don't think in this run， I'll actually get a sample， but if I did， it would increment the hoops。

Sorry， the count and oh， I get get one， I guess。Okay。

 so and then I have the so account of the number of particular query values I see。

 and then I normalize that to get a probability and I return it。Okay， so in that case。

 it wasn't very interesting because I only got one value。But if I do this a thousand times。

We'll see that this gives me an estimate of the probability of the query。

The probability of a query given the evidence。So remember the query here was probability of B。

 so the probability of B given a equals 1， given a equals 1 is 0。56。

 so remember the true number was 0。51 or something so it's close but it's not exactly right because this is just a sampling algorithm。

So。This algorithm can be very inefficient， especially when the evidence is rare。

RightBecause you're essentiallyly sampling from the prior and if you have a rare event。

 you're just like the event happens with probably 0。001。

 then most of the time you're just going to waste your time sampling so it's not a very efficient algorithm。

 but mathematically， I think it's very clean。There is a guarantee that if you are very patient and you increase the number of samples in infinity。

 then this actually converges to the true probability。

And in this class we've seen a lot of times where we do sampling， like we do policy evaluation。

 we just sample expectax， we can sample and so on。Okay， let's do the medical diagnosis example。

 So in medical diagnosis， remember we have we're interested in the probability of cold given cough equals one。

 So here is the floor line Bayesian network。 So cough allergies。 and then。Sorry， cold allergies。

 cough and itchy ice。So again， very， very simple。 and if I。The query is C。

 and the evidence is testing whether H equals1 or not。And then I do rejection sampling。

 I get the probability of cough equals1， given h equals 1 is 0。26。

 which is actually pretty close to the right answer。

And you see that this is closer even with 200 samples， it's because the problem the。

The events of these， the probability of these events are higher。Here's another fancier example。

 and it shows you the power of。Of probabilistic programming or the succinctness。

 so there's these things called hidden Markov models that couldn of look like this。

 they can be used for object tracking so imagine there is some object and H1 H2 represents the position of that object at successive times and then you don't see the object position instead you get a noisy sensor reading of the object。

And so the goal is， for example， to figure out， let's say you observe E5。What is a probability of H3？

Okay， so this is， you know， fairly complicated。 There's a lot of things happening here。

 But rejection and sampling is a fairly like， you know， black box way of handling this。

 So hit a Markov model。 Here's what we're gonna do。 We're gonna to iterate for five steps。

And for each step， what I'm going to do is I'm going to look at the previous step and I'm going to add either one with probability 0。

5 or 0 with probability 0。5 so 0。5 probably I stay this in the same state， probability 0。

5 I advance to an next state。And then this E is basically the noisy sensor observation where I get。

 I have my。T location and I either add one or add zero， depending on it。

And then you return basically the sequence of H's and E's。Okay， so this gives you a sample。

 the query here is。I'm interested in H22 because it's a zero base instead of one based and evidence E4。

Oh， and testing that equals two。Okay， so now if I do rejection sampling。

 I can estimate the probability of H3 given E5 equals 2。And basically。

 I inferred that the object most likely was in position one， but maybe it was in position zero。Okay。

All right， so to summarize。This section was brief， but I think it has a lot of。Important insights。

The probilive programming is another way to think about programs as representations of distribution。

So this is a sort of a。Pretty different way of thinking about probability。

 which I think is has some attractive features because once you can sample。

 you can do a lot of things， for example， rejection sampling。

 you can just draw samples and then compute or estimate at least the probability of various queries that you're interested in。

Okay， so quick maybe discussion here。 One is that if you're used to thinking about building classifiers。

 which we're all used to in modern machine learning。

 using Bayes networks requires a shift in mindset So for example。

 if you wanted to predict whether you have a cold versus a cough right in traditional machine learning。

 you would say okay， let me train a classifier that maps my input into output。

 So the input here is whether I have a cough and the output is whether I have a coal but in Bayian networks。

 you're often going from output to input right because the way you to think about is。No， I。

Interesting the cold and that I'm defined a Beijingesian network that takes cold and generates what are the things I observe。

And then you're using probabilistic inference to kind of go backwards。So why would you do this？

 One advantage is that it handles missing information。 So， for example。

 if your data points have a missing value， sometimes the doctor didn't record whether you had HEIs or not Bay models allow you to automatically take that into account。

 if you have prior knowledge about how things work like you know your alarm system what it reacts to you can just write down what it does instead of trying to learn that you can interpret all the intermediate variables here。

 it gives you interability， which is often missing from big end to- end systems and then you can answer。

Questions about causality， which is beyond the scope of this class。

 but Bayesian networks give you a way to do that。Okay， so to final summary， so probability。

 there's joint distributions， you can marginalize them， you can condition， these are all tensors。

 you can use IOs。Beesian networkss gives you a convenient way to define joint distributions。

 probabilistic inference says giving me a joint distribution。

 I can answer questions which look like probability of query given evidence and then finally Ive showed you probabilistic programs as a way to represent programs as joint distributions and finally rejection sampling which is a very simple and generic way to do probabilistic inference in any Bayesian network。

But it is very slow， and so next time we're going to try to improve the algorithm and look at other alternatives。



![](img/4f9c544e3dee2e3d52ef198ea9cf7548_3.png)