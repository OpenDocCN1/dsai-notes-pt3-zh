# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P56：7_线性回归简介第2部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So best practices for any modeling is first we establish what our cost function that we want to minimize is going to be。



![](img/c4e3b38f161648c65d814cfeae35f3fe_1.png)

And this will give us a method to compare the strength of one model versus the other。



![](img/c4e3b38f161648c65d814cfeae35f3fe_3.png)

We then want to develop multiple models， perhaps with different hyperparmeters， perhaps difference。

Models altogether to see which one of the models will give us our best predictions。



![](img/c4e3b38f161648c65d814cfeae35f3fe_5.png)

And then finally， we can compare results and choose the best one according to our cost function。



![](img/c4e3b38f161648c65d814cfeae35f3fe_7.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_8.png)

Now another important metric beside mean squared error that we should keep in mind is the R2 metric。

 R squared metric。

![](img/c4e3b38f161648c65d814cfeae35f3fe_10.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_11.png)

And we're going to break down its components here。 The first one is going to be the sum squared error。

 and that's going to measure the distance between truth and our predictions。

 similar to that portion of our cost function that we saw earlier。



![](img/c4e3b38f161648c65d814cfeae35f3fe_13.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_14.png)

So that's going to be sum of squared error， our total squared error just measures the distance between the truth and the average values of the truth。



![](img/c4e3b38f161648c65d814cfeae35f3fe_16.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_17.png)

So summa squared error is the unexplained variation from our model。

 so we had a line through each one of our dots and it's going to be what were we not able to explain that's going to be the summa squared error。

 and then the total squared error is the total variation。

 so imagine just a line going horizontal which is the average values and that would be the total variation around the mean of our outcome variable。



![](img/c4e3b38f161648c65d814cfeae35f3fe_19.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_20.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_21.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_22.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_23.png)

So r squared is a measure of the explained variation by our model。

 so we see here one minus our sum of squared error。

 which is our unexplained variance divided by the total variance so one minus where the unexplained variance is essentially what is our explaineded variation so we're seeing how well did our model explain the variation from the mean。



![](img/c4e3b38f161648c65d814cfeae35f3fe_25.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_26.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_27.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_28.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_29.png)

How much was it able to reduce the amount of unexplained variance， so the closer this is to one。

 the better we did in regards to explaining the overall variance？



![](img/c4e3b38f161648c65d814cfeae35f3fe_31.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_32.png)

Now we want to keep in mind that as we make any model more complex。

 we can better fit to every single data point if we'd like， so we can always， for example。

 add on more features and even if those features don't have any predictive power。

 they will never bring down the R2 square they are squared score if you think about it if you were to add on another feature and it didn't have any predictive power。

 we could just set that coefficient to zero and it wouldn't bring down our r squared because we will still be explaining the same amount of variation。



![](img/c4e3b38f161648c65d814cfeae35f3fe_34.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_35.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_36.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_37.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_38.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_39.png)

Also， I want you to note that this isn't a score that we can only use for linear regression。

 even though you've probably heard about it in regards to linear regression in most of your past lessons wherever they may be。



![](img/c4e3b38f161648c65d814cfeae35f3fe_41.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_42.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_43.png)

But you can actually use this for any regression model in order to understand the explained variance given that model。



![](img/c4e3b38f161648c65d814cfeae35f3fe_45.png)

So how do we actually do this in Python？

![](img/c4e3b38f161648c65d814cfeae35f3fe_47.png)

So our first step will be to import that class containing the regression method。



![](img/c4e3b38f161648c65d814cfeae35f3fe_49.png)

So this is going to be our I actually we did get a quick introduction to SKLearn earlier。

 but this is going to be our first introduction to using SKLearn for a predictor。



![](img/c4e3b38f161648c65d814cfeae35f3fe_51.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_52.png)

So from SKLearn dot linearar model， we're going to import the linear regression function。



![](img/c4e3b38f161648c65d814cfeae35f3fe_54.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_55.png)

The next step is going to be to create an instance of this class and this is going to be our algorithm。

 it just has not been fitted to any data set yet， so we're just calling our object LR LR is going to be our linear Russian object which is our model just not fit to any data yet so if you recall we have our model then we pass in the data and then that model is fitted to optimize。



![](img/c4e3b38f161648c65d814cfeae35f3fe_57.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_58.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_59.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_60.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_61.png)

Bringing down that loss function as much as possible。

We then fit the instance on the data and we can then predict the expected value。



![](img/c4e3b38f161648c65d814cfeae35f3fe_63.png)

So here the training data that we're going to train our model on。

 the model the data that we already have is going to be Xtrain and Ytrain， so we call LR。

tfi and we are fitting on Xtrain and Ytrain， so now we have a fitted version of our model where we have come up with these coefficients。



![](img/c4e3b38f161648c65d814cfeae35f3fe_65.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_66.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_67.png)

And then we can call LR。t predictics this predict method is now available to this fitted model in order to predict on a test set that we have not seen yet that does not have labels。

 and that will be our predictions。

![](img/c4e3b38f161648c65d814cfeae35f3fe_69.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_70.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_71.png)

And we'll see this as we get into the notebook right after this section。



![](img/c4e3b38f161648c65d814cfeae35f3fe_73.png)

So let's recap what we've learned so far。

![](img/c4e3b38f161648c65d814cfeae35f3fe_75.png)

We've gone over linear regression as well as the loss function that we may want to be aware of。

 as well as how to optimize that according to the different parameters， beta and beta1。



![](img/c4e3b38f161648c65d814cfeae35f3fe_77.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_78.png)

We talked about modeling best practices in regards to making sure that we are first coming up with what our model is。

 what our loss function is， looking at different models。

 and then optimizing which one is the best model that we should use given our loss function。



![](img/c4e3b38f161648c65d814cfeae35f3fe_80.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_81.png)

And with all that， we discuss how to measure errors and we talked about how we don't want to just subtract and end up with positive negative values。

 but rather how we're going to use the square of those values in order to actually come up with an optimal model as well as going over R squared and how that will help us define how well we are actually explaining the overall variance。



![](img/c4e3b38f161648c65d814cfeae35f3fe_83.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_84.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_85.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_86.png)

From here we'll jump into the notebook and I look forward to seeing you there， thank you。



![](img/c4e3b38f161648c65d814cfeae35f3fe_88.png)

![](img/c4e3b38f161648c65d814cfeae35f3fe_89.png)