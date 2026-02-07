# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P143：54_boosting笔记本（选修部分）第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to question number three in our notebook。Here we're going to be using gradient booth in models。

 and the goal of this question is to loop through different numbers of trees and see how our accuracy tends to increase or decrease as we increase that number of trees。



![](img/d970090f0a2e272b44b760d16fe1e7e5_1.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_2.png)

Now some things to note is we set max features equal to five， if you recall just from last video。

 we have 561 different features available to us。If we let it run on all 561 features。

This will take very， very long to actually fit our model。 So this is a way to just speed things up。

 The accuracy tends to be around the same for this given model， that's not always the case。

 If you want to test it on your own， note that this could take again。

25 to 30 minutes in order to actually run。 if you set max features equal to none and allow it to run through every single feature。

 But here， we set it to five features， just to ensure that it runs a bit quicker。



![](img/d970090f0a2e272b44b760d16fe1e7e5_4.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_5.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_6.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_7.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_8.png)

The other thing to note is that we when we did bagging in our last notebook。

 we were able to use something like this warm flag so that we didn't have to keep reinitiating or keep relearning the trees that we learned before as we increase that number of trees there's a bit of a bug in the boosted models so we won't be able to do that as well。

 Also there's no out of bag error since we're training on the full data set when we do any type of boosting compared to bagging remember with bagging we have that bootsrapping whereas with boosting。

 we're just trying to fix on past errors。

![](img/d970090f0a2e272b44b760d16fe1e7e5_10.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_11.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_12.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_13.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_14.png)

And then also because this is done successively， because we're fitting each one of these trees successively。

You have to note that this will take a longer time than baggging because we can't fit the next tree until we fit the tree before and so on and so forth。

So the first thing that we want to do is import our gradient boosting classifier。



![](img/d970090f0a2e272b44b760d16fe1e7e5_16.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_17.png)

We're then also going to import our accuracy score。

 what we want to measure here is going to be our error rate。

 which will just be1 minus the accuracy score。

![](img/d970090f0a2e272b44b760d16fe1e7e5_19.png)

We're then going to set our tree list， which is just 15 through 400 with each one of these different numbers。

 and we're going to want to for loop through each one of these different possible number of trees that we're going to run through。



![](img/d970090f0a2e272b44b760d16fe1e7e5_21.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_22.png)

So each step in our for loop。We initiate our gradient boosting classifier。 Again。

 we set max features equal to 5 to ensure that doesn't run for too long。



![](img/d970090f0a2e272b44b760d16fe1e7e5_24.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_25.png)

We set our number of estimators equal to this n trees variable。

 which will just be wherever we are within our list that we have here in our tree list。

 and we set our random state equal to 42。

![](img/d970090f0a2e272b44b760d16fe1e7e5_27.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_28.png)

We're then just going to print out at each step along the for loop where we are in the for loop。

 so we're fitting model for n trees for that number of trees。



![](img/d970090f0a2e272b44b760d16fe1e7e5_30.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_31.png)

We're then going to fit our initiated model with that number of trees on our training set。

 so on X train and Y train， and then we are going to come up with the prediction on our test set using Gc。

pred。

![](img/d970090f0a2e272b44b760d16fe1e7e5_33.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_34.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_35.png)

So then once we have our predictions， we can use our accuracy score。



![](img/d970090f0a2e272b44b760d16fe1e7e5_37.png)

Pass in our test values， the actual values， as well as our predicted values。

1 minus that accuracy score will be our error。 We'll append that to this error list that we initiated at the top before our for loop so that we have。



![](img/d970090f0a2e272b44b760d16fe1e7e5_39.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_40.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_41.png)

At each step， a panda series with a number of trees as well as the actual error。



![](img/d970090f0a2e272b44b760d16fe1e7e5_43.png)

And then we can concatenate those all together to create our era data frame that we'll see。

 and as we've seen in past notebooks as well。

![](img/d970090f0a2e272b44b760d16fe1e7e5_45.png)

So I'm going to run this， and this will take about maybe a minute to run here。

 as you see it's looping through each one of these different options。

 and it did it fairly quickly for 15，25， 50 trees， and you see that slowing down as asked to fit more and more trees。



![](img/d970090f0a2e272b44b760d16fe1e7e5_47.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_48.png)

So I'm going to pause the video here。

![](img/d970090f0a2e272b44b760d16fe1e7e5_50.png)

And we will come back as soon as it's done， running through each one of these trees。



![](img/d970090f0a2e272b44b760d16fe1e7e5_52.png)

