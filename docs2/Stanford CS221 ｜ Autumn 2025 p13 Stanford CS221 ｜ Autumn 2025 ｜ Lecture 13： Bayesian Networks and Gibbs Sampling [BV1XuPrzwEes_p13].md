# Stanford CS221 ｜ Autumn 2025 p13 Stanford CS221 ｜ Autumn 2025 ｜ Lecture 13： Bayesian Networks and Gibbs Sampling [BV1XuPrzwEes_p13]

![](img/a937d8a29715cb4f318cca2ad69bd18a_0.png)

![](img/a937d8a29715cb4f318cca2ad69bd18a_1.png)

Last lecture we started talking about Bay networks。

And Bayian Networks is this new chapter on how to represent the world and in particular。

 uncertainties about the world。And last time we looked at rejection sampling as a way to answer queries about Bay Notes。

 and this time we're mostly going to focus on Gib sampling which is faster， potentially faster。

 I should say， way to do probabilistic inference， and then we're going to talk about conditional independence。

So let's start by reviewing Bayesian networkss， so Bayian networkss are probably one of the most kind of intensely deep part of the class。

 so please ask me questions if anything is confusing。嗯。So to get us into the right mindset。

 we should think about joint distributions over a set of variables as like a database that specifies how the world works right so you have a state of the world that's represented by assignment to a bunch of variables。

 and the database basically says for every assignment how likely that is。

So remember we defined Bayesian networks through a four step procedure。

 the first step is in any given problem， you have to figure out what the variables are in general we talk about variables as X1 through XN。

 but in a specific example we saw a case where we had three variables。

 one representing whether there's a burglary B， one representing whether there's an earthquake。

 E and one representing whether the alarm went off a。Okay so once you have all the variables。

 then you define a graph over all the variables。So in this case。

 we intuitively think of burglaries and earthquakes as independent events。

 but the alarm is going to depend on either there's a burglary or an earthquake。

That's what's advertised by the alarm， the alarm goes off if there's a burgary or earthquake。Okay。

 so now we have this graph。And this specifies the structure of the Bayian network。

 think about it's kind of like the bones in some sense。

And now the third step is to actually put meat on those bones。

 So the meat here is actually specifying numerically the local conditional distribution。

For every node， given the parents of that node。So in this case， there are three nodes。

So for each node B， I have the probability of B given its parents， there's no parents。

 so it's just P of B， I have probability of E given its parents， there's no parents。

 so that's P of E and the probability of A given its parents， which are B and E。

 so I have probability of A given B and E。Okay， so the local conditional distributions are going to be denoted with a lowercase P。

Okay， so just to ground this out in code。We can look at probability tables。So for example。

 probability of B represents this table， which is for every setting of V I have a probability。

 so the probability of there being a burglary is of 0。05。

and the probability of not bearing up burglary is 0。95。Okay， so same with earthquake。

 I have the probability of an earthquake being 0。05 and not being an earthquake， 0。95。

And then finally， I have this table， which represents the probability of their alarm。

 given the status of burglary and earthquake， so for all possible settings of B and E。

 I have to give a probability of A。Okay and this is a really shorthand for saying。

 I first compute B or E， that's a booleed。 And if that equals a， then it's a probability of one。

 otherwise it's a probability 0。 Okay， so what this logically says is a equals B or E。Okay。

 so you can just check that if A equals B or E， then I get a probability of1。

 if a does not equal B or E， then I get a probability of0。

So that's sort of a probabilically verbo way of just saying a equals B or E。Okay。

 so given these tables， I can define the joint distribution over a set of random variables as simply the product of all the local conditional distributions。

 so in this particular example， the joint distribution written with an uppercase P is equal to just those product of a local conditional distributions。

 P of B， P of B， B of a given B and E。Okay， so we also saw that we can。

Use Einom notation to simply multiply all these local conditional distributions。

 which are just tensors。Together， and so you have P of B， P of E， P of A given B and E。

 and then you just make sure you index the right variables， B and E for the first case。

 and then BEA for the last local conditional distribution。And that gives me the joint distribution。

Okay。So I could have just written down numbers for all these eight possible assignments。

But the way we did it is going through this more qualitatively inspired process of defining the the Bayesian network。

 This gives us a little bit more interpretability than just writing down some arbitrary numbers。

So what do you do with a Bayesia network？Yeah， so we infer the probability of certain variables given other ones。

 so this is a joint distribution， you can think about it as a database。

 so literally it can be represented at a table， but instead of using SQL。

 you use the language of probabilistic inferences。So you might be interested in what is the probability of there being a burglary given the alarm went off。

That is one particular query and the way you compute this。Is as follows。m so。I'm using slightly。

 I'm going to introduce another step here that is different from last time。

 I think this is a bit more intuitive。 So the first。I have up here。

 I have just the probability of B E and A， right， and then in general。

 probabilistic inference query looks like I'm interested in the probability of some query variables given some evidence。

 evidence here is a equals1。So what I'm going to do is condition on evidence。

So I basically take the probability tensor of a B E A and I'm going to slice it。

 I'm just going to take so this corresponds to B， this correspond to E and this corresponds to A right。

 so when I say A equals1， I'm just going to take the slice where I only look at a equals 1。Okay。

 so what this looks like is I take this table and I'm going to look at all the rows where a equals1。

 and I'm going to select them out。Okay， so these four rows are exactly the rows where a equals 1。

Okay， you can check that。Okay， so now I'm interested in B given a equals 1。 I don't care about E。

