# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P56：-056-Statistical Learning_ 8.3 Classification Trees.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

![](img/2f3ee3a5a5e528f8f387dbc26701af56_0.png)

Okay， well， so far we've been talking about regression trees。

 the response was quantitative salaries in this case of baseball players。

Oftentimes trees are used when the response is a categorical variable and so then we call those classification trees。

 but you'll see the technologies is very similar and we just have to change the essentially the loss function and how we measure good performance。

 so let's see how that goes。So。We're going to predict in a classification tree each observation belonging to the most commonly occurring class。

 so that's what's going to happen in the terminal node of the tree instead of just giving the prediction being the mean。

 we're going to classify to the most common class。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_2.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_3.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_4.png)

We're going to grow the tree in a very same way as we did for regression trees。

 but we don't use residual summer squares as a criterion for making the splits。

 we need a criterion that's more geared towards classification。

So one thing you can do is at each internal node， you can just look at the classification error rate。

And that's easy to compute。Suppose class K。I'll beon， so suppose you've got capital K classes。

And you compute the proportion in the terminal node in each of the classes from one up to capital K Well the class you're going to classify is going to is a class that's got the largest of those probabilities。

 those proportions and the error you're going to make is going to be one minus that maximum right so all the ones that don't belong to the maximumimal class are going to be counted as errors so you could use that to decide on the split and so that's a proportion of errors you're going to make。

But it turns out that that's a little bit jumpy and noisy。

 and it's not very it doesn't lead to a very smooth tree growing process。 And for that reason。

 some other measures are preferable。One measure is the GI index。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_6.png)

And it's a kind of variance measure across the classes， so you've got K classes， capital K classes。

 often K is two， but not necessarily。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_8.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_9.png)

And this for those who know the binomial distribution。

 this is each of the terms there is like a binomial variance and in fact for the multinomial。

 this is the diagonal of these on the diagonal of the covariance matrix。

 so this is a measure of total variability， in that region。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_11.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_12.png)

And if the genome index is really small， what that means is。

Pretty much one class is is favored and all the rest are really small。

 whereas as an extreme case travel writer， if the region is pures， it's all one class。

 then one of those be hat will be one， the rest will be 0 and G will be 0。 That's a good。

 that's a good point。 And， and on the other hand， if。

 I guess if they all equally distributed in the classes， this G index will be maximum。

AndBut moves it changes in a smooth way。So that's one of the criteria that are very popular。嗯。

And it's also known as a purity index。 that measures the purity of the class。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_14.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_15.png)

An alternative is the deviance or cross entropy and this is based on the binomial log likelihoodlude or the multinomial log likelihoodlude and it's a measure that's。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_17.png)

Phas rather similarly to the Gni index。 and either of these are used and give very similar results。

So let's look at an example， wherell look at the heart data。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_19.png)

These later have a binary response called HD， there's 303 patients。

 and they're all represented with chest pains。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_21.png)

So the outcome has a value yes， indicates the presence of heart disease based on an angiographic test while no means no heart disease。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_23.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_24.png)

For these data there are 13 predictors， amongst them age， sex， cholesterol。

 and other heart and lung function measurements。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_26.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_27.png)

And so we ran the tree growing process with cross validation and we see what we get in the next figure。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_29.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_30.png)

At the top。You see the full tree grown to all the data， and you can see it's quite a bushy tree。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_32.png)

With an early split on T， it's actually it's E thalium stress test， ahelium stress test， okay？



![](img/2f3ee3a5a5e528f8f387dbc26701af56_34.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_35.png)

And then the two the left and right nodes were split on CA calcium， I think。

 which is calcium and then the subsequent splits， it's hard to see but these pictures are in the book。

 so quite a bushy tree。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_37.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_38.png)

And you see at the terminal nodes of this tree that the classificationifications know or yes。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_40.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_41.png)

So that means an observation that， for example， ended up in this leftmost terminal noddia。

 the majority in that class were nos， no heart disease。

 and so the classification produced would be a no。Whereas the right hand one year is a yes。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_43.png)

Interesting。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_45.png)

This terminal node has two nodes。So if they both predicted no why was the e splitlitier tool。

 well it must mean that one of these nodes is purer than the other。

 so even though they were both ended up having a majority of nodes。

 the one node was purer than the other node and the GI index would identify such a node。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_47.png)

