# 【Algorithms Lab】计算几何 ｜ Computational Geometry p07 P07_用于点定位的垂直分解_第3部分-随机增量构建的分析 -BV1Jtn7zSEXD_p7-

Now we want to analyze the randomized incrementalcrement construction of the vertical decomposition。

😊。

![](img/4641725ed883cde75ebecba188ea2d91_1.png)

So where do we stand， we're constructing the vericular de composition。

 and we are at the same time constructing a search structure。



![](img/4641725ed883cde75ebecba188ea2d91_3.png)

The vertical decomposition does not depend on the order in which we insert the segments。

 so we can ignore that here。

![](img/4641725ed883cde75ebecba188ea2d91_5.png)

The search structure， however。

![](img/4641725ed883cde75ebecba188ea2d91_7.png)

And in this example， we had that。Very much depends on the order or may very much depend on the order and it may vary between linear and quadratic in terms of the size of the search structure and what we want to show is that the expected size is actually linear。

😊。

![](img/4641725ed883cde75ebecba188ea2d91_9.png)

![](img/4641725ed883cde75ebecba188ea2d91_10.png)

![](img/4641725ed883cde75ebecba188ea2d91_11.png)

And the way we're going to show that is that we're going to analyze the expected number of nodes that we create in the I step。

 and we're going to use a very nice analysis for this， which is called a backwards analysis。

 But instead of looking at the nodes of the search structure that are inserted。

 we instead analyzing it in terms of the new trapezoids and the reason that is a valid way of analyzing this is because。

😊，The number of trapezoids that I'm removing and the number of trapezoids that I'm inserting and in between the number of new nodes。

 all of that stands in a linear relationship to each other。

 So it's enough to counts a number of or analyze the expected number of newly created trapezoids and we're going to use a backwards analysis for that。

 So what does backwards analysis mean？

![](img/4641725ed883cde75ebecba188ea2d91_13.png)

So first of all， I mean， if you think about how would you naturally analyze this。

 you would be looking at the search structure after I minus-1 insertions， all possible I insertions。



![](img/4641725ed883cde75ebecba188ea2d91_15.png)

嗯。And you would have to do an analysis about segments that are not actually in the verticaltic de compositionposition yet。

😊。

![](img/4641725ed883cde75ebecba188ea2d91_17.png)

![](img/4641725ed883cde75ebecba188ea2d91_18.png)

Backwards and analysis does this in a very clever way as in that you're looking at the vertical decomposition after the ice insertion。

 So all segments that we're going to talk about are already there。😊。



![](img/4641725ed883cde75ebecba188ea2d91_20.png)

In this situation， if I think about the last insertion。

Every segment that is currently there has the same probability of having been the last segment to be inserted。

 so how can I analyze the number of trapezoids created in the last insertion so I can look at all the segments that are currently there I can count how many new trapezoids would they have created so for instance。

 let's take one。😊。

![](img/4641725ed883cde75ebecba188ea2d91_22.png)

This year I can count one，2，3，4，5，6， so this one creates six trapezoids so here we get a nine。



![](img/4641725ed883cde75ebecba188ea2d91_24.png)

Nine trapezoids， I do this for every segment。😊，And now the average of this。

 because every segment has the same probability of being the last。

Average of this is the expected number of trapezoids created。

 So the quantity that we're going to analyze is the sum of all of these numbers。 And then we can。

 after it's divided by。 So K I will be then sum。Over all segments and then the number of trapezoids that would have been created if this segment or if the segment Sj because the sum goes overj。

 if this the segment Sj would have been the last。And now comes the main trick。

And that is the following。 So this sum sums of oil segments and count trapezoids。

 but we can also look at this from the trapezoid perspective。

 So instead of summing of oil segments and counting trapezoids。

 what we're going to do is we go going to some of trapezoids that are currently there and see which how many segments would have resided in creating this trapezoid last。

 the only segments that would have caused this trapezoid to be one of the trapezoidites that were inserted in the last step the only trapezoids are the ones that is either the top one。

 So let's say here， this one is it would have been。😊。



![](img/4641725ed883cde75ebecba188ea2d91_26.png)

The segment here。Or the bottom one， okay， the bottom one right now is a bounding box。



![](img/4641725ed883cde75ebecba188ea2d91_28.png)

Or the one that gives me the left endpoint or the right endpoint。

So only those three segments would have resulted in creating this one last。And if I do the same。

 let's say for this trapezoid， it's again。Bottom top left right。 And in this case， okay， bottomman。

T and right is the same bottom and left is the same。

 but overall it's at most four segments that would have reside in any given trapezoid to be。

