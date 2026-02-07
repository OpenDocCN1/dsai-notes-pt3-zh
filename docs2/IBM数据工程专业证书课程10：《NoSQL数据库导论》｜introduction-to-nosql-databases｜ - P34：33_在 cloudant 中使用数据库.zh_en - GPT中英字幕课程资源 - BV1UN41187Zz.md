# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P34：33_在 cloudant 中使用数据库.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/e1e88bd06515f8901968b8234dfdd447_0.png)

![](img/e1e88bd06515f8901968b8234dfdd447_1.png)

Welcome to Working with databases in Cloudant。

![](img/e1e88bd06515f8901968b8234dfdd447_3.png)

After watching this video， you will be able to explain the difference between partitioned and nonpartitioned databases。

 describe how to create databases in Cloudant， describe the characteristics of documents in a Cloudant database。

 and describe how to insert， view， query， update， and delete documents in a Cloudant database。

You can create and use two types of database in IBM Cloudant。

 nonpartitioned and partitioned nonpartition databases have no partitioning scheme that needs to be defined。

 which makes them relatively simple to use。 However。

 non partition databases only provide global querying。



![](img/e1e88bd06515f8901968b8234dfdd447_5.png)

![](img/e1e88bd06515f8901968b8234dfdd447_6.png)

![](img/e1e88bd06515f8901968b8234dfdd447_7.png)

A nonpartition database is a legacy type of cloud and database that is used with earlier versions of IBM Cloudant and also with couch Db in nonpartition databases。

 documents are distributed to shards randomly based on a transformation of their document I D。

 For this reason， there is no actual relation between a documents I D and the shard that it ends up being located on。

 In fact， it is unlikely that documents that share similar document Is will be located on the same shard as each other。



![](img/e1e88bd06515f8901968b8234dfdd447_9.png)

Partitioned databases provide both partitioned and global querying。

 They also offer substantial performance and cost benefits。



![](img/e1e88bd06515f8901968b8234dfdd447_11.png)

![](img/e1e88bd06515f8901968b8234dfdd447_12.png)

Partitioned querying takes advantage of the data layout within the database cluster to deliver improved and more scalable query performance。



![](img/e1e88bd06515f8901968b8234dfdd447_14.png)

![](img/e1e88bd06515f8901968b8234dfdd447_15.png)

Partition queries are also often cheaper than global queries。



![](img/e1e88bd06515f8901968b8234dfdd447_17.png)

Partitioned databases are a newer type of cloudant database。 However。

 they require you to specify a logical partitioning of your data。

 A partition database requires a partition key for every document。

 A partition is a logical grouping of documents。 All documents are assigned to a partition and several documents are typically given the same partition key。

 It is highly recommended that you use partition databases to get the best long term performance out of your databases if your data model allows for logical partitioning of documents。

 It's important to note you cannot change the partitioning type of an existing database。



![](img/e1e88bd06515f8901968b8234dfdd447_19.png)

![](img/e1e88bd06515f8901968b8234dfdd447_20.png)

You create new databases in cloudant from the databases dashboard tab When you create a database。

 you must select whether you want the database to be partitioned or nonpartitioned。

 and that is all you need to configure before you create a database。



![](img/e1e88bd06515f8901968b8234dfdd447_22.png)

Databases that have been created already are displayed on the database's dashboard tab。

 The list displays name information， the size of each database。

 the number of documents contained in each database and whether the database is partitioned or not。



![](img/e1e88bd06515f8901968b8234dfdd447_24.png)

Many other database systems store their data in tables with data contained in rows。

 each with identical fixed columns， and the schema of each table is predefined。

 A list of columns with their name， date type， value constraints and relations to other tables carefully defined。

 but in cloudant， things are very different。 We have already discussed that cloudant is a document database type that uses adjacent document store。

 So your cloud and instance has collections called databases rather than tables。

 and each of these will contain a number of documents。



![](img/e1e88bd06515f8901968b8234dfdd447_26.png)

![](img/e1e88bd06515f8901968b8234dfdd447_27.png)

![](img/e1e88bd06515f8901968b8234dfdd447_28.png)

![](img/e1e88bd06515f8901968b8234dfdd447_29.png)

A cloud and document must be a J object， which must start and end with curly braces or brackets。

 and it will contain a number of key value attributes。

The adjacent objects must be less than one megabyte and can contain any number of strings， numbers。

 booles， arrays and nested objects。You insert documents into a database on the details page for the selected database in the Cloud dashboard to insert a document you need to create a document in the database。



![](img/e1e88bd06515f8901968b8234dfdd447_31.png)

![](img/e1e88bd06515f8901968b8234dfdd447_32.png)

When inserting a document into a database， you need to use the starting and ending curly braces。

 and you need to either use the provided underscore ID or supply your own custom underscore ID Cloudon uses the underscore ID key to uniquely identify a document。

 It's the equivalent of the primary key in relational databases。

You then populate the document details either by entering them manually between the curly braces or by pasting in from another source。

 then you create the document to insert it into the database。When you select a database。

 you can view the documents it contains by three different views。 The first is metadata view。

 which is the default view after you insert documents into a database， and this view shows ID。

 key and value information for each document。

![](img/e1e88bd06515f8901968b8234dfdd447_34.png)

![](img/e1e88bd06515f8901968b8234dfdd447_35.png)

![](img/e1e88bd06515f8901968b8234dfdd447_36.png)

You can also view documents in a database in TableVi。

 which shows information about the data tables for each document in a database。



![](img/e1e88bd06515f8901968b8234dfdd447_38.png)

![](img/e1e88bd06515f8901968b8234dfdd447_39.png)

In this example， we can see tabled data for ID， number of bedrooms， price and square footage。



![](img/e1e88bd06515f8901968b8234dfdd447_41.png)

![](img/e1e88bd06515f8901968b8234dfdd447_42.png)

And the last view you can use is Jason view， which shows the contents of the document in J format。

 You can also edit the J document from here。

![](img/e1e88bd06515f8901968b8234dfdd447_44.png)

![](img/e1e88bd06515f8901968b8234dfdd447_45.png)

You can run queries against the documents in your database。

 You enter your query in the query window and then run the query。



![](img/e1e88bd06515f8901968b8234dfdd447_47.png)

You can update data in a document in your database， you simply select a document。

 make the changes you want， and then save your changes。



![](img/e1e88bd06515f8901968b8234dfdd447_49.png)

You can also delete documents from your database using the Cloud and dashboard。

 you simply select the document， delete it， and confirm the deletion operation。In this video。

 you learned that you can create and use two types of database in IBM Cloudant。

 non partitioned and partitioned。

![](img/e1e88bd06515f8901968b8234dfdd447_51.png)

![](img/e1e88bd06515f8901968b8234dfdd447_52.png)

Non partition databases have no partitioning scheme to define， but they only provide global querying。

Partitioned databases provide both partitioned and global querying。

 and they offer substantial performance and cost benefits。

Partitioning type is set at database creation。Cloudant is a document database system that uses adjacent document store。

You can use the cloud and dashboard to create databases。

And you can also use the CloudEn dashboard to insert， view， query， update。

 and delete documents in a database。