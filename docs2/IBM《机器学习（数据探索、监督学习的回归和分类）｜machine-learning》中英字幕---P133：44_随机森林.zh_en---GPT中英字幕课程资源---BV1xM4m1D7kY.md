# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P133：44_随机森林.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

The goal in this video will be to show how we can reduce variance further than we've done so far with just baggging。

If our bagging produced n independent trees， each with variance sigma squared。

 key word being independent trees here。

![](img/6e3001af190788e3cb6b7360a96fccf7_1.png)

Then the badged variance would be sigma squared divided by n。 So the larger n is。

 that is the more trees that we are using， assuming independent trees。

 the more we can reduce this overall variance。

![](img/6e3001af190788e3cb6b7360a96fccf7_3.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_4.png)

In reality， though， these trees are not independent since we are sampling with replacement。

 they are likely to be very highly correlated。

![](img/6e3001af190788e3cb6b7360a96fccf7_6.png)

And as we see with this equation， if the correlation is close to one。

 we end up with no reduction in variance， which should make sense if you keep using the same or very similar trees。

 you're not gaining any new information。 If you keep using the same decision tree over and over。

 you need to ensure that each one of these decision trees are somewhat different than one another。



![](img/6e3001af190788e3cb6b7360a96fccf7_8.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_9.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_10.png)

So what's our solution。We can just introduce more randomness。



![](img/6e3001af190788e3cb6b7360a96fccf7_12.png)

We need to try and make sure that those trees are significantly different than one another and thus deco。



![](img/6e3001af190788e3cb6b7360a96fccf7_14.png)

To achieve this， we restrict the number of features the trees are allowed to be built from。

 So each tree will be built from a random subset of not just rows。

 but of a random subset of columns as well。

![](img/6e3001af190788e3cb6b7360a96fccf7_16.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_17.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_18.png)

And by default， our classification model will limit that subset of features， that subset of columns。

To the square root of the total number of features available。

 and regression will take one third of the total number of features that are available。



![](img/6e3001af190788e3cb6b7360a96fccf7_20.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_21.png)

And this will force different decisions for each tree。

 depending on which one of the features are now still available for that tree， for that subset。



![](img/6e3001af190788e3cb6b7360a96fccf7_23.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_24.png)

And this resulting algorithm。

![](img/6e3001af190788e3cb6b7360a96fccf7_26.png)

Is what is called random forest。 So random forest is essentially the bagging that we just learn。

 So bootsshopping， aggregating with not only the subset of the rows being random。

 but also the subset of the features or columns also being random。



![](img/6e3001af190788e3cb6b7360a96fccf7_28.png)

So that's our new type of subset， not just a subset of those rows， subset of the rows and columns。



![](img/6e3001af190788e3cb6b7360a96fccf7_30.png)

And generally speaking， we need。A bit more trees。 But with those extra trees。

 we generally eventually get better out of sample accuracy compared to just simple bagging。

 as we see here on this graph。

![](img/6e3001af190788e3cb6b7360a96fccf7_32.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_33.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_34.png)

So we know we can further reduce air using random force。



![](img/6e3001af190788e3cb6b7360a96fccf7_36.png)

But how many trees do we actually need for random forests？



![](img/6e3001af190788e3cb6b7360a96fccf7_38.png)

Similar to with baggging。We can see at what threshold our out of bag air tends to plateau。

 And at that point， any additional trees will no longer improve our results。

 So that's how we come up with that number of trees by testing different values for the number of trees and where it tends to plateau。



![](img/6e3001af190788e3cb6b7360a96fccf7_40.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_41.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_42.png)

So how do we run random force in practice？It's going to be very similar to all the classification methods that we learned before。

 We're going to import the class。 So from SK learned ensemble。

 we import that random forest classifier。

![](img/6e3001af190788e3cb6b7360a96fccf7_44.png)

We're then going to initiate it here we're setting the number of estimators。

 the number of trees here equal to 50。

