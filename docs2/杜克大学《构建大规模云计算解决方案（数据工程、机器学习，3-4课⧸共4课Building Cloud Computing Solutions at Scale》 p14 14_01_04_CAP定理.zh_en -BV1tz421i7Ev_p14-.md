# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p14 14_01_04_CAP定理.zh_en -BV1tz421i7Ev_p14-

![](img/f05a135e97c661954461620cd068e458_0.png)

One of the fundamental theorems in distributed computing is the Cap theorem。

 and what it means is that theres a trade off between consistency， availability， and fault tolerance。

What this means in practice is that， let's say in the case of consistency。

 you can see that the same data is received for every request。In the case of availability。

 every request receives a healthy response and in the case of fault tolerance。

 the system continues to function。As messages drop between nodes。

You can only have two to three of these and in particular from， let's say 1970 forward。

 what happened was you would have consistency being really the primary driver of a relational database because it handled。

 let's say bank transactions and the tradeoff though was a lot of times there were scale issues because you had to decide between fault tolerance or availability。

 a good example would be if you had a relational database and you had some read replicas that are associated with it。

 well the read replicas if you call into these things they're going to be highly available。

But maybe the fault tolerance will be slightly changed because of the nature of how the read replica works。

 likewise in terms of consistency， because in the case where the read replicas are not getting the data at the exact same time as the right。

 you could get a slightly older version of the data because the read replicas are only copying the reads and the rights are happening slightly different。

 so there's a tradeoff there in terms of relational database。

Things have gotten even further down the road of picking between consistency availability and fault tolerance with key value databases and a good example of that is。

Amazon Dynamo Db。And with DynamoDb， it's eventually consistent meaning that it can scale out to any number of requests because it doesn't really matter if let's say two people visit a website and there's a slightly different piece of news with let's say three or four different words in it than the other that's not that important to be consistent about you know if they refresh the page it'll update Now if it's a bank balance that's a totally different thing and that's why a relational database could be great for that particular scenario so in the cloud you have lots of different choices of how to pick between these three options。

 but you can't get all three at the same time。

![](img/f05a135e97c661954461620cd068e458_2.png)