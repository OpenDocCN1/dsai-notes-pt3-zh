# 【帝国理工学院】机器学习数学：主成分分析Pca ｜ Pca Machine Learning p03 P03_数据集的均值_01_02_02 -BV1fUYSzBEMp_p3-

Data is often compactly described by some of its statistical properties。

 such as the mean and the variance。In this video， we'll explain how to compute means of data sets。

The mean of a data describes the average data point。

 The mean does not have to be a typical data point。

 and it also does not need to be part of the data itself。For example。

 if we look at a set of images of digit 8， the average image looks like this。

It has properties of all images in the data。But it is not part of the data set itself。

We obtain the average 8， as follows。

![](img/528b3b10fd4edbf76bae52a984d9f9a2_1.png)

Remember that an image can be represented as a long vector in a high dimensional vector space by stacking all pixels together After transforming all images into these vectors。

 we take all image vectors in our dataset， add them together and divide by the number of images in the dataset。

This gives us the average image vector。If we then reshape that vector into an image again。

 we get the average digit in the data set。Here's an example with four8s。

The mean of the first one is just the image itself。But when we add the second image。

 we see that the average image now contains properties from both images。When we add the third image。

 the mean image is all three images on top of each other， divided by three。After the fourth image。

 we can still see characteristics of all four images in the average image。😊。

When we add more images to our data， the average digit becomes a bit more blurry。



![](img/528b3b10fd4edbf76bae52a984d9f9a2_3.png)

And if we take all eight in our data set， we get this8 as the average image。Generally。

 if we have a data set， X1 to X N， let's say。Di。Cons of data points， x1，2。Xn。

We get the mean value of the expected value of this data set as follows。 we write， well。

 the expected value of D。Is one over the number of data points。 So this is n。Times， the sum。

N equals 1 to capital n。Of X， N。 So we sum up all data points in our data and divide by the number of data points that we have。

Let's look at an example。 I create a data set consisting of the five numbers that I get when I roll five dies。

We got one，2，4，6 at 6。 So let's write this down。So I'm going to call this D prime。Is one，2，4，6。

 and 6。And now， the expected value。Or the average。Of this data set。Is。

The sum of all elements in this data set。 So this is  one plus 2 plus 4 plus 6 plus 6。

Divided by the number of elements in our data set。 And that is 5。

So if we sum these things together and divide by5， we get 19。Over 5 or。3。8。We can clearly see that 3。

8 is not part of the data set and cannot even be achieved by rolling a dice。Therefore。

 it is also worthwhile keeping in mind that although the mean is the average of the data set。

 it does not have to be a typical instance。 In this video。

 we computed the mean value of data sets as the average data point。

The mean value doesn't have to be part of the data set。In the next video。

 we'll introduce variances to describe the spread of the data around the mean value。



![](img/528b3b10fd4edbf76bae52a984d9f9a2_5.png)