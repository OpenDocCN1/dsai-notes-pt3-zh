# 华盛顿大学《机器学习（分类，聚类和检索，第3-4课⧸共4课）｜Machine Learning》中英字幕 p147 25_简要回顾.zh_en -BV1Sr421F7N7_p147-

。

![](img/4ccdc65bf2cd3f14ea095f3d42424534_1.png)

So in summary we've covered a lot of ground in this module。

 so we've returned to this task of retrieving a document of interest and formulated this in terms of performing nearest neighbor search we reviewed our nearest neighbor search algorithms for performing one nearest neighbor search as well as K nearest neighbors search but we got into some of the nitty gritty of these algorithms in particular thinking about how do we represent our data so we focus here on different representations of documents but we also talked about the really really critical idea of how do we compute distances between two different data points and we went through a set of different ways to compute these types of distances and discussed the tradeoffs that we're faced with and the fact that there's really no one answer for what's the right data representation and what's the right distance to use and that's where a lot of domain knowledge comes in and can have a lot of impact on the performance of the algorithms and you really have to think very critically there。

But then for the rest of the module we talked about ways to think about performing really efficient nearest neighbor search to help handle the fact that the brute force search when you have lots and lots of observations can be really。

 really， really computationally intensive， so we talked about Kd trees as a very efficient data structure that we can use for performing our nearest neighbor search。

And we showed when it can be useful， but we also said that it struggled in high dimensions。

 So then we turned to this idea of locality sense of hashing。

 which only provides approximate nearest neighbors。

 but we motivated that that can actually be reasonable and a really large set of different applications。

 but this locality sense of hashing is really， really really simple to implement and can be very efficient and provide good approximations that have probabilistic guarantees on the approximations made。

 So coming out of this module， you really have some really powerful tools that are useful in just a huge number of retrieval tasks going beyond document retrieval。

 lots and lots of applications where you have some query and you want to find some similar object and all the tools that we've discussed in this module generalized to these other applications as well。

 And so I'll just leave you with a summary of a set of things that you should be able to do now that you've seen this module。



![](img/4ccdc65bf2cd3f14ea095f3d42424534_3.png)

![](img/4ccdc65bf2cd3f14ea095f3d42424534_4.png)