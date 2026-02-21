# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p20 9_MATLAB 中评估分类模型.zh_en -BV1yJ4m13715_p20-

🎼，Accuracy is a useful way to evaluate a model's effectiveness by assessing its ability to correctly label images across all classes。

However。To meet an application's needs， you'll often need to consider other metrics。

 such as recall and fall out。For the rest of this video。

 imagine your training a model to classify images of concrete and find areas in need of repair。



![](img/42b427c9b6ef0170c81130c12bdada51_1.png)

![](img/42b427c9b6ef0170c81130c12bdada51_2.png)

Incorrectly asserting that there is a crack and undamaged concrete will result in wasted effort。



![](img/42b427c9b6ef0170c81130c12bdada51_4.png)

But missing a crack could be dangerous。So how can you adjust your training approach when not all errors have equal consequences？



![](img/42b427c9b6ef0170c81130c12bdada51_6.png)

Because false positives lead to less severe errors than false negatives。

 Instead of finding the highest overall accuracy， you'll want to emphasize the recall of the crack class。

To this end， assume the goal is to correctly identify 99% of the cracks。

While keeping the false positives below 10%。

![](img/42b427c9b6ef0170c81130c12bdada51_8.png)

In this video。You'll use the Class learner app to visualize a model's recall and fall out using confusion matrices and ROC curves。



![](img/42b427c9b6ef0170c81130c12bdada51_10.png)

Then you'll train a model that takes misclassification severity into account using a cost matrix。



![](img/42b427c9b6ef0170c81130c12bdada51_12.png)

Let's get started。

![](img/42b427c9b6ef0170c81130c12bdada51_14.png)

In the classification learner app， we've trained a canN N model that classifies images as having cracks or no cracks。



![](img/42b427c9b6ef0170c81130c12bdada51_16.png)

![](img/42b427c9b6ef0170c81130c12bdada51_17.png)

This model has a high accuracy， but let's see if it meets the application's goals。



![](img/42b427c9b6ef0170c81130c12bdada51_19.png)

Open the confusion matrix to examine its ability to identify cracks。



![](img/42b427c9b6ef0170c81130c12bdada51_21.png)

And select true positive rates， false negative rates to show each class's recall。



![](img/42b427c9b6ef0170c81130c12bdada51_23.png)

Remember， true positive rates is synonymous with recall。

And false discovery rates is another term for fallout。



![](img/42b427c9b6ef0170c81130c12bdada51_25.png)

Therefore， if you instead wanted to see the models fall out。

 you'd select the positive predictive values false discovery rates option。



![](img/42b427c9b6ef0170c81130c12bdada51_27.png)

Looking at the crack's true positive rate， you can see that the recall is below the goal of 99%。

Too many cracks are being missed。

![](img/42b427c9b6ef0170c81130c12bdada51_29.png)

Open the R of C curve。And set the positive class to crack。



![](img/42b427c9b6ef0170c81130c12bdada51_31.png)

An ROC curve allows you to visualize both metrics， recall and fall out in a single plot。

The area under the curve or AU is a simple to interpret metric for a model's balance of recall and followout。



![](img/42b427c9b6ef0170c81130c12bdada51_33.png)

The higher the score， the better。We know from the confusion matrix that the current model's performance is falling short of its goal。



![](img/42b427c9b6ef0170c81130c12bdada51_35.png)

But before you train a new model， you'll want to know if the desired result is even possible。



![](img/42b427c9b6ef0170c81130c12bdada51_37.png)

To answer this question， examine the RO C curve to see if there is any point where the recall is at least 99% and the fallout is below 10%。

Zoom in。And click points on the curve to see their values。啊，哈。

You can see that there is a place where the recall and fallout meet the requirements。



![](img/42b427c9b6ef0170c81130c12bdada51_39.png)

The current model treats all errors as being equally bad。 However， in this case。

 missing a crack is worse than predicting a crack that isn't there。



![](img/42b427c9b6ef0170c81130c12bdada51_41.png)

You can train a new medium K& N model。

![](img/42b427c9b6ef0170c81130c12bdada51_43.png)

That shifts the balance towards higher correct recall， using a cost matrix。



![](img/42b427c9b6ef0170c81130c12bdada51_45.png)

A cost matrix trains models biased against certain errors by changing their misclassification costs。

In other words， it tells a model how much it should penalize each mistake during training。

The diagonal values in a cost matrix are always zero。These classifications are correct。

 There's no need to penalize them。By default， the Classification learner app assigns the same penalty for all misclassifications。

But you can emphasize the importance of avoiding certain mistakes by increasing their costs。

The model you train will be five times more biased against false negatives than false positives。

See how the costs of your new model are now set to custom。



![](img/42b427c9b6ef0170c81130c12bdada51_47.png)

You're ready to train。

![](img/42b427c9b6ef0170c81130c12bdada51_49.png)

As might be expected， the resulting model has slightly lower accuracy。



![](img/42b427c9b6ef0170c81130c12bdada51_51.png)

But it also has a much higher crack recall。Not bad。Check the ROC curve。



![](img/42b427c9b6ef0170c81130c12bdada51_53.png)

Remember to plot the crack class。

![](img/42b427c9b6ef0170c81130c12bdada51_55.png)

The new classifier meets the specifications of having at least 99% recall with a fall up below 10%。

Congratulations， you've successfully tailored a model to meet your needs。😊。



![](img/42b427c9b6ef0170c81130c12bdada51_57.png)

The concepts discussed in this video also apply to models with multiple classes。Such as this model。

 trained to distinguish between four different traffic signs。



![](img/42b427c9b6ef0170c81130c12bdada51_59.png)

By looking at the confusion matrix， you can characterize differences between every class。



![](img/42b427c9b6ef0170c81130c12bdada51_61.png)

![](img/42b427c9b6ef0170c81130c12bdada51_62.png)

For example， road close signs were most often mistaken for yield signs。Not a good mistake to make。



![](img/42b427c9b6ef0170c81130c12bdada51_64.png)

In the multi class case， the false negative rate is the sum of the false negative rates of the individual signs。



![](img/42b427c9b6ef0170c81130c12bdada51_66.png)

As with the two class case。The recall and the fallout are reflected with individual ROC curves for each class。



![](img/42b427c9b6ef0170c81130c12bdada51_68.png)

In conclusion， the metrics you use to evaluate your classification model depend on the questions you're trying to answer。

Accuracy is a great metric when every error is treated the same。

 but if your application emphasizes a specific class， utilize recall。

 fall out and cost matrices to train and evaluate the model you need。😊。



![](img/42b427c9b6ef0170c81130c12bdada51_70.png)

![](img/42b427c9b6ef0170c81130c12bdada51_71.png)