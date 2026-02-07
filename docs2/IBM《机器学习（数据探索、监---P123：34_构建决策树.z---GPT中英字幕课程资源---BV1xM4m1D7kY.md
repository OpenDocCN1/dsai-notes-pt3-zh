# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P123：34_构建决策树.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

![](img/ec7d24a65d4aaf9406915b16385bb928_0.png)

So now let's get back to decision trees for classification。



![](img/ec7d24a65d4aaf9406915b16385bb928_2.png)

And we will recall that our first step is going to be to select the feature and ask a question with a true or false answer to first start rowing our tree。

 So split it into those two subsets， Given whether or not we answer true or false to a given question。



![](img/ec7d24a65d4aaf9406915b16385bb928_4.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_5.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_6.png)

We then continue splitting with our available features to create further subsets of our data。



![](img/ec7d24a65d4aaf9406915b16385bb928_8.png)

And can continue to split。And what we need to think of is when can we actually stop splitting and declare we've made a decision？



![](img/ec7d24a65d4aaf9406915b16385bb928_10.png)

So if we think back to our tennis example， we can split there by outlook of weather， temperature。

 humidity levels and stronger weak wind。 And then after we split， perhaps the subset of sunny。

 mild weather and weak wind would lead to a subset where everyone plays tennis。

 given that it's sunny mild weather and weak wind， whereas a split of rainy versus not rainy。

 just that subset of rainy may already determine that no one will play tennis on that day。😊。



![](img/ec7d24a65d4aaf9406915b16385bb928_12.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_13.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_14.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_15.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_16.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_17.png)

So one of the ideas in terms of determining when we should stop splitting is to continue splitting until the leaves are pure。



![](img/ec7d24a65d4aaf9406915b16385bb928_19.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_20.png)

That means every leaf， once we do all our splits is a collection of only one class。

 so either everyone in that subset plays tennis or everyone in that subset does not play tennis。

 and there aren't any leaves with the combination of yes and no。



![](img/ec7d24a65d4aaf9406915b16385bb928_22.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_23.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_24.png)

It's either fully will play tennis in that subset or fully will not play tennis within that subset。



![](img/ec7d24a65d4aaf9406915b16385bb928_26.png)

Another idea is we can enter a max depth。

![](img/ec7d24a65d4aaf9406915b16385bb928_28.png)

And then stop or prune our tree at that be。

![](img/ec7d24a65d4aaf9406915b16385bb928_30.png)

So when we say stop， meaning we don't make any more splits。

 Prune means that we build it all the way out， and then we start pruning that tree。

 cutting off some of the leaves to get down to our original predetermined maximum depth。



![](img/ec7d24a65d4aaf9406915b16385bb928_32.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_33.png)

And at that depth， we don't allow it to grow any further。



![](img/ec7d24a65d4aaf9406915b16385bb928_35.png)

As a result， leaves are probably not going to be pure in this example。

 and we can make our best guess at that point by determining what class in that subset is more dominant。

 Which one has the majority， and we can assign that class to that leaf。



![](img/ec7d24a65d4aaf9406915b16385bb928_37.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_38.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_39.png)

Now， a third idea。

![](img/ec7d24a65d4aaf9406915b16385bb928_41.png)

Is we can keep going until a predefined performance metrics is achieved。



![](img/ec7d24a65d4aaf9406915b16385bb928_43.png)

For example， if the classification has a certain accuracy， then we would stop。



![](img/ec7d24a65d4aaf9406915b16385bb928_45.png)

In practice， that first idea will often overfit， so if we allow it to keep going until all of our leaves are pure。

 then we will often overfit our training set。 That is our splits or that questions that we ask at each node are usually going to be tailor made for that training set and may not generalize well。

 and those last two ideas are in order to avoid overfitting。

 So either pruning at a maximum depth or setting once we get to certain accuracy metric we stop。



![](img/ec7d24a65d4aaf9406915b16385bb928_47.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_48.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_49.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_50.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_51.png)

So how exactly do we find the right splits？

![](img/ec7d24a65d4aaf9406915b16385bb928_53.png)

The right question to ask in terms of that true or false in order to get to those subsets that we'd like to ultimately get to。



![](img/ec7d24a65d4aaf9406915b16385bb928_55.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_56.png)

We need a way of evaluating all of the possible splits。Once we have that wave evaluating the splits。

 we can then use greedy search to find the best split。



