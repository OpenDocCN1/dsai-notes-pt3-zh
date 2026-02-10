# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P19：18_支持向量机.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

![](img/ebfc3c62fe29028acab4226039fc56bd_0.png)

Hello and welcome In this video， we will learn a machine learning method called support Ve Mach or SBM。

 which is used for classification。 So let's get started。😊。



![](img/ebfc3c62fe29028acab4226039fc56bd_2.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_3.png)

Imagine that you've obtained a dataset set containing characteristics of thousands of human cell samples extracted from patients who were believed to be at risk of developing cancer。

Analysis of the original data showed that many of the characteristics differed significantly between benign and malignant samples。

You can use the values of these cell characteristics and samples from other patients to give an early indication of whether a new sample might be benign or malignant。

You can use support vector Mach or SVM as a classifier to train your model to understand patterns within the data that might show benign or malignant cells。

Once the model has been trained， it can be used to predict your new or unknown cell with rather high accuracy。

 Now， let me give you a formal definition of S VM。A support vector machine is a supervised algorithm that can classify cases by finding a separator。



![](img/ebfc3c62fe29028acab4226039fc56bd_5.png)

SVM works by first mapping data to a high dimensional feature space so that data points can be categorized。

 even when the data are not otherwise linearly separable， Then a separator is estimated for the data。

The data should be transformed in such a way that a separator could be drawn as a hyperplane。

 For example， consider the following figure， which shows the distribution of a small set of cells only based on their unit size and clump thickness。

As you can see， the data points fall into two different categories。

 It represents a linearly nonseparable data set。The two categories can be separated with a curve。

 but not a line。 That is， it represents a linearly nonseparable data set。

 which is the case for most real world data sets。We can transfer this data to a higher dimensional space。

 for example， mapping it to a three dimensional space。After the transformation。

 the boundary between the two categories can be defined by a hyperplane。

As we are now in three dimensional space， the separator is shown as a plane。

This plane can be used to classify new or unknown cases。Therefore。

 the SVM algorithm outputs an optimal hyperplane that categorizes new examples。Now。

 there are two challenging questions to consider。 First。

 how do we transfer data in such a way that a separator could be drawn as a hyperplane。And two。

 how can we find the best or optimized Hy planee separator after transformation？

Let's first look at transforming data to see how it works。



![](img/ebfc3c62fe29028acab4226039fc56bd_7.png)

For the sake of simplicity， imagine that our data set is one dimensional data；

 this means we have only one feature X。

![](img/ebfc3c62fe29028acab4226039fc56bd_9.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_10.png)

As you can see， it is not linearly separable。 So what can we do here。



![](img/ebfc3c62fe29028acab4226039fc56bd_12.png)

Well， we can transfer it into a two dimensional space。 For example。

 you can increase the dimension of data by mapping x into a new space using a function with outputs x and x squared。



![](img/ebfc3c62fe29028acab4226039fc56bd_14.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_15.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_16.png)

Now the data is linearly separable， right？

![](img/ebfc3c62fe29028acab4226039fc56bd_18.png)

Notice that as we are in a two dimensional space， the hyperplane is a line dividing a plane into two parts where each class lays on either side。



![](img/ebfc3c62fe29028acab4226039fc56bd_20.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_21.png)

Now we can use this line to classify new cases。

![](img/ebfc3c62fe29028acab4226039fc56bd_23.png)

Basically， mapping data into a higher dimensional space is called kerneling。



![](img/ebfc3c62fe29028acab4226039fc56bd_25.png)

The mathematical function used for the transformation is known as the kernel function and can be of different types such as linear。

 polynomial， radial basis function， or RBF， and sigmoid。



![](img/ebfc3c62fe29028acab4226039fc56bd_27.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_28.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_29.png)

Each of these functions has its own characteristics， its pros and cons， and its equation。

 but the good news is that you don't need to know them。

 as most of them are already implemented in libraries of data science programming languages。



![](img/ebfc3c62fe29028acab4226039fc56bd_31.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_32.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_33.png)

Also， as theres no easy way of knowing which function performs best with any given data set。

 we usually choose different functions in turn and compare the results。



![](img/ebfc3c62fe29028acab4226039fc56bd_35.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_36.png)

Now we get to another question， specifically how do we find the right or optimize separator after transformation？



![](img/ebfc3c62fe29028acab4226039fc56bd_38.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_39.png)

Basically， SVMs are based on the idea of finding a hyperplane that best divides a data set into two classes as shown here。



