# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P54：P54 StatsLearning Lect10b 120213.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/8552ea16a0b3d623f5dc5295c4c585d2_0.png)

Okay， well， so far we've been talking about regression trees。

 the response was quantitative salaries in this case of baseball players。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_2.png)

Oftentimes trees are used when the response is a categorical variable and so then we call those classification trees。

 but you'll see the technologies is very similar and we just have to change essentially the loss function and how we measure good performance。

 so let's see how that goes。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_4.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_5.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_6.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_7.png)

So。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_9.png)

We're going to predict in a classification tree each observation belonging to the most commonly occurring class。

 so that's what's going to happen in the terminal node of the tree instead of just giving the prediction being the mean。

 we're going to classify to the most common class。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_11.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_12.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_13.png)

We're going to grow the tree in a very same way as we did for regression trees。

 but we don't use residual summer squares as a criterion for making the splits。

 we need a criterion that's more geared towards classification。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_15.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_16.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_17.png)

So one thing you can do is at each internal node， you can just look at the classification error rate。

And that's easy to compute。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_19.png)

Suppose class K。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_21.png)

Ill beon， so suppose you've got capital K classes。And you compute the proportion in the terminal node in each of the classes from one up to capital K Well the class you're going to classify is going to is a class that's got the largest of those probabilities those proportions and the error you're going to make is going to be one minus that maximum so all the ones that don't belong to the maximal class are going to be counted as errors so you could use that to decide on the split and so that's the proportion of errors you're going to make。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_23.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_24.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_25.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_26.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_27.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_28.png)

But it turns out that that's a little bit jumpy and noisy and not very it doesn't lead to a very smooth tree growing process。

 and for that reason some other measures are preferable。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_30.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_31.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_32.png)

One measure is the GI index。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_34.png)

And it's a kind of variance measure across the classes so you've got K classes， capital K classes。

 often K is two， but not necessarily。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_36.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_37.png)

And for those who know the binomial distribution， this is each of the terms there is like a binomial variance and in fact for the multinomial。

 this is the diagonal of the these on the diagonal of the covariance matrix。

 so this is a measure of total variability in that region。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_39.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_40.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_41.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_42.png)

And if the genome index is really small， what that means is。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_44.png)

Pretty much one class is favored and all the rest are really small whereas as an extreme case traveler。

 if the region is pures， it's all one class， then one of those Ps will be one。

 the rest to be0 and G will be zero。 that's a good point。 and on the other hand。

 if I guess if they all equally distributed in the classes， this G index will be maximum。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_46.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_47.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_48.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_49.png)

And but it moves it changes in a smooth way。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_51.png)

So that's one of the criteria that are very popular。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_53.png)

嗯。And it's also known as a purity index， it measures the purity of the class。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_55.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_56.png)

An alternative is the devviance or cross entropy， and this is based on the binomial log likelihoodli or the multinomial log likelihoodlude and it's a measure thats。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_58.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_59.png)

B is rather similarly to the GI index， and either of these are used and give very similar results。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_61.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_62.png)

So let's look at an example， we'll look at the heart data。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_64.png)

These later have a binary response called HD， there's 303 patients。

 and they're all represented with chest pains。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_66.png)

So the outcome has a value yes， indicates the presence of heart disease based on an angiographic test while N means no heart disease。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_68.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_69.png)

For these data， there are 13 predictors， amongst them age， sex， cholesterol。

 and other heart and lung function measurements。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_71.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_72.png)

And so we ran the tree growing process with cross validation and we see what we get in the next figure。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_74.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_75.png)

At the top。You see the full tree grown to all the data and you can see it's quite a bushy tree。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_77.png)

With an early split on T， it's actually it's a thalium stress test， a thium stress is， okay。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_79.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_80.png)

And and then。The left and right nodes were split on CA with calcium， I think。

 which is calcium and then the subsequent splits， it's hard to see that you these pictures are in the book。

 so quite a bushy tree。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_82.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_83.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_84.png)

And you see at the terminal nodes of this tree that the classifications know or yes。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_86.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_87.png)

So that means an observation that， for example， ended up in this leftmost terminal nodedia。

 the majority in that class were nos， no heart disease。

 and so the classification produced would be a no。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_89.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_90.png)

Where the right hand， one year is a yes。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_92.png)

Interesting。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_94.png)

