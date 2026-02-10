# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P11：10_mongodb 概述.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/d3df709d3a8d11f1878d4c2d8cba2218_0.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_1.png)

Welcome to an overview of Mongo DB After watching this video。

 you will be able to explain what MongoDB is list the different components of MongoDB and describe why and where to use Mongo DB Mongo DB is a document and a no SQL database instead of storing data in tables of rows or columns like SQL databases。

 each record in a MongoDB database is a document and you store the data in a non-relational way。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_3.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_4.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_5.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_6.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_7.png)

Documents are associative arrays like J objects or Python Dictionaries， for example。

 a student document representing a student's first name， last name， email address， and ID。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_9.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_10.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_11.png)

Mongo Dbi documents of similar type are grouped into a collection Our campus management system stores all student records or documents in the student's collection。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_13.png)

And similarly， all staff documents are stored in the employee's collection。

So what is a database following our previous example。

 the campus management system stores all different types of data related to it in a Mongo DB database called Campus Management DB Let's dissect our document in the document below。

 first name， last name， email and student ID， our fields or properties with values representing a student named John Doe。

 and each field name is unique within that document。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_15.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_16.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_17.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_18.png)

MongoDB supports a variety of data types， so you have the full capability to use the correct data type to store your information in。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_20.png)

For example， dates should be stored as ISO date or Uniix style E dates。

 which will help you with queries likeG me all students born between 15th of January to 15th of February。

 Numbers can be stored either as whole numbers or decimals。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_22.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_23.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_24.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_25.png)

Being a document database， MongoDB also allows you to store sub documentscu to group secondary information together。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_27.png)

It also supports lists of values， not just text， but even different kinds mixed together。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_29.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_30.png)

Working with Mongo Db is easy because you can focus on the data you are writing and how you are going to read it。

 Traditional relational databases required you to create the schema first。

 then create table structures that will hold your data。

 So if you decide to store an additional field， you will then have to alter your tables。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_32.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_33.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_34.png)

In Mongo Db， you change as you go along。MangoDB also gives you the power to bring in any structured or unstructured data。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_36.png)

It also provides high availability by keeping multiple copies of your data。

 which we will cover in later topics。You can design complex data structures easily in Mongo DB without worrying about the complexity of how it is stored and how it should be linked。

 For example， your campus management application is also launched in the USA。

 where they do not store postcodes but have zip codes。

Scalability provided by MongoDB means as your data needs grow。

 you can easily scale vertically by introducing bigger， faster， better hardware。

 or horizontally by partitioning your data。All of that can be done whether you are running a self managedaged onpres Mongo DB or the hybrid or cloud hosted and fully managed services such as IBM Cloud databases for MongoDB。

 or Mongo DB Atlas on AWS， Azure and Google Cloud。In this video you have learned that MongoDb is a document and a no SQL database MongoDB supports various data types。

 Documents provide a flexible way of storing data MongoDB documents of a similar type are grouped into collections MongoDb models data as you read and write。

 bring structured or unstructured data and provides high availability and MongoDb can be used for a variety of purposes because of the flexibility of storing structured or unstructured data。



![](img/d3df709d3a8d11f1878d4c2d8cba2218_38.png)

![](img/d3df709d3a8d11f1878d4c2d8cba2218_39.png)