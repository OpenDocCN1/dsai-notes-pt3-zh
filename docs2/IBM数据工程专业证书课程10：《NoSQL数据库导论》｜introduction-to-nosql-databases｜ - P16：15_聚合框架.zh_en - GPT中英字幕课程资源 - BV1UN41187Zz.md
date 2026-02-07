# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P16：15_聚合框架.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/28b03e413c3ccc3ee20adef2c63edb5c_0.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_1.png)

Welcome to Aggregation Framework。

![](img/28b03e413c3ccc3ee20adef2c63edb5c_3.png)

After watching this video， you will be able to explain what aggregation frameworkra is in MongoDB。

 describe how it is built and what the most common stages are。

 and describe where you can use aggregation。

![](img/28b03e413c3ccc3ee20adef2c63edb5c_5.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_6.png)

Aggregation Frame， which is also sometimes referred to as aggregation Piline。

 is a series of operations that you apply on your data to get a desired outcome for example。

 to understand whether students are really developing their knowledge。

 you want to see the average student scores in 2020 by course。

 this will mean filtering 2020 documents， then grouping those documents by course。

 then calculating an average score per year。

![](img/28b03e413c3ccc3ee20adef2c63edb5c_8.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_9.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_10.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_11.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_12.png)

In our example， we have used the stages Dollar St Mat to filter out documents from year 2020 and Dollar sign group to group documents from the last stage using course ID and calculating the average in a field called average score It is like a pipeline。

 documents enter from one side， go through one or more processes and come out in the desired format at the other end。



![](img/28b03e413c3ccc3ee20adef2c63edb5c_14.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_15.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_16.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_17.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_18.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_19.png)

An aggregation stage can be repeated in a pipeline。

 and the most common stages are Dollar sign project if you want to change the shape of documents or project out certain fields。



![](img/28b03e413c3ccc3ee20adef2c63edb5c_21.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_22.png)

Dollar Sign sort to sort your documents。

![](img/28b03e413c3ccc3ee20adef2c63edb5c_24.png)

Dollar sign count to count and assign the outcome to a field called Total Students and Doar sign merge。

 which takes the outcome from the previous stage and stores it into a target collection。



![](img/28b03e413c3ccc3ee20adef2c63edb5c_26.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_27.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_28.png)

Now that we understand what different stages are in the MongoDB aggregation pipeline。

 let's talk about where you will use it Like we saw earlier。

 it can be used to track the progress of students by course another example could be in an e-commerce application the average sale of a product per country these kinds of reports can easily be created through the aggregation pipeline these can be complex calculations or simple grouping of data to provide a different picture of the data。



![](img/28b03e413c3ccc3ee20adef2c63edb5c_30.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_31.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_32.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_33.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_34.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_35.png)

In this video， you learned that using an aggregation framework。

 you can perform complex analysis on the data in MongoDB。

 you can build your aggregation process in stages such as match， group， project。

 and sort and that the outcome can be queried or stored into another collection using Doar sign merge。



![](img/28b03e413c3ccc3ee20adef2c63edb5c_37.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_38.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_39.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_40.png)

![](img/28b03e413c3ccc3ee20adef2c63edb5c_41.png)