# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P139：50_Adaboost和梯度boosting概述.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now， let's discuss the loss functions use when we're trying to do boosting。



![](img/41eb28c768a6b6f824ec05372c7aeed7_1.png)

Now there are a few options that are used in practice when it comes to boosting。

And at each stage or for each of our weak learners。

 we can determine a margin for each point in our data set。



![](img/41eb28c768a6b6f824ec05372c7aeed7_3.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_4.png)

Now， the margin is calculated to be positive or to the right of the plot for correctly classified points。



![](img/41eb28c768a6b6f824ec05372c7aeed7_6.png)

And is to the left on the plot for incorrectly classified points。



![](img/41eb28c768a6b6f824ec05372c7aeed7_8.png)

The value of the loss function。

![](img/41eb28c768a6b6f824ec05372c7aeed7_10.png)

Can be thought of as the distance from our decision boundary。 So from that margin。

 as in the case of logistic versus linear regression， we can penalize misclassified far away points。



![](img/41eb28c768a6b6f824ec05372c7aeed7_12.png)

Heavily or not。

![](img/41eb28c768a6b6f824ec05372c7aeed7_14.png)

And the loss function gives us the penalization and determines what type of boosting algorithm we're actually going to be using。



![](img/41eb28c768a6b6f824ec05372c7aeed7_16.png)

So the most frequently discussed loss function is the01 loss。



![](img/41eb28c768a6b6f824ec05372c7aeed7_18.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_19.png)

This function returns one for incorrectly classified points。And ignores correctly classified ones。



![](img/41eb28c768a6b6f824ec05372c7aeed7_21.png)

And this is a theoretical loss function because it's actually rarely used。



![](img/41eb28c768a6b6f824ec05372c7aeed7_23.png)

And this is due to the fact that it's not differentiable。



![](img/41eb28c768a6b6f824ec05372c7aeed7_25.png)

A function such as this one that is not smooth and not confect。Convex is difficult to optimize。

 Instead， there are various types of loss functions for our different boosting algorithms that we will use in practice。



![](img/41eb28c768a6b6f824ec05372c7aeed7_27.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_28.png)

So let's first how the loss function looks for at a boost。



![](img/41eb28c768a6b6f824ec05372c7aeed7_30.png)

At a boost or adapted boosting was one of the first boosting algorithms used in practice。



![](img/41eb28c768a6b6f824ec05372c7aeed7_32.png)

At a boostt uses an exponential loss function。

![](img/41eb28c768a6b6f824ec05372c7aeed7_34.png)

As it can be seen here。Very negative points can strongly affect the loss。



![](img/41eb28c768a6b6f824ec05372c7aeed7_36.png)

So if the distance from our margin is large and incorrect。



![](img/41eb28c768a6b6f824ec05372c7aeed7_38.png)

We end up with a large contribution to that overall error for that given point。



![](img/41eb28c768a6b6f824ec05372c7aeed7_40.png)

And this makes it so that atdabu can be very sensitive to outliers。



![](img/41eb28c768a6b6f824ec05372c7aeed7_42.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_43.png)

Now we'll also cover a second type of loss function associated with a boosting algorithm。



![](img/41eb28c768a6b6f824ec05372c7aeed7_45.png)

PsyCit learns gradient boosting function。

![](img/41eb28c768a6b6f824ec05372c7aeed7_47.png)

Another popular boosting algorithm used often in practice。



![](img/41eb28c768a6b6f824ec05372c7aeed7_49.png)

Uses a log likelihood loss function。And the reduced value of the log likelihood loss function for large margins for misclassified points。

 of course。

![](img/41eb28c768a6b6f824ec05372c7aeed7_51.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_52.png)

Makes this version of boosting here gradient boosting， more robust to outliers than add a boost。



![](img/41eb28c768a6b6f824ec05372c7aeed7_54.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_55.png)

Now let's compare the two ensemble methods that we've discussed so far。



![](img/41eb28c768a6b6f824ec05372c7aeed7_57.png)

Such as bagging and boosting。

![](img/41eb28c768a6b6f824ec05372c7aeed7_59.png)

For boosting。We can use the entire data set to train each of our classifiers so boostings what we just went over。

 and then for bagging， we recall we had those subamples and we would only train each classifier on one bootstrap sample。



![](img/41eb28c768a6b6f824ec05372c7aeed7_61.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_62.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_63.png)

Now， starting with baggging， bass learners， each one of those smaller trees are independent from one another。

 and usually they are not going to be stunts， but rather full trees。



