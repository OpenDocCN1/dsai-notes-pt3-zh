# UBC《机器学习和数据挖掘｜CPSC 340 Machine Learning and Data Mining 2012》中英字幕 p24 -24-undergraduate machine learning 24_ Text classification with Naive Bayes.zh_e -BV1pJ2ABFEFg_p24-

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_0.png)

The first thing was a generalizationization of the Beta Bnoulli model。

 and this is a generalization that allows us to deal with more than just two classes。So they个。

We can do hate classes。For a dye， for example， you would makeup。Can you tune your my going on？

Thank you。How's that。Thanks。So。When we have multiple classes， say K classes。

 the extension of the Bernoulli is this distribution that I call the categorical distribution。

 which is essentially。This guy over here。That's the categorical distribution。

And the natural extension to vectors of the。With more values of the beta distribution is what we call the deishlet distribution。

And we learned that if we multiply deishchlet distribution times a categorical distribution and normalize。

 we get a derichle distribution。Thereish lived prior。Categorical likelihood， British lip posteria。

Now， if you're dealing with words， words are essentially counts。

When we deal with text we always think of what words have occurred in a document。

 so essentially we're accounting， we're dealing with coins basically except that we have many coins。

 one coin for each word is this word present or not and the same is when when we deal with bioinformatics and we need to deal with DNA。

 where we're looking at do we have an A， do we have a D， we have a T， which DNA basis。

 are we dealing with here so this type of models extremely useful in bioinformatics and extremely useful for web information mining。

Text， analytics， and a like， any sort of discrete quantities。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_2.png)

嗯。We began with an example， and this example was the one of tweets。 And so what we wanted to。

 what we want to do is a tweet classifier。 We want to say whether a tweet is positive or negative。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_4.png)

And so we decided that the way we were going to code the input is just as a vector x。

 And this vector has a one if the word appears。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_6.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_7.png)

In the corresponding component， and it will have a zero otherwise。

 So this vector will tend to be mostly zeros and will have， say。

I don't know how many words typically appear in a tweet， maybe five to 10。Onces in the vector， Okay。

 so it's a various parts vector， you just basically store the positions of the ones。

And then we might want to classify the switch into two classes， positive or negative。

 or three classes， positive， negative neutral， or any other number of classes that you might want to choose。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_9.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_10.png)

Positive negative is easy because one way to get labeled data from Twitter and there's many ways。

 but one possible hack is you look for all the tweets that have a happy face and you call them positive and you look for all the tweets that have an unhappy face and you call them negative。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_12.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_13.png)

Of course。In those there will be mistakes because you sarcas and so on。

 but fortunately by popularity， you know with high probability。

 most of the tweets with happy faces will be happy。 And so in the end when we build our classifier。

 there's going to be mistakes in the data。There are very good techniques to deal with these mistakes in the data。

 which what we call out liars， but I'm not going to cover them in this course。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_15.png)

I'm happy to talk to you after。But it will turn out that even if we allow for a certain margin of error。

 we're already able to actually come up with very good classifiers。In fact。

 theres particular site called Senment 1，40， which you can。

You can go to this site and you can type any term。And you so the way it works is like you go to decide site you type Obama。

 it then extracts a bunch of older recent tweets about Obama。

 and then it applies the classifier to each tweet。So it's just prediction。

 So you're first training in a million tweets。 then for any query。

 you just basically predict what each tweet is in terms of how whether it's positive or negative。

 and then you just count the number of positive tweets about Obama， the number of negatives。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_17.png)

And。And that's pretty much what you see there in those two bars。So when I did this two days ago。

 the sentiment in Twitter for Obama before the election was quite positive。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_19.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_20.png)

嗯。I'mFairly sure you could have used this to predict the result of the election。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_22.png)

嗯。发的。Yeah， the positive might be higher now。The important thing though is like with statistical analysis。

 actually， if you look at a lot of indicators out there。

 and this actually I might as well use the election to preach on something。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_24.png)

If you looked at all the economic indicators a few days before the election。

 it was you could make a fairly reasonable forecast of what the outcome was going to be。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_26.png)

