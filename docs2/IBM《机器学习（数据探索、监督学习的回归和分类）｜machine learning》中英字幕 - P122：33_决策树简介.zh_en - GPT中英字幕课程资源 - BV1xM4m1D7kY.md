# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P122：33_决策树简介.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/f3b769a895e206509d92842a4a27c81f_0.png)

So now say we're going to give this example to move to decision trees。

 we have this data related to customer turnout at a tennis facility and for our upcoming discussion。

 suppose you are going to be the administrator of this facility。



![](img/f3b769a895e206509d92842a4a27c81f_2.png)

And in addition to predicting the number of customers。

 you want to evaluate the impact of various drivers on player turnout。

 such as outlook of weather where we have this ornal value of sunny。



![](img/f3b769a895e206509d92842a4a27c81f_4.png)

![](img/f3b769a895e206509d92842a4a27c81f_5.png)

which is greater than overcast， which is greater than rainy temperature with the ordinal values of cool。

 mild or hot with hopping， you know the greatest and cool being the least。



![](img/f3b769a895e206509d92842a4a27c81f_7.png)

![](img/f3b769a895e206509d92842a4a27c81f_8.png)

We also have humidity levels and stronger weak wind。



![](img/f3b769a895e206509d92842a4a27c81f_10.png)

So using these features， we want to again predict whether or not customers will play。

 will play tennis at our courts。

![](img/f3b769a895e206509d92842a4a27c81f_12.png)

Decision trees will seek to split up the data set into two data sets at every set。

 for which the decision is going to be easier and then continue to iterate。



![](img/f3b769a895e206509d92842a4a27c81f_14.png)

![](img/f3b769a895e206509d92842a4a27c81f_15.png)

So this purple node asks the questions。Is temperature greater or equal to mild。

 remember working with an ordinal variable， so it's mild or greater would be mild or hot。



![](img/f3b769a895e206509d92842a4a27c81f_17.png)

![](img/f3b769a895e206509d92842a4a27c81f_18.png)

That question then divides the original training data set into two subsets。



![](img/f3b769a895e206509d92842a4a27c81f_20.png)

And hopefully these two sub datata sets contain more information in regards to the target variable to predict so that we can say if temperature is less than mild。

 then it's most likely that customers will not play tennis and if temperature is greater than or equal to mild。

 then customers will be more likely to play tennis。

 so that's the idea we split up our data and hopefully we have a cleaner split between those that play tennis and those that do not play tennis。



![](img/f3b769a895e206509d92842a4a27c81f_22.png)

![](img/f3b769a895e206509d92842a4a27c81f_23.png)

![](img/f3b769a895e206509d92842a4a27c81f_24.png)

![](img/f3b769a895e206509d92842a4a27c81f_25.png)

![](img/f3b769a895e206509d92842a4a27c81f_26.png)

Now the circles where we ask each one of our questions。Are going to be our node。

And the circle where we reach a decision， yes or no， are going to be called the leaves。



![](img/f3b769a895e206509d92842a4a27c81f_28.png)

And those are our leaves here below。

![](img/f3b769a895e206509d92842a4a27c81f_30.png)

Now there's no reason to ask just one question， we can keep asking question after question to further segment our data set。



![](img/f3b769a895e206509d92842a4a27c81f_32.png)

The depth of this tree is now a plateau。

![](img/f3b769a895e206509d92842a4a27c81f_34.png)

Since we've split our tree twice。

![](img/f3b769a895e206509d92842a4a27c81f_36.png)

And decision tree has categories in the leaves， so categories here being will or will not play tennis and it will use the majority class left at those final leaves to predict a class that followed the steps down this decision tree。

 So it's going to be a classification algorithm trying to classify according to the majority class here。

 either play tennis or did not play tennis。

![](img/f3b769a895e206509d92842a4a27c81f_38.png)

![](img/f3b769a895e206509d92842a4a27c81f_39.png)

![](img/f3b769a895e206509d92842a4a27c81f_40.png)

![](img/f3b769a895e206509d92842a4a27c81f_41.png)

However， this idea can be used in predicting quantities instead of classes as well。

 and rather than incision trees， you will be called regressioning trees。



![](img/f3b769a895e206509d92842a4a27c81f_43.png)

