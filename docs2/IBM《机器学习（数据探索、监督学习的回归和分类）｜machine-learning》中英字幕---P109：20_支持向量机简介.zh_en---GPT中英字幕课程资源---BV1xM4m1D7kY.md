# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P109：20_支持向量机简介.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this section， we'll discuss the powerful linear classifier support vector machines。

So the learning goals for this section will include gaining an understanding to the support vector Ma approach to classification。



![](img/8a2b5a333b1feace40a339f6e68543e5_1.png)

Seeing how support vector machines compare with the logistic regression model that we introduced earlier in this course。



![](img/8a2b5a333b1feace40a339f6e68543e5_3.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_4.png)

Willll go over the cost function used to optimize our support vector machines。



![](img/8a2b5a333b1feace40a339f6e68543e5_6.png)

And as we do with every model， we'll learn how to properly regularize to ensure that we find the right balance between bias and variance。



![](img/8a2b5a333b1feace40a339f6e68543e5_8.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_9.png)

Now I'd like to start off by recalling what we learned early in the course in regards to logistic regression。



![](img/8a2b5a333b1feace40a339f6e68543e5_11.png)

The idea here was to transform our loss function for our linear regression so that we weigh the far away points much less。



![](img/8a2b5a333b1feace40a339f6e68543e5_13.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_14.png)

So that our separation hyperplane does not try too hard to get those right。



![](img/8a2b5a333b1feace40a339f6e68543e5_16.png)

And that was a measure taken in order not to be skewed by the outliers in our data set。



![](img/8a2b5a333b1feace40a339f6e68543e5_18.png)

Now let's try from there to build an intuition behind the support vector machine。



![](img/8a2b5a333b1feace40a339f6e68543e5_20.png)

With the support vector machine here we're just looking at one dimension that phone usage。

 we ought to find that optimal point in the phone usage in which we can split our data and create a decision boundary。

Now， we see that here。 and with all values above this line。

 we were going to predict that we would not churn。 And all values below this line。

 we would predict that they did churn。

![](img/8a2b5a333b1feace40a339f6e68543e5_22.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_23.png)

And here we clearly see that it's not a good choice as this specific boundary results in three misclassifications。

 right， We have three examples where we predict not churned given our decision boundary when in actuality it should have been predicted churn。



![](img/8a2b5a333b1feace40a339f6e68543e5_25.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_26.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_27.png)

Next we can move to the other gap in our phone usage。



![](img/8a2b5a333b1feace40a339f6e68543e5_29.png)

And we see this gap here。 And again， we have a bad misclassification because we have two misclassifications。

 It's a bad choice of decision boundary。 We probably want to move somewhere in between。



![](img/8a2b5a333b1feace40a339f6e68543e5_31.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_32.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_33.png)

Now， this decision boundary has no misclassifications。



![](img/8a2b5a333b1feace40a339f6e68543e5_35.png)

But we want to think， is it really the best choice that we can make？

In the close neighborhood of this choice and split。There are going to be other choices first。

 but that will also result in no misclassifications， right。

 essentially anything between those blue and pink dots will result in no misclassifications。



![](img/8a2b5a333b1feace40a339f6e68543e5_37.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_38.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_39.png)

So you want to start thinking， should we move this boundary a little bit to the left。

 a little bit to the right in order to optimize where this decision boundary lays？



![](img/8a2b5a333b1feace40a339f6e68543e5_41.png)

And we're also going to introduce here this dotted line。

 which will represent how far we are from the nearest point。



![](img/8a2b5a333b1feace40a339f6e68543e5_43.png)

So that nearest point here is going to be just that the left of the line is going to be that blue dot。

 and we see that we have a very tight。

![](img/8a2b5a333b1feace40a339f6e68543e5_45.png)

Dotted lines across either side of our straight line， which is our decision boundary。



![](img/8a2b5a333b1feace40a339f6e68543e5_47.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_48.png)

And then we can think again for this point。We see that we're very close to the other side of our boundary。

 and we end up with a very tight margin as well， with these dotted lines being very close to that decision boundary。



![](img/8a2b5a333b1feace40a339f6e68543e5_50.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_51.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_52.png)

So here's an idea。Let's maximize that region between the two classes。



![](img/8a2b5a333b1feace40a339f6e68543e5_54.png)

Let's draw the boundary at a place where it's equidistant from the closest blue and the closest red class。

😊。

![](img/8a2b5a333b1feace40a339f6e68543e5_56.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_57.png)

And this will ultimately be the goal of our support vector machine algorithm。



![](img/8a2b5a333b1feace40a339f6e68543e5_59.png)

In the next video， we'll continue to expand on this idea on how support vector machines will end up performing classifications on your data。

 see there。

![](img/8a2b5a333b1feace40a339f6e68543e5_61.png)

![](img/8a2b5a333b1feace40a339f6e68543e5_62.png)