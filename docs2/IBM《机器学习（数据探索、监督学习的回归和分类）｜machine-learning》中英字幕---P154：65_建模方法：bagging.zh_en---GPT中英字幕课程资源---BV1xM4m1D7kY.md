# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P154：65_建模方法：bagging.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now， if we think through our over and under sampling solutions。

As we discussed earlier in regards to possible solutions for unbalanced classes。

 we can also mix up sampling and down sampling。

![](img/340f62ba794d69b28269b30281dcb66d_1.png)

![](img/340f62ba794d69b28269b30281dcb66d_2.png)

So we can use smoke to upsample， and then to remove noisier objects and not have to upsample too heavily。

 we can then downsample some of our majority class as well by removing points using either Tx link or by using edited nearest neighbors。



![](img/340f62ba794d69b28269b30281dcb66d_4.png)

![](img/340f62ba794d69b28269b30281dcb66d_5.png)

Now I'd like to briefly touch on an intuitive ensemble technique for unbalanced data sets called bragging or balanced baggging。

 and hopefully you can tell at this point， data scientists love to mash together words。



![](img/340f62ba794d69b28269b30281dcb66d_7.png)

![](img/340f62ba794d69b28269b30281dcb66d_8.png)

The idea here is to ensure to continuously down sampleample each of our bootstrap samples。

 So as you see， we have our bootstrap samples， and then we down samplele each of the majority classes。



![](img/340f62ba794d69b28269b30281dcb66d_10.png)

![](img/340f62ba794d69b28269b30281dcb66d_11.png)

And then use these now balanced samples to learn each one of our individual decision trees。



![](img/340f62ba794d69b28269b30281dcb66d_13.png)

And this will again allow for more weight to be attributed to that minority class。

 ensuring that we have a more balanced decision being made。



![](img/340f62ba794d69b28269b30281dcb66d_15.png)

![](img/340f62ba794d69b28269b30281dcb66d_16.png)

Now， I want to briefly go over some steps to keep in mind whenever we're working with unbalanced data sets。

 Now， that first step。

![](img/340f62ba794d69b28269b30281dcb66d_18.png)

![](img/340f62ba794d69b28269b30281dcb66d_19.png)

Is going to ensure that you first do your train test split before doing any of this over under sampling。

 recall that if we do this over sampling first， we can end up with values being both represented in the train and test set。

 which means we can very easily overfit， have that data leakage。

 And even if we're synthetically creating those new samples。

 those values will be very close to those train set samples， and we can still have that overfitting。



![](img/340f62ba794d69b28269b30281dcb66d_21.png)

![](img/340f62ba794d69b28269b30281dcb66d_22.png)

![](img/340f62ba794d69b28269b30281dcb66d_23.png)

![](img/340f62ba794d69b28269b30281dcb66d_24.png)

![](img/340f62ba794d69b28269b30281dcb66d_25.png)

So always do your train test split first。

![](img/340f62ba794d69b28269b30281dcb66d_27.png)

We also want to ensure that we use sensible metrics。



![](img/340f62ba794d69b28269b30281dcb66d_29.png)

And we start here with a sensible metric AU， for example。



![](img/340f62ba794d69b28269b30281dcb66d_31.png)

Because this will give us a trade off between our true positive rate and our false positive rate for our minority class。

 And we can see that for different thresholds so that we can get a clear picture of this classification method as a whole and can even look here to get an idea of what threshold is optimal for your business objective。

😊。

![](img/340f62ba794d69b28269b30281dcb66d_33.png)

And the same thing can be said for precision recall curve as well。Thinking of precision and recall。

 we can also use our F1 score。

![](img/340f62ba794d69b28269b30281dcb66d_35.png)

Because this will always balance out the precision and recall and will punish you more strongly for getting either of those two too low for your given class。



![](img/340f62ba794d69b28269b30281dcb66d_37.png)

![](img/340f62ba794d69b28269b30281dcb66d_38.png)

So unlike accuracy， it will not be skewed by unbalanced classes。

 assuming again that you are testing it for that minority class。

 that precision or recall for the minority class。

![](img/340f62ba794d69b28269b30281dcb66d_40.png)

![](img/340f62ba794d69b28269b30281dcb66d_41.png)

Then we have here Cohen's Kappa， and this is a new one that we haven't discussed。

 but we felt it was worth at least letting you all know that it's available。



![](img/340f62ba794d69b28269b30281dcb66d_43.png)

