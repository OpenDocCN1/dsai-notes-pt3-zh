# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P95：6_混淆矩阵、准确率、特异性、精确率和召回率.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's discuss this concept of classification error metrics。

 which will be of utmost importance to keep in mind as we begin building machine learning models for classification。

So in this section， we're going to go over different types of errors to be aware of when we're working with classification problems。



![](img/7e9920585b67434b6c9e98e5477e08da_1.png)

![](img/7e9920585b67434b6c9e98e5477e08da_2.png)

Some approaches to measuring classification outcomes according to the different types of errors that can be made。



![](img/7e9920585b67434b6c9e98e5477e08da_4.png)

And finally， how to ultimately use classification error metrics to choose between our different models。



![](img/7e9920585b67434b6c9e98e5477e08da_6.png)

Throughout the last course， we have extensively covered how models are selected based on splitting the data and calculating the error on some holdoutset。



![](img/7e9920585b67434b6c9e98e5477e08da_8.png)

Let's now move on to how to best calculate that error。



![](img/7e9920585b67434b6c9e98e5477e08da_10.png)

The choice of the right error metric depends heavily on the question and the data available。



![](img/7e9920585b67434b6c9e98e5477e08da_12.png)

For example， assume we're trying to classify patients likely to get leukemia。



![](img/7e9920585b67434b6c9e98e5477e08da_14.png)

In our training data， a large majority， 99% of patients are healthy。



![](img/7e9920585b67434b6c9e98e5477e08da_16.png)

Let's say we built a classifier and use accuracy as our error metric。



![](img/7e9920585b67434b6c9e98e5477e08da_18.png)

If we used accuracy as our measure， a simple model could be built that always predicts healthy。

 and although this is a useless model， it would result in 99% accuracy。 Thus。

 we see the importance in understanding our data and choosing the appropriate metric。

 Ac is often not the right metric for a binary classification problem。



![](img/7e9920585b67434b6c9e98e5477e08da_20.png)

![](img/7e9920585b67434b6c9e98e5477e08da_21.png)

![](img/7e9920585b67434b6c9e98e5477e08da_22.png)

![](img/7e9920585b67434b6c9e98e5477e08da_23.png)

![](img/7e9920585b67434b6c9e98e5477e08da_24.png)

So when thinking about errors with classification， we often talk about a confusion matrix。

The vertical axis in our confusion matrix contains rows that correspond to the ground truth。

 either positive or negative here， and the horizontal axis So each one of our columns corresponds to what the model ends up predicting。

 either true or false， right， either positive or negative。



![](img/7e9920585b67434b6c9e98e5477e08da_26.png)

![](img/7e9920585b67434b6c9e98e5477e08da_27.png)

![](img/7e9920585b67434b6c9e98e5477e08da_28.png)

The blue diagonal that we see is going to be the elements that are correctly predicted values。



![](img/7e9920585b67434b6c9e98e5477e08da_30.png)

And then the red diagonal off from the right corner to the left corner is going to be the elements corresponding to the errors。



![](img/7e9920585b67434b6c9e98e5477e08da_32.png)

![](img/7e9920585b67434b6c9e98e5477e08da_33.png)

The bottom left is going to be a false positive， which is also called a type1 error。

 and then the top right is going to be a false negative。

 which is also sometimes called a type2 error。

![](img/7e9920585b67434b6c9e98e5477e08da_35.png)

![](img/7e9920585b67434b6c9e98e5477e08da_36.png)

![](img/7e9920585b67434b6c9e98e5477e08da_37.png)

So let's walk through some of the measures that we may use for this measuring error with classification。



![](img/7e9920585b67434b6c9e98e5477e08da_39.png)

First is our classic accuracy measure。

![](img/7e9920585b67434b6c9e98e5477e08da_41.png)

We can calculate accuracy as the sum of both correct predictions。

 true positives and true negatives are blue values that we have。

 And the denominator is the total number of samples。

 So total correct prediction over all of our labels。 This is probably the most common ametric。

 but it can be deceiving in situations like we just saw before， where the population may be skewed。



![](img/7e9920585b67434b6c9e98e5477e08da_43.png)

![](img/7e9920585b67434b6c9e98e5477e08da_44.png)

![](img/7e9920585b67434b6c9e98e5477e08da_45.png)

![](img/7e9920585b67434b6c9e98e5477e08da_46.png)

Next we have recall， or you may have heard this called sensitivity。

 which is our ability to identify all the actual positive incidents。



![](img/7e9920585b67434b6c9e98e5477e08da_48.png)

![](img/7e9920585b67434b6c9e98e5477e08da_49.png)

So when we're trying to recall all the actual positive instances。

 recall measures the percentage of the actual positive class that is correctly predicted so out of that top row of true positives how many did we predict correctly in other words this is going to be the capture rate so with our example what percentage of the true leukemia cases is our model capturing and notice that you can easily achieve 100% recall by predicting everything to be positive everyone has leukemia so then out of all of our actual positives because we predicted everyone has leukemia we got those all correct。



