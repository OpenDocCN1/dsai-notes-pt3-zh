# 斯坦福大学《统计学习导论2023R语言版｜An Introduction to Statistical Learning with R》中英字幕 - P89：-089-Statistical Learning_ 12.4 Hierarchical Clustering.zh_en - GPT中英字幕课程资源 - BV1yU421o7WA

Welcome back， I had to run out and get a haircut and change my shirt， but we're ready to go。

So we were just talking about K means clustering， and you remember one of the things with K means clustering。

 one of the challenges is you have to choose the number of clusters K， right？

Which is can be a problem， and later we'll talk about strategies for choosing K。But in this segment。

 we'll talk about hierarchical clustering， a different kind of clustering。

 the second major one that we'll talk about， and it has advantage doesn't require the choice of K。

 As a matter of fact， as we'll see， it gives us the clusterings for all K at all at once。

And we'll talk about what's called a glometer or bottom up hierarchical clustering。

 which is the most common kind of hierarchicalquesting is also top down hierarchicalquesting you might see。

 but we won't talk about that in the lecture because the bottom up or a glometer is by far the most common。

And we'll see that the gllometerative。Thequesting starts from the bottom the individual observations as leaves and combines them successively in a hierarchy。



![](img/a3fe4bb50657b79153ff1065e5cc667a_1.png)

So let's see the main idea just in a picture。 So here's some data with five objects and two features in the horizontal vertical axis。

 and what hierarchcho clustering does is successfully joins each the closest pair of objects。

 So I'll first of all， run through it quickly and then we'll go back and look at the operations more slowly。

 So here's the data and I see what hierarchcholestering does。



![](img/a3fe4bb50657b79153ff1065e5cc667a_3.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_4.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_5.png)

So there's one linkage and another clustering， another one and another one， so I did a total of one。

 two， three， four joins。

![](img/a3fe4bb50657b79153ff1065e5cc667a_7.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_8.png)

Let's go backll slowly now and see what happened。 So starting with the raw data。

 it looks for the closest pair of objects in terms of square distance。 we'll talk little bit later。

 we can actually vary that use a different metric， but usually at square distance。

 So the closest points in the plane here。 the closest pair are A and C it joins those together。



![](img/a3fe4bb50657b79153ff1065e5cc667a_10.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_11.png)

Then it looks for the next closest pair， and that is D and E right。



![](img/a3fe4bb50657b79153ff1065e5cc667a_13.png)

And then it's going to join the next closest pair， but now the idea of a pair we're going to join not necessarily always just single observations。

 we might join an observation with an existing cluster or maybe join two clusters。



![](img/a3fe4bb50657b79153ff1065e5cc667a_15.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_16.png)

And'll have to decide on what we mean by how far apart of two clusters， which will。



![](img/a3fe4bb50657b79153ff1065e5cc667a_18.png)

We'll talk about a little later in the segment， but lets see how we've made some choice of that metric and let's see what happens。

 it joined B with A and C and then finally all five points together in one cluster。



![](img/a3fe4bb50657b79153ff1065e5cc667a_20.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_21.png)

So in this last one I joined two clusters together。 the the big red cluster and the green cluster。

 right， So this next slide summarizes。

![](img/a3fe4bb50657b79153ff1065e5cc667a_23.png)

Now the clustering， again， you see here on the left， the series of joins that we just saw。



![](img/a3fe4bb50657b79153ff1065e5cc667a_25.png)

And now， on the right。There's a denogram or clustering tree。

 which is a very nice way of summarizing the clustering。

 the picture on the left is fine when you have two features。

 But imagine if you had if you're 100 features， we'd have to be drawing 100 dimensional object。

 right， which you can't do。 The clustering tree on the right is a。



![](img/a3fe4bb50657b79153ff1065e5cc667a_27.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_28.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_29.png)

The most useful way of summarizing the cluster。 So let's see what's how it summarizes things。 Well。

 here's the A seat。 We， first of all， the bottom we have the leaves of the tree， the objects。

