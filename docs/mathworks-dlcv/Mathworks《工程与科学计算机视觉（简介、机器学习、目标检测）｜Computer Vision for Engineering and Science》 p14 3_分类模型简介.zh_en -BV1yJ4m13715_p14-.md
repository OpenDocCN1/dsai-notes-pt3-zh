# Mathworks《工程与科学计算机视觉（简介、机器学习、目标检测）｜Computer Vision for Engineering and Science》 p14 3_分类模型简介.zh_en -BV1yJ4m13715_p14-

🎼，Previously， you learned that classification models predict the discrete value or values of a response using one or more predictors。

You can think of this as categorizing some unknown items into a discreteet set of classes。



![](img/ea1d5484f2981625a85595bf266bb696_1.png)

Classification is widely applicable。 It is used for email filtering。

 speech and handwriting recognition， medical diagnosis， and much more。



![](img/ea1d5484f2981625a85595bf266bb696_3.png)

So how does classification work。

![](img/ea1d5484f2981625a85595bf266bb696_5.png)

In this video， you'll learn the basics of two popular image classification models。



![](img/ea1d5484f2981625a85595bf266bb696_7.png)

Let's begin with the K nearest neighborighs model， also known as K and N。KN N。

 like all classification models， can work with any number of predictor features and response classes。



![](img/ea1d5484f2981625a85595bf266bb696_9.png)

But for the following examples， we'll just have two of each。

This classification model assumes that similar things exist in close proximity or， in other words。

 are near to each other。

![](img/ea1d5484f2981625a85595bf266bb696_11.png)

K and N predicts a response by looking at a given number， K of neighboring observations。

To better understand how K and N works， consider an example in which you've set K equal to 3。

For a new data point， the classification will take into account the point's three nearest neighbors。

Here， notice two of the data points are labeled as class 2， and one is labeled as class 1。

Since the majority of the neighbors belong to class 2， the new data point is classified as class 2。

This is also known as a majority voting mechanism。

![](img/ea1d5484f2981625a85595bf266bb696_13.png)

A K& N model is different from most other classification models。

 and that making a new prediction requires referencing it to all existing data。

 rather than running it through a mathematical equation。Therefore。

 KNN models can be computationally expensive for large data sets。



![](img/ea1d5484f2981625a85595bf266bb696_15.png)

Also， you need to be mindful of the right value for K。

 A value of one might lead to predictions that are less robust to noise or outliers。



![](img/ea1d5484f2981625a85595bf266bb696_17.png)

Larger values of K will produce more stable predictions due to majority voting。But eventually。

 a very large value of K will make less accurate predictions as it becomes difficult to capture complex behavior。

You'll need to adjust K to find the most appropriate value for a particular data set。



![](img/ea1d5484f2981625a85595bf266bb696_19.png)

Depending on the value of K， it is common to use the terms fine。

 medium and coarse when describing can and classifications。



![](img/ea1d5484f2981625a85595bf266bb696_21.png)

![](img/ea1d5484f2981625a85595bf266bb696_22.png)

In general， the K& N classification model is among the easiest to understand and interpret。



![](img/ea1d5484f2981625a85595bf266bb696_24.png)

K N N's main disadvantage is that it becomes significantly slower as the volume of data increases。

This can make it an impractical choice in environments where predictions must be made rapidly or where there are tight memory constraints。

 since all the data must be available when making a prediction。



![](img/ea1d5484f2981625a85595bf266bb696_26.png)

The next type of model covered in this video is called support vector Mach， or S VM。



![](img/ea1d5484f2981625a85595bf266bb696_28.png)

SVM models are also a popular choice for classification because of their flexibility。



![](img/ea1d5484f2981625a85595bf266bb696_30.png)

In the binary classification problem， suppose you want to separate the orange squares representing class 1 from the blue circles representing class 2。



![](img/ea1d5484f2981625a85595bf266bb696_32.png)

Any line shown on this plot is a viable option。They would all perfectly separate the orange squares from the blue circles。

But is there an optimal line or decision boundary。In order to best capture the behavior of the data。

The goal is to find the line that will most accurately classify new observations into one of the two classes。

You would probably want a line that is evenly spaced between these two classes and provides a buffer for each class。

That's exactly what SVM does。The algorithm tries to find a line that's right in the middle of your two classes。

 maximizing the distance between the two， called the margin。

To find the line that maximizes the margin， the S VM algorithm first finds the points closest to the line from both classes。

 These points are called support vectors。Thus， the SBM algorithm tries to find a decision boundary in such a way that the separation between the two classes is as wide as possible。

In this two dimensional case， that decision boundary corresponds to a line。

 but this boundary is generally known as a hyperplane， which is applicable in higher dimensions。

In short， a support vector machine is a classifier that finds an optimal hyperplane that maximizes the margin between two classes。

In real examples， it's usually impossible to find a hyperplane that perfectly separates the two classes。

A point inside the margin， but correctly classified， is called margin error。

A point on the wrong side of the separating boundary is a classification error。

The total error is the sum of the margin error， and the classification error。



![](img/ea1d5484f2981625a85595bf266bb696_34.png)

![](img/ea1d5484f2981625a85595bf266bb696_35.png)

What happens when the data cannot be separated by a straight line or hyperplane， as shown here。



![](img/ea1d5484f2981625a85595bf266bb696_37.png)

In these situations， you can use a kernel method which projects the data into an extra dimension。



![](img/ea1d5484f2981625a85595bf266bb696_39.png)

Instead of a decision line， there is now a decision surface that separates the points。

This concept can be generalized to higher dimensions。With the kernel method。

 you map data into a higher dimensional space where the data is linearly separable。



![](img/ea1d5484f2981625a85595bf266bb696_41.png)

The mathematical function used for the transformation is known as the kernel function。

 and there are different types of kernel functions。



![](img/ea1d5484f2981625a85595bf266bb696_43.png)

Linear is the most common， but other options include polynomial， radial basis function。

 and particularly Gaussian。Each of these functions has its own characteristics and its own expression。



![](img/ea1d5484f2981625a85595bf266bb696_45.png)

The kernel method is a real strength of SVM， as it enables you to handle nonlinear data efficiently。

However， the kernel function must be properly chosen to avoid increasing the training time drastically。



![](img/ea1d5484f2981625a85595bf266bb696_47.png)

There are many more classification models available for you to choose from。



![](img/ea1d5484f2981625a85595bf266bb696_49.png)

Each model has its own advantages and disadvantages in terms of accuracy。

 speed and memory requirements。

![](img/ea1d5484f2981625a85595bf266bb696_51.png)

The best way to know how they perform on a particular data set is to try them out。



![](img/ea1d5484f2981625a85595bf266bb696_53.png)

Next， you'll learn how to quickly train models in Matlab and compare their results。



![](img/ea1d5484f2981625a85595bf266bb696_55.png)

。