# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P61：-061-Statistical Learning_ 8.3 Classification Trees.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_0.png)

Okay， well， so far we've been talking about regression trees。

 the response was quantitative salaries in this case of baseball players。

Oftentimes trees are used when the response is a categorical variable and so then we call those classification trees。

 but you'll see the technologies is very similar and we just have to change the essentially the loss function and how we measure good performance。

 so let's see how that goes。So。We're going to predict in a classification tree each observation belonging to the most commonly occurring class。

 so that's what's going to happen in the terminal node of the tree instead of just giving the prediction being the mean。

 we're going to classify to the most common class。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_2.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_3.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_4.png)

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

And it's a kind of variance measure across the classes， so you've got K classes， capital K classes。

 often K is two， but not necessarily。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_6.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_7.png)

And this for those who know the binomial distribution。

 this is each of the terms there is like a binomial variance and in fact for the multinomial。

 this is the diagonal of these on the diagonal of the covariance matrix。

 so this is a measure of total variability， in that region。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_9.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_10.png)

And if the genome index is really small， what that means is。

Pretty much one class is is favored and all the rest are really small。

 whereas as an extreme case travel writer， if the region is pures， it's all one class。

 then one of those be hat will be one， the rest will be 0 and G will be 0。 That's a good。

 that's a good point。 And， and on the other hand， if。

 I guess if they all equally distributed in the classes， this G index will be maximum。

AndBut moves it changes in a smooth way。So that's one of the criteria that are very popular。嗯。

And it's also known as a purity index。 that measures the purity of the class。

An alternative is the deviance or cross entropy and this is based on the binomial log likelihoodlude or the multinomial log likelihoodlude and it's a measure that's。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_12.png)

Phas rather similarly to the Gni index。 and either of these are used and give very similar results。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_14.png)

So let's look at an example， wherell look at the heart data。

These later have a binary response called HD， there's 303 patients。

 and they're all represented with chest pains。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_16.png)

So the outcome has a value yes， indicates the presence of heart disease based on an angiographic test while no means no heart disease。

For these data there are 13 predictors， amongst them age， sex， cholesterol。

 and other heart and lung function measurements。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_18.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_19.png)

And so we ran the tree growing process with cross validation and we see what we get in the next figure。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_21.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_22.png)

At the top。You see the full tree grown to all the data， and you can see it's quite a bushy tree。

With an early split on T， it's actually it's E thalium stress test， ahelium stress test， okay？



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_24.png)

And then the two the left and right nodes were split on CA calcium， I think。

 which is calcium and then the subsequent splits， it's hard to see but these pictures are in the book。

 so quite a bushy tree。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_26.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_27.png)

And you see at the terminal nodes of this tree that the classificationifications know or yes。

So that means an observation that， for example， ended up in this leftmost terminal noddia。

 the majority in that class were nos， no heart disease。

 and so the classification produced would be a no。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_29.png)

Whereas the right hand one year is a yes。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_31.png)

Interesting。This terminal node has two nodes。So if they both predicted no why was the e splitlitier tool。

 well it must mean that one of these nodes is purer than the other。

 so even though they were both ended up having a majority of nodes。

 the one node was purer than the other node and the GI index would identify such a node。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_33.png)

So this tree is probably too bushy and so once again cross validation was used and again we see in the right hand panel the results of cross validation。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_35.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_36.png)

And we see。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_38.png)

The training error， the test error and the validation error。

Here we've actually looked at the training error averaged over each of the cross validation folds。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_40.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_41.png)

Which is why it's a little jumpy。And actually even increases in one point。

 in because the trees and the architecture of the trees are different in each of the folds。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_43.png)

The cross validation and test error we had a left our test set here as well。

 those curves look pretty much the same and we end up seeing that a tree size of around about six tends to do well these bars on these cross validation and test curves are standard error bars so there's quite a bit of variability here the data set's not that big。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_45.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_46.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_47.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_48.png)

And on the right here we see the prune back tree that's pruned back to size6。

 of course the prunian was again governed by the cost complexity parameter alpha。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_50.png)

And this year will be a subtree of the big tree grown。

 and that gave the best classification performance。

 which is estimated to be around about 25% error in this case。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_52.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_53.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_54.png)

In this figure。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_56.png)

We show we compare trees with linear models， trees aren't always the right thing to do。

 and so to contrast that， we look at two different scenarios。

In these cartoons here the truth is indicated by these two colors in this top left panel。

 the truth is actually best depicted by a linear model so the decision boundary in this case between the two classes is best in by a line and in this case a tree is not going to do very well we see a trees attempt to partition this space。

And you know while it does a valiant job， it just doesn't do well enough because it's confined to pick boxy regions right so there'd be a split over here。

 a split over there， and then this region was subdivided。

 then that region was subdivided in an attempt to get at this linear decision boundary。

 so this would be classified as as beige， this would be classified as green， beige。

 green and so on in a steppy fashion。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_58.png)

On the other end， in the lower， in the lower two panels， the， the optimal region is。

A blocky kind of partition region。And here， a linear model is not going to do well In the left panel。

 we see the best linear approximation to this decision boundary。

 and it's going to make lots of errors because。You know， with a one single linear boundary。

 it's hard to approximate a rectangular region like this。 And， of course， in this one。

 a tree will nail it。 So itll with two splits， it can get the decision boundary perfectly。

So some problems are more naturallyly suited to trees， some problems aren't。

 and so the idea is we're going to think of trees as one tool in our toolbox and we'll use it where appropriate。

 but of course we'll also bear in mind simpler linear models as well。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_60.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_61.png)

So just to wrap up the section on treason， we've seen some。

 there's advantage and disadvantages in a sense they're simple if the trees are small。

 not too many terminal notes because they're easy to display and to understand for nonspecs。

And for example， we look back at this heart disease tree， right， the prune one in the bottom right。

A doctor might like history tree because。It mimics in a sense the way his decision making process might work。

 and I was trying to decide whether a patient has heart disease he might first do initial tests based on thalumium stress tests。

And if they failed that test。

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_63.png)

Then do a further test based on calcium and decide about heart disease if the test was passed。

 we might again do a calcium test and then fall by some other criteria。

 so you stratify the population in a series of simple rules to try to determine whether a patient is of high or low risk。

 so for that reason it's trees are popular because their simplicity in the fact that they mimic the way some people make decisions。



![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_65.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_66.png)

![](img/d0ad1cc0bea2fd71dbdbe381c0629c5b_67.png)

Ass a series of。Of of splits。And they can display in a simple tree， which means， again。

 they're attractive because there aren't equations to have to understand。

They can also handle qualitative predictors without the need to create dummy variables words some of the categorical variables can be have more than two levels and you can split a categorical variable into two sets of subcategories。

So these are all good things。 The big downside is that the。

They don't predict so well compared to more state of the art methods， and we'll see， for example。

 for the heart data that the prediction accuracy of a tree is not very good compared to other methods。

The other maps that we'll talk about now actually use trees， but an ensemble， they combine trees。

They build many trees on the same data， and then they average or combine them in some way。

 and in the process they improve the predictionary substantially。

