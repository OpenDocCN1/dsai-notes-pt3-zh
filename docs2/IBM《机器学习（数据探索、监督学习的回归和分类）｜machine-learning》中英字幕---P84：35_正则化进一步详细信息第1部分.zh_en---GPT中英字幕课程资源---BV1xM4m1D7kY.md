# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P84：35_正则化进一步详细信息第1部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

In this video， we're going to go into deeper detail in regards to regular to gain a deeper intuitive understanding of how it works。

So in this section， we'll be covering the details of regularization。



![](img/f415ad0916271c6a084657315c9f3c8b_1.png)

And some different approaches to understanding exactly how regularization works。



![](img/f415ad0916271c6a084657315c9f3c8b_3.png)

So here we'll examine intuitively how regularization works the goal here is to shed additional lights that regularization approaches don't seem as much of a black box。



![](img/f415ad0916271c6a084657315c9f3c8b_5.png)

![](img/f415ad0916271c6a084657315c9f3c8b_6.png)

![](img/f415ad0916271c6a084657315c9f3c8b_7.png)

We're going to go through a few approaches to adding intuition to this process。



![](img/f415ad0916271c6a084657315c9f3c8b_9.png)

First， we're going to go over the analytical view to give a logical review of how we are achieving our goal of reducing complexity。



![](img/f415ad0916271c6a084657315c9f3c8b_11.png)

We'll then go over the geometric view， which will illuminate further the actual optimization problem。

 as well as showing why LASso generally zeros out coefficients and Rich does not。



![](img/f415ad0916271c6a084657315c9f3c8b_13.png)

![](img/f415ad0916271c6a084657315c9f3c8b_14.png)

And then finally， we'll go over the probabilistic view。

 which will show how we can recalibrate our understanding of Lasso and of rich as a bayes problem where our coefficients have particular prior distributions。



![](img/f415ad0916271c6a084657315c9f3c8b_16.png)

![](img/f415ad0916271c6a084657315c9f3c8b_17.png)

![](img/f415ad0916271c6a084657315c9f3c8b_18.png)

So let's start off with the analytic view。

![](img/f415ad0916271c6a084657315c9f3c8b_20.png)

The analytic view is going to present the obvious， as we incur L2 and L1 penalties。

 we force our coefficients to be smaller， thus restricting their plausible range。



![](img/f415ad0916271c6a084657315c9f3c8b_22.png)

![](img/f415ad0916271c6a084657315c9f3c8b_23.png)

Think a smaller range for coefficients must imply a simpler model with lower variance than a model with an infinite possible coefficient range。



![](img/f415ad0916271c6a084657315c9f3c8b_25.png)

![](img/f415ad0916271c6a084657315c9f3c8b_26.png)

Think when we eliminate features， this is clear how we're quickly eliminating that variance as we can just think of the difference between the possible solutions that are available for y as a function of X。



![](img/f415ad0916271c6a084657315c9f3c8b_28.png)

![](img/f415ad0916271c6a084657315c9f3c8b_29.png)

Versus as a function of x and x squared。

![](img/f415ad0916271c6a084657315c9f3c8b_31.png)

In regards to just shrinking coefficients， so not necessarily eliminating coefficients。

 we can think about how much that y variable actually changes in response to a feature。



![](img/f415ad0916271c6a084657315c9f3c8b_33.png)

So if the coefficient is close to zero。That is essentially saying that that feature has almost no effect。



![](img/f415ad0916271c6a084657315c9f3c8b_35.png)

Whereas if the coefficient is large， a small change in that feature will have a large impact on our outcome variable。



![](img/f415ad0916271c6a084657315c9f3c8b_37.png)

![](img/f415ad0916271c6a084657315c9f3c8b_38.png)

Thus， it will be higher sensitivity to a change in that feature and thus a higher variance in that underlying model。



![](img/f415ad0916271c6a084657315c9f3c8b_40.png)

Now let's discuss the geometric view。So first we're going to go over the actual optimization problem and then slightly reframe them so we can understand it from this geometric standpoint。