So what I'm going to do is marginalize E out and that basically corresponds to remember marginalization is just kind of ignoring E so I'm going to collapse entries that have different values of E but the same elsewhere So I'm going to collapse these first two rows in these last two rows and then in this notation I can use eN sum to do that as well。

 So that gives me probability of B and A equals one。Okay。So that's probabilitybable B and a equals 1。

Allright。So the next step is this is the probability of B and a equals1。

 I want condition on a equals  one。So to condition。

 it's just the rules of probability that I need to first compute。

 what is the probability of the evidence， P equals a equals a 1。

And that conveniently here is just the sum of these two items。Okay， so if I sum these two two items。

 I get the probability of a equals 1。And then finally， in order to get the probability。

 the joint divided by the module gives me the conditional。

 so I'm just going to divide each of these two numbers by this number and we get my answer。

So finally， the probability of a burglary given alarm equals 1 is 0。51。

Which is what we got last time。Now， one downside is that forming the joint distribution in this way can be really。

 really slow。So imagine you have 100 variables， each variable has two values。

Then the total number of assignments is2 to 100。And you definitely don't want to be writing that down。

Okay， so what we're going to do is do approximate inference。

 so we're going to try to approximate the answer and hope for the best。that's all we can do。

And we took a little bit of detour to explain probabilistic programs。

 which is another way to think about Bay networks in order to introduce rejection sampling。

So idea behind a probabilistic program is that it's a program that returns a sample from the joint distribution。

Okay，And therefore， it defines the distribution。 Okay， I give you a program。

 and if samples from it obey some distribution， then that's as good as the definition in some sense。

Okay so here's an example of the alarmm probabilsistic program。

 I just basically go through each of the variables in the Beijing network and I set its value given its parents so naturally has to a node it has to be generated after its parents are generated so I flip with probability 0。

05， I set B equals1， so usually it get0 E gets 0 and a equals B or E it gets 0 so that is one particular assignment。

So when I run a problemba program， I get an assignment of variables to values。Okay。

 so if I run it again， I'm going to get potentially a different set independent of the first。Okay。

 so then rejection sampling， as we talked about last time， is。

I first declare what part of the assignment I'm interested in， what is a query variable。

 So here I'm interested in B。 So given a sample， I want to extract B。

And then what is the evidence I'm going to represent the evidence as a test of whether the sample satisfies that evidence。

 and here I'm going to look up the value of a and check that it equals 1。

 so remember I'm still computing probability of B given a equals 1。Okay。

 so let's step through the rejection sampling algorithm， just taking one sample。

So I'm going to just for each number of samples。I'm going to just draw a sample calling the probabilistic program that might give me something like this。

And then， oh， I got an earthquake。 Wow， it's very lucky。 Oh， not lucky。 but anyway。

 So if evidence of sample， So remember， evidence is this test that test a equals1。

And if that is true， then I increment the count and I can't increment the count of I take query of sample。

 which gives me the value of B， which is zero， and I increment that。Okay。

 and I loop until I'm at the end， I look at the total number of counts。

And I normalize by that count to get the probabilities。Okay。So why is here's a question。

 why is total count not the same as number samples？Yeah。

 so only some meet the evidence because of rejection， right。

 I only count a sample if it meets the evidence， right。Okay， so。

That gives me the probabilities and if I do it 300 times， then I get this distribution， which。

44 probability of burglary given。Alar equal one。 So notice that it's in the ballpark。 it's not。

 this is the exact quantity that we computed using the actual tensor。

 Here is the approximate and approximation with 300 samples。

 Now if you increase the number of samples is to a million， this is going to get really。

 really close。 but at 300， we're still in the rough， only the rough of ballpark。Okay。

 so one problem with rejection sampling is that it can be quite slow if the evidence is rare。

Okay and in this case， I actually got extremely lucky last remember last lecture I wasn't able to get any earthquakes or burglars。

 and in general， if you're conditioning on some evidence， maybe it could be exponentially small。

 Maybe it's like the probability of hitting the evidence is 10 to the minus 30 or something。

 And then you would just be sitting around and rejecting， rejecting， rejecting， rejecting。

 so it can be a very， very slow algorithm。And the， the problem with this is that if you think about the program。

I'm just generating samples and I'm not even looking at the evidence。

 and I just hope that the program happened to generate the evidence。

So while I really like rejection sampling because it is very simple， like within。In some sense。

 this is the fastest path to defining a Bayian network and also an inference algorithm that is actually provably works in the limit。

 but it is not the most efficient way to do it。Okay， so then how can we do this faster？

That's going to be the topic of the next part of this lecture。Okay。

 so now I'm going to talk about Gib sampling。So remember， rejection sampling。

 what it looks like is that I draw a sample， I draw a sample， I might reject it， I draw a sample。

 I might reject it， reject it。And so the nice thing about rejection sampling is that every sample is independent。

RightSo if I'm estimating some quantity， like 10 samples is 10 independent samples。

 but the the cons are that every time I'm starting from scratch， right。

 So every it's sort of the flip side of this is that this sample doesn't， I'm generally fresh。

 I don't even consider what happened before。So I'm not really kind of learning anything about my past experiences and the second thing is that。

As I mentioned before， I'm generating a sample without looking at the evidence。

 so if the evidence is rare， that's going to cause a lot of rejections。

