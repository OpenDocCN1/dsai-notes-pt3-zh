# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P53：P53 StatsLearning Lect10a2 121213.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/793deccf236270c3b58ac75d98e00ae2_0.png)

At any point， once a tree is built， you'd predict the the test observation by passing it down the tree。

 obeying each of the splits。 It'll end up in a terminal node， and then you'll， you'll。



![](img/793deccf236270c3b58ac75d98e00ae2_2.png)

![](img/793deccf236270c3b58ac75d98e00ae2_3.png)

Use the mean of the training observations in that region to make the prediction。



![](img/793deccf236270c3b58ac75d98e00ae2_5.png)

Let's look at a slightly bigger example， a cartooning example in the next slide。



![](img/793deccf236270c3b58ac75d98e00ae2_7.png)

嗯。

![](img/793deccf236270c3b58ac75d98e00ae2_9.png)

First of all， in the slide we show in the left panel here。嗯。



![](img/793deccf236270c3b58ac75d98e00ae2_11.png)

ASe of regions that couldn't be achieved by this process so this one could not be achieved because these aren't boxes that were obtained by sequentially splitting the data repeatedly。

 whereas the one on the right can If you look at the one on the right in conjunction with the tree on the bottom left here you'll see that the first split was made at T1 so there's T1 over there and that was a vertical split。



![](img/793deccf236270c3b58ac75d98e00ae2_13.png)

![](img/793deccf236270c3b58ac75d98e00ae2_14.png)

![](img/793deccf236270c3b58ac75d98e00ae2_15.png)

![](img/793deccf236270c3b58ac75d98e00ae2_16.png)

![](img/793deccf236270c3b58ac75d98e00ae2_17.png)

Right， that。Broke this region。 we've got got two variabless x1 and x2 here into a region to the left and to the right。

 so that's a partition。

![](img/793deccf236270c3b58ac75d98e00ae2_19.png)

![](img/793deccf236270c3b58ac75d98e00ae2_20.png)

Then we have a split on x2 at T2， so that is this split over here where we divided that box into 2。



![](img/793deccf236270c3b58ac75d98e00ae2_22.png)

And so that takes care of the left， we' got region one and region two。



![](img/793deccf236270c3b58ac75d98e00ae2_24.png)

Then on the right hand partition that we had by splitting T1， we split x1 again at T3。

 so we make another vertical split here that partitions。



![](img/793deccf236270c3b58ac75d98e00ae2_26.png)

![](img/793deccf236270c3b58ac75d98e00ae2_27.png)

![](img/793deccf236270c3b58ac75d98e00ae2_28.png)

Stol these in。And so that's split at this internal node over here。



![](img/793deccf236270c3b58ac75d98e00ae2_30.png)

And so that makes region 3 on the left。

![](img/793deccf236270c3b58ac75d98e00ae2_32.png)

And on the right， we're going to do one more split and that's a T4 on variable x2 that divides that into2。

 so you can see in the sequential greedy fashion we've subdivided the space。

 which is just two variables here into five different regions。



![](img/793deccf236270c3b58ac75d98e00ae2_34.png)

![](img/793deccf236270c3b58ac75d98e00ae2_35.png)

![](img/793deccf236270c3b58ac75d98e00ae2_36.png)

Now， at each of the terminal nodes， we are going to approximate。



![](img/793deccf236270c3b58ac75d98e00ae2_38.png)

The regression function in this case by the mean of the training observations that end up in these terminal nodes。



![](img/793deccf236270c3b58ac75d98e00ae2_40.png)

![](img/793deccf236270c3b58ac75d98e00ae2_41.png)

So what that means is if you have a test observation and you want to come and predict it。

 you're going to start at the top and you're going to query what's its value for x1 if it's less than T1 you'll go to the left otherwise you'll go to the right。



![](img/793deccf236270c3b58ac75d98e00ae2_43.png)

![](img/793deccf236270c3b58ac75d98e00ae2_44.png)

Likewise， you answer each of the questions at each of the internal nodes and you're going to end up in one of these regions and then your prediction is going to be the mean in that region。



![](img/793deccf236270c3b58ac75d98e00ae2_46.png)

![](img/793deccf236270c3b58ac75d98e00ae2_47.png)

