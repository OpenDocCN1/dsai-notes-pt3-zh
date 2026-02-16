# 杜克大学《大型语言模型实践（高级数据工程、AWS、Databricks和本地LLM）｜Large Language Model Operations 》 - P110：09_01_10_通用集群与作业集群对比.zh_en - GPT中英字幕课程资源 - BV1oi421Q7GT

![](img/2e8e3d845d81641db64d3e3e26b17100_0.png)

Let's take a look at this concept of all purpose compute。

 which is things like a general cluster or building ML clusters。

And this is one type of compute that works very well for notebooks or for other things you're doing。

 But there's a different type called a job cluster。

 Let's go ahead and look at that by going to data engineering job runs。 And if we go over here。

 what we can see is this was a previous run that I did， it was successful。

 it took about six minutes And so I can see all of my runs here and it's a great way to really have an interface that I can see where things have been failing or succeeding or whether I skipped one。

 Now if we go over to create job。 you'll see that I can actually dive into what a job cluster is。

 So by default。 you'll get this job cluster。 And the idea here is that a job cluster is optimized and dedicated to run production jobs。

 And so auto scalinging is enabled by default to handle the job load and it's gonna to terminate automatically after being idle for a set time。

 So this is really ideal for doing scheduled ETL pipeline。



![](img/2e8e3d845d81641db64d3e3e26b17100_2.png)

And recurring batchsh processing。The all purposeurpose clusters are more for interactive general data analysis。

 So if we went through here and we said test and I went through and I selected the notebook that I was going to use。

 here's where we would see the job cluster and you can see that this job cluster has slightly different characteristics than the all purposeurpose cluster right it has bigger memory so 126 gigs 36 cores and it's also going to delineate by saying here that it's a job cluster and it's going to say that the existing all- purposeurpo clusters are different than these。

 So this is just another tool that you have in your toolkit if you're going to be running batch-based jobs doing ETL operations this is a great way to get things going。

