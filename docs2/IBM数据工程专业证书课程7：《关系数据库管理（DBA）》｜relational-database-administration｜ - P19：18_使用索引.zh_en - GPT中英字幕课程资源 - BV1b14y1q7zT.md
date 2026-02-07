# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P19：18_使用索引.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/d6c2c40ba366916756b9d8816aa242f5_0.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_1.png)

Welcome to using Ines After watching this video， you will be able to explain how indexing improves query performance。

 create effective indexes， describe the different types of database indexes， create primary keys。

 create and drop database indexes， and list the considerations for creating indexes。



![](img/d6c2c40ba366916756b9d8816aa242f5_3.png)

So what is a database index， much like the index in a book helps you find information in the book faster。

 an index for a database makes finding information in the database faster， For example。

 if you search a book without an index， you must search every page in the book to find information you want and similarly。

 if a computer searches a database without an index。

 it must search the entire database to find the information， which can be very slow。

 particularly in a very large database a database index， however。

 can significantly improve search performance for a database。



![](img/d6c2c40ba366916756b9d8816aa242f5_5.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_6.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_7.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_8.png)

In a database， the index is essentially an ordered copy of selected columns of table data and is designed to enable efficient searches without having to search every row in a database table every time it is accessed。

The columns selected to make an index are typically defined by administrators and can be based on many factors such as frequently searched terms In this example。

 we are selecting the customer ID column regardless of how they are constructed。

 the overall goal of an index is to help users find the information they need quickly and easily So an index serves as a lookup table with a pointer or link to the original rows in the base table for which the index is created an index can include one or more columns in the table however。

 while indexes can improve database performance。 they also require additional storage space and maintenance。

 because they must be continually updated for any database。

 you will likely have to experiment with different types of indexes and indexing options。

 This will help you find an optimal balance of query performance and index maintenance such as how much disk space and activity are required。



![](img/d6c2c40ba366916756b9d8816aa242f5_10.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_11.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_12.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_13.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_14.png)

To keep the index up to date， for example， narrow indexes or indexes with relatively few columns in the index key take up less disk space and require less overhead to maintain。

 whereas wide indexes， while they may cover a greater number of queries also require more space and maintenance。



![](img/d6c2c40ba366916756b9d8816aa242f5_16.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_17.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_18.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_19.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_20.png)

There are many different types and methods of indexing databases。

 The main types can generally be described as one of the following。

 The primary key is a special type of index that is always unique， non nullable。

 and there can only be one per table。 It is also clustered。

 meaning that the data is actually stored in the underlying table in the same order as the primary key。

 Each table can also have any number of additional or secondary indexes， other than the primary key。

 These are noncled and can have single or multiple columns。 Indes can be defined as unique or nonun。



![](img/d6c2c40ba366916756b9d8816aa242f5_22.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_23.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_24.png)

Ordering of columns is important because an index will be sorted in the order in which columns are specified when the index is created。

 sorting can be ascending， which is the default or descendending。

 but it will sort by the first column first， then by the next column and so on。

The primary key of a table uniquely identifies each row in a table。

 while having a primary key is optional in some RDBMSss。

 it is generally a good practice to create one when creating a table。

 it may also be possible to add a primary key later by altering the table。



![](img/d6c2c40ba366916756b9d8816aa242f5_26.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_27.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_28.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_29.png)

The first code block on this screen shows the general syntax for creating a primary key when creating a table。

The second code block shows a simple example。 This example would create a table called team with the team ID column as the primary key。

If the primary key consists of multiple columns， you can even specify the primary key constraint after defining all of the columns。

 you simply add the primary key option， then specify the column names in parentheses。



![](img/d6c2c40ba366916756b9d8816aa242f5_31.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_32.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_33.png)

Since primary keys need to have unique values， one way to ensure that is to create automatically generated incrementing values for the primary key columns in DB2。

 these are calledI columns， and they can be created by specifying the keywords generated by default as identity after the column definition。

 and in my SQL， you simply add the auto underscore increment keyword after the column definition。



