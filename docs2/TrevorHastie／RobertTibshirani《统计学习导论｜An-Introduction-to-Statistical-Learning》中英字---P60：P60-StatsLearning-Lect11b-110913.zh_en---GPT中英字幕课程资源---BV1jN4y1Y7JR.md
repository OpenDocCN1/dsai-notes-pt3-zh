# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P60：P60 StatsLearning Lect11b 110913.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/d413d0ab24c116230d043b42bcc26a8a_0.png)

Okay， we're going to see how we can extend our maximumimal margin classifier now to deal with situations where you cannot separate the data well。



![](img/d413d0ab24c116230d043b42bcc26a8a_2.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_3.png)

So we'll start off in the case where the data aren't separable at all。

 as we see in this picture over here。

![](img/d413d0ab24c116230d043b42bcc26a8a_5.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_6.png)

Okay， well， all good and well， what happens if the data aren't separable， I mean。

 it's a little bit wishful thinking that we can always separate the data perfectly with a hyperplane。



![](img/d413d0ab24c116230d043b42bcc26a8a_8.png)

So here's a similar picture to what we had before， and in this case the data aren't separable。



![](img/d413d0ab24c116230d043b42bcc26a8a_10.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_11.png)

You see， you cannot fit a hyperplane through these data。And exactly separate them。

 You can try as much as you like。 But， you know， there's maybe an attempt， but no， youre always。

 you can just， it's obvious you're always going to get， you're always going to get overlap。



![](img/d413d0ab24c116230d043b42bcc26a8a_13.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_14.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_15.png)

And this is often the case， especially if the number of points is large relative to the dimensions。



![](img/d413d0ab24c116230d043b42bcc26a8a_17.png)

On the other hand。For a lot of wide data， like in genomics and other kinds of problems。



![](img/d413d0ab24c116230d043b42bcc26a8a_19.png)

The number of sample points is less than the dimensions。

 and in general when the number of sample points is less than the dimensions you can always separate the data with a hyperplane。



![](img/d413d0ab24c116230d043b42bcc26a8a_21.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_22.png)

Okay so but when N's much bigger than P， typically not。



![](img/d413d0ab24c116230d043b42bcc26a8a_24.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_25.png)

So that's a problem we need to deal with， another problem we're going want to deal with is when you have noisy data。



![](img/d413d0ab24c116230d043b42bcc26a8a_27.png)

And so I alluded to that earlier。

![](img/d413d0ab24c116230d043b42bcc26a8a_29.png)

So here we've got our original data and it's not too noisy and we get a hyperplane over there。

 What happens if we add one more point， blue point here it is over year？



![](img/d413d0ab24c116230d043b42bcc26a8a_31.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_32.png)

And now we still want to separate in Hyplane。 Well。

 just the presence of that one extra point means we've had to tilt the hyperplane quite dramatically to still get separation。



![](img/d413d0ab24c116230d043b42bcc26a8a_34.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_35.png)

So that's a little bit of crazy behavior， we'd say non robustbu behavior to the addition of one extra point。

 This point might be an outli and it's going to have a dramatic effect on the maximal margin classifier。



![](img/d413d0ab24c116230d043b42bcc26a8a_37.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_38.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_39.png)

So we want to be able to deal with those both of these problems。



![](img/d413d0ab24c116230d043b42bcc26a8a_41.png)

The what we call the support vector classifier。

![](img/d413d0ab24c116230d043b42bcc26a8a_43.png)

Is going to do that， and it maximizes what we call a soft margin。

 So we're going to relax the idea of a separate hyperplane。



![](img/d413d0ab24c116230d043b42bcc26a8a_45.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_46.png)

Okay， so here's the idea。 We've got two pictures here。 both of them have soft margins。



![](img/d413d0ab24c116230d043b42bcc26a8a_48.png)

In the left picture， the data actually are separable。

 but we've made the margin wider than we need to。

![](img/d413d0ab24c116230d043b42bcc26a8a_50.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_51.png)

And so we've got two points on the wrong side of the margins。Amongst the blue guys。

 this point here number 80 is on the wrong side of the margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_53.png)

This one。Right。And amongst the pink guys， this guy's on the wrong side of the margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_55.png)

But by getting the margin wider。

![](img/d413d0ab24c116230d043b42bcc26a8a_57.png)

We've had to put up with those two so called errors， and so we call this a soft margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_59.png)

And the idea is that making a soft margin wider or smaller is a way of kind of regularizing because。



![](img/d413d0ab24c116230d043b42bcc26a8a_61.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_62.png)

Once you allow some points to be on the wrong side of the margin。

 the margin gets determined by more than just the closest points。



![](img/d413d0ab24c116230d043b42bcc26a8a_64.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_65.png)

In the right plot。It's essential to have a soft margin because we cannot get a separate in hyperplane。



![](img/d413d0ab24c116230d043b42bcc26a8a_67.png)

And so here we have a candidate hyperplane with its margins and we see that there's several points on the wrong side。

 we've got a blue point on the wrong side of its margin over year， we've got a blue point。



![](img/d413d0ab24c116230d043b42bcc26a8a_69.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_70.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_71.png)

