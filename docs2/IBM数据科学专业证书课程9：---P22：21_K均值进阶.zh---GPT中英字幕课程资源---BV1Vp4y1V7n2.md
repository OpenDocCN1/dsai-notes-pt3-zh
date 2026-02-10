# IBM数据科学专业证书课程9：《Python机器学习课程（IBM）》machine-learning-with-python（中英字幕） - P22：21_K均值进阶.zh_en - GPT中英字幕课程资源 - BV1Vp4y1V7n2

![](img/3f6b9a84026927f20f1944e195c3049b_0.png)

Hello and welcome In this video， we'll look at K means accuracy and characteristics。

 Let's get started。😊。

![](img/3f6b9a84026927f20f1944e195c3049b_2.png)

Let's define the algorithm more concretely before we talk about its accuracy。



![](img/3f6b9a84026927f20f1944e195c3049b_4.png)

A K means algorithm works by randomly placing K centroids， one for each cluster。

 The farther apart the clusters are placed， the better。



![](img/3f6b9a84026927f20f1944e195c3049b_6.png)

![](img/3f6b9a84026927f20f1944e195c3049b_7.png)

The next step is to calculate the distance of each data point or object from the centroids。

 Euclidean distance is used to measure the distance from the object to the centroid。 Please note。

 however， that you can also use different types of distance measurements。

 not just Euclidean distance。 Euclidean distance is used because it's the most popular。



![](img/3f6b9a84026927f20f1944e195c3049b_9.png)

![](img/3f6b9a84026927f20f1944e195c3049b_10.png)

![](img/3f6b9a84026927f20f1944e195c3049b_11.png)

![](img/3f6b9a84026927f20f1944e195c3049b_12.png)

![](img/3f6b9a84026927f20f1944e195c3049b_13.png)

Then assign each data point or object to its closest centroid， creating a group。Next。

 once each data point has been classified to a group， recalculate the position of the K centroids。

The new centroroid position is determined by the mean of all points in the group。Finally。

 this continues until the centroids no longer move。Now， the question is。

 how can we evaluate the goodness of the clusters formed by K means， In other words。

 how do we calculate the accuracy of k means clustering？

 One way is to compare the clusters with the ground truth if it's available。 However。

 because K means is an unsupervised algorithm。 We usually don't have ground truth and real world problems to be used。

 But there is still a way to say how bad each cluster is based on the objective of the K means。😊。



![](img/3f6b9a84026927f20f1944e195c3049b_15.png)

![](img/3f6b9a84026927f20f1944e195c3049b_16.png)

![](img/3f6b9a84026927f20f1944e195c3049b_17.png)

![](img/3f6b9a84026927f20f1944e195c3049b_18.png)

![](img/3f6b9a84026927f20f1944e195c3049b_19.png)

![](img/3f6b9a84026927f20f1944e195c3049b_20.png)

This value is the average distance between data points within a cluster。Also。

 average of the distances of data points from their cluster centroids can be used as a metric of error for the clustering algorithm。

Essentially， determining the number of clusters in a data set or K as in the K means algorithm。

 is a frequent problem in data clustering。

![](img/3f6b9a84026927f20f1944e195c3049b_22.png)

![](img/3f6b9a84026927f20f1944e195c3049b_23.png)

The correct choice of K is often ambiguous because it's very dependent on the shape and scale of the distribution of points in a data set。



![](img/3f6b9a84026927f20f1944e195c3049b_25.png)

![](img/3f6b9a84026927f20f1944e195c3049b_26.png)

There are some approaches to address this problem， but one of the techniques that is commonly used is to run the clustering across the different values of K and looking at a metric of accuracy for clustering。



![](img/3f6b9a84026927f20f1944e195c3049b_28.png)

![](img/3f6b9a84026927f20f1944e195c3049b_29.png)

![](img/3f6b9a84026927f20f1944e195c3049b_30.png)

This metric can be mean distance between data points and their cluster centroid。

 which indicate how dense our clusters are， or to what extent we minimize the error of clustering。



![](img/3f6b9a84026927f20f1944e195c3049b_32.png)

![](img/3f6b9a84026927f20f1944e195c3049b_33.png)

Then looking at the change of this metric， we can find the best value for K。



![](img/3f6b9a84026927f20f1944e195c3049b_35.png)

But the problem is that with increasing the number of clusters。

 the distance of centroids to data points will always reduce。



![](img/3f6b9a84026927f20f1944e195c3049b_37.png)

![](img/3f6b9a84026927f20f1944e195c3049b_38.png)

This means increasing K will always decrease the error。



![](img/3f6b9a84026927f20f1944e195c3049b_40.png)

So the value of the metric as a function of k is plotted。

 and the elbow point is determined where the rate of decrease sharply shifts。

 It is the right K for clustering。

![](img/3f6b9a84026927f20f1944e195c3049b_42.png)

![](img/3f6b9a84026927f20f1944e195c3049b_43.png)

![](img/3f6b9a84026927f20f1944e195c3049b_44.png)

This method is called the elbow method。So let's recap K means clustering。



![](img/3f6b9a84026927f20f1944e195c3049b_46.png)

K meanss is a partition based clustering， which is a relatively efficient on medium and large size data sets。

 B produces sphere like clusters because the clusters are shaped around the centroids。 And C。

 its drawback is that we should pre specify。 the number of clusters， and this is not an easy task。

 Thanks for watching。

![](img/3f6b9a84026927f20f1944e195c3049b_48.png)

![](img/3f6b9a84026927f20f1944e195c3049b_49.png)

![](img/3f6b9a84026927f20f1944e195c3049b_50.png)

![](img/3f6b9a84026927f20f1944e195c3049b_51.png)

![](img/3f6b9a84026927f20f1944e195c3049b_52.png)