![](img/d6c2c40ba366916756b9d8816aa242f5_35.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_36.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_37.png)

The basic syntax for creating an index is shown in the first code block。

 you use the Cate index statement to define an index。

 and you use the on statement to specify on which database table to create it。

 you specify the column names in parentheses， and the order in which you enter them dictates the index's sort order。



![](img/d6c2c40ba366916756b9d8816aa242f5_39.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_40.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_41.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_42.png)

Here are a couple of examples。 The first one creates a unique index named unique nu in the project table with a column namedProdge name。

 meaning that the project table cannot have multiple rows with the same Pro name value When the on table name is specified。

 the unique option prevents the table from containing two or more rows with the same value of the index key。

 The second example creates an index named job by DPT in the employee table。

 and it includes work Dept and job columns in that order。 This one is not unique。

 so the table can have multiple rows with the same workdept and job columns but the benefit of the index is that the query filtering on those fields will be faster than those without an index。



![](img/d6c2c40ba366916756b9d8816aa242f5_44.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_45.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_46.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_47.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_48.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_49.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_50.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_51.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_52.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_53.png)

To delete an index， you use the drop statement。 Droping an index does not cause any other objects to be dropped。

 but will cause packages that have a dependency on the dropped index or index specification to be invalidated。

 This example deletes the index named job by DPT。 A primary key or unique key index cannot be explicitly dropped using the drop statement。

 Deleting the primary index or a unique key index is done through the Al table statement。

 After the primary key or unique key is deleted using Al table。

 The index is no longer considered the primary index or unique index。

 and it can be explicitly dropped using the drop statement。



![](img/d6c2c40ba366916756b9d8816aa242f5_55.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_56.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_57.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_58.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_59.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_60.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_61.png)

One of the major sources of database application bottlenecks can be poorly designed indexes or a lack of sufficient appropriate indexes。

 therefore， designing efficient indexes is vital for optimizing database application performance when designing an index you should consider the following core principles Understand how the database will be used。

 for example， will it be used for heavy online transaction processing or for the storage and retrieval of large data sets。



![](img/d6c2c40ba366916756b9d8816aa242f5_63.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_64.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_65.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_66.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_67.png)

Understand the most frequently used queries。 For example。

 if you know that a frequently used query joins two or more tables that may assist you in deciding the most appropriate index type to use。

 and understand the characteristics of the columns。 For example， what kind of data will they contain。

 Will they contain integer values， Will they be unique。

 knowing these characteristics from the outset will help you choose an appropriate index type。



![](img/d6c2c40ba366916756b9d8816aa242f5_69.png)

You will also need to consider when creating or maintaining an index which indexing options will best improve its performance。

 For example， if you are creating a clustered index on an existing large table。

 it would be a good idea to use the online index option as it permits concurrent activity on the underlying data while the index is being built。

 and where is the best place to store the index， where you decide to store your indexes can improve query performance by increasing the performance of disk input output operations For example。

 if you store a non-cllustered index on a storage group located on a different disk than where the table storage group is located。

 it can improve performance as both disks could be read simultaneously。



![](img/d6c2c40ba366916756b9d8816aa242f5_71.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_72.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_73.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_74.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_75.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_76.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_77.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_78.png)

In this video， you learned that database indexes can significantly improve search performance for a database Dataase indexes can be either primary key indexes or nonprimary key indexes that is standard indexes primary keys can be defined when creating tables The create index statement is used to define an index on a database table and the drop statement is used to drop or delete an index a primary key or unique key index cannot be explicitly dropped using the drop statement it must be dropped by using the Al table statement first one of the major sources of database application bottlenecks is poorly designed indexes or a lack of sufficient appropriate indexes and finally。

 designing efficient indexes is vital for getting optimal database application performance。



![](img/d6c2c40ba366916756b9d8816aa242f5_80.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_81.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_82.png)

![](img/d6c2c40ba366916756b9d8816aa242f5_83.png)