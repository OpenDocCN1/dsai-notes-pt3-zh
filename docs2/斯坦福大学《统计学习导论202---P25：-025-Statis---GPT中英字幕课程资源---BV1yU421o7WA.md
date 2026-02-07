# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P25：-025-Statistical Learning_ 4.R.2 Linear Discriminant Analysis.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Okay， well， welcome back， we're going to have our session now and once again we'll use our studio。

Which is very convenient platform for running R and for demonstrating R。

 So we'll go to our screen now and and we'll do our studio session on linear discriminant analysis。

 first of all。And then followed by nearest neighbor classification。So here we own our studio。

Session window， and the first thing we do is we require ISLR that's our package with some of our data sets。

So I hit the control button and return and it loads the package and then we require the mass package。

Which is ven in Ripleley's package of， of useful functions。

 and including the function for doing linear discriminant analysis。

You'll see in the right hand panel I've got a help file for linear discriminants analysis。

 so as always in R if you don't know or you're not too familiar with a new procedure。

 you do help and make sure you understand the syntax and all the options and so on。So。

The first thing we do， we're going to use the stock market data here。

 and the the response is going to be the direction。That the market took on a particular day。

 and we're going to use the， the returns on the previous two days to try and predict the direction。

 on， on this particular day。And so there we use a command LDA do。And it takes a formula。

 so the response is direction。They're the two predictors。

 It's telling you the data comes from S market， stock market。

And were going to use the subset which is years less than 2005 and because later on we're going to make predictions for year 2005 so you can put that directly in the formula subset equals year less than 2005 and this variable year of course is referenced in S market as well as these variables over year Okay so if we go and we fitted it。

And。It fits it so very quickly。 and we print it by just typing its name。

 And there's a little summary printed below you。And you see。

 gives typically you get the formula that was used to create it。

 and then it gives a summary of the linear discriminant analysis。

 So the prior probabilities are just the proportions of ups and downs in the data。 It's roughly 50%。

Which says something about the market， right。It's kind of a random walk half the time it's goes up。

 halflf the time it goes down。It summarizes the group means for the two groups。

For the downs and the ups。Looks like maybe a slight difference。In in these two groups。

 the means seem to be separated a little bit。 And then it gives the LDA coefficients。

 So if you remember， the LDA function fits a linear function for separating the two groups。And。

 and so it's got two coefficients。Okay， well， you there's some methods that work for LDA。

 for example， you can plottter LDA foot， which well do yeah， and it gives a very convenient plot。

ItIt plots a linear discriminant function。

![](img/ed220e65e009390a78549ae205d2626a_1.png)

Separately， the values of the linear discriminant function。

 separately for the the up group and the down group。



![](img/ed220e65e009390a78549ae205d2626a_3.png)

And when we look at this， it looks to the eye like there's really not much difference。

 those two histograms look pretty much on top of each other。



![](img/ed220e65e009390a78549ae205d2626a_5.png)

![](img/ed220e65e009390a78549ae205d2626a_6.png)

Which， of course， is not a big surprise because if we could very easily like this。

 predict the movement of the stock market， we'd be making lots of money。

 and we wouldn't be sitting there given our demonstrations。



![](img/ed220e65e009390a78549ae205d2626a_8.png)

![](img/ed220e65e009390a78549ae205d2626a_9.png)

![](img/ed220e65e009390a78549ae205d2626a_10.png)

So now we're going to see how well our rule predicts on the year 2005。



![](img/ed220e65e009390a78549ae205d2626a_12.png)

And I'm doing this in a slightly different way as to what was described in the book。



![](img/ed220e65e009390a78549ae205d2626a_14.png)

嗯。We first of all， make a subset of the data frame S market， and we'll call it Smarket do 2005。



![](img/ed220e65e009390a78549ae205d2626a_16.png)

![](img/ed220e65e009390a78549ae205d2626a_17.png)

And we use a command in our useful command called subset。

 And so the first argument is the data frame that you're going to subset， which is S market and then。



![](img/ed220e65e009390a78549ae205d2626a_19.png)

![](img/ed220e65e009390a78549ae205d2626a_20.png)

Following that are some logical expressions that can use variables in that data frame to define the subset。

 and so here it is years equals 2005。

![](img/ed220e65e009390a78549ae205d2626a_22.png)

![](img/ed220e65e009390a78549ae205d2626a_23.png)

Okay， and that will create。

![](img/ed220e65e009390a78549ae205d2626a_25.png)

The data frame with just the year 2005 observations。



![](img/ed220e65e009390a78549ae205d2626a_27.png)

Okay， and so now we can use that as the， the test data or the the place where we want to make our predictions。

 So we call。

![](img/ed220e65e009390a78549ae205d2626a_29.png)

![](img/ed220e65e009390a78549ae205d2626a_30.png)

LDA we called the predict method for an LDA fit。