So this tree is probably too bushy and so once again cross validation was used and again we see in the right hand panel the results of cross validation。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_49.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_50.png)

And we see。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_52.png)

The training error， the test error and the validation error。

Here we've actually looked at the training error averaged over each of the cross validation folds。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_54.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_55.png)

Which is why it's a little jumpy。And actually even increases in one point。

 in because the trees and the architecture of the trees are different in each of the folds。

The cross validation and test error we had a left our test set here as well。

 those curves look pretty much the same and we end up seeing that a tree size of around about six tends to do well these bars on these cross validation and test curves are standard error bars so there's quite a bit of variability here the data set's not that big。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_57.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_58.png)

And on the right here we see the prune back tree that's pruned back to size6。

 of course the prunian was again governed by the cost complexity parameter alpha。

And this year will be a subtree of the big tree grown。

 and that gave the best classification performance。

 which is estimated to be around about 25% error in this case。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_60.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_61.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_62.png)

In this figure。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_64.png)

We show we compare trees with linear models， trees aren't always the right thing to do。

 and so to contrast that， we look at two different scenarios。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_66.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_67.png)

In these cartoons here the truth is indicated by these two colors in this top left panel。

 the truth is actually best depicted by a linear model so the decision boundary in this case between the two classes is best in by a line and in this case a tree is not going to do very well we see a trees attempt to partition this space。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_69.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_70.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_71.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_72.png)

And you know while it does a valiant job， it just doesn't do well enough because it's confined to pick boxy regions right so there'd be a split over here。

 a split over there， and then this region was subdivided。

 then that region was subdivided in an attempt to get at this linear decision boundary。

 so this would be classified as as beige， this would be classified as green， beige。

 green and so on in a steppy fashion。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_74.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_75.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_76.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_77.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_78.png)

On the other end， in the lower， in the lower two panels， the， the optimal region is。

A blocky kind of partition region。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_80.png)

And here， a linear model is not going to do well In the left panel。

 we see the best linear approximation to this decision boundary。

 and it's going to make lots of errors because。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_82.png)

You know， with a one single linear boundary， it's hard to approximate a rectangular region like this。

 And， of course， in this one， a tree will nail it。 So itll with two splits。

 it can get the decision boundary perfectly。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_84.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_85.png)

So some problems are more naturallyly suited to trees， some problems aren't。

 and so the idea is we're going to think of trees as one tool in our toolbox and we'll use it where appropriate。

 but of course we'll also bear in mind simpler linear models as well。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_87.png)

So just to wrap up the section on treason， we've seen some。

 there's advantage and disadvantages in a sense they're simple if the trees are small。

 not too many terminal notes because they're easy to display and to understand for nonspecs。

And for example， we look back at this heart disease tree， right， the prune one in the bottom right。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_89.png)

A doctor might like history tree because。

![](img/2f3ee3a5a5e528f8f387dbc26701af56_91.png)

It mimics in a sense the way his decision making process might work。

 and I was trying to decide whether a patient has heart disease he might first do initial tests based on thalumium stress tests。

And if they failed that test。Then do a further test based on calcium and decide about heart disease if the test was passed。

 we might again do a calcium test and then fall by some other criteria。

 so you stratify the population in a series of simple rules to try to determine whether a patient is of high or low risk。

 so for that reason it's trees are popular because their simplicity in the fact that they mimic the way some people make decisions。



![](img/2f3ee3a5a5e528f8f387dbc26701af56_93.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_94.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_95.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_96.png)

![](img/2f3ee3a5a5e528f8f387dbc26701af56_97.png)

Ass a series of。Of of splits。And they can display in a simple tree， which means， again。

 they're attractive because there aren't equations to have to understand。

They can also handle qualitative predictors without the need to create dummy variables words some of the categorical variables can be have more than two levels and you can split a categorical variable into two sets of subcategories。

So these are all good things。 The big downside is that the。

They don't predict so well compared to more state of the art methods， and we'll see， for example。

 for the heart data that the prediction accuracy of a tree is not very good compared to other methods。

The other maps that we'll talk about now actually use trees， but an ensemble， they combine trees。

They build many trees on the same data， and then they average or combine them in some way。

 and in the process they improve the predictionary substantially。

