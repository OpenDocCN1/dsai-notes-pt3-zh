# 斯坦福大学《社会和经济网络：建模与分析｜Social and Economic Networks： Models and Analysis》中英字幕 p16 16_02_04_2-4-中心性-特征向量度量.zh_en -BV1v1421U7Nk_p16-

![](img/c07db15a8da6387ea00f0f8a8e326d4f_0.png)

folks。 so we're back again， and。Now we're looking at eigenvector based centrality measures。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_2.png)

Again， as in terms of what we've looked at for characterizing the position of a node in a network。

 we've looked at things like degree。You know， local clustering。

 distance other nodes and then in terms of measuring these centrality influence and power。

 one difficulty is that when we've looked at things like degree centrality it doesn't necessarily capture the importance of a node's friends so you know when we look at this picture for instance there's sort of two aspects to it。

 one is that we you know this node might be much further from a lot of nodes than this one。

 so things like decay and closeness centrality can capture the fact that it's sort of out in the outskirts。

 but another thing is that when we look at the friends of this particular node。

 so if we look at the connections of this node， they each have degree2 themselves whereas this nodes friends have degree6 and seven。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_4.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_5.png)

And so in some sense they're better connected than this other nodes friends and so the idea of eigenvector centrality is that your importance comes from being connected to other important nodes and in particular here。

 if we look at a centrality notion where the centrality is proportional to the sum of the neighbor centralities then we're defining eigenvector centrality。

 so the node I's centrality is proportional to the centrality of the nodes to which I is connected。

 so that gives us an equation which says that C is dependent on the sum of the CJs where what's going to happen here is if GJ is equal to one then we get the CJ being counted and if it's equal to zero then it's not counted so we're just count。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_7.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_8.png)

The centralities of the friends you're connected to。

Okay what's interesting here now is that this is a system of equations in a system of unknowns。

 so we have that in order to figure out what C is， we have to figure out what all the CJs are and so this is a set of equations in set of unknowns and so basically what we have is that the vector C is equal to some a times the matrix G times the vector C and so this is what's known as an eigenvector right so it's a vector where you multiply the matrix by that vector and you get back something which is proportional to the original vector you started with so this A is just some proportional constant which tells you how you're scaling and that's what's known as an eigenvector。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_10.png)

Now， we'll say a little bit more about that in a moment。

 but what we can begin to see is that if we calculate the eigenvector centrality of these。

 so solving that system of equations and unknowns and looking for non-negative solutions。

 what we'll find is this one gets a 0。31， this one gets a 0。11。

 this one is essentially three times as important according to this eigenvector centrality measure of importance。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_12.png)

Okay so what's happening here is you're getting value from connections to others。

 it's a self-referential concept so we have to figure out how to solve that and in particular what we have is we have this equation which we just wrote the eigenvector centrality then of a network G is proportional to itself times G and one thing about eigenvectors is there's many possible solutions so if we have n equations in n unknowns generally there can be up to n different solutions and what we tend to do is look for the one with the largest eigenvalue and there's a theorem in matrix algebra known as the perun forbeius theorem which says that if we're dealing with a non-neative matrix then the eigenvector associated with theligs eigenvalue is going to have non-neativevalues and in particular。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_14.png)

in a lot of contexts we'll be looking at the other eigenvectors won't make sense that might have some negative values or even non-real values。

 so the convention will be to look for the one which has all non-negative real valuess。

 that's going to be the one with the largest eigenvalue and there's a variety of programs that'll calculate eigenvectors for you so if you have a matrix representing your network。

 you can plug them into different programs and at least get an approximation of the largest eigenvalue。

 the eigenvector associated with the largest eigenvalue。

Then we can sort of normalize the entries to sum to1， so any eigenvector if you multiply it by two。

 then that's also an eigenvector so these are all going to be taken up to rescalings and so if we normalize these things to sum to one。

 then we'll have a well definedfin definition。

![](img/c07db15a8da6387ea00f0f8a8e326d4f_16.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_17.png)

Okay， so if we begin to look at you know the eigenvector centrality of different。

Families in the pageant nacent data actually these are not quite normalized。

 but here you know we see that again the Medidici come out higher than other families。

 not as strikingly high， but that's going to give us a different picture of。

What's going on in this kind of setting？

![](img/c07db15a8da6387ea00f0f8a8e326d4f_19.png)

