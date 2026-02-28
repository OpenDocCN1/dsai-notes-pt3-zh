# 杜克大学｜机器学习运维｜DevOps⧸DataOps、Azure、MLFlow和抱脸｜MLOps ｜ Machine Learning Operations p08 15_01_02_微服务运维化.zh_en -BV1yE421c7uA_p8-

![](img/7fa6dc6678def0dcb52cec3923255526_0.png)

Here we have a diagram of operationalizing a microservice。

 noticeice that in Git some of the advantages of a microservice come alive。

 I really like to think about a microservice in terms of the concept of logic that you go live with some of the characteristics are that it is small and it's reusable code So you can maybe turn this into a commandlan tool。

 you can turn it into a library。 you can of course make a microservice out of it。

 You can also convert it into a dockcker container。

 All of these are characteristics of a microservice。

 It's really like a function that you've operationalized and turn it into something new。

 Now if you go to the continuous delivery system of the build server。

 it'll go through the steps of Liing testing compiling maybe pushing this into a container repository and then finally deploying through infrastructure as code。

 What this does by using infrastructure as code， coupled with， let's say a container。

that you can create any number of environments， you can create a staging environment。

 you can create a production environment， you can create a load test environment。

 you can create a development environment， and you can do automated things depending on which environment it gets deployed to。

 So in the case of the staging environment and this is something I've done in my career you have a microservice that has health metrics like CPU memory latency。

 these are all monitored in some kind of monitoring system like Prometheus or potentially cloudwa from AWS and then you do a performance verification and what this is really doing is verifying that what you think will happen will actually happen。

Once this is actually approved， you can easily just merge this into a new branch and push it。

Directly into production。 So really a microservice。

 the simplest possible explanation is it's logic that you push live。



![](img/7fa6dc6678def0dcb52cec3923255526_2.png)