# 杜克大学《数据科学数学技能｜Data Science Math Skills》中英字幕 - P13：13_02_03_笛卡尔平面距离公式 - GPT中英字幕课程资源 - BV12mv6BLEhC

![](img/91eb6c86674174f61a9192878908bcb6_0.png)

Welcome back everyone Our video today is called Disance in the plane and I'm going to talk about three things The first thing I'm going to do is I'm either going to tell you for the first time will remind you about the distance formula that computes the distance between two points in the Carteian plane we're both going to remind ourselves why the formula is what it is and we'll work a few examples。



![](img/91eb6c86674174f61a9192878908bcb6_2.png)

![](img/91eb6c86674174f61a9192878908bcb6_3.png)

![](img/91eb6c86674174f61a9192878908bcb6_4.png)

AndThen we'll immediately show you some stuff which is almost certainly not familiar to you。

 but as new data science concepts， which is the idea that as long as you just have a notion of distance between points in the plane。

 you can talk about nearest neighbors that turns out to be very， very important for machine learning。

 which you'll see in later datacience courses and then we can also talk about clustering that's also very very important for machine learning and later data science courses In fact。

 just to use words that you'll see later， nearest neighbors is one of the main methods in supervised learning and clustering is one of the main methods in unsupervised learning that's really fancy let's start really simple。



![](img/91eb6c86674174f61a9192878908bcb6_6.png)

![](img/91eb6c86674174f61a9192878908bcb6_7.png)

![](img/91eb6c86674174f61a9192878908bcb6_8.png)

![](img/91eb6c86674174f61a9192878908bcb6_9.png)

![](img/91eb6c86674174f61a9192878908bcb6_10.png)

![](img/91eb6c86674174f61a9192878908bcb6_11.png)

![](img/91eb6c86674174f61a9192878908bcb6_12.png)

Before we even draw the Cartesian plane， let me remind you of something that you probably saw in high school。

 maybe in middle school depends where you took it， which is the idea of the pythagorean theorem。



![](img/91eb6c86674174f61a9192878908bcb6_14.png)

![](img/91eb6c86674174f61a9192878908bcb6_15.png)

So suppose I draw a right triangle。So that means a triangle where one of the angles is the right angle。



![](img/91eb6c86674174f61a9192878908bcb6_17.png)

Alway as close to a right angle as I can do without having a straight edge。AndMy little waycom here。

 so there's that。Suppose this side length here is x， this side length here is y。

 and this side length here is z， where this is hypotenuse。What the Pythagorean theorem tells us。



![](img/91eb6c86674174f61a9192878908bcb6_19.png)

Pythagorean0。Going back to Pythagoras， on to Wikipedia him and find out his amazing life。



![](img/91eb6c86674174f61a9192878908bcb6_21.png)

Tells us that z squared root the square of the length hypothesistenus is equal to x squared plus y squared。



![](img/91eb6c86674174f61a9192878908bcb6_23.png)

Now that's just one of the things that's true， you can look up proofs of it。

 which is the same thing as writing the Z as the square root of x square plus y squared。



![](img/91eb6c86674174f61a9192878908bcb6_25.png)

![](img/91eb6c86674174f61a9192878908bcb6_26.png)

That's really what makes the distance formula tick。

Let's see what I mean by the distance formula a So we're going to start abstract。



![](img/91eb6c86674174f61a9192878908bcb6_28.png)

And then I we'm going to give you some examples。So as I give you two points in the point。

There's the point A， equal to A B。And here's the point C。Z骨C。

And let me draw the line segment between them。ぱ。We want to ask the question， how far apart are CD？

What the distance formula says。

![](img/91eb6c86674174f61a9192878908bcb6_30.png)

Is that the distance disk from A to C？

![](img/91eb6c86674174f61a9192878908bcb6_32.png)

Is the square root of the difference in the x values c minus a squared？



![](img/91eb6c86674174f61a9192878908bcb6_34.png)

Plus， the square of the difference in the y values plus d minus b squared。

 Y on earth would that be true？

![](img/91eb6c86674174f61a9192878908bcb6_36.png)

Well， let's draw a right triangle。 Let's take this here， and let's draw a dotted line。

Bad dotted line there。

![](img/91eb6c86674174f61a9192878908bcb6_38.png)

And if you paid attention during the points in the plain lecture。

 you can convince yourself of the coordinates of this point here。 Let's see。

 it has the same Y coordinate as a， and it has the same X coordinate as C。 So the points there。

 that is， in fact， C。

![](img/91eb6c86674174f61a9192878908bcb6_40.png)

![](img/91eb6c86674174f61a9192878908bcb6_41.png)

![](img/91eb6c86674174f61a9192878908bcb6_42.png)

Com乐比。Therefore， the length of this。

