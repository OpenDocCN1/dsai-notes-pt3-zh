# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P103：14_K最近邻距离度量.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Let's now focus on how to compute distance between two given points。



![](img/6932be13c31400e38fbef4fe378b451b_1.png)

This is the similarity measure in our model where close points are thought to be similar。

 the assumption is that similar points will most likely have similar outcomes。

 churn versus not churned here。

![](img/6932be13c31400e38fbef4fe378b451b_3.png)

![](img/6932be13c31400e38fbef4fe378b451b_4.png)

So what is the distance between these two points？Now there are a few choices that one can make here。



![](img/6932be13c31400e38fbef4fe378b451b_6.png)

Perhaps the most popular is going to be the Euclidean distance。



![](img/6932be13c31400e38fbef4fe378b451b_8.png)

This is easy to understand and interpret because it's very visual， it's the literal distance。



![](img/6932be13c31400e38fbef4fe378b451b_10.png)

We have the distance from our point of prediction in data usage on the vertical axis。



![](img/6932be13c31400e38fbef4fe378b451b_12.png)

And we have the distance from our point of prediction in foam usage on the horizontal axis。



![](img/6932be13c31400e38fbef4fe378b451b_14.png)

And the distance is just going to be the square root of the sum of each one of these distances squared。

 and with more features， we just square each one of these distances for each of the individual features from that point of prediction and take the square root of that sum of each one of those distances。

 that'll be our Euclidean distance。

![](img/6932be13c31400e38fbef4fe378b451b_16.png)

![](img/6932be13c31400e38fbef4fe378b451b_17.png)

![](img/6932be13c31400e38fbef4fe378b451b_18.png)

![](img/6932be13c31400e38fbef4fe378b451b_19.png)

Another measure can be the L1 distance， it's appropriately named the Manhattan distance。

 since you usually can't walk between two points directly， you have to turn at that corner first。

So now we just add all the absolute distances。And again， if we extend to more dimensions。

 we simply add on the absolute distance from each of these individual features from that point that we're trying to predict。

And these are going to be the two choices that are most popular in practice。



![](img/6932be13c31400e38fbef4fe378b451b_21.png)

So we've discussed how distance is going to be important for our our K nearest neighbors model and given that it relies so heavily on distance when we're trying to predict that point from our training set。



![](img/6932be13c31400e38fbef4fe378b451b_23.png)

![](img/6932be13c31400e38fbef4fe378b451b_24.png)

This implies that the scale of our variables is going to be really important。

 Suppose we have another customer feature， number of services to which they subscribe。

 And we can see an example this year where the number of services is small。

 ranging between  one and 5， as we see on the X axis， relative to the average data usage。

 which is measured in gigabytes and ranges from 10 to 60。



![](img/6932be13c31400e38fbef4fe378b451b_26.png)

![](img/6932be13c31400e38fbef4fe378b451b_27.png)

![](img/6932be13c31400e38fbef4fe378b451b_28.png)

![](img/6932be13c31400e38fbef4fe378b451b_29.png)

Unscaleed， then the services feature has a reduced impact on distance relative to this data usage。



![](img/6932be13c31400e38fbef4fe378b451b_31.png)

Now， this is a problem because once we expand that region and we look at the closest distance to this point。



![](img/6932be13c31400e38fbef4fe378b451b_33.png)

We can see that the number of services will largely determine the nearest neighbors。



![](img/6932be13c31400e38fbef4fe378b451b_35.png)

And data usage will have little effect on the outcome at all since it's much more spread out as much greater distances。



![](img/6932be13c31400e38fbef4fe378b451b_37.png)

![](img/6932be13c31400e38fbef4fe378b451b_38.png)

And if you remember the formulas， we're artificially weighing the number of services distances heavily here。



![](img/6932be13c31400e38fbef4fe378b451b_40.png)

This can be a good thing in some examples， maybe if you find given your domain expertise that perhaps we want to weight number of services more heavily。

 but in most cases this is probably not going to be the case。

 so let's look at this same example when the data has been appropriately scaled。



![](img/6932be13c31400e38fbef4fe378b451b_42.png)

![](img/6932be13c31400e38fbef4fe378b451b_43.png)

![](img/6932be13c31400e38fbef4fe378b451b_44.png)

![](img/6932be13c31400e38fbef4fe378b451b_45.png)

