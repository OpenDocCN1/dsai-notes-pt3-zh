# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p14 Lecture 16 - probabilistic classification.zh_en -BV1utzNYqEkr_p14-

![](img/1120d176e99f4b71f2cd0a64b9eebc8b_0.png)

![](img/1120d176e99f4b71f2cd0a64b9eebc8b_1.png)

Hello， welcome to the section on Probabilistic classificationification。😊。

So so far we've talked about classifiers that given a record。

You return for us a prediction of which class the target variable lies in。

And now we want to talk in this section about an extension of that idea。

Instead of having a classifier that simply predicts one value。

 we want to think about a classifier that can make more general types of predictions。😊。

So if we have a classifier that predicts one value， we'll say call it V hatAT。😊。

That would be called a point classifier or a point predictor， it makes just one guess。

A classifier that produces more than a single guess。😊。

Might for example produce a list of guesses or an ordered list of guesses so it says here are the top three things。

 so for example we've got a cameras sitting on a car that's looking at all the things out on the street。

😊，And it says， well， you know， that could be a pedestrian or it could be a person riding a scooter or it could be a。

A person。Who is riding a bicycle。 And those would be that the best guesses that the。

Predor makes it knows it's not a car， but it can't determine exactly which one of those three things it is and it may rank those。

Guesses， it is most likely to be a。Pedestrian second choice of scooter， third choice， bicyclist。嗯。

Another possible output of a predictor or a classifier would be a probability distribution on possible targets。

 so with probability 0。9， it's a pedestrian with probability 0。05。

's somebody on a scooter with probability 0。05， it's somebody on a bicycle。嗯。

And these are very common， in fact， probabilistic classification is probably the most common type of classifier that people use today。

😊，嗯。😊，And we also are of course， quite familiar with the idea of probabilistic predictions from weather forecasts。

Now if you look at your weather app on your phone， it will tell you the chance of rain today is 10%。

For example。So let's just consider a list classifier。

 so this is a classifier that produces an ordered list we might call these V top V second and V third as its best。

😊，First， second and third best。Guees for what the true why should be， what the true V should be。

And of course it may produce three guesses， it may produce a top 10 or it could be a variable number。

 sometimes it will know with this very strong certainty that it's a pedestrian and others it may have more uncertainty and so it produces two or three or 10。

Guesses。And so some predictors do produce a variable number of guesses。

 and some predictors always produce a fixed number。嗯。And so if we're trying to。

Evaluate such a predictor， well， you know， we'd be obviously happiest if the true V is the first choice of the predictor。

And I'm a little bit less happy if it's the second choice and so on。😊，One place you very often see。

listist predict in a recommendation system。Amazon has a predictor， for example。

 that looks at your recent browsing history and looks at your recent purchases and tries to figure out what you're most likely to be interested in for your next purchase and show you those things and so it will figure out your top 10 list of things you're most likely to buy or most likely be interested in and show you those。

One way to make a list classifier is to use an embedding that we've seen so far， so for example。

 we've used nearest neighbor un embedding to construct a classifier a。

Prediction algorithm that produces a Y hat， we have a bunch of different representatives embedded in RM。

 Psi 1 through Psi K。And our predictor so far has always just returned for us the representative。😊。

Which is closest to Yha。But it could equally well return for us the three closest representatives。

Two y hat， and those would be the three。嗯。Our best predictions and the closest one would be the top guest。

 the second closest one would be the second guess and so on。

So we're going to spend some time in the next few sections talking about probabilistic methods and so we really need to start looking at probability in earnest so this is where the corequisite in this class of knowing about probability is going to。

Start to come into play we're not going to use a great deal of probability。

 but we will certainly use some and so just a brief review right here or probability。

And probability distribution on our target set B， it's a function。For each element of our target set。

 it gives us a real number and those real numbers have to be non negative and add up to one and those are the probabilities associated with those。

