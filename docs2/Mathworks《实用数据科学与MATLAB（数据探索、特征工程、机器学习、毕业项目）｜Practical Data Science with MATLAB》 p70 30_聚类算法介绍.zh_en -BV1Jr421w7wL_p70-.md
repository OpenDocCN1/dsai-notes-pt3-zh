# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p70 30_聚类算法介绍.zh_en [BV1Jr421w7wL_p70]

🎼，Cluster methods are among the most common ways data scientists look for hidden patterns or groupings in a data set。

 The clustering algorithms often use an iterative process to assign each data point to the group it's most similar to。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_1.png)

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_2.png)

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_3.png)

Let's walk through a simple example of how this is done with the K means algorithm to better understand the steps taken。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_5.png)

First， select the number of groups you want to identify here。 it looks like there are two。

This number is often denoted as K， which is what the K stands for in K means in K meoids。

The algorithm will generally select K random data points to get things started。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_7.png)

Each point serves as a group center known as a centroid。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_9.png)

The remaining data points are assigned to the group they are most similar to for K means that means the one they're closest to。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_11.png)

Next， the centroid locations are updated here。 The new positions are the mean X and Y values of all data points in each group。

 Once the centroids have moved， the data points are all reassigned to the group whose centroid they are now closest to。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_13.png)

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_14.png)

These steps repeat until the sum of all the distances between points in a group and their centroid reaches a minimum。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_16.png)

The end result is a new feature identifying which group each data point belongs to。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_18.png)

This example showed how the data would be clustered with K means。 However。

 there are many clustering algorithms to choose from。

 and the results may differ depending on the algorithm used。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_20.png)

Let's take a few minutes to go over some of these algorithms。 You will be introduced to Kines。

 K meoids， spectral clustering and Gaussian mixture models。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_22.png)

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_23.png)

K means is the best known clustering method。 It's a simple。

 efficient approach that's best suited for creating circular clusters。

It's often the first algorithm used to explore data。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_25.png)

Its results can serve as a baseline against which other methods can be compared。As you've just seen。

 data points are grouped based on their distance from centroids。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_27.png)

Because the starting points are selected at random。

 include the replicates option to use multiple starting points to perform the clustering。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_29.png)

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_30.png)

The result with the lowest total distance is returned。

Distance is calculated using the squared Euclidean distance by default。 However。

 several other common measures are available。

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_32.png)

Which one you use depends on your data and clustering algorithm。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_34.png)

Check the documentation to see the options available。

 You can change the distance measure used by including the distance option in the function call。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_36.png)

Depending on how your debt is distributed， the median may be a better measure of censure than mean。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_38.png)

When this is the case， use K meoids instead。

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_40.png)

The options for k meoids are similar to K means， because the median is used。

 It's used to reduce the influence of outliers on the clustering or in situations when the mean is not appropriate for the data。

One feature of K meoids is that the central point called the Meoid is always an existing data point in the group。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_42.png)

The previous algorithms work well when the groups are arranged next to each other。

 meaning a single line can be used to separate two groups from each other。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_44.png)

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_45.png)

But what if your data looked like this？

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_47.png)

You can clearly see three groups。 but because the groups wrap around each other。

 K means and K meowoids won't work。

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_49.png)

Spectral clustering algorithms are better suited for such distributions。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_51.png)

They look at the distance between each point and its neighbors and assign groups based on similarity。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_53.png)

When you know the number of groups to find， use the spectral cluster function。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_55.png)

When you don't， use DB scan。Both use Euclidean distance by default。

 but you can change that using the distance option。

You can see all the available options in the documentation。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_57.png)

In this example， DB scan is able to find the same clusters without specifying how many there were。

This is especially useful with high dimensional data sets for which it's difficult to visually estimate the number of clusters。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_59.png)

The inputs to D B scan are the data， a radius called epsilon， and a minimum number of points。

The algorithm labels all points as either core， border， or noise。

Core points have at least the minimum number of points within epsilon of themselves。

Border points do not have the minimum number of points within epsilon of themselves。

 but are within epsilon of a core point。

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_61.png)

All other points are labeled as noise。A cluster consists of all core and border points that are within epsilon of each other。

A unique feature of D B scan is that the noise points do not get assigned to a cluster。 Therefore。

 this function can also be used to identify outliers。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_63.png)

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_64.png)

Finally， what about distributions that overlap？Which cluster should the points in the overlapping region be assigned to。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_66.png)

Gausian mixture models use probability to determine which cluster to assign each data point to。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_68.png)

You first specify the number of clusters to find。That same number of Gaussian distributions are then fit to the data。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_70.png)

Each point then has the probability。 It came from each distribution computed。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_72.png)

There are several options for making the actual cluster assignments， but in the simplest case。

 each point is assigned to the highest probability distribution。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_74.png)

When viewing the data， the probability curves can be depicted as ellipses around the clusters。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_76.png)

The variance of each feature influences the shape。When variance is the same for all features。

 the result is a circle or sphere。

![](img/e25c5d0d6453e889e91b0f6bd5241f6e_78.png)

When it's different， the result is an ellipse that more tightly encompasses the cluster data。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_80.png)

When using the Gaussian mixture model， first determine the number of clusters to create。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_82.png)

Next， fit a Gaussian mixture model to the data using Fit GMD。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_84.png)

Cluster assignments are then made by passing the fit results along with the data into the cluster function。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_86.png)

The output is a vector of cluster assignments for every point。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_88.png)

To summarize， clustering algorithms are able to identify hidden patterns or groupings in your data。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_90.png)

The best algorithm to use will depend on your data。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_92.png)

Many of the clustering algorithms you will need are built into MATLb。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_94.png)

The documentation provides details and examples to help you get started。



![](img/e25c5d0d6453e889e91b0f6bd5241f6e_96.png)