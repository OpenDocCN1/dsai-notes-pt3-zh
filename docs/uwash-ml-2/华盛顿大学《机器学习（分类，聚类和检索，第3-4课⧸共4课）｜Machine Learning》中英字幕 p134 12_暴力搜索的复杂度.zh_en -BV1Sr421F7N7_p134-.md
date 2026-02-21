# 华盛顿大学《机器学习（分类，聚类和检索，第3-4课⧸共4课）｜Machine Learning》中英字幕 p134 12_暴力搜索的复杂度.zh_en -BV1Sr421F7N7_p134-

。

![](img/20917ecba83f8c97dffdb81be3fc13cf_1.png)

We've set up how to perform nearest neighbor search in terms of describing the algorithm that we have to run through and then spending some time discussing two really critical components of that algorithm。

 The first being， how do we represent our documents of interest and the second being。

 how do we compute the distance between two different documents。

And we show that those two components are really， really important for the performance of the method。

 but now I want to spend a little bit of time thinking about how computationally intensive doing nearests neighbor search can be。



![](img/20917ecba83f8c97dffdb81be3fc13cf_3.png)

And we refer to this as the complexity of search。

![](img/20917ecba83f8c97dffdb81be3fc13cf_5.png)

Okay， so what's the complexity of brute force search。 So let's say we have a given query point。

 What do we need to do， Well， we need to scan through all the documents of the corpus。

 Compute the distance to each one。And then we have to say， okay， which is the smallest distance。

 So what's the complexity of doing that， Well， for a one nearest neighbor query。

 we have to compute n different distances。 So the complexity is order capital N number of documents in the corpus。

 And if we want to do K nearest neighbors。 So return the K nearest documents。

 then the complexity is order n log K， And the reason we get that log K term is if we do a smart implementation where we maintain this priority Q and insert into the priority Q in an efficient manner。

Okay， but what if n is really， really large and importantly， what if you have to do many。

 many queries on this corpus again and again and again and again。

Is there something we can do that's more efficient than this brute force search？



![](img/20917ecba83f8c97dffdb81be3fc13cf_7.png)