So Gb sampling is another sampling procedure。But here I'm going to the idea is that I'm going to work with a previous sample。

 which I'm going to construct to always satisfy the evidence and then gradually modify it over time。

 so it's a much more incremental approach rather than throw everything out。

 sample afresh and hope that you hit the evidence。Okay， so here's a basic idea of Gib sampling。

I'm going to start with an arbitrary assignment。And then I'm going to iterly change one variable at a time。

 given the other variables。And I'm going to do this in a very specific way so that I'm going to get a bunch of samples and those samples are going to give me also the kind of the correct answer in the limit。

Okay， it is worth noticing that or noting that G sampling is a special case of a wider class of algorithms called Markov chain Monte Carlos。

 so if you study probability or statistics， you might encounter these things and the idea is that you have a sequence of samples which are drawn and each one is dependent on the other and that's why it's called a Markov chain because each one is dependent on the previous sample。

And the idea with Gi sampling is that we're going just start with samples that satisfy the evidence。

 So from the first getgo， I'm going to incorporate the evidence， so I don't have to reject anything。

 There's no rejection in Gib sampling。Now， the con is that the samples are not going to be independent。

So this sample might be very similar to that one。So if you could get。10。

Independent samples from rejection sampling， that's going to give you a better estimate than 10 samples from Gib sampling where the samples are correlated。

Okay， so I still haven't told you what Gi sampling is。

 so let me try to go through that using a simple example。So how many have played the game telephone？

Okay， maybe when you're young。 but， but the idea is that。

You have some person A who sends a message to person B。

 and then the person the person B sends a message to C。 And in general， this could go on for a while。

 And then you basically see if the message you got out at the end is the same as the the one in the beginning。

 And， of course， the whole point is that every point in time。

 there is a chance that the message gets corrupted。 So at the time at the end。

 that you are not the same。 And everyone burst out into laughter。 Okay That's how it works。

 So let's model this using a Bayesian network。😊，So I'm going to assume that the message is single bit。

 either one or zero。And the probability of the first message is going to be good than going it by a coin flip。

 either 0。5 probability of 0， 05 probability of 1。Okay， so then I look at probability of B given a。

And that's going to be essentially， if。Pot a probability of saying the same and 02 probability of flipping it。

Okay。So if a is 0， then the probability of B equals 0 is 0。8， if a is 1。

 the probability of b equals 1 is 0。8。And C given B is the same。

So point A probability of preserving the message and point2 probability of flipping it。Okay。

 so this defines another Bayesian network。And it defines in particular joint distribution over A。

 B and C。So now the probabiling inference query I want to ask is assuming C。

 the person at the N gets a1。 What is the probability of a。Equals1 or zero。嗯。Okay， so intuitively。

Now if you saw C equals1。That probably increases the probability of a equals1 because the probability of a error is less than 50%。

But there's noise。 So it's not going to be certainly one because there could have been flips。 Okay。

 so that's the intuition。So let's first rerun rejection sampling。

So you shouldn't necessarily in general， be expected to know what the exact value is。

 so let's try to compute it。Okay， so here is a probabilistic program。I have A， I sample a one， B。

 I decided to preserve the message， C， I decided to preserve the message， and I get the sample。Okay。

😊，So then I'm going to do rejection sampling。 I'm interested in the query， which is。What a is。

 and then the evidence I'm going to condition on C equals 1。

 and I do rejection sampling with 100 samples， and I get the probability estimated probability of a equals 1 to be 0。

65。Okay， so seems plausible。Every point there's a 0。2 probability of error。

 so it's sort of if you add that you get point around 0。

6 that's sort like sketchy math a more precise estimate is you can compute。All right。

 so let's do give sampling。So what we're going to do is。Here's a pseudocobe。

 we're going to start with a particular initialization to all the variables。

And then I'm going around Robin through the variables。

 and I'm going to change it based on all the other variables。In particular， to change it。

 I'm going to compute the conditional distribution over a variable， given all the other variables。

 and then sample a new value for that variable， given this conditional distribution。Okay。

 so let me walk through an example to explain what that looks like。

So here I've initialized with an arbitrary samples that satisfies the evidence。

 so this should be c equals 1。So A is one， B is 0。 C is one。 Okay。

 The initialization generally doesn't matter too much， but sometimes for certain problems。

 it could make your。Make your convergence faster or slower。Okay。

 so now let's look at what this conditional distribution is。 Okay。

 so suppose our goal is to sample B。Given A and C， okay。So A is1， B， C is1， B is zero right now。

 and if I think about basically sampling is like what is the probability of B given A and C。

 So what's my best guess at what B should have been。Okay。So to do that。

 we're gonna do some basic math。 So the probability of B equals some value given A And C is the joint probability of A。

 B and C divided by the probability of。A and C， so all the variables except for the one I'm sampling。

ok。😊，So now let's break this down， so the normalizer。

Which is the thing I'm dividing by is a probability of all the variables we're not sampling。

 and that is simply equal to the sum of over values of B of the joint。

And then what is a joint probability is a product of local conditional probabilities which are given above as I define them。

And note it's something that's important here， I'm writing this down。

 but I don't have to instantiate the joint distribution for all possible values of A B and C。

 because in Gib sampling， I'm only looking at a particular assignment and I only care about looking up the probability of that particular assignment or the assignments around that assignment。