![](img/6e3001af190788e3cb6b7360a96fccf7_46.png)

We fit on our training set， we come up with our prediction on our test set。



![](img/6e3001af190788e3cb6b7360a96fccf7_48.png)

And then similar to before we can use cross validation in order to see which different hyperparameter perform better for out of sample fits and also for random force classifier。

 many of those hyperparameter will be similar to decision treats。



![](img/6e3001af190788e3cb6b7360a96fccf7_50.png)

And then if you want to do regression rather than classification。

 all you need to do is use the random force orgresser rather than the random force classifier and then ensure that your Y variable is a continuous value rather than different classes。



![](img/6e3001af190788e3cb6b7360a96fccf7_52.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_53.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_54.png)

Now， what about the cases where random force does not reduce the variance enough？



![](img/6e3001af190788e3cb6b7360a96fccf7_56.png)

So in the cases where even random forests are overfit。



![](img/6e3001af190788e3cb6b7360a96fccf7_58.png)

We can introduce even more randomness。We can also randomly select the actual splits in each one of our decision trees。



![](img/6e3001af190788e3cb6b7360a96fccf7_60.png)

And recall that decision trees typically use a greedy search to find a best split。

 So if a certain feature is available in a given subset。

 that feature may always be chosen as that first split at the top of the decision tree。



![](img/6e3001af190788e3cb6b7360a96fccf7_62.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_63.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_64.png)

As opposed to with this method， which will pick where to split and which feature to split at at random。



![](img/6e3001af190788e3cb6b7360a96fccf7_66.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_67.png)

These extra random trees。Are called fittingly extra random trees。 And the hope is。

 with enough random splits， we still have majority classes at each one of those leaf nodes。

 and the boat will still be a good classifier when all aggregated together。

 Even if those individual components are a bit weaker。😊。



![](img/6e3001af190788e3cb6b7360a96fccf7_69.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_70.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_71.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_72.png)

Now， we're going to walk through the syntax for creating these decision trees。 And as usual。

 itll be the same sets。 First， we're going to import the class containing the classification method。

 So here from Escalar do Ensemble， we import the extra trees classifier。



![](img/6e3001af190788e3cb6b7360a96fccf7_74.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_75.png)

We then set the number of estimators。We initiate the objects。Fit it on our training set。

Run our prediction on our test set。

![](img/6e3001af190788e3cb6b7360a96fccf7_77.png)

And then again we can tune those parameters using cross validation and use the extra trees regressiongressor for regression。

 so it's all the same steps that we saw before here replacing what was random forest with extra trees or what was bagging with extra trees and coming up with a more random classification method than either of those other two options。



![](img/6e3001af190788e3cb6b7360a96fccf7_79.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_80.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_81.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_82.png)

Now， just to recap what we learned here in this section in this section。

 we introduced this concept that we may be able to improve our predictive power by combining models。

 and this is what is called an ensemble based method。



![](img/6e3001af190788e3cb6b7360a96fccf7_84.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_85.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_86.png)

We introduced Botrap aggregation or bagging with the bootstrapping step being the step where we get random subsets of the original training set to build our classifiers。

 and the aggregation step being the step where we aggregate the classifications together using a majority vote。



![](img/6e3001af190788e3cb6b7360a96fccf7_88.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_89.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_90.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_91.png)

And finally， we showed how we can evolve from bagging to more random。

 less likely to overfit versions of the model， such as random forests with a random subset of the features and extra trees classifiers。

 which will even choose the splits of the decisionry at random。



![](img/6e3001af190788e3cb6b7360a96fccf7_93.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_94.png)

With that， we'll take what we learned and see it all in action in our notebook Den。 All right。

 I'll see you there。😊。

![](img/6e3001af190788e3cb6b7360a96fccf7_96.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_97.png)

![](img/6e3001af190788e3cb6b7360a96fccf7_98.png)