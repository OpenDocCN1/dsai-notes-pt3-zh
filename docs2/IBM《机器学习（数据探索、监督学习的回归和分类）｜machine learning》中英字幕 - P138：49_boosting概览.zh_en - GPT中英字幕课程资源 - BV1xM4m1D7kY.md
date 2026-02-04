# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P138：49_boosting概览.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

Now let's see how boosting actually works。So we're going to start off by creating this initial decision stump with one node and two leaves。

 So this initial decision stump will split our universe into2。



![](img/4472776e38c3f73f4f367a9885b9ddf7_1.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_2.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_3.png)

And let's say these are our examples and notice that there are three samples that are falsely classified as blue when they should be red。



![](img/4472776e38c3f73f4f367a9885b9ddf7_5.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_6.png)

These are the mistakes that that first model made。And it would be a good idea to weigh these more heavily in our next week learner。

As in we will weigh those records more heavily， so we'll get a larger error if we get those ones that we got wrong before。

 wrong again with our new decision boundary。

![](img/4472776e38c3f73f4f367a9885b9ddf7_8.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_9.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_10.png)

That is that next week' learner should be rewarded more to get those ones right。



![](img/4472776e38c3f73f4f367a9885b9ddf7_12.png)

So we lower the weights of the records that the first model got right and increase the weights of the ones that that were wrongly classified。

 And that's the major idea here in boosting。

![](img/4472776e38c3f73f4f367a9885b9ddf7_14.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_15.png)

And if we did that， maybe this is our new decision boundary of our second week learner。



![](img/4472776e38c3f73f4f367a9885b9ddf7_17.png)

And we see here that we have now classified those three that we got incorrect on the first time on our first model。

 correctly on this second model。

![](img/4472776e38c3f73f4f367a9885b9ddf7_19.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_20.png)

And we can continue to do this based on the errors made by each one of those prior learners。

 So we see here in that second model， we got those three blue ones incorrectly classified。

 so we create another decision boundary。

![](img/4472776e38c3f73f4f367a9885b9ddf7_22.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_23.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_24.png)

And now we have three different week learners。

![](img/4472776e38c3f73f4f367a9885b9ddf7_26.png)

And once we're done， we can combine those decisions to output one final decision。



![](img/4472776e38c3f73f4f367a9885b9ddf7_28.png)

So even though our weak learners are very simple decision trees with very simple decision boundaries。

 our final decision boundary can be more complex。

![](img/4472776e38c3f73f4f367a9885b9ddf7_30.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_31.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_32.png)

And for each one of these stumps。This final decision boundary will be created by waitinging how well each decision boundary did and correctly classifying at each step so better classifiers get more weight。



![](img/4472776e38c3f73f4f367a9885b9ddf7_34.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_35.png)

As well as incorporating a learning rate to say how much we allow to correct our errors at each one of these steps。



![](img/4472776e38c3f73f4f367a9885b9ddf7_37.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_38.png)

And that learning rate is a hyperparmeter that we can actually tune。



![](img/4472776e38c3f73f4f367a9885b9ddf7_40.png)

And this Lada represents that learning rate， or how much weight do we provide to each successive decision tree？



![](img/4472776e38c3f73f4f367a9885b9ddf7_42.png)

Or how much we will allow each step to move towards correcting the prior trees。



![](img/4472776e38c3f73f4f367a9885b9ddf7_44.png)

Generally speaking， we would want more trees if we are working with a lower learning rate。

 as that would mean that we are correcting our errors at a very slow pace。

 the lower that learning rate is。

![](img/4472776e38c3f73f4f367a9885b9ddf7_46.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_47.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_48.png)

On the other hand， if it's too high， then we can easily overfit by allowing each decision。

 each successive tree to have too much influence on our final decision。😊。



![](img/4472776e38c3f73f4f367a9885b9ddf7_50.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_51.png)

So a smaller learning rate。

![](img/4472776e38c3f73f4f367a9885b9ddf7_53.png)

Means less overfitting。Hence， a higher bias if we have a smaller lower learning rate and a lower variance。



![](img/4472776e38c3f73f4f367a9885b9ddf7_55.png)

Now， that gives us a general overview of how boosting works in general with each successive weak learner helping to correct the errors of prior learners。

 And with that， we'll get more into the mathematical side in that next video。



![](img/4472776e38c3f73f4f367a9885b9ddf7_57.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_58.png)

![](img/4472776e38c3f73f4f367a9885b9ddf7_59.png)

All right， I'll see you there。

![](img/4472776e38c3f73f4f367a9885b9ddf7_61.png)