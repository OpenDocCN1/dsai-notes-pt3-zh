# TrevorHastie／RobertTibshirani《统计学习导论｜An Introduction to Statistical Learning》中英字 - P68：P68 StatsLearning Lect12d 111113.zh_en - GPT中英字幕课程资源 - BV1jN4y1Y7JR

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_0.png)

Welcome back， I had to run out and get a haircut and change my shirt， but we're ready to go。

So we were just talking about K means clustering， and you remember one of the things with K means clustering。

 one of the challenges is， do you have to choose the number of clusters K， right？

Which is can be a problem， and later we'll talk about strategies for choosing K。But in this segment。

 we'll talk about hierarchical clustering， a different kind of clustering。

 the second major one that we'll talk about， and it has advantage doesn't require the choice of K。

 As a matter of fact， as we'll see， it gives us the clusterings for all K at all at once。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_2.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_3.png)

And we'll talk about what's called a gallometerative or bottom up hierarchicalquesting。

 which is the most common kind of hierarchicalquesting is also top down hierarchicalquesting you might see。

 but we won't talk about that in the lecture because the bottom up or gallometer is by far the most common。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_5.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_6.png)

And we'll see that a glometerative。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_8.png)

Thequesting starts from the bottom the individual observations as leaves and combines them successively in a hierarchy。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_10.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_11.png)

So let's see the main idea just in the picture。 So here's some data with five objects and two features in the horizontal verticalla and what hierarchcholeing does is success joins each the closest pair of objects。

 So first of all，'ll run through it quickly and then we'll go back and look at the operations more slowly。

 So here's the data and I see what hierarchchoqueststering does。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_13.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_14.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_15.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_16.png)

So there's one linkage and another clustering， another one， and another one。 so I did a total of one。

 two， three， four joints。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_18.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_19.png)

Let's go back more slowly now and see what happened， so starting with the raw data。

 it looks for the closest pair of objects in terms of square distance and we'll talk little bit later。

 we can actually vary that and use a different metric， but usually at squared distance。

 so the closest points in the plane here， the closest pair are A and C it joins those together。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_21.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_22.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_23.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_24.png)

Then it looks for the next closest pair， and that is D& E。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_26.png)

And then it's going to join the next closest pair， but now the idea of a pair we're going to join not necessarily always just single observations。

 we might join an observation with an existing cluster or maybe join two clusters。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_28.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_29.png)

Now I'll have to decide on what we mean by how far apart our two clusters。

 which we' we'll talk about a little later in the segment。 but let's let's。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_31.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_32.png)

Let's see how we've made some choice of of that metric and let's see what happens。

 It joined B with A and C， and then finally， all five。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_34.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_35.png)

Points together in one question。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_37.png)

So in this last one， I joined two clusters together。 red the big red cluster and the green cluster。

 right， So this next slide summarizes。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_39.png)

Now the clustering， again， you see here on the left， the series of joins that we just saw。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_41.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_42.png)

And now on the right。Is a denogram or clustering tree。

 which is a very nice way of summarizing the clustering。

 the picture on the left is fine when you have two features。

 But imagine if you had if you're 100 features， we'd have to be drawing 100 dimensional object。

 right， which you can't do。 The clustering tree on the right is a。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_44.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_45.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_46.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_47.png)

The most useful way of summarizing the cluster。 So let's see what's how it summarizes things。 Well。

 here's the A seat。 first of all， at the bottom have the leaves of the tree， the objects。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_49.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_50.png)

Labeled A through E。 the first join is indicated here。 This is the join of A And C。

 And the height of the join is also this height of this join is drawn at the height at which is at the。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_52.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_53.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_54.png)

The distance between the two points involved， right So A and C， their square distance is here。

 and that's the height at which this is is drawn。 The next join is D and E， then B with A and C。

 And finally all the objects to get at the top So the cluster tree gives us a nice summary of the the series of joins that we get in in the cluster。

 what's it mean a distance between a point in the cluster。 Well。

 we'll get to that do want me tell you right now， okay。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_56.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_57.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_58.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_59.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_60.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_61.png)

嗯。So here's another example， there's 45 observations， again， two dimensions。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_63.png)

And in reality here， we've imagined there's three classes， so I've colored them as such green。

 purple and gold。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_65.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_66.png)

But we're not going to use these class labels in the clustering。

 we want to see after we do the cluster where these points end up。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_68.png)

