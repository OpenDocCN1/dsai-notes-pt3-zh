# 斯坦福大学《机器学习｜Stanford EE104 Introduction to Machine Learning  2020》deepseek翻译 p04 Lecture 4 - validation.zh_en -BV1utzNYqEkr_p4-

![](img/6ab4e081b89af7ef14edc78604c79dc1_0.png)

![](img/6ab4e081b89af7ef14edc78604c79dc1_1.png)

Welcome to the validation section。So we've seen so far。Several different predictors。

Which given up an X can predict for us what the。Corresponding value of Y should be。

And I want to talk now about how we're going to。Evaluate。Different predictors。

 we have seen K nearest neighbors predictors， we've seen tree based predictors。

 we've seen neural network predictors， we've seen linear predictors。And so。

Somebody's come along and said， well， here's my favorite predictor which I designed。

And you're going to decide， well， should I use that predictor or should I use some other predictor？

So one of the key ideas is that we need what's called a performance metric。

And what it is is it's a measure of how large。Prediction errors are。

And so what we can do is we can say， well， we've got a data set， x1 through xn and y1 through YN。

And each one of those data points。We can evaluate the predictor G at。

The I data point Xi to get prediction。Why hat I？And ask the question。

 how close is why hat I to why I？And the performance metric is going to。😊。

Be the measure of how close Y eye is to Y I。And normally， it's。

Designed so that the smaller the metric， the better。The prediction performance。

 it's an error measure。Some people call the prediction performance metric， the prediction error。

 as a result。So there are a few which are very commonly used。The first one is the mean square error。

So this here is the two norm let me just mark here。YouSee the subscript2 there。

 what it means is it means。Means the following。If you give me a vector。X。Then。That's equal to。

The sum from I is one up to n。X， I squared。Or square rooted。

And the Subscript2 there indicates which particular norm we are using。

There are other norms that we might use with different subs， so for example， we might use。

The one norm。Which is just。The absolute value。Of each of the components of X。Add it up。

And we'll see a few other norms in this class， as well as a few other performance metrics in this class。

😊，So。If Y I is a vector， an M dimensional vector， then if you give me a particular Yi and a particular corresponding prediction Y hat I。

 I can compute its two norm as。A measure of the error between Y hat and YI。And then I can average up。

And。So some of those up and divide by in。And that would be a prediction。Performance metric。

And of course， if y I is just a scalar so M is1， then that's just the mean square error。

 the mean square difference between Y I and Y hat I very often instead of working with the mean square error。

 we work with the root mean square error。That is the square root of1 on n multiplied by the sum from i is1 to n of y hat I minus y i squared。

Which is convenient because it has the same units as Y。And。Another very useful。

Error metric or performance metric is the mean absolute error。

 so that's one and n the sum from minus1 to n of the absolute value of y I minus y of I。😊。

If you have scalar positive Y's， then we define the mean fractional error as the average of the absolute value of Y hat I minus Yi。

 divided by the minimum of Y hat I and Yi。😊，And this is something like an average percentage error。

If y hat I is greater than Y I， then the absolute value of Y hat I minus Y I divided by the minimum of Y hat I and Y I is the percentage by which Y hat I is greater than Y I。

There are many other。Common performance metrics， the median error。

There's other ones very commonly used and we'll see many others in this class。

So now we've got a prediction performance metric that allows us to compare different predictors on a particular data set。

So for example， we might conclude that K nearest neighbors with K is7 does better than K nearest neighbors with K is 12。

Or we might conclude that a particular neural network does better than a particular linear model。嗯。

Several things to notice about these kinds of conclusions， they depend on several things。

 first of all， they depend on the performance metric。

It is quite reasonable and quite common that you can have a predictor that does better。😊。

On one performance metric。But does worse in a different performance metric。

 So the neural network may do better than the linear model when using。RMS error。

 but may do worse than the linear model when using the mean absolute error。

So you got to choose the performance metric carefully so that it corresponds to something that you actually care about。

Another important thing to notice about performance metrics and using them for analysis of predictors is that they are predictor agnostic。

That's a very good thing。It means that when we evaluate。The performance of a predictor。

 we're not evaluating it using the same software that was used to develop it。

 we're not evaluating it on the basis of the properties of the learning algorithm。

We're evaluating it on some objective notion of performance。

And anybody's predictor could be evaluated。Using the same performance measure。So somebody else has。

Method of generating a predictory。 And if you don't know what that method is。