Now when we talk about eigenvector centrality， there's a number of different concepts that are related to it。

 Google Page ranknk， so named after Larry Page was the system that sort of helped Google become the search engine that really dominated the market early on and the idea was that when you typed in something and it had a bunch of pages that it could show that would have whatever term you typed in on it。

 it had to pick one in the way that it sort of picked the ordering originally was that it would look for the ones with the largest eigenvector centrality。

 so it was trying to look for pages that were connected to by pages that were important and that was a sign of its importance。

And you know it's that algorithm is now much more complicated and has evolved over time to do all kinds of other kind things people were manipulating the algorithm。

 it also could take into account what it thinks people might want and so forth。

 but the basic idea here was eigenvectorcentity to begin with。

Something known as the random surfer model as well which is you know suppose you hopped on the web and you started just picking pages at random and then so you go to a page and then click on one of its links at random go to that page click on a link at random and so forth and then look at the fraction of time you would spend on each page as you went through this process over time that's going to be related to an eigenvector calculation so eigenvector calculations are ones that encapsulate this idea of important connections to other nodes and then being connected to by big important ones helps pre more traffic to you。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_21.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_22.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_23.png)

We can go back to the network we had before and we can put in eigenvector centrality measures and now node3 actually comes out ahead of node4。

 so depending on which way you do these things you get different measures。

One last measure which is going to be very useful and is related to eigenvector centrality is what's known as boniage centrality。

 or cat's bosage centrality， It's actually builds on a definition originally by cats that was later extended by Phil Bosage。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_25.png)

And the idea is that you give each node some base value and the base value is some number a times the degree of a node so if I have degree 10 and a is a half。

 then I start with a value of five， and so everybody starts with some value proportional to their degree。

And now you add in all paths of length1 from I to some J times B times J's base value。

So I get some fraction of my neighbors value。 So let's say that B is a third。

 So now I've got a base value。 plus I add in one third times my friends's base values。

 Then I go to length2 and I add in B squared times those people's value。

 So if this is you know one half times my friends or sorry， one third times my friends values。

 Now this is going be one ninth times friends of friends values right so I can go out length two walks of length2。

 some of them might come back to me。 So it sort of counts these things doubly。

 But what it's doing is just counting。 So I get a times my degree。

 which is just G times a vector of ones。

![](img/c07db15a8da6387ea00f0f8a8e326d4f_27.png)

Then I get B times walks of length2。 Remember G squared gives us walks of length 2。

 So I'm getting B times the connections of length2。 I have times their base values。

 then B squared times length 3 and so forth。 So what we end up with is this calculation where we're sort of raising G to successive powers and then weighting that by some level B。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_29.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_30.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_31.png)

And if we normalize the A here to1 is just multiplying the whole thing。

 then basically this thing is going to be like a sum of a series。

 and I'm getting more value from indirect walks times the value of those nodes。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_33.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_34.png)

If you want this thing to be convergent so that actually gives you a number。

 B is going to have to be relatively small in order for that to be finite。

 it's going to have to depend on the magnitude of the matrix the largest eigenvalue but a small enough B we'll make sure that this thing converges so when we look at bos centrality then we can go through and calculate this for different values and you know go through and for instance then the Medidici again appear more important than some of the other families so this kind of calculation gives you something like eigenvector centrality and in fact for B being close enough to one over the largest eigenvalue of the matrix then it's going to begin to approach eigenvector centrality but more generally it can diverge from them and depending on what be's you work with。

 you're going。

![](img/c07db15a8da6387ea00f0f8a8e326d4f_36.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_37.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_38.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_39.png)

different notions， so here if we normalize a to1 and work with different Bs。

 we can get different values of boes centrality out and know it's going to be another measure of centrality。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_41.png)

Basically we've got a whole sequence of different measures of centrality。

 some of them are going to work better in some context than others。

 exactly how we do that and which ones are going to be right for which context depends on what we're studying and again there's sort of four different ideas that we've gone through degree is just getting basic connectedness of a node。

 how many neighbors does it have， then there's things like how close are you。

 how easily can you access other nodes， then there's connectorbased definitions so how important are you as an intermediary and then there are these sets of influence prestige and eigenvectors sorts of things that are capturing not only who you know but waiting them by their importance and doing sort of iterativeg of calculations that will capture importance of the value of your friends as measuring your own importance。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_43.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_44.png)

So what we'll do is now we'll have a quick look at one application which will distinguish which one of these centrality measures does well and which ones don't in a particular setting。

 and then we'll start to move on and trying to understand a little bit more about formation of networks。



![](img/c07db15a8da6387ea00f0f8a8e326d4f_46.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_47.png)

![](img/c07db15a8da6387ea00f0f8a8e326d4f_48.png)