Okay， so this is where I get the savings， although if I have to instantiate this for all values。

 A B and C， I' might as well just brute force the whole thing。Okay。So。We we do have to， as stated。

 touch every variable when evaluating the assignment， we'll come back to that later。 Okay。

 so suppose we're sampling B。 Okay， so I need to compute what the value of a equals 1 bs 0 and c equals 1 as well as the probability of a equals 1 b equals 1。

 c equals 1。Okay， so basically what I'm saying is I'm freezing all the other variables。

 I'm only changing B， and I'm going to evaluate each of these new assignments based on the joint probability。

Okay， so let's look at how this is defined。So。Joint probably is a function。

 It takes a particular assignment。And then it its， in some sense， making a modification。

 So it says I'm going to change various some var into value。

 So I might pass B for var and one to value。 And then so here I'm going to let y be the updated assignment。

 So basically taking this original assignment and substituting var colon v here。

 So here I'm basically change 10，1 to。Okay， well， I guess it's a B0 is the same。

 so nothing gets changed there， and then I compute the joint probability of the updated assignment。

And this is going to be that now tensor is a probability of a given Y a， which is1 here。

And then probability of B， given A。Using these assignments， so zero given one。

 and then probability of C given B。ok。So， that gives me。A probability。Of 。02。

For the probability of a equals 1， b equals 0， c equals 1。

And now I do the same thing for the alternative value that I'm considering， which is p equals 1。

And again， why is now I update this assignment to be 111？I compute its probability。

And I get a number out。ok。😊，So and now I compute the normalization。

A factor which is the sum of these two things。I get 0。34， and then I divide。

each of these quantities by P of AC， and that gives me a valid distribution over B。

So now given this distribution。0。05 for b equals 0 and 0。94 for equals 1， I can sample this B。

And notice that I modified x to be 11，1 now based on that sample。And intuitively。

 what's happening is that。You know，1，1，1 is much more likely than 1，0，1， so。

B gets pulled to1 because of a equals1 and C equals 1。 Now。

 this is probabilistic with 5% probability， I could have just left 1，0，1。Okay。

But it's more likely that a started with a message one and then it sort of preserved the message all along rather than a flipping to zero and then flipping back to one。

I think the most important thing is that。Basically。

 you have an assignment and you're considering one particular variable。

 and I'm going to look at different values that variable could be。

And then I evaluate the joint probability of each of those kind of possibilities。And then。

I sample according to those probabilities。Okay， so here's skip sampling in in general。

So I'm going to define the skip sampling function。 I'm going to pass in the initial assignment。

 Vrs is going to give me the variables I'm going to actually sample。😊。

Query is the same as rejection sampling where I'm interested in， let's say in A。

And a joint probability is how I've defined， how I decide to score variables。

 and I'm going to do it for one iteration。Okay。So let's do Gib sampling。 So I start out with X。Okay。

And then I'm going to track counts of the co values as as before， as in rejection sampling。

I'm going to iterate a number of iteration times。And for each variable。 So here。

 the variables I'm sampling are A And B。 Why don't I I sample。 Why don't I include C。Yeah。

 C is the evidence that's the one I'm conditioning on， so I've conditioned on c equals one。

 so I don't want to change that。Okay， so let's consider A。

 so that means I'm going to try to modify A。Okay， so what I'm doing here is I'm going to consider all possible values that a could take on。

 and for each of them， I'm going to compute the joint probability of the assignment where variable has been assigned to a。

ok。😊，So that gives me。嗯。呃。Basically 4 a， I have the joint probability of 0。08 and 032。Okay。Now。

 I compute the。The evidence， the probability， sorry， not the evidence， the probability of a， sorry。

 B and C， which is the sum of these two things。 and I normalize。

 So here I'm just normalizing the probabilities to 02 and 08。And I sample according to that。

 and in this case， I drew a one， so you， nothing， nothing changed。

And then here I'm going to record the count of the query value。

 so I look at this assignment and I see a equals1， so I'm going to write down， I saw one once。Okay。

 and then now I go to the second variable， B。And again。

 I'm going to compute the joint probabilities here。

 this is actually what we just did before in the specific example。So I normalize the probabilities。

And and I sample。And here again， I didn't change anything and then I。

Record that I saw a equals one another time。And so I keep on doing that for some number of iterations。

 And then at the end I。Keep track of the probabilities。So that's one round of Gib sampling。

So now if I run it for multiple iterations。Then what do I get？I get that。 the probability。Of。

So I'm interested in a query， which is the probability of a。Given everything is given c equals 1。

 I get that the probability of one。A equals1， given C equals 1 is estimated to be 068。

Okay and then if I compare that with rejection sampling， it's sort of in the same ballpark。

 so these are random algorithms or different algorithms。

 so we're not going to get exactly the same thing。ok。So let me actually draw a picture。

 Maybe it can can help visualize what's happening here。 So I have variables A， B and C。 So C goes1。

 So I'm not going to touch it。 Okay， so this is over time， some number of iterations。

 So I start out with 1，0，1。 Okay， and then I'm going to sample a according to some probability。

 So let's say I do I do 1，0，1。 and now I'm going sample B。 So let's。Let's do。Yeah。Let's do this。Okay。

 so I'm going to sample B。So I'm going to， let's say sample one， because remember that's more likely。

And then I go back to a and I sample， let's say I got all lucky and I get becomes a zero and I sample B。

 so that becomes。Let's say it's a one。And now sample A， maybe that becomes a。

So I sample A that becomes a， I don't know one， and then I sample B now。sorry。

I'm getting confused here。Okay。A， B， A， that shouldn't be there。嗯。😊，And this sort of continues。

 and dot dot， dot dot。 And then once how do I compute the estimate of the probability？

 So each of these columns is a sample。A joint sample。