![](img/7e9920585b67434b6c9e98e5477e08da_51.png)

![](img/7e9920585b67434b6c9e98e5477e08da_52.png)

![](img/7e9920585b67434b6c9e98e5477e08da_53.png)

![](img/7e9920585b67434b6c9e98e5477e08da_54.png)

![](img/7e9920585b67434b6c9e98e5477e08da_55.png)

![](img/7e9920585b67434b6c9e98e5477e08da_56.png)

![](img/7e9920585b67434b6c9e98e5477e08da_57.png)

To balance that， enter precision。

![](img/7e9920585b67434b6c9e98e5477e08da_59.png)

With precision， we are identifying out of all our positive predictions that left most column out of our predictions。

 How many did we get correct？When the model predicts leukemia， how often is it right？

If you always predict leukemia， then your recall will be 100%， but your precision here。

 all of your predictions， a lot of them will be wrong， So it will suffer a lot。

 So you'll have this trade off。So notice you can also predict one really sure case to be leukemia and everything else you can predict to be non leukemia and end up achieving 100% precision。



![](img/7e9920585b67434b6c9e98e5477e08da_61.png)

![](img/7e9920585b67434b6c9e98e5477e08da_62.png)

And in that case， your recall would be very low。 You only captured one of the true cases out of all them。

 So there's this trade off here between precision and recall。



![](img/7e9920585b67434b6c9e98e5477e08da_64.png)

Next we have specificity， so trying to avoid our false alarms。



![](img/7e9920585b67434b6c9e98e5477e08da_66.png)

Here， we're only looking at that bottom row of actual negative classes。

 and specificity is concerned with how correctly the actual negative class is predicted。

 In other words， it's going to be the recall for class 0 out of all the cases where we do not have leukemia。

 How often do we correctly identify those patients as not having leukemia。😊。



![](img/7e9920585b67434b6c9e98e5477e08da_68.png)

![](img/7e9920585b67434b6c9e98e5477e08da_69.png)

![](img/7e9920585b67434b6c9e98e5477e08da_70.png)

![](img/7e9920585b67434b6c9e98e5477e08da_71.png)

And we can see how it would be much more important for our leukemia example to have higher recall。

 identify all the true positives correctly than any of our other measures that we've discussed。



![](img/7e9920585b67434b6c9e98e5477e08da_73.png)

![](img/7e9920585b67434b6c9e98e5477e08da_74.png)

![](img/7e9920585b67434b6c9e98e5477e08da_75.png)

So putting these all together， we have accuracy to measure how well we classified overall but can be heavily thrown off by skewed data。



![](img/7e9920585b67434b6c9e98e5477e08da_77.png)

![](img/7e9920585b67434b6c9e98e5477e08da_78.png)

We have precision， which is out of all our predicted positive。

 We see the denominator here is true positive and false positive。 so all of our predicted positive。

 how many did we actually get correct？

![](img/7e9920585b67434b6c9e98e5477e08da_80.png)

![](img/7e9920585b67434b6c9e98e5477e08da_81.png)

We have recall and here our denominator is all the actual positives。

 both true positive and false negatives and false negatives are the addict negative when they were actually positive。

 so we are seeing out of all our actual positives， which ones we calculated correctly。



![](img/7e9920585b67434b6c9e98e5477e08da_83.png)

![](img/7e9920585b67434b6c9e98e5477e08da_84.png)

![](img/7e9920585b67434b6c9e98e5477e08da_85.png)

And then specificity， which we will just be recall for our negatives， so for all actual negatives。

 which ones did we predict correctly？

![](img/7e9920585b67434b6c9e98e5477e08da_87.png)

![](img/7e9920585b67434b6c9e98e5477e08da_88.png)

The last important metric is going to be this F1 score。

 and the F1 score is two times the product of our precision and recall over their sum。



![](img/7e9920585b67434b6c9e98e5477e08da_90.png)

![](img/7e9920585b67434b6c9e98e5477e08da_91.png)

And this is sometimes called the harmonic mean。 And the F1 score is a nice metric because it uses both precision and recall。

 and it tries to capture this trade off between recall and precision。 Unlike just using accuracy。

 this trade off will more heavily weight if either precision or recall is too low。



![](img/7e9920585b67434b6c9e98e5477e08da_93.png)

![](img/7e9920585b67434b6c9e98e5477e08da_94.png)

![](img/7e9920585b67434b6c9e98e5477e08da_95.png)

![](img/7e9920585b67434b6c9e98e5477e08da_96.png)

So optimizing F1 will not allow for the corner cases like predicting everything to be one。



![](img/7e9920585b67434b6c9e98e5477e08da_98.png)

In this next video， we will continue our discussion of classification metrics with an introduction of another metric。

 the ROC curve， as well as showing how we can quickly make each of these values readily available that we just discussed using Scalalar。



![](img/7e9920585b67434b6c9e98e5477e08da_100.png)

![](img/7e9920585b67434b6c9e98e5477e08da_101.png)

![](img/7e9920585b67434b6c9e98e5477e08da_102.png)