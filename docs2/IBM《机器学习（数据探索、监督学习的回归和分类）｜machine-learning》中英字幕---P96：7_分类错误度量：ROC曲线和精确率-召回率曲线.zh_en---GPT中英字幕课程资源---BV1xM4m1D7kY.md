# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P96：7_分类错误度量：ROC曲线和精确率-召回率曲线.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So as we discussed， we're going to introduce another method of evaluating our classification metrics。

 namely here the receiver operating characteristic curve or the ROC curve。



![](img/97b779f094505e6a13ed5c13bb33120b_1.png)

![](img/97b779f094505e6a13ed5c13bb33120b_2.png)

![](img/97b779f094505e6a13ed5c13bb33120b_3.png)

An ROC curve indicates the sensitivity or the recall out of all of our actual positives。

 how many did we get correct on our Y axis？

![](img/97b779f094505e6a13ed5c13bb33120b_5.png)

And then the false positive rate or one minus the specificity on our x axis and specificity is our true negative rate。

 if you recall， we discussed that in the last video。

 one minus this value is going to be the false positive rate。

 so if we got all of our negatives correctly identified， then our false positive rate is zero。



![](img/97b779f094505e6a13ed5c13bb33120b_7.png)

![](img/97b779f094505e6a13ed5c13bb33120b_8.png)

![](img/97b779f094505e6a13ed5c13bb33120b_9.png)

![](img/97b779f094505e6a13ed5c13bb33120b_10.png)

![](img/97b779f094505e6a13ed5c13bb33120b_11.png)

And then for every actual negative we predict incorrectly as positive。

 we increase this false positive rate。

![](img/97b779f094505e6a13ed5c13bb33120b_13.png)

This looks at the predictive probabilities that we output。

 which is just going to be a list of scores， not a list of classes， so rather than outputting1 or0。

 it's going to output a value such as 0。9， meaning it's pretty certain that the value is 1 or 0。

1 meaning it's pretty certain the value should have been zero it's then going to plot both this sensitivity and the false positive rate values for various score thresholds。



![](img/97b779f094505e6a13ed5c13bb33120b_15.png)

![](img/97b779f094505e6a13ed5c13bb33120b_16.png)

![](img/97b779f094505e6a13ed5c13bb33120b_17.png)

![](img/97b779f094505e6a13ed5c13bb33120b_18.png)

![](img/97b779f094505e6a13ed5c13bb33120b_19.png)

![](img/97b779f094505e6a13ed5c13bb33120b_20.png)

So here we can start considering thresholds other than the 0。

5 that we've been using for logistic regression。

![](img/97b779f094505e6a13ed5c13bb33120b_22.png)

And we can think again to our trade off， if our threshold for predicting positive is really high。

 such as 0。99， then we will have a high true positive rate。

 which is going to be the top of our chart， but also a high false positive right。



![](img/97b779f094505e6a13ed5c13bb33120b_24.png)

![](img/97b779f094505e6a13ed5c13bb33120b_25.png)

![](img/97b779f094505e6a13ed5c13bb33120b_26.png)

Which is also going to be to the right of our chart if we pick a very low threshold， say 0。01。

 then we will have a low false positive rate to the left of our plot。

 but also a low true positive rate， which is our bottom of our plot。



![](img/97b779f094505e6a13ed5c13bb33120b_28.png)

![](img/97b779f094505e6a13ed5c13bb33120b_29.png)

![](img/97b779f094505e6a13ed5c13bb33120b_30.png)

And that's what's creating this straight diagonal across。

 so you're not interested here in the classes predicted about how meaningful the class probabilities output by the model actually are。



![](img/97b779f094505e6a13ed5c13bb33120b_32.png)

![](img/97b779f094505e6a13ed5c13bb33120b_33.png)

![](img/97b779f094505e6a13ed5c13bb33120b_34.png)

So that diagonal of this matrix represents the value that can be obtained by just randomly guessing。

 if we randomly guess then we can set them all to one， all to zero and end up on either corner。

 otherwise we can end up somewhere in the middle。

![](img/97b779f094505e6a13ed5c13bb33120b_36.png)

![](img/97b779f094505e6a13ed5c13bb33120b_37.png)

![](img/97b779f094505e6a13ed5c13bb33120b_38.png)

The lower right portion， we want to avoid those are models that end up here doing worse than guessing and this will almost never happen with our models。

 the top left。

![](img/97b779f094505e6a13ed5c13bb33120b_40.png)

![](img/97b779f094505e6a13ed5c13bb33120b_41.png)

Is where we want to be。

![](img/97b779f094505e6a13ed5c13bb33120b_43.png)

And the closer we are to that top left corner， the better we are with all the way in the top left being our perfect model。

 that means we have a really high true positive rate and because it's all the way to the left。

 a really low false positive rate。

![](img/97b779f094505e6a13ed5c13bb33120b_45.png)

![](img/97b779f094505e6a13ed5c13bb33120b_46.png)

![](img/97b779f094505e6a13ed5c13bb33120b_47.png)

So now the ROC area under the curve。

![](img/97b779f094505e6a13ed5c13bb33120b_49.png)

Sometimes called ROCAU gives a measure of how well we are separating the two classes。



