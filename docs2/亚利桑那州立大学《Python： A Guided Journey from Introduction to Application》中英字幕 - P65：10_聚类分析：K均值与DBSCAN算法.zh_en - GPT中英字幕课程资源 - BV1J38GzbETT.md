# 亚利桑那州立大学《Python： A Guided Journey from Introduction to Application》中英字幕 - P65：10_聚类分析：K均值与DBSCAN算法.zh_en - GPT中英字幕课程资源 - BV1J38GzbETT

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_0.png)

Welcome。In this lecture， we'll be going over cluster analysis。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_2.png)

Today， we're going to go over what is unsupervised learning， what is clustering analysis。

Some algorithms that shows how clustering analysis works。

 So we're going to learn about K means and how does the K means algorithm work。

 We're going to learn about the DB scan algorithm and how does it work。

 and we're going to identify when do we use clustering analysis。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_4.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_5.png)

So what is unsupervised learning？Unsupervised learning is one of the branches of machine learning。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_7.png)

And in this branch of machine learning， models are trained on unlabeled data sets。

 meaning we don't have features that describe our data， it's also known to not have a ground truth。

 we don't have anything that describes our data， essentially we have samples of data and we want to make sense of all these numbers or values in our data set。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_9.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_10.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_11.png)

Now， mind you， there are no labels that describe the data sets。 I cannot reinforce that enough。

 That's what specifies unsupervised learning and distinguishes it from supervised learning。

We typically use unsupervised learning to analyze and cluster unlabeled data sets。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_13.png)

We want to make sure we find patterns and identify groupings of data without being told by the programmer this is how we're able to classify data without the labels。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_15.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_16.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_17.png)

So what is clustering analysis clustering is utilized to find structure or patterns in data。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_19.png)

We want to determine whether the data forms groups and we want to understand what the groupings mean。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_21.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_22.png)

Our goal or objective is to structure the samples into clusters to understand what the samples are based on their groupings。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_24.png)

It may be difficult to identify the clusters and select the algorithm that will work optimally initially。

 but as you find a pattern and you see how the data is being grouped。

 it becomes a little more easier。

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_26.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_27.png)

Some unsupervised machine learning algorithms that will be going over in this lesson include the K meanss machine learning algorithm and the DB scan machine learning algorithm。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_29.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_30.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_31.png)

So before we talk a little bit about how it works， here's a visual depiction of how the K means algorithm works versus DB scan。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_33.png)

Now you could see that in this image right here， we have one big group or one big cluster of samples and they're all green。

 Now if you were to look at it visually， you could see that we could actually specify them as three separate clusters just because there's a certain distance that is that spaces them out so when we apply K means you could see that we have three separate clusters of data that have been classified。

 so we have green samples， blue samples and black samples。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_35.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_36.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_37.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_38.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_39.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_40.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_41.png)

Now D scan or density based clustering works like this， we can work with spherical shaped clusters。

 it's very similar and how it works to K means where we have three clusters here， blue dots。

 pink dots， orange dots， or we can use arbitrary shape clusters where it doesn't have to be spherical here we can see we have clusters within clusters。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_43.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_44.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_45.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_46.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_47.png)

And we have nonpherical shape clusters as well that are used to describe the data。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_49.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_50.png)

So how does decay means algorithm work？The basic assumption we want to make sure we abide by is that samples form round clusters。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_52.png)

The initial center points are spread out by the algorithm。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_54.png)

Now here are the basic steps for the K means algorithm。

 the first step is to randomly choose a number of clusters。

 specified the variable end to be the number of clusters。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_56.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_57.png)

The next step is to randomly choose the number of center points or end center points。

Each sample should be assigned to the nearest center point。

 the center point should be moved until it is at the center of the cluster。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_59.png)

The preceding two steps should be repeated until there is no more movement in the data。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_61.png)

Here we have our line of code that shows how you can create the model。

 so here we're calling the K means function and we're specifying our number of clusters to have a certain value which is represented by cluster count。

 where we're initializing it to be K means。

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_63.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_64.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_65.png)

And then we I'll explain these hyperparameter in our demo moving forward。

 but that's how K means works。

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_67.png)

Now how does DB scan work DB scan stands for density based spatial clustering of applications with noise。

The assumption we want to abide by is that samples within close proximity should be placed together。

Unlike hay means， theres no need to assume the number of clusters and control controls how close samples are required to be。

Now DB scan places samples into three different categories we have core points which are points that are surrounded by a minimum number of points within an epsilon distance。

We have border points， which are points that are in reachable distance from a core point and have less than the specified minimum number of points in the surrounding area。

Then we have outliers， which are points that are not core points and are not within close proximity of any core points。

So again， now that you know the steps between K means versus DB scan。

 this is just to reinforce your memory that K means can be used to categorize our data into spherical structures。

 whereas with DB scan or density based clustering， we don't need to have spherical clusters。

 we can have arbitrary shape clusters as depicted in this image right here。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_69.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_70.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_71.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_72.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_73.png)

