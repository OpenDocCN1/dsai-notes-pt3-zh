# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P100：11_逻辑回归实验（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Allright， now let's get started with question number6 here we will actually start to predict each one of our different labels as well as start storing the probabilities。

 and that's because as we spoke about during lecture。

 when we want to do certain scoring such as the ROC curve， we're going to need the probabilities。

 whereas when we're trying to do the accuracy or the precision or the recall we'll need the actual predicted labels。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_1.png)

So we're going to start off with。Creating an empty list。

 which is just going to be our different predictions for each one of our different models。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_3.png)

And then our list of probabilities， which is just going to be the probabilities for each one of our different classes for each one of our different models。

 so for each model there'll be six different probabilities and we'll see how that looks in just a second。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_5.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_6.png)

We're then going to create this list of coefficient labels in coefficient models。

 which is going to be similar to what we've seen before so that when we zip these two together。

 we'll be able to access both a labeling as well as the actual model。

 and we're going to access those as lab and mod。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_8.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_9.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_10.png)

So the first thing that we're going to do is take our empty list， whyP。

 and we're going to append a Pada series。That's just going to be the prediction for each value in our X test。

 so X test is our holdout set we can call model dot predicts like we've done before with other with our linear regression model。

 it works the same this time it will output a label either 0，1，2，3，4 or5。

And then we're going to name that series， every series is similar to a column within a pandas data frame。

 we will name that according to the label， whether that's LR， L1 or L2。

 so that will have a prediction for each one of these different models that we created。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_12.png)

The next thing that we're going to do is create a multile index again。

Using the levels are going to be at the top level is going to be which model we're using so here we're using LR L1 or L2 and then for each one of those we're going to have a output of probabilities so we need a different column for each one of our different labels。

 so it's going to be the probability for label0 for label 1 for label 2 etc。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_14.png)

We're then going to call mod do predictic Praba here。

 and that will get us that probabilities and to show you what that looks like。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_16.png)

I'm going to pull out one of our models， which is LR and call that predicts。Proba。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_18.png)

And we're going to do that on X test as we have here。And if we look at the shape。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_20.png)

We'll see that we have 3090 rows and six columns， so X test was going to be 3090 in length and then for each one of those 3090 rows。

And then for each one of those different rows， we predict the probability of each one of the classes。

 And this looks a little bit cleaner if we look at a data frame rather than array。

 So let's take that original array and look at what this actually looks like。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_22.png)

We have， you know， label zero is very unlikely whereas label 3 here is very likely because it's around 0。

99 and we'll see how that factors into actually coming up with the prediction as well in just a second。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_24.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_25.png)

So we have that again， outputting a data frame for each one of our different models。

 so we're going to have to have that again， multilevel index where we have both the model as well as what we see here。

0，1，2，3，4，5， the predicted probability for each one of the different classes。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_27.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_28.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_29.png)

So we're going to pass that coF label that we created as our columns for our data frame。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_31.png)

And then we're just going to concatenate here it's going to be the prediction for each one of our models。

 and here it's going to be all the different probabilities for each one of our models。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_33.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_34.png)

So now let's look at what YP dot head now looks like。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_36.png)

It predicted 3，5，3，1，0 for L R。 It actually predicted the same values for L R， L1 and L2。

 We can see which ones were different by doing something like。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_38.png)

Yhy pre such that Y pre dot L R is not equal to。Y pred。

l1 and here we'll see some examples where it came up with different predictions。

 but there's not that many here。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_40.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_41.png)

We can then also look at our probability data frame that we created。

 and we see that it has for each one of these different classes， L R， L1， sorry， L1。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_43.png)

And L2。We have the different probabilities for each one of the classes here we see that by far。

Class3 is the highest for LR。As well as for L1。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_45.png)

As well as for L2。And that makes sense， given that if we look back here。

 that it predicted class3 for each one of those different models。

 So the way that it predicts is just which one has the highest probability。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_47.png)

So now we have our probabilities and we have our predicted labels so we can start coming up with the scores that we'd want in order to actually see how well we performed。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_49.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_50.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_51.png)

So we have here the we're going to import new metrics。

 the precision recall F score support is going to output each one of those separate scores in one function。

 it'll output the precision， the recall the F score and then the support is just going to be essentially the same as the value counts for our labels。

 so we'll see this in just a second and we're importing that f score。

We're then also going to import the confusion matrix so we can look at our different confusion matrices。

 our accuracy score， our ROC AUC score， which is that area under the curve for the ROC curve and again for that we're going to need the probabilities which is why we output it all the different probabilities and then we'll see how this label binaryized comes into play it's just the way that the ROC accept certain values。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_53.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_54.png)

So the first thing we're going to do， I'm going to import all those libraries by running that cell。

And then I'm going to show you what the score comes out as， so let's say we're working with Y test。

That's our actual values and we want to see that score again。

 it's going to have to use the actual predicted labels。

 not the probabilitiesre since we're trying to find precision recall and F score here。

So I'm going to say why test， and then I'm going to say why。Pread。

 and we want it specifically here for L。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_56.png)

开R。And we see all the different scores， we have an array we can look at thet shape。Oh， it's a tuple。

 excuse me。We can see here that we have one， two， three， four arrays。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_58.png)

