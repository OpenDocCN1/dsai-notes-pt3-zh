# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P23：P23 StatsLearning Lect10 R A LDA 111213.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

Okay， well， welcome back， We're going to have our session now and once again we'll use our studio。

which is a very convenient platform for running R and for demonstrating R。

 so we'll go to our screen now and we'll do our studio session on linear discriminant analysis first of all。

And then followed by nearest neighbor classification。So here we own our studio。Session window。

 and the first thing we do is we require ISLR that's our package with some of our data sets。

So I hit the control button and return and it loads the package and then we require the mass package。

Which is available in Ripleley's package of， of useful functions。

 and including the function for doing linear discriminant analysis。

You'll see in the right hand panel I've got a help file for linear discriminants analysis。

 so as always in R if you don't know or you're not too familiar with a new procedure。

 you do help and make sure you understand the syntax and all the options and so on。So。

The first thing we do， we're going to use the stock market data here。

 and the response is going to be the direction。That the market took on a particular day。

 and we're going to use。The， the returns on the previous two days to try and predict the direction on。

 on this particular day。And so there we use a command LDA dotfi。And it takes a formula。

 so the response is direction。They're the two predictors。

 It's telling you the data comes from S market， stock market。

And we're going to use the subset which is years less than 2005 and because later on we're going to make predictions for year 2005。

 so you can put that directly in the formula， subset equals year less than 2005。

And this variable year， of course， is referenced in S market as well as these variables over year。

 Okay， so if we go and we fitted it。And。It fits it so very quickly。

 and weprint it by just typing its name。 And there's a little summary printed below you。

And you see gives typically you get the formula that was used to create it。

 and then it gives a summary of the linear discriminants analysis。

 so the prior probabilities are just the proportions of ups and downs in the data， it's roughly 50%。

Which says something about the market， right。It's kind of a random。Walk half the time goes up。

 halflf the time it goes down。It summarizes the group means for the two groups。

For the downs and the ups。Looks like maybe a slight difference。InIn these two groups。

 the means seem to be separated a little bit， and then it gives the LDA coefficients。

 So if you remember the LDA function fits a linear function for separating the two groups and and so it's got two coefficients。

Okay， well， you there's some methods that work for LDA， for example， you can plot a LDA foot。

 which will do you and it gives a very convenient plot。ItIt plots a linear discriminant function。



![](img/4e77d5293e97b1483251969c714bd681_1.png)

Separately， the values of the linear discriminant function。

 separately for the up group and the down group。

![](img/4e77d5293e97b1483251969c714bd681_3.png)

![](img/4e77d5293e97b1483251969c714bd681_4.png)

And when we look at this， it looks to the eye like there's really not much difference。

 those two histograms look pretty much on top of each other。



![](img/4e77d5293e97b1483251969c714bd681_6.png)

Which， of course， is not a big surprise because if we could very easily like this。

 predict the movement of the stock market， we'd be making lots of money and we wouldn't be sitting here given our demonstrations。



![](img/4e77d5293e97b1483251969c714bd681_8.png)

![](img/4e77d5293e97b1483251969c714bd681_9.png)

![](img/4e77d5293e97b1483251969c714bd681_10.png)

So now we're going to see how well our rule predicts on the year 2005。



![](img/4e77d5293e97b1483251969c714bd681_12.png)

Now I'm doing this in a slightly different way as to what was described in the book。



![](img/4e77d5293e97b1483251969c714bd681_14.png)

嗯。

![](img/4e77d5293e97b1483251969c714bd681_16.png)

We first of all， make a subset of the data frame S market， and we'll call it Smarket。 2005。



![](img/4e77d5293e97b1483251969c714bd681_18.png)

And we use the command in our useful command called subset。

 And so the first argument is the data frame that you're going to subset， which is S market and then。



![](img/4e77d5293e97b1483251969c714bd681_20.png)

![](img/4e77d5293e97b1483251969c714bd681_21.png)

Following that are some logical expressions that can use variables in that data frame to define the subset。

 and so here it is year equals 2005。

![](img/4e77d5293e97b1483251969c714bd681_23.png)

![](img/4e77d5293e97b1483251969c714bd681_24.png)

Okay， and that will create。

![](img/4e77d5293e97b1483251969c714bd681_26.png)

A data frame with just the year 2005 observations。

![](img/4e77d5293e97b1483251969c714bd681_28.png)

Okay， and so now we can use that as the the test data or the the place where we want to make our predictions。

 So we call。

![](img/4e77d5293e97b1483251969c714bd681_30.png)

![](img/4e77d5293e97b1483251969c714bd681_31.png)

LDA we called the predict method for an LDA fit。

![](img/4e77d5293e97b1483251969c714bd681_33.png)

And we give it outfit and we give it this new data frame， S market 2005。