You can evaluate their predictor by evaluating the quality of their predictions。

And all that should matter is whether or not their predictions do better are better than the predictions given by some other predictor。

The third thing to notice about comparing predictors using a performance metric is then it depends on the data。

😊，And so all you can do is you can use the performance metric。

To evaluate the performance of a predictor on a particular data set。

And that leads us to the question of generalization。

Suppose we have a predictor and it performs well on the data set that we use to train it。

Can we conclude that it's going to perform well on a data set that it's never seen before。

 unseen data？And if it does， that's called generalization。

Generalization is the ability of a predictor to perform well on unseen data。

An unseen here means that the data was not used to create the prediction model。

 it was not part of the learning data set。The person who developed the predictor never looked at that data when they were developing the predictor。

So we'd like to answer the question of when we can。

Infer that good performance of a predictor on one dataset implies that the predictor will perform well on a second data set。

And in order to do that， when we need to make some probabilistic assumptions， for example。

 one might say that both sets of data are samples from some underlying probability distribution。😊。

With some kind of probabilistic assumptions like that。

 we might well be able to conclude that performance on one dataset says something about performance on another dataset。

For example。If we have two sets of data both sampled from the same distribution。

 we might reasonably conclude that the mean。Of the first set of data and the mean of the second set of data。

Should be very close。Provided we have enough data。So。

There is a framework for doing this kind of analysis， we will not discuss it in this class。

 it's a more advanced topic。But instead， what we will see is we will see some practical methods。😊。

So methods for actually assessing whether or not the predictor that you've got actually generalizes。

The fundamental thing to do， of course， if you want to know whether your predictor generalizes to a new set of data is to try it out on a new set of data。

And so we think about。Having two sets of data， one we call the training data or the in sample data。

And that's the data set that we use in order to construct the predictor。

And then we have another set of data， which we call the out of sample of data。

 that's the unseen data on which we're going to test the performance of the predictor。😊。

And if the predictor performs well on this unseen data， we say the predictor generalizes。😊。

It makes good predictions on data it is never seen。If it doesn't， we say it fails to generalize。

 it's overfit。This terminology overfit is quite evocative and we will have much more to say about it。

Okay here is a simple example， this is data downloaded from the federal government。😊。

this plot shows the number of vehicle miles traveled in each year over a range of years from 1970 to 2005。

And so vehicle miles traveled is the total number of miles traveled。Over the year。

 by all of the vehicles。嗯。And on the left here， we have a subset of the data， we have 12 data points。

And will just highlight right there。And what we do with those 12 data points is we fit a straight line predictor Y hat is Theta1 plus Theta 2 times x。

 where Y hat is our prediction of the number of vehicle miles traveled and x is the year。

And we will just choose those parameters using English least squares。

That gives us this nice straight line fit。Here。Which goes all the way。好的。And then we can say， well。

 let's look at the rest of the data， the data that we held aside。

 we only fit this straight line using 12 blue sample points， we've got another 14 data points。

 these are these 14 data points right here。😊，And we can see that those 14 data points actually lie rather close to the straight line fit。

And so the predictor actually does generalize to those additional points。Of course。

 in this simple example， you can plot it all and see it all by eye。

 it's very simple in two dimensions。And of course， we'd like to be able to work with very large data sets in a very large number of dimensions where it's no longer possible to do such simple plots。

And that's why we need to use the tool of。Prediction， error metric， prediction performance metric。

In order to evaluate how well the predictor is doing on these different data sets。

Now there's a specific approach to doing this， in fact there are several specific approaches to doing this kind of analysis。

 The first one is called out of sample validation。😊，And that goes like this。

Very often we don't have data sets which are naturally fall into two categories data that we used to。

呃。Do the training and data that we use to test and so what we do is we split the data。

And so we'll download some data set， it may be a whole bunch of images。

 and we'd like to develop a predictor that can。Look at an image and tell us whether that's a cat or that's a dog。

And。啊。We take this data and we divide the data into two data sets， a training set and a test set。

And often we do that randomly， so we' might use 80。An 8020 split where 80% of the points。

We used for training and 20% were use for test。Now we might use 9010。

 it doesn't really matter very much the exact。😊，Split is not very important and the results are quite insensitive to that。

What we do with the training set is we train the predictor， we use it to choose the predictor。

And then the test set is used to。Validate the predictor to evaluate how well the predictor performs using the particular performance metric we've decided upon。