![](img/f3b769a895e206509d92842a4a27c81f_44.png)

So here's an example of a regression tree。 here， the inputs are going to be numerical values for slope and elevation within the Himalayas。

 and we're going to want to predict the average precipitation。

 which is going to be a continuous value。 So we're no longer trying to come up with a classification。

 but rather a regression in trying to predict some continuous value。



![](img/f3b769a895e206509d92842a4a27c81f_46.png)

![](img/f3b769a895e206509d92842a4a27c81f_47.png)

![](img/f3b769a895e206509d92842a4a27c81f_48.png)

![](img/f3b769a895e206509d92842a4a27c81f_49.png)

We'll use the same idea as we did with classification at the node we're going to ask this yes or no question Here we see the question is。

 is the elevation less than 7900 feet， we use that to split our data set into true or false and that's going to be a split of original data into two smaller dataset sets。



![](img/f3b769a895e206509d92842a4a27c81f_51.png)

![](img/f3b769a895e206509d92842a4a27c81f_52.png)

![](img/f3b769a895e206509d92842a4a27c81f_53.png)

![](img/f3b769a895e206509d92842a4a27c81f_54.png)

And we can again ask another question or make a decision。



![](img/f3b769a895e206509d92842a4a27c81f_56.png)

Here we have slope less than or equal to 2。5 and then we have at each one of these leaves。

 we're going to have the average value for the remaining of that subset。

 so we keep splitting up our data into smaller subsets。

 we will then have the outcome variables which are going to be continuous values for each one of these subsets。



![](img/f3b769a895e206509d92842a4a27c81f_58.png)

![](img/f3b769a895e206509d92842a4a27c81f_59.png)

![](img/f3b769a895e206509d92842a4a27c81f_60.png)

![](img/f3b769a895e206509d92842a4a27c81f_61.png)

And then with that subset， we can average out within that subset what is going to be the average precipitation。

 and we can use that as our prediction。

![](img/f3b769a895e206509d92842a4a27c81f_63.png)

![](img/f3b769a895e206509d92842a4a27c81f_64.png)

So to see how this looks in regards to a twodisional graph where we have maybe just one value so here our x is0 through5 and our y is going to be negative two to two and we're trying to predict using the continuous values on the x axis。

 what the values will be on the y axis， since there can ultimately be a certain number of leaves with binary splits depending on the depth of our tree。

 so we saw a depth of our tree increase from one to two before the possible outputs of a regression tree are going to be bound by the number of splits that there are。

 so those are going to be the number of values that we can have。



![](img/f3b769a895e206509d92842a4a27c81f_66.png)

![](img/f3b769a895e206509d92842a4a27c81f_67.png)

So it'll not get an output of a linear function that can basically spit out any value。

 but rather limited to whatever amount of leaves we have at the end of our tree。



![](img/f3b769a895e206509d92842a4a27c81f_69.png)

![](img/f3b769a895e206509d92842a4a27c81f_70.png)

So here' is a regression tree of depth2 that would spit out four different values and we project that onto the y axis。

 ignoring each one of the jumps， and those are going to be the four values that we predict given our different values of x。



![](img/f3b769a895e206509d92842a4a27c81f_72.png)

![](img/f3b769a895e206509d92842a4a27c81f_73.png)

Now， increasing the depth of a tree， one can allow for more possible values。

 the bigger the depth of a tree， the more different average and different subsets you're going to be working with。



![](img/f3b769a895e206509d92842a4a27c81f_75.png)

![](img/f3b769a895e206509d92842a4a27c81f_76.png)

And that could be a good thing or a bad thing this new tree of depth5 seems a bit overfit to each one of our data points。

 so we may be overfitting here so we want to find that right balance of the right depth so we don't overfit our data。



![](img/f3b769a895e206509d92842a4a27c81f_78.png)

![](img/f3b769a895e206509d92842a4a27c81f_79.png)

![](img/f3b769a895e206509d92842a4a27c81f_80.png)

In the next video， we'll begin to dive under the hood into how decision tree is actually built All right。

 I'll see you there。

![](img/f3b769a895e206509d92842a4a27c81f_82.png)

![](img/f3b769a895e206509d92842a4a27c81f_83.png)

![](img/f3b769a895e206509d92842a4a27c81f_84.png)