# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P101：12_K最近邻分类.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this video， we'll be discussing our second algorithm of the course， K nearest Neighors。

So the learning goals for our section on KNN will be to first identify the K nearest neighbors approach for classification。



![](img/f86aea66ad78a24992da917b992e31a2_1.png)

![](img/f86aea66ad78a24992da917b992e31a2_2.png)

We'll then discuss the K& N decision boundary， now we can adjust that boundary by our choice in K。



![](img/f86aea66ad78a24992da917b992e31a2_4.png)

We'll discuss distance measurement and the importance of feature scaling。

 and here we'll make clear how important it will be to first scale the data before using a model such as KNN。



![](img/f86aea66ad78a24992da917b992e31a2_6.png)

![](img/f86aea66ad78a24992da917b992e31a2_7.png)

And then finally， we'll show the implementation of CanNN for classification in SKLRn。

 as well as showing you how CanN can be used for regression as well。



![](img/f86aea66ad78a24992da917b992e31a2_9.png)

![](img/f86aea66ad78a24992da917b992e31a2_10.png)

Now， as in our previous example， when we did logistic regression。

 we want to predict the telecom customer churn， we have our historical data that includes the customer's usage。

 both in minutes as well as the customer' usage in gigabytes， their data usage。

 and we can display this historical data on the plot。

 as we see here where the phone usage is going to be shown on the X axis in minutes and the data usage in gigabytes is shown on the Y axis。



![](img/f86aea66ad78a24992da917b992e31a2_12.png)

![](img/f86aea66ad78a24992da917b992e31a2_13.png)

![](img/f86aea66ad78a24992da917b992e31a2_14.png)

![](img/f86aea66ad78a24992da917b992e31a2_15.png)

![](img/f86aea66ad78a24992da917b992e31a2_16.png)

![](img/f86aea66ad78a24992da917b992e31a2_17.png)

We can then color the points according to whether or not that customer churned。

 where blue means a customer churned and red means that they did not。



![](img/f86aea66ad78a24992da917b992e31a2_19.png)

![](img/f86aea66ad78a24992da917b992e31a2_20.png)

Now， let's say we examine an existing customer and we want to predict the likelihood that that customer will turn。



![](img/f86aea66ad78a24992da917b992e31a2_22.png)

This purple dot signifies such a customer， and we can plot it alongside the other data。 Now。

 I want you to think when you look at how this customer compares to others for which we have their churn outcomes。



![](img/f86aea66ad78a24992da917b992e31a2_24.png)

![](img/f86aea66ad78a24992da917b992e31a2_25.png)

![](img/f86aea66ad78a24992da917b992e31a2_26.png)

Can we predict the customer's churn likelihood。

![](img/f86aea66ad78a24992da917b992e31a2_28.png)

Think how would you intuitively predict this results？

What many of you hopefully did or are doing is looking at nearby customers or those with similar features and using that to guess the results。



![](img/f86aea66ad78a24992da917b992e31a2_30.png)

![](img/f86aea66ad78a24992da917b992e31a2_31.png)

And it stands reason that churn outcomes of newer customers are going to be similar to those of nearby customers。

 as long as each one of these features， of course， are important in regards to predicting this matter。



![](img/f86aea66ad78a24992da917b992e31a2_33.png)

![](img/f86aea66ad78a24992da917b992e31a2_34.png)

![](img/f86aea66ad78a24992da917b992e31a2_35.png)

And this， looking at how similar new data is to our label data is essentially what the can nearest neighbor algorithm does for us。



![](img/f86aea66ad78a24992da917b992e31a2_37.png)

![](img/f86aea66ad78a24992da917b992e31a2_38.png)

So again， we're trying to predict what this new value will be。



![](img/f86aea66ad78a24992da917b992e31a2_40.png)

And we need to think what happens if the nearby results are in conflict。

 we see both churned and not churned nearby。

![](img/f86aea66ad78a24992da917b992e31a2_42.png)

![](img/f86aea66ad78a24992da917b992e31a2_43.png)