So hopefully that didn't take you guys too long， didn't take too long on my end。

 and then once we ran through each one of those different numbers of trees。

 we were able to output that error data frame， which gives us as our index， that number of trees。

 and then for the values for that error， we saw the actual error rate as we increase the number of trees。



![](img/d970090f0a2e272b44b760d16fe1e7e5_54.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_55.png)

And we see here as we increase the number of trees， we keep decreasing that error rate。

And as we get towards higher numbers of trees， we see this diminishing returns as we increase those numbers of trees。



![](img/d970090f0a2e272b44b760d16fe1e7e5_57.png)

So we're then going to plot out this error data frame。So we call AirDF。

 which is going to be our data frame， dot plots or using the Padas functionality for plotting。

We set our marker to just be that circle。We set our fig size to 12 by 8。

 and we're going to connect it with a line and we're setting that line with equal to five。



![](img/d970090f0a2e272b44b760d16fe1e7e5_59.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_60.png)

We're then going to set our X label to number of trees。

 and that's going to reference the number of trees that index here。

 and the Y label will be the actual error。

![](img/d970090f0a2e272b44b760d16fe1e7e5_62.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_63.png)

And then we're going to set our x limits from zero to the max error index max maximum of the Air DF index。

 that index again is just this number of trees， so the maximum value will be 400 times 1。

1 will be 440， so we're setting it for values between 0 and 440 on that x axis。



![](img/d970090f0a2e272b44b760d16fe1e7e5_65.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_66.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_67.png)

And when we plot it， we see this diminishing error as we continue to increase the number of trees。

 and we see that somewhat plateau from 200 to 400 is a slight increase at 400。

 but probably will plateau moving forward。

![](img/d970090f0a2e272b44b760d16fe1e7e5_69.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_70.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_71.png)

Now for question number four。We're going to use a grid search with cross validation to fit a new gradient boosted classifier。



![](img/d970090f0a2e272b44b760d16fe1e7e5_73.png)

Here we're going to be setting the number of trees equal to 400s。

 So we're not going to loop through that。 But in practice。

 you may want to actually loop through these number of estimators again。

 If you recall during lecture， we discuss how there's a relationship between the learning rate and the number of trees。

 And if you have a lower learning rate， you probably want more trees。



![](img/d970090f0a2e272b44b760d16fe1e7e5_75.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_76.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_77.png)

Ands perhaps you'd be able to come up with a better model， but it will take a very long time to run。

 So keeping it at 400 just to ensure that it won't take too long as we run。

 This will take quite some time still， given the parameters that we're using。



![](img/d970090f0a2e272b44b760d16fe1e7e5_79.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_80.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_81.png)

We're then going to try varying the learning rates。 the sub samplingling values。

 So recall that the sub samplingampling value is just going to be how much of that training set we're actually going to be learning on for each one of the trees。

 If we say only 50%， then rather than using the full training set， or using a portion of it。

 and this adds a bit of regularization to our model。



![](img/d970090f0a2e272b44b760d16fe1e7e5_83.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_84.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_85.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_86.png)

And then we're going to use different number of maximum features with the lower numbers。

 meaning more regularization and the more features we allow， the more complex that model can be。



![](img/d970090f0a2e272b44b760d16fe1e7e5_88.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_89.png)

We're then going to examine the best parameters。

![](img/d970090f0a2e272b44b760d16fe1e7e5_91.png)

For the best fit model。 So what are the parameters our output。

 we're going to calculate the relevant error metrics on this model。

 So all those error metrics that we discussed in past lectures。



![](img/d970090f0a2e272b44b760d16fe1e7e5_93.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_94.png)

And again， I want to note that this will take some time to run。 So as before， I'm going to say。

 I'm going to let it run， and then I'm going to pause， but I will also show you。

 so that you don't have to keep rerunning this code if you lose your model or your kernel shuts down。

 how to actually save that model and reuse it later on or bring it back into your memory later on。



![](img/d970090f0a2e272b44b760d16fe1e7e5_96.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_97.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_98.png)

So in order to create our model， first we import grid search CV。



![](img/d970090f0a2e272b44b760d16fe1e7e5_100.png)

We're then going to set a parameter grid， we're setting our learning rate to values looping through 0。

10。01 and 0。001， our subsample are 1 and 0。5 and our max features are 2，3 and 4。



![](img/d970090f0a2e272b44b760d16fe1e7e5_102.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_103.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_104.png)

We're then going to pass in our actual classifier。