![](img/91eb6c86674174f61a9192878908bcb6_44.png)

Is。B is c minus a。

![](img/91eb6c86674174f61a9192878908bcb6_46.png)

And the length of this is d minus B。So we have a right triangle with side length C minus A and D minus B。



![](img/91eb6c86674174f61a9192878908bcb6_48.png)

Therefore， the length of this hypotenuse， once this hypotenuse， of course， is the distance。



![](img/91eb6c86674174f61a9192878908bcb6_50.png)

Between A and C。

![](img/91eb6c86674174f61a9192878908bcb6_52.png)

Thiss given by this formula down here。So if you didn't understand that that's okay。

 you can also just memorize this formula， but often people like to know why a formula is true so they can derive it later in a pinch or really just understand it。



![](img/91eb6c86674174f61a9192878908bcb6_54.png)

![](img/91eb6c86674174f61a9192878908bcb6_55.png)

Okay， let's work some examples。

![](img/91eb6c86674174f61a9192878908bcb6_57.png)

So I'm going to give you a whole bunch of points to the plane and we'll give you distance between a bunch of them。

So let's start with the point A is 11。That谁。And let's take the point B way up here not related to scale。

It's 5，4。And let's start by computing the distance between A and B。

 so let's do that over here in our scratch paper。The distance。Between A and B。

Just very distance from them， let's going to be the square root。

Of the difference in the x value is squared， so 5 minus1 squared。Plus 4 minus-1 squared。

 and now we have to do a little bit ofrithmetic。 So that's the square root of four squared plus3 squared。

Which is equal to the square root of 16 plus 9 just a square root of 25。

 which magically works to be a whole number is 5。

![](img/91eb6c86674174f61a9192878908bcb6_59.png)

![](img/91eb6c86674174f61a9192878908bcb6_60.png)

Electronic hands up if you think I rigged that to make that a nice whole number just to get us off to a gentle start。



![](img/91eb6c86674174f61a9192878908bcb6_62.png)

So that means that the length of this line between A and B is tro in。



![](img/91eb6c86674174f61a9192878908bcb6_64.png)

The length of that line is5。 It's five units to part that way， which is interesting， right。

 because it's not true that you need to go five units in the x direction to get from A to B or five units in the y direction。

 but you do need to go five units to get from A to B。 They're fairly far away。 All right。

 let's also draw the origin。

![](img/91eb6c86674174f61a9192878908bcb6_66.png)

![](img/91eb6c86674174f61a9192878908bcb6_67.png)

![](img/91eb6c86674174f61a9192878908bcb6_68.png)

![](img/91eb6c86674174f61a9192878908bcb6_69.png)

This is the point big O is 00。And let's compute the distance。



![](img/91eb6c86674174f61a9192878908bcb6_71.png)

Between a and the origin。

![](img/91eb6c86674174f61a9192878908bcb6_73.png)

Sequ equal to the square root。So at the distance between the x values， so 1 minus0 squared。



![](img/91eb6c86674174f61a9192878908bcb6_75.png)

Plus 1 minus0 squared。 Let's stop for a second， by the way。

 and point out that1 minus0 squared is the same thing as 0 minus1 squared。

 That is it doesn't matter whether you do the x value of a minus the x value of O or the x value of o minus x value of a。

 which makes sense because the distance from a to0 should be the same as distance from O to a should be symmetric。

 So if we work this out， this is just the squared if  Q。



![](img/91eb6c86674174f61a9192878908bcb6_77.png)

![](img/91eb6c86674174f61a9192878908bcb6_78.png)

![](img/91eb6c86674174f61a9192878908bcb6_79.png)

![](img/91eb6c86674174f61a9192878908bcb6_80.png)

![](img/91eb6c86674174f61a9192878908bcb6_81.png)

In other words， for the fans of the Pthagorean Theorem。That length there is square root of2。

 There's a right triangle。 Okay， let's do one more point。 Let's look at B。



![](img/91eb6c86674174f61a9192878908bcb6_83.png)

![](img/91eb6c86674174f61a9192878908bcb6_84.png)

Equals1，3 has。So the distance of that line。

![](img/91eb6c86674174f61a9192878908bcb6_86.png)

Now here you don't really need a fancy form though。

 you notice the only difference between them is in the x values。

 it's pretty clear the distance between A and B is just three hals minus1。



![](img/91eb6c86674174f61a9192878908bcb6_88.png)

![](img/91eb6c86674174f61a9192878908bcb6_89.png)

Is a half。 so I'll let you work that out with a distance formula。

 but you can just write down the distance between。

![](img/91eb6c86674174f61a9192878908bcb6_91.png)

I'm sorry that should not have been B， let's call that。D， that's the sort of thing you edit out。

 but we're going to keep that here is to give it a sense of reality， the distance between A and D。