So when do we use clustering analysis？Well， when using a data that contains no ground truth or labeled data。

 clustering analysis works best because we are trying to find any pattern or structure within the unlabeled data。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_75.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_76.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_77.png)

Now， when there are no assumptions made about the relationship within the data。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_79.png)

Cluing analysis will work well。Cluing analysis should be used when information regarding patterns or associations in the data are to be discovered and to be understood。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_81.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_82.png)

Let's go ahead and jump to our demo。So here's our demo。

The first step as always is that we want to import our libraries We're going to go ahead and from SK Learn。

 we want to import makeBlobs and K means from the cluster with from cluster within SKLn and makeBlobs from datas within SKLear makeBlobs will be used to create the clusters and K means is our algorithm that we're going to be utilizing this demo Now we want to visualize it as well。

 so we're going to be using the Maplot Lib library and we're going to name it S PLT。

So this is a really short program， but it is fairly complex in this program we want to create data points that form three centers that use two features and 300 samples in this example。

 we can adjust a cluster standard deviation to whatever we want and randomize the samples to see。

what is the best separation of the data。So here we have clusters before cas is applied。

So when we specify that we specify X and y to be our clusters and we're going to call make blobs to basically create our cluster clusters。

 we are going to specify that we're using 300 samples and we're going to be utilizing two features and three center points we want to specify that our clustered standard deviation is going to be 0。

2 and we're going to shuffle our data to make sure it's randomized。

Now we want to specify the colors and markers to be used to distinguish the samples in their respective clusters as well。

 so some of the colors I'm going to be using for the clusters include brown， green， blue and gray。

We also want to specify our markers， which are sponsor by V，X O and N the carrot symbol。

Nextext we want to create our k means model and apply the algorithm to the clusters。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_84.png)

So for every cluster or for each cluster I call the cluster count in this example。

 we're going to say for every cluster in the range from one to5 so it'll be actually from1 to4 we want to create our model so here we're applying k means and we're specifying our cluster to be our cluster count so for each cluster count1 to4 we're going to initialize it to be k means pass it with 10 initialized values 300 samples our tolerance is going to be specified to be 1 e to the minus4 and our random state is going to be initialized to zero because we don't in this case we don't want to randomize it。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_86.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_87.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_88.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_89.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_90.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_91.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_92.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_93.png)

So that's one thing you want to make sure you do Now if you want to know more about these hyperparameters。

 you can go ahead and Google the K meanss machine learning algorithm on SKLar and what it'll do is it'll give you a site with a more elaborate explanation of how each of these hyperparameters work so that if you want to improve your model and you want to understand how it works you can mess around with the hyperparameters and adjuster values but for the sake of simplicity I am just showing you how you can create a model using in Python using Python code。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_95.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_96.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_97.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_98.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_99.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_100.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_101.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_102.png)

Next， you want to compute the cluster centers and predict the cluster index for each sample。

 so basically here we're training and testing our model and we're by calling the fit_ predict function on our X data and we're applying that on our K means model and we're going to store that in predicted。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_104.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_105.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_106.png)

Now we want to specify what cluster is being plotted。

 so we're going to specify the cluster numbers and we're going to plot it on a scatter plot。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_108.png)

And here you can see that basically I'm passing in our predicted values and I'm specifying what each predicted value should be based on their cluster number。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_110.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_111.png)

And here we're specifying our markers， we're specifying our labels， and so forth。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_113.png)

I highly encourage you to read through my comments if you have a hard time understanding。

 go ahead and pause the video if you don't understand it or rewind so that way you can understand how each line of code works again。

This is a little bit more complicated and a little bit more complex compared to supervised machine learning。

 but after watching it a few times you'll understand how it works。Now。

Final step is we want to basically like plot our clusters and their centers。

 so I'm plotting this using a scatter plot and I'm going to plot their cluster centers。

 I'm specifying what are our centers， how many samples are we going to plot and what are our centers depicted by so this is going to be depicted by an orange star and those are going to be called our centroids。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_115.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_116.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_117.png)

Our orange stars are known as our centroids。

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_119.png)

Now finally we want to go ahead let me move this， we want to put it on a grid。

 that's why I'm calling the grid function， I'm going to title it K means and I'm going to show you what happens for each cluster count。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_121.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_122.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_123.png)

And we're going to include a legend to identify what is each cluster represented by。 and finally。

 I'm going to we call the show function to display all our graphs。

 So here you can see that technically we have only one cluster which is all in red and we have one centroid。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_125.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_126.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_127.png)

Here we have two centroids and we have two clusters， one in red， one in green。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_129.png)

Here we have three centroids where we have one red， one green and one blue。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_131.png)

And finally， here we have four centroids where we have one red， one green， one blue， one gray。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_133.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_134.png)

That's how you can go ahead and classify your data using an unsupervised machine learning algorithm。

 This case， we use the K means machine learning algorithm。



![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_136.png)

![](img/cc6ac3cd054e4f226c8158fb6bcbb21e_137.png)

Thank you。