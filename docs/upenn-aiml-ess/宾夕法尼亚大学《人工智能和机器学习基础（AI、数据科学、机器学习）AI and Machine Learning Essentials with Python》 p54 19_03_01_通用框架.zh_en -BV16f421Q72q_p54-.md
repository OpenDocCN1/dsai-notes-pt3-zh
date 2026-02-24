# 宾夕法尼亚大学《人工智能和机器学习基础（AI、数据科学、机器学习）AI and Machine Learning Essentials with Python》 p54 19_03_01_通用框架.zh_en -BV16f421Q72q_p54-

Let me just put everything in a broader perspective。

 Let's see what we have learned and how we can generalize the concepts that we have learned。 Okay。

 so what so far we have， we have had this kind of。

![](img/261f060190a1af5e63c4ac19c5b53927_1.png)

![](img/261f060190a1af5e63c4ac19c5b53927_2.png)

![](img/261f060190a1af5e63c4ac19c5b53927_3.png)

Block diagram， right， So there is some real world。Physical phenomenon。



![](img/261f060190a1af5e63c4ac19c5b53927_5.png)

That we want to learn about， right？

![](img/261f060190a1af5e63c4ac19c5b53927_7.png)

Some underlying kind of parameters that we want to learn， for example。

 the average height or the percentage of people who would who we would like to estimate the percentage that would vote for a certain candidate。

 Okay， so there are some parameters。

![](img/261f060190a1af5e63c4ac19c5b53927_9.png)

![](img/261f060190a1af5e63c4ac19c5b53927_10.png)

Some quantities here that we want to estimate about this real world for now。



![](img/261f060190a1af5e63c4ac19c5b53927_12.png)

![](img/261f060190a1af5e63c4ac19c5b53927_13.png)

And for that， we are collecting data， so there is this data。quicquisition module， Okay。

 so that gives us。

![](img/261f060190a1af5e63c4ac19c5b53927_15.png)

X found through x and the data points。

![](img/261f060190a1af5e63c4ac19c5b53927_17.png)

Okay， now what's important about these data points is the is the concept of random example。

 so statistically。

![](img/261f060190a1af5e63c4ac19c5b53927_19.png)

We model our sequence of data points x1 through Xn。



![](img/261f060190a1af5e63c4ac19c5b53927_21.png)

To be random variables Xs that are。

![](img/261f060190a1af5e63c4ac19c5b53927_23.png)

Identically and independently distributed。 Okay， so in short， we say I I D， in other words， each X I。



![](img/261f060190a1af5e63c4ac19c5b53927_25.png)

![](img/261f060190a1af5e63c4ac19c5b53927_26.png)

Is independent from the other data points？That's property number one， the independence， all these。



![](img/261f060190a1af5e63c4ac19c5b53927_28.png)

Data points that we have。Or samples that we have obtained regarding this real world phenomenon are independent from each other。

 And the second important thing is that they are identically distributed Okay。

 they have the same distribution right because they are generated regarding the same phenomenon。



![](img/261f060190a1af5e63c4ac19c5b53927_30.png)

![](img/261f060190a1af5e63c4ac19c5b53927_31.png)

![](img/261f060190a1af5e63c4ac19c5b53927_32.png)

![](img/261f060190a1af5e63c4ac19c5b53927_33.png)

So that's the IID assumption that we make about Xs。



![](img/261f060190a1af5e63c4ac19c5b53927_35.png)

So that's the statistical assumption that we're going to work with throughout the course about the data。

😊。

![](img/261f060190a1af5e63c4ac19c5b53927_37.png)

And once we have Xs， we're going to process them， so this is the data。



![](img/261f060190a1af5e63c4ac19c5b53927_39.png)

Analysis。

![](img/261f060190a1af5e63c4ac19c5b53927_41.png)

Module。😊，Okay， we're going to process them。

![](img/261f060190a1af5e63c4ac19c5b53927_43.png)

To essentially to obtain some knowledge or about the underlying real world phenomenon now。 Okay。

 so we we will compute some kind of function。

![](img/261f060190a1af5e63c4ac19c5b53927_45.png)

![](img/261f060190a1af5e63c4ac19c5b53927_46.png)

Of data x through Xn。

![](img/261f060190a1af5e63c4ac19c5b53927_48.png)

Which would give us some property about the real work， for example。

 the sample mean something that we have been for working on so far Okay so EG。



![](img/261f060190a1af5e63c4ac19c5b53927_50.png)

![](img/261f060190a1af5e63c4ac19c5b53927_51.png)

The sample right， that could be the function of the data points that we have appear compute。



![](img/261f060190a1af5e63c4ac19c5b53927_53.png)

So this function is typically called a statistic， a statistic of the date， okay？😊。



![](img/261f060190a1af5e63c4ac19c5b53927_55.png)

In other words by a statistic， we just mean a function of the sample data that we are computing a basic definition is this a statistic is a quantity whose value can be computed from some sample data is a function of the sample data and what's important here is that the outcome of the statistic is a random value because data happens randomly so X is are random variables as a result the outcome of the statistic would be a random variable。



![](img/261f060190a1af5e63c4ac19c5b53927_57.png)

![](img/261f060190a1af5e63c4ac19c5b53927_58.png)

![](img/261f060190a1af5e63c4ac19c5b53927_59.png)

![](img/261f060190a1af5e63c4ac19c5b53927_60.png)

![](img/261f060190a1af5e63c4ac19c5b53927_61.png)

![](img/261f060190a1af5e63c4ac19c5b53927_62.png)

![](img/261f060190a1af5e63c4ac19c5b53927_63.png)

Okay， you know， I mean， as an example， so far or a statistic or the function of the data that we have been trying to compute was export the average of the data points Xs right and export is a random variable because X is are random variable。

 So the outcome of this a statistic， whatever we compute from data is a random value variable And we need to analyze is different properties right for example。

 so far we have computed expectation and the mean of this random but what's important to note here is that export this statistic that we compute from data is in general。

 a random variable。

![](img/261f060190a1af5e63c4ac19c5b53927_65.png)

![](img/261f060190a1af5e63c4ac19c5b53927_66.png)

![](img/261f060190a1af5e63c4ac19c5b53927_67.png)

![](img/261f060190a1af5e63c4ac19c5b53927_68.png)

![](img/261f060190a1af5e63c4ac19c5b53927_69.png)

![](img/261f060190a1af5e63c4ac19c5b53927_70.png)

![](img/261f060190a1af5e63c4ac19c5b53927_71.png)