😊，And as a result， you have an honest test， you have an honest simulation of how the predictor works on unseen data。

And。We hope that because it worked well on data that was not used to train it。

 it will also work well on other unseen data that we haven't seen yet at all。

And this hope is founded on the assumption that all of this data looks kind of the same。

 the data that we used for training， the data that we're using for testing and future unseen data。

 they're all kind of similar。Very often we do this split in a random way for two reasons。

One is that we want to get the training right。If I'm， for example。

 outside taking photographs of cats and dogs in the hope to develop a predictor that can tell the difference between them。

😊，Well， during the day the sun might go down， the clouds might come over。

 might become quite overcast， the conditions can change quite significantly。😊。

And so if I simply take the last 20% of the images， then I could end up with。A test set。

 which is all cloudy images and a training set which is all sunny images。And that will boast。

Upset my。Training， it could well be that my predictor will not learn how to distinguish cats and dogs under cloudy conditions。

 but only under sunny conditions。And will upset my test in that。

 all I will be doing is testing the predictor in cloudy conditions and I won't measure the performance in sunny conditions。

😊，So the fact that you make this split random helps to avoid these kinds of。😊。

Bes and errors which are a result of。A particular ordering of the data in the data set。

Now what matters is the performance on the test set。

The training set performance doesn't really matter at all。We expect it to be good。AndIn fact。

 we usually expect the training performance to be better than the test performance。

Usually the test performance is only a little bit worse than the training performance。嗯。

Sometimes the test performance is still okay， but actually quite a lot worse than the training performance。

That's fine。 if your test performance is okay， that's what matters。

You can be in a situation where the training performance is perfect， for example。

 one nearest neighbor's predictor。The one nearest neighbor predictor。

 if you give it an element of the training set， one of the XI's。

It predicts the corresponding Yi corresponding to their Xi because that is the closest。X to that Xi。

And so it gets zero error。On the training set。But it still makes useful predictions even for data that's not in the training set。

But the training error is no indicator。Of how well it will do on the test set。

So let's look at how we interpret validation results。😊，We have two measurements。

 the first is the performance on the test set， that's really what matters。

And the second is the performance on the training set。That doesn't matter。And so we get four numbers。

 we'll plot these in a table here。In the first column。We have the training error。

 we have small training error。And in the second column。We have a large training error。

And in the first row we have small test error， and in the second row we have large test error。

So this top left entry here。It's really good news， it means we've got small test error and small training error。

So it performs well when we did our training and then when we tried it out on data we haven't seen before。

 it did were well there too， and so it generalizes。It is possible to be over here。😡。

To be in the case where we have small test error， but large training error。

That is luck or perhaps we've cheated in there some kind of fraud involved。

It doesn't happen very often because one does the training and one it see a large training error and typically doesnt even we don't even bother to try it against unseen data。

 if we can't get it to work on data that we can see。

 we're probably not going to get it to work on data that we can't see。

So this doesn't happen very often。NowIf we have large test  error， the bottom row。

 well then there's two possible explanations。😊，One is we have small training error。

 but we had large test error。This is the failure to generalize we thought we developed a good predictor。

 it seemed to do well when we were training it。But then we tested it on data we've never seen before and it didn't do well。

We would say such a predictor is overfi。And in the worst case of all。

 we have large training error and large test error。😊，It generalizes okay。

 it does the same thing on the test data that it does on the training data。

But it doesn't do very well on the training data。So how do we choose between different candidate predictors？

Two people come along， they've both're both experts in machine learning and they come to us with their predictors。

 but they've developed them using completely different methods。We don't even get to see their code。

We can do validation。We take their predictors and we try their predictors on data that they've never seen before。

And typically what we're going to do is we're going to choose the predictor amongst all of those candidates。

 which has the smallest test error。It's not always what we do because sometimes when were willing to back off a little bit on that requirement。

 we might accept a little bit larger test error if that gives us a particularly simpler predictor。

There are good reasons for this and we will have more to say on this later。

let's look at a particular example here as simply a one dimensional example。

 we have a data set with 30 data points， 20 of which we'll use for training and 10 of which we'll use as the test set。

Here on this plot we see 20 blue points， those are the training set and 10 red points。

So here is the performance of two of our favorite classes of predictors。On that data set。

Here on the top row， we have the K nearest neighbor predictors when K is1， two， and3。

And on the bottom row， we have。The aire predictor， the quadraautic predictor and the qubic predictor。

