# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P64：15_训练集和测试集分割实验（选修部分）第3部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/788a54d5e2caf7951b0d074f24ad1c8f_0.png)

Welcome back to our notebook Here。 we'll cover question number4。

 where we will perform our train and test splits for both of our data sets。

 Both the original data frame with all of our string， our categorical features dropped。

 as well as the version that had created all the one hot end versions of each one of those string variables。

 So we're going to have one where there's only。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_2.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_3.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_4.png)

37 different features and one where we have 294 features， as we saw before。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_6.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_7.png)

We're going to train and split。Using the train test split functionality so that they are both split in the same fashion。

 and then we're going to see given that holdout set。

 which one will be able to perform better between the one hot encoded version and the original version。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_9.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_10.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_11.png)

So the first thing that we do is import our train test split from SK Learnearn。t model selection。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_13.png)

We set our Y call equal to this string sale price， and we're going to use this in just a second in order to separate out our X variable and our y variable。

 our features and our target column。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_15.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_16.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_17.png)

So our feature calls are going to be x for x and data。 columns。

 so that would be a list of all of our actual columns。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_19.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_20.png)

If X is not equal to Y call， so it's essentially taking all of our columns except for sale price。

 which we defined up here。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_22.png)

So that'll be all of our feature columns。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_24.png)

We can then isolate all of our features using that feature calls list， so we say from our data。

 pull out just the feature calls and set that equal to X data。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_26.png)

We then set y data equal to our target column， which is just going to be data selecting that y call that we defined above。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_28.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_29.png)

And then we're going to use those X and Y data in order to create our X train X test。

 Y train and Y test using the train test split function。

 So how does the train test split function work， We saw this briefly in another notebook。

 We pass in X data and Y data。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_31.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_32.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_33.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_34.png)

We pass in the test size， so test size is going to be。For the number of rows we have。

 what percentage do we want to hold out for test and not train on。

 and then a random state to ensure that we get the same split every time and you'll be getting the same split that I'm getting now。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_36.png)

So we get four outputs from train test split， assuming that we passed in both an X and a Y。

 those four values will be in this order， Xtrain， X test， then Y train， then Y test。

 where Xtrain and Y train will be paired together in order to fit our model and then we're going to use that fitting in order to see how well we can predict on X test。

 and then take those predictions from X test。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_38.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_39.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_40.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_41.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_42.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_43.png)

And compared to how well they perform against Y test， assuming that it was a holdoutet。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_45.png)

Then we're going to do the same thing for our data underscore OHC。

 which is just our data with the one hot encoded variables。

We will get the X data underscore OHC using the same feature calls process as we did before。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_47.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_48.png)

Justin， this time， we're going to say x for x and data underscore OH。colns。

 assuming it's not sale price so that we get all 294 columns that we discussed before。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_50.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_51.png)

And then we set the Y data in the same fashion， and we use the same train test split to get our Xtrain x test。

 Y train and Y test in the same fashion that we did above， but this time for one hot encoding。

 and we're going to name them appropriately with this underscore OHC suffix。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_53.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_54.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_55.png)

So we run that。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_57.png)

We can look at the shape of Xtrain OHC， that's going to be 965 rows。

 which should be 70% of your original data frame。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_59.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_60.png)

If we were to look at Y train OHC， what do you think that shape would be？



![](img/788a54d5e2caf7951b0d074f24ad1c8f_62.png)

Hopefully you guessed correctly with 965 rows。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_64.png)

Complementing each one of the rows in our X train because that's going to be how we fit。

 there has to be the same number of rows。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_66.png)

And then if we look at。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_68.png)

X train without OHC。We should have。Many less columns。

 namely 36 columns because we don't have all those one hot encoded columns。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_70.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_71.png)

We're going to check here that Xtrain OC and Xtrain from the original data set both had the same indices so that we know that we got the same exact split。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_73.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_74.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_75.png)

We see that that is true。Just to make clear how the dot all functionality works。

 if we run two arrays to see if they're equal to one another， it'll output。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_77.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_78.png)

True for every single value or false for every single value， according to their one by one match。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_80.png)

If we run all， then every single value in that array has to be true for this to evaluate to true。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_82.png)

Now let's run our linear regression to see how well we're able to perform on our train and test setss。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_84.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_85.png)

We're going to initiate our linear regression object using linear regression。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_87.png)

We're importing the linear regression from SK learn dot linear model。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_89.png)

