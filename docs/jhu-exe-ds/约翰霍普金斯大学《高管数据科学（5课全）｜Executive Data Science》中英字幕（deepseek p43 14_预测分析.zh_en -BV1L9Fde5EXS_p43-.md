# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p43 14_预测分析.zh_en -BV1L9Fde5EXS_p43-

This lecture gives an example of how to think about formal modeling in a prediction setting。



![](img/e97a5ce6871f7b6860041ecca5c431fa_1.png)

With associational analyses， the basic goal is to determine whether a key predictor and an outcome are associated with each other in the presence of many other potentially confounding factors。

 but sometimes you want to be able to predict the outcome with all of the available information that you have So usually you don't necessarily have to distinguish between say a key predictor and a set of other predictors you just want to use all the information and furthermore。

 it doesn't matter kind of if the variables are related to the outcome in some sort of causal or mechanistic way but if they carry any information at all about the outcome。

 they may be useful in a prediction setting and you might want to use them because you're usually not interested in developing a kind of detailed understanding of how the variables are related to each other or about how they're related to the outcome you just want to be able to produce solid and high quality predictions and so any variable that could play a role in that might be useful to you。

So what are the expectations that we have about prediction problems so when we build a prediction model。

 the thing that we want is to be able to produce find a feature or a set of features that can produce good separation in the outcome because typically the outcome is typically going to be some binary outcome or some multi-class outcome where that can take either two values or just a handful of values that is a typical setup of a prediction problem and you want to be able to separate the two classes using a set of features that you collect and a model that you develop so here's a very simple example of a single predictor on a binary outcome that produces very good separation this data is simulated so I just want to show you so you can see what it looks like on the y axis I have the values of the outcome which are just zero and one。

 So it's binary outcome you can think of this as like not having the disease and having the disease or or any sort of kind of binary class outcome like that on the X axis。

Here I've got a simulated predictor that ranges between these say minus2 and 2 roughly and it's continuous so it takes all the different values in between there and I can see that。

There's a gray area here that I've highlighted in the plot that's kind of near the middle and you can see that in that gray area that the outcome can take value will take value 0 and1。

 depending on the value of the predictor。 So the outcome can take either value in that gray area to the right of the gray area you'll notice that the outcome is always one and to the left of the gray area you'll see that the outcome is always zero so the goal of most prediction algorithms is essentially to minimize the size of that gray area because that gray area is the area where you have the most uncertainty。

 It's because this is where this is the range of the predictor where the outcome can actually take both value so you have some uncertainty there。

 once you're outside that gray area， you have almost absolute certainty because itll the outcome will either be zero or one So the goal is to minimize the size of this gray area using some set of features that you can collect。

So for this example， I'm going to use a data on the creditworthiness of a group of individuals and the data is taken from the UCI machine learning repository。

 which is an excellent repository for all kinds of machine learning and prediction types of data sets So the data classifies individuals into good credit or bad credit worthiness and they include a variety of variables to help you to predict the credit worthiness of these people So the basic process that we'll go through here is we'll firstll split the data into a training and test set then we'll fit the model to the training data and we'll make predictions based on the model but on the test data and then we'll compare the predictions on the test data to the truth that we know from the test data to see how well we did So here are some of the results from the model that we fit I won't get into the details of the model because it doesn't really matter at this point but here's a plot that you might make and the basic idea here is on the X axis that we have our predicted probability of being good a good credit quality and on the。

Y axis is we have the actual truth or whether you're a good or a bad credit。

 you have good or bad credit， because this is the test data set。 we actually know the truth。

 And so we can compare the truth with what our prediction says。

 And so a couple things you'll notice here。 First of all。

 you'll notice that doesn't quite look like that picture that where I simulated the data。

 So it doesn't quite match our expectations of having this very good separation。

 all along the range of the X axis， as you'll see there are both values of bad and good。

 And so the separation isn't necessarily so good。 Now you'll notice that there's a big clump of points in in the range of on the X axises about 0。

6， there are mostly in the good credit qualities category。

 And so as you can see as the predicted probability goes up。

 you'll see that the the number of the number of actual good credit quality people increases。

 So there is at least an association there。 So that's good。 But one thing you'll notice is that the。