Elements of the targets set V。 So P of V is the probability。我 about飞。So for example。

 if the target set is rain and shine， we might have P of rain is 0。15 and P of shine is 0。

85 if our predictor。Is predicting a probability that will rain of 15% and a probability that will not rain。

Of 85%。If we have a probability distribution like this。Well， we have numbered the entries in。

The targets at V is V1 through V capital K got K categories or K classes well then we've。Also， got。啊。

PVI， which is the probability of VI we can think about as the I entry in a probability distribution vector。

And so our probability distribution assigns a number to each of those K classes。

 and so we've actually got K numbers which give us a K dimensional vector。And so in vector notation。

 we might say that p is greater than equal to 0 and what that means is that that inequality should be interpreted element wise。

 all of the entries p sub I of p as a vector are non negative。

And the fact that because this is a probability distribution， the entries have to sum up to one。

 we can express that as one transpose p is equal to1。

 where the one on the left there is the vector of all ones。

And so that's simply saying that the entries have to sum up to one。

So we can either think about our probability distributions as functions which map script V to the res。

 or we can think about them as K dimensional vectors。😊，Both of those are convenient。

And we will make use of both choices of notation。A probabilistic classifier produces a probability distribution P hat on V given U。

So we have a classifier it takes in the input U and it returns for us a prediction and instead of that prediction being why hat。

An embedded。Value of V， or instead of it being V hat， a prediction of which。Clas。

The target variable lies in， it produces us P hat。And so the hat here indicates prediction。

And Pi is a probability distribution on V。So it's a number associated with each of the different classes。

 which informs us how likely。The classifier thinks each one of the different classes is。

To correspond to that， particularly you。So what like this is P hat is G of U， this is capital G。

 so the capital G is used in the same way we used it before in that we use little Gs to indicate a predictor that's taking input X。

And producing an output Y and a big G to use to indicate a predictor that's unembedded。

 that's composed with the embedding and unembedding operations。

To take in an input U and produce an output V。And here。

 because we're dealing with probabilistic classification。

 we're using capital G to indicate a predictor that takes in an input U and returns for us an output。

 which is a probability distribution en V。So when you read this。

 you should keep in mind that we've got something a little tricky going on here G is a function and it's returning a distribution which is itself a function。

So we want a function that returns a function。We can call the function。

 so we get PHAT is G of U and then I can take PHAT and evaluate it at a particular class VI so I can take P hatAT of VI。

And that would give us the probability that V is VI when the independent variable is U。Of course。

 I could just bite that all at once， I could say G of U evaluated it VI。

 which Id remind as G parentheses U， parentheses VI。嗯。And so here， of course， this is totally fine。

Functions returning concrete objects such as numbers and vectors and matrices。

 and here we've got a function that's returning a more abstract object which is a function。

And modern programming languages such as Julia can happily do this。

We've seen this already when we pass around loss functions in Julia。

 and so here we're going to pass around probability distributions， which are just functions。

Now in some sense， the point classifier and a probability probabilistic classifiers are related to each other。

 we can say， well for example a point classifier is a special case of a probabilistic classifier。

 it's a probabilistic classifier that's saying the probability of a particular target is 100% and the probability of all the other classes is zero。

😊，So we could construct such a thing， we' would have P hatt of V being one。

B is V hat and zero otherwise。And that would be a distribution。That corresponds to 100% certainty。

That。The guess is V hat and0% certainty for the others，0% probability for the others。

And typically this is not what you want， of course。

 yes it's a probabilistic classifier you've taken a point classifier and constructed a probabilistic classifier。

 but you haven't gained any more information out of this。😊。

You can also go the other way if you've got a probabilistic classifier。

 you can construct a point classifier so what you do is you say。

 well my probabilistic classifier gave me a probability distribution P hat。

 let me look out of all of the V's for the one that's most likely the one which maximizes P hat of V。

😊，And。That would be。A way of translating a probabilistic prediction into a deterministic prediction。

 into a very specific prediction， which is actionable。嗯。So， for example， if you。啊。