Inser it in the last step。 So if I now look at this sum again。

 So K I is a sum over all possible segments and then counting the number of trapezoids that would have been created if this segment would have been the last。

I now rewrite this in terms of trapezoids。So I count instead， I count over all trapezoids deelta in。

In the I vertical decomposition。 And now I count number。Of segments that would create。

That trapezoid would create。データ。Now， I know these segments can only be bottom top left。Right。

 so these can be， this can be at most4。 So what I get is sum。Over trapezoids4。

 So for each trapezoid I get at most of four。 So this is a smaller equal。

So this corresponds to four times。Number。Of trapezoids。So how many trapezoids do we have。

 we analyze that previously， so if I have n segments we said I have at most3 n plus1 trapezoids。

 or here if I have I segments， I have at most3 i plus1 trapezoids。

 so what I have here is I can bounce this by four times3 i plus1。😊，Which is。12 i。Plus 4。

 So this sum K I is bounded by 12 I plus 4。 That was summing of all segments。

 So the average is bounded by 12 I plus 4 divided by So roughly 12。 Okay。

 so that's what we have so far。 So what does that tell us。

 So we have that K I is bounded by 12 I plus 4。This means that the average or the expected number of trapezoids created in the I' insertion。

 so K corresponds to K divided by I so that is smaller equal 12 I divided by I plus4 divided by I let's say we're looking at the case I larger equal4 to make our life easier then this is smaller equal 13 i divided by I so that is 130 so on average we don't create more than 13 trapezoids so that is in the I insertion so then I would be summing over all insertion steps so from I I is1 to n if on average I'm not creating more than 13 trapezoids then overall I'm not creating more than 13 n trapezoids。

An expectation。So the expected number of trapezoids graded。Is indeed linear。

 So this is now about the size of the search structure。

 Now we are interested in the length of the search path because the length of the search path corresponds to our query time。

 So let's say this is my query， this point Q。 and I want to know how long the search path。

 we can again use backwards analysis to analyze how long the search path might be。

 And for this we ask， let's say this is D。

![](img/4641725ed883cde75ebecba188ea2d91_30.png)

![](img/4641725ed883cde75ebecba188ea2d91_31.png)

What is the probability that the search path got longer with the I insert？



![](img/4641725ed883cde75ebecba188ea2d91_33.png)

Which means that from the I to D I minus1。The trapezoid in which Q lies。Actually changed。 That again。

 can only be if one of the defining segments was the one that was inserted in the I insertion。

So what is the probability does that in the ice insertion？😊。

One of these segments has been inserted so I have n segments， these are three。

 so the probability that one of these was the last is 3 divided by or because in general it could be four segments defining this trapezoid。

 I can bound the probability that the trapezoid in which Q lies in terms of the search structure after I steps that that is different after I minus1 steps I can bound that by4 divided by I so these one23 possibly a fourth one divided by。



![](img/4641725ed883cde75ebecba188ea2d91_35.png)

![](img/4641725ed883cde75ebecba188ea2d91_36.png)

![](img/4641725ed883cde75ebecba188ea2d91_37.png)

![](img/4641725ed883cde75ebecba188ea2d91_38.png)

This means that the length of the search pass， so what I'm analyzing is probability。

So I'm looking at n insertions。

![](img/4641725ed883cde75ebecba188ea2d91_40.png)

The probability that the search pass became longer。With an I insertion。



![](img/4641725ed883cde75ebecba188ea2d91_42.png)

That is bounded by。

![](img/4641725ed883cde75ebecba188ea2d91_44.png)

So I have the sum from one to n。The probability that this path got longer with ice insertion was backwards。

 analysis， we concluded this is bounded by4 divided by I。 So I have this is four times this sum here。



![](img/4641725ed883cde75ebecba188ea2d91_46.png)

![](img/4641725ed883cde75ebecba188ea2d91_47.png)

So ideally， you recognize this sum already and know how large it is。To give you some intuition。

 I mean the sum is somewhat similar， so we have one divided by I。

 so this is somewhat similar to the integral one divided by x Tx。Which is。log X。

This is a base to get bound here， this is4。Can be bound by four times one plus。This lovely with me。

Lock of n base。 Here we were analyzing the expected length of the search path。

 This is bounded by order lock N。Yes so expected that also means the expected query time is order log。

So where do we stand now。We have everything that we wanted to get given the assumptions that we made。

 So we given the plan subdivision。

![](img/4641725ed883cde75ebecba188ea2d91_49.png)

![](img/4641725ed883cde75ebecba188ea2d91_50.png)

Defined by non causinging line segments so that's standard。

