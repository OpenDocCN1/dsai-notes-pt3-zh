# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P125：36_其他决策树分割准则.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

So now let's look at the classification error versus entropy in a graph。

 so this is starting off with the graph of the classification error function。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_1.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_2.png)

So the X axis is just going to be the purity of the node。

 So how much of the node is going to be one over the total amounts of actual values in that subset。

And the Y axis is the classification error if we were to classify everything as either one or zero。

 which is what we're doing with each one of our subsets using that majority class。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_4.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_5.png)

Since we are using the majority class， the most uncertain and thus the largest error will occur at that 50。

50 split。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_7.png)

The idea is to find splits that are furthest away from this center， right。

 we want that Y axis that air to be as small as possible。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_9.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_10.png)

And we can see here for the given equation that we end up with this straight line relationship。

 If you have a subset of 75% being that class of one， then the error is going to be 25%。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_12.png)

And if you move up to move up 5 per cent to 80%， let's say， then the air goes down linearly 5%。

 So as your subset increases in purity by 5 per cent， your air goes down linearly by 5% cent。

 and hence， the straight line relationship。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_14.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_15.png)

Now， if we look at the curve that the more sophisticated new entropy function creates。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_17.png)

As should be the case， it will also have a maximum impurity at that 5050 split。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_19.png)

But it's now curved outside of that 5050 split。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_21.png)

And this curvature is what allows the splitting to continue to occur。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_23.png)

So why is this the case for this more complex equation that we have here？



![](img/8922ff76e149a7a1db1a381a38bf7a8e_25.png)

Let's focus in on an example to see why。So starting with the classification error。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_27.png)

Say that this is going to be our parent node。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_29.png)

And these are the child node。 We have the left node with that 50。

50 split for that smaller class that we saw earlier。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_31.png)

And the right note is a larger subset with a bit of a better split， so a lower classification error。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_33.png)

Now， the weighted average of the blue and red nodes here will always be another point on the straight line。

 as B a straight in between these two nodes。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_35.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_36.png)

So this may， as it does here， land on that parent node。

 which would prevent us from splitting our tree any further。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_38.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_39.png)

So the weighted average will always be within a straight line between our right and left node。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_41.png)

Now hopefully you're starting to think， well， with curvature。

 maybe we won't have that problem since it's not a straight line。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_43.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_44.png)

So now moving to our entropy curve。The curvature now creates this bulge above that straight line。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_46.png)

And we can go back to our example of our parent node， which is here on our entropy curve。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_48.png)

That left node at the 5050 split of the smaller sunset。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_50.png)

And that right node with a bit of a better split。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_52.png)

And now the weighted average is on that straight line that's connecting the red and blue。

 which is guaranteed to be below our parent note。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_54.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_55.png)

Here， the x values of the parent node and the average that weighted average will line up。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_57.png)

And the weighted average here ensures that we。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_59.png)

Are ensuring a smaller value than what we had for our parent note in regards to entropy。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_61.png)

So we now ensure some information gain at the split and can therefore continue splitting to get down to our homogeneous nodes。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_63.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_64.png)

Now， with that in mind， another popular measure to be aware of， in fact。

 the default measure used for SscaleLn is the Genie index。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_66.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_67.png)

Similar to entropy， it will also have that bulge， so it will ensure that there's the possibility of perfect splits down the line。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_69.png)

And one advantage of the genie versus entropy。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_71.png)

Is it does not contain logs， so it'll be easier to compute。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_73.png)

The equation is as simple as 1 minus the sum of the accuracy squared。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_75.png)

So we've talked a lot here about ensuring the capability of perfect splits。

 but at the end of the day， getting perfect splits at all of our leaf nodes will eventually lead to overfitting as we discussed much earlier。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_77.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_78.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_79.png)

So we do want the possibility， but we know that if we allow it to completely get down to those homogeneous nodes。

 we will be overfitting， so in the next video， we'll touch on this and discuss as we do with all our algorithms。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_81.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_82.png)

How to avoid overfitting to our training set and ensure that right balance of the bias and variance。



![](img/8922ff76e149a7a1db1a381a38bf7a8e_84.png)

![](img/8922ff76e149a7a1db1a381a38bf7a8e_85.png)

All right， I'll see you there。

![](img/8922ff76e149a7a1db1a381a38bf7a8e_87.png)