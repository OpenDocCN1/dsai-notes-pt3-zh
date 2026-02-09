# 约翰霍普金斯大学数据科学课程4：《探索性数据分析》｜exploratory-data-analysis｜ - P27：26_k均值聚类部分2.zh_en - GPT中英字幕课程资源 - BV1U94y1s7th

So in R， the K means function is the function that we use to implement the K means algorithm here and I can demonstrate it here with using a simple data frame I got with just two dimensions and I called k meanss on the data frame and I tell it there are three centers so three centroids。



![](img/701266acad0e513b3f4d01a1970dfb61_1.png)

![](img/701266acad0e513b3f4d01a1970dfb61_2.png)

![](img/701266acad0e513b3f4d01a1970dfb61_3.png)

And what Ka meanss returns is is a list with a number of different elements in it。

 And so for example， probably the most important element is the cluster element。

 And you can see here when I print out the cluster element。

 you can see that it's a vector of numbers from one to3。

 So and what this shows is for each data point in in the data frame that I passed it it tells me which cluster it's in。

 So see the first four points are in cluster 3， the next four are in cluster1 and the next four are in cluster 2。

 you can see another element。 if you look in the print out of the names another element of the object return from K meanss is called centers and this tells you the location of the centroids in the space。



![](img/701266acad0e513b3f4d01a1970dfb61_5.png)

![](img/701266acad0e513b3f4d01a1970dfb61_6.png)

![](img/701266acad0e513b3f4d01a1970dfb61_7.png)

![](img/701266acad0e513b3f4d01a1970dfb61_8.png)

![](img/701266acad0e513b3f4d01a1970dfb61_9.png)

![](img/701266acad0e513b3f4d01a1970dfb61_10.png)

![](img/701266acad0e513b3f4d01a1970dfb61_11.png)

![](img/701266acad0e513b3f4d01a1970dfb61_12.png)

![](img/701266acad0e513b3f4d01a1970dfb61_13.png)

So if you want to plot the kind of the results of k means。

 the first thing you can do you run the k means algorithm on your data and here I'm just going plot data so the first thing I do is I plot the data so I plot Xy。

 and then I color the data points according to the cluster that they happen to be in so you can see I pass the call argument to be equal to the cluster number and then I use the points function to kind of add the centers。

 the cluster centroids to the plot and and I plot them using the plus symbol so here I plotted the data and the k means clustering results。



![](img/701266acad0e513b3f4d01a1970dfb61_15.png)

![](img/701266acad0e513b3f4d01a1970dfb61_16.png)

![](img/701266acad0e513b3f4d01a1970dfb61_17.png)

![](img/701266acad0e513b3f4d01a1970dfb61_18.png)

![](img/701266acad0e513b3f4d01a1970dfb61_19.png)

![](img/701266acad0e513b3f4d01a1970dfb61_20.png)

SoFinally， another way that you can visualize clustering information for an algorithm like k means is by using the heat map function or looking at heat maps。

 I should say。 So here I I've using the same data。 I take a different random sample of the data set。

 I sample a replacement。 and I just run k means again again with three centers。

 and I stored an object called Ka means object2。 and now I'm going to make an image plot of the data。

 So the first plot on the left here is just an image of the original data。

 and then on the right hand side， I've reordered the。



![](img/701266acad0e513b3f4d01a1970dfb61_22.png)

![](img/701266acad0e513b3f4d01a1970dfb61_23.png)

The columns of the data I'm should I say the rows of the data frame so that the clusters are kind of put together so here you can see that if you go up and down up and down this matrix you'll see the data points are clustered together so that they're next to each other and you can use this to look at high dimensionsal data in high dimensionsal image type data or matrix type data where you can reorganize the rows in the columns and kind of look at clusters that are cluster together or farther apart so look at your kind of matrix data in an organized way so you can so you can look for patterns we'll talk a little bit about this more when we talk about hierarchical clusterings but you can use heat map type of visualizations with other types of clustering algorithms like K means two just to summarize K means is handy algorithm for organizing and looking for patterns and high dimensional data a couple things it requires that you know the number of clusters。



![](img/701266acad0e513b3f4d01a1970dfb61_25.png)

![](img/701266acad0e513b3f4d01a1970dfb61_26.png)

![](img/701266acad0e513b3f4d01a1970dfb61_27.png)

![](img/701266acad0e513b3f4d01a1970dfb61_28.png)

![](img/701266acad0e513b3f4d01a1970dfb61_29.png)

![](img/701266acad0e513b3f4d01a1970dfb61_30.png)

![](img/701266acad0e513b3f4d01a1970dfb61_31.png)

![](img/701266acad0e513b3f4d01a1970dfb61_32.png)

![](img/701266acad0e513b3f4d01a1970dfb61_33.png)

![](img/701266acad0e513b3f4d01a1970dfb61_34.png)

![](img/701266acad0e513b3f4d01a1970dfb61_35.png)

![](img/701266acad0e513b3f4d01a1970dfb61_36.png)

So you have to specify at least roughly speaking how many clusters there are you can kind of play with that a little bit to figure out kind what pattern probably looks the best。

 but there's no easy rule there and then so you have to kind of pick those clusters out by eye or through some other mechanism there are a few algorithms for kind determining the number of clusters using cross validation information theory。

 other types of metrics and so here's a link to determining the number of clusters and and the K means algorithm is not deterministic so depending on how it's implemented there can be sometimes those starting points are chosen at random so it's often useful to run the K means algorithm a couple times just to make sure you're not getting a very unstable finishing point so for example if you run at three different times and every time you get a totally different pattern then that means that the algorithm may not be have a very stable kind of view of the data and so K means。



![](img/701266acad0e513b3f4d01a1970dfb61_38.png)

![](img/701266acad0e513b3f4d01a1970dfb61_39.png)

![](img/701266acad0e513b3f4d01a1970dfb61_40.png)

![](img/701266acad0e513b3f4d01a1970dfb61_41.png)

![](img/701266acad0e513b3f4d01a1970dfb61_42.png)

![](img/701266acad0e513b3f4d01a1970dfb61_43.png)

![](img/701266acad0e513b3f4d01a1970dfb61_44.png)

![](img/701266acad0e513b3f4d01a1970dfb61_45.png)

![](img/701266acad0e513b3f4d01a1970dfb61_46.png)

can be problematic in that way with certain types of data sets and here I've got a couple links kind of to videos and references on that provide a lot more information about canings。



![](img/701266acad0e513b3f4d01a1970dfb61_48.png)

![](img/701266acad0e513b3f4d01a1970dfb61_49.png)

![](img/701266acad0e513b3f4d01a1970dfb61_50.png)