The prediction scores are all kind of on the high end， they're all in basically greater than a half。

 and so there isn't a lot of range there。So ultimately it's not clear that this prediction algorithm is particularly good and it seems like it's having some difficulty finding out。

 finding a good combination of features that can separate people with good and bad credit risk。

 something that can also be helpful is to compute a set of summary statistics about the prediction algorithm and you can see that here。

So here at the very top is what's called the confusion matrix and it shows the number of predictions that are in the kind of truth。

 bad or good， that's called the reference， and then what we predict to be bad or good。

And you'll notice。Immediately that most of the predictions are just of good。

 So the algorithm just basically classifies everyone as good credit quality。

 So and and I guess that makes sense because most of the individuals in this data set have good credit quality。

 So if you were to make a prediction， it be easiest just to say you're a good credit you have good credit and then your prediction would be right about 70% of the time。

And you can see that the accuracy of the algorithm is about 70% and so that's okay。

 but the problem is that the algorithm's specificity is very poor。

 which means that if you actually have bad credit， the probability that the algorithm will classify you as such is only about 2。

6% so it's very low， so if you truly have bad credit。

 the algorithm will have difficult time picking that up。



![](img/e97a5ce6871f7b6860041ecca5c431fa_3.png)

So there are a couple things to think about when you see the results of a prediction model like this one and so the first thing to think about is prediction quality okay first you have to ask yourself is the model's accuracy good enough for your purposes so you saw the summary statistics from this particular model which is okay it had 7% accuracy had 2。

6% specificity is that good enough for your purposes well it depends on what your purposes are for example。

 in many medical applications where the outcome is， for example， the presence of a disease。

 you may want that test or that algorithm to have a very high sensitivity。

 So if they truly have the disease， you want the algorithm to pick it up because then you can send them into treatment and then kind of send them down the road to recovery however。

 if the treatment for that disease is very painful or there are a lot of bad side effects you may want to be careful about exactly who you send out the treatment and particularly you wouldn't want to send someone who didn't have the disease to a treatment that's going to be very painful and have a lot of side effects so there you would make sure。

you would want to make sure that if someone does not have the disease that you pick that the algorithm picks that up。

There are different metrics that you going' want to favor over each other。

 depending on kind of the decision that will be made and the consequences of those decisions。 And so。

 for example， in a financial application like the data we just look at with good and bad credit quality。

 there may be asymmetric costs associated with mistaking good credit for bad versus bad credit for good。

 So one scenario might have very little cost or another scenario might have very high costs。

 And so you want to be you want to think about given given the outcomes of your decision。

 what types of metrics you want whether the sensitivity。

 your specificity or all these other kinds of metrics。

 which ones are going be most important to you in your setting。

 every setting is going to be a little bit different And so you're not going to always want to focus on a given metric for every single application。

So a hallmark of almost all prediction algorithms is tuning parameters。

 Most algorithms have lots and lots of tuning parameters and even though they're called tuning parameters。

 they can often have a very big impact on the prediction quality of the algorithm depending on how you set them And so so you should be careful about how you set them and how you change them around now there's no prediction algorithm that I'm aware of where a single set of tuning parameters works fine for all problems So for any new data set that you bring into a prediction algorithm。

 you're probably have to tune it a little bit and that's okay but the most thing the most important thing。

 excuse me， is that you're going want to make sure you keep track of all the tuning parameters that you set and the process through which you choose these tuning parameters because ultimately you're going to want this model to be reproducible and if you cant figure you can't remember or you can't reproduce the tuning parameters。

 you'll never be able to reproduce the algorithm itself。

So last thing I want to mention is about the availability of other data。

Many prediction algorithms these days are very good at exploring the structure of complex data and making very good predictions。

 especially once you get the tuning parameters right。

 And so but now it may be that if your model is not working very well that you have to change to another algorithm or another procedure because there are different procedures can work well in different settings in different types of data structures and different types of data a setup and so it's not necessarily true that the algorithms are exchangeable。

 you may want to change the algorithm。 however， if you try a few algorithms and they all seem to be producing kind of a similar quality of prediction regardless of how well you tune them。

 it may be time to get more data or other data to help you predict the outcome。

 it could just be that the data set you have only has an intrinsic amount of ability to predict whatever outcome you're interested in and you have to kind get other data that will have better predictive power and so think about that as you're building prediction algorithms and you're seeing the results that there always might be this possibility that you have to bring in additional data to improve your prediction。



![](img/e97a5ce6871f7b6860041ecca5c431fa_5.png)