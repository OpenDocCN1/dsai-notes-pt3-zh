# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P102：13_K最近邻决策边界.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/070b73145bb985b7d43d769acc2d50e8_0.png)

So what is needed to get started with arc cane end model。

The first thing that we're going to need is the correctly determined value of k， right。

 how many neighbors are we going to choose between？



![](img/070b73145bb985b7d43d769acc2d50e8_2.png)

![](img/070b73145bb985b7d43d769acc2d50e8_3.png)

The second thing that we need is we need to know how to measure the distance between each one of our neighbors。

 Now， this may seem somewhat obvious， but there are different measures that we can use。

 And we need to also keep in mind， how will those measures extrapolate to beyond two dimensions。



![](img/070b73145bb985b7d43d769acc2d50e8_5.png)

![](img/070b73145bb985b7d43d769acc2d50e8_6.png)

![](img/070b73145bb985b7d43d769acc2d50e8_7.png)

And then finally， related to that second question of the different measures that we'll use for distance。

 we need to know if some neighbors should perhaps be weighted more heavily than others， perhaps say。

 according to how close they are to the value that we're trying to predict。



![](img/070b73145bb985b7d43d769acc2d50e8_9.png)

![](img/070b73145bb985b7d43d769acc2d50e8_10.png)

![](img/070b73145bb985b7d43d769acc2d50e8_11.png)

So when we make predictions with K andN， we can draw what is called a decision boundary。



![](img/070b73145bb985b7d43d769acc2d50e8_13.png)

![](img/070b73145bb985b7d43d769acc2d50e8_14.png)

So we see here that this is a line that divides a data based on different prediction values and here where k equals 1。

 we can see that the decision boundary follows nearly every single example in our training set。



![](img/070b73145bb985b7d43d769acc2d50e8_16.png)

![](img/070b73145bb985b7d43d769acc2d50e8_17.png)

And conceptually， it would seem that we are probably overfitting。

 and it would make sense for each of these two small pockets that we have in blue and pink within our larger pink and blue boundaries may need to be eliminated。



![](img/070b73145bb985b7d43d769acc2d50e8_19.png)

![](img/070b73145bb985b7d43d769acc2d50e8_20.png)

![](img/070b73145bb985b7d43d769acc2d50e8_21.png)

We can go to the other extreme and set k to the value of the total number of points。

 which is 34 and let's think what would happen if we set it to all of the points that we have。

 so we set it to 34 rather than to 1。

![](img/070b73145bb985b7d43d769acc2d50e8_23.png)

![](img/070b73145bb985b7d43d769acc2d50e8_24.png)

![](img/070b73145bb985b7d43d769acc2d50e8_25.png)

Hopefully， you guess this， that once you set it to the size of all of the data points。

 essentially all we're doing is classifying each one identically。

 according to a majority vote of our data set。 So again， this is probably underfitting。

 So this is that idea of trade off between variance and bias。 This is highly biased。

 whereas K equals1 has a very high variance。

![](img/070b73145bb985b7d43d769acc2d50e8_27.png)

![](img/070b73145bb985b7d43d769acc2d50e8_28.png)

![](img/070b73145bb985b7d43d769acc2d50e8_29.png)

![](img/070b73145bb985b7d43d769acc2d50e8_30.png)

So based on this discussion， you can probably already guess that the decision boundary depends on our choice in the value of K。



![](img/070b73145bb985b7d43d769acc2d50e8_32.png)

Thus， we need to decide how to determine that optimal value of k for our model。



![](img/070b73145bb985b7d43d769acc2d50e8_34.png)

Now， K and N does not provide a correct K for us。 This will not be a learned parametermeter。

 but rather， it's going to be a hyperparameter that we。

 as users will have to tune in a similar fashion to how we have tuned things such as regularization terms。

 Lambda and C in our past models。

![](img/070b73145bb985b7d43d769acc2d50e8_36.png)

![](img/070b73145bb985b7d43d769acc2d50e8_37.png)

![](img/070b73145bb985b7d43d769acc2d50e8_38.png)

![](img/070b73145bb985b7d43d769acc2d50e8_39.png)

We're just going to choose different Lambdas and Cs and see which ones work best。



![](img/070b73145bb985b7d43d769acc2d50e8_41.png)

The right value is going to depend on which error metric is most important。

 We now have clarity on the importance of the right error metric when performing classification and know that we must keep in mind what our business objective is Again。

 do we need to ensure we capture all the true positives then focus more on recall or do we need to ensure that our predicted positives are actually correct than we may want to focus more on precision and we can find that balance using something like the F1 score。



![](img/070b73145bb985b7d43d769acc2d50e8_43.png)

![](img/070b73145bb985b7d43d769acc2d50e8_44.png)

![](img/070b73145bb985b7d43d769acc2d50e8_45.png)

![](img/070b73145bb985b7d43d769acc2d50e8_46.png)

![](img/070b73145bb985b7d43d769acc2d50e8_47.png)

![](img/070b73145bb985b7d43d769acc2d50e8_48.png)

A common approach is to use an elbow method approach。

 and this emphasizes kins in a curve of the error rate as a function of K。

 and this will be similar to using our grid search。

 where we find the K for which we see the model approaches the minimum error on our holdout set。



![](img/070b73145bb985b7d43d769acc2d50e8_50.png)

![](img/070b73145bb985b7d43d769acc2d50e8_51.png)

![](img/070b73145bb985b7d43d769acc2d50e8_52.png)

And beyond this point， the rate of improvement slows or stops。



![](img/070b73145bb985b7d43d769acc2d50e8_54.png)

Now， in the next video， we'll continue our discussion of K&N with a focus on how we can choose the correct distance measure。



![](img/070b73145bb985b7d43d769acc2d50e8_56.png)

![](img/070b73145bb985b7d43d769acc2d50e8_57.png)