Have a predictor of the weather that's telling you the probability of rain at some point you have to make that actionable。

 you have to decide， am I going to carry an umbrella outside or not？😊。

And so one way to do that would be to say， is it more likely that it's going to rain or that it's going to shine。

 that it's not going to rain？😊，And if it's more likely that it's going to rain。

 then you carry your umbrella， if it's more likely that it's going to be sunny。

 then you don't carry your umbrella。😊，And of course。

 there are many ways of translating probability distributions into actions。

And this is just one way of doing it。This particular method of translating probabilistic prediction into a point prediction is called maximum likelihood。

😊，We look for the。Class that's most likely that that highest probability。

We can also generate a list classifier from a probabilistic classifier simply by giving the value sorted by probability。

😊，There are several different ways of constructing a probabilistic classifier。

 all of the ones that we've seen so far for point classifiers can be extended。

 so one can have a tree tree based probabilistic classifier。

 which is a decision tree has nodes labeled by feature and threshold value in the leaves contain distributions rather than point predictions。

😊，You can have a nearest neighbor probabilistic classifier。 the way that works is then you have a。😊。

Predicted if you have a query point X。Then you look for the K nearest neighbors2 x。

 so the x sub I's in your data set， which are the closest x。And then amongst those。

 you look at the distribution of VIs that you have。

 so if three of them are true and five of them are false。

 then one would predict a probability of three/ fifths for the corresponding target variable at the0 x。

You can also do probabilistic classifiers which are based on linear predictors or based on neural network predictors。

 and we will come to those shortly。So here we have our nearest neighbor classifier， we've embedded。

The U's in R2 take give us two dimensional x's， given a query point。

We would look at the corresponding point in the plane and we would like to predict either red or blue for the corresponding class。

The way we do it is here we look at the K nearest neighbors。Of a query point。

 So here K has been chosen to be8。 So for any given query point we look at the eight nearest neighbors。

 let's look at an example。嗯。So we'll have a query point。So right here。

And we'll draw a circle that contains eight neighbors， which I would guess is。Something like that。

And then of those eight neighbors， we will count how many of them are red and how many of them are blue。

 and that will give us the prediction， probability distribution。

 the empirical distribution that we're seeing。Amongst the nearest eight neighbors。

And so here the colors in this plot are chosen accordingly。

 so if the prediction is blue 100% red 0% then that's this color which is dark blue。

 if the prediction is red 100%， blue0%， that's this orange color。

 and of course the color is in between vary and really we are only predicting one probability here because once we've got a prediction probability for blue。

 the prediction probability for red is one minus the probability for blue。So now we want to consider。

 well， suppose we've got a probabilistic classifier or a list classifier。

 How are we going to evaluate how good they are。😊，嗯。

And there are several different ways of doing this。

 It's not quite as simple as it is for a point classifier。If we're trying to judge a list classifier。

 then we may look at the error rate as a function of the list rank。😊，So for example。

 we have a test data set， we have a true value of V， and we have our predictor is given us。

 is giving us。😊，The top， the second and V third。as it guesses and then we ask ourselves。

 wellre going how many points in the test set did the predictor？😊，Get V top to be the actual true V。

And we might find that's say 68% of the samples。The V top was actually the true V。

And then we could say， well。How many of the test set points was the true value among the top two guesses。

 and that might be has to be higher than 68% that might be 79%。

And then amongst the top three guesses might be 85%。And so。If you want just one number。

 you might decide， well， I'm really concerned that it'd be in the top three as long as it's in the top3。

 I'm happy and in which case， 85% might be a reasonable accuracy。

Another way to do it might be to score the test data set for every。啊。

Data point VI in the test data set， we look at whether it was the top guess in which case we give its three points。

 the second best guess in which case it gets two points or the third best guess in which case it gets one point and then we add up the scores over the entire test set and that's a measure of how good a job our list classifier。

