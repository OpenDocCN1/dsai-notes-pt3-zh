# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p19 8_评估分类模型.zh_en -BV1yJ4m13715_p19-

🎼。

![](img/626e9f3444a5d8e00202f8362194dde7_1.png)

Previously， you've seen confusion matrices as a method for evaluating classification models。



![](img/626e9f3444a5d8e00202f8362194dde7_3.png)

In this video， you'll learn how to construct a confusion matrix from which you'll derive four key evaluation metrics。

 recall。Fallout， precision， and accuracy。Next， you'll see why it's necessary to consider trade offs among these metrics when evaluating classification model performance。

Finally， you'll work with receiver operating characteristic curves to systematically evaluate the trade off between recall and fallout。

😊。

![](img/626e9f3444a5d8e00202f8362194dde7_5.png)

Let's get started with a simple example of binary classification。Recall。

 a binary classification model uses the decision boundary to separate two classes of data。

 In this case， positives and negatives。😊，Although in general。

 the decision boundary does not have to be a straight line。

 this video focuses on this simple case to illustrate the concepts。

Tta points on one side of the decision boundary are predicted to be positive。

And data points on the other side are predicted to be negative。



![](img/626e9f3444a5d8e00202f8362194dde7_7.png)

There are 12 data points in the positive class， and this model correctly identifies nine of them。

These are the true positives。 You can see this abbreviated as T P。

The remaining three positives that were classified as negatives are the false negatives。Similarly。

 there are 12 data points in the negative class。The 10 of them that were correctly classified。

 are the true negatives。Finally， the two negatives incorrectly classified as positive are the false positives。

A common way to evaluate these four quantities together is using a confusion matrix。

The true values are grouped by row。And the predicted values are grouped by column。Each quadrant。

 the confusion matrix， represents the corresponding number of true positives， true negatives。

 false positives and false negatives。

![](img/626e9f3444a5d8e00202f8362194dde7_9.png)

![](img/626e9f3444a5d8e00202f8362194dde7_10.png)

These four quantities form the basis of all the classification evaluation methods in this video。

The total actual positives is equal to the sum of the true positives and false negatives。😊，Similarly。

 the total actual negatives equals false positives plus true negatives。



![](img/626e9f3444a5d8e00202f8362194dde7_12.png)

![](img/626e9f3444a5d8e00202f8362194dde7_13.png)

Total predicted positives equals true positives， plus false positives。



![](img/626e9f3444a5d8e00202f8362194dde7_15.png)

And total predicted negatives equals false negatives， plus true negatives。



![](img/626e9f3444a5d8e00202f8362194dde7_17.png)

The four key metrics mentioned earlier in this video， recall， fallout， precision and accuracy。

Can all be calculated from here。

![](img/626e9f3444a5d8e00202f8362194dde7_19.png)

Let's take a closer look at each of them individually before considering the trade offs among them。



![](img/626e9f3444a5d8e00202f8362194dde7_21.png)

Recall tells you how much of a given class is correctly identified by a model。



![](img/626e9f3444a5d8e00202f8362194dde7_23.png)

Here， that is the ratio of the data correctly classified as positive。



![](img/626e9f3444a5d8e00202f8362194dde7_25.png)

To the total positive data。

![](img/626e9f3444a5d8e00202f8362194dde7_27.png)

Fallout tells you how many false alarms the model generates for a given class。

For binary classification， this is the ratio of data incorrectly classified as positive to the total negative data。



![](img/626e9f3444a5d8e00202f8362194dde7_29.png)

![](img/626e9f3444a5d8e00202f8362194dde7_30.png)

Precision represents the fraction of classifications to a given class that were correct。

Which is the ratio of correctly classified， positive data。To the total data classified as positive。

Accuracy is the overall rate a model correctly classifies data。



![](img/626e9f3444a5d8e00202f8362194dde7_32.png)

It is the fraction of all correct predictions。

![](img/626e9f3444a5d8e00202f8362194dde7_34.png)

To the total of all predictions。

![](img/626e9f3444a5d8e00202f8362194dde7_36.png)

In other words， how often the model got its predictions right overall。



![](img/626e9f3444a5d8e00202f8362194dde7_38.png)

If the classification is perfect， the accuracy， precision， and recall will be one。

And the fallout will be 0。Simple， right？Unfortunately。

 most of the time you will not be able to achieve this kind of ideal。Instead。

 you'll have to consider trade offs in the context of a model's optimal capabilities for the intended application。



![](img/626e9f3444a5d8e00202f8362194dde7_40.png)

To see this， let's return to the example。The model has an accuracy of 79%。A recall of 75%。

A precision of 82%。And a fallout of 17%。Would this be acceptable performance for a real life situation。

In a situation like cancer detection， a false positive may cause a temporary anxiety for a patient。

 but a false negative。 in other words， a missed positive could have potentially deadly results。Here。

 you may want to maximize recall to ensure you don't miss any positives。You have to be careful。

 though。By changing the decision boundary， you can make recall 100%。However。

 accuracy will decrease to 71% and worse yet， the new false positives will drop precision down to 63% and increase the fallout to 58%。