![](img/97b779f094505e6a13ed5c13bb33120b_51.png)

One is perfect classification and we'll be close to that top left corner with a high true positive rate and a low。

 false positive rate。

![](img/97b779f094505e6a13ed5c13bb33120b_53.png)

![](img/97b779f094505e6a13ed5c13bb33120b_54.png)

We see as we move further to the right。

![](img/97b779f094505e6a13ed5c13bb33120b_56.png)

That the value decreases。

![](img/97b779f094505e6a13ed5c13bb33120b_58.png)

And as we get to 0。5， this is essentially as good as picking at random and similar to our F1 score。

 this is again a balanced metric as opposed to accuracy which can have an inflated value。

 even with a useless such as predicting all zeros， such a useless model。

 this will not fall track to that same unbalanced metric。



![](img/97b779f094505e6a13ed5c13bb33120b_60.png)

![](img/97b779f094505e6a13ed5c13bb33120b_61.png)

![](img/97b779f094505e6a13ed5c13bb33120b_62.png)

And the curve will always connect that bottom left， no false positives， but also no true positives。

 essentially a threshold that predicts all zero to this upper right corner， all the true positives。

 but also a lot of false positives， essentially a threshold that predicts all one。



![](img/97b779f094505e6a13ed5c13bb33120b_64.png)

![](img/97b779f094505e6a13ed5c13bb33120b_65.png)

![](img/97b779f094505e6a13ed5c13bb33120b_66.png)

![](img/97b779f094505e6a13ed5c13bb33120b_67.png)

In practice， it will almost always be a convex curve as we see here with the 0。9 or the 0。75。



![](img/97b779f094505e6a13ed5c13bb33120b_69.png)

Similar to the ROC curve， we can plot the precision recall values for various score thresholds。



![](img/97b779f094505e6a13ed5c13bb33120b_71.png)

Now this is an unbalanced metric， this will mostly be a decreasing curve。

 the curve will end up at the right where recall is equal to one。

 we predicted all ones and then position would just be equal to the number of positives over all the possible labels because we predicted them all as one so it's just the number of positives。



![](img/97b779f094505e6a13ed5c13bb33120b_73.png)

![](img/97b779f094505e6a13ed5c13bb33120b_74.png)

![](img/97b779f094505e6a13ed5c13bb33120b_75.png)

![](img/97b779f094505e6a13ed5c13bb33120b_76.png)

Versus all that we predicted as positive， that's going to be our precision。



![](img/97b779f094505e6a13ed5c13bb33120b_78.png)

Think at the left， we are starting at predicting all zeros。

 so there's no recall but also no precision because we haven't predicted any true values but then we can get very high precision almost immediately which is why we see that jump in model 1 once we have a threshold of let's say 99。

99 and then we are very certain for that single one that we have predicted it correct。

 so therefore we have a high precision and here our area under the curve will depend on how unbalanced our data set is。



![](img/97b779f094505e6a13ed5c13bb33120b_80.png)

![](img/97b779f094505e6a13ed5c13bb33120b_81.png)

![](img/97b779f094505e6a13ed5c13bb33120b_82.png)

![](img/97b779f094505e6a13ed5c13bb33120b_83.png)

So how do we choose the right approach， which approach works best for choosing a classifier？



![](img/97b779f094505e6a13ed5c13bb33120b_85.png)

The ROC curve will generally do better for data with balanced classes。



![](img/97b779f094505e6a13ed5c13bb33120b_87.png)

The precision recall curve will generally be better suited for data with imbalance classes。

 so something similar to what we saw with our leukemia example。



![](img/97b779f094505e6a13ed5c13bb33120b_89.png)

![](img/97b779f094505e6a13ed5c13bb33120b_90.png)

The right curve will depend on tying our results。

![](img/97b779f094505e6a13ed5c13bb33120b_92.png)

2 so true positive versus true negative to our outcomes and the relative cost of false positives versus false negatives。

 so for example， if we want to predict whether our customer is likely to churn and initiate intervention if that customer does churn the prediction threshold takes that customer's value。



![](img/97b779f094505e6a13ed5c13bb33120b_94.png)

![](img/97b779f094505e6a13ed5c13bb33120b_95.png)

![](img/97b779f094505e6a13ed5c13bb33120b_96.png)

![](img/97b779f094505e6a13ed5c13bb33120b_97.png)

Loss if the customer returns and the cost of intervention both into account when trying to come up with that threshold。



![](img/97b779f094505e6a13ed5c13bb33120b_99.png)

![](img/97b779f094505e6a13ed5c13bb33120b_100.png)

And since business outcomes， relative costs of false positive versus false negative will probably lead to a specific decision threshold for an application。

 results at that threshold may be more relevant than results across all threshold。

 which is what we're getting with both the ROC and the precision recall curves。

 so we may want to just look at precision， just look at recall， just look at the F1 score。



![](img/97b779f094505e6a13ed5c13bb33120b_102.png)

![](img/97b779f094505e6a13ed5c13bb33120b_103.png)

![](img/97b779f094505e6a13ed5c13bb33120b_104.png)

![](img/97b779f094505e6a13ed5c13bb33120b_105.png)

![](img/97b779f094505e6a13ed5c13bb33120b_106.png)