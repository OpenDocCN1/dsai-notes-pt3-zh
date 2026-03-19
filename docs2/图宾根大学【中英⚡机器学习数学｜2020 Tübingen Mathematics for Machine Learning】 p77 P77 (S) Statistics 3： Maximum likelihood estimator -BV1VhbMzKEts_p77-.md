# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p77 P77 (S) Statistics 3： Maximum likelihood estimator -BV1VhbMzKEts_p77-

In the last lectures， we have looked at statistical estimation programs。

 we have a family of distributions that is described by parameter and our goal is to estimate this parameter。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_1.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_2.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_3.png)

The only examples we've done so far were very simple examples where you want to estimate the mean of the distribution or the variance or something like that。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_5.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_6.png)

Now the problem is in machine learning， we rarely want to estimate that。

 I mean it's also nice to estimate the mean， but typically we want to estimate something that is much more complicated and then it is very difficult to write down immediately what a closed form solution for your estimate is。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_8.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_9.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_10.png)

And sometimes you can still write down a closed form。

 but it is not so obvious to derive the closed form。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_12.png)

And I want to start with an example。😊。

![](img/7d029b60a8c64a0842faf1d18aefb4f1_14.png)

I can't resist， it comes from a paper we published last year， it's called Net Gun Without Gu。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_16.png)

And here the scenario is the follow following。 So as you， we are given a graph。 And so in our case。

 the statistical model consists of all kinds of graphs。 So this is the set of。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_18.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_19.png)

嗯。In times in matrices， I right maybe。

![](img/7d029b60a8c64a0842faf1d18aefb4f1_21.png)

A matrix a。A symmetric。

![](img/7d029b60a8c64a0842faf1d18aefb4f1_23.png)

The entries are all AIJ， are either zero or1。

![](img/7d029b60a8c64a0842faf1d18aefb4f1_25.png)

And this is supposed to be in the adjacency matrix of a graph。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_27.png)

I just write adjacency matrix。

![](img/7d029b60a8c64a0842faf1d18aefb4f1_29.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_30.png)

The adjacentency matrices of graphs。Say of size in。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_32.png)

Maybe I write asymmetricsymmetricsymmetric。 It would be an n times n matrix。 So n is known。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_34.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_35.png)

And it's supposed to be the adjacency matrix of a graph。So the ideas in the background。

 we have some graphs， say a social network or brain graph or climate graph。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_37.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_38.png)

Whatever scientific phenomenon you want to look at and that can be modeled paragraph graph。

 so assume we have a brain graph to make it concrete concrete。

 100 vertices that symbolize different regions in the brain and some edges if these regions in the brain talk to each other。

 something like that。

![](img/7d029b60a8c64a0842faf1d18aefb4f1_40.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_41.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_42.png)

And now our as is something complicated because here there's nothing random so far。

 so a is sort of that's the parameterization， we know that there's a graph in the back。



![](img/7d029b60a8c64a0842faf1d18aefb4f1_44.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_45.png)

![](img/7d029b60a8c64a0842faf1d18aefb4f1_46.png)