So as a function， you can actually represent it nicely because it's just a two dimensional function by this picture that we got on the right here。

 and so it's a piecewise constant function。

![](img/793deccf236270c3b58ac75d98e00ae2_49.png)

![](img/793deccf236270c3b58ac75d98e00ae2_50.png)

It's piecewise constant， you can see here the slices。

 let's see this will be this will be T1 is this slice over here and this will be T2 and this function is constant in each of the regions and that's how we're going to represent our function at the end of the day。



![](img/793deccf236270c3b58ac75d98e00ae2_52.png)

![](img/793deccf236270c3b58ac75d98e00ae2_53.png)

![](img/793deccf236270c3b58ac75d98e00ae2_54.png)

![](img/793deccf236270c3b58ac75d98e00ae2_55.png)

Okay， so we've seen how we grow a tree， question one question arises is how large should the tree be？



![](img/793deccf236270c3b58ac75d98e00ae2_57.png)

![](img/793deccf236270c3b58ac75d98e00ae2_58.png)

When we stop growing the tree， well， one possibility would just be to grow as largest trees as possible right？



![](img/793deccf236270c3b58ac75d98e00ae2_60.png)

At the extreme， we could， for example， have a tree that had one observation。

 each terminal node or leaf。

![](img/793deccf236270c3b58ac75d98e00ae2_62.png)

But that's not I could to overfit the data by producing poor test set performance。



![](img/793deccf236270c3b58ac75d98e00ae2_64.png)

I say why well I guess it's kind of obvious right if you have a tree that's so large that each observation has its own terminal node it's going to have training error of zero that it's going to be adapted to that data very much and it's going to overfit when you give it new test data。

 you're probably going to have a quite high high error as a result。

 so not a good idea to build as large a tree as possible。



![](img/793deccf236270c3b58ac75d98e00ae2_66.png)

![](img/793deccf236270c3b58ac75d98e00ae2_67.png)

![](img/793deccf236270c3b58ac75d98e00ae2_68.png)

![](img/793deccf236270c3b58ac75d98e00ae2_69.png)

Another possibility would be to stop early， in other words。嗯。

Just keep splitting until it looks like no split helps in some sense in terms of reducing the residual sum of square is the criterion we saw before。

But it turns out。This strategy can be too short sighted。

 will very often stop too early because it looks like no good split is available。

 but actually if we kept splitting， we'd see a better split farther down the tree。

So it turns out that a better strategy is actually to grow a large tree。Stopping only once a rule。

 like， for example， a typical of one that's used is a terminal node has to have no fewer than five observations。

 say。And then with this large tree， which is probably too big。

 we prune it from the bottom to produce a tree which。Of midsize。

 it tries to balance bias and variance。And hence have lower prediction error than either the single node tree or the extreme tree that has one observation。

One node per observation so a very bushy tree has got high variance in right。

 it's got high variance low overfitting the data no bias but is overfitting and probably not going to predict well。

So actually， so what's done in the cart software， for example， or the Tre library in R。

 which we'll see， is this idea of building a large tree and then pruning it back。



![](img/793deccf236270c3b58ac75d98e00ae2_71.png)

![](img/793deccf236270c3b58ac75d98e00ae2_72.png)

![](img/793deccf236270c3b58ac75d98e00ae2_73.png)

And the framework for that is called cost complexity pruning or weakest link pruning。



![](img/793deccf236270c3b58ac75d98e00ae2_75.png)

So for that， we do something actually very much like the。



![](img/793deccf236270c3b58ac75d98e00ae2_77.png)

The lastso we saw for regression， we have an objective function， which is the fit。



![](img/793deccf236270c3b58ac75d98e00ae2_79.png)

And remember the fit we're going to measure in terms of the sum squares of observations are the response around the assigned terminal nodes。

 so our terminal nodes are R1 through。

![](img/793deccf236270c3b58ac75d98e00ae2_81.png)

![](img/793deccf236270c3b58ac75d98e00ae2_82.png)

RM， I'm say， Rt。The number of term nodes we're going to note by this notation looks like an absolute value。

 but that means the number of terminal nodes in the tree T。



![](img/793deccf236270c3b58ac75d98e00ae2_84.png)

![](img/793deccf236270c3b58ac75d98e00ae2_85.png)