![](img/d970090f0a2e272b44b760d16fe1e7e5_106.png)

And here we see that that's going to be great at boost classifier with the default of the number of estimators equal to 400。

 so no matter what we loop through for each one of these parameters。

 we're keeping that number of estimators at 400。

![](img/d970090f0a2e272b44b760d16fe1e7e5_108.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_109.png)

We're then setting our parameter grid to the parameter grid we defined above。



![](img/d970090f0a2e272b44b760d16fe1e7e5_111.png)

We're trying to optimize on accuracy and end jobs。 again。

 that's just saying how much we can run in parallel and recall that with boosting compared to bagging。

 we're not going to be able to paralyze our models as much。 So， again。

 this will take some time to run。

![](img/d970090f0a2e272b44b760d16fe1e7e5_113.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_114.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_115.png)

So now that we initiate this object， we can fit it on our training set。



![](img/d970090f0a2e272b44b760d16fe1e7e5_117.png)

So we're just going to run this year。And this will take some time to run。

 so I'll let it run and I'll see you back here when it's done running。



![](img/d970090f0a2e272b44b760d16fe1e7e5_119.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_120.png)

All right， now that may have taken quite sometimes time run， I don't know， 10 minutes or so。

Now to ensure that you don't have to keep running this。

 if you mess up at some point or if you restart your kernel， something that you can do is。



![](img/d970090f0a2e272b44b760d16fe1e7e5_122.png)

Actually， save that Python object。 So I'm going to import something called pickle。

 And what we're doing here is something called pickling。



![](img/d970090f0a2e272b44b760d16fe1e7e5_124.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_125.png)

Which will serialize our Python objects， save them as bytes。So that they're saved in a file。

 and then if we want to reintroduce them as a Python object。

 we can just pull them back out using this pickle functionality。



![](img/d970090f0a2e272b44b760d16fe1e7e5_127.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_128.png)

So the way that it works is we can do pickle dot dump。

And that's just dumping our Python object into a pickle file。So we want to save this。GV。

 GBC object that we just fit。GBC， and then we just want to。Open up a file。

 Now this will just create a new file if it doesn't exist。 I'll call this G V， GVC。

tP is a pickle file， and then we will just say whenever you call open and Python。

 you have to say what you want to do with that file here we want to write that file so that's going to be a double W。

 and then we want to write it as bytes。 so we just sayWB。



![](img/d970090f0a2e272b44b760d16fe1e7e5_130.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_131.png)

And now we've saved this object as Ggbc。p。And if later on or another notebook you want to load this up。

 assuming you're in the right directory， this actually saves it in the director you were working on。

 and we see here that our current working directory is going to be this data directory。



![](img/d970090f0a2e272b44b760d16fe1e7e5_133.png)

What we'd want to do is， actually。Call pickle do load。And just say。The file that we want to load。

 which is G V。GBC dot P。And then we would just say read bytes。



![](img/d970090f0a2e272b44b760d16fe1e7e5_135.png)

And then we'd be able to load that in。 We'd probably want to save that as an object。

 This would be the same as the G V。

![](img/d970090f0a2e272b44b760d16fe1e7e5_137.png)

GBC object that we just created。 So we can just say GBC is equal to pickle download。

And then we would load it back up。So now let's see what our best estimator was for that model。

We see that it shows max features equal to4 the number of estimators we already had set to 400。

 It actually took a sub sampleample， so subsampling， which introduced a term of regularization。

 actually helped in terms of our model， and then for the learning rates， which is in in here。

 we can just call learning。

![](img/d970090f0a2e272b44b760d16fe1e7e5_139.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_140.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_141.png)

The learning rate and see that it shows 0。1。

![](img/d970090f0a2e272b44b760d16fe1e7e5_143.png)

We're then going to use that best estimator to predict on our X test。



![](img/d970090f0a2e272b44b760d16fe1e7e5_145.png)

And see the classification report across each one of our different a。



![](img/d970090f0a2e272b44b760d16fe1e7e5_147.png)

Different values that we could be predicting here。And see what our precision， recall。

 so on and so forth。 All are。 So we run this， and we see really high scores across the board。



![](img/d970090f0a2e272b44b760d16fe1e7e5_149.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_150.png)

So for the zero class we got everything perfectly for one， maybe not as well， but still 96， 97%。

 and we see that across each of these classes， these very high values for precision。

 recall in the F1 score。

![](img/d970090f0a2e272b44b760d16fe1e7e5_152.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_153.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_154.png)