So here is the result of hierarchical clustering to the 45 points。

 and these are all all the same dengram。 But what I've done here is I've。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_70.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_71.png)

I've cut off the question tree at different heights on the left。

 I've basically cut it off at the top， so the entire tree is one cluster。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_73.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_74.png)

That's why I've labeled all the leaves by the same colored green。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_76.png)

But here I've cut the cluster tree off at this height， with about nine。

 it creates two clusters which I've indicated by red and green。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_78.png)

And then finally here， I've chosen a different cutting height of around five。

 it it forms three clusters。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_80.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_81.png)

The purple， the gold and the green， and you see the original three classes。

 which I color are actually coincide with these three clusters。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_83.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_84.png)

The point is that by doing the hiarchcho clustering and cutting the tree off at an appropriate height。

 we recover exactly the three classes we started with。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_86.png)

You can also see that now what this is showing us is that with a single operation giving us this clustering tree。

 we get a clustering for all k right if we decide we take the same tree if we cut off at the top。

 we get k equals 1， we cut it off at9， we get k equals2 and we cut it off here we k equals 3。

 I could cut lower and get more clusters， I could cut it right at the bottom and get a clustering which had a cluster for each observation。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_88.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_89.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_90.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_91.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_92.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_93.png)

Which probably wouldn't be very useful， but the point is that we get a spectrum from one up to n clusters depending on where we cut from a single cluster injury。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_95.png)

Okay， so this is the details of the figure， which I have already been through。Okay。

 so memory we talked before about how we had to decide whether how far apart two clusters were or a point from a cluster。

The linkage is what that's called and now let's talk about the details of the choice of linkage。

 So on this slide I've got the different linkages complete single average and centroid and the definitions I maybe be easier to go to a blank slide and I'll have my Khan Academy moment and show you just in pictures what these what these。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_97.png)

These measures are so complete link first of all， I think we have a measure of two clusters。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_99.png)

Okay， and this guy's already cluster and over here we have another cluster。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_101.png)

And now we want to decide how far apart is this cluster of three from this cluster of two。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_103.png)

Complete linkage。First of all， the first kind。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_105.png)

We look at the farthest distance between any pair where pick one object from here and one from here。

 So the farthest distance will be。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_107.png)

We'll read this one。This pair is the farest apart， so we deem these two clusters to be this distance apart。

 that's complete linkage， so it's kind of a worst case measure。

 single linkage is the other one it's the best case we find the closest pair and for that looks like it would be this pair right this pair would be the closest。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_109.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_110.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_111.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_112.png)

A single linkage。And then the average linkage is， as you can imagine。

 take we look at all pairs and take the average distance。

 so we look at the distance between this guy and these two and so howing altogether to every' six。

 I guess， six distances。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_114.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_115.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_116.png)

The average of those six pairwise distances would give us the average linkage measure。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_118.png)

Yes，6，6。He's quick。 Okay， and then the so these are the three first three measures。

 the last one's called centroid linkage， which is。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_120.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_121.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_122.png)

Not used as commonly， pity then at different colors of this painting。

 Actually they do have different colors。 Well， okay， centroid linkage。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_124.png)

We take the centroids of each cluster first， that's the average， right， the middle point。你都。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_126.png)

I think stable。 I want to。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_128.png)

Okay。And now， so these points are meant to be the average of these three。 And this one。

 the average of these two， the centroid。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_130.png)

Linage is how far apart the centroids are these two。 So that's the third measure。

 the ones that use most commonly are complete and average single linkage if you have a look at this。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_132.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_133.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_134.png)

In our book， theres some examples of it。 S linkggage has a problem that tends to produce long。

 stringy clusters， so it tends to join one point at a time as a cluster， but as complete an average。

 tend0 to produce trees， which are more bound， more symmetric looking center where linkage is common in genomics。

 It has some problems， though， with what called inversions， which you won't discuss。

 but you can read about in the book。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_136.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_137.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_138.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_139.png)

So there's four choice of measure with complete and average being the most commonly used。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_141.png)

Great， one picture tells it all， yes， and but if you want details。

 the previous slide has all this done in words。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_143.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_144.png)