![](img/41eb28c768a6b6f824ec05372c7aeed7_65.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_66.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_67.png)

Well， as for boosting。The base learners are going to be weak learners。

 and they are created successively where each learner builds on top of the previous steps。



![](img/41eb28c768a6b6f824ec05372c7aeed7_69.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_70.png)

Now， another difference， bagging only takes into account the data of the bootsraprap sample。



![](img/41eb28c768a6b6f824ec05372c7aeed7_72.png)

Boosting， on the other hand， takes into account not only the current data。

 but also accounts for residuals from previous models when building each one of these successive learners。



![](img/41eb28c768a6b6f824ec05372c7aeed7_74.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_75.png)

For bagging， all samples are going to be equal in coming up with that final classification。

 so it could be an equal vote。Whereas for boosting at each iteration。

 the previous mistakes are trying to correct by weighting them more heavily。

 So we're going to have different weights for each one of our weak learners。



![](img/41eb28c768a6b6f824ec05372c7aeed7_77.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_78.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_79.png)

And then finally， with bagging， we don't have to worry about excess trees causing overfitting。



![](img/41eb28c768a6b6f824ec05372c7aeed7_81.png)

Whereas with boosting， we do have to be aware of overfitting。



![](img/41eb28c768a6b6f824ec05372c7aeed7_83.png)

So why is this the case？

![](img/41eb28c768a6b6f824ec05372c7aeed7_85.png)

As we see here， as we increase the number of trees。

What we are doing is continuing to try and improve on mistakes that we made by prior trees。



![](img/41eb28c768a6b6f824ec05372c7aeed7_87.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_88.png)

So at a certain point， we do risk that danger of overfitting because we keep trying to improve and improve off of the air from past trees。



![](img/41eb28c768a6b6f824ec05372c7aeed7_90.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_91.png)

With that in mind， we want to use cross validation to hone in on the correct number of trees that should be used for our boosting models。



![](img/41eb28c768a6b6f824ec05372c7aeed7_93.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_94.png)

Also， our learning rate needs to be optimized in order to properly regularize the model。

 As I mentioned earlier， if you have a lower learning rate。

 you should probably use more trees as the learning rate represents how much we are correct in the model at each step。

 So these two hyperparameters， the learning rate and the number of trees are going to be related。



![](img/41eb28c768a6b6f824ec05372c7aeed7_96.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_97.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_98.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_99.png)

Ideally， to bring down the amount of correction at each step。

 we should set that learning rate also called the shrinkage as it shrinks the impact of each successive learner to a value less than one。



![](img/41eb28c768a6b6f824ec05372c7aeed7_101.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_102.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_103.png)

Another argument available for gradient boosting is the sub samplele。



![](img/41eb28c768a6b6f824ec05372c7aeed7_105.png)

And this is another parameter we can use to add randomness to reduce overfitting。



![](img/41eb28c768a6b6f824ec05372c7aeed7_107.png)

By using a subsample， our base learners don't train on the entire data set。

 and this alone allows for faster optimization， as well as a bit of regularization as it will not perfectly fit to our entire data。



![](img/41eb28c768a6b6f824ec05372c7aeed7_109.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_110.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_111.png)

Here we see that just using a subsample does not seem to aid our overall test error much。



![](img/41eb28c768a6b6f824ec05372c7aeed7_113.png)

But combining that with a low learning rate so that it also does not over correctrect seems to do well。



![](img/41eb28c768a6b6f824ec05372c7aeed7_115.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_116.png)

Another parameter we can use is max features。 The max features will determine how many features to consider when trying to find each split。

 So， again， reduces the possible complexity of our model。



![](img/41eb28c768a6b6f824ec05372c7aeed7_118.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_119.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_120.png)

And we see。This is decently in regards to improving our testE errorR。



![](img/41eb28c768a6b6f824ec05372c7aeed7_122.png)

Now I do want to note that how well this hyperparmeter tuning will do in practice will actually depend on the data set。

 and as usual you probably want to consider using cross validation when deciding between each one of these different hyperparameters。



![](img/41eb28c768a6b6f824ec05372c7aeed7_124.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_125.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_126.png)

So that closed out this video in our next video， we'll do a short walkthrough。



![](img/41eb28c768a6b6f824ec05372c7aeed7_128.png)

Of the actual syntax of both gradient boosting and add a boost in Escal learnn。 All right。

 I'll see you there。

![](img/41eb28c768a6b6f824ec05372c7aeed7_130.png)

![](img/41eb28c768a6b6f824ec05372c7aeed7_131.png)