And so what I'm going to do is now I'm going to look at。If I'm interested in。

 let's say probability of a equals one， given C equals one。

Well C equals 1 is already taken care of because I never change it。

 so I'm going to look at only the query， so I'm going to look at only these values。

And then I'm going to just count how many ones there are and the fraction of ones is not my estimated。

 So this is like the fraction。Of of once。So that's not going to be my estimate of the probability of a given c equals 1。

Sorry that must have been a mistake。So this。So I'm here I'm sampling B， so A should not change。Y。

 you're right。So each column， I'm only changing one variable at a time。Okay。

And the reason why you only change one variable because it keeps it tractable。

 because when I'm fixing everything else， I'm only looking at one variable。

 that means I can consider all the possible values of that variable and in some sense。

 I'm like bruteforcing that variable， let's see what that variable value could be。

And then I'm sampling according to that distribution。Yeah， so in the code。For every variable。

I'm considering all possible values。Right， and and so that's the same here here。 what I。

 I'm not showing the computation of the probabilities。

 I'm just saying I pick this variable and I'm gonna consider 0 here。

 I'm also gonna consider one here， and I'm gonna sample， and I happen to choose a one。Yeah。All right。

 so the running time of this algorithm is the number of variationerations。

Times the number variables because I go through all the variables per iteration。

Times the size of the domain， which is the number of values that a variable can take on。

 in this case it's two。And times the number of variables， because every time I consider a possible。

Assignment。Joint probability。Has to go through all of the variables to evaluate the joint probability。

ok。So summary。The basic formulaative algorithm is I'm going to update one variable at a time using its conditional distribution given all the other variables。

And then I'm going to compute the conditional distribution using the joint distribution。

And here I only have to sum over the domain of the variable we're sampling。喺。嗯。So。Next。

 I'm going to show you how you can make this a bit more efficient。By leveraging the property of the。

 the Beijingian network。Okay， so let's do that and that's going to introduce a new concept called the Markov blanket。

Okay， so imagine this is some arbitrary。You know， probability over five variables， ABCDV。嗯。

And if you're doing Gib sampling here， you would for every variable。

 for every value of that variable， I have to consider the whole set of variables in my entire Bayesian network。

And so can you avoid doing that and intuitively。It seems like you should。

 because only one variable is changing。 So why do other variables。Matter， maybe they don't matter。Um。

It's not going to be you know， completely， like you can't just ignore all the other variables because variables interact。

 but the these interactions are potentially local。Okay， so remember this telephone Bay network。

 So A generates B， generates C。Okay， so that's the same thing we had from before。

 So now suppose we're， we're sampling。Probability of A given B and C。Okay。

 so what we would normally do is we're going to look at the joint distribution of both a equals 0 and a equals 1。

So I'm considering what what should a be， so I'm going to consider both all the values。

 a equals 0 and equals 1。And I fill in my current assignment for all the other variables。

And this is just， you know， just by the definition of the Bayesian network。

 the probability of a given B given A times C given B。So when I compute the probability。

 I also have to normalize， so I sum these two numbers and I get a probability of B equals B and c equals C。

 and then I divide each of these quantities by this normalizer and I sample from that。Okay。

 so that's what we did normally。But。There's something that we might notice about this expression that could allow us to save some work。

So if you look at this expression。You know， I care about basically what's happening to A。

 So a is changing either 0，1。But if you look at this last factor here。It doesn't depend on A。Okay。

 so it's just some number。And in particular， this is this number that gets multiplied by this a equals 0 and if a equals 1。

 it's the same number， and in the denominator， I'm going to also have the same number。

 so I'm basically multiplying and dividing by the same number and you can of sort of see that if this is 0。

1 versus 0。2， it doesn't really matter。So therefore， I can just drop that completely。

And I can just ignore it。Okay。So， in general。There's a question of which variables can you drop and which ones you can't？

And there's a kind of very nice way to think about that。

 so we need to only include variables that touch the variable we're sampling。

 that interact with it directly。Okay， so B is connected to A。So therefore， I can't drop。

YouI can't drop this factor。嗯。But C is not connected to A so I can drop it。

And so the set of variables that I need to。You consider it's called the Markov blanket。

And the Markov blanket of a variable is in a Bay network is simply all its children and its parents。

So let me draw this visually。So in general， you have a variable。

 let's say you're sampling and has a number of parents。Yes。And maybe these have other parents。

 maybe this is like really complicated。And maybe this is， it could be kind of as odd as as a dag。

 it's fine right， so I'm just going to draw some stuff and suppose I'm interested in this node。

 what is the Markov you know the Markov blanket。Of， of this node， of。Of。You know， this node is。

All its children， so this is， these notes are in the Markov blanket and all its parents。Okay。

So these are all the local conditional distributions that touch depend on this value。

So this is not in a Markup blanket， this is not in a Markup blanket， this is not either。Okay。

 so when I compute the joint you can imagine just writing down the joint。

 remember a local conditional distribution for every variable。

 so I have this condition on its parents and then have this condition on its parents。

 which includes this， this condition on its parents， this condition on its parents。

And then everything else doesn't depend on the orange node。So the question is。

 do you have to include coherence， So for example， do you have to include。

 let's say this is just to make it more interesting， let's say this depends on that。

So the answer is yes， because if you think about， let's just label this。X， Y， Z。

 So this factor is going， this conditional distribution is y given x him z。Okay。

 so this acts as a unit， the parents always act as a unit。 So if you're changing this。

 you have to depend on the value of Z to determine what the probability of y is。有。Okay， so for this。

