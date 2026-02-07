# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P112：23_支持向量机中的正则化.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So what have we learned so far in regards to support vector machines？

We know that they are a linear classifier。 We also know that they won't return probabilities。

 but rather will return labels， either one or0 churn versus not churn。

 And those labels are decided by which side of a certain decision boundary they fall on。

 and that decision boundary was initially found by determining that hyperplane or that line that minimized errorss。

 as well as finding that widest margin between our two classes。

 And that boundary was decided purely by the support vectors in our data by those points that are going to be on the margin that we had seen earlier。



![](img/724424c2da0ae2367468b6cfc8f7bd05_1.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_2.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_3.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_4.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_5.png)

We then discussed how we may actually be overfitting our data if we stick to this formulation。



![](img/724424c2da0ae2367468b6cfc8f7bd05_7.png)

As what we see here is the best boundary which minimizes our misclassifications。

 minimizing our hinge loss。

![](img/724424c2da0ae2367468b6cfc8f7bd05_9.png)

And that will refer to our first term in our overall cost function that we see here on the left。

 which is just the cost for misclassification。

![](img/724424c2da0ae2367468b6cfc8f7bd05_11.png)

And this term is minimal given the boundary that we have here。



![](img/724424c2da0ae2367468b6cfc8f7bd05_13.png)

However， for the second term in our overall function for support vector machines。

The regularization term。

![](img/724424c2da0ae2367468b6cfc8f7bd05_15.png)

There is an added cost to having a bit more of a complex decision boundary with higher coefficients。

So we may be minimizing the first portion of our cost function， but at the same time。

 the other portion of that regularization term is quite high。



![](img/724424c2da0ae2367468b6cfc8f7bd05_17.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_18.png)

So what do we do？Here we now have our less complex decision boundary。



![](img/724424c2da0ae2367468b6cfc8f7bd05_20.png)

And for this one， because we now have some misclassifications。

 this one that we see in pink to the left。

![](img/724424c2da0ae2367468b6cfc8f7bd05_22.png)

Our first term， that's just going to be the amount of misclassifications that we have that hinge loss。



![](img/724424c2da0ae2367468b6cfc8f7bd05_24.png)

That we're trying to minimize is now a bit higher。

![](img/724424c2da0ae2367468b6cfc8f7bd05_26.png)

But that regularization term should have been reduced by hopefully a greater degree so that that overall cost function is minimized。



![](img/724424c2da0ae2367468b6cfc8f7bd05_28.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_29.png)

And we want to note that the regularization effect here can be tweaked using this value of C。



![](img/724424c2da0ae2367468b6cfc8f7bd05_31.png)

Where here， a smaller sea will mean more regularized。 So the smaller the sea。

 the more that means the larger one overea is， and the more of an effect。

 the more we penalize for higher coefficients。

![](img/724424c2da0ae2367468b6cfc8f7bd05_33.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_34.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_35.png)

So let's give a closer look to this error term to this regularization term that we have here。



![](img/724424c2da0ae2367468b6cfc8f7bd05_37.png)

The vector beta， each one of our coefficients， represents the vector orthogonal to the hyperplane to our decision boundary。



![](img/724424c2da0ae2367468b6cfc8f7bd05_39.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_40.png)

And recall that these coefficients multiplied by their respectiveed features added up or what we would call the dot product of these coefficients and their respective features。



![](img/724424c2da0ae2367468b6cfc8f7bd05_42.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_43.png)

Will ultimately determine which side of the decision boundary our label will fall。



![](img/724424c2da0ae2367468b6cfc8f7bd05_45.png)

With values greater than zero for this dot product being a certain class and values less than zero being the other class。



![](img/724424c2da0ae2367468b6cfc8f7bd05_47.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_48.png)

And the dot product adding up to exactly zero represents where this decision boundary actually lies。



![](img/724424c2da0ae2367468b6cfc8f7bd05_50.png)

So that orthogonal line will be the value that we compute with values further away being larger。

 positive or negative values depending on which direction that line points。



![](img/724424c2da0ae2367468b6cfc8f7bd05_52.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_53.png)

