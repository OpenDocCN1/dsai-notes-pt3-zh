# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P13：12_分类模型评价指标.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

![](img/71c39543635029ab724dd3f6f6af3a65_0.png)

Hello and welcome In this video， we'll be covering evaluation metrics for classifiers。



![](img/71c39543635029ab724dd3f6f6af3a65_2.png)

So let's get started。Evaluation metrics explain the performance of a model。

 Let's talk more about the model evaluation metrics that are used for classification。

 Imagine that we have an historical data set， which shows the customer churn for a telecommunication company。

 We have trained the model， and now we want to calculate its accuracy using the test set。

 We pass the test set to our model and we find the predicted labels。 Now， the question is。

 how accurate is this model。 Basically， we compare the actual values in the test set with the values predicted by the model to calculate the accuracy of the model。

 Evalation metrics provide a key role in the development of a model as they provide insight to areas that might require improvement。

😊。

![](img/71c39543635029ab724dd3f6f6af3a65_4.png)

![](img/71c39543635029ab724dd3f6f6af3a65_5.png)

![](img/71c39543635029ab724dd3f6f6af3a65_6.png)

![](img/71c39543635029ab724dd3f6f6af3a65_7.png)

![](img/71c39543635029ab724dd3f6f6af3a65_8.png)

There are different model evaluation metrics， but we just talk about three of them here。

 specifically Jaard indexdex， F1 score， and log loss。

Let's first look at one of the simplest accuracy measurements， the Jaard index。

 also known as the Jaard similarity coefficient。

![](img/71c39543635029ab724dd3f6f6af3a65_10.png)

Let's say Y shows the true labels of the churnern data set。

 and Y hat shows the predicted values by our classifier。

 Then we can define Jaard as the size of the intersection divided by the size of the union of two label sets。



![](img/71c39543635029ab724dd3f6f6af3a65_12.png)

![](img/71c39543635029ab724dd3f6f6af3a65_13.png)

![](img/71c39543635029ab724dd3f6f6af3a65_14.png)

![](img/71c39543635029ab724dd3f6f6af3a65_15.png)

For example， for a test set of size 10 with eight correct predictions or eight intersections。

 the accuracy by the Jaard index would be 0。66。

![](img/71c39543635029ab724dd3f6f6af3a65_17.png)

![](img/71c39543635029ab724dd3f6f6af3a65_18.png)

If the entire set of predicted labels for a sample strictly matches with the true set of labels。

 then the subset accuracy is 1。0。 Otherwise， it is 0。0。



![](img/71c39543635029ab724dd3f6f6af3a65_20.png)

![](img/71c39543635029ab724dd3f6f6af3a65_21.png)

Another way of looking at accuracy of classifiers is to look at a confusion matrix。



![](img/71c39543635029ab724dd3f6f6af3a65_23.png)

For example， let's assume that our test set has only 40 rows。

 This matrix shows the corrected and wrong predictions in comparison with the actual labels。



![](img/71c39543635029ab724dd3f6f6af3a65_25.png)

![](img/71c39543635029ab724dd3f6f6af3a65_26.png)

![](img/71c39543635029ab724dd3f6f6af3a65_27.png)

Each confusion matrix row shows the actual true labels in the test set。

 and the columns show the predicted labels by classifier。 Let's look at the first row。



![](img/71c39543635029ab724dd3f6f6af3a65_29.png)

![](img/71c39543635029ab724dd3f6f6af3a65_30.png)

The first row is for customers whose actual churn value in the test set is one。

 As you can calculate out of 40 customers， the churn value of 15 of them is  one and out of these 15。

 the classifier correctly predicted 6 of them as  one and 9 of them as 0。



![](img/71c39543635029ab724dd3f6f6af3a65_32.png)

![](img/71c39543635029ab724dd3f6f6af3a65_33.png)

![](img/71c39543635029ab724dd3f6f6af3a65_34.png)

This means that for six customers， the actual churn value was one in the test set。

 and the classifier also correctly predicted those as one。 However。

 while the actual label of 9 customers was one。 The classifier predicted those as 0。

 which is not very good。 We can consider this as an error of the model for the first row。

 what about the customers with a churn value 0， let's look at the second row。



