# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P18：17_从 python 访问 mongodb.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/7603e49e2ca8e75f35e37ac602741823_0.png)

![](img/7603e49e2ca8e75f35e37ac602741823_1.png)

Welcome to Aesing Mongo DB from Python。

![](img/7603e49e2ca8e75f35e37ac602741823_3.png)

After watching this video， you will be able to explain what the Mongo client is and perform basic crud operations for our campus management database using Python。



![](img/7603e49e2ca8e75f35e37ac602741823_5.png)

The Mongo client is a class that helps you interact with Mongo Db。 First。

 we import Mongo client from Pine Mongo， which is an official Mongo Db driver for Python。

 The UI tells us the address where Mongo Db is。 Then we create Mongo client。

 which we should only do once in our code。 The next part gets the object pointing to the campus management database。

 And finally， from the campus management database object， we point to the student's collection。



![](img/7603e49e2ca8e75f35e37ac602741823_7.png)

![](img/7603e49e2ca8e75f35e37ac602741823_8.png)

![](img/7603e49e2ca8e75f35e37ac602741823_9.png)

![](img/7603e49e2ca8e75f35e37ac602741823_10.png)

![](img/7603e49e2ca8e75f35e37ac602741823_11.png)

![](img/7603e49e2ca8e75f35e37ac602741823_12.png)

![](img/7603e49e2ca8e75f35e37ac602741823_13.png)

Now that we have a reference to the student's collection， let's create a student document for this。

 we call the insertt one function， which takes the document we are trying to insert as its input。

 We can also do a bulk insert by calling the insert many function。



![](img/7603e49e2ca8e75f35e37ac602741823_15.png)

![](img/7603e49e2ca8e75f35e37ac602741823_16.png)

![](img/7603e49e2ca8e75f35e37ac602741823_17.png)

![](img/7603e49e2ca8e75f35e37ac602741823_18.png)

This function takes a list instead as its input。

![](img/7603e49e2ca8e75f35e37ac602741823_20.png)

Now， let us do some read operations in the first one， we call find one without any filter criteria。

 This will return the first document in natural order。

 which is the order in which the database refers to documents on disk。



![](img/7603e49e2ca8e75f35e37ac602741823_22.png)

![](img/7603e49e2ca8e75f35e37ac602741823_23.png)

Then we find the first student with an email if more than one document matches the criteria。

 only the first one will be read because we are using the Find One function。



![](img/7603e49e2ca8e75f35e37ac602741823_25.png)

![](img/7603e49e2ca8e75f35e37ac602741823_26.png)

To get all the documents， we do a fine， and now we are retrieving all students with the last name of Do。



![](img/7603e49e2ca8e75f35e37ac602741823_28.png)

![](img/7603e49e2ca8e75f35e37ac602741823_29.png)

And finally， if we just want to count how many students there are with the last name Do。

 we call the count function。 This count will happen on Mongo Db。

 and only the number value will be returned to the client。



![](img/7603e49e2ca8e75f35e37ac602741823_31.png)

![](img/7603e49e2ca8e75f35e37ac602741823_32.png)

![](img/7603e49e2ca8e75f35e37ac602741823_33.png)

When we do a find on a collection in Mongo Db， we get a cursor back。

 This cursor points to our documents in Mongo Db。 If you have run this using Mongo Shell。

 the shell retrieves those documents for you behind the scenes。



![](img/7603e49e2ca8e75f35e37ac602741823_35.png)

![](img/7603e49e2ca8e75f35e37ac602741823_36.png)

![](img/7603e49e2ca8e75f35e37ac602741823_37.png)

To retrieve documents from our cursor， we call Python dumps。

 which will exhaust our cursor to retrieve all the documents。



![](img/7603e49e2ca8e75f35e37ac602741823_39.png)

![](img/7603e49e2ca8e75f35e37ac602741823_40.png)

Let us retrieve a student and make some changes to the document。



![](img/7603e49e2ca8e75f35e37ac602741823_42.png)

We are creating a new field to identify whether students are on campus or online only。

 We will also update the email with the campus email address。



![](img/7603e49e2ca8e75f35e37ac602741823_44.png)

![](img/7603e49e2ca8e75f35e37ac602741823_45.png)

Once all changes are made， we will call the replace function。

 which takes its first argument as the filter criteria to find a document with the last name of Do。

 and the second argument is the updated Python object。



![](img/7603e49e2ca8e75f35e37ac602741823_47.png)

![](img/7603e49e2ca8e75f35e37ac602741823_48.png)

![](img/7603e49e2ca8e75f35e37ac602741823_49.png)

In the replace example， we were sending the whole document back with the new changes for larger documents。

 this will take a lot of transfer time between the client and the database。



![](img/7603e49e2ca8e75f35e37ac602741823_51.png)

![](img/7603e49e2ca8e75f35e37ac602741823_52.png)

We can use Mongo DBs in place updates for small changes。

 We do this by constructing a change document， which in our case only has two assignments which come under Doar Sign set。

 and with this inplace update， we don't even need to retrieve the student document。



![](img/7603e49e2ca8e75f35e37ac602741823_54.png)

![](img/7603e49e2ca8e75f35e37ac602741823_55.png)

![](img/7603e49e2ca8e75f35e37ac602741823_56.png)

![](img/7603e49e2ca8e75f35e37ac602741823_57.png)

To update all of the students to online only due to lockdown。

 we can run the updated menu function without any filter criteria and change all documents。



![](img/7603e49e2ca8e75f35e37ac602741823_59.png)

![](img/7603e49e2ca8e75f35e37ac602741823_60.png)

![](img/7603e49e2ca8e75f35e37ac602741823_61.png)

Just like update and find the deletete one and delete many functions。

 take filter criteria as the first argument， and these functions will delete one or many documents in the given collection matching the criteria。



![](img/7603e49e2ca8e75f35e37ac602741823_63.png)

![](img/7603e49e2ca8e75f35e37ac602741823_64.png)

![](img/7603e49e2ca8e75f35e37ac602741823_65.png)

In this video you learned that Mongo clientient is a class that helps you interact with MongoDB Mongo clientient is imported from Py Mongo。

 the official Mongo DB driver for Python You can perform single or bulk inserts You can replace whole documents You can perform an in place update which is a preferred option。

 and you can delete one or more documents from your collection。



![](img/7603e49e2ca8e75f35e37ac602741823_67.png)