Just for maybe a simpler example。对。So let's do this example， Okay， so what's a Markov blanket of a？

Should be B。Whats a Markov blanket of B。A and C， And what about C？Okay， so think。We're good。Okay， so。

So then what it means is that instead of computing the joint probability。Over the entire assignment。

 what we're going to do is only include the terms that are in the markup blanket。

 so for this particular three variable network。What it looks like is the following。

So I have a joint assignment X， and I updated this variable with this value， and if it's a。

I just have to include A and B， given A。I don't have to look at C given B。嗯。

And if it's a variable equals B。I only have to look at B given A and C given B。

And I don't look at probability of A。Okay， so if I run Gib sampling。

Using passing in this function to evaluate the probe， basically a score for every assignment。Then。

 I get。This， this quantity。Okay， which is similar to what I had before。But this is a lot faster。

Actually， this should compute exactly the same answer as G sampling with joint probability up to like floating point precision。

Okay， and there's a speed up here。Because， instead of。Considering the total number of variables。

For evaluating this probability of an assignment， I only have to consider the size of the Markov blanket for evaluating the cost of this particular assignment。

So this I would say is an optimization， it doesn't resolve any sort of fundamental issues with Gi sampling。

 but it's just like， why not do it？Okay， so the quick summary here is that the Markov blanket of a node is all its children and parents。

Gif sampling requires the conditional probabilities of the node。And it's Markup blanket。

 so any local conditional distribution that touches the node and its Markup blanket。And this is。

Much more efficient if the Markov blankets are small。So if the Markov blankets are large。

 if you have a node that's connected to many， many nodes and it doesn't really save you very much。

 but it doesn't hurt either。Okay， let's move on。 So now let's apply give sampling to this alarm network。

 which we are familiar with。 So remember， we have burglary earthquake giving you rise to alarm。

 So here is the。The probability tables。嗯。We're going to initialize with an arbitrary sample that's satisfied the evidence。

 so assuming there's a burglary surgeon everything bad happens。And then let's look at。嗯。

We're interested， let's say， in burglary， given the evidence。嗯。So which is a equals1。

And I'm going to see what happens if I run Gib sampling？Okay。So if I run Gib sampling here。

 I get probability of B equals 1， given equals 1 is 0。6。So if you guys remember。

 that's not exactly the correct answer， it not it was more like 0。51。If you run it again for 200。

 that's 0。33 now。So you might wonder， this is kind of not working super well。

mSo let's try to understand why。And so as I mentioned before。

 the sampling algorithms are just approximate and your mileage is going to vary depending on what situation you're in so it's very important before you try one of these algorithms to be attentive to when it's going to work and when it's not。

Okay， and by the way， I'm also going to talk about when rejection sampling works and when it doesn't。

Okay， so let's actually start with rejection sampling because I think it's， I've already said this。

 but just to put it in concrete terms。When is it hard for rejection sampling？

And the answer is when the evidence has low probability。

RightBecause you're going to reject most of the things。

 the number of samples that you actually keep is。Basically， the minus probability of。

 the probability of evidence。So if the evidence is low probability。

 that means you're going to have very few samples to work with， possibly zero even。Okay。

 so here is an example where it's， its sort of telephone， except for the probability of。

I was actually sorry。 It's not telephone。 Here's the， there's the problem。 So if it's a one。

 its the probability of a0 is very high。 So if a is 0， B is 0 with 0。999， if a is 1， B is 0 with 0。

9998。Okay， so if you look at the joint distribution here， the probability of B equals one。

Is going to be quite small。But what I'm interested in is probability of a given B equals1。

And intuitively， if you think about a PVP of a given bes1， and you're taking these two rows。

 and it should be two third， so the ratio between these is two over three。嗯。But。You know。

 you need to reject all the samples that don't match the evidence。

 So if you were to do rejection sampling， you would get basically， you would reject。

Like you would only keep one out of 10，000 samples。So it is a very inefficient way of sampling。

And it would probably take like 100，000 or even more samples to get a fine estimate。

But if you do Gib sampling。This is totally fine。RightBecause what Gib sampling says is I'm going to condition on b equals1。

 so immediately I restrict to these only these two rows and I normalize and then I can， in fact。

 Gib sampling will just give you the exact answer every time。Okay， so what about the other way。

 so what examples are hard for Gib sampling？And the answer is when the variables are highly correlated。

So let's take another example here， so two variables， A and B。A is 0。5 probability on 0 and1。

 and here。B equalゼ。So probability 1， A and B are the same。Okay。

 so now let's say I wanted to do Gib sampling and I just want to compute the probability of a。Okay。

 just question， what's the probability of A？So it should be 50，50， right？

Okay so here I'm not there's nothing I'm in condition on， there's no evidence here。

So rejection sampling will get nail this because it generates from scratch every time and works perfectly。

 there's no rejection because there's no condition。Okay。

 so it's going to have no problem detecting that P of A is。Is 0。5。

But what happens with Gib sampling now。Gip sampling will get stuck。Okay。

 and the reason it will get stuck is that。Let's say I start out with0， zero。Okay， so now I sample。

 try to sample A。And what happens when I try to sample A？Well， I can come over here and I look at。

 okay， B is0 and we're going to consider possible values of a it could be zero or1。 Well。

 if that's one oops， that has zero probability。So therefore， I have to choose zero。And therefore。

 and same with B， if I try to sample B， it always six the same。

 so basically sip sampling will get stuck completely in 00 and not be able to move。