Let's see。Okay， so a few more things to talk about。

 we talk about the the complete average and single linkage and sentry in the previous slide and that was to do with how we deem how far apart we deem a pair of clusters from each other。

 but then we still have to we we have to decide what it we mean by far apart and we've be using square distance up and now and that's Euclidean distance and that's actually the most commonly used measure。

 but another one that's used quite commonly is correlation which is the correlation between the profiles the features across two observations across their features。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_146.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_147.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_148.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_149.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_150.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_151.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_152.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_153.png)

This is often a case when features are actually measurements at different times。

 so you can think of each series， each measurement for for an individual as a series of points over time。

 a little time series like each of these curves And you were to see how similar the patterns in each of those series。

 So then correlation measure is suitable in that case。

 So yeah here' here's an example and we can imagine this indexversese could be time。

 you have three observations， the purple， the gold and the green。 in terms of square distance。

 we'd look across the coordinates， the purple and the gold are very close together in the greens farther part from those those two。

 in terms of correlation， if we could consider the pairs of points at each of these。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_155.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_156.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_157.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_158.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_159.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_160.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_161.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_162.png)

Indices， then actually the green is closer to the gold than it is to the purple。

 right because the green and the gold they go down and up together， right。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_164.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_165.png)

So the point is that if your correlation doesn't worry about the level but rather the shape。

 so shape is in your example is in particular problem is more important than the actual level。

 then correlation correlation is a better choice than Euclidean distance。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_167.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_168.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_169.png)

and also you have to choose decide whether you want to use correlation or absolute correlation。

 Sometimes it matters whether things are anti correlated or positive correlated other times。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_171.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_172.png)

You just use the absolute value of the correlation。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_174.png)

So those are all common those are both。 I suppose this brings up the point that you can actually come up with any distance that suits you right。

 you know， depending on the problem， if there's a particular distance that makes whole sense use that like the only thing you need for particle clustering and actually whatque means for that matter is a choice of distance between pairs of observations。

 Having decided that， then the algorithms just use that as their input。O。

So some practical issues two more things well scaling of the variables matter and that's the case in K means as well so this slide actually refers to both K means clustering and how clustering and principal components that have exactly right if the variables are not in the same units and one variables in a unit that it has very large numbers then if you don't standardize the variables that variable will dominate either principal components or clustering because it's the units are such that the square distance for that variable is much larger。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_176.png)

So typically， if variables are not in the same units， one should standardize them。

 and that words make the mean zero and variance standard deviation to be 1。

If they're in the same units， you have a choice。And it's often good to do it both ways。

 during the same units you might want to leave the variables as is and see which ones have more variation and those will tend to drive the principal components or clustering in other cases people will standardize in that situation。

 so it's good to try it both ways。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_178.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_179.png)

And then the case of hierarchical clustering， we talked about these already。

should we use square distance or correlation for dissimilarity and the linkage choice of linkage a problem I' alluded to。

 I'm not really going to give much say much more here is that the choice of K。

 the number of clusters。And let me just say we're not going to talk about it because it's a difficult problem with no agreed upon solution。

 there's not a standard method we can point you to to say this is how you choose K in our data mining book。

 the elements ofs Learn in Cha 13， there's much more detail about this。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_181.png)

But typically the problem is again it's not well solved and it's usually done in sort of a qualitative way。

 like for an a clustering hierarchical clustering， people just tend to look at the result of a clustering tree。

 see where the biggest drop in the branches is and they maybe cut it off there like we sort remember the example and go back just to the clustering。

In this example， right， might this was actually some data you had， you might look at this and say。

 oh it looks like the longest branches are here， here's where the longest arms are。

 I'll cut it off here and then below that the arms are much shorter。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_183.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_184.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_185.png)

And remember， that's reasonable because the height at which we draw these joins is the square distance at which the joins occur。

 so the biggest bang for the buck is occurring in these joins and then is less lower down。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_187.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_188.png)

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_189.png)

So that's subjective， and that's typical what people do。 They just have a look at this and say， oh。

 I'm going to cut it off， you know， maybe at three clusters。



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_191.png)

ok。

![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_193.png)

嗯。And which feature should we use to drive the clustering？



![](img/e0de71a0df0e3a9f9eff1bb6ea7037ff_195.png)

You are often given in some areas of science， given a large number of features and you want to use those features for clustering some objects。

 you can choose the features you use and if you change the choice of features as you can imagine。

 it's going to change the clustering that you get。Okay。

 that's the end of this segment on higherarchchoquesting in the last segment we'll talk we'll see a real example of the application of higherarchchoquesting to a study of breast cancer。