This terminal node has two nodes。So if they both predicted no why was the Eplier tool。

 well it must mean that one of these nodes is purer than the other。

 so even though they were both ended up having a majority of nodes。

 the one node was purer than the other node and the GenI index would identify such a node。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_96.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_97.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_98.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_99.png)

So this tree is probably too bushy and so once again cross validation was used and again we see in the right hand panel the results of cross validation。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_101.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_102.png)

And we see。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_104.png)

The training error， the test error and the validation error。

Here we've actually looked at the training error averaged over each of the cross validation folds。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_106.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_107.png)

Which is why it's a little jumpy。And actually even increases in one point here。

 because the trees and the architecture of the trees are different in each of the folds。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_109.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_110.png)

The cross validation and test error we had a left our test set here as well。

 those curves look pretty much the same and we end up seeing that a tree size of around about six tends to do well these bars on these cross validation and test curves or standard error bars so there's quite a bit of variability here the data set's not that big。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_112.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_113.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_114.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_115.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_116.png)

And on the right here we see the prune back tree that's pruned back to size6。

 of course the pruning was again governed by the cost complexity parameter alpha。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_118.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_119.png)

And this year will be a subtree of the big tree grown and that gave the best classification performance。

 which is estimated to be around about 25% error in this case。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_121.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_122.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_123.png)

In this figure。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_125.png)

We show we compare trees with linear models， trees aren't always the right thing to do。

 and so to contrast that， we look at two different scenarios。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_127.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_128.png)

In these cartoons here， the truth is indicated by these two colors in this top left panel。

 the truth is actually best depicted by a linear model。

 so the decision boundary in this case between the two classes is best in by a line and in this case a tree is not going to do very well we see a trees attempt to partition this space。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_130.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_131.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_132.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_133.png)

And you know while it does a valiant job， it just doesn't do well enough because it's confined to pick boxy regions right so there'd be a split over here。

 a split over there and then this region was subdivided。

 then that region was subdivided in an attempt to get at this linear decision boundary。

 so this would be classified as beige， this would be classified as green， beige。

 green and so on in a stepy fashion。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_135.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_136.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_137.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_138.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_139.png)

On the other end， in the lower two panels， the optimal region is。A blocky kind of partition region。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_141.png)

And here， a linear model is not going to do well in the left panel。

 we see the best linear approximation to this decision boundary and it's going to make lots of errors because。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_143.png)

You know，With a one single linear boundary， it's hard to approximate a rectangular region like this。

 and of course， in this one， a tree will nail it so itll with two splits it can get the decision boundary perfectly。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_145.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_146.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_147.png)

So some problems are more naturallyly suited to trees， some problems aren't。

 and so the idea is we're going to think of trees as one tool in our toolbox and we'll use it where appropriate。

 but of course we'll also bear in mind simpler linear models as well。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_149.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_150.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_151.png)

So just to wrap up the section on treason， we've seen some。

 there's advantage and disadvantages in a sense they're simple if the trees are small。

 not too many terminal notes because they're easy to display and to understand for nonspecs。

And for example， we look back at this heart disease tree， right， the prune one in the bottom right。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_153.png)

A doctor might light history tree because。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_155.png)

It mimics in a sense the way his decision making process might work。

 and I was trying to decide whether a patient has heart disease he might first do initial tests based on thalium stress tests。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_157.png)

And if they failed that test。

![](img/8552ea16a0b3d623f5dc5295c4c585d2_159.png)

Then do a further test based on calcium and decide about heart disease， if the test was passed。

 we might again do a calcium test and then fall by some other criteria so you stratify the population in a series of simple rules to try to determine whether patient is of high or low risk。

 so for that reason it's trees are popular because their simplicity in the fact that they mimic the way some people make decisions。



![](img/8552ea16a0b3d623f5dc5295c4c585d2_161.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_162.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_163.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_164.png)

![](img/8552ea16a0b3d623f5dc5295c4c585d2_165.png)

As's a series of。Of splits。And they can display in a simple tree， which means again。

 they're attractive because there aren't equations to have to understand。

They can also handle qualitative predictors without the need to create dummy variables。

 other words some of the categorical variables can be have more than two levels and you can split a categorical variable into two sets of subcategories。

So these are all good things。 The big downside is that the。

They don't predict so well compared to more state of the art methods， and we'll see， for example。

 for the hard data that the prediction accuracy of a tree is not very good compared to other methods。

The other maps that we'll talk about now actually use trees， but in an ensemble， they combine trees。

They build many trees on the same data， and then they average or combine them in some way。

 and in the process they improve the predictionary substantially。