We're also going to import the mean square to error from SK learn dot metrics。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_91.png)

And。Again， we initiate that linear regression model to LR， recre an empty list called Air DF。

 where we will append each one of our error terms so that we can evaluate them later。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_93.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_94.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_95.png)

The first thing that we're going to do is fit our model on the original X train and Y train without any one hot encoding。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_97.png)

So we say Lr dot fit xtrain and Ytrain， LR is now fit to our model so as come up with the parameters。

 and then we can use the Lr dot predict in order to predict first how well we do on xtrain。

 So when we predict and we're setting that equal to Ytrain predict。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_99.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_100.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_101.png)

When we predict on the Xtrain， we should be able to get a much lower error because we've already seen all of this data before。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_103.png)

And then we're going to LR do predict on X test， which is our holdout set。

 and that should give us a better picture of the reality as to how well we're able to generalize once we see new data that hasn't been trained。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_105.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_106.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_107.png)

We're then going to append to error underscore DF this series。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_109.png)

Now the series is just going to pass in the dictionary， you can think of a series as a column again。

 and then each one of these values will be an index for that column。

 so we have the first index value is train and we get the mean squared to error for the training set and the prediction for the training set recall that that should be a lower number and then we get the mean squared to error for the test and the test predictions and that should be a little bit of a higher error。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_111.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_112.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_113.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_114.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_115.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_116.png)

And then we're going to name it no encoding， so later on you'd assume if you're creating columns。

 you're going to eventually be creating a data frame， so that will be the column name。

 so we have the column name no space and ENC standing for no encoding。

 and these will be the two indices train and test。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_118.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_119.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_120.png)

We're then going to do the same thing for our one hot encoded version of our data。

 So it's all the same steps。 L R dot fit， X train08， Y train08 C。

 So just looking at the X train and Y train in relation to the one hot encoded version。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_122.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_123.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_124.png)

We are then going to come up with a prediction on our training set again。

 that should be doing better than it would on the test set。

 and then next we see how well we're able to predict on the actual test set on our holdout set that we didn't actually use in our training。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_126.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_127.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_128.png)

We're then going to append to our original AirDF， another panda series。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_130.png)

This time， we're again going to call the indices train and test。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_132.png)

We're going to take the mean squared error for y train versus the prediction as well as Y test versus the prediction。

 and this one we're going to name this column one hot encoding。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_134.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_135.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_136.png)

So we should have now two columns， one that is not no encoding， another one， one hot encoding。

 and then we'd be able to see each one's going to have the same indices， train and test。We use PDd。

comcat in order to concatenate each one of these series together in order to create our data frame。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_138.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_139.png)

And then we end up with our error underscore Df， which is going to be this data frame here。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_141.png)

Now let's think about which one ended up having a lower error， we see that on the training set。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_143.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_144.png)

The with no encoding。So looking back at the same training set that was used。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_146.png)

We got a lower mean squared error for the one hot encoded versus the known encoded。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_148.png)

So in that sense， it did better on just the training set， but then looking at the holdout set。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_150.png)

We see that we performed much worse on the one hot encoding。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_152.png)

Now， what could be the reason for this？

![](img/788a54d5e2caf7951b0d074f24ad1c8f_154.png)

If you think about the idea that we talked about in terms of complexity and overfitting。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_156.png)

The more parameters that you're able to use， the more likely you are to overfit your data。

 You're able to come up with variation or different coefficients to exactly fit to your training set that may not replicate out in the real world。

 So in this case， using the one hot encoding， it seems that we may have overfi our data。

 a good indicator that is a big gap between the training set error and the test set error。😊。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_158.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_159.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_160.png)

And then you see here， we are closer to just right when these aren't as largely separated。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_162.png)

Now， this is all relative， of course， because this is 10 to the power of 9。

 So this may be a large difference， but compared to the train and test set of one hot encoding。

 you see that we vastly overfit and came up with the way too complex of a model。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_164.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_165.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_166.png)

So that closes out question number four in question number five。

 we will talk about scaling our data and then we'll also go into question number six to quickly plot out our predictions versus the actual values and that will close out this notebook。



![](img/788a54d5e2caf7951b0d074f24ad1c8f_168.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_169.png)

![](img/788a54d5e2caf7951b0d074f24ad1c8f_170.png)

I'll see you there。 Thank you。

![](img/788a54d5e2caf7951b0d074f24ad1c8f_172.png)