So this is the sum of squares of observationssations around the mean of region M。



![](img/793deccf236270c3b58ac75d98e00ae2_87.png)

Wwhich is one of the terminal nodes and we add them up over all the terminal nodes so we want a tree which has small variants。

 but we also want to counterbalance the size of the tree。

 so we put a penalty on the total number of nodes of the tree with the penalty parameter which will last cross validation again this is very much the lastso where we had a sum of squares of regression and we penalize the sum of the absolute values of the coefficient which is a complexity so we want the coefficients to be small to avoid overfitting here we want the size of the tree to be small to avoid overfitting。



![](img/793deccf236270c3b58ac75d98e00ae2_89.png)

![](img/793deccf236270c3b58ac75d98e00ae2_90.png)

![](img/793deccf236270c3b58ac75d98e00ae2_91.png)

![](img/793deccf236270c3b58ac75d98e00ae2_92.png)

![](img/793deccf236270c3b58ac75d98e00ae2_93.png)

![](img/793deccf236270c3b58ac75d98e00ae2_94.png)

![](img/793deccf236270c3b58ac75d98e00ae2_95.png)

OkaySo cost complexity perruninggan is going kind of find the best value of alpha by cross validation。

 and then we're going to pick the subte。

![](img/793deccf236270c3b58ac75d98e00ae2_97.png)

![](img/793deccf236270c3b58ac75d98e00ae2_98.png)

In the tree， the large tree you've grown that has the smallest value of this criterion。



![](img/793deccf236270c3b58ac75d98e00ae2_100.png)

So summarize in the next slide， well， sorry， this actually just says what I just said。



![](img/793deccf236270c3b58ac75d98e00ae2_102.png)

Again。

![](img/793deccf236270c3b58ac75d98e00ae2_104.png)

Yes， okay so here's the summary of the tree growing algorithm again this is not something that you would normally have to program yourself because software which is available。

 for example CAt or the tree software in R， it does all this cross foundation process for you。

 but it's good to see at least once what it's doing so we build a large tree with a very simple stocking rule again for example。

 the。For example， we stop it when the number of observations in the Truman node is some minimum number like five。

And then we prune the tree to find the the。The best subte。

 and for that we need to get an idea of the cost complexity parameter。

 the best trade off between fit and tree size。So for that。

 we use cross validation in the similar way that we've used it before for regression。

We divide the data into K parts， Kb maybe five or 10。We set aside one part。

 we fit trees of various sizes on the k minus1 parts and then evaluate the prediction error on the part we've left out so it's clear the whole things controlled by alpha in alpha decides how big the tree is and you use cross validation just to pick alpha exactly right and so we choose the alpha and we'll see cross validation curves in a few slides。

 but it's going to tell us a good idea of the best value alpha to trade off the fit with the size of the tree。

Having chosen alpha， we then go back to the full tree and find the subt that has the smallest。

 I mean the tree grown on all the training data， exactly。

So let's see what this looks like for the baseball data。



![](img/793deccf236270c3b58ac75d98e00ae2_106.png)

So。For illustration， we actually took the observation and divided them into a training set of 132 observations in the remainder 131 in a test set。



![](img/793deccf236270c3b58ac75d98e00ae2_108.png)

![](img/793deccf236270c3b58ac75d98e00ae2_109.png)

Is that we want to compare the cross validation error what we're going to get to the test error on the separate test set just for illustration。



![](img/793deccf236270c3b58ac75d98e00ae2_111.png)

We build a regression tree on the training set using cross validation and get an idea of the best cost complexity parameter alpha。



![](img/793deccf236270c3b58ac75d98e00ae2_113.png)

![](img/793deccf236270c3b58ac75d98e00ae2_114.png)

嗯。Using six wall cross validation， and by the way， six may seem like a funny number of bets' because six divides into 132 exactly。



![](img/793deccf236270c3b58ac75d98e00ae2_116.png)

So。

![](img/793deccf236270c3b58ac75d98e00ae2_118.png)

This was the full tree before pruning， so remember we saw the top part of this tree before。

 right we saw the top split。

![](img/793deccf236270c3b58ac75d98e00ae2_120.png)

And the right split。 And this had all been pruned away。

 But now we're seeing the details of how we got to that 3 node tree。

 Here's the the large tree that we get。 The only rule being that。



