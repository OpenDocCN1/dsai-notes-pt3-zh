# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P68：19_交叉验证演示第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/29f79d9ce2580b5b47cbeffbe75c489f_0.png)

Welcome to our third notebook here in the second course on cross validation In this notebook。

 we will discuss how to chain multiple data processing steps together。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_2.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_3.png)

Using the pipeline functionality， which will allow you to speed up a lot of your machine learning workflow。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_5.png)

We'll talk about using the K foldolds object to split data into multiple folds as we saw in lecture。

 and then we'll learn how to perform cross validation using SK learns cross Val predictict。

 as well as the grid search CV to see how well we are able to perform given our model on each one of these folds。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_7.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_8.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_9.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_10.png)

Now， as usual， we're going to bring in many different libraries。

 let's go down to the second line here on SKLear。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_12.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_13.png)

From model selection， we're going to bring in the objects we just mentioned。

 Kfold and cross file predicts。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_15.png)

From the linear model， we're not just going to bring in linear regression。

 but we're also going to introduce lassso and Rige regression。

 We're going to talk more about these in detail during lecture。

 but note that these are just linear regression plus a way of ensuring that you don't overfit that linear regression。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_17.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_18.png)

Then from metrics， we're bringing in the R2 score， which is just R squared， and then from pipeline。

 we're bringing in the pipeline function。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_20.png)

Now our data set this time is going to be saved in a pickle file。

 this pickle file is actually a dictionary， pickle allows us to save Python objects and be able to retrieve them easily。

So we're going to open up this pickle file that we have here。And if we look at Boston do Keys。

 we see this is a dictionary with the keys data frame and description。

 And we're going to pull out the。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_22.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_23.png)

Paandnda's data frame specifically call that Boston data。

 and then we're also going to pull out the Boston description to separate these two out into their own objects。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_25.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_26.png)

And then we see we have the pandas data frame and we can look at the first five rows and see the median value is what we're trying to predict for the housing。

 and we also have all these different features in order to help us predict that median value。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_28.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_29.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_30.png)

Now， we know given our discussion and the subject of this current notebook that our goal is going to be。

 how can we predict future values when we only have the data available us in this data set。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_32.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_33.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_34.png)

So what we're going to want to do is use K folds and separate out into three different folds。

 three different train and test sets。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_36.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_37.png)

And we want to think about how are we going to do this in Python code？



![](img/29f79d9ce2580b5b47cbeffbe75c489f_39.png)

So to code this up， the first thing that we want to do is separate out our X and y variables。

 our features x， and our target variable Y。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_41.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_42.png)

So x is just going to be equal to Boston data， and we're doing dot drop just to remove the outcome variable。

 and then y is just going to be equal to the outcome variable。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_44.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_45.png)

Then as we've done so far with SK learn， we're going to want to initiate an object。

 so we're going to initiate our K fold object before using it。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_47.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_48.png)

And we're going to pass into that initiated object， certain arguments。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_50.png)

When we say shuffle equals true， if you recall when we're looking at a data frame。

 we can take the first 10 and leave， let's say， was data frame of 100 values。

 We can take the first 10 and lead out the next 90 and then take the next 10。

 So we start off with 0 through 9， then 10 through 19。

 and each one of those can be the different test sets。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_52.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_53.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_54.png)

Or we can shuffle it and choose a random 10 to be our test set， the rest being our training set。

 and then take another random 10， and this will become clear as we actually look at the indices that we're pulling out in the next couple cells。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_56.png)

So we're going to shuffle that， so it's not just an order。And then we set our random state。

 And then the other important argument that we need to pass is the number of splits。

 So how many times do we want to split up our data frame， We're going to have three folds。

 meaning three training sets and three test sets where none of the test sets are going to overlap。

 If you recall from lecture， the training sets can overlap。 but the test sets have to be exclusive。

 so that we are looking at different test sets every single time。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_58.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_59.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_60.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_61.png)

So for。Let's actually look at what Kf。 split does for us。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_63.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_64.png)

That's going to。Give us a generator object。That generator object you can think of as a list。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_66.png)

A list where each value in that list is a tuple。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_68.png)

That tripleal is going to be first all the indices that we want to set to our train index。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_70.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_71.png)

And the second part of that tuple is going to be the test index， so it's going to be three tus。

 each one with a train index， giving all the indices taken from our data frame， taken from our X。

 so it's going to be the same size。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_73.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_74.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_75.png)