![](img/91eb6c86674174f61a9192878908bcb6_93.png)

![](img/91eb6c86674174f61a9192878908bcb6_94.png)

It is what head。

![](img/91eb6c86674174f61a9192878908bcb6_96.png)

Okay。That's cool， so by the way， this word of  two is approximately 1。4。



![](img/91eb6c86674174f61a9192878908bcb6_98.png)

All right， so we have these three distances here， here's a key concept。



![](img/91eb6c86674174f61a9192878908bcb6_100.png)

Let's consider the set S。

![](img/91eb6c86674174f61a9192878908bcb6_102.png)

Which is equal to the origin， B and D。

![](img/91eb6c86674174f61a9192878908bcb6_104.png)

And notice I just computed the distances from A to these three points， O， B and D。

 the distance from A to O is 1。4 approximately。

![](img/91eb6c86674174f61a9192878908bcb6_106.png)

Distance from。

![](img/91eb6c86674174f61a9192878908bcb6_108.png)

Data D is12， which is equal to。5。

![](img/91eb6c86674174f61a9192878908bcb6_110.png)

And the distance from A to B is5。

![](img/91eb6c86674174f61a9192878908bcb6_112.png)

So here's a following statement， meaning should be pretty clear。The nearest neighbor。



![](img/91eb6c86674174f61a9192878908bcb6_114.png)

Of a in the set S。

![](img/91eb6c86674174f61a9192878908bcb6_116.png)

Is the。

![](img/91eb6c86674174f61a9192878908bcb6_118.png)

Because it's the nearest point。The second nearest neighbor。



![](img/91eb6c86674174f61a9192878908bcb6_120.png)

Second， N N。Of A in S。

![](img/91eb6c86674174f61a9192878908bcb6_122.png)

Is。Oh， the origin。 and the third nearest neighbor in the farthest away point is。



![](img/91eb6c86674174f61a9192878908bcb6_124.png)

で。That's something we often use in data science， you have these three points， O， D and D。

 and you want to say if A had to be most like one of them， which one and would it be？



![](img/91eb6c86674174f61a9192878908bcb6_126.png)

![](img/91eb6c86674174f61a9192878908bcb6_127.png)

In this case， we see what it is。

![](img/91eb6c86674174f61a9192878908bcb6_129.png)

Okay， one last little use of distance formulas that we use in data science a lot is the idea of clustering。



![](img/91eb6c86674174f61a9192878908bcb6_131.png)

You'll see later and later in many， many courses why this is important。

Butupp we have a configuration of points in the plane。

 so here's lots small to points here that look like this。

Let's say here's another budget point which look like that。And say another clump over here。Visually。

 if we look at these points， and there might be many， many， many of these points。

 visually and intuitively we say there are three clusters， three clubs。

Really defined what a clump is or a cluster， but somehow it looks like I've got three of them right over here。

 there's cluster one。Cluster two， cluster3。

![](img/91eb6c86674174f61a9192878908bcb6_133.png)

So if these were sort of three different people measured by some blood measurements or something like that。

 we would say there are three stereotypical groups， group one， group two and group three。



![](img/91eb6c86674174f61a9192878908bcb6_135.png)

Distance to the good way of expressing membership in a cluster， essentially， what you might say is。

If A and B。A in cluster one。And C is in cluster of2。



![](img/91eb6c86674174f61a9192878908bcb6_137.png)

And D is in cluster 3。

![](img/91eb6c86674174f61a9192878908bcb6_139.png)

So let's put those points down， say that's a。

![](img/91eb6c86674174f61a9192878908bcb6_141.png)

That's B。There's the point C， there's the point D。

![](img/91eb6c86674174f61a9192878908bcb6_143.png)

Then。The distance between A and B。Whatever it is is much， much less。 Remember that symbol。

 which we've seen before doesn't really have a formal meaning。

 but we know what it means in the picture， much， much less in the distance between。



![](img/91eb6c86674174f61a9192878908bcb6_145.png)

![](img/91eb6c86674174f61a9192878908bcb6_146.png)

A and c。

![](img/91eb6c86674174f61a9192878908bcb6_148.png)

And it's also much， much less from the distance between A and D。

So having this distance formula of this distance metric often allows you to break points up into stereotypical clusters or clumps。



![](img/91eb6c86674174f61a9192878908bcb6_150.png)

![](img/91eb6c86674174f61a9192878908bcb6_151.png)

And somehow， whatever these are measuring， A and B are much much more similar than A is to C and A is to B。



![](img/91eb6c86674174f61a9192878908bcb6_153.png)

Okay， that concludes our video。

![](img/91eb6c86674174f61a9192878908bcb6_155.png)