And then there were the so called pundits， and so in particular I recommend a blog by a guy called Nate Silver in The New York Times。

ho did some statistical analysis based on historical data。

 and if the historical data is to be believed， if it's good data。

 then you can make some good forecasts。They will not be 100% accurate because we have learned one thing。

 probably is important， the world's very uncertain， you don't measure everything。

But it's certainly better than just saying this guy will win because he happens to。

 I can see the glimmer in his eye。It might be that if you do a proper analysis with La Su。

 the one variable is the glimmer in the eye， but at least you've done that analysis。Okay so。

So statistics is very useful， and indeed， it's even in。You know。

 thingss like this election that played a big important role。

Like I believe that both parties were getting all the census data of U citizens and using that data to actually forecast how they were going to vote。

 and then they would only。Because if you know the people that would vote for you。

 you approach them to ask them to vote if they haven't voted。

 You don't approach the people of the other party and ask them to vote。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_28.png)

All right。Now。In order to make a classification， we're going to go from。

A prior probability of a classes。So two things with the current representation of。

 one that it's not considering the frequency of the terms。How many times is a particular world。

That's correct。So yeah， that's a very good point。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_30.png)

Here if someone says like， Obama， ob， Obamaama， Obama。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_32.png)

Its all you get is a one Obama， okay， so you don't get a frequency of three。So if we make。

 instead of having multiated or only， if you have multid。Cateorical， that's correct。

No one can do that。 They actually work about the same in practice。

 so this book actually discusses that particular topic。Compverse different models。

We could do the na class with that model。 I could take that route。

 and it would be very similar the derivation and so on。Like performance ways。Not really。

This actually works pretty well this binary well。Like the issue which I see is that if you use nab for a text document。

 it's okay， but since that wheels are so small。The frequency and the order in which words are good。

 right， There are several arguments。 I'm not going to have time to go into them， but I will。

Discuss this with you at the end。 There's arguments in favor and against using this model versus as a multinoial model。

Let's talk about it。I first want to do one before we start discussing all the possibilities of what other models we could do。

No， it's a good point。十岁时。I' pick one randomly or。That's a detail of how you construct your data。

I don't know， big one randomly or。Or construct to。At that stage。

 you might even consider not using that data point because that data point is probably just going to add noise to your data。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_34.png)

There's a way of also making the data cleaner is we have lists of like 8000 words。

4000 of which are the words that tend to be positive， like extraordinary， fantastic， awesome。

 so cool。😊，OM G， Xlam mark， and so on， and we also have words that are negative。

 and then you could use that to just sort of。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_36.png)

Protect you a bit against sarcasm and so on to improve the quality of the data。 but ultimately。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_38.png)

What we need to do here is a robust analysis， which is we need to have techniques that are robust with respect to ourliers。

 I have not talked about that topic yet so。For now， let's assume that someone gave us data。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_40.png)

Of happy faces and sad faces， and that's the data we have to work with。And just with that data。

 I can tell you， you can build something like this， which is pretty good。 So we will get it wrong。

The tweak here is that in how many tweets did this retrieve， this retrieved about 40， say 60 tweets。

And it probably got it wrong。In10 of those。But the main thing is if the signal is very obvious。

 if you get it wrong， even if you have the prediction wrong in a few tweets。

It doesn't matter because you want to predict the sentiment about Obama and you have lots of tweets about Obama to make that prediction。

 So if you get it， you're not trying to predict。Your interest is not in a single tweet。

 your interest is in an aggregate， so even if you make a few mistakes when you average。

Those mistakes will hurt you less。 It will still affect the index。 You， of course， want0 mistakes。

 but。嗯。One thing I'm hoping to start getting from this course is getting zero mistakes is impossible in most applications。

现到为什。Yeah， you collect more data of happy faces and sad faces， and that's your test set。

But there's no way to like say this prediction。Well you do get it。

 you build more data sets with H and you see how well the model that you learn in the training data is able to predict the test set。

And you adjust your regularization coefficients and so on， and then you eventually。

Take yet another data set and make sure that you've got the data model。

And ultimately you create a product like this and you put it out there online。诶。