Now to judge a probabilistic classifier， that's a reasonably subtle idea。

what do we have well we have a data set with using Vs in it。

 and then for each one of those data points， we have a prediction P hat。And so。嗯。

So for each data point。We have a true value， the V， and we have a prediction。

 which is a probability distribution P hat over the set of possible V's。は。

And one way to say whether this is a good prediction or not would be to say。

Let's look at the P hatt that we got and see whether it。

Gives a high probability to the actual value that happened V。😊，So for example。

 if we've got a prediction of rain and we look back at historical data and we look at the predictions of rain based on the weather the day before and we look on whether it did rain or not。

 well what we'd like to see is that on days when it rained the probability predicted for rain was large and on days when it didn't rain。

 we'd like the probability predicted for rain to be small。😊，And if we see something like that。

 we might say， well， that's a good predictor。Now we' got to make this idea formal。

 the most common way of formalizing this idea is to use what's called a log likelihood。😊。

So we have a data set， new one through UN， V1 through VN。And。

We're going to have a prediction at each of those UIs， which we're called P hat I。

 it's the output of our predictor when we feed UI in and it's a probability distribution over the Vs。

Now， if this were the。True distribution of so if P hat I was the true probability distribution that the Vs that VI was generated according to。

 then we could ask ourselves， what is the probability of seeing that sequence V1 through VN？

So if I is one， the probability of getting the particular。

V that we got is given by evaluating P hat1 at that particular V， which is just V1。😊。

Similarly for i is equal to 2， we have to evaluate P hat2 at V2。

And those give us the probabilities of getting those outcomes under that distribution。

If we make the probabilistic assumption， then each of those data points is independent。

Then the probability of getting the entire data set is the product of the individual probabilities。

And so the probability of seeing that entire data set under those distributions。

 P hat1 through P hat N is simply the product from I1 to n of P hat I evaluated at VI。😊。

So this is just a probability， it says。😊，When you've got some distribution。

And what's the probability of getting that particular outcome？😊，And we can look at it as well。

 just the probability of getting the outcome， but we can also look at it another way and look at it as a measure of。

😊，The distributions P hat1 with P hat n。And when we do that。

 instead of calling it the probability of getting Vs。

 we call it the likelihood of P hats being correct。😊。

So the likelihood is simply another name for the probability。

 but we call it the probability when we're looking at the probability of outcomes and we call it the likelihood when we're talking about the likelihood of probability distributions。

😊，And so we'd like this quantity， the probability or the likelihood to be。😊，Large。

And this is a fundamental measure of how well the predicted distribution matches the data。

 just as in our rain versus sun example， if the probability of rain is large on days when it did rain。

 that's a。Good predictor。So we can compare two different classifiers by looking at their associated likelihoods。

 which one has the largest probability value， theyre the largest likelihood。😊。

And the one with the largest likelihood。😊，We would consider the better classifier。

Now it's actually more convenient to work with log probabilities rather than purely probabilities now one reason for that is that the likelihood is a product and when we take the log we're going to get a sum。

There are some other reasons for that as well， which we will see。😊。

So what we work with is actually the negative log likelihood。

 that's simply the negative log of the probability of getting V1 through VN under our predicted distributions。

 P hatAT1 through P hatAT N。😊，That's the negative log of the product of the P hat I evaluated through the VIs。

Which is negative of the sum of the logs of the PIs of the eyes。😊，Now。

The negative log likelihood is actually a positive quantity。And we would like it to be small。

If the negative log is small， that means the probability itself is large。嗯。

One of the things about this is that this is。If we just look at the log of the probabilities。

 then that gets smaller， the more data points we have and so we need to normalize in some way and the way we do that is we look at the average negative log like Leode。

😊，So that's here L is minus1 on n， the sum from I is1 to n of the log of P hat I of B。😊。

And this is a quantity that we can compare。😊，嗯，Effectiveness of different classifiers and different size data sets。

