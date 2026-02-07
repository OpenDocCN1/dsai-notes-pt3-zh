# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P124：35_基于熵的分割.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now， we're going to introduce a new ametric called entropy。

 and our new ametric to find the best split will be defined by this equation。

H of T equals the negative sum of I given T times of log of probability of I given T。

 and similar to before P of I given T is just going to be the probability of a class。

 given the certain subset of data we are currently working in。



![](img/9432e6c14b8dd9aab580e34a47e51edd_1.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_2.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_3.png)

So this equation becomes the sum of8 over 12。

![](img/9432e6c14b8dd9aab580e34a47e51edd_5.png)

Times log 2 of 8 over 12 for the positive class。

![](img/9432e6c14b8dd9aab580e34a47e51edd_7.png)

And 4 over 12 times log  to a 4 over 12 for the negative class。

 So that's just working with that top node there and giving each of the two possible outcomes。

 So we have the 8 over 12 for one proportion and 4 over 12 for the other proportion working within that top node。



![](img/9432e6c14b8dd9aab580e34a47e51edd_9.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_10.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_11.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_12.png)

We then multiply that sum by negative one as the equation states。

 and we have an initial entropy of 0。9183。 Nena eventually reduced that by going down nodes and getting the weighted average of each of the entroies。



![](img/9432e6c14b8dd9aab580e34a47e51edd_14.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_15.png)

So now let's get the entropy of our two child notes。



![](img/9432e6c14b8dd9aab580e34a47e51edd_17.png)

On the left， we have negative two fourth times log 2 of24 minus again。

 two fourth times log2 of two fourths， because they're going to be equal for both the positive and negative classier。



![](img/9432e6c14b8dd9aab580e34a47e51edd_19.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_20.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_21.png)

Then on the right。

![](img/9432e6c14b8dd9aab580e34a47e51edd_23.png)

We have negative 6 over 8 times log 2 of 6 over 82 over 8 times log 2 of2 over 8。

 and the entropy on the right side will be equal to 0。8113。



![](img/9432e6c14b8dd9aab580e34a47e51edd_25.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_26.png)

We can then take the weighted average of each， as we did with that classification error。



![](img/9432e6c14b8dd9aab580e34a47e51edd_28.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_29.png)

And we see that we have decreased entropy by 0。0441。

 So here rather than the entropy being exactly the same。



![](img/9432e6c14b8dd9aab580e34a47e51edd_31.png)

When we take the weighted average， according to how much of the subset from our parent node went into each one of the child nodes。



![](img/9432e6c14b8dd9aab580e34a47e51edd_33.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_34.png)

We see that the entropy has decreased by 0。0441。

![](img/9432e6c14b8dd9aab580e34a47e51edd_36.png)

Since we were able to have information gained when we use entropy。

 we now can allow for further splitting down the line。

 rather than that early stopping that we saw with the classification error。😊。



![](img/9432e6c14b8dd9aab580e34a47e51edd_38.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_39.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_40.png)

And we can now actually reach a goal of having all homogeneous notes。



![](img/9432e6c14b8dd9aab580e34a47e51edd_42.png)

Now in the next video， we're going to dive deeper into why entropy actually works where classification tends to fail。

All right， I'll see you there。

![](img/9432e6c14b8dd9aab580e34a47e51edd_44.png)

![](img/9432e6c14b8dd9aab580e34a47e51edd_45.png)