With this in mind， how do we decide which one is correct？In the case that we have here。

 we're setting k equals to1， which means we're looking at the one nearest neighbor。



![](img/f86aea66ad78a24992da917b992e31a2_45.png)

![](img/f86aea66ad78a24992da917b992e31a2_46.png)

And we see with this one year's neighbor， which we just highlighted in pink。

 that we are going to end up predicting not churned because that is the one closest labeled customer to our current customer that we're trying to predict。



![](img/f86aea66ad78a24992da917b992e31a2_48.png)

![](img/f86aea66ad78a24992da917b992e31a2_49.png)

![](img/f86aea66ad78a24992da917b992e31a2_50.png)

Now， what if we look at the two closest neighbors， So does this value change。

 So we see here now we're looking at the two closest neighbors， and we have a bit of a conflict。

 One churned， and one did not。 How can we decide which is correct。



![](img/f86aea66ad78a24992da917b992e31a2_52.png)

![](img/f86aea66ad78a24992da917b992e31a2_53.png)

![](img/f86aea66ad78a24992da917b992e31a2_54.png)

One solution is to only use an odd value for the number of neighbors。



![](img/f86aea66ad78a24992da917b992e31a2_56.png)

You can think what else can we do to break this tie。

 You can weight the points according to their distance。 We can choose the certainty of results。

 or we can just randomly choose one。

![](img/f86aea66ad78a24992da917b992e31a2_58.png)

![](img/f86aea66ad78a24992da917b992e31a2_59.png)

And what we want to keep in mind here is that there will be different options available to us to creating this tiebreaker。

 but a clean way to ensure that you don't have to create a tiebreaker would just be to choose an odd number of k。



![](img/f86aea66ad78a24992da917b992e31a2_61.png)

![](img/f86aea66ad78a24992da917b992e31a2_62.png)

![](img/f86aea66ad78a24992da917b992e31a2_63.png)

So now let's say we are using the three closest neighbors now we're increasing k to 3。

 and we see now we have three of the closest neighbors This time we have two customers that churned and one that did not。



![](img/f86aea66ad78a24992da917b992e31a2_65.png)

![](img/f86aea66ad78a24992da917b992e31a2_66.png)

![](img/f86aea66ad78a24992da917b992e31a2_67.png)

So here we would predict that they would churn。This new customer。

 and that's going to be a different result than K equals one。



![](img/f86aea66ad78a24992da917b992e31a2_69.png)

And this odd number of k eliminates the issues with ties。

 and this value we choose for K is something that we're going to continue to explore as we go through。

 It will be one of those hyperpara that we will tune in order to come up with the best fit model。



![](img/f86aea66ad78a24992da917b992e31a2_71.png)

![](img/f86aea66ad78a24992da917b992e31a2_72.png)

![](img/f86aea66ad78a24992da917b992e31a2_73.png)

![](img/f86aea66ad78a24992da917b992e31a2_74.png)

Okay， now for our last example， let's take the four closest neighbors。

 so we're adding on one more This time our prediction stays the same because we have three neighbors that are churned and one that did not thus our prediction of churn seems even more certain as we add on more neighbors and also we don't have this situation of a tie。

 so we are able to do four neighbors here， but again。

 we'd suggest moving up to five or down to three in regards to choosing your number of k in general。



![](img/f86aea66ad78a24992da917b992e31a2_76.png)

![](img/f86aea66ad78a24992da917b992e31a2_77.png)

![](img/f86aea66ad78a24992da917b992e31a2_78.png)

![](img/f86aea66ad78a24992da917b992e31a2_79.png)

![](img/f86aea66ad78a24992da917b992e31a2_80.png)

![](img/f86aea66ad78a24992da917b992e31a2_81.png)

In the next video， we will continue with this example and dive deeper into how to actually set up your Can nearestus neighbor's algorithm。



![](img/f86aea66ad78a24992da917b992e31a2_83.png)

![](img/f86aea66ad78a24992da917b992e31a2_84.png)