![](img/71c39543635029ab724dd3f6f6af3a65_36.png)

![](img/71c39543635029ab724dd3f6f6af3a65_37.png)

![](img/71c39543635029ab724dd3f6f6af3a65_38.png)

![](img/71c39543635029ab724dd3f6f6af3a65_39.png)

![](img/71c39543635029ab724dd3f6f6af3a65_40.png)

It looks like there were 25 customers whose churn value was0。



![](img/71c39543635029ab724dd3f6f6af3a65_42.png)

The classifier correctly predicted 24 of them is 0， and one of them wrongly predicted as one。

 So it has done a good job in predicting the customers with a churn value of 0。

 a good thing about the confusion matrix is that it shows the model's ability to correctly predict or separate the classes。

 In the specific case of a binary classifier， such as this example。

 we can interpret these numbers as the count of true positives， false negatives。

 truee negatives and false positives。😊。

![](img/71c39543635029ab724dd3f6f6af3a65_44.png)

![](img/71c39543635029ab724dd3f6f6af3a65_45.png)

![](img/71c39543635029ab724dd3f6f6af3a65_46.png)

![](img/71c39543635029ab724dd3f6f6af3a65_47.png)

![](img/71c39543635029ab724dd3f6f6af3a65_48.png)

![](img/71c39543635029ab724dd3f6f6af3a65_49.png)

Based on the count of each section， we can calculate the precision and recall of each label。



![](img/71c39543635029ab724dd3f6f6af3a65_51.png)

Precision is a measure of the accuracy provided that a class label has been predicted。

 It is defined by precision equals true positive， divided by true positive plus false positive。😊。



![](img/71c39543635029ab724dd3f6f6af3a65_53.png)

![](img/71c39543635029ab724dd3f6f6af3a65_54.png)

![](img/71c39543635029ab724dd3f6f6af3a65_55.png)

And recall is the true positive rate。 It is defined as recall equals true positive divided by true positive plus false negative。

 so we can calculate the precision and recall of each class。😊。



![](img/71c39543635029ab724dd3f6f6af3a65_57.png)

![](img/71c39543635029ab724dd3f6f6af3a65_58.png)

![](img/71c39543635029ab724dd3f6f6af3a65_59.png)

Now we're in the position to calculate the F1 scores for each label based on the precision and recall of that label。



![](img/71c39543635029ab724dd3f6f6af3a65_61.png)

![](img/71c39543635029ab724dd3f6f6af3a65_62.png)

The F1 score is the harmonic average of the precision and recall。

 where an F1 score reaches its best value at one， which represents perfect precision and recall。

 and its worst at 0。 It is a good way to show that a classifier has a good value for both recall and precision。

 It is defined using the F1 score equation。

![](img/71c39543635029ab724dd3f6f6af3a65_64.png)

![](img/71c39543635029ab724dd3f6f6af3a65_65.png)

For example， the F1 score for class 0 Ie churn equals 0 is 0。83 and the F1 score for class 1 I。

e churn equals 1 is 0。55。And finally， we can tell the average accuracy for this classifier is the average of the F1 score for both labels。

 which is 0。72。 In our case。 Please notice that both jaard and F1 score can be used for multi class classifiers as well。

 which is out of scope for this course。😊，Now， let's look at another accuracy metric for classifiers。

 Sometimes the output of a classifier is the probability of a class label instead of the label。

 For example， in logistic regression， The output can be the probability of customer churn， I。e。 yes。

 or equals to1。 This probability is of value between 0 and1。😊。



![](img/71c39543635029ab724dd3f6f6af3a65_67.png)

![](img/71c39543635029ab724dd3f6f6af3a65_68.png)

![](img/71c39543635029ab724dd3f6f6af3a65_69.png)

Logarithmic loss， also known as log loss， measures the performance of a classifier where the predicted output is a probability value between0 and 1。

 so for example， predicting a probability of 0。13 when the actual label is 1 would be bad and would result in a high log loss。

 we can calculate the log loss for each row using the log loss equation which measures how far each prediction is from the actual label。

 then we calculate the average log loss across all rows of the test set。

It is obvious that ideal classifiers have progressively smaller values of log laws。

 so the classifier with the lower log loss has better accuracy。 Thanks for watching。

