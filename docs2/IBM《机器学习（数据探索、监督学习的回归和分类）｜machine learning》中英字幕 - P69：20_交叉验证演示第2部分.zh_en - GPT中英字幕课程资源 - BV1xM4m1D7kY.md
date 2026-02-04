# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P69：20_交叉验证演示第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to part two of our notebook。Here we're going to discuss adding in a prepro step。

As well as introducing the pipeline and the cross file predict。

 which we'll see will consolidate a lot of the code that we're writing out in this next step。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_1.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_2.png)

So similar to before， we're going to start off with just an empty list for scores。

 we're going to initiate our linear regression object to LR。

And then we're also going to add on this preproces step of scaling our data。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_4.png)

And that's going to be this S equals standard scalar。

We're then going to run that same for loop using our KF dot split。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_6.png)

And end up with an X train， X test， Y train， and Y test set。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_8.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_9.png)

We're then going to take our X train and then fit and transform it using our standard Scalar。

So we're going to come up with that mean and standard deviation and subtract the mean divided by the standard deviation and come up with this new Xtrain S。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_11.png)

So we've now scaled our data， we're then going to pass in our scaled data along with our original outcome variable just for the training set。

 and we're going to fit our linear Russian model on our training set。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_13.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_14.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_15.png)

We then have to transform our test set。Getting it to the same scale。

 using what we learned from the standard Scalar on the training set。

 so we just run SDot transform on our test set。We get the output when we subtract the mean and the standard deviation of x test S。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_17.png)

We can then pass that into our linear Russian model that's fitted to our training set and come up with predictions on that test set。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_19.png)

We can then use those predictions in order to see our R2 score between the actual values and our predictions。

 and then just as we did before， we'll keep app on the new scores into our scores list。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_21.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_22.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_23.png)

And then we see here that our scores are exactly the same。

 and that's because for linear regression for vanilla linear regression without any regularization。

 And that's going to be a term we'll introduce later on。

 But the idea they are being that there's lasso and ridge， which we talked about。

 which will allow you to prevent overfitting。 those will need you to scale your data for regular linear regression。

 scalinging won't actually affect performance。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_25.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_26.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_27.png)

So as we add on more and more preprocessing steps， this can become pretty cumbersome to keep adding on and doing your fit transform。

 then your next fit transform if you have another preprocessing step。

 and then when you want to run it on the test having to transform each one of those。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_29.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_30.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_31.png)

So luckily， SKLn recognizes that this is common within the machine learning workforce for and they have introduced the pipeline functionality。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_33.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_34.png)

So pipeline is going to allow you to chain together multiple operators on your data as long as they each have a fit method。

 so they all have to have a fit method and then on top of that。

Every step leading up to the last step has to have a fit and transform。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_36.png)

So that the output of one can be the input of the next step。

 so you can chain together more than two steps， you can chain together 10 steps as long as each one of those steps has fit transform and the last step has fit。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_38.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_39.png)

So we're going to reinitiate our standard scalar and our linear regression。

 and then we're going to introduce our pipeline function here。

 recall we imported pipeline earlier from Scalalar do pipeline。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_41.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_42.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_43.png)

And we're going to set this variable estimator equal to our pipeline。

 and our pipeline is going to have two steps， first it will scale our data。

 then it will pass that through to a linear regression。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_45.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_46.png)

And this will allow us to bypass those steps that we saw above of fit transform as well as transform when we actually want to test。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_48.png)

So to show you what that looks like。We're going to quickly introduce the code。

 So we have estimator now created that object is created and similar to what we do with。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_50.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_51.png)

Linear regressiong， we can actually just pass in our X train。And our why train。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_53.png)

And we have now fit that pipeline objects specifically to the Xtrain and Y train。

 and what we've done there is we' first scaled our Xtrain data and then we ran regression so we fit the data according to the scaled version of the data。

Now that the estimator is fit to the data。We can even call estimator dots predict。

Similar to what we do with linear regressiong and pass in our X test。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_55.png)

And it will create an actual prediction。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_57.png)

So that's the way the pipeline works。Now， rather than doing that for loop。

 if we want to get the cross valve， if we want to get the prediction for each one of our holdout sets in our K folds。

 we can use this function called crossV predicts。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_59.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_60.png)

And the way that that works， first， let's reintroduce that we have this Kfold object。

 which will specify that we want three splits。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_62.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_63.png)

And that we want it to shuffle rather than doing it in some type of ordering。

So we're going to pass in that K folds object here into our cross valve predict。

 which is why we reintroduced it。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_65.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_66.png)

And we're going to say， I want to form my estimator。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_68.png)

And that's the pipeline that we created above。And for my initial values of x， so no splits。

 the cross valve predict will do the splitting for you。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_70.png)

And for my initial why。I want to pass in how many folds。

 so you can say I want the K folds object that we specified here。

 which will ensure that you're not just passing in three splits， but also that it's a shuffle。

 it'll be a specific type of split。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_72.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_73.png)

You could also just pass into here for your CV the number three， and that will create three splits。

 but they may not be shuffled。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_75.png)

So this allows you to specify exactly how you want it to split。And then when I run predictions。

 that will output predictions， giving that it's going to train on two thirds and then predict for the other third。

 and after it predicts all three of those thirds， it will have predicted for every single value in our data。

 but only using training from different subsets of that dataset。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_77.png)

Right that's how the cross valve predict works。 We have our training set。

 which is two thirds and a holdout set that is one third， so we're predicting that one third。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_79.png)

And then we're using a different two third to predict another one third。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_81.png)

So now we have our predictions， I'm going to run the length of our predictions and you see that it's the same length as the length of our actual data frame。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_83.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_84.png)

Then going to check the R2 score on our predictions compared to the original Y。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_86.png)

And we see that that's almost identical， I'm going to run that here。

 these are the scores that we had above。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_88.png)

In regards to。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_90.png)

Calling out。Every single one， one at a time。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_92.png)

So that's how the cross valve predict will work。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_94.png)

What's important to note is that the cross valve predicts did not actually fit the model at any step along the way。

 It's going to give you all the outputs， but it essentially came up with three different models。

 right， one trained on the first two thirds， one trained on the next two thirds and so on。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_96.png)

So our estimator will actually reit our estimator， but otherwise I wouldn't be able to run estimator。

 predictd。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_98.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_99.png)

We can here because I fit it。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_101.png)

Back up here。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_103.png)

But otherwise， after you run crosst predict， just be aware that the estimator had never been fitted。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_105.png)

All right， that closes out this section。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_107.png)

After this， we will come back and talk about hyperparameter tuning。

 so remember that we learn our parameters。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_109.png)

But we have to choose our hyperpara。And hopefully you can start thinking about now that we're introducing this cross file predict。



![](img/195ec22cbacf9fa0cc96b582f6eb3531_111.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_112.png)

How are we going to change our hyperparmeter， those arguments that we're allowed to change that will actually change the output of our model。

 So they're not learned， but we adjust them。 So how do we choose upon all the different hyperparmeter that may be available？

 All right， I'll see there。

![](img/195ec22cbacf9fa0cc96b582f6eb3531_114.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_115.png)

![](img/195ec22cbacf9fa0cc96b582f6eb3531_116.png)