# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p21 21_01_05_数据湖.zh_en -BV1tz421i7Ev_p21-

![](img/a07a7ebab97d64c947d575f18298604c_0.png)

Let's talk through one of the most important concepts in big data， which is a data lake。

It's somewhat self-explanatory if you think about what a lake is。

 it's a big body of water that holds things for a town or a city and oftentimes you'll use this lake to go fishing or to as a reservoir for drinking water it's a similar concept with a lake for data is that your data all flows in and once the data flows into this lake in the center here it can be processed in the same spot that the data lives。

 which is a key takeaway with the data lake so S3 has a high reliability。

 it has the ability to infinitely scale up in terms of the request and so that means that。

If you wanted to create a dashboard right in terms of analytics。

 you could go through and directly access that S3 location and do analytics on the data lake。

 likewise if you wanted to do realtime stream processing。

 you could also connect to the data as it goes into S3 and in realtime process the data。

Another thing is you could have an on premise system。

 let's say another third party data center synchronized with this S3 location。

 and that's where you could process your data is you could you know bring it up to the cloud and then have the cloud do some operation finally。

With machine learning， this is a key takeaway is a lot of times。

 especially with a deep learning problem， it's not possible to do that on a laptop or even a physical data center and so if the data is already in S3 or whatever cloudbased data lake system you're using you have your machine learning system directly access that data。

 process it， do the training and then put the model back down into the data lake and so this is really the concept here is that instead of you moving the data around and you can see this here。

 you can work on the data without moving it back and forth。

 you also can do analytics and machine learning， you can deal with structured and unstructured data and it's actually a very lowco storage system and potentially it could be much lower than buying that hardware yourself and maintaining it。



![](img/a07a7ebab97d64c947d575f18298604c_2.png)