![](img/f415ad0916271c6a084657315c9f3c8b_42.png)

So for Ridge we're trying to minimize the error that we see here in that curly brackets。

 which is just the normal OLS optimization problem that sum of squared residuals that we're trying to minimize。

 but it's going to be subject to our coefficients being as small as possible。



![](img/f415ad0916271c6a084657315c9f3c8b_44.png)

![](img/f415ad0916271c6a084657315c9f3c8b_45.png)

![](img/f415ad0916271c6a084657315c9f3c8b_46.png)

![](img/f415ad0916271c6a084657315c9f3c8b_47.png)

And no matter what solution we come up with， those coefficients。

 those coefficients squared in this case will end up being equal to some value。

 and here we're setting that value to S， so we want to subject it to a value lesson or equal to S so we're minimizing that and once we do that beta squared is going to be equal to some value。

 and this will become clear as we get into the geometric graph。



![](img/f415ad0916271c6a084657315c9f3c8b_49.png)

![](img/f415ad0916271c6a084657315c9f3c8b_50.png)

And then the same is going to hold true for Laso， just this time we're minimizing our error subject to the absolute value of our coefficients being less than this value S。



![](img/f415ad0916271c6a084657315c9f3c8b_52.png)

![](img/f415ad0916271c6a084657315c9f3c8b_53.png)

So with this formulation of breaking down the cost function。

 the optimal solution will have to be found at the intersection of that penalty boundary。

 which is just the penalty that we get for each one of our coefficients。

 whether that's beta squared or the absolute value of the different betas。



![](img/f415ad0916271c6a084657315c9f3c8b_55.png)

![](img/f415ad0916271c6a084657315c9f3c8b_56.png)

![](img/f415ad0916271c6a084657315c9f3c8b_57.png)

As well as the contour of the traditional OLS Co function。



![](img/f415ad0916271c6a084657315c9f3c8b_59.png)

So we see that here that we have the different contours。

 the red lines being the cost of the OLS function and the diamond or the circle representing the penalty for ridge versus Lasso。



![](img/f415ad0916271c6a084657315c9f3c8b_61.png)

![](img/f415ad0916271c6a084657315c9f3c8b_62.png)

And the geometry of this will reveal why this selection of Lasso will tend to zero out certain coefficients。

 and let's go into a bit of detail here so when we look at the graph。



![](img/f415ad0916271c6a084657315c9f3c8b_64.png)

![](img/f415ad0916271c6a084657315c9f3c8b_65.png)

![](img/f415ad0916271c6a084657315c9f3c8b_66.png)

We see that the possible coefficients for beta 1 and beta 2 that can solve our optimization problem。



![](img/f415ad0916271c6a084657315c9f3c8b_68.png)

When we see these red lines。

![](img/f415ad0916271c6a084657315c9f3c8b_70.png)

Those are supposed to represent the set of solutions that would have the same error on our traditional OLS cost function。

 so if we weren't constrained by Lasso or riddge， the optimal solution would be that beta in the middle。



![](img/f415ad0916271c6a084657315c9f3c8b_72.png)

![](img/f415ad0916271c6a084657315c9f3c8b_73.png)

But each one of those outer rings are going to be a set of different betaovs that would all end up producing the same error on our classic OLS function。

 so think for every value on that inner ring that would lead to a squared error of 10 in that second ring。

 all those values of beta would produce a value of or an error of 20 and so on。



![](img/f415ad0916271c6a084657315c9f3c8b_75.png)

![](img/f415ad0916271c6a084657315c9f3c8b_76.png)

![](img/f415ad0916271c6a084657315c9f3c8b_77.png)

![](img/f415ad0916271c6a084657315c9f3c8b_78.png)

