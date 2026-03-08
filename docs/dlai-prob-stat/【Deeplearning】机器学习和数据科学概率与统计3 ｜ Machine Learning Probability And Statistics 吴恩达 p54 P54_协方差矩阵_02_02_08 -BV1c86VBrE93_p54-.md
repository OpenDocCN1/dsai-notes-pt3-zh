# 【Deeplearning】机器学习和数据科学概率与统计3 ｜ Machine Learning Probability And Statistics 吴恩达 p54 P54_协方差矩阵_02_02_08 -BV1c86VBrE93_p54-

So far we looked at several examples we've calculated the variance of the covariance of join distributions。

 we look at the discrete join distributions with age of children and height grades and naps and we got the following variances and covariances we also saw three different games with the same variances the same expectations and covariance of1 minus1 and0 and finally we looked at the data set of waiting time and customer ratings and we noticed that it has a negative covariance because the higher the waiting time。

 the lower the ratings so now what we want to do is we want to put all these things together and imagine that we have a very large data set would say five variables how would the covariances work here Well we have the variance of each one of them separately and the covariances of each of the pairs so we would have 10 pairs over here。



![](img/98866812aeaf49ecc42027ea3d50c4c5_1.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_2.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_3.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_4.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_5.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_6.png)

And that's going to be the covariance matrix， so the covariance matrix simply has the variances in the diagonal。



![](img/98866812aeaf49ecc42027ea3d50c4c5_8.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_9.png)

That's the variance of x here， the variance of y and the covariances on the anti diagonal capturing this in matrix form will look as follows。

 so for example， the covariance matrix of this data set is this matrix over here。



![](img/98866812aeaf49ecc42027ea3d50c4c5_11.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_12.png)

Covariance matrix is very， very useful in statistics and also in machine learning。



![](img/98866812aeaf49ecc42027ea3d50c4c5_14.png)

So let's look at the covariance matrix for the age versus height1。

 it's going to be this matrix over here。

![](img/98866812aeaf49ecc42027ea3d50c4c5_16.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_17.png)

Now let's look at the one for the game examples they are these two four games1 and two and finally let's say we had three variables so for a data set with three variables we're going to have a three by3 covariance matrix where in the main diagonal we're going to have the variances and in the other coordinates we're going to have the corresponding covariances so for example in the coordinate Xy we're going to have the covariance of xy and the coordinates x set。

 we have the covariance of x set， etc etc and again if we have five variables and we're going to have a5 by5 covariance matrix where in the main diagonal we have all the variances and in the other places we have the corresponding covariance of the row variable and the column variable this matrix is going to be called sigma。

 the covariance matrix。

![](img/98866812aeaf49ecc42027ea3d50c4c5_19.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_20.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_21.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_22.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_23.png)

![](img/98866812aeaf49ecc42027ea3d50c4c5_24.png)