![](img/4e77d5293e97b1483251969c714bd681_35.png)

And it'll produce some predictions for us。 And let's just print the first five of these。



![](img/4e77d5293e97b1483251969c714bd681_37.png)

And oops， they' like that。 So it's not I was assuming it was in a matrix format。



![](img/4e77d5293e97b1483251969c714bd681_39.png)

![](img/4e77d5293e97b1483251969c714bd681_40.png)

And it's not。 So what format is it， So we don't。

![](img/4e77d5293e97b1483251969c714bd681_42.png)

Throw up her hands and run away when a we error， we just investigate。

 So let's look at the class of LDA dot pre。 Well， it's a list。



![](img/4e77d5293e97b1483251969c714bd681_44.png)

Now I happen to know what kind of listed is and when you have a list of variables and each of the variables have the same number of observations。



![](img/4e77d5293e97b1483251969c714bd681_46.png)

![](img/4e77d5293e97b1483251969c714bd681_47.png)

![](img/4e77d5293e97b1483251969c714bd681_48.png)

The convenient way of looking at such a list is through data frame。And so we can do。



![](img/4e77d5293e97b1483251969c714bd681_50.png)

Data frame of LDA pre。 and then look at the first five rows。



![](img/4e77d5293e97b1483251969c714bd681_52.png)

And this is what we get。And。

![](img/4e77d5293e97b1483251969c714bd681_54.png)

You'll see what it gives is it gives a row name。

![](img/4e77d5293e97b1483251969c714bd681_56.png)

It gives the classification， the first five all up。

Two of the one of the components of the list was a matrix of posterior probabilities。

 which had actually a two column matrix。 but data frame smart enough to。

 to understand that that can also get， you know that that these can fit into the data frame。

 And so it makes two columns one。

![](img/4e77d5293e97b1483251969c714bd681_58.png)

![](img/4e77d5293e97b1483251969c714bd681_59.png)

![](img/4e77d5293e97b1483251969c714bd681_60.png)

![](img/4e77d5293e97b1483251969c714bd681_61.png)

For up and one for down， the posterior probabilities。

 And then there's the actual values of the LDA score。



![](img/4e77d5293e97b1483251969c714bd681_63.png)

Okay。

![](img/4e77d5293e97b1483251969c714bd681_65.png)

And so now we can， now we realize that the。

![](img/4e77d5293e97b1483251969c714bd681_67.png)

The output of pre has these different components。 The thing we're really interested in here is the classification。

 So that's class。 So we're going to do a table of LD pre dollar class。

 That's a true class label for the 2005 versus the prediction。😊。



![](img/4e77d5293e97b1483251969c714bd681_69.png)

![](img/4e77d5293e97b1483251969c714bd681_70.png)

![](img/4e77d5293e97b1483251969c714bd681_71.png)

嗯。Sorry， that is the prediction versus the true value right so this is the predicted class and this is the true value over in the data frame。

 We'll do a table of that。

![](img/4e77d5293e97b1483251969c714bd681_73.png)

![](img/4e77d5293e97b1483251969c714bd681_74.png)

RightAnd' we get the little confusion matrix， which tells us which downs were classified as down。

 which downs were classified as up and so on。

![](img/4e77d5293e97b1483251969c714bd681_76.png)

![](img/4e77d5293e97b1483251969c714bd681_77.png)

And it's the off diagonal elements of those that are the mistakes。



![](img/4e77d5293e97b1483251969c714bd681_79.png)

And and the diagonal elements， which are the correct classifications。

 And so one simple command tells us how。

![](img/4e77d5293e97b1483251969c714bd681_81.png)

![](img/4e77d5293e97b1483251969c714bd681_82.png)

CCorrect classification rate， which is we， weve got a conditional year。

 which is the predicted class is equal to the true class。



![](img/4e77d5293e97b1483251969c714bd681_84.png)

So that'll be true if they're equal and it'll be false if they're not。



![](img/4e77d5293e97b1483251969c714bd681_86.png)

And since truths and forces can be coerced to be zeros than ones。

 we can just take the mean of that and it'll give us our。



![](img/4e77d5293e97b1483251969c714bd681_88.png)

![](img/4e77d5293e97b1483251969c714bd681_89.png)

Correct classification rate， which in this case is about 0。56。



![](img/4e77d5293e97b1483251969c714bd681_91.png)

So it's not huge， but again， in this kind of industry， any little edge like that that actually helps。



![](img/4e77d5293e97b1483251969c714bd681_93.png)

![](img/4e77d5293e97b1483251969c714bd681_94.png)

So that's a little session using linear discriminants analysis and there's many other approaches。

 there are more examples in the book and you should have a look there。



![](img/4e77d5293e97b1483251969c714bd681_96.png)