![](img/ebfc3c62fe29028acab4226039fc56bd_41.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_42.png)

As we're in a two dimensional space， you can think of the hyperplane as a line that linearly separates the blue points from the red points。



![](img/ebfc3c62fe29028acab4226039fc56bd_44.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_45.png)

One reasonable choice as the best hyperplane is the one that represents the largest separation or margin between the two classes。



![](img/ebfc3c62fe29028acab4226039fc56bd_47.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_48.png)

So the goal is to choose a hyperplane with as big a margin as possible。



![](img/ebfc3c62fe29028acab4226039fc56bd_50.png)

Examples closest to the Hyplane are support vectors。



![](img/ebfc3c62fe29028acab4226039fc56bd_52.png)

It is intuitive that only support vectors matter for achieving our goal。

 and thus other training examples can be ignored。

![](img/ebfc3c62fe29028acab4226039fc56bd_54.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_55.png)

We try to find the hyperplane in such a way that it has the maximum distance to support vectors。



![](img/ebfc3c62fe29028acab4226039fc56bd_57.png)

Please note that the Hyplane and boundary decision lines have their own equations。



![](img/ebfc3c62fe29028acab4226039fc56bd_59.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_60.png)

So finding the optimized Hyplane can be formalized using an equation which involves quite a bit more math。

 so I'm not going to go through it here in detail。

![](img/ebfc3c62fe29028acab4226039fc56bd_62.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_63.png)

That said， the hyperplane is learned from training data using an optimization procedure that maximizes the margin。



![](img/ebfc3c62fe29028acab4226039fc56bd_65.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_66.png)

And like many other problems， this optimization problem can also be solved by gradient descent。

 which is out of scope of this video。

![](img/ebfc3c62fe29028acab4226039fc56bd_68.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_69.png)

Therefore， the output of the algorithm is the values W and B for the line。



![](img/ebfc3c62fe29028acab4226039fc56bd_71.png)

You can make classifications using this estimated line。



![](img/ebfc3c62fe29028acab4226039fc56bd_73.png)

It is enough to plug in input values into the line equation。

 then you can calculate whether an unknown point is above or below the line。



![](img/ebfc3c62fe29028acab4226039fc56bd_75.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_76.png)

If the equation returns a value greater than0， then the point belongs to the first class。

 which is above the line and vice versa。

![](img/ebfc3c62fe29028acab4226039fc56bd_78.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_79.png)

The two main advantages of support vector machines are that they're accurate in high dimensional spaces。

 and they use a subset of training points in the decision function called support vectors。

 So it's also memory efficient。

![](img/ebfc3c62fe29028acab4226039fc56bd_81.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_82.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_83.png)

The disadvantages of support vector machines include the fact that the algorithm is prone for overfitting。

 If the number of features is much greater than the number of samples。



![](img/ebfc3c62fe29028acab4226039fc56bd_85.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_86.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_87.png)

Also， SVMs do not directly provide probability estimates which are desirable in most classification problems。



![](img/ebfc3c62fe29028acab4226039fc56bd_89.png)

And finally， SVMs are not very efficient computationally if your data set is very big。

 such as when you have more than 1000 rows。

![](img/ebfc3c62fe29028acab4226039fc56bd_91.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_92.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_93.png)

And now， our final question is， in which situation should I use S VM。



![](img/ebfc3c62fe29028acab4226039fc56bd_95.png)

Well， SVM is good for image analysis tasks such as image classification and handwritten digit recognition。



![](img/ebfc3c62fe29028acab4226039fc56bd_97.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_98.png)

Also， SVM is very effective in text mining tasks， particularly due to its effectiveness in dealing with high dimensional data。

 For example， it is used for detecting spam， text category assignment and sentiment analysis。



![](img/ebfc3c62fe29028acab4226039fc56bd_100.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_101.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_102.png)

Another application of SVM is in gene expression data classification。

 again because of its power in high dimensional data classification。



![](img/ebfc3c62fe29028acab4226039fc56bd_104.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_105.png)

SVM can also be used for other types of machine learning problems such as regression。

 outlier detection and clustering。

![](img/ebfc3c62fe29028acab4226039fc56bd_107.png)

![](img/ebfc3c62fe29028acab4226039fc56bd_108.png)

I'll leave it to you to explore more about these particular problems。



![](img/ebfc3c62fe29028acab4226039fc56bd_110.png)

This concludes this video。 Thanks for watching。

![](img/ebfc3c62fe29028acab4226039fc56bd_112.png)