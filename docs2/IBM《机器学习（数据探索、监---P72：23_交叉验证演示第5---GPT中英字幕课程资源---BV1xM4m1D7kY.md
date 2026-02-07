# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P72：23_交叉验证演示第5部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In the last section of this notebook， we're going to show you how we can use grid search C to take everything that we just learned with all the four loops。

 how we went with four loops for the K folds and how we pass that through to cross valve predictict to make that more succinct。

 Now， we're using the for loop through each one of our hyper parametersmeters and then passing through cross valve predictts。

 how we can do all that in just one step using grid search Cv。😊。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_1.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_2.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_3.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_4.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_5.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_6.png)

So we're going to import from SKL model selection our grid search CD。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_8.png)

We're going to initiate our objects， our estimator object using pipeline。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_10.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_11.png)

So our pipeline is going to be the polynomial features， then the scalar， then Rige regression here。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_13.png)

And then we're going to say what our parameters are going to be。

Now what are going to be the hyperparameters that we want to loop over in order to figure out which one of the hyperparas。

 again， those hyperparameters being the ones that we choose rather than what the model learns。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_15.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_16.png)

That will optimize the results for a holdout set。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_18.png)

So we're actually going to look at both polynomial features as well as the different alpha values that we saw。

 so higher polynomial features will mean more complexity and then a higher alpha value will mean less complexity and we're look at looping through every single one of those values so if there's three values here and there's 30 here we're actually going to be looking at 90 different values。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_20.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_21.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_22.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_23.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_24.png)

And we're going to run grid search CV。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_26.png)

We have our estimator that we have defined here。So that's going to be our model and then our parameters。

 just so you know， just all practice when you're using grid search TV is going to be a dictionary where you're going to have as each one of the values the difference。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_28.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_29.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_30.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_31.png)

Hyperpar that you can loop through。So the different hyperparmeters that we can loop through here are the different degrees。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_33.png)

So first we have to use the name that we defined up here。

 which is polynomial features and then two underscores and then we can pass in any of the hyperparameters that are available for polynomial features。

 so that's the way that we decide how to name this and then the same thing goes for Rige where we have to just use hyperparas that are available within initiating ridge。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_35.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_36.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_37.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_38.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_39.png)

And we're going to use， again， the name Rige regression two underscores。

 and then we're going to pass the hyperpar alpha。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_41.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_42.png)

So we pass in our estimator， as well as the dictionary of each one of the different values that we want to loop through。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_44.png)

And then we say， we want to be， again， looking at holdout sets。

 how are we going to split up our data set， We're going to use that Kfolds object that we defined earlier。

 As I mentioned when we were doing cross valve predictic。

 you can also pass in a number if you don't have a K folds object created。

 but we create our grid object。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_46.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_47.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_48.png)

Now that we have our grid objects。 That grid object is similar to many of the S Kar objects that we've been using so far。

 where it's going to have this fit method。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_50.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_51.png)

And it's going to fit that pipeline。But running through each one of these different hyperparameters。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_53.png)

So we fit it， and that's going to take a bit a minute as it's going through 90 different hyperparameters。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_55.png)

It's going to figure out what the best score and the best parameters were。

 we're going to print that out and that's going to be the best score they got was 0。

85 and the best degree was degree2 with a Rige regression alpha of 4。0。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_57.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_58.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_59.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_60.png)

We can then actually use that grid in order to predict the x values。

 The reason that we're able to do that。 recall we were not able to do that with cross Val predicts。

 The reason why we're able to do that now is that with grid search。

 it's going to test against all the different holdout sets。😊。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_62.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_63.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_64.png)

And then once it's tested against all the different holdout sets。

 it's going to and it finds the best hyperparameter。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_66.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_67.png)

That will fit for generalization for dataset sets that we've never seen。

 It's then going to use those hyperparameter to learn the parameters on the entire data set because the more data that you have。

 the better you're going to be able to predict， and the idea is that you are now able to use this to predict as new data comes in。

 it's ready for production。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_69.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_70.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_71.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_72.png)

So we're going to run grid dot predicts since it's now fit on the entire data set。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_74.png)

Again， we don't have actual holdout data or new data， so it should perform fairly well。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_76.png)

And we get our2 score of 0。89。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_78.png)

And then with the grid， we would want to call out our best estimator that's an attribute that's available within grid。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_80.png)

If we want to look at different attributes within our actual。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_82.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_83.png)

Estimator that we're looking at。 So we have our estimator。We do grid。 best estimator。

 best estimator specifying the estimator that we had passed into our grid search CV。

 and then from there we can pull out name stepss such as Rige regression and get our coefficients。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_85.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_86.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_87.png)

And then if we do grid。cv results。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_89.png)

This is actually a little bit cleaner， if we do。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_91.png)

Data frame。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_93.png)

And you can see for each one， if you want all the details of what grid search did。

 we can look for each one of the parameters， what the different scores were for each one of the splits。

 and then it looks at the mean score， the standard deviation of each one of those scores。

 and ultimately picks the best mean score。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_95.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_96.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_97.png)

So if you want to look at more details， you can look at V CVV results。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_99.png)

So in conclusion， in our notebook， we learned first just how to do those general K folds。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_101.png)

We then moved on to using cross Valel predict so that we can see the scores for each one of those k folds in a succinct fashion。

And then we talked about how we can use hyperpres in order to look at multiple versions of the same model。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_103.png)

Reducing or increasing the complexity of that model to see which one performs best on our holdout set。

 We pass that in using grid search C。 That's going to find the best hyper parameters。

 Given the hyper parameters that we gave it the options to run， such as。😊。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_105.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_106.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_107.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_108.png)

Dgreee1， two or three， or alphas within this range of four to 20。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_110.png)

And then it'll ultimately fit on all the data so that you will have the best hyperparameter。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_112.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_113.png)

Which are chosen and then tested across each one。As well as all the best parameters。

 as all be learned on the entire dataset set。

![](img/a5e43002aa9c0fd66e62a6780c2c5320_115.png)

That closes out our notebook， I look forward to seeing you back in lecture， thank you。



![](img/a5e43002aa9c0fd66e62a6780c2c5320_117.png)

![](img/a5e43002aa9c0fd66e62a6780c2c5320_118.png)