And then our test index， which is just going to be， again。

 the indices just specifying the test index。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_77.png)

So we have our train index， that's just going to be a list of numbers。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_79.png)

And that list of numbers are going to be somewhere between， let's just look at X dot shape。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_81.png)

It's going to be within 506， so values between zero and 505。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_83.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_84.png)

Right， all the way up until the end。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_86.png)

And we're going to look at the first 10 values for each one of our train and test splits。

 So that's the first 10 here。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_88.png)

And then we're also going to get the length of our train index and the length of our test index。Now。

 think about what the length of our train and test indices should be。If we're splitting into three。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_90.png)

Then we know that our test indices should be around one third of the length of our entire data set。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_92.png)

So I'm going to run this。And we see that170， which is around one third of 505。

 is going to be our test index size， and it's going to be the same for each one of these folds。

 One of them is one off just because it didn't cleanly divide by3。

 but we see that each one of these lengths for test index is going to be around one third。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_94.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_95.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_96.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_97.png)

And then the remaining two thirds are going to be the size of our training index。

 so all the values that we're going to eventually want to train our model on。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_99.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_100.png)

We also see that we have the actual indices just the first 10 here for the train index。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_102.png)

And remember the train indices can overlap。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_104.png)

And you should see some overlap here you see the two and the two。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_106.png)

2 and 2。 and there should be some overlap， but the test indices will not have any overlap。

 These are each going to be unique， and these are going to be different holdout sets。

 So we're going to train on this training set and then test on this test set。

 Then we're going to train on this train set and test on this test set and so on。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_108.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_109.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_110.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_111.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_112.png)

So now we want to see the scores for each one of our train and test splits。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_114.png)

So we're going to start off with a blank list for scores。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_116.png)

We're going to initiate our linear regression object。Now we have our predictor， it's LR。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_118.png)

And we're going to say four train index and test index in our split。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_120.png)

Again， the split was defined earlier， and we saw what that output will look like。 That'll be。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_122.png)

A train index and a test index we' run through that and then we'll get to the next duple of train and test indices。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_124.png)

We're going to set our X train， X test， Y train and Y test to the following outputs。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_126.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_127.png)

It's going to be x， so our original x with all of our rows。

 but we're only going to take the rows for our first train index。

And we're obviously going to take all of our columns from X。We're then going to take。

To set to X test。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_129.png)

All of our test indices， so now we've set the x train and the X test and then Y train is just going to be Y。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_131.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_132.png)

And it's going to be the matching train index to our X train that we specified first。

 and then we're going to set our y towards test index to match up with the X test index。

 which we defined here with X test。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_134.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_135.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_136.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_137.png)

We're then going to fit our model to our training set again， this is going to be a for loop。

 so it's going to do this three times using our first training set。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_139.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_140.png)

We're going to do Lr dotfi on X train and Y train。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_142.png)

We're going to come up with our predictions on X test。

 so again we fit to our training model and then we test what the predictions will be assuming we didn't have the labels for X test。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_144.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_145.png)

We get our prediction， and then we can say for that prediction。

 how well did we do according to the actual values？



![](img/29f79d9ce2580b5b47cbeffbe75c489f_147.png)

That we held out in our test set。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_149.png)

So we get the R2 score of Y test do values and Y pre。 So R 2 score we brought in earlier。

 You recall that was one of the metrics that we pulled in。 We set that equal to our score。

 and then we add that on our original list that we had empty at first。

 So we're going to do this for three different splits。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_151.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_152.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_153.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_154.png)

We'll run this code and you see that it will output three different results。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_156.png)

For each one of those test and training sets， and this also makes clear。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_158.png)

How you can end up with。

![](img/29f79d9ce2580b5b47cbeffbe75c489f_160.png)

Fairly different values， depending on what your test set is。

 And this highlights the importance of doing multiple folds。 And then eventually。

 if you're doing cross validation， you would end up averaging these altogether。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_162.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_163.png)

Now in the next section， we will continue with this。

 adding on scaling and then going into cross file prediction using the cross file predict functionality I'll see you there。



![](img/29f79d9ce2580b5b47cbeffbe75c489f_165.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_166.png)

![](img/29f79d9ce2580b5b47cbeffbe75c489f_167.png)