# 斯坦福大学《统计学习导论2023Python版｜An Introduction to Statistical Learning with Python》中英字幕 - P67：-067-Statistical Learning_ 9.2.Support Vector Classifier.zh_en - GPT中英字幕课程资源 - BV1u4421A7ZU

![](img/83eec4165c8f7acbc306c27f13a6b27a_0.png)

Okay， we're going to see how we can extend our maximumimal margin classifier now to deal with situations where you cannot separate the data well。



![](img/83eec4165c8f7acbc306c27f13a6b27a_2.png)

So we'll start off in the case where the data aren't separable at all。

 as we see in this picture over here。Okay， well， all good and well。

 What happens if the data aren't separable？ I mean。

 it's a little bit wishful thinking that that we can always separate the data perfectly with a hyperplane。

So here's a similar picture to what we had before， and in this case， the data aren't separable。

You'll see， you cannot fit a hyperplane through these data and exactly separate them。

 You can try as much as you like。 But， you know， there's maybe an attempt， but no， you always。

 you can just， it's obvious you're always going to get， you're always going to get overlap。

And this is often the case， especially if the number of points is large relative to the dimensions。

On the other hand。For a lot of wide data， like in genomics and other kinds of problems。

The number of sample points is less than the dimensions。

 and in general when the number of sample points is less than the dimensions。

 you can always separate the data with a hyperplane。Okay so but when N's much bigger than P。

 typically not。

![](img/83eec4165c8f7acbc306c27f13a6b27a_4.png)

So that's a problem we need to deal with， Another problem we're going want to deal with is when you have noisy data。

And so I alluded to that earlier。So here， we've got our original data， and it's not too noisy。

 and we get a hyperplane over there。 What happens if we add one more point。

 blue point here it is over year。And now we still want to separate in Hyplane。 Well。

 just the presence of that one extra point means we've had to tilt the hyperplane quite dramatically to still get separation。

So that's a little bit of crazy behavior。 we'd say non robust behavior to the addition of one extra point。

 This point might be an outli， and it's going to have a dramatic effect on the maximal margin classifier。

So we want to be able to deal with those both of these problems。

ThisWhat we call the support vector classifier。Is going to do that。

 And it maximizes what we call a soft margin。 So we're going to relax the idea of。

 of a separate hyperplane。

![](img/83eec4165c8f7acbc306c27f13a6b27a_6.png)

Okay， so here's the idea。 we've got two pictures here， both of them have soft margins。

In the left picture， the data actually are separable。

 but we've made the margin wider than we need to。And so we've got two points on the wrong side of the margins。

Amongst the blue guys， this point here， number 80 is on the wrong side of the margin。This one。Right。

And amongst the pink guys， this guys on the wrong side of the margin。But by getting the margin wider。

We've had to put up with those two so called errors， and so we call this a soft margin。

And the idea is that making the soft margin wider or smaller is a way of kind of regularizing because。

Once you allow some points to be on the wrong side of the margin。

 the margin gets determined by more than just the closest points。In the right plot。

It's essential to have a soft margin because we cannot get a separate in hyperplane。

And so here we have a candidate hyperplane with its margins。

 and we see that theres several points on the wrong side。

 We've got a blue point on the wrong side of its margin over year。 we've got a blue point。

On the wrong side of the decision boundary and on the wrong side of the margin， Likewise。

 there's a move point。On the wrong side of of， of the decision boundary。

 also the wrong side of the margin。So these are called soft margins。

And we need to modify the the formulation of the problem to accommodate it。

So part of the problem is the same， we're going to maximize n subject to the beta summ squares1。

 so that's a unit vector。Now， we want all the points。

 the distance of all the points be bigger than M， but discounted by a discount factor。1 Epsilon I。

 So we allow some slack。 some points needn't be。Exactly bigger than the margin。

 but there can be some slack。And how do we account for all the slackla， we give ourselves a budget。



![](img/83eec4165c8f7acbc306c27f13a6b27a_8.png)

We give ourselves a budget for the total amount of slack， which in this case is C。

So the epsilons tell us how much each point is allowed to be on the wrong side of its margin。

 it's a relative amount relative to the margin。And we give ourselves a number C。

 a total amount of overlap。 And then subject to that。

 we're going to make the margin as wide as possible to get on either side of the margin。Okay， again。

 convict optimization problem we can solve using the SVM packaging in R。



![](img/83eec4165c8f7acbc306c27f13a6b27a_10.png)

C is now tuning parameter， and as we change C， the soft margin is going to get wider or smaller。



![](img/83eec4165c8f7acbc306c27f13a6b27a_12.png)

![](img/83eec4165c8f7acbc306c27f13a6b27a_13.png)

So as I said it's a regularization parameter and so here we've got four scenarios where we've changed C。

 here's the biggest C， and in fact it's the biggest possible C that's needed because now all points on the wrong side of the margin。



![](img/83eec4165c8f7acbc306c27f13a6b27a_15.png)

Okay。And so there's an epsilon for every single point。

So these epsilons you can think of as let's do in this picture over here， you can draw arrows。Which。

 which tells you the distance of each point from the margin。Okay， so there's one for this guy。

And the length of these is proportional to the epsilons， and likewise for these guys。

And as we tighten C， the margin gets tighter because we're allowing less and less overlap。

And so that becomes a tuning parameter。We'll see a little bit later that， in effect。

 the number of points that are on the wrong side of the margin in others with all the points inside the margin or on the wrong side of the margin become。

The effective points that are controlling the orientation of the margin。So in some sense。

 the more points that are involved in the orientation of the margin， the more stable it becomes。

And that means as sea gets bigger， the more stable the margin becomes。

And so there's going to be a kind of a biospherance trait or we change C。

 So's sorry regularization Rob it's had a question actually I mean we're taking at the Euclidean distance in all these pictures does it matter if I standardize the variables first。

 Should I standardize the variables first Oh， that's a good point Yes。

 you're not I think I think you're write Rob。嗯。TheThe sport victim treats all the variables as equals in a way。

 And so the units count't。 So good point。 The variable should be standardized。

If you remember when we did the lassoon and Rige regression， we said that was important there， too。

 Well， the same， for the same reasons， it's important here。



![](img/83eec4165c8f7acbc306c27f13a6b27a_17.png)

Well， so we've come up with a compromise when the points overlap， but in some cases。

 no matter how much we try， that compromise isn't going to help。 And so here's a fake situation。

 but it's a situation where having a soft margin doesn't help。

 You can see we've got the most set of points is exactly in the middle of a crowd of blues on one side and another crowd of blues on the other side。

And no matter what we do， we won't get a good classifier。



![](img/83eec4165c8f7acbc306c27f13a6b27a_19.png)

What we'd like to do is bend the margin and we're going to talk about ways of how we do that in the next segment。

