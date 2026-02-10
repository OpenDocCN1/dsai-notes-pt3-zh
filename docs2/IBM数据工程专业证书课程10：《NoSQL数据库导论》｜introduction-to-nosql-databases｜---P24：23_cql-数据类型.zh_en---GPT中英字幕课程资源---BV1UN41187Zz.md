# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P24：23_cql 数据类型.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/8282ca07bbee25ba5d87a8b0b654324b_0.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_1.png)

Let's talk about the Cassandra query language or CQL accepted data types After watching this video you will be able to describe the main data types in CQL。

 explain how to use these data types when defining a Cassandra table and describe the role of collection data types and user definedfin data types in CQL there are many data types。

 but they can be grouped into three main categories， built in data types， collection data types。

 and user definedfin data types。

![](img/8282ca07bbee25ba5d87a8b0b654324b_3.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_4.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_5.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_6.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_7.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_8.png)

The user can choose any of them according to the requirements of the application and data model。 Now。

 let's discuss each of them in turn to understand what they mean。



![](img/8282ca07bbee25ba5d87a8b0b654324b_10.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_11.png)

The built in data types are basically predefined in Cassandra。

 the user can refer the variables to any of them。

![](img/8282ca07bbee25ba5d87a8b0b654324b_13.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_14.png)

Besides regular data types like ASCI， Boolean， Decimal， double， floatat， int， and text。

 which are fairly straightforward， there are some other types that maybe require a bit of explanation。



![](img/8282ca07bbee25ba5d87a8b0b654324b_16.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_17.png)

Let's take the blob data type， although Cassandra mainly stores textbased information。

 there is also the possibility to store blobs， which stands for binary large objects blobs are typically used to store images。

 audio or other multimedia objects while blobs represent a collection of binary data stored as a single entity in Cassandra it is recommended that their size does not exceed one megabyte。



![](img/8282ca07bbee25ba5d87a8b0b654324b_19.png)

Thus， you could store a small image or string using a blob。

The big int data type can be used for a 64 bit signed long integer。

 This data type stores a higher range of integers when compared to the int data type。

The well known VarA is also available in Cassandra as a data type。

 it represents UTF8 encoded strings。Moving on to more complex data types。

 Cassandra provides collection types as a way to group and store data together in a column for example。

 in a relational database a grouping such as a user's multiple email addresses is related with a many to one joined relationship between a user's table and an email table Cassandra avoids joins between two tables by storing the user's email addresses in a collection column in the user's table Each collection specifies the data type of the data held。



![](img/8282ca07bbee25ba5d87a8b0b654324b_21.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_22.png)

A collection is appropriate if the data for collection storage is limited。

 if the data has unbounded growth potential， like messages sent or sensor events registered every second。

 do not use the collection data type， instead， use a table with a compound primary key。

 where data is stored in the clustering columns。Within the collection data types category there are three data types lists this Cassandra data type represents a collection of one or more elements in a table list is to be used in cases where the order of the elements is to be maintained and a value is to be stored multiple times。

 such as entries in a log。

![](img/8282ca07bbee25ba5d87a8b0b654324b_24.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_25.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_26.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_27.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_28.png)

Mps this Cassandra data type represents a collection of key value pairs Ma is a data type that is used to store a key value pair of elements。

 such as entities in a journal entered using a date and then text。



![](img/8282ca07bbee25ba5d87a8b0b654324b_30.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_31.png)

And sets this Cassandra data type represents a collection of one or more sortded elements in a table set is a data type that is used to store a group of elements。

 The elements of a set will be returned in a sorted order。

 an example would be a list of email addresses。

![](img/8282ca07bbee25ba5d87a8b0b654324b_33.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_34.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_35.png)

Let's go back to the users table and add a new column to the table called Jobs。

 which is basically just a list of jobs。

![](img/8282ca07bbee25ba5d87a8b0b654324b_37.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_38.png)

We would like to store the jobs in the order of their occurrences。

 Remember that the user's table is a static table with its primary key consisting of the user ID column。



![](img/8282ca07bbee25ba5d87a8b0b654324b_40.png)

In Cassandra， we will store all the users jobs in a single column since we cannot perform joins in this case。

 we will use the list type of the collection data types because we want to preserve the order of the jobs。

Another reason is that a person can work at a specific company more than once。

 so uniqueness is not required。We can add a job in the list。

 either at the beginning or end of the list， or in a specific position。

 the entries in the list can be repetitive as they are not unique。



![](img/8282ca07bbee25ba5d87a8b0b654324b_42.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_43.png)

A select inCQLSH on our table shows that we currently have two jobs recorded for our user。



![](img/8282ca07bbee25ba5d87a8b0b654324b_45.png)

We can also remove an entry from the list。A select on our table now shows that we only have one job listed for our user。

We have seen that collection data types can be used instead of a one to many joint relationship。

 however， for one to one relationships， we can use Cassandra user defined types or UDTs。



![](img/8282ca07bbee25ba5d87a8b0b654324b_47.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_48.png)

UDTs can attach multiple data types to a single column。

 think of an address being a combination of an apartment number， building， street， and so on。

CQL enables the user to create their own data type。

 the fields used in a created UDT can be any valid data type。

 including collections and other existing UDTs。After creating a data type and fields in it。

 the user can alter， verify， and even drop a field or the whole data type。Once created。

 UDTs can be used to define a column in a table。Let's see how we do this on the next screen。

In this example， we create a new data type called And Once created。

 we can use it to define a column in our new table called Lo。



![](img/8282ca07bbee25ba5d87a8b0b654324b_50.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_51.png)

We can insert data using the new address data type， and we can also drop the data type。



![](img/8282ca07bbee25ba5d87a8b0b654324b_53.png)

![](img/8282ca07bbee25ba5d87a8b0b654324b_54.png)

In this video， you have learned that Cassandra supports built in。

 collection and user defined data types。

![](img/8282ca07bbee25ba5d87a8b0b654324b_56.png)

Both collection and user defined data types offer a way to group and store data together。

 Collect data types can emulate one to many relationships。

 There are three types of collection data types， lists， maps and sets。

User defined data types can emulate one to one relationships。

 and user defined data types can attach multiple data fields to a column。



![](img/8282ca07bbee25ba5d87a8b0b654324b_58.png)