On the other hand， no matter what betas we choose on that ring。

 we now also have the associated regularization term that we have to deal with as well within our cost function。

 so we want to ensure that since every point on that ring has the same error for traditional OLS we want to ensure that we choose the point that will also minimize our regularization terms so this is the idea why they will have to intersect in the first place because no matter where we choose on that ring。

 we will automatically have the associated beta 1 and beta 2 which is just going to be our penalty。



![](img/f415ad0916271c6a084657315c9f3c8b_80.png)

![](img/f415ad0916271c6a084657315c9f3c8b_81.png)

![](img/f415ad0916271c6a084657315c9f3c8b_82.png)

![](img/f415ad0916271c6a084657315c9f3c8b_83.png)

![](img/f415ad0916271c6a084657315c9f3c8b_84.png)

![](img/f415ad0916271c6a084657315c9f3c8b_85.png)

So no matter what values of beta we choose， there will be that additional associated costs for Laso that was the absolute value of beta 1 and the absolute value of beta 2 sums。



![](img/f415ad0916271c6a084657315c9f3c8b_87.png)

![](img/f415ad0916271c6a084657315c9f3c8b_88.png)

And looking at Laso， we see that if that value is equal to one。

 let's say whatever that penalty is of absolute value of beta 1 an absolute value of beta 2。



![](img/f415ad0916271c6a084657315c9f3c8b_90.png)

![](img/f415ad0916271c6a084657315c9f3c8b_91.png)

We will end up with a diamond which represents all the values for beta 1 and beta 2。

 for which that value， that sum of absolute values is equal to1。

 so if we look all the way on the right hand corner。



![](img/f415ad0916271c6a084657315c9f3c8b_93.png)

![](img/f415ad0916271c6a084657315c9f3c8b_94.png)

Then we have beta 1 is equal to 1 and beta 2 is equal to zero。



![](img/f415ad0916271c6a084657315c9f3c8b_96.png)

At that top corner， we have beta 2 equal to 1 and beta 1 equal to0 and when you add those together those will both equal to1。

 and in the middle you'll create a straight line leading from that 10 to 01 where you'd have something like 0。

5 plus 0。5 or 0。25 plus 0。75 for beta 1 and beta 2， all those equal to 1。



![](img/f415ad0916271c6a084657315c9f3c8b_98.png)

![](img/f415ad0916271c6a084657315c9f3c8b_99.png)

So all those terms are equal to the same value， and when you plot that out。

 you end up with this diamond。

![](img/f415ad0916271c6a084657315c9f3c8b_101.png)

And this diamonds on the Lasso side。

![](img/f415ad0916271c6a084657315c9f3c8b_103.png)

For to intersect with that contour it is and for us to minimize that value。

 it will have to hit one of those edges unless that contour is directly parallel to our function。

 it will have to hit one of those edges and each one of those edges。



![](img/f415ad0916271c6a084657315c9f3c8b_105.png)

![](img/f415ad0916271c6a084657315c9f3c8b_106.png)

![](img/f415ad0916271c6a084657315c9f3c8b_107.png)

Means that we are zeroing out one of our coefficients。

 and this follows for a higher dimensions as well。

![](img/f415ad0916271c6a084657315c9f3c8b_109.png)

And then when we look at the Rige regression。

![](img/f415ad0916271c6a084657315c9f3c8b_111.png)

That intersection can happen at any point because for the beta 1 squared plus beta 2 squared to be equal to1。

 we don't have this diamond， this pointy diamond， but rather we have a circle。



![](img/f415ad0916271c6a084657315c9f3c8b_113.png)

![](img/f415ad0916271c6a084657315c9f3c8b_114.png)

To finds the values everything on that outer circle is equal to one。

 and therefore it will be equally likely to hit any point on that circle given our contour。



![](img/f415ad0916271c6a084657315c9f3c8b_116.png)

![](img/f415ad0916271c6a084657315c9f3c8b_117.png)

So that's why we will just be minimizing values by using griddge by actually eliminating values when we use LASA。



![](img/f415ad0916271c6a084657315c9f3c8b_119.png)

![](img/f415ad0916271c6a084657315c9f3c8b_120.png)