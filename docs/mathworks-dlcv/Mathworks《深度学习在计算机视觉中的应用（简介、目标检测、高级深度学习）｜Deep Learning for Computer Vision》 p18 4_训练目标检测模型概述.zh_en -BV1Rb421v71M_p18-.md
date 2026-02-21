# Mathworks《深度学习在计算机视觉中的应用（简介、目标检测、高级深度学习）｜Deep Learning for Computer Vision》 p18 4_训练目标检测模型概述.zh_en -BV1Rb421v71M_p18-

🎼。

![](img/8665ac65a2602e9a666c30042d9aeea6_1.png)

At a high level， training object detection models can be broken down into a few stages。

Data processing。Network set up in training and evaluation。



![](img/8665ac65a2602e9a666c30042d9aeea6_3.png)

Steps like labeling。Separating test data。Preprocessing the trainings at。



![](img/8665ac65a2602e9a666c30042d9aeea6_5.png)

And data analysis are done up front。Then you choose or build a network architecture to train and do the training。



![](img/8665ac65a2602e9a666c30042d9aeea6_7.png)

Finally， you apply any pre processing that was done to the training data to your test data。



![](img/8665ac65a2602e9a666c30042d9aeea6_9.png)

And use it to evaluate the model。In this course， we focus on transfer learning。Remember。

 transfer learning starts with a pre traineded model。

 typically developed with a large general purpose data set。



![](img/8665ac65a2602e9a666c30042d9aeea6_11.png)

![](img/8665ac65a2602e9a666c30042d9aeea6_12.png)

This model is then retrained， updating the weights to tailor the model to your new data。



![](img/8665ac65a2602e9a666c30042d9aeea6_14.png)

Using previously learned weights and proven network architecture to extract useful features often leads to faster training and better performance。



![](img/8665ac65a2602e9a666c30042d9aeea6_16.png)

![](img/8665ac65a2602e9a666c30042d9aeea6_17.png)

With transfer learning， you keep the feature extraction backbone of the pretrain network。



![](img/8665ac65a2602e9a666c30042d9aeea6_19.png)

And add new components specific to your application。



![](img/8665ac65a2602e9a666c30042d9aeea6_21.png)

For object detection， the data you either import or label consists of images。



![](img/8665ac65a2602e9a666c30042d9aeea6_23.png)

As well as object annotations， or ground truth。For each image。

 there may be multiple objects of interest。Each of which has a class label。



![](img/8665ac65a2602e9a666c30042d9aeea6_25.png)

And a bounding box coordinates。Therefore， when you split your data， for example。

 to create a test set， you have to ensure you keep the correct ground truth labeling associated with the correct images。

You'll also need to be aware of this during any preprocess you apply。



![](img/8665ac65a2602e9a666c30042d9aeea6_27.png)

For example， if you resize the images， you need to adjust the associated bounding box coordinates appropriately。



![](img/8665ac65a2602e9a666c30042d9aeea6_29.png)

When analyzing a classification data set， you're primarily concerned with the class labeled distribution。



![](img/8665ac65a2602e9a666c30042d9aeea6_31.png)

For detection， you need to consider not only class label distribution。

 but also class occurrences per image。

![](img/8665ac65a2602e9a666c30042d9aeea6_33.png)

You'll also need to examine the distribution of object sizes and aspect ratios。

As you will see later in this course， all of this information together helps you choose a network architecture and when necessary anchor boxes。



![](img/8665ac65a2602e9a666c30042d9aeea6_35.png)

![](img/8665ac65a2602e9a666c30042d9aeea6_36.png)

For detection， you need to add a new head or multiple detection head attachments to the backbone via a neck。

Remember， you can determine where and how many heads to add based on the variety of object sizes you need to detect。

This can require some trial and error。

![](img/8665ac65a2602e9a666c30042d9aeea6_38.png)

If the detection of frame employs anchor boxes。You need to estimate an optimal set of them based on the ground truth data。

What you need to do is find clusters of size and aspect ratio in your ground tooth data。



![](img/8665ac65a2602e9a666c30042d9aeea6_40.png)

To do this， you'll use a clustering algorithm to determine where you have the best average intersection over union between anchors and ground truth。

The exact details of how an object detection model is optimized during training are beyond the scope of this course。

At a high level， a combined loss function that accounts for classification。

 as well as localization errors is used。Then the same sort of algorithms， for example。

 adaptive moment estimation or atom are used to minimize the loss function。Therefore。

 you can use similar rationale when choosing training parameters， such as initial learning rate。

Miinni batch size and regularization， as you do with classification。



![](img/8665ac65a2602e9a666c30042d9aeea6_42.png)

Evaluation for optic detection models is more complicated than for classification models。



![](img/8665ac65a2602e9a666c30042d9aeea6_44.png)

Since each image may contain multiple objects， each of which needs to be correctly classified and localized。

There are multiple potential errors per image with object detection。

These can include things like failing to detect objects。Detecting false objects。

Misclassifying objects。Or failing to adequately localize objects。



![](img/8665ac65a2602e9a666c30042d9aeea6_46.png)

You'll learn how to use metrics like precision， recall。

 and mean average precision to evaluate and compare different models。This may seem like a lot。

 but it will help to remember this workflow。In the rest of this course。

 you'll get to apply all of the concepts and processes we showed in this video。



![](img/8665ac65a2602e9a666c30042d9aeea6_48.png)

Luckily， as you'll see， a lot of the heavy lifting will be done for you by functions in Matlab。



![](img/8665ac65a2602e9a666c30042d9aeea6_50.png)

。