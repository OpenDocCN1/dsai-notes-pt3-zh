# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p17 17_01_07_高可用性与九个九.zh_en -BV1tz421i7Ev_p17-

![](img/d3eabab6b33db13f47cf9605b0d3d7b3_0.png)

Highly available is another key term in cloud computing。

 and what it means is the amount of time that your system is available。

In a service contract for a SAS system， a lot of times you'll hear this highly available terminology and also uptime or service level agreement and in particular the 99s what that means would be that there's literally 99。

999 all the way to 99s availability and that equates to 31 milliseconds of downtime currently Amazon S3 as an example has I believe 119s availability and what that means is that there's essentially a millisecond or so of downtime per year。

How do they do this， Well， what they do is they have multiple copies， So you've got a copy here。

 you've got a copy here， you've got a copy here and you load balance things across all of those different regions。

 So the same data lives many different times in many different regions globally distributed and that's how you can have a highly available architecture Now a lot of times this would be almost impossible for a regular company to build on their own and that's why cloud computing is a great way to accomplish this because you can use the highly available infrastructure like。

 for example， S3 to distribute object storage across the globe and you didn't have to build that。

 you just pay for the services that you use at that time。

 So highly available is an important term to be aware of and also some of the decimals right99s119s and what those equate to is the uptown time that your service is going to be available to your customer。



![](img/d3eabab6b33db13f47cf9605b0d3d7b3_2.png)