😊，Okay。So now we have a。They're very nice。Performance metric。

Which is this average negative log likelihood。Now just as we did when we were looking at loss functions。

 when we were looking at the square loss and the absolute loss， we asked ourselves the question。

 if we just looked at constant classifiers，Which would be the best constant classifier。

Which minimizes the average value of those losses。Here we have a particular performance metric。

 the average negative log likelihood。😊，And we're going ask ourselves the question， which is。The。Best。

 constant。Predicctor the best constant probabilistic classifier that minimizes。

That particular performance metric。So how is this going to work， Well。

 we're going to have a data set， which is just。V1 to VN， a bunch of classes。

And we're going to look for a classifier that doesn't depend on the use。

 so the use and they don't even exist。All we're going to do is try to predict a distribution P hat。嗯。

And that distribution P hatt has to be a probability distribution on script V。So what do we do。

 we're going to choose P hat to minimize the average negative log likelihood。😊，in-1 on n。

 the sum from I is1 to n of the log of P hat or VI。And we can choose any distribution P hatt we want。

Of course， it has to be a probability distribution。

 so it has to be non negative at every point v and it has to sum to one。Now。

It turns out that the optimal， constant probabilistic classifier。Its very nice。

 it's a very sensible quantity。 It's actually the empirical distribution of the data。😊。

So the empirical distribution of the data， we simply count up for each V in script V。

 the fraction of the data。Which are equal to that particular class。

So it's simply the empirical distribution， it's simply the counts divided by the total number of data elements we have。

 we call that Q。And then the P hat that minimizes the average negative log likelihood。It's cute。

And this is very nice， this is just like when we talked about minimizing the square loss。

 we found that the best constant predictor was the mean。

 when we talked about minimizing the absolute loss。

 we found that the best constant predictor is the median。

Now we're predicting probabilities and when we think about minimizing the average negative log likelihood。

 the best constant predictor is the empirical distribution。Now， the。

Negative log likelihood can be computed in a particular way。

So we have the negative log likelihood is minus1 on n， the sum from I1 to n of the log of P hat V。😊。

Now， each of the VIs lives in one of the classes。Now remember what the classes are。

 we use this notation V is V1 up to Vk， notice those are subscripts to indicate the classes and we've got the data elements which are V superscript I from I is1 up to n。

Now， if I compute this quantity， the sum from I is one up to n of the log。🤢，Of P hat of V I。 Well。

 I can split that sum up。 I can split it up into。Those eyes for which V is， say V1。

And then I can take the log of P hatt of VI， but all of those Vs are V1 so I can just write that V1 and then I can do the next category。

Such that V is V2 of the log of P hat of V2。And so on。Up to K categories。

Some from overI such that VI is VK。Of the log。Of P hat， of B。看。So by splitting it up like this。

 I just split them up into into。😊，Categories， notice that this inside here。😊。

Inside each of these sums。The terms don't depend on I。So I've really got。

Just a certain number of terms that are all the same and the number that I've got。

 well it's just the number of data points for which VI is V1 in this sum。

 the number of data points for which VI is V2 in this sum and so on。😊，So when I work out this arm。

 I'm taking into account the factor of in。Well， then the fraction of terms。Is Q VJ。

 that's the fraction of the terms in this sum for which VI is equal to category Vj。

And for those each one of those terms， the quantity log P hatt， a VI is just log Phat。

Of the corresponding class VJ。So I end up with a sum over the categories rather than a sum over the data points。

😊，And I have that the average negative log likelihood is the sum over the categories of the。

Empirical distribution。Of each of the categories times the log of the probability of that category。

This quantity is called the cross entropy of P hat relative to Q。Where P hatt is the distribution。

That is being evaluated。 It's the distribution that's produced by the predictor。

And Q is the underlying true empirical distribution。Of the Vs。We might bite this as。H， oops。H of Q。

