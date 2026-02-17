# 杜克大学《大型语言模型实践（高级数据工程、AWS、Databricks和本地LLM）｜Large Language Model Operations 》 - P24：24_02_04_什么是Apache Airflow.zh_en - GPT中英字幕课程资源 - BV1oi421Q7GT

![](img/90ae01fff2bb82d8a13e9b4acabb447c_0.png)

Let's go through some of the details of what is exactly Apache airflow and why would you want to use it in what circumstances it might make sense and we'll go with the basics and then we'll start digging into some of the important details so what is exactly Apache airflow well it is well it's an open source project for sure。

 but it allows you to batch certain jobs together similar to how you like if you're familiar with CICD systems it's kind of like that where you're setting up certain things to happen at a certain time so we have to deal with certain concepts like like triggering things and pieces of code that will execute at some point and will do or perform some actions。

It is essentially an open source batch workflow platform。

 so it is a platform and you're dealing with workflows that are going to perform actions and these are performed in batches and we'll see those in detail later。

You are bound by writing everything in Python， so youre writing Python to define all of these tasks and how they're going to work together and you have a webUI。

 a user interface for looking at monitoring and trying to keep up with how these workflows are executing and what is the state again very similar to certain CICD platforms where you have a UI workflow and you can actually take a look at what's going on。

And definitely you can， I mean， you can deploy it from a laptop。

 it's not 100% something that I would recommend， but like to try it out very easy to get started as we will see later now some of the reasons why you might one consider airflow Apache airflow is because it allows you to orchestrate certain things so you're going to group imagine like you have certain actions。

 certain things that you want to do and you want to put them together and make them work together so that is what an orchestration platform will do and in this case airflow definitely delivers。

Now you have all of these definitions and all of these configurations that you can have with these workflows and you definitely have a very clear a very easy straightforward way to start and end these batches of work that need to happen at certain interval。

 not necessarily regular， they could be regular intervals but they could also be non-regular intervals as well。

 and definitely again， these are a setup constructed define using Python。

 you're going to have to write some Python in order to put all of these together。

Some other things that you might want to consider is because the scheduling and the execution is very rich and what this means is actually the ability not only to schedule something but you can have many different ways of triggering a run an execution backfilling for example allows historical reruns which allows you to go back and perform a certain action。

 imagine if you're trying to populate a database from scratch。

 you can rerun pipelines which we'll see as well on historical data I mean I give the example of the database and rerunning partial pipelines like if something happens in the middle and you want to fix some errors this is very common in data engineering where you might get surpriseded in the middle of an execution that you need to fix something and you can definitely have that ability with airflow now the user。

F the UI provides a pipeline or task inspection， you can poke around， you can see what is going on。

 when did it start， did it fail， did it succeed and 100% you can have like an overview of the pipelines over time like how was this pipeline working in the past month in the past year and what was the situation happening when these tasks were executed and of course log output and retries when things are failing。

 you can also of course configure the retries if something is failing you might not want to retry certain tasks because they don't make sense but in some situations like say for example if you're dealing with the network 100% that will be something that might be interesting to you。

And it's open source and customizable being open source always a good thing because of the community of course is' going to be developed and used globally so you have that support。

 that ecosystem， that community sense when you're dealing with a very large project the community also provides a lot of support but as well resources and extensibility which I really like and this is very important I certainly work with very large open source projects in the past and whenever there's a big community this is very very useful highly customizable architecture is also pretty fantastic and you can interact with the API to make it happen now let's take a look at a couple of reasons why you might now want to choose Saflow I mean we've seen some of the things that are important。

And this is not necessarily for event drivenn workflows and not infinite right like this is not going to have tasks that are going to run forever。

 you want to have things that are going to be triggered on a schedule they're going to process something。

 they're going to do something， they're going to do a task。

 you're probably going to want to have to retry， if something happens。

 but if you're looking for something different， say， for example。

 if you wear a streaming platform and you want to stream certain events well that's。

Probably not going to work that well with airflow。And the other thing is if you want to do less coding。

 you don't want to do some developing and you want to do actually more UI well this is definitely not going to be it so there you go that is kind of like a good introduction to Apache airflow some of the things where it shines and one of the some of the things where you might want to consider on not using it。



![](img/90ae01fff2bb82d8a13e9b4acabb447c_2.png)