![](img/340f62ba794d69b28269b30281dcb66d_44.png)

This is best if you are working with a team， and it's actually a measure of agreement between two different raters or two different models。

 where each rater will be classifying n items into mutually exclusive categories。

 So just performing classification And the goal here is to come up with a ratio of observed agreement between these two models as compared to the probability of there being agreement just by chance。

 So with unbalanced classes， we want to make sure that we have strong agreement and that that agreement between those two different models are better than just agreement by chance。



![](img/340f62ba794d69b28269b30281dcb66d_46.png)

![](img/340f62ba794d69b28269b30281dcb66d_47.png)

![](img/340f62ba794d69b28269b30281dcb66d_48.png)

![](img/340f62ba794d69b28269b30281dcb66d_49.png)

![](img/340f62ba794d69b28269b30281dcb66d_50.png)

![](img/340f62ba794d69b28269b30281dcb66d_51.png)

![](img/340f62ba794d69b28269b30281dcb66d_52.png)

So the higher this value is for Cohen's Kappa， the more you can trust the agreed upon predictions of those two models。



![](img/340f62ba794d69b28269b30281dcb66d_54.png)

![](img/340f62ba794d69b28269b30281dcb66d_55.png)

And then finally， we want to make sure that you do not use accuracy as that can be easily fooled when working with unbalanced data。



![](img/340f62ba794d69b28269b30281dcb66d_57.png)

So to recap in this section， we discuss additional approaches to dealing with unbalanced data。

 starting with just using class weights hyperpara for many of our models without messing too much with resampling。



![](img/340f62ba794d69b28269b30281dcb66d_59.png)

![](img/340f62ba794d69b28269b30281dcb66d_60.png)

![](img/340f62ba794d69b28269b30281dcb66d_61.png)

We then got into random and synthetic oversampling techniques， such as Smote and Addison。

 with both relying on generating random examples based off of the Ken nearest neighbor's algorithm。



![](img/340f62ba794d69b28269b30281dcb66d_63.png)

![](img/340f62ba794d69b28269b30281dcb66d_64.png)

We then discussed undersampling techniques such as near misss， toec links， and edited neighbors。



![](img/340f62ba794d69b28269b30281dcb66d_66.png)

![](img/340f62ba794d69b28269b30281dcb66d_67.png)

And then we also briefly discussed using balance vgging or flaggging to address unbalanced class data。



![](img/340f62ba794d69b28269b30281dcb66d_69.png)

Now， in regards to over sampling and under sampling， I want you to note here that for both of them。

 they each have their advantages in practice for each one of them。

 for the specific techniques for each of them。

![](img/340f62ba794d69b28269b30281dcb66d_71.png)

![](img/340f62ba794d69b28269b30281dcb66d_72.png)

![](img/340f62ba794d69b28269b30281dcb66d_73.png)

But it'll often be difficult to tell。For over sampling or under sampling。

 which technique to use without cross validation， Since we can almost never visualize as clearly as we did in each one of these examples。



![](img/340f62ba794d69b28269b30281dcb66d_75.png)

But when deciding between under over samplingamp in general， remember what we discussed earlier。

 under sampling will probably lead to a bit of a higher recall for that minority class at the cost of precision。

 whereas over samplingamp will keep all the values from our majority class。

 and thus will have a bit of a lower recall than under sampling。

 but better precision on those predictions。

![](img/340f62ba794d69b28269b30281dcb66d_77.png)

![](img/340f62ba794d69b28269b30281dcb66d_78.png)

![](img/340f62ba794d69b28269b30281dcb66d_79.png)

![](img/340f62ba794d69b28269b30281dcb66d_80.png)

![](img/340f62ba794d69b28269b30281dcb66d_81.png)

Now that closes out our video on balance classes， as well as our lecture here introducing many of the machine learning models available and the best practices。



![](img/340f62ba794d69b28269b30281dcb66d_83.png)

![](img/340f62ba794d69b28269b30281dcb66d_84.png)

Now， I would note here as a practicing data scientist。

 having an intuitive feel for how each of these models work will go a very long way in ensuring you can choose and tune your models in a timely and rewarding fashion。

😊。

![](img/340f62ba794d69b28269b30281dcb66d_86.png)

![](img/340f62ba794d69b28269b30281dcb66d_87.png)

![](img/340f62ba794d69b28269b30281dcb66d_88.png)

Thank you。😊。

![](img/340f62ba794d69b28269b30281dcb66d_90.png)