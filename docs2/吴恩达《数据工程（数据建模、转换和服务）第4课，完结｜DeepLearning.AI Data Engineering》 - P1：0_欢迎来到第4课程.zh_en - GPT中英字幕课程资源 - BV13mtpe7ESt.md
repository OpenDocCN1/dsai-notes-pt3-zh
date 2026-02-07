# 吴恩达《数据工程（数据建模、转换和服务）第4课，完结｜DeepLearning.AI Data Engineering》 - P1：0_欢迎来到第4课程.zh_en - GPT中英字幕课程资源 - BV13mtpe7ESt

Welcome to the fourth and final course of this data engineeringring specialization You've come a long way in completing the previous three courses and now it's time to wrap it up with a focus on data modeling。

 transformation and serving。😊，I'm your game with Joevies your instructor for this course Can you say a bit about what' next in this final course Sure thing thanks Andrew Well as you mentioned this final course is all about data modeling transformation and serving data for end use cases with your work in the previous three courses you've built a solid foundation when it comes to things like ingestion storage data ops and orchestration and with these skills you'll be well equipped to build robust data systems this course is all about delivering value for stakeholders remember I said that your job as a data engineer is to get raw data from somewhere turn it into something useful and then make it available to end users well in some sense you have experience with all those things already but the focus of this course is really on turning data into something useful and serving it in a way that creates business value So data is usually meant to reflect the real world but it also just captures。

small slice of this real world for example， if you operate a website and have clickstream data and data on what users are purchasing and if additionally you have a mobile app where users are taking actions and all those actions are coming in and additionally all of these user actions call a lot of APIs like maybe a recommend system or classF to tag content and on and on and on。

 how do you model all of this in a database to capture all the stuff happening in the world。

And then of course， if one day someone in new company decides to run a survey of users so you get information about the demographics and personal interests of users。

 how do you then add that data in？And then if your company acquires an adjacent business which has its own database of users with different attributes。

 and some of those users overlap with your database of users。

 what do you do these two databases now and make it work？Together。Exactly。

 given the complexity of the real world， your ability to design the right way to represent the data will have a huge impact on what types of questions you can efficiently ask of the data。

 as well as how accurately your data reflects the real world Yeah so one use case that comes up a lot as serving machine learning models to end users。

 there's a lot of complexities not just in terms of training the model。

 but in terms of making that model available to end users so they can get maybe predictions or classifications or in the case of large language models。

 outputs from a model， but there's also some complexities involved with this。

 maybe you have some experience with deploying machine learning models at scale in fact in addition to the software architecture data storage and so on challenges of deploying there's one additional wonderful and annoying thing to deal with which is。

Data drift and concept drift So when we built AI models。

 we train on a data and then sometimes the future turns out to be different than the past and so the data we I train the AI system on is no longer reflective of whatever the world has turned into and so how do you set that the system to spot when the world has changed and how do you gather the new data if needed to maybe update the model and an appropriate timescale So beyond the software architecture。

 software engineering aspects， real world deployment also has this additional statistical and machine learning complexity to deal with absolutely and so this is where the course I think gets very exciting is because now we're talking about modeling your data transforming it in such a way that's useful and then serving it to end users in a way that they're going to get valuable like you say there's a lot of complexities involved it's not just you're not just one and done's constant cycle of serving and this kind of goes back。

The data engineering lifecycl in general we're having to go back and sometimes revisit other parts of the lifecycl as we indicated earlier in the courses and so yeah this is in a lot of ways we've saved the best for last or maybe at least the most fun stuff for last so yeah it should be a lot of fun I think complexity is fun sometimes let's go on to next video and get started it with this final course。