![](img/626e9f3444a5d8e00202f8362194dde7_42.png)

As another example， imagine your training an image classifier to identify overripe fruit。



![](img/626e9f3444a5d8e00202f8362194dde7_44.png)

Your initial goal might be to reduce the number of fruit incorrectly identified as over ripe。



![](img/626e9f3444a5d8e00202f8362194dde7_46.png)

In this case， reducing fallout will lower the number of false positives generated by your model。

Again， though， be careful。If you change the decision boundary to make fallout 0%。

 the accuracy will be 71%。However， this will increase false negatives so that your recall drops down to 42%。

In other words， your model would let 58% of bad fruit through。In real life scenarios。

 there will rarely be a decision boundary that perfectly separates the positives and negatives。

 So you need to consider the inherent trade offs to build an acceptable model。



![](img/626e9f3444a5d8e00202f8362194dde7_48.png)

Based on what you've seen so far， it may be tempting to assume that while the other metrics may give contradictory priorities to the model。

 shooting for high accuracy will find a good balance among them all。



![](img/626e9f3444a5d8e00202f8362194dde7_50.png)

![](img/626e9f3444a5d8e00202f8362194dde7_51.png)

![](img/626e9f3444a5d8e00202f8362194dde7_52.png)

This works sometimes， but yet again， you have to be careful。



![](img/626e9f3444a5d8e00202f8362194dde7_54.png)

If your data has a class im balance， for example， a large majority of the data is negatives。



![](img/626e9f3444a5d8e00202f8362194dde7_56.png)

Then a model that predicts nearly， if not every data point to be negative。

 will have high accuracy and even high precision and low fallout。 However， the recall will suffer。



![](img/626e9f3444a5d8e00202f8362194dde7_58.png)

What about when you have a large majority of positives？In this case， a model that predicts almost。

 if not all data is positive， will again have high accuracy。What happens to the other metrics。



![](img/626e9f3444a5d8e00202f8362194dde7_60.png)

At this point， you may correctly suspect it is a good idea to always look at multiple metrics when evaluating a model。

 For example， both recall and fall out。An effective way to evaluate a model using both recall and fallout is to construct the ROC curve and determine the area under the curve or AU。



![](img/626e9f3444a5d8e00202f8362194dde7_62.png)

![](img/626e9f3444a5d8e00202f8362194dde7_63.png)

R OC stands for receiver Operating Charistic， a term that comes from radar engineering。

 where it was first developed and used。The ROC curve represents recall and fallout for a model as functions of a threshold parameter that varies from 0 to1。

 moving the decision boundary through the range of data。



![](img/626e9f3444a5d8e00202f8362194dde7_65.png)

The area under the curve also ranges from 0 to1， with better models being closer to one。



![](img/626e9f3444a5d8e00202f8362194dde7_67.png)

Now， let's see what's behind all of this。First， let's talk about the threshold parameter。

Various binary classification models will sign a confidence score or probability of a data point being positive。

 ranging from 0 to1。Which can be plotted as contours。As you have seen。

 the decision threshold can vary throughout this range。

 affecting both recall and follow up metrics as it changes。



![](img/626e9f3444a5d8e00202f8362194dde7_69.png)

Vary the threshold from 0 to 1 and calculate the recall and fallout。



![](img/626e9f3444a5d8e00202f8362194dde7_71.png)

The calculated recall and fallout values are used to construct the ROC curve。



![](img/626e9f3444a5d8e00202f8362194dde7_73.png)

Notice that ROC curves always start from the upper right corner。This is because for a threshold of0。

 all data will be classified as positive， so both recall and fallout will be one。

As the threshold value progresses through the data， the recall and fallout will change accordingly。



![](img/626e9f3444a5d8e00202f8362194dde7_75.png)

Until the threshold reaches one， where all data will be classified as negative。

 making both recall and fall out0。

![](img/626e9f3444a5d8e00202f8362194dde7_77.png)

In practice， the ROC curve is often constructed with more granularity。



![](img/626e9f3444a5d8e00202f8362194dde7_79.png)

In general， various models will have different ROC curves and therefore different areas under them。

An AU value close to1 indicates that the model can achieve high recall while still maintaining low fallout。

As the area under the curve decreases， the amount of fallout necessary to achieve high recall gets worse。

At an area of 0。5， the model is essentially making random predictions。Below this。

 the model is actually better at predicting incorrectly than correctly。

The RFC curve is useful for helping you determine where to set a decision boundary by visualizing how recall and fallout are related。

Let's summarize in this video， you learned how to construct a confusion matrix and derive key metrics for evaluating classification models。

You saw how evaluating a classification model requires considering trade offs。

And how to work with receiver operated characteristic curves to systematically evaluate the trade off between two metrics。

 recall and fall out。

![](img/626e9f3444a5d8e00202f8362194dde7_81.png)

。