We can see right here that theyre in the top left plot， the k nearest neighbors predictor when K is1。

Just perfectly on the training。Data。Let me just highlight that it passes perfectly through。

The blue data points。If I look at the K is's equal to two plot。😊，Well。

 that doesn't pass perfectly through all the data points。

But it's a bit smoother than the K is equal to one。😊。

In Ks equal 3 also doesn't pass through all the data points， but it's a little bit smoother。

Then K is equal to2。Now the ane predictor here。That's the best straight line fit。

Here's the quadratic predictor。And here's the cubic predictor。Just looking at these。

Now let's look at the RMS performance error， so we're using the RMS error here as the performance metric and we could say。

 well， which is the best？😊，Prediction model。Some things to highlight， well， first of all。😊。

That number right there is zero the K nearestish neighbors predictor when K is equal to 1。

 that perfectly on the training data。doesn't when we increase k is equal to 2 k is equal to3。

 actually the performance gets worse on the training data。😊，嗯。And all the test data。

It changes a little bit， it goes from 0。1 when k is 1 to 0。08 when k is 2 back up to 0。1 when k is 3。

When we look at the polynomial predictors， we see something which is。Quite interesting。

With an air find predictor on the training。Data， we have 0。08。

And then when we go to the quadratic predictor， the error decreases。This has to happen。

Because we're optimizing over the best possible quadratic predictor and of course an II predictor is a quadratic predictor。

 it's just a very special one。And so the quadratic predictor is comparing all possible quadratics。

 including all the airvines， and so it has to do at least as well as the best aire predictor。

So when we go from Aire to quadratic， the performance has to get better。😊。

And the same when we go from quadratic to cubic。Every quadratic predictor is a cubic predictor。

 And so the best cubic predictor must do。At least as well as the best quadratic predict。

And so the training error has to decrease as we go from air to quadratic to Cbic。😊。

Those statements aren't true for the test data。We do see that as we go。

From AirFe to quadratic to cubic， that the performance on the test data does get better。

But there's no guarantee that that would happen。It doesn't have to happen。

So out of all of these predictors， which one has the best test？😊，Error is this one right here。

That's noticeably better， That's the cubic。Proredor it's test error 。025。

The next comparable ones are。The quadratic predictor and the two nearest neighbor predictor。

 but those are substantially worse at 0。08。So we might decide to。Go4。The best。The cubic predictor。

 which does well in test and it does well。In train。

 and so it both performs well and generalizes well。

We have the k nearest neighbor with k is equal to 1， which performs well on the train。

 but doesn't generalize so well。Let's look more generally at polynomial fits。

So suppose we have scalar U and Scalar V as our raw data。

And then we use a feature mapping where we construct x's from U by x is equal to phi of U。

 and for each U we construct a D dimensional vector。Consisting of the powers。Of U1。

 u u squared up to u to the power of d minus1。And then we're going to construct a linear predictor。

 G of x， Car transpose x， a linear combination。😊，Of those D monoials。

A polyno will of degree D minus1。And we're going to choose the The by least squares。😊。

And here's the kind of thing that we see。Here we have 60 data points。

And we are looking at the predictors with D is equal to 6 on the left in the middle of D is equal to 12 and on the right D is equal to 14。

 so these are degree 5 degree 11 and degree 13 polynomial fits of the data。😊，Now。

 if we look at the RMS error。😊，The one that has the smallest RMS error。😊，Is the degree 13 plot？

And that's not surprising at all， for the same reason the cubic did better than the quadratic in the previous example。

 that the degree 13 has to do better than the degree 11。

 which has to do better than the degree 5 against the training data。

Now we'll take those same 60 data points and we'll split the data points into 48 training points and 12 test points。

嗯。Now， for each。Degree D between here， we've got degrees between  zero and 14。

What we're going to do is we're going to train a predictor。On the 48 data points。

And then we'll compute two numbers。It's RMS error on the training set and it's RMS error on the test set。

So for degree two。That's this number。And。This number。And then we do it again， say it degree four。

 and we end up with this number。And this number。We expect。The training error is going to be。

 is going to be less than the test error， and it is at every different degree that we see here。

It doesn't have to be that way。Plots can certainly cross。

It usually happens that we do better in training than we do in tests， but not always。😊，Now。

 what happens on the training set as you increase the degree is that。

The training error has to decrease。Increasing the class of functions。

 increasing the set of functions over which we're optimising means we're going to get better fits。