And the estimated probability of a is going to be probability1 on zero。

 which is the incorrect answer。So this is an instance where A and B are as correlated as possible here。

 they're identical。And。And in that case， because G sampling is just。

Trying to change one of the variables。Then you can't do it because the other one needs to change as well。

's I don't know， it's kind of like doing a threelegged race with someone you're like attach to them and like you can't really move until until the other person moves And even if this weren't exactly identical。

 if this were 0。9999， that would also be pretty bad because then it would be very unlikely for gi sampling to change into a different variable。

Okay， so we saw kind of sort of complementary examples which are bad for Gib sampling and。

Rejection sampling， so rejection sampling。Rare events are hard。And for gib sampling。

 highly correlated variables are hard。And the bad news is that in most real world problems。

 both are true， so it's going to be hard for both keep sampling and rejection sampling。

 but it's helpful to know the reasons why a problem is hard。So a few remarks here， so Gib sampling。

 as I mentioned， is an example of a MCMC algorithm。

 there's a more general MCMC algorithm called Metropolis Hastings。

 which uses a proposal distribution to more smartly guide the search and there's actually some really beautiful theory around Markov chains and analyzing how fast they run and has to do with this thing called mixing times in practice Gib sampling is fairly commonly used because it's fairly simple and effective。

 the only simpler thing is rejection sampling which generally doesn't get used because the probability of hitting the evidence is generally pretty low but Gib sampling can also be quite slow。

So now I'm going to switch gears and talk about conditional independence。

 So this is going to be kind of different。 So so far what we've done is we focus on probabilistic inference algorithms in Bay networks。

And they've been mostly agnostic to the structure of the Beijing network， right？

 So you in rejection sampling， you just。You know， sample all the variables and then you reject。

 it doesn't matter what depends on what。Now with Gi sampling。

 we paid attention to the structure a little bit， we define the Markup blankets。

 so when you're computing the probability of a variable， you're looking at the things around it。

But there's some really interesting deeper structures in Bay networks。

 so let's try to explore them a bit。In a particular。You。

 a Bayian network is simultaneously a probabilistic object。

 It is a distribution over a bunch of variables， and it is also a combatorial object。 It's a graph。

And there's a connection between the graph properties and the probability properties。

 in particular when we talk about independence。Okay。

 so hopefully you guys have seen independence from your probability class， but just to review it。

Two variables， random variables are independent， if and only if you look at the probability of A and B。

 that's the same as the probability of a times the probability of B for all possible values of A and B。

Okay so that's the definition， so let's look at some examples where A of B corresponds to variables in Bay networks。

Okay， so example one。So。I'm going to try to do some of these on the board， actually， Okay。

 so this is the。World's second simplest Bayesian network， the simplest one is， I guess， one variable。

And so this corresponds to the joint probability， just P of a times P of V。And in this one。

A and B are independent。Just almost like if you pattern match。

 that's exactly the definition of independence。Okay。And。Notably， AM B are not connected。Okay。

 so independence。Corresponds to。In this case， to two nodes which are disconnected。

 So if you see Bayesian networks where you have two variables that are not connected。

 then you can reasonably say that they're independent。 Now。

 we'll see later it gets a little bit more complicated， but in this case。

 that's the generally the right intuition you should have。Okay， so what about if I put it？

A between them。So that means the probability of A and B is probability A times probability B given A。

And in this case， A and B are not independent。Because a B here depends on A in some way。Okay。

And here they are connected， so they， I mean， just intuitively。

 they're kind of connected and depend on each other。Okay。So now let's look at a different。Graph here。

So let me just ask a question。R A and B。 So this is the independent symbol。AM B independent here。

Okay， so let's just try to figure this out。Let's look at the joint distribution。Over A B and C。

 that's the product of local conditional distributions。

 And I'm going to look at probability of A and B。That that's the marginal here。

 and that's the summation over C over the joint and then write it out summation of C over the local conditional distributions。

And notice that。I can move this summation over sea over to this side。And that gives me。1。Okay。

 let me let me just make sure this is an important point。

 So I want to make sure that so summation oversea of probability of。A， probably of B。

 probably of C given A and B。So this is equal to probability of a times probability of B times the summation over C probability of C given A and B。

And whenever you sum a local conditional distribution over all the values on the left hand side。

 what do you get？What is this value？This is equal to  one， right？So therefore。

 this is just probably of A and B。Okay， so therefore， A and B are actually independent。

So this is part that's a little bit tricky about Beijing networks。

 so you can't just only look at whether two variables are connected or not。嗯。

But this is just the only real special case that you have to think about。Okay， so intuitively。

We already actually saw this before， right？So we had burglary an earthquake and alarm。

 and we said that burglary and earthquake are independent。A。

And it just happened that there's stuff that could depend on both， right。

 so you can have two independent things。And then someone creates a variable that depends on those things。

 it doesn't， it shouldn't change anything about the underlying causes independence。ok。

So mathematically， you can see it this way， but intuitively you can see why it might be true。Okay。

 so that that's an important case。So let me just just write it a。So。Yes， okay。Okay。

 so here is another case， so C and A and B。Okay， so。Our。A and B independent。

How many of you think yes？How do you say no。Okay， the answer is no， right， So don't be fooled。

 It looks kind of like that。 If you're looking at upside down， then they look the same。

 but the direction matters。And in particular， these things visually look very similar。

 but they're like almost completely different Bayian networks， right。

 This one in particular has C given A and B， and this has C probability of A given C times probably B given C。