The first array is going to be our precision。This precision for each one of our different labels。

 so remember it's one versus the rest， so for those that it predicted the first class it was able to get all those were correct。

 that's our precision we can and then the same for class two and class3 each one separately。

One is going to be the recall for our scores。2 is going to be the F score， and then。The last one。

 which is support， which we're not going to use is just going to give us the breakdown again。

 similar to value counts of each one of our different labels。Now， when we say average。

Equals weighted， which is what we do here。We see that instead of giving a list of all the scores。

 it's actually going to average out those scores， according to that breakdown。

 so we no longer need support， it's going to weight the scores so it's going to come up with a weighted average for each one of the scores。

 so we have a single score for precision recall F score and then support no longer is necessary。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_60.png)

So that's going to be what we use here with score。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_62.png)

Our accuracy score， we just need to pass in Y test。

 as well as our prediction for each one of our different the labels being the different models。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_64.png)

And then for the R O C AU score， we see here that we pass a label binary rise。

 That's because when you want to look at each one of the。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_66.png)

Different scores and each of the probabilities， the input just has to be similar to what we get with a one hot encoding。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_68.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_69.png)

If I call label B rise。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_71.png)

We see here that instead of saying what was our original values， which let's pull out Y test。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_73.png)

That head。We see that's 353， we see this is0， one，2，3。And we have that one at the third label。

 So that's what it's replacing。 And then here we see it's a 5。 And that's because it's 0，1，2，3，4，5。

 And that's the last label。 So it's just one hot encoding What we have here。

 That's what the label binary rise will do for us。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_75.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_76.png)

And then we're going to pass in the probabilities， which is the same shape。 When I call Y prob。

 recall that that is data frame， I believe， with 18 different columns。

 right 6 for each one of the models of our three models。 when I call a certain。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_78.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_79.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_80.png)

One of those models， we get it down to just the six columns so that these will match up with the shape of our label binary rise。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_82.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_83.png)

And then we are able to calculate for different thresholds that ROC AUC score and see that area under the curve。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_85.png)

We're then also going to save our confusion matrix。

 here we're creating a dictionary so we just get for each one of our labels what the confusion matrix is and we'll see this in the next cell。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_87.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_88.png)

And then for our metrics， our list， we're just going to create a series that has our precision。

 our recall， our F score， our accuracy， our area under the curve for each one of our different labels。

 we can canate that together。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_90.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_91.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_92.png)

And we can see our metrics for each one， which are fairly high for each one of these different metrics。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_94.png)

So we have our precision， recall， F score， and accuracyacies and area under the curve for each one of these different values。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_96.png)

The final thing that we're going to do here。Is we're going to plot out our confusion matrix for each one of our different labels。

 This can be similar to before We have four different。Subplots that we want here。

 so I'm going to run this and let it run for a second， we create four subplots。

 but really there's only three models。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_98.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_99.png)

So we're saying two by two， we flatten that out as we have before。

 so our axs is just each one of those bounding boxes。

 we call flatten so we can run a clean for loop through it。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_101.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_102.png)

We're setting the size of that full image to 12 by 10。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_104.png)

We're shutting off the axis for that last one because we don't want to actually plot that last one。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_106.png)

Axless negative one。 that's going to be the last one。

 And then we're saying for ax and lab in each one of our different bounding boxes up until the last one and our coefficient labels。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_108.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_109.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_110.png)

We want to pull out our confusion matrix that we saved before in a dictionary。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_112.png)

We want to pull out for each one of the specific models。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_114.png)

And we're going to create a heat map， and that heat map will give us the densest values to where each one of our different predictions came from。

So hopefully for zero and0，1 and one， all those darkest values are across that diagonal because that means we predicted correctly。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_116.png)

And we're also annotating so we see the actual values and we're using the CM mapAP colors that we brought in earlier。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_118.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_119.png)

So if we look here， what we actually have across the rows are going to be the actual classes。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_121.png)

Whereas across the different columns are going to be what was predicted。

 So we see that one is going to be the actual class， and it predicted two。

 and those seem to be confused with one another when we use LR， same with L1 and same with L2。

 and those seem to be the most confused classes。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_123.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_124.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_125.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_126.png)

If we look back to， I believe it was。Let's scroll all the way to the top so we can see what that reference is to。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_128.png)

We passed in。 We used our。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_130.png)

Label encoder here， I'm going to reinitiate this。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_132.png)

We have to reinitiate each one of these steps。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_134.png)

And coming back to the bottom， we see that we're using LE。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_136.png)

We can look at our。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_138.png)

LE doc classes。And we can see which ones are getting confused。 Lang is 0， Sitting is one。

 standingd is 2。 So it seems that sitting and standing are getting confused with one another。

 which may is wife， any of you have Apple watches that remind you to stand every once in a while。

 and you're like， wait， I just stood。 This is similar to the algorithm that's being used in order to predict sit or stand。



![](img/9472d88b9d2ea4daf1fd2c7beca99026_140.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_141.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_142.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_143.png)

That closes out our lab here on logistic regression as well as errormetrics。

 and with that we look forward to seeing you back in lecture where we will get started with Can nearest neighbors All right。

 I'll see you there。😊。

![](img/9472d88b9d2ea4daf1fd2c7beca99026_145.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_146.png)

![](img/9472d88b9d2ea4daf1fd2c7beca99026_147.png)