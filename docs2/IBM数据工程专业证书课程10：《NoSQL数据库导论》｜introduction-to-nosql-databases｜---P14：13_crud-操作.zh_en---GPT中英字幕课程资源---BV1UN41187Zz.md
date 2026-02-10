# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P14：13_crud 操作.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/44b68190fe0f1ba52229a427e9fb3133_0.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_1.png)

Welcome to CRd Op After watching this video， you will be able to use Mongo Shell to connect to your Mongo DB database and perform basic CRD operations。



![](img/44b68190fe0f1ba52229a427e9fb3133_3.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_4.png)

Mongo Shell is a command line tool provided by MongoDB to interact with your databases。

 it is an interactive JavaScript interface and you can use it to perform data and administrative operations on MongoDB。



![](img/44b68190fe0f1ba52229a427e9fb3133_6.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_7.png)

So first， we connect to our cluster by providing a connection string and once connected。

 we can view the list on all our databases For simplicity。

 we will assume the shell is already connected to our Mongo DB instance to start working on the campus management database we will run the following statement。

 and then we can see what collections are present in the campus management database using this command。



![](img/44b68190fe0f1ba52229a427e9fb3133_9.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_10.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_11.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_12.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_13.png)

It shows two collections， staff and students crud operations are create， read。

 update and delete operations， hence the acronym crud。 Let's start with a create operation。



![](img/44b68190fe0f1ba52229a427e9fb3133_15.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_16.png)

We will insert a new document into the student's collection， it takes the form of DB。

 which is the Campus management DB database， then the collection name， which is students。

 and then the insert one function， which takes an argument as the document we want to create in the student's collection。

 the outcome is an acknowledgement that the operation was successful。

 and since this was an insert operation， it shows inserted ID。



![](img/44b68190fe0f1ba52229a427e9fb3133_18.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_19.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_20.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_21.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_22.png)

Underscore ID is a required field on every document in MongoDB。



![](img/44b68190fe0f1ba52229a427e9fb3133_24.png)

Because we didn't provide one ourselves in John Doe's document。

 the Mongo Shell driver will add the_ ID field and generate the object ID for us。



![](img/44b68190fe0f1ba52229a427e9fb3133_26.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_27.png)

Mongohell is a JavaScript interpreter， meaning you can define variables and perform other functions in it too here students underscore list is created with two documents in it。

 and we can pass this as an argument to the Inert Many function。



![](img/44b68190fe0f1ba52229a427e9fb3133_29.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_30.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_31.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_32.png)

Now let's do some read operations in the first one。

 we call the Find One function without any filter criteria。

 This will return the first document in natural order。

 which is the order in which the database refers to documents on disk。



![](img/44b68190fe0f1ba52229a427e9fb3133_34.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_35.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_36.png)

In this second read operation， we want to find the first student with a specific email address。



![](img/44b68190fe0f1ba52229a427e9fb3133_38.png)

If more than one document matches the criteria， only the first one will be read as we are using the Find One function。



![](img/44b68190fe0f1ba52229a427e9fb3133_40.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_41.png)

Next， we want to retrieve all students with the last name of Do。And finally。

 if we want to count how many students have the last name Do， we call the count function。

 this count will happen on Mongo DB， and only the number value will be returned。



![](img/44b68190fe0f1ba52229a427e9fb3133_43.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_44.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_45.png)

Now we will perform a replace operation。Let's retrieve a student record and make some changes to the document。



![](img/44b68190fe0f1ba52229a427e9fb3133_47.png)

We are creating a new field to identify which students are on campus or online only。



![](img/44b68190fe0f1ba52229a427e9fb3133_49.png)

We will also update the email with campus email Once all changes are made。

 we will call the replaceplace one function， which takes as its first argument。

 the filter criteria to find a document with the last name of Do。



![](img/44b68190fe0f1ba52229a427e9fb3133_51.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_52.png)

The second argument is the updated student object。 The outcomes of this statement are an acknowledgecment。

 the information about how many documents matched our filter criteria and the count of how many were actually modified。



![](img/44b68190fe0f1ba52229a427e9fb3133_54.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_55.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_56.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_57.png)

In the replace example， we were sending the whole document back with the new changes for larger documents。

 this will take a lot of transfer time between the client and the database。

 Instead we can use Mongo DBs in place updates for small changes so we do this by constructing a changes document。

 which in our case only has two assignments which come under Doar Sign set。

 Then we would call the Upd one function。

![](img/44b68190fe0f1ba52229a427e9fb3133_59.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_60.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_61.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_62.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_63.png)

To update all of the students to online only due to lockdown。

 we can run the Upd menu function without any filter criteria and a change document。



![](img/44b68190fe0f1ba52229a427e9fb3133_65.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_66.png)

To run a delete operation like update and find the deletete one function takes filter criteria as a first argument runningning that delete statement provides you with an acknowledgecment and a number representing how many documents were deleted。



![](img/44b68190fe0f1ba52229a427e9fb3133_68.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_69.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_70.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_71.png)

Similarly， you have a delete many function to delete more than one document meeting the criteria。



![](img/44b68190fe0f1ba52229a427e9fb3133_73.png)

In this video， you learned that the Mongo Shell is an interactive command line tool provided by MongoDB to interact with your databases。



![](img/44b68190fe0f1ba52229a427e9fb3133_75.png)

![](img/44b68190fe0f1ba52229a427e9fb3133_76.png)

To use the Mongo She， you first need to make a connection to your cluster via a connection string。

 You use showhow DBs to list databases， use database name to select a database and show collections to show collections in a database。

Cred operations consist of create， read， update and delete useful functions include insert one。

 insertt many， find one， find， count， replace， update one， update many， deletete one and delete many。

 and finally， different kinds of acknowledgments are returned based on the operation being run。



![](img/44b68190fe0f1ba52229a427e9fb3133_78.png)