And the higher those coefficients are。The larger the effect each feature has on determining that positive or negative class。



![](img/724424c2da0ae2367468b6cfc8f7bd05_55.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_56.png)

Now let's discuss how you can actually implement support vector machines using SKL in Python so the first thing that we're going to want to do is import the class containing our classification method。

 so from SKLarn to SVM we're going to import our model linear SVC so here we're specifying that we're just using linear support vector machines。

 we have not touched on kernel support vector machines which we'll touch on in just the next video。



![](img/724424c2da0ae2367468b6cfc8f7bd05_58.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_59.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_60.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_61.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_62.png)

So focusing in on that linear support vector machine。

 the first thing that we're going to want to do is create an instance of our class。



![](img/724424c2da0ae2367468b6cfc8f7bd05_64.png)

So when we create our instance， we are also going to pass in our hyperparameters。

 which here are going to be our regularization terms， with a penalty equal to L2。

 and a C value equal here to 10 and recall that a lower C value means more regularization and a simpler model。



![](img/724424c2da0ae2367468b6cfc8f7bd05_66.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_67.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_68.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_69.png)

We're then going to fit that instance on our training set， so we call LSVc。

fit and passing our Xtrain and Y train， and once we fit our model。

 we can use that fit in order to predict on our holdout set on our X test as we've done with our other models。



![](img/724424c2da0ae2367468b6cfc8f7bd05_71.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_72.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_73.png)

We can then tune our regularization parameters that see and the penalty that we choose using cross validation。

 we can use that grid search CV that we learned in earlier courses。



![](img/724424c2da0ae2367468b6cfc8f7bd05_75.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_76.png)

And then if you want to do regression rather than classification。

 you can just call linear SVM rather than linear SVC。



![](img/724424c2da0ae2367468b6cfc8f7bd05_78.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_79.png)

In order to perform regression and you'd run all the same steps except that your Y train would have to be continuous value。



![](img/724424c2da0ae2367468b6cfc8f7bd05_81.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_82.png)

So let's recap what we learned here in this section。



![](img/724424c2da0ae2367468b6cfc8f7bd05_84.png)

We discussed support vector machine approach to classification。

 how we use our support vectors from our different classes in order to find that decision boundary with the largest margin。



![](img/724424c2da0ae2367468b6cfc8f7bd05_86.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_87.png)

We compared support vector machines with logistic regression。

 what support vector machines were are predicting actual labels versus probabilities with logistic regression。

 our cost function for support vector machines only penalizes those on the wrong side of our boundary compared to all labels being or all outcomes being penalized with logistic regression。



![](img/724424c2da0ae2367468b6cfc8f7bd05_89.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_90.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_91.png)

And support vector machines only depend on those support vectors and then comes up with the largest margin using those support vectors。

 And something I'd like to note here is in the difference is that。



![](img/724424c2da0ae2367468b6cfc8f7bd05_93.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_94.png)

This means that support vector machines may be more sensitive to values that fall within our margin。

But they will not be affected at all by those large values classified correctly well outside our margin。

 If we recall that was a major problem that logistic regression was meant to solve and sport vector machines can be even stronger as they are going to completely ignore these outliers that are correctly identified。

 They won't have any effect on our overall model。

![](img/724424c2da0ae2367468b6cfc8f7bd05_96.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_97.png)

We also went over the support vector machine cost function。

 which was that hidden loss to minimize misclassifications。

 as well as that added regularization term， And we discussed how regularization actually works in support vector machine models。

 and that we can tune the value of C with a lower C。

 meaning higher regularization and a simpler model。



![](img/724424c2da0ae2367468b6cfc8f7bd05_99.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_100.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_101.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_102.png)

With that that closeds out our section on linear support vector machines。

 we're now going to expand on that and show how powerful support vector machines can be using something called kernels Allright。

 I'll see you in the next video。

![](img/724424c2da0ae2367468b6cfc8f7bd05_104.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_105.png)

![](img/724424c2da0ae2367468b6cfc8f7bd05_106.png)