On the wrong side of the decision boundary and on the wrong side of the margin， Likewise。

 there's a move point。

![](img/d413d0ab24c116230d043b42bcc26a8a_73.png)

On the wrong side of of of the decision boundary， also the wrong side of the margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_75.png)

So these are called soft margins。

![](img/d413d0ab24c116230d043b42bcc26a8a_77.png)

And we need to modify the formulation of the problem to accommodate it。



![](img/d413d0ab24c116230d043b42bcc26a8a_79.png)

So part of the problem is same， we're going to maximize n subject to the beta summ squares1。

 so that's a unit vector。

![](img/d413d0ab24c116230d043b42bcc26a8a_81.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_82.png)

Now we want all the points， the distance of all the points be bigger than M。

 but discounted by a discount factor。

![](img/d413d0ab24c116230d043b42bcc26a8a_84.png)

1 Epson I。 So we allow some slack。 some points needn't be。



![](img/d413d0ab24c116230d043b42bcc26a8a_86.png)

Exactly bigger than the margin， but there can be some slack。



![](img/d413d0ab24c116230d043b42bcc26a8a_88.png)

And how do we account for all the slackla， we give ourselves a budget。



![](img/d413d0ab24c116230d043b42bcc26a8a_90.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_91.png)

Yeah。We give ourselves a budget for the total amount of slack， which in this case is C。



![](img/d413d0ab24c116230d043b42bcc26a8a_93.png)

So the epsilon tell us how much each point is allowed to be on the wrong side of its margin。

 it's a relative amount relative to the margin。

![](img/d413d0ab24c116230d043b42bcc26a8a_95.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_96.png)

And we give ourselves a number C， a total amount of overlap， and then subject to that。

 we're going to make the margin as wide as possible to get on either side of the margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_98.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_99.png)

Okay， again， convict optimization problem we can solve using the SVM package in R。



![](img/d413d0ab24c116230d043b42bcc26a8a_101.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_102.png)

C is now tu in parameter， and as we change C， the soft margin is going to get wider or smaller。



![](img/d413d0ab24c116230d043b42bcc26a8a_104.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_105.png)

So as I said， it's a regularization parameter。 and so here we've got four scenarios where we've changed C。

 here's the biggest C and in fact it's the biggest。



![](img/d413d0ab24c116230d043b42bcc26a8a_107.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_108.png)

A possible C that's needed because now all points on the wrong side of the margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_110.png)

Okay。And so there's an epsilon for every single point。



![](img/d413d0ab24c116230d043b42bcc26a8a_112.png)

So these epsilons you can think of as let's do in this picture over here， you can draw arrows。



![](img/d413d0ab24c116230d043b42bcc26a8a_114.png)

Which， which tells you the distance of each point from the margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_116.png)

Okay， so there's one for this guy。And the length of these is proportional to the epsilons。

 and likewise for these guys。

![](img/d413d0ab24c116230d043b42bcc26a8a_118.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_119.png)

And as we tighten C， the margin gets tighter because were allowing less and less overlap。

 and so that becomes a tuning parameter。

![](img/d413d0ab24c116230d043b42bcc26a8a_121.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_122.png)

We'll see a little bit later that， in effect， the number of points that are on the wrong side of the margin in others with all the points inside the margin or on the wrong side of the margin become。



![](img/d413d0ab24c116230d043b42bcc26a8a_124.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_125.png)

The effective points that are controlling the orientation of the margin。



![](img/d413d0ab24c116230d043b42bcc26a8a_127.png)

So in some sense， the more points that are involved in the orientation of the margin。

 the more stable it becomes。

![](img/d413d0ab24c116230d043b42bcc26a8a_129.png)

And that means as C gets bigger， the more stable the margin becomes。



![](img/d413d0ab24c116230d043b42bcc26a8a_131.png)

And so there is going to be a kind of a biospherance trait off as we change C so's read sorry regularization permit Rob it's had a question actually thinking I mean we're taking at the Euclidean distance in all these pictures does it matter if I standardize the variables first should I standardize the variables first Oh that's a good point Yes you're not I think I think you're right Rob。



![](img/d413d0ab24c116230d043b42bcc26a8a_133.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_134.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_135.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_136.png)

The sport victim treats all the variables as equals in a way， and so the units count't。

 So good point， the variable should be standardized。



![](img/d413d0ab24c116230d043b42bcc26a8a_138.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_139.png)

If you remember when we did the lasux and Rige regression， we said that was important there too。

 Well， the same for the same reasons， it's important here。



![](img/d413d0ab24c116230d043b42bcc26a8a_141.png)

![](img/d413d0ab24c116230d043b42bcc26a8a_142.png)

Well， so we've come up with a compromise when the points overlap。

 but in some cases no matter how much we try that compromise isn't going to help and so here's a fake situation but it's a situation where having a soft margin doesn't help you can see we've got the most set of points is exactly in the middle of a crowd of blues on one side and another crowd of blues on the other side。

And no matter what we do， we won't get a good classifier。

What we'd like to do is bend the margin and we're going to talk about ways of how we do that in the next segment。