If it's a good product， people will use it。I think that's eventually the usability test。

 whether you've done something useful Well like for something like this， we don't have any user。Okay。

 there's no feedback。 Oh true。 That's a good point。 So if I was designing this website。

 I would probably have put a button there that would say agreed disagree。 this decision。So。

 there you go。This was a cut paste。And that sort of feedback would help you improve because then you get labeled data。

 But of course， the moment you put buttons agree， disagree， trust me。

 there's going to be a million spammers and a million。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_42.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_43.png)

People that just for the fun of it will try to break your system。So therell be more people like that？

It's no。Whenever you build a website， a product。The first thing you need to do is be protected against maliciaious。

Attacks。That's essential。They happen the first day you become popular。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_45.png)

And if you're building a search engine， the first thing you need to deal with is spa and pornography。

I deal。Allright， so。呃。We're going to stick with this idea that we're going to have。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_47.png)

The axis are going to be model is going to be a vectors one and zeros。

 each entry of that vector x is a coin flip。 it's either1 or0， so it's a beerulli variable。

 and we're going to assume that those words are independent。 That's a na based assumption that。

That's why it's called naive， because we're just assuming all of those words to be independent。

 So we have， in this case， small D， independent binary variables。 Okay， so small D is the number of。

Distct words。N is the number of tweets， the number of data。It's important to keep this in mind。

 and C will be the number of classes。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_49.png)

Okay。So what we want to do then is we start is we want to derive posteror this quantity here。

 which is the posterior probability of the class。Given as input， the tweet X。

What's the probability of why ranges of a positive and negative is binary？

And then access that vector of many small deep beoni variables。A priority。

 and then we can just simply apply here。We can factorize this as a joint divided by a marginal or apply base rules effectively。

And the。We have this quantity P of Y I given pi， which is the prior probability of each class。

 so a priority， how positive， what's your prior positiveness and what's your prior negativeness。

Of tweets。And I will model that prior with a deish layer， sorry。

There'll be traditionally prior in this prior， but at the prior itself。

This P of YI given pi is a categorical distribution。So the probability that you are of class C。

In our case， we have。Cital C。Its 2。And then for c equal1， and we are positive。Tweets。

And then for SQL 2， we have negative tweets。And so we said that the probability of you being in class C is just pisC。

And so if you have a multinomial， this just is a summary of this。tweets anymore。 Part it。

 Are we not allowing neutral tweets A glass class you talk about allowing tweets that are neutral。

Yeah， I deleted Netro for first simplicity， in essence we're back to yeah let'。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_51.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_52.png)

This was an example。 let's now assume that c equal to in this example， positive connect。

The other thing is this factor， I is the index of a tweet。So for the I tweet。

 we have D word possible words。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_54.png)

So。The ice tweet。The prior probability of the words in the I tweet is going to be a product over all distinct words in the dictionary。

Of the probability of that variable。So we was just saying it's n sorry。

 small D independent beernoi variables。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_56.png)

And each of these guys will be verly。F。And then what we hope is for different classes we will have different Bernoulli variables。

 so these might be over here， this is for class y equal1。And this is for class y equal to。

 and so you might have different coin being tossed with different frequency for different classes and that's what's going to allow us to separate So in some classes you'll see more words like Viaggra and special and for other words you'll see other words like midterm homework。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_58.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_59.png)

And so on。 And that's what's going to allow us to separate say spam from。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_61.png)

This， by the way， is how you build a spam classifier tube na base the typical。

Easy way to build a spam pifier。All right， so lastly。So I wrote the full expression for the model。

 so and I promised that I was going to parse it。 so we know that P of y。Given pi。

It's equal to the product over the data。The product。Over from one to end， the product over。

Cllas of pi C。Os。I see， to the power。Ycy。And this is just basically saying equivalently that the probability of Yi being equal to C even pi is what I'm calling pi C。

Because when Yi happens to be equal to C。It will be equal to C， it will not be equal to any other。

If y is equal to 2， it will not be equal to1， and so this indicator， just like for the Bernoulli。

 will only choose one of the pis or components。And we assuming that we have。See independent ones。