![](img/ec7d24a65d4aaf9406915b16385bb928_58.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_59.png)

And greedy search here means that at every step， we find the best split regardless of what happened in prior steps or what would happen in future steps。



![](img/ec7d24a65d4aaf9406915b16385bb928_61.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_62.png)

So how do we find that split？Enter here information theory。

 We're going to find the split that induces the biggest information gain。

 which we will continue to elaborate on in a couple of slides。😊。



![](img/ec7d24a65d4aaf9406915b16385bb928_64.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_65.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_66.png)

But how is that information gain going to be defined mathematically？



![](img/ec7d24a65d4aaf9406915b16385bb928_68.png)

Let's go ahead and take a look。So let's start by first trying classification error。

 just saying if we can decrease the overall average error when we split our data。 In other words。

 we're doing one minus the overall accuracy and that accuracy metric just being how many we got correct over how many there are there in total。



![](img/ec7d24a65d4aaf9406915b16385bb928_70.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_71.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_72.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_73.png)

So at the top note， given that the majority vote would have been yes， yes， they will play tennis。

 we have a classification error of1 minus 8 over 12。

1 minus our accuracy since we would have predicted four out of those 12 incorrect。

 so we have an error rate of 0。33 here。

![](img/ec7d24a65d4aaf9406915b16385bb928_75.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_76.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_77.png)

Now， stepping down to the leaves now I actually want to introduce some vocabulary here。

 the top node we will consistently be calling the parent， whereas the nodes underneath。

 such as the yes no two and2 that we have here and the yes no six and two that we have here。

 those will be the children so we'll have the parent on top and the children underneath。



![](img/ec7d24a65d4aaf9406915b16385bb928_79.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_80.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_81.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_82.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_83.png)

And that'll be interchange with leaves as well， so stepping down to the leaves。

 steeping down to the children， we see a classification of 0。5 on the left side。



![](img/ec7d24a65d4aaf9406915b16385bb928_85.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_86.png)

So we actually have some information loss rather than information gain here。



![](img/ec7d24a65d4aaf9406915b16385bb928_88.png)

But it's with a smaller fraction of our data points compared to what we see on the right leaf。



![](img/ec7d24a65d4aaf9406915b16385bb928_90.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_91.png)

And then on our right side， we see that we reduce our error from that larger subset。



![](img/ec7d24a65d4aaf9406915b16385bb928_93.png)

From 0。3333 to 0。25。

![](img/ec7d24a65d4aaf9406915b16385bb928_95.png)

Now， we want to measure that overall change， according to the weighted average of our two new classification errors。

 where the weight is equal to the proportion of that parent node that are now in each one of those two different child notes。

 So we're going to weight each one of those classification errors。

 According to how much of that parent node went into the subset of each the left and right child notes。



![](img/ec7d24a65d4aaf9406915b16385bb928_97.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_98.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_99.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_100.png)

So we get on the left side， 412 times 0。5。

![](img/ec7d24a65d4aaf9406915b16385bb928_102.png)

And then on the right side， we get 812 times 0。25。

![](img/ec7d24a65d4aaf9406915b16385bb928_104.png)

And we find that the， once we multiply those two and then add them together to get the weighted average。

 we find that overall， we have not had any information gained given our new split。



![](img/ec7d24a65d4aaf9406915b16385bb928_106.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_107.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_108.png)

So in this example， assuming this is the best split that we had left， which is possible。

 we would claim that we should not split the nodes any further。



![](img/ec7d24a65d4aaf9406915b16385bb928_110.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_111.png)

The problem here is that we are forced to stop well short of a point where all of our leaves would be homogeneous。



![](img/ec7d24a65d4aaf9406915b16385bb928_113.png)

Such that all would play or all would not play in each one of our child leads。



![](img/ec7d24a65d4aaf9406915b16385bb928_115.png)

With this possibility in mind。

![](img/ec7d24a65d4aaf9406915b16385bb928_117.png)

In our next video， we will begin to discuss air metrics using practices that actually allow for us to continue to split until we have perfectly homogeneous notes。

😊。

![](img/ec7d24a65d4aaf9406915b16385bb928_119.png)

![](img/ec7d24a65d4aaf9406915b16385bb928_120.png)

Allright， I'll see you there。

![](img/ec7d24a65d4aaf9406915b16385bb928_122.png)