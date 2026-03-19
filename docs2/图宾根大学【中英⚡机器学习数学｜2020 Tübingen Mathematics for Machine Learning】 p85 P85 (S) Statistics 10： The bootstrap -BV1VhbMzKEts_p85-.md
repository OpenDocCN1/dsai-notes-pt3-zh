# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p85 P85 (S) Statistics 10： The bootstrap -BV1VhbMzKEts_p85-

![](img/ff7204bd67457d1c2884353767ea40b3_0.png)

Good morning today we want to discuss the bootstrap which is a very generic and general and also powerful method in statistics in particular in nontermetric statistics。



![](img/ff7204bd67457d1c2884353767ea40b3_2.png)

![](img/ff7204bd67457d1c2884353767ea40b3_3.png)

So consider you're in a situation where you have to make an estimate of a complicated quantity and you don't have any distribution assumptions。



![](img/ff7204bd67457d1c2884353767ea40b3_5.png)

![](img/ff7204bd67457d1c2884353767ea40b3_6.png)

So consider a medical quantity or something like， I don't know。

 estimating the correlation between school grades and family income。

 it would be really difficult to have distribution assumptions for these kind of estimates。



![](img/ff7204bd67457d1c2884353767ea40b3_8.png)

![](img/ff7204bd67457d1c2884353767ea40b3_9.png)

![](img/ff7204bd67457d1c2884353767ea40b3_10.png)

Or if you want to run a test on such data。

![](img/ff7204bd67457d1c2884353767ea40b3_12.png)

However， Botra provides a method by which we can still do use for statistics。

 even if we don't know any or if we don't have any distribution assumptions。



![](img/ff7204bd67457d1c2884353767ea40b3_14.png)

![](img/ff7204bd67457d1c2884353767ea40b3_15.png)

We have already in one of the last lectures seen a couple of different methods for nonparmetric statistics and maybe the one that is closest to the bootstrap is permutation tests。



![](img/ff7204bd67457d1c2884353767ea40b3_17.png)

![](img/ff7204bd67457d1c2884353767ea40b3_18.png)

Because in permutation test， what you do is you're given the sample of your data and then you randomly scramble your data test in the permutation test。

 you scramble the label of your data， the class membership。



![](img/ff7204bd67457d1c2884353767ea40b3_20.png)

![](img/ff7204bd67457d1c2884353767ea40b3_21.png)

![](img/ff7204bd67457d1c2884353767ea40b3_22.png)

So you reample your data by doing something slightly different and then use the resample data to estimate。

 for example， what might be a confidence interval or what might be the standard deviation of an estimate。



![](img/ff7204bd67457d1c2884353767ea40b3_24.png)

![](img/ff7204bd67457d1c2884353767ea40b3_25.png)

![](img/ff7204bd67457d1c2884353767ea40b3_26.png)

Now the bootsstrrap is a more generic method of achieving something similar。

 and before I want to outline how it really works， let me maybe again come up with a bit of motivation。



![](img/ff7204bd67457d1c2884353767ea40b3_28.png)

![](img/ff7204bd67457d1c2884353767ea40b3_29.png)

So assume we have a sample， some motivation。

![](img/ff7204bd67457d1c2884353767ea40b3_31.png)

Assume we have a sample x1 xn that comes from some distribution F。

 but we do not have any assumptions on the underlying distribution typically。



![](img/ff7204bd67457d1c2884353767ea40b3_33.png)

![](img/ff7204bd67457d1c2884353767ea40b3_34.png)

If。

![](img/ff7204bd67457d1c2884353767ea40b3_36.png)

Maybe I write no assumptions on F。But are no knowledge。On F， I mean beyond the sample， of course。

 that we observe。

![](img/ff7204bd67457d1c2884353767ea40b3_38.png)

And we want to estimate。

![](img/ff7204bd67457d1c2884353767ea40b3_40.png)

A parameter。

![](img/ff7204bd67457d1c2884353767ea40b3_42.png)

Some kind of statistics， the average correlation， or if you want to mean that would be sort of the simplest space。



![](img/ff7204bd67457d1c2884353767ea40b3_44.png)

![](img/ff7204bd67457d1c2884353767ea40b3_45.png)