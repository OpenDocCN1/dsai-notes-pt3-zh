# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p05 05_01_02_摩尔定律终结导论.zh_en -BV1tz421i7Ev_p5-

![](img/aeef990012c12c62c5a755811c7a7178_0.png)

In this lesson we aim to understand the end of Moore's law。

 Moore's law states that the processors every 18 months or so would double in speed and for a long time that occurred。

 but now things have changed and we're going to talk about some of the implications of the end of Moore's law let's go into the learning objectives。



![](img/aeef990012c12c62c5a755811c7a7178_2.png)

First， we analyze different approaches to concurrency， there's network concurrency。

 there's process concurrency， there's GPU concurrency， we talk about a few of those tradeoffs。

Then we evaluate the tradeoffs in different chip types。

 there are many different specialized chips that we'll get into and we'll talk about some of the things that occur when you use a different chip other than just a CPU。

We'll also evaluate ASI use cases， ASIs are application specific integrated circuits and they're used in very specialized scenarios like machine learning or in graphics processing。



![](img/aeef990012c12c62c5a755811c7a7178_4.png)

Let's go through and look at a key term KUa， Kuda stands for Compute Unified device Architure。

 and it's an API for the NviIDdia GPU， which is one of the most popular graphics processing units by the company NviIDdia。

We also dive into parallel computing and we talk about this with KUDa and we realize that parallel computing and programming are all something that occur using the KUDa SDK。

Asics stand for application specific integrated circuit。

 and they're a new trend especially in terms of machine learning and cloud computing。

They're a chip that's customized for a particular use case， like， for example， Bitcoin。

 graphics processing， machine learning， or lower power devices。

 and there'll be something thatll come up again and again with cloud computing。

Some good examples of A6 that are used today are TPUs or TensorFlow processing unit from Google。

 a GPU， a graphics processing unit or an FPGA。Which is a programmable chip that are used for specialized workflows。

 let's say for cryptocoin mining。

![](img/aeef990012c12c62c5a755811c7a7178_6.png)