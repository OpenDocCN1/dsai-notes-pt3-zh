# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P75：26_正则化和模型选择.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Welcome to our section on regularization and model selection。In this section。

 we'll discuss the power of regularization， which will ultimately be one of the major keys to ensuring that we choose a model that will give us the balance between bias and variance within our models。

Now let's go over the learning goals for this section In this section。

 we're going to cover a quick recap on the relationship between model complexity and model error。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_1.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_2.png)

We'll discuss how regularization can be used as an approach to avoid overfitting。

 so as we get to a more complex model， often we end up overfitting to our training data。

 we will use regularization to ensure that we do not overfit。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_4.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_5.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_6.png)

We'll discuss some standard approaches to regularization， including Ridge and Lasso。

 which we were introduced to briefly in our notebooks。

 but now we'll look under the hood at the actual math， as well as looking at elastic net。

 which will be sort of balance between Ridge and Lasso regression。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_8.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_9.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_10.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_11.png)

And then finally， we'll discuss recursive feature elimination。

 which just a means of eliminating features that may be diluting the power of our model to be able to generalize。

 so it'll be a means of reducing the number of features to ensure that we're only including features that really have predictive power。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_13.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_14.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_15.png)

So from last time we recall when building a model， we want training and test errors to be as small as possible。

 so we want both train and test to be small， the curve on top is again going to be the error of the test set and we recall that as we get a more complex model our test set will end up increasing an error because it is not generalizing well so we discuss one way to handle working with complexity versus error is we can use just a simpler overall model。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_17.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_18.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_19.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_20.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_21.png)

Another way that we can deal with this is using regularization to take our existing model and make it not as complex。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_23.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_24.png)

So can we tune with more granularity than just choosing a polynomial degree， for example。

 when we're working with linear regression？

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_26.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_27.png)

Yes， we can by using something called regularization。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_29.png)

So what do we mean by this term regularization？If you recall the means by which our machine learns the parameters from the data is that we try and minimize some cost function。

 as we saw for linear regression， is is going to be minimizing the mean square error。

 the error between the outcome variable and our predicted variable squared。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_31.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_32.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_33.png)

And our new cost function with regularization will be that original cost function。

 which we represent here as M of W。

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_35.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_36.png)

Plus， this Lada symbol， which we have seen before when we introduced Lassso and Ridge regressiongression in our last notebook。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_38.png)

Multiplied by R of W， where R is just going to be a function of the strengths of our different parameters。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_40.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_41.png)

The regularization portion， which is just lambmbda times R of W。

 is added on to our original cost function so that we can penalize the model extra if it is too complex。

Essential， this will allow us to du down the model。 so the stronger our weights。

 the stronger our parameters， the higher this cost function is going to be。

 and we're trying to ultimately minimize this， so we're not going to be able to fit it as closely to the actual training data。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_43.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_44.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_45.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_46.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_47.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_48.png)

The lambda is going to add a penalty proportional to the size of the strength of these parameters or some function of these parameters。

 and we'll get deeper into how can be a function of the parameter later on。

 But the takeaway is that the larger this lambda is。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_50.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_51.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_52.png)

The more we penalize stronger parameters。And again， the more we penalize our model for being。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_54.png)

Stronger and having stronger parameters， the less complex that model will be able to be as we try to minimize this function。

 right， that'll make it so that we are trying to minimize the strength of all of our parameters while minimizing our original cost function。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_56.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_57.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_58.png)

Therefore， we're going to be increasing our original cost function according to how much we want to penalize our model for being more complex。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_60.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_61.png)

So。

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_63.png)

The regularization strength parameter Lambda allows us to manage this complexity trade off。

 The idea being that more regularization， a higher lambda introduces a simpler model or more bias。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_65.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_66.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_67.png)

So increasing lambda means more penalty for stronger weights。

 the more penalty we attribute to our weights， the less complex our model can be。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_69.png)

And then on the other end， less regular makes it so that the model is more complex and will increase the variance。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_71.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_72.png)

And if our model is overfit， so if we see that our variance is too high and we can see this because our TesA error is very high。

 while our training error is very low， regularization can help improve the generalization error and reduce this variance。

Now let's take a step back from just looking at regularization and thinking about it in the context of feature selection or figuring out which one of our features are important to include in our actual model。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_74.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_75.png)

So regularization is essentially going to be a form of feature selection since it's going to take the contribution of each one of those features and eliminate or reduce them as it adds more weight to the penalty。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_77.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_78.png)

So this will be most obvious when we work with Lasso regression。

 as Lassso will actually drive some of the coefficients in our linear regression down to zero。

 so if you think about a coefficient of 0， you're essentially removing the contribution of that feature altogether。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_80.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_81.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_82.png)

It's going to be the same effect as manual removing some features prior to modeling。

 except that with Laso， it'll find which ones to remove automatically according to some mathematical formula。

 which we'll see in a bit。

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_84.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_85.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_86.png)

Another way to perform feature selection would be to just remove some of the features right at the start。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_88.png)

This would have to be done quantitatively and a way that we can do this is remove a feature at a time and then measure the predictive results via cross validation。

 and if the feature elimination does improve the model on the holdout set or it doesn't reduce the error of that much。

 then we would say that we can probably safely remove that feature and perhaps even generalize better if that feature was not included。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_90.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_91.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_92.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_93.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_94.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_95.png)

So why are we doing this？Wouldn't you assume that models with more features are better now obviously。

 given what we discussed， that's not always going to be the case。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_97.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_98.png)

Not all features are necessarily relevant。 You can think about a lot of the analysis that you may do in your business practices。

 If you think about the customer churn， the customer name probably does not add a lot of value。

 but it could help you predict if you are just fitting to the training set。

 so it can add some extra noise that allow you to overfit your model。

 trick your algorithm to think that that is actually an important feature。

 but then when you get new data， you're not able to generalize well。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_100.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_101.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_102.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_103.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_104.png)

Besides reducing the effects of overfitting， feature elimination can also be useful to improve fitting time and or results of some of the models。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_106.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_107.png)

Particularly for those that don't have a built in。

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_109.png)

Regularization terms such as Ridge or aasso， this will allow us to eliminate features not train on all the features that we have available。



![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_111.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_112.png)

Feature elimination can also be used to identify what are the most important features。

 which can improve the model interpretability。 And this is often going to be an important business requirement as we actually try to learn。

 how can we affect the outcome of our variable。

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_114.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_115.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_116.png)

So that closes out the section in regards to regularization in the next video we will continue by looking at Ri regression。

 thank you。

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_118.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_119.png)

![](img/a3c6e82b411d94cb438e55b9a0ed9dbe_120.png)