See independent classes and we're assuming that the data are independent。

 so each tweet is independent of other tweets。Which is also， again， a stark assumption。

 because tweets often。The tweets that you see coming one after the other。

 do you have a certain dependency， But we will we will throw away all these。Complications。

 and we'll assume that everything is nicely independent。Finally。

 I'm going to say that the probability。Of X Ij。Given。

Given the fact that class the I tweet is of class C。And given its parameters。

It's going to be a beernoulli variable， and if it's a beernoulli variable。

 it's going to have beta sky。So it will have theta JC， which is the probability of X。

J being equal to1。And that happens。When why I。Is equal to p of class C。And。X Ij is one。

And then the probability of failure。Why I still love class C。But XIj is of plus。0。

Okay so we're saying we have。Given that you're in a particular class。

 so we've selected y equal to C to indicate we are now in class C。

So that's why we need to put our indicator in both terms。But given it， we are in class C。

Assuming we are in class C。We could still， the word could be on or off。

 the word Viagra could be on or off， and so we need we have a Bernoulli mo。

aheadJust explain what the J index is for again。Sure。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_63.png)

So。We have a vector x。So a tweet will be a vector of。Words。

 it's a vector that just basically has a one if a word occurs in a zero otherwise。

 and each position indicates a particular word。And this goes from I equal1 to1，2，3，4，5，6，7，8。呃。

All the way up to I equal D。Which in this case is8。 So it's a number of components of the vector Xi。

Each entry of the vector X I is benoulli。You mean Jay， right？Oh， yes。 thank you， sorry。Thank you。

J is the index from one to two。And that for the ice tweet。 and then for the ice tweet。

 I also have that Yi is equal to。诶。One or two。In other words。Class one or class two。

Instead of saying class1， class two， I just say class C in order to make the derivativerivation generic。

Okay， so I is the index of the data， I goes from one to n。J is the index of a word features。

 it goes from one to D。And C is the index of a classes， it goes from1 to capital C。

 and for the positive negative capital C is 2。Okay。And so we have N observations， IID。

 so we take the product of our N。And since we have C classes。

 we use a categorical distribution for C classes， so in other words。

 we're bin into class one or class two。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_65.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_66.png)

I could have used a Bernoulli model here because we only have two classes and that would have simplified it。

 but I'm doing something more general because if I to more ask you to do your homework。

 implement it for three classes。Including neutral， then you would know how to do it。

You would go from one to three， in that case， capital C would be3。

And then we have this quantity theta JC。Which is just a probability。

That the J element of the vector Xi is on。When you are in class C， that's what the subinex indicates。

So theta JC is just a probability that in。The positive class， the word fabulous。Appears。

And each class will have a different distribution。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_68.png)

So each of these guys is essentially。Like each of these lines is basically your feet。No Ij。

Sorry Theta J。When。C equal one。And this will be。A particular theta J。When C is equal to。

For class two， y equal equal to two。So for each class you have many of these theaters。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_70.png)

And in particular， you have D of these thes。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_72.png)

Because there are D words， each word gets its own theta。

 each word has a success probability of being on or off。

And what's going to allow us to separate one class from another one is that these classes。

 when you consider all the words， that will have different distributions。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_74.png)

Pam tends to have words like Viaggra and great offer， super deal， et cetera， whereas normal male。

 I guess like a professor will have things like a deadline assignment and so on。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_76.png)

So thetheta JCs， are they determined by a maximum likelihood estimate。

 are they too determined by bayesiness， we're about to derive that？Once we。

 you know the tricky thing here with these models is to just keep track of the three indices and to know。

What are we doing， how are we binning everything？

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_78.png)

Oncet we know that， this is essentially like Bnoulli models。

Once we know that doing maximum likelihood， this is actually quite easy。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_80.png)

And we'll get to it。So in particular， I'm going to do the following thing。I'm going to define。

 So n is the number of data points。 I'm going to introduce here two more indices to two more summaries。

One is going to be the number of points of class C。In other words。

 the number of positive tweets and the number of negative tweets。

So N C is just a sum over all the tweets and you count how many times y was of class C。