And so you can see that every time we increase degree。Training error decreases。

The test error certainly doesn't have go and it doesn't。Now。

 if you just looked at the training error， you might conclude we conclude we should use a degree as high as possible。

So we should use D is equal to 15 here。And。啊。However， if you look at the test error。😊。

That suggests quite a different story。 That suggests that we should use。Dgree 5。

What's happening out here to the right？😊，As we're seeing overfitting。

We're seeing predictors that are doing really well on。The training data， but much less well。

On the test data。Let's look at our plots again。So here we can see it。

 you can just about see that really this data is kind of noisy and there's plots points scattered everywhere。

😊，But here we've seen these little wiggles showing up。😊。

Let's look at our polynomial again to see if we can see evidence of overfitting。

So there's two things that show up on this plot that are interesting。One is。

 is that there seems to be quite a lot of noise in the data。What do I mean by that？If we look at。

Just a particular region。Let's look at this region。If I look at x's within this region here。

Then we can see that vertically the value of y still tends to have some variability。

 it's not a smooth curve like the predictor would have us believe。😊，But instead。

 the points juiggle up and down a lot， you know， it suggests that those points come about。😊。

That variation in those vertical position of those points comes about ju to noise。😊，Now。

 what's happening with regard to our predictor？Our predictor is doing something interesting。

A predictor in this degree5 plot is just sort of averaging out the noises。

 doing something rather gentle。It's just moving gently through the center of the cloud of the points。

But this predictor over here。At degree 13， we can see that it's starting to wiggle。

And the reason it's starting to wiggle is that it's starting to believe in the noise。

 it's starting to try and fit the noise。And this is what we mean by overfitting。

Learning algorithm is fitting a predictor to features of the training data。

 which are due to noise or variation which isn't present。In the test set。And that's what we see。

Is that as we move down here？We're getting better and better fit as we fit more and more closely the features in the training data but the reality is。

😊，Is that。With test data， we're going to move up here。

And we're going to find that those features don't actually exist。In the test data。

 and they are going to give us greater error in the test data。

Then we are led to believe by the performance in the training data。

Now we can do several more slightly more sophisticated things than simply split the data into a test set and a training set。

😊，One extension is to split the data。More ways So we split the data into K different subsets。

 we'll call them K folds of the data， and this is called K fold cross validation。😊，And so we have。K。

 different buckets of data， K different subsets of the data。And。

What we're going to do is we're going to go through that's the sets of data and the first time we fit so let's draw say respect suppose K is5 and then we'll have five different subsets of the data。

 there's one， there's two， there's three， there's four。And there's five the first time we fit。

We will fit。Newsing。Those four。And we'll test using that one。The second time we fit。

 we will fit using this one。Those four and test using that one。The third time will fit。

Using those four and test， using that one and so on。 So we'll have。Each time we do a run。

 we will train using four out of our five buckets of data and we're going to test using the either bucket of the data。

As a result， we get better than having。Just one test error and one training error。

 we have five different training errors and five different corresponding test errors。

These five different test errors we can look at， we can work at the mean test error。

 the standard deviation of the test errors， and just get a sense of their variation if they're all small then we can feel rather confident。

That actually， this predictor。Does well。Comversely， if there's a whole lot of variability。

 then we start to feel a little less confident。And of course， we haven't really got one predictor。

 we're going to have， if KS5， five different predictors。And so we can look at the different theaters。

 the different predictor parameters。If they were very similar。

 that's not the reason to feel confident that our methods are giving us a certain amount。

Of uniformity， we're getting the same predictor for each one of our different subsets of the data。

On the other hand， is the predictor。😊，Prameters vary wildly。All them were less confident。That。

We've got a sensible choice of predictor coming out of our method。Here's an example。

 this is just randomly generated data。 we can see here on the left we have fitted a。😊。

A straight line。Through the data。So that's determined by two parameters。

 theta 1 plus theta2 times x is the predictor。And then we do。

 we split the data five ways and do fivefold cross validation。That gives us five different results。

 each of which is a training loss and has a training loss and a test loss。And we can see that， well。

 typically the test loss， it not that different from the training loss， it's a good sign like there。

And there's some variability in the test loss， the test smallest test loss we see here is 0。0027。

 the largest test loss is 0。0071， but that's either way， it's still very small。😊。

The Theta parameters where we also see some variability there in particular in Theta1。

 but it's rather a small number again。It's going to be 0。003 up to 0。012。U to minus 0。012。