And we've discussed this in prior courses， the process of creating a uniform range for all of our features is something known as feature scaling。



![](img/6932be13c31400e38fbef4fe378b451b_47.png)

And thinking back， can we recall different methods that we discuss for scaling our data？



![](img/6932be13c31400e38fbef4fe378b451b_49.png)

![](img/6932be13c31400e38fbef4fe378b451b_50.png)

Hopefully what you're thinking of are Min Max Scalrs was one of those examples where we subtract the minimum value of a given feature and divide that value by the maximum minus the minimum for that given feature or the standard scalar where we subtract the mean and divide by the standard deviation。



![](img/6932be13c31400e38fbef4fe378b451b_52.png)

![](img/6932be13c31400e38fbef4fe378b451b_53.png)

![](img/6932be13c31400e38fbef4fe378b451b_54.png)

![](img/6932be13c31400e38fbef4fe378b451b_55.png)

So once we perform our feature scaling， we can now ensure that our features have equal influence on our K nearest neighbors model。



![](img/6932be13c31400e38fbef4fe378b451b_57.png)

![](img/6932be13c31400e38fbef4fe378b451b_58.png)

Here we can see that the X axis， the number of services， is expanded much more so than before。



![](img/6932be13c31400e38fbef4fe378b451b_60.png)

And in this case， the nearest neighbors are going to be different than what we saw previously。



![](img/6932be13c31400e38fbef4fe378b451b_62.png)

This time with equal influence coming from the data usage。

 they are customers that churn rather than not churn。

 which was the case when we didn't scale our features。



![](img/6932be13c31400e38fbef4fe378b451b_64.png)

![](img/6932be13c31400e38fbef4fe378b451b_65.png)

So we can also predict multiple classes with KNN fairly easily。



![](img/6932be13c31400e38fbef4fe378b451b_67.png)

Here we are predicting three classes churned and left for competitor， churned by cancelling。

 and we don't have other info。 and just they did not churn。



![](img/6932be13c31400e38fbef4fe378b451b_69.png)

![](img/6932be13c31400e38fbef4fe378b451b_70.png)

And we can again just set the value of k and create a decision boundary as before。



![](img/6932be13c31400e38fbef4fe378b451b_72.png)

The prediction of multiple classes is quite simple for Can nearest neighbors for other machine learning methods。

 we'll see that sometimes modifications are required to handle multiple cases。

 but here it'll be as simple as just choosing between more potential classes。

Which one class has the majority vote in regards to which one of those classes？



![](img/6932be13c31400e38fbef4fe378b451b_74.png)

![](img/6932be13c31400e38fbef4fe378b451b_75.png)

Is closest to the point that we're trying to predict or has a majority vote in the class that we're trying to predict？



![](img/6932be13c31400e38fbef4fe378b451b_77.png)

And notice that in multiple classes choosing an odd K may not save us。

 so instead you may want to choose K where it's equal to a multiple of the number of labels。

 so if we have three labels here， some multiple of three plus one to ensure that one always has majority vote。



![](img/6932be13c31400e38fbef4fe378b451b_79.png)

![](img/6932be13c31400e38fbef4fe378b451b_80.png)

![](img/6932be13c31400e38fbef4fe378b451b_81.png)

Now we've been focused on classification thus far。

![](img/6932be13c31400e38fbef4fe378b451b_83.png)

But it's worth noting that regression can also be performed with can nearest neighbors。

 That is we can predict continuous values as well， that idea of how much。



![](img/6932be13c31400e38fbef4fe378b451b_85.png)

![](img/6932be13c31400e38fbef4fe378b451b_86.png)

And this works in a similar fashion to classification。

 except that the value predicted is the mean value of its neighbors。



![](img/6932be13c31400e38fbef4fe378b451b_88.png)

So when k is the same value as the number of points。



![](img/6932be13c31400e38fbef4fe378b451b_90.png)

As single value is predicted， that is the mean of all the values will be predicted。



![](img/6932be13c31400e38fbef4fe378b451b_92.png)

When k is larger than1， KN regression acts as a smoothing function。

 with is the rolling average of the closest three points where k equals the three here。



![](img/6932be13c31400e38fbef4fe378b451b_94.png)

And when k is1， the prediction simply connects each one of the points exactly。

 we're just saying the nearest neighbor for each one of the points is going to be our prediction。



![](img/6932be13c31400e38fbef4fe378b451b_96.png)