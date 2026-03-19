# 图宾根大学【中英⚡机器学习数学｜2020 Tübingen Mathematics for Machine Learning】 p74 P74 (P) Probability theory 21： Conditional expectation -BV1VhbMzKEts_p74-

![](img/e3097fd075ee701a1e9221f53c4e22c8_0.png)

In the last lecture， we've already seen conditional distributions in case when all our distributions have the form of densities。



![](img/e3097fd075ee701a1e9221f53c4e22c8_2.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_3.png)

Now I want to start introducing this slightly more general concept all then， in fact。

 not only slightly more general concept， but much more general concept。



![](img/e3097fd075ee701a1e9221f53c4e22c8_5.png)

And to introduce this concept， we need the conditional expectation。



![](img/e3097fd075ee701a1e9221f53c4e22c8_7.png)

This is something you need to define these conditional distributions in general。

 but also it happens quite often maybe not so much in standard statistical learning but inrobabilistic method of machine learning that you integrate one variable with respect to or conditioned on some other variable。

 and then you need to look at conditional expectations。



![](img/e3097fd075ee701a1e9221f53c4e22c8_9.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_10.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_11.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_12.png)

So when I learned about conditional expectations in my maths degree， you learned a very。

 very abstract way， and it took me when I started to become a PhD student in computer science。

 it took me really months to understand what is really how can I map this very abstract concept that I've seen in mathematics to all these heuristic manipulations everybody in machine learning simply does without thinking about it。

 So this is something that can be quite complicated。

 I try to give you some of the intuition in the next half an hour also in next 50 minutes。

 I don't know but I already want to warn you this is a topic that is also not so simple and I don't expect you to digest all of this right now this takes a large amount of work to really understand what's going on here。

 but I try to do my best in this lecture。

![](img/e3097fd075ee701a1e9221f53c4e22c8_14.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_15.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_16.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_17.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_18.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_19.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_20.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_21.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_22.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_23.png)

I want to start with very simple cases， conditional expectations。

 So assume we have two random variabless， x and Y。

![](img/e3097fd075ee701a1e9221f53c4e22c8_25.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_26.png)

And we want to compute the expectation of y under the assumption that we already know something about the outcome of x。



![](img/e3097fd075ee701a1e9221f53c4e22c8_28.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_29.png)

And in the discrete case， this is something that is very simple to do。

 and maybe we start with this because here it's easier to see what is going on。



![](img/e3097fd075ee701a1e9221f53c4e22c8_31.png)

嗯。

![](img/e3097fd075ee701a1e9221f53c4e22c8_33.png)

So maybe I write a definition。

![](img/e3097fd075ee701a1e9221f53c4e22c8_35.png)

In the discrete case。

![](img/e3097fd075ee701a1e9221f53c4e22c8_37.png)

We consider to random X。And why。

![](img/e3097fd075ee701a1e9221f53c4e22c8_39.png)

They live on the same probability space。

![](img/e3097fd075ee701a1e9221f53c4e22c8_41.png)

And take real values。 So in all what happens now is these conditional expectations only between two random orbits only work if these random orbits are defined on the same space。



![](img/e3097fd075ee701a1e9221f53c4e22c8_43.png)

![](img/e3097fd075ee701a1e9221f53c4e22c8_44.png)