And see two is about one。You can see that， of course， when we plot the。Different predictors。

Each of the different predictors， those are really five different plots here on this curve。

 there are really five lines on top of each other。They're all so close to each other that we can't really tell the difference。

Of course， when you're in high dimensions you can't necessarily plot your predictors。

 but you can look at theta1 and the different Theta parameters and you can look at the training loss and the test loss。

We might want to be even more confident than simply having five different results。😊。

Here's how you might do that。You take the data。And split it into a training and test split， say 8020。

 but completely randomly。😊，Train the predictor using the training data and then evaluate the predictor on the test data。

And then repeated it them again a thousand different times。😊。

So here's how you' making gain a little bit more confidence。😊。

You might split the data into a training and test split。Say 8020 randomly。

Then you train the predictor using the training data。And you evaluated it on the test data。

Now you repeat that a thousand times。And then you'll have a thousand different。Test errors。

You can plot the histogram of those test errors and see how much variation is there。😊。

And we can see right here that。The mean test error in this example is about 0。05。

AndIf we look back to our previous data， it's not that inconsistent between where we see so arrows between 0。

027 and 0。071 and couple here around 0。05。And so really。

 we can be confident that when we try this on new test data。

We would expect to see something around 0。05， at least if our entire data set。

Is representative of unseen data。And we can also see that there's going to be some variation even with the data set the size that we have。

We're going to see sometimes we're going to see some significant test errors of 0。015， 0。02。Okay。

 one last topic in this section and that is what do you do once you've chosen a predictor？Well。

 one thing you have to be careful is of is that。😊，You've revisited this test set too many times。

 even if you kept one test set in escrow， you trained based on the date on the training set。

And then you evaluated your predictor on the test set and you decided that the project wasn't very good。

Well suddenly you're taking information from that test set and using it in your training procedure。

 and when you do it again and again and again， information is leaking from the test set。

Into your training procedure， your learning based in part on the test set。

And so it's no longer a really。Honest simulation of how well the model will do on data you've never seen。

Of course， there's a trick to avoid this and the trick to avoid this is to split the original data instead of into two data sets into three data sets。

😊，A training set。And's how we fit multiple candidate models。

A validation data set which we evaluate the performance of our models on。And then a test dataset set。

 which is pristine， it's untouched， we keep it to one side when we never look at it。

 or we look at it once。That tells us how well we've done。

But then we don't go back and change our predictor once we've looked at it。嗯。This of course。

 is a little bit more honest。Some people will say that it's taking it into extremes。

And this really depends on how much leakage information there is from your test set into your training set。

 from your validation set into your training set。Now， some practitioners do this， others do not。Also。

 the names of test and validation are not really well。Seettled。

 some people reverse the terminology and refer to the pristine set as the validation set and the test set as the thing that's used to evaluate the performance of models。

In this course， we won't go to this extreme， we'll simply use。One test set and one validation set。

And it we'll use out a sample Pfold cross validation。

One more thing you can do is that you're satisfied at the end of the day。

 you've done train validation and tests and you've got a predictor that you're pretty happy with。

Now you could just stop there and say that's a predictor。

 we're going to use it and we're happy with it。😊，Another thing you can do is you can say， well。

 what we've really validated is not the predictor but。The procedure， the learning algorithm。

 which we're using to develop the predictor。And so why not just take that learning algorithm。

 which we're happy with and now apply it to the whole data set so that it can learn from all of the data we have。

 not just the。😊，Pieace that we used for training。奶奶。It is a very common practice。

And there's nothing wrong with it， it works very well， many people do this。So for example。

 you might train K nearest neighbor predictors for various values of K。

Validation suggest that KS6 is a good choice。Now the final predictor you supply is a key nearest neighbors predictor with K is6。

 but it uses all of the data。Okay， in this section， we've talked about evaluating。Predicctorors。

In the previous section， we talked about different predictors that we could have。嗯。

We've yet to talk about how you might make predictors and how you might learn and that's of course。

 coming in this class。But right now， you're in a position where。If somebody gives you a predictor。

 you can decide whether it's good or not。But also you're in a position where。

The stage for this course has been set。We know what we're trying to do now with this class。

 we're trying to develop predictors。We know how once we've got predictors。

 how we're going to evaluate them， how we're going to tell good predictors from bad predictors。

And what's next is to go ahead and make some。

![](img/6ab4e081b89af7ef14edc78604c79dc1_3.png)