![](img/ed220e65e009390a78549ae205d2626a_32.png)

And we give it outfit and we give it this new data frame， S market 2005。



![](img/ed220e65e009390a78549ae205d2626a_34.png)

And it'll produce some predictions for us。 And let's just print the first five of these。



![](img/ed220e65e009390a78549ae205d2626a_36.png)

And oops， didn't like that。 So it's not I was assuming it was in a matrix format。



![](img/ed220e65e009390a78549ae205d2626a_38.png)

![](img/ed220e65e009390a78549ae205d2626a_39.png)

And it's not。So what format is it so we don't throw up our hands and run away when we an error。

 we just investigate。 So let's look at the class of LDA dot pre。 Well， it's a list。



![](img/ed220e65e009390a78549ae205d2626a_41.png)

![](img/ed220e65e009390a78549ae205d2626a_42.png)

Now I happen to know what kind of listed is， and when you have a list of variables and each of the variables have the same number of observations。



![](img/ed220e65e009390a78549ae205d2626a_44.png)

![](img/ed220e65e009390a78549ae205d2626a_45.png)

![](img/ed220e65e009390a78549ae205d2626a_46.png)

The convenient way of looking at such a list is through data frame。

And so we can do data frame of LDA pre and then look at the first five rows。



![](img/ed220e65e009390a78549ae205d2626a_48.png)

![](img/ed220e65e009390a78549ae205d2626a_49.png)

And this is what we get。And。

![](img/ed220e65e009390a78549ae205d2626a_51.png)

You'll see what it gives is it gives a row name。It gives the classification。 The first five all up。



![](img/ed220e65e009390a78549ae205d2626a_53.png)

two of the comp one of the components of the list was a matrix of posterior probabilities。

 which had actually a two column matrix。 But data frames smart enough to。

 to understand that that can also get。

![](img/ed220e65e009390a78549ae205d2626a_55.png)

![](img/ed220e65e009390a78549ae205d2626a_56.png)

![](img/ed220e65e009390a78549ae205d2626a_57.png)

You know， that that， that these can fit into the data frame。 And so it makes two columns， one。



![](img/ed220e65e009390a78549ae205d2626a_59.png)

For up and one for down， the posterior probabilities。

 And then there's the actual values of the LDA score。



![](img/ed220e65e009390a78549ae205d2626a_61.png)

Okay。

![](img/ed220e65e009390a78549ae205d2626a_63.png)

And so now we can now we realize that the。The output of pre has these different components。

 The thing we're really interested in here is the classification。 So that's class。

 So we're going to do a table of LDA pre dollar class。

 That's a true class label for the 2005 versus the prediction。😊。



![](img/ed220e65e009390a78549ae205d2626a_65.png)

![](img/ed220e65e009390a78549ae205d2626a_66.png)

![](img/ed220e65e009390a78549ae205d2626a_67.png)

![](img/ed220e65e009390a78549ae205d2626a_68.png)

嗯。Sorry， that is the prediction versus the true value， right， So this is the predicted class。

 and this is the true value over in the data frame。 We'll do a table of that。



![](img/ed220e65e009390a78549ae205d2626a_70.png)

![](img/ed220e65e009390a78549ae205d2626a_71.png)

Right， and's we get the little confusion matrix， which tells us which downs were classified as down。

 which downs were classified as up and so on， okay。



![](img/ed220e65e009390a78549ae205d2626a_73.png)

![](img/ed220e65e009390a78549ae205d2626a_74.png)

And it's the off diagonal elements of those that are the mistakes。



![](img/ed220e65e009390a78549ae205d2626a_76.png)

And， and the diagonal elements， which are the correct classifications。

 And so one simple command tells us our。

![](img/ed220e65e009390a78549ae205d2626a_78.png)

![](img/ed220e65e009390a78549ae205d2626a_79.png)

Correct classification rate， which is we， weve got a conditional yeah。

 which is the predicted class is equal to the true class。



![](img/ed220e65e009390a78549ae205d2626a_81.png)

So that'll be true if they're equal and it'll be false if they're not。



![](img/ed220e65e009390a78549ae205d2626a_83.png)

And since truths and forces can be coerced to be zeros and ones， we can just take the mean of that。

 and it'll give us our。

![](img/ed220e65e009390a78549ae205d2626a_85.png)

![](img/ed220e65e009390a78549ae205d2626a_86.png)

Correct classification rate， which in this case is about 0。56。



![](img/ed220e65e009390a78549ae205d2626a_88.png)

So it's not huge， but again， in in， in this kind of industry， any little edge like that。

 that actually helps。

![](img/ed220e65e009390a78549ae205d2626a_90.png)

![](img/ed220e65e009390a78549ae205d2626a_91.png)

So that's a little session using linear discriminant analysis。 And there's many other approaches。

 There are more examples in the book。 And you should have a look there。



![](img/ed220e65e009390a78549ae205d2626a_93.png)