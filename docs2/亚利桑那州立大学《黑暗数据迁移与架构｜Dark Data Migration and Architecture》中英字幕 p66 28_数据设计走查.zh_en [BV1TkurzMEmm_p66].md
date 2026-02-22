# 亚利桑那州立大学《黑暗数据迁移与架构｜Dark Data Migration and Architecture》中英字幕 p66 28_数据设计走查.zh_en [BV1TkurzMEmm_p66]

In this lesson we're going to focus on data design and we're going to start with database design right so when talking data design。

 we're thinking data and the data journey all the way through。

 but here we're going to focus on the database on this first slide。

 So the one thing we want to do is you see the first part of that is discovery and this follows this whole credo that we've been through with U understand learn evaluate and assess first thing off the top。

 then you want to define now we're going into solutioning so we're looking at the conceptual design。

 architectural design， logical design and physical design。

 where physical design is needed when we're including hardware。After design phases。

 most of you know you' go to build， test， delivery。

 there's a bunch of different phases and build build itself has its own discovery phase， discovery。

 design and solution， because the upfront stuff is around designing the product and then in the build。

 you're going always typically make some changes to what you thought was true。

 but if you've done the first part。Well， you're not going to make too many changes。All right。

 so this also includes the resulting data product， but we'll talk about that on another video right but right now at the inception you definitely want to think of the dark data and the data products that ensue from the dark data。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_1.png)

Now critical processes and tools， right， APIs， ETLs， data accessibility， data visualization。

 that's how we're going consume the data， intelligence creation the intelligence creation is going to go what is going to be what's in the visualization so we can consume it and make better decisions。

 automation and storage， automation is critical because when we get data coming in。

 new data coming in， new data streaming in possibly from event listening like Kafka is going to be critical that we have automation set up and is done correctly and that the transformations that result from automation are done in a timely fashion so that we don't have lag。

 storage is also critical because that's what's going to house our information and house our intelligence。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_3.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_4.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_5.png)

There's many different things when we talk about strategy architecture design。

 but these are the tools， these are some of the primary tools， there are many other ones。

 but these are some of the primary tools that we'll use to help this data design one of the key things is ETL right so there's ETL and there's also transformation。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_7.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_8.png)

Highly similar to some extent but some extent there's some differences right so we're talking about ETO we're talking about extract transform and load from data going from system to system sometimes needs to be adjusted。

 transformed， made different addeds to so the ETO process allows us to receive data and deliver it in a new form right sometimes it needs to be transformed and it's also just a general transformation。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_10.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_11.png)

W can occur inside of databases depending on how you set up your overall code like Python。

 if you're using Python to create new derivations。

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_13.png)

Now going into data storage right we want to talk about that a little bit we spoke about data lakes。

 data warehouses as we know data lakes typically are more raw in nature a lot of times you're gonna to get different types of data and mass right and there are some data lakes that are partially unstructured and partially structured and in fact most large companies they' data lakes are partially structured and partially not structured so you're looking at raw large undefined data that sort of out there in the wild and you got to tamement bring it in and make sense of it。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_15.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_16.png)

You use use cases to set up the streaming process to do your machine learning and data scientists and a lot of will use a lot of different processes and tactics to learn from the data and have their own new process and algorithms learn from itself data warehouses are sort of more clean in nature。

 typically not always but typically so when we talk about refined， small relational。

 it's typically a set of data tables because once data tables get too big you have a challenge themselves。

 which is why you move to unstructured in the lake。

To some extent you have these tables that are inside the lake that are usable and can be compatible with the warehouse。

 but sometimes not the users can be analysts， they can be anybody。

 anybody who needs some data typically there needs to use it for their transactional purposes。

 but primarily for the analytical purposes when you come out of these systems。

 so it's important to understand that the lake or the warehouse is a place that you can send data to through an ETL process through APIs as well as pulling it out ETL using ETL and APIs as well。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_18.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_19.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_20.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_21.png)

So lastly， going through an ODS， I wanted to point this out because there are some places you can use like data layers。

 data marks and data stores and this diagram， this points out。

Quite simply that data comes out of these OLTP systems and sometimes you have these flat files。

 they go into either staging areas and go directly into a data warehouse。

 but sometimes they go into a data store。

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_23.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_24.png)

Now data stores are typically structured by nature。

 but these data stores then send data over to the data warehouse for it to be stored long term and the data stores typically depend with how this diagram is setup up。

 it's going to be more temporary in nature and it's sort of smaller in nature so you have a lot of overriding。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_26.png)

Lastly， on the far right you'll have the data marks and other files that may need to be output and if you notice you have ETL processes between each of these stages because that data needs to be transformed and loaded。

 those ETL processes typically operate off either algorithms or referential data RDBMS like referential Data manager so at the end here on the far right when you're looking at that reporting data。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_28.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_29.png)

Those data marks then service in the users for the purpose of building dashboards or for any other reporting or intelligence purposes。

 so this data store here in the light blue。

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_31.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_32.png)

Accs is a supporting mechanism making everything else happen downstream。

So this is a quick overview of data storage， data transformation and how we would design something like this。

 just the high level architecture as well as those conceptual designs that you've seen throughout to allow us to better service and better build as we go through the process Thank you for your time。



![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_34.png)

![](img/3f4c31cd7a0b8bc351cc2660fe21a5d3_35.png)