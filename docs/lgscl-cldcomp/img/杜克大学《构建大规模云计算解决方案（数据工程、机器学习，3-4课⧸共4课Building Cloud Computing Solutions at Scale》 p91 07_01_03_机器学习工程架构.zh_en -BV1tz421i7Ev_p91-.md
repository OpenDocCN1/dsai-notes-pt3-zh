# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p91 07_01_03_机器学习工程架构.zh_en -BV1tz421i7Ev_p91-

![](img/e7033d522cc34dad929ab1548821af13_0.png)

Let's walk through what a typical machine learning architecture will look like。

You'll start with a microservice here and in this microservice you'll have an API that's exposed via the web and that's where all the requests will come in and in fact you'll have a JSN payload here that will have the serialized data go into this service and that service will then go and make a prediction and what are the subcomponents of a microservice well you could have a Python Flask gap here which could be you let's say 50 to 100 lines of code you could have a model already built and it's inside of the actual project and included in it。

Perhaps is even versioned and then also you could have some kind of container technology it could be either serverless where the cloud vendor itself is already managing that container or it's a direct Docker type file that contains all of the different characteristics of the runtime but really those are the three components of machine learning microservice。

 the web application code， the model in the container now how do you actually deploy this model and what would be the process and doing this well you would be continuously delivering that data and also the application as is checked into source control and the data itself would come from this data lake infrastructure here。

 and this data lake would allow you to detect things like maybe data drift and datad is something where you would monitor whether there were changes from the last time。

madeade the model and if the drift appears to be you know let's say over 25% right the data has changed more than 25% than the last time。

 then potentially that would automatically trigger a rebuild on the model and you would redeploy a new version of the machine learning system so this feedback loop is really important and it's constantly you know in flux and its dynamic。

And that's really the most important component of this and if you remember a microservice is intentionally simple。

 so there are only three moving pieces here now the final component here which is often overlooked is that a production system is going to have some kind of a monitoring dashboard and health alerts that people will look at to determine whether the service is successful and this is a critical component。

 this dashboard here could have everything from let's say the response time in terms of latency all the way to whether the model's prediction is still accurate and this is a finishing touch that isn't optional in a production environment but in a nutshell。

 this is a good overview of essentially like a checklist of what you need to build a machine learning system。



![](img/e7033d522cc34dad929ab1548821af13_2.png)

![](img/e7033d522cc34dad929ab1548821af13_3.png)