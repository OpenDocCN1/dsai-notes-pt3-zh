# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p99 14_在MATLAB中评估分类模型.zh_en [BV1Jr421w7wL_p99]

🎼，You've just learned about classification model metrics， including accuracy， precision。

 recall and fallout， as well as techniques to evaluate and compare classification models using multiple metrics at once。

In this video， you'll apply the model evaluation methods you've learned to models trained in the classification learner app。

You'll see how to export your models or the training code itself into Scs for further analysis and customization。



![](img/dd044963793a161395068eea7ef199f8_1.png)

Let's start with a logistic regression model and medium KNN model you saw earlier。



![](img/dd044963793a161395068eea7ef199f8_3.png)

These models predict if a toll will be charged based on pickup and drop off locations。

The models were trained on the January taxi data， with no validation。



![](img/dd044963793a161395068eea7ef199f8_5.png)

You can get a rough idea of model performance from the scatter plot visuals of correctly and incorrectly classified observations。



![](img/dd044963793a161395068eea7ef199f8_7.png)

Remember， the accuracy for each model is shown here。



![](img/dd044963793a161395068eea7ef199f8_9.png)

It looks like both models do well according to this metric。However。

 you also just learned that you should always consider more than one metric when evaluating classification models。



![](img/dd044963793a161395068eea7ef199f8_11.png)

![](img/dd044963793a161395068eea7ef199f8_12.png)

Let's look at the Conci matrix to see how to assess the other metrics in the app。



![](img/dd044963793a161395068eea7ef199f8_14.png)

The Con matrix shows the correctly and incorrectly classified data in absolute terms。



![](img/dd044963793a161395068eea7ef199f8_16.png)

Since toll paid is a logical variable， the two class outcomes are named true and false。

Be careful not to confuse these class names with the true and false in the metrics names。Remember。

 fier means no toll。And true means to。Either outcome could be considered the positive or negative class。

For example， considering the false or no to class as the positive one。

You have the true positives in the upper left， true negatives in the lower right。

 falsese negatives in the upper right and false positives in the lower left。However。

 if you consider the true or to class as the positive one， the true positives and negative swap。

 as do the false positives and negatives。It just depends on which class you consider positive。



![](img/dd044963793a161395068eea7ef199f8_18.png)

You can calculate all the metrics you've learned for each class from the confusion matrix itself。

 or you can have the app calculate them for you。

![](img/dd044963793a161395068eea7ef199f8_20.png)

Select the true Poitive rates， falsese negative rates option under plot。



![](img/dd044963793a161395068eea7ef199f8_22.png)

The matrix entries change to percentages and two new columns appear。

These new columns report the true positive rate and false negative rate。

 considering the actual class in each row as the positive one。

Notice that these percentages are the same that you see in the confusion matrix now。

This is only true for binary classification。Later， when you train multiclass models。

 these percentages will differ。For binary classification， the true positive rate for one class。

Is the true negative rate for the other？Similarly， the false negative rate for one class is the false positive rate for the other。

You can get all four of these metrics for each class using these facts。For example。

 if you want both the true positive rate or recall and false positive rate or fallout for the false class here。

These are given by the true positive rate in the false class row and the false negative rate for the true class row。



![](img/dd044963793a161395068eea7ef199f8_24.png)

If instead of recall， you need to know precision， select the Poitive Pretive valuesues Fse Discovery ratess option。



![](img/dd044963793a161395068eea7ef199f8_26.png)

Now， instead of focusing on the rows of the confusion matrix。

 you're focusing on percentages for the columns or total predictions。

The positive predictive value gives the precision of a given class。As you might imagine。

 you can also obtain the false discovery rate， negative predictive value。

 and false emission rate for each class in similar ways you just saw with the row normalized metrics。



![](img/dd044963793a161395068eea7ef199f8_28.png)

![](img/dd044963793a161395068eea7ef199f8_29.png)

Now that you can interpret the confusion matrix， let's evaluate the models。



![](img/dd044963793a161395068eea7ef199f8_31.png)

The logistic regression model has excellent recall for the false or no total class of 99%。

 but very poor fallout of 90% for this class。In other words。

 trips that have a toll will be misclassified9 out of 10 times。



![](img/dd044963793a161395068eea7ef199f8_33.png)

Let's compare these results to the medium can and model。



![](img/dd044963793a161395068eea7ef199f8_35.png)

The recall is above 99%， and followed is much better， just 14% for the false class。



![](img/dd044963793a161395068eea7ef199f8_37.png)

Is this the best each model can do。Remember， an ROC curve is used to show the relationship between recall and fallout。



![](img/dd044963793a161395068eea7ef199f8_39.png)

Let's look at the ROC curve for the logistic regression model。

The current classifier denoted by the red marker uses the default threshold of 0。5。

The area under the curve of 0。93 suggests this model is capable of a better recall fallout trade off if you were to use a threshold different than the default。

It looks like with a higher threshold value， you could get a fallout down to the 14% that the canN N model had。

 while maintaining a recall above 95%。

![](img/dd044963793a161395068eea7ef199f8_41.png)

To customize the threshold and view the updated confusion matrix。

 export the model to the MALb Workspace。Or generate the code to train a new model with customizations。



![](img/dd044963793a161395068eea7ef199f8_43.png)

You'll work through evaluating and customizing models in code in a later reading。



![](img/dd044963793a161395068eea7ef199f8_45.png)

Let's recap what you've learned。You saw how to evaluate classification models and apply ROC。

 a UC analysis to models trained in the classification learner app。

Then you saw how to export your models or the training code itself for further analysis and customization。



![](img/dd044963793a161395068eea7ef199f8_47.png)

🎼。