We were assuming that all x coordinates are different。

 so let's keep that assumption in here because we haven't resolved that yet。

 so given the situation in the plane we can preprocess the subdivision in or end lock n time so we I didn't specifically discuss the running time now。

 but what we saw is that in each insertion every time in every step of the randomized incremental construction we first have a search。



![](img/4641725ed883cde75ebecba188ea2d91_52.png)

![](img/4641725ed883cde75ebecba188ea2d91_53.png)

![](img/4641725ed883cde75ebecba188ea2d91_54.png)

That takes order length of the search pass。 And we've seen that is order of log n or log I for the ice insertion plus the number order of number of new trapezoids。

 which is overall， if I sum over all linear。 So what I get per insertion is essentially the the expensive parts is a。



![](img/4641725ed883cde75ebecba188ea2d91_56.png)

![](img/4641725ed883cde75ebecba188ea2d91_57.png)

![](img/4641725ed883cde75ebecba188ea2d91_58.png)

![](img/4641725ed883cde75ebecba188ea2d91_59.png)

Going down the search structure， the log n or log I and then summing over or in search set gives us order n log n。

 we need order n log n to create this data structure。

 it has an expected linear size and the expected query time is order log。



![](img/4641725ed883cde75ebecba188ea2d91_61.png)

![](img/4641725ed883cde75ebecba188ea2d91_62.png)

![](img/4641725ed883cde75ebecba188ea2d91_63.png)

![](img/4641725ed883cde75ebecba188ea2d91_64.png)

We have constructed the vertical decomposition for point location。

But we haven't handled degenerate cases so far。 So initially we made this assumption that we have a bounding rectangle。

 that's a valid assumption because for a given plain a subdivision we can always find a bounding rectangle。

 but we also made the assumption that we have unique X coordinates。

 and if we wouldn't have unique X coordinate， then we would have difficulties deciding left right for the same X coordinates。

 So how can we handle this degenerate case。 The solution here is。



![](img/4641725ed883cde75ebecba188ea2d91_66.png)

![](img/4641725ed883cde75ebecba188ea2d91_67.png)

![](img/4641725ed883cde75ebecba188ea2d91_68.png)

A sharing transform and actually a symbolic sharing transform。 So best to。

 to look at these pictures first。 So essentially we are slightly， So if we have something vertical。

 we are slightly tilted to the right so that these two points that are were previously。



![](img/4641725ed883cde75ebecba188ea2d91_70.png)

Vertical。Now， this one is slightly to the right。 We do this with a this transformia。

 So depending on the y， we slightly tilt x。 We do it with a very small epsilon such that the overall x order。

We made the same。 So what we want to have is at this point should still be。

Before the next point in ex， we will actually not explicitly do this transformation。

 That's why it's called symbolic。But we， will look at how would we need to。

Do our computations if this transformation would have been done？

So we' are only applying it symbolically So we don't apply the transformation。

 but we use the algorithm as if it would have been applied specifically。

What is the effect of such a transformation， It essentially just means that we're going to handle vertices lexiographically。

 so in lexiographical order， so in terms of the x so the new X order is the old x order just if they had same x coordinates。

 the one with the larger Y coordinate will come slightly later。



![](img/4641725ed883cde75ebecba188ea2d91_72.png)

So it means we're going to use lexographical ordering。

 but it also means that all of the point line incidences will still be maintained。

So let's see how that affects the operations that we needed for the algorithm so which which operations did our algorithm actually need。

 So we had essentially two types of tests。 We are testing for a given query point whether it's to the left or the right of a vertical line or actually more precisely left or right of the vertical line through some given point P and we were testing whether Q is above or below a segment because we are using a lecoographicical order we will get that this test is executed。

 So if we do this test using the leographical order。

 we would have this test correct for the setting where we would have applied the share transform so test1 will be。

😊，Correct， assuming the point that was shared if we use lexxiographical or。

Since we key point lines incidences， the above below relation will also still be the same。

 So the test， the second test will also be answered correctly。 So this is all about to general cases。

 This solves。What we have to solve for this algorithm。

 It's a very elegant way to handle these degenerate cases。

 So what we have is now the finer theor given a plane a subdivision consisting of n non-cosing line segments in the plane so we can preprocess them in order n log n time or expected time as to get a structure of expected linear size with expected query time order log N。

 So overall what have we seen we've been looking at the problem of point location as a data structure we've seen a vericularity composition together with a search structure。

 the technique that we were using where was a randomized incremental construction and we analyzed that randomized incremental construction using a backwards analysis and that's all for today。



![](img/4641725ed883cde75ebecba188ea2d91_74.png)

![](img/4641725ed883cde75ebecba188ea2d91_75.png)