P hat is equal to minus the sum from J is 1 up to K of Q J。Lolog。P hat J using our vector notation。

There's also a related quantity when P hat and Q are the same distribution。So we'll call them both P。

That quantity is called H of P。Next's the sum。Over K of PK log PK， just negative PK log PK。

That's called the entropy of a probability distribution。😊，And both of these quantities。

 the cross entropy and the entropy are。Very important， mathematically， very important practically。

 they're used very widely in coding theory and in information theory and in machine learning。

They're fundamental properties of probability distributions we don't need much of the theory of that here or in fact any of the theory of it here。

 we just want to be able to determine。Which is。The P hat that minimizes the average negative log likelihood。

WellAnother the way to say it is。If I've got a Q， which P hat minimizes？H of Q P hat。

 because H of Q P hat， the cross entropy is the average negative log likelihood。Okay。

There's a convenient。Quantity。To use for this， and that's called the coolback high blur divergence of Q& P。

So we've got H of QP， we'd like to minimize that。Over p。But actually instead of looking at H of QP。

 we're going to look at this thing called the callback libla divergence DKL of QP。

 and that's H of Qp minus H ofq minus the entropy ofq。😊，This is convenient for the following reason。

 we want to minimize H ofQP。😊，Over。P， but actually， well， H。F Q P。It's just DKL of Q P plus H。Fq。

If I'm minimizing this quantity over P， well this additional term here doesn't matter because it doesn't depend on P。

😊，Just depends on Q， it's just a constant。So we're just shifting the objective function in our optimization problem。

This quantity， the callback glla divergence， has a very nice property。😊，That it's non negative。

One way to think about it is that it's a measure of how similar。😊，Two distributions。

 probability distributions P and QR and when they are the same。Well， then。D Q P is 0。Because。

If we look back at our definition of entropy。😊，H of P is。The cross entropy of P with itself。And so。

When Q is equal to P， we clearly have that the calledback gllylo dirgence of Q and P is0。😊。

And when Q andP are not equal， well， then the k later divergence is always known negative。😊。

This is easy to see。😊，If I just look at what the sum is。

 DKL of QP is the sum over J of Qj log Pj on QJ， so here we're using our vector notation。

 PJ is simply a shorthand for P of VJ。嗯。😊，So here I've used the fact that I've subtracted one log from another。

 and that's simply the log of the ratio。Now the log of PJ over QJ。Its a nice bound， the log。😊。

Of the quantity。Log， this is one。And then the logarithm。Looks like that。

And I can compare that with the function x minus1。Function x minus1。It is the tangent right there。

And so the log of x is less than or equal to x minus1。

This implies that this sum is less than or equal to is greater than equal to this sum。

And this sum we can expand as being equal to the sum over j of。PJ。Minus the sum over j of Qj。

And both of those terms。Are equal to1 and so because both P and Q are distributions。

 and so the overall sum adds up to zero。Hence the。Call back light blur。Divergence of P and Q。

Is greater than or equal to zero。Here we used the fact that Q was non zero when we did this division。

U but in fact， this proof can be shown to hold even if some of the cus are equal to zero。😊。

And that tells us the best constant predictor。The best constant predictor is given by the P hat that minimizes the average negative log likelihood。

 the average negative log likelihood is equal to the cross entropy。

 and so we would like to minimize H of Qp hat with a spec P hat。😊，We can make this term zero。

By setting P hat equal to Q。And of course， this is just a constant term。And so when P hat is Q。

That's the best constant predictor。 Best constant predictor as。

Probability distribution equal to the empirical distribution。The resulting。

Co entropy is the entropy of Q。So let's summarize a point classifier makes a single guess of the given you。

Whereas a probabilistic classifier， this is a probability distribution on the on the target set of classes V。

 given the U。😊，And we judge a probabilistic classifier by its average log likelihood。On test。



![](img/1120d176e99f4b71f2cd0a64b9eebc8b_3.png)