![](img/793deccf236270c3b58ac75d98e00ae2_122.png)

![](img/793deccf236270c3b58ac75d98e00ae2_123.png)

The size of the we don't split a terminal node that has fewer than say five observations。

 and that gave us this tree with how many nodes， 1，2，3，4，5，6，7，8，9， 10，11，12。



![](img/793deccf236270c3b58ac75d98e00ae2_125.png)

![](img/793deccf236270c3b58ac75d98e00ae2_126.png)

![](img/793deccf236270c3b58ac75d98e00ae2_127.png)

Right but probably not all these are predictive one is some of the arms of the tree long and some short term。

 Good question。

![](img/793deccf236270c3b58ac75d98e00ae2_129.png)

![](img/793deccf236270c3b58ac75d98e00ae2_130.png)

Tell me why it's because the early splits which have caused a big decrease in the summer squares。

 they depicted by long arms and then as we get down deeper。

 the incremental improvements get smaller and smaller so that's depicted in the way the trees drippers into your idea or who thought of that not me it's a good idea So it's whoever the author of the tree growing program in R is so here's all the cross foundation which is going to give us the prune tree so what do we see here we see along the horizontal axis tree size which is the alpha parameter so as a very alpha it's in one to one corresponds with tree size？



![](img/793deccf236270c3b58ac75d98e00ae2_132.png)

![](img/793deccf236270c3b58ac75d98e00ae2_133.png)

![](img/793deccf236270c3b58ac75d98e00ae2_134.png)

![](img/793deccf236270c3b58ac75d98e00ae2_135.png)

![](img/793deccf236270c3b58ac75d98e00ae2_136.png)

![](img/793deccf236270c3b58ac75d98e00ae2_137.png)

![](img/793deccf236270c3b58ac75d98e00ae2_138.png)

If alpha equals zero， there's no penalty to tree size， so we get the largest tree that we fit。

 which was about 12 terminal nodes。

![](img/793deccf236270c3b58ac75d98e00ae2_140.png)

![](img/793deccf236270c3b58ac75d98e00ae2_141.png)

As we crank up alpha to be bigger and bigger， it puts more and more penalty on tree size until eventually we're forced to the left hand side here。

 we have actually just there's just one node， there's no splits at all。



![](img/793deccf236270c3b58ac75d98e00ae2_143.png)

![](img/793deccf236270c3b58ac75d98e00ae2_144.png)

So we're seeing the extreme from the full data set to the 12 terminal node tree。

 and let's look at the green curve as what we get from cross validation and it's minimized at around three terminal nodes。

 okay。

![](img/793deccf236270c3b58ac75d98e00ae2_146.png)

![](img/793deccf236270c3b58ac75d98e00ae2_147.png)

![](img/793deccf236270c3b58ac75d98e00ae2_148.png)

Well， the training error， should has said this first， as we expect。

 this is of course we know that we can't use training error to choose a cost complexity parameter because the more we fit。

 the better it's going to look and we see that here right， the more we fit the lower the air。



![](img/793deccf236270c3b58ac75d98e00ae2_150.png)

![](img/793deccf236270c3b58ac75d98e00ae2_151.png)

![](img/793deccf236270c3b58ac75d98e00ae2_152.png)

So cross validation， the other hand， you fit for a while， it's happy with the splits。

 and then it looks like it's overfitting， just increasing variance and not helping prediction error。



![](img/793deccf236270c3b58ac75d98e00ae2_154.png)

![](img/793deccf236270c3b58ac75d98e00ae2_155.png)

The test error which we can evaluate here because we've set aside a separate test set。



![](img/793deccf236270c3b58ac75d98e00ae2_157.png)

Is it's roughly tracking the CB curve， it's minimized maybe around the same place。



![](img/793deccf236270c3b58ac75d98e00ae2_159.png)

So it looks like about three terminal nodes is good， which was the first tree we showed exactly。

 so it's on the base of this graph that we drew that three node tree。



![](img/793deccf236270c3b58ac75d98e00ae2_161.png)

![](img/793deccf236270c3b58ac75d98e00ae2_162.png)

![](img/793deccf236270c3b58ac75d98e00ae2_163.png)