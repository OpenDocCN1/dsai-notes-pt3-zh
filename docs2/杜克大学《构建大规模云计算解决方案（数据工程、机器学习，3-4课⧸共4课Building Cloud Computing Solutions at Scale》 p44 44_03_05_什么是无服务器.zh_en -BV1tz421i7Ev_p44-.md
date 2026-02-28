# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p44 44_03_05_什么是无服务器.zh_en -BV1tz421i7Ev_p44-

![](img/9b332be347dda62d9017f476349604c6_0.png)

What is serverless， It's a technique that uses an abstraction where you don't have to worry about the servers underneath that are doing all the work。

 So， for example， AWS Lambda beneath the hood， it could be using Kubernetes or Docker containers to do all the heavy lifting。

 but you don't have to think about it。 you just write the Python function that does some work and maybe attaches to a trigger。

 Likewise， there are other kinds of serverless technologies like AWS Athena， for example。

 can look at an S3 bucket and combine a bunch of data and do SQL queries on it。

 but you not necessarily worrying about the servers themselves。

 So that's really the idea with serverless is it isn't that the servers aren't there。

 It's that you don't have to worry about it and you focus only on the business logic。



![](img/9b332be347dda62d9017f476349604c6_2.png)