We're also going to count the number of times the tweets were of class C and a particular word was on。

So how many times did the word Viagra occur in the positive class and how many times did the word Vigra occur in the negative class？



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_82.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_83.png)

That's NJC。Now， if you wanted to guess pi C。Which is just a probability。That you will be of class C。

what do you think would be The probability or tweet will be positive or negative。

 What would be sort of an estimate for it。Exact。You would expect this to be N C divided by N。

You know， let's just use our intuition。 the number of tweets positive will be the total number of tweets。

I guess I was using a small end for that， so let me make sure。Likewise， given that you're in class C。

What do you think is a good estimate for the probability of a word being on？And。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_85.png)

Number of times the word J appears in class C， divided by the number of times words are number of tweets in class C。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_87.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_88.png)

We will derive these， but first I wanted to start with some intuition。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_90.png)

If we want to make predictions， let's assume we've got these estimates。Once you have this estimates。

 you're done。And this will be the maximum likelihood estimates， by the way。

 sort of ruined the surprise。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_92.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_93.png)

Then when you want to do a prediction， you use precisely the model that we wrote。 So our model is。

This product of these picess and then these small D Bernoulli variables。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_95.png)

And that's precisely what I'm going to do。 So given a new data point X star。

The way I'm going to predict if it's of class C， whether it's positive or negative。

 is I'm just going to multiply the prior。Of the class。Times。You know， personallyly。

For each of the deep components of that vector x star。 So I evaluate the model。

And I only need to evaluate it up to proportionality。

Right because I only have two classes positive and negative， so I compute each。

 and then I just divide by their sum。And that gives me the probability that the tweet is positive and the probability that the tweet is negative。

 and that's how we're going to do predictions， we're going to have probabilistic predictions on these tweets。

So it's just evaluating them all。This expression here is the same as expression I had before。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_97.png)

I'm just now going to assume I am of class， so I set this to one。

 and then I just have the estimate theta JC to the power of。嗯。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_99.png)

Whether the word is on or off， So it's just evaluating the probability of a pernolet distribution。

That gives us a prediction and we're done。That's how we make protection。

So that search engine that I showed to you， every time you type a word。

 it applies this equation to each of those tweets。And then it sums the number of positive or the number of the negatives。

 or maybe it sums the total probability and the total negative probability。

And that's how you get a sentiment of the tweets。Of course， you could do this。

 This is actually quite useful because if you're in market research and you launch a new product。

 you want to know how people are talking about your product in Twitter。You would want to do this。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_101.png)

The algorithm。That's simple。RightBecause all we have to do is comes。

So we just loop and we count a number of times。You estimate basically pi C and theta JC。

 which are just counts。So I'll let you at home passse the algorithm。

 in fact I'm going to ask you to implement this。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_103.png)

There's only one warning。I'm multiplying。Many probabilities now probabilities are numbers between0 and 1。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_105.png)

When we deal with millions of tweets。And。Possibly millions of words。

You're going to be multiplying millions of small numbers。Now， computers are not analog。

 at least not the ones that we use mostly。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_107.png)

And because of that， when you multiply many small numbers。You're going to get zero。

And that's because the machines are rounding off。They're going through under flow。

This is a problem when you invert matrices as well a few people during the exam actually asked me what is numerical stability well often if you don't add that small rich element to the diagonal。

 what happens is the numbers are very small and they're small below machine precision so you put a zero in the matrix as one of diigenvalues and if you try to invert one divided by zero。

 you get infinity and the wave machines often react to that as they stop working。They hang out。

 or some will gracefully give you a message not to do something stupid。嗯。

But numerical precision is something we need to contend with。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_109.png)

I'm not going to go through the details of this。And I'm going to let the TAs teach you this trick。

But if you have， let me give you just the intuition here as an example。

If you have to take the log of the sum of two very tiny numbers。In other words。

 you're multiplying two tiny numbers。So if you're multiplying two tiny numbers you。

You exponishate them so you can factor them out and then you take the log because the log is in up there。

Exponentiation property， so you still have the right thing。But what you can do instead。

 is you can write it in log E。For。You're then。Take the common factor。

