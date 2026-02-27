# 斯坦福大学《社会和经济网络：建模与分析｜Social and Economic Networks： Models and Analysis》中英字幕 p20 20_02_08_2-7-随机网络-阈值与相变.zh_en -BV1v1421U7Nk_p20-

![](img/e72017e9e28c4282250926f32120daf2_0.png)

hell again， so now we're going to talk a little bit more about random networks and in particular we can talk about what are known as thresholds and phase transitions。

 so just to get some terminology out there and to take a look a little bit at the Erdaranni networks to understand them a little better so first thing when we talked about these properties。

 we were talking about monotone properties， so we're specifying that on a given set of nodes N we have a particular property。

 and we'll say that some function of n called T of n is a threshold function for some property。

 if the probability that that property holds goes to one as long as the probability of links compared to this threshold is becoming quite large heading towards infinity。

 So if we're've got a probability that's much。

![](img/e72017e9e28c4282250926f32120daf2_2.png)

![](img/e72017e9e28c4282250926f32120daf2_3.png)

![](img/e72017e9e28c4282250926f32120daf2_4.png)

![](img/e72017e9e28c4282250926f32120daf2_5.png)

![](img/e72017e9e28c4282250926f32120daf2_6.png)

than this threshold， we get the property for sure and if we have a probability compared to the threshold which goes to zero so the probability shrinks compared to the threshold then the property does not hold so the idea here is we'll identify some level of probability that links have to form with and if you're above that then the property holds and if you're below that the property doesn't so that's a threshold function and we'll say that a phase transition occurs at this threshold。

 meaning that if your probability is above that， you're getting the property if not you don't so the network structure is changing and either satisfying or not satisfying that property as you cross those thresholds So let's have a look at some threshold functions and we can then put a little more meat on this So what do these threshold functions look like So the first question is you know when do you begin to get。



![](img/e72017e9e28c4282250926f32120daf2_8.png)

![](img/e72017e9e28c4282250926f32120daf2_9.png)

![](img/e72017e9e28c4282250926f32120daf2_10.png)

![](img/e72017e9e28c4282250926f32120daf2_11.png)

![](img/e72017e9e28c4282250926f32120daf2_12.png)

Links。So if P is much smaller than one over n squared。

 you're not going to get any links with a high probability， you won't see any links at all。

 if P is bigger than one over n squared then the network is going to begin to have some links so this is basically where the average degree is one over n so you have a fairly small average degree but now when you aggregate across a bunch of nodes。

 somebody is likely to have at least one link。

![](img/e72017e9e28c4282250926f32120daf2_14.png)

The second threshold then is where you get to one over n to the three/ halves and now the network begins to have a component with at least three links。

 so this you begin to see some nodes connected to each other appearing。

 so this is the average degree is one over the square root of n。



![](img/e72017e9e28c4282250926f32120daf2_16.png)

The next point at which you get a threshold here at one over n is going to be a threshold for the network having a cycle。

 the network having a unique largest component。Where a giant component where a giant component means that for some fixed A less than one you've got at least NA nodes in that component so this is basically the point where average degree is one so everybody expects to have at least one neighbor or on average have one neighbor then if you're above this。

 you begin to have cycles and the network starts to look connected below this you don't have cycles and you tend not to have a giant component so things look like lots of small components or disconnected nodes。



![](img/e72017e9e28c4282250926f32120daf2_18.png)

Then probably one of the more interesting thresholds comes in at the point where you hit log n over n。

 so the average degree now people expect to have log n neighbors and at that point the network starts to be path connected。

 so now you can go from every node to every other node and you actually have a connected network。



![](img/e72017e9e28c4282250926f32120daf2_20.png)

So let's just have a look at some of these pictures。of networks drawn in this way。

 so here I started with fairly low P and 50 nodes we begin to see there's not much the nodes are fairly separate a lot of isolates。

 a few links here and there once we hit the point where we've crossed the first the threshold for the emergence of cycles in a giant component that's 0。

02 in this particular case， so we get the P equals 0。

03 so now everybody has an expectation of about 1。5 friends' above that level we begin to see this giant component emerging we see some cycles emerging so there's some cycles in here we still see some small disconnected components in a bunch of isolated nodes so we're still at a point where we're small enough that things aren't completely connected but we start to see a giant component。



![](img/e72017e9e28c4282250926f32120daf2_22.png)

![](img/e72017e9e28c4282250926f32120daf2_23.png)

![](img/e72017e9e28c4282250926f32120daf2_24.png)

![](img/e72017e9e28c4282250926f32120daf2_25.png)

As we continue to increase the P so now we make it so that you have on average two and a half friends now this giant component gets larger。

 there's actually only a few isolated nodes left we're seeing more cycles。

 it's beginning to take more shape and then once we get to P equals 0。1。

 so now we've got an expectation of five links roughly per node。

 then we're looking at a situation where we're above the threshold for overall connection。



![](img/e72017e9e28c4282250926f32120daf2_27.png)

![](img/e72017e9e28c4282250926f32120daf2_28.png)

Remember was on the order of log n and now indeed we begin to see that we've got one large component and every node is able to reach every other node。

 so what we saw here is a series of different threshold functions and as you crept increasing P you're getting more and more properties in terms of these monotone properties holding and we're seeing more connectedness。

 a fewer isolated nodes， cycles beginning to form eventually the whole network is connected。

 we don't have any small components left and these are very sharp transitions in the sense that once you get a little bit above these even for 50 nodes the transitions work fairly sharply and there's a lot of mathematics that's been worked out about the properties of these random graphs and understanding them what we'll do is in the next video will go through understanding exactly how some of these are proven for people who don't want to go through them。

thematics of that you can skip this one the next one what I'll do is just go through an explicit calculation of one of these and sort of show you how one of these theorems is proven and in particular this sort of threshold for not having isolated nodes and making sure that things have coalesced into a network。



![](img/e72017e9e28c4282250926f32120daf2_30.png)