And then when we look at the overall accuracy， we see we had 99% accuracy。

 and then we have that macro average and weighted average。

 which here doesn't mean as much since the support is pretty evenly distributed。



![](img/d970090f0a2e272b44b760d16fe1e7e5_156.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_157.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_158.png)

We're then going to check our confusion matrix to see for those that we got wrong。

 Where did we go wrong， and those should be somewhere around these classes of one and 2。

 So we run this。 And we see for class 1， we're getting those two that confused with class 2 and class 2 confused with class 1。



![](img/d970090f0a2e272b44b760d16fe1e7e5_160.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_161.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_162.png)

As we see here with the 15 and 18 alongside the diagonal。

 that means that they all were classified correctly。

 So it seems that the classes 1 and 2 seem to be getting mixed up。 And if we go back up here。

 we see that。

![](img/d970090f0a2e272b44b760d16fe1e7e5_164.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_165.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_166.png)

Those were going to be sitting and standing， are getting mixed up。



![](img/d970090f0a2e272b44b760d16fe1e7e5_168.png)

So if you have an Apple Watch again， that may be that it's telling you to stand and may be confused between that sitting and standing。



![](img/d970090f0a2e272b44b760d16fe1e7e5_170.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_171.png)

Now， finally， we're going to do the same thing for add a boost。



![](img/d970090f0a2e272b44b760d16fe1e7e5_173.png)

And we're going to then compare the errors from addbu and this gradient boosted classifier we just learned。

 And again， note this will take a long time to run。 So I'm going to run this here。

 We're going to look through different estimators。

![](img/d970090f0a2e272b44b760d16fe1e7e5_175.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_176.png)

And different learning rates。 so that's all that we're going to loop through here。

 it will still take quite some time。

![](img/d970090f0a2e272b44b760d16fe1e7e5_178.png)

And。

![](img/d970090f0a2e272b44b760d16fe1e7e5_180.png)

As we discussed， if you want to change that max depth of your add boost classifier。

 This is actually the default value。 You could have also passed in different max depths here。

 We we're just going to set max depth equal to one。 So we're using a decision stump。

 And then we're using the pram grid everything the same as what we just did with gradient boosting。



![](img/d970090f0a2e272b44b760d16fe1e7e5_182.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_183.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_184.png)

Alright， so I'm going to run this and fit this on our training set。

 so now we're fitting our add a boost classifier and again， this will take some time to run。

 so I'll pause the video here and then come right back as soon as it's done running。



![](img/d970090f0a2e272b44b760d16fe1e7e5_186.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_187.png)

So that may have taken some time to fit something along 10 or maybe even a little bit more minutes in regards to fitting this model again。

 I would suggest pickling using that pickle dot dump in order to save this file I have already done that we're then going to see the best estimator。



![](img/d970090f0a2e272b44b760d16fe1e7e5_189.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_190.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_191.png)

And see that we have the learning rate of 0。01 and the number of estimators equal to 100 being our best hyperparameter here。



![](img/d970090f0a2e272b44b760d16fe1e7e5_193.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_194.png)

We can then create our prediction using that fitted model on our X test on our test set。

 and then see that classification report for our predictions and our Y test。



![](img/d970090f0a2e272b44b760d16fe1e7e5_196.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_197.png)

And we see here that we have。

![](img/d970090f0a2e272b44b760d16fe1e7e5_199.png)

A much reduced recall F1 score and accuracy score compared to what we had for gradient boosting。



![](img/d970090f0a2e272b44b760d16fe1e7e5_201.png)

We see that for class two， we're doing poorly with recall with class1 our precision and F1 score we're at zero。



![](img/d970090f0a2e272b44b760d16fe1e7e5_203.png)

And if we look at the confusion matrix。We see that we are getting that class one wrong and keep misclassifying that as a two。

 And then we see also with the threes and fives we're starting to get some of those wrong as well。



![](img/d970090f0a2e272b44b760d16fe1e7e5_205.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_206.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_207.png)

And this can be due to the fact that add boost can be greatly skewed by outliers as we discuss with the loss function used for add boostt。

So in this example， and this is not always the case。

 gradient boosting will perform better and this is why we check across different models。



![](img/d970090f0a2e272b44b760d16fe1e7e5_209.png)

Now that's going to close out this section in regards to the different boosting methods。

In the next video， we'll start to discuss the stacking method using the voting classifier and I will see you there。



![](img/d970090f0a2e272b44b760d16fe1e7e5_211.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_212.png)

![](img/d970090f0a2e272b44b760d16fe1e7e5_213.png)