And then you take the log of that common factor out。

And now you just need to deal with exponentiating like bigger terms each of this year， which is one。

 e to the minus1， which is one over 2。7。So it's a very useful trick to deal with underflow。

I don't want to go over these tedious details on how you do it。

 there's code here in the slide which will be available to you as to how you would implement a trick This here is called the log。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_111.png)

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_112.png)

Some。X。Function。And then。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_114.png)

The code is there to tell you how to do it。 The Ts will help you with that so that you can finish your homework。

 If you don't do this trick。It will not work， your code will not handle the we're going to give you a million tweets for you to train this。

 and if you don't do that smartly， the code will not work。Because you do need to use these tricks。

There are also very good interview questions， by the way。

 if you ever want to apply for a text analytics company。

 chances are this is actually a very nice question to ask how to deal with underflows with multinos。

Okay， the maximum likelihood estimate， so。What I'm going to do first is I'm going to rewrite this as the product。

From c equal 1 to C。And then， I'm going to take。I see。To the NC。

Times the product from J equal 1 to D。Of theta J C。And just see。N C minus N J。

What I'm doing that is the same trick that I did with the Bernoulli distribution in detail before。

 which is if I multiply。I'll do it with one term。 If I have the product over I。

And the product over C。Of pi C to I of Yi。That's equal to the product of a sea。Of pi C to the sum。

Over I。Of the indicator。So I'm using the same operation that we use all the time if you're multiplying the same term to an exponent。

 you just take that term to the sum of the exponents。In other words。

 two to the three times 2 to the four is equal to2 to the three plus four。

 That's the property that I'm。But once I use this property。

 I get an expression that's a bit more condensed。Okay， and。

The sum over those two indicators was the definition of NJC。Now， what I have it in this form。

The log likelihood。Of the parameters， which in this case are the and pi。I just。

Some of a sea equal 1 to capital C。And see。Log of5 C。

And then I'm going to put it separately as two terms， so there's this term。

And then there's going to be the sum of a C equal 1 to N C。And the song。Of a j equals 1 to D。Of NJC。

Log。Theta JC。Plus N minus NJ C。Law of one minus teacher JC。One more。Okay。

 so that's my log likelihood It's just taking。 So from now on， it's all mechanical。

 there's a lot more indices than we had with the coin model。

 but what I'm doing is exactly the same thing。I just need to keep track of more indices。

 I take the log， then I will differentiate equal to zero， and I will get theta and I will get pi。

All right， so that's my log likelihood。 Let's first estimate pi。Actually。

 let's start with theta because theta is a familiar term。Actually。

 I did realize I went very slow today， so I've run out of time。 Here's what we're going to do。嗯。

We're going to compute the law that we're going to take the derivative of this term。

 and we're going to estimate pi， and we're going to estimate theta。

I'm going to ask you as an exercise and this really will help with me presenting this material so I've noticed sort of how faces seem to be lost and I think they're lost because of keeping track of the indices because this material is not new and judging by the exam you actually knew the distribution pretty well so what I'm going to ask you is to go home I will put this online and you will derive the maximum likelihood estimator of pi and the maximum likelihood of theta and if you try that for the next class when I do this and the next class it will go a lot quicker and we'll get these estimates。

Okay， and then we'll do the ba analysis prior likelihood and we'll be done we'll have the solution for the na base once you know that you can go and implement your own sentiment engine。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_116.png)

On the web。I'll take a question。Oh yeah。 I called her anything。等一下。For the midterm， to hand it back。

I'm going to。Split them。They sorted by surname。And so。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_118.png)

So， I'm gonna to。All right， before you guys pick it up。

 let me make sure this will minimize the amount of problems here。 There will be two piles there。

 A to G。And then， H to。And。Right。And then oz over here。Yeah。No， sorry， little update快。I job。那个。

将系系晒嘅事啊。反咩都咩。My name is much。 when I my。Right。过觉是。没有。Yeah。



![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_120.png)

Yeah。I don't see anything。

![](img/4a1ccc7e437351c4b8e24cb3d89ff1b1_122.png)

我几点啊。