So the directionality matters。And so if you look at the joint distribution。Probably of C， A given C。

 B times B， B given C。 And if you look at the probability， joint probability of A and B。

 that's equal to summation over C times probability of C。 I mean， it's just kind of like a mess。

 There's no way to simplify that。 So they're not independent in general。

And sometimes it can be useful to think about， if you see a structure。

 just think about special cases in your head。For example， I can say， well。

 C is a coin flip and a equals C and B equals C。And clearly， they're not independent。

Because a can be lital equal to B。Okay， so you can somehow work out these some simple examples in your head。

To kind of convince yourself when things might not be independent。Okay， so that's independent。

 So this is definitely no。 So let's look at conditional independence now。Okay。

 so this is also a familiar concept from probability。And we say that two variables。

 A And B are conditionally independent， given C equals some particular value if。Basically。

When you it's the same thing except where you condition on C in all the different terms。Okay。

 so let's look at some examples， so let's revisit this example here in example four。

 So the question is。Is A and B given C， are they A and B conditionally independent given C？Okay。

 so here let's look at the math。Joint distribution。 sorry， this is the conditional distribution。

And this is simply equal to the joint。Divided by probability of C。

 and that's equal to probability of a given C times B equals given C。Which is。

Literally the definition of conditional independent。Okay， so here。

 A and B are conditionally independent given C。Okay， and intuitively， you can think about it as。

Let's say there's a coin flip and then A does some stuff and then B does some stuff。

 and they only depend on that coin flip。 So condition on knowing the coin flip。

 then A and B are doing sort of different independent things。Okay， so now。Let's revisit example 3。

So here I want to ask the question。Are A and B。Independent， given C。Yeah。Okay， so remember。

 A And B are independent。 What about given C， How many of you think there is still independent。

And they're not independent。Okay， so now hopefully you anchor to the burglar alarm earthquake example。

 and you see in math。That。Well， this whole thing is just kind of a mess。

 you see that C and A and B are all combined in this arbitrary function here。

 so it definitely is not the case that A and B are conditionally independent given C。Okay， so these。

 so this is a no。Okay。So these two are examples you should kind of like， you know。

 really remember in your head because theres are like very similar。 but yet they follow different。

 follow differently。 So in the above， A And B are marginally。Independent。

 but conditionally not independent， where it's the opposite here。

 A and B are marginally not independent。 But when you condition on C， they become independent。Okay。

 so this is a good primitive to have in your head when you're trying to reason about these things。

Okay， so let's now go to the alarm example。 hopefully this should be old news by now。

 So here B and E are independent。But B and E are not conditionally independent given a equals1。

 which is how you get explaining a way which we saw in last lecture。Okay， so in general。

How do you tell if I just give you a huge visual network， and there are some variables。

Here' is a general。Alre다。Okay， so A and B， are they independent given C First。

 you shaden the variable of C。So you can think about these as when you condition on something。

 it's kind of like blocking a path。Okay， that's intuition。

 you recursively remove any non shaded leaves。So this is to deal with the fact that A and B are really independent。

 but there's something here that makes it look like it's not independent。

So you just kind of remove that， this is just， I mean。

 you don't have to literally remove it from the picture， but in your head。

 usually think about it not being there。Now you connect the parents to each other。

 you can think about remembering it as like marrying the parents。And then finally。

 the answer is return whether there's a path from A to B that doesn't go through any shaded notes。

Okay， so let me do a a quick example here。 So I have this medical diagnosis example from。

From last time， so we have cold allergies， cough。And itchy eyes， okay？

So I can go through a bunch of examples。So are C and A independent？And the answer is yes， because。

This is a condition， there's nothing to condition on。

 I can essentially remove this and remove that because they're unshaded no leaves and then I'm just left with CNA and there is no path that goes between them。

 so they're independent。What about C I。cn i。Okay， again， I can， I， I can't remove this。

 I can remove H。Because H is a leaf that's not shaded。

 and then I get basically C and this subgraph A and I， and there's no path between them。

 and therefore they're independent。So I've given a equals 1 or a equals 0， whatever。So if I say that。

And I'm asking， are these independent or not？These are independent。

Because there's no path that goes like this is essentially blocking off the way to go over there and。

You know， similarly， if I H if I shade H， then these two are also kind of blocked off。Okay， so。

 maybe we'll do more of these examples next time。But hopefully that's just a taste of how you think about conditional independence in the context of Bay networks。

So just a summary。So we talk about probabilistic inference。

 the ability to answer queries on this database Bayian network。

And we can do exact probabilistic inference， we just form the distribution。

 joint distribution and we can marginalize and we can condition this is exact， but its complexity。

 can be exponential in the size of the number of nodes in the Bayesian network Then we look at two approximateian a probabilistic inference method。

 rejection sampling， G sampling。 remember they have kind of complementary strengths and weaknesses。

And then finally， we started looking at conditional independence。

 which assesses whether two variables are independent given evidence and we're essentially able to reduce that to sort graph properties。

 are these two variables connected after a bunch of processing on the graph。Okay。

 so next time we here so far we've just assumed that the Bayesian network has given and we're answering questions Next time we're going to talk about how you actually learn the parameters of the Bayesian network。

 how do you get these probability tables。

![](img/a937d8a29715cb4f318cca2ad69bd18a_3.png)