Labeled A through E。 the first join is indicated here。 This is the join of A And C。

 And the height of the join is also this height of this join is drawn at the height at which is at the。



![](img/a3fe4bb50657b79153ff1065e5cc667a_31.png)

The distance between the two points involved， right So A and C， their square distance is here。

 and that's the height at which this is is drawn。 The next join is D and E。 then B with A and C。

 And finally， all the objects to get at the top So the clustering tree tree gives us a nice summary of the the series of joins that we get in in the cluster。

 what does it mean a distance between a point in the cluster， Well， we'll get to that。

 do you want me tell you right now， okay。

![](img/a3fe4bb50657b79153ff1065e5cc667a_33.png)

嗯。So here's another example， there's 45 observations， again， two dimensions。



![](img/a3fe4bb50657b79153ff1065e5cc667a_35.png)

And in reality here， we've imagined there's three classes， so I've colored them as such green。

 purple， and gold。

![](img/a3fe4bb50657b79153ff1065e5cc667a_37.png)

But we're not going to use these class labels in the clustering。

 we want to see after we do the clustering where these points end up。



![](img/a3fe4bb50657b79153ff1065e5cc667a_39.png)

So here is the result of hierarchical clustering to the 45 points。

 And these are all all the same dengram。 But what I've done here is I've。



![](img/a3fe4bb50657b79153ff1065e5cc667a_41.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_42.png)

I've cut off the question tree at different heights on the left。

 I've basically cut it off at the top so the entire tree is one cluster。



![](img/a3fe4bb50657b79153ff1065e5cc667a_44.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_45.png)

That's why I've labeled all the leaves by the same colored green。



![](img/a3fe4bb50657b79153ff1065e5cc667a_47.png)

But here I've cut the cluster tree off at this height， with about nine， it creates two clusters。

 which I've indicated by red and green。

![](img/a3fe4bb50657b79153ff1065e5cc667a_49.png)

And then finally here， I've chosen a different cutting height around five。

 it choose it forms three clusters。

![](img/a3fe4bb50657b79153ff1065e5cc667a_51.png)

The purple， the gold and the green， and you see the original three classes。

 which I color are actually coincide with these three clusters。



![](img/a3fe4bb50657b79153ff1065e5cc667a_53.png)

The point is that by doing the hierarchcho clustering and cutting the tree off at an appropriate height。

 we recover exactly the three classes we started with。



![](img/a3fe4bb50657b79153ff1065e5cc667a_55.png)

You can also see that now what this is showing us is that with a single operation giving us this clustering tree。

 we get a clustering for all k right if we decide we take the same tree if we cut off at the top。

 we get k equals1， we cut it off at nine， we get k equals two and we cut it off here we k equals3。

 I could cut lower and get more clusters， I could cut it right at the bottom and get a cluster which had a cluster for each observation。



![](img/a3fe4bb50657b79153ff1065e5cc667a_57.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_58.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_59.png)

Which probably wouldn't be very useful， but the point is that we get a spectrum from one up to n clusters depending on where we cut from a single cluster injury。



![](img/a3fe4bb50657b79153ff1065e5cc667a_61.png)

Okay， so this is the details of the figure which I have already been through。Okay。

 so memory we talked before about how we had to decide whether how far apart two clusters were or a point from a cluster。

The linkage is what that's called and now let's talk about the details of the the choice of linkage so on this slide i've got the different linkages complete single average and centroid and the definitions。

 but I think it'd be easier to go to a blank slide and I'll have my Khan Academy moment and show you just in pictures what these what these。

These measures are so complete linkage first of all， I think we have measure of two clusters。Okay。

 this guy's already cluster and over here we have another cluster。



![](img/a3fe4bb50657b79153ff1065e5cc667a_63.png)

And now we want to decide how far apart is this cluster of three from this cluster of two？



![](img/a3fe4bb50657b79153ff1065e5cc667a_65.png)

Complete linkage。First of all， the first kind。

![](img/a3fe4bb50657b79153ff1065e5cc667a_67.png)

We look at the farthest distance between any pair where pick one object from here and one from here。

 so the farthest distance will will be this one。

![](img/a3fe4bb50657b79153ff1065e5cc667a_69.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_70.png)

This pair is the father's apart， so we deem these two clusters to be this distance apart。

 that's complete linkage， so it's kind of a worst case measure single linkage is the other one it's the best case we find the closest pair and for that looks like it would be this pair right its the closest。



![](img/a3fe4bb50657b79153ff1065e5cc667a_72.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_73.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_74.png)

A single linkage。And then the average linkage is， as you can imagine。

 if we take we look at all pairs and take the average distance。

 so we look at the distance between this guy and these two and so how many altogether tover are six。

 I guess， six distances。

![](img/a3fe4bb50657b79153ff1065e5cc667a_76.png)

The average of those six pairwise distances would give us the average linkage measure。Yes，6，6。

he's quick。 Okay， and then the so these are the three first three measures。

 the last one's called centroid linkage， which is。

![](img/a3fe4bb50657b79153ff1065e5cc667a_78.png)

Not used as commonly pity then have different colors of this painting。

 actually they do have different colors。 Well， okay， centroid linkage。

We take the centroids of each cluster first， that's the average， right， the middle point， we go。



![](img/a3fe4bb50657b79153ff1065e5cc667a_80.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_81.png)

🎼嗯。I think stay I want to。

![](img/a3fe4bb50657b79153ff1065e5cc667a_83.png)

Okay。And now， so these points are meant to be the average of these three and this one。

 the average of these two， the centroid。

![](img/a3fe4bb50657b79153ff1065e5cc667a_85.png)

Linage is how far apart the centroids are these two。 So that's the third measure。

 the ones that use most commonly are complete and average single linkage if you have a look at this。



![](img/a3fe4bb50657b79153ff1065e5cc667a_87.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_88.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_89.png)

In our book， there's some examples of it。 S linkage has a problem that tends to produce long。

 stringy clusters， so it tends to join one point at a time as a cluster， as complete an average。

 tend to produce trees， which are more balanced， more symmetric looking。

 centerent where linkage is common in genomics。

![](img/a3fe4bb50657b79153ff1065e5cc667a_91.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_92.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_93.png)

It has some problems， though， with what called inversions， which you won't discuss。

 but you can read about in the book。 So there's these four choices of measure with complete and average being the most commonly used。



![](img/a3fe4bb50657b79153ff1065e5cc667a_95.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_96.png)

Great， one picture tells it all， yes， but if you want details。

 the previous slide has all this done in words。

![](img/a3fe4bb50657b79153ff1065e5cc667a_98.png)

Let's see。Okay， so a few more things to talk about。

 we talk about the complete average and single linkage sent in the previous slide and that was to do with how we deem how far apart we deem a pair of clusters from each other but then we still have to we we have to decide what do we mean by far apart and we'd be using square distance up than that and that's Euclidean distance and that's actually the most commonly used measure。

 but another one that's used quite commonly is correlation which is the correlation between the profiles the features across two observations across their features。



![](img/a3fe4bb50657b79153ff1065e5cc667a_100.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_101.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_102.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_103.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_104.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_105.png)

This is often a case when features are actually measurements at different times so you can think of each series each measurement for an individual as a series of points over time。

 a little time series like each of these curves and you were to see how similar the patterns in each of those series so then correlation measure is suitable in that case so yeah here's here's an example and we can imagine this index as t set could be time you have three observations。

 the purple， the gold and the green in terms of square distance we'd look across the coordinates。

 the purple and the gold are very close together and the greens for either part from those those two in terms the correlation if we just consider the pairs of points in each of these indices but actually the green is closer to the gold than it is to the purple because the green and the gold the goal down and up together right。



![](img/a3fe4bb50657b79153ff1065e5cc667a_107.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_108.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_109.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_110.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_111.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_112.png)

So the point is that if your correlation doesn't worry about the level but rather the shape。

 so shape is in your example is in particular problem is more important than the actual level。

 then the correlation correlation is a better choice than Euclidean distance。



![](img/a3fe4bb50657b79153ff1065e5cc667a_114.png)

also you have to choose decide whether you want to use correlation or absolute correlation。

 Sometimes it matters whether things are anti correlated or positive correlated other times。



![](img/a3fe4bb50657b79153ff1065e5cc667a_116.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_117.png)

You just use the absolute value of the correlation。



![](img/a3fe4bb50657b79153ff1065e5cc667a_119.png)

So those are all common those are both。 I suppose this brings up the point that you can actually come up with any distance that suits you right。

 you know， depending on the problem， if there's a particular distance that makes whole sense。

 use that。 exactly the only thing you need for our clustering and actually for K means for that matter is a choice of distance between pairs of observations。

 Having decided that， then the algorithms just use that as their input。O。So some practical issues。

 two more things， well scaling of the variables matter and that's the case in K means as well so this slide actually refers to both K means clustering and powercoquesting。

And principal components that have exactly right， if the variables are not in the same units and one variable is in a unit that has very large numbers then if you don't standardize the variables。

 that variable will dominate either principal components or clustering because the units are such that the square distance for that variable is much larger。

So typically， if variables are not in the same units。

 one should standardize them and other words make the mean zero and variance standard deviation to be  one。

If they're in the same units， you have a choice。And it's often good to do it both ways。

 they're in the same units， you might want to leave the variables as is and see which ones have more variation and those will tend to drive the principal components or clustering other but in other cases people will standardize in that situation。

 so it's good to try it both ways。And then the case of hierarchical clustering。

 we talked about these already。Should we use square distance or correlation for dissimilarity and the linkage。

 choice of linkage。A problem I' alluded to， I'm not really going to give say much more here is the choice of K number of clusters。

And let me just say we're not going to talk about it because it's a difficult problem with no agreed upon solution。

 there's not a standard method we can point you to to say this is how you choose K in our data mining book the El of Learn in Cha 13。

 there's much more detail about this。But typically the problem is again。

 it's not well solved and it's usually done in sort of a qualitative way。

 like for an a clustering hierarchical clustering， people just tend to to look at the result of a clustering tree。

 see where the biggest drop in the branches is and they maybe cut it off there like when we saw remember the example and go back just to the clustering。

In this example， right， this was actually some data you had， you might look at this and say， oh。

 it looks like the longest branches are here， here's where the longest arms are I'll cut it off here。

 and then below that the arms are much shorter。

![](img/a3fe4bb50657b79153ff1065e5cc667a_121.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_122.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_123.png)

And remember， that's reasonable because the height at which we draw these joins is the square distance at which the joins occur。

 so the biggest bang for the buck is occurring in these joins and then is less lower down。



![](img/a3fe4bb50657b79153ff1065e5cc667a_125.png)

![](img/a3fe4bb50657b79153ff1065e5cc667a_126.png)

So that's subjective， but that's typically what people do。

 they just just have a look at this and say， oh， I'm going to cut it off， you。

 maybe at three clusters。

![](img/a3fe4bb50657b79153ff1065e5cc667a_128.png)

ok。

![](img/a3fe4bb50657b79153ff1065e5cc667a_130.png)

。And which feature should we use to drive the quaing？You are often given in some areas of science。

 given a large number of features and you want to use those features for clustering some objects。

 you can choose the features you use and if you change the choice of features as you can imagine it's going to change the clustering that you get。

Okay， that's the end of this segment on higherarchcho clustering in the last segment we'll talk we'll see a real example of the application of higherarchchoqueststering to a study of breast cancer。

