# IBM数据工程专业证书课程4：《关系数据库导论（RDBMS）》｜introduction-to-relational-databases｜ - P20：19_包括模式在内的数据库对象层次结构.zh_en - GPT中英字幕课程资源 - BV1Mj4116716

![](img/c7de4960137690919e6f1728a6b4dafb_0.png)

![](img/c7de4960137690919e6f1728a6b4dafb_1.png)

Welcome to database Object and Hierarchy。

![](img/c7de4960137690919e6f1728a6b4dafb_3.png)

After watching this video you will be able to recall the hierarchy of database objects。

 describe an instance of a database， define the termreal database。

 explain when to create a new database， define the term schema。

 compare user schemas and system schemas， describe a database partition。

 and list commonly used database objects。

![](img/c7de4960137690919e6f1728a6b4dafb_5.png)

Relational database management systems or RDBMSss contain many objects that database engineers and database administrators must organize Storing tables。

 constraints， indexes and other database objects in a hierarchical structure allows database administrators to manage security。

 maintenance and accessibility， this example hierarchy gives you an overview of how RDBMSss are structured。

 although slight variations may occur between products。



![](img/c7de4960137690919e6f1728a6b4dafb_7.png)

![](img/c7de4960137690919e6f1728a6b4dafb_8.png)

![](img/c7de4960137690919e6f1728a6b4dafb_9.png)

![](img/c7de4960137690919e6f1728a6b4dafb_10.png)

![](img/c7de4960137690919e6f1728a6b4dafb_11.png)

Most R DBMss begin with an instance， a single way of organizing the database and everything it contains。

 Many R DBMss permit more than one database within a single instance。



![](img/c7de4960137690919e6f1728a6b4dafb_13.png)

![](img/c7de4960137690919e6f1728a6b4dafb_14.png)

You will generally find at least one schema at some level in the hierarchy。

 a schema is a logical grouping of objects within a database。



![](img/c7de4960137690919e6f1728a6b4dafb_16.png)

![](img/c7de4960137690919e6f1728a6b4dafb_17.png)

Schemas define how database objects are named and prevent ambiguous references。

 Some RGBMSss consider the schema a apparent object of a database。

 and others consider it a database object Within a schema are the database objects， including tables。

 constraints and indexes。

![](img/c7de4960137690919e6f1728a6b4dafb_19.png)

![](img/c7de4960137690919e6f1728a6b4dafb_20.png)

![](img/c7de4960137690919e6f1728a6b4dafb_21.png)

An instance is a logical boundary for a database or set of databases where you organize database objects and set configuration parameters。

 Every database within an instance is assigned a unique name has its own set of system catalog tables which keep track of the objects within the database and has its own configuration files。

 you can create more than one instance on the same physical server providing a unique database server environment for each instance。

 the databases and other objects within one instance are isolated from those in any other instance。

 you can use multiple instances when you want to use one instance for a development environment and another instance for a production environment。

 restrict access to sensitive information or control highlevel administrative access。



![](img/c7de4960137690919e6f1728a6b4dafb_23.png)

![](img/c7de4960137690919e6f1728a6b4dafb_24.png)

![](img/c7de4960137690919e6f1728a6b4dafb_25.png)

![](img/c7de4960137690919e6f1728a6b4dafb_26.png)

![](img/c7de4960137690919e6f1728a6b4dafb_27.png)

![](img/c7de4960137690919e6f1728a6b4dafb_28.png)

![](img/c7de4960137690919e6f1728a6b4dafb_29.png)

Not all RDBMSss use the concept of instances， often managing database configuration information in a special database instead。

 in cloud based RDBMSs， the term instance means a specific running copy of a service。

A relational database is a set of objects used to store， manage and access data。

 These objects include tables， View， indexes， functions， triggers and packages。

 database objects can be either defined by the system built in objects or defined by the user user defined objects in a relational database database engineers establish relationships between tables to reduce redundant data and improve data integrity。

 a distributed relational database shares tables and other objects across different but interconnected computer systems。



![](img/c7de4960137690919e6f1728a6b4dafb_31.png)

![](img/c7de4960137690919e6f1728a6b4dafb_32.png)

![](img/c7de4960137690919e6f1728a6b4dafb_33.png)

A schema is a specialized database object that provides a way to group other database objects logically。

 A schema can contain tables， View， nicknames， triggers， functions packages and other objects。

 When you create a database object， you can assign it to a schema。

 If you want to assign the object to a specific schema。 you can explicitly include the schema name。

 If you don't include the schema name。 the object is implicitly assigned to the current schema。

 In most RDBMSss， the default schema is the user schema for the currently logged on user。

 A schema also provides a naming context。 using the schema name as a name qualifier enables you to distinguish between objects with the same name in different schemas。

 For example， the schema names internal and external。

 make it easy to distinguish two different sales tables。



![](img/c7de4960137690919e6f1728a6b4dafb_35.png)

![](img/c7de4960137690919e6f1728a6b4dafb_36.png)

![](img/c7de4960137690919e6f1728a6b4dafb_37.png)

![](img/c7de4960137690919e6f1728a6b4dafb_38.png)

![](img/c7de4960137690919e6f1728a6b4dafb_39.png)

![](img/c7de4960137690919e6f1728a6b4dafb_40.png)

![](img/c7de4960137690919e6f1728a6b4dafb_41.png)

![](img/c7de4960137690919e6f1728a6b4dafb_42.png)

![](img/c7de4960137690919e6f1728a6b4dafb_43.png)

![](img/c7de4960137690919e6f1728a6b4dafb_44.png)

Internal dot sales in the internal schema and external dot sales in the external schema。 thus。

 schemas enable multiple applications to store data in a single database without encountering namespace conflicts。

Many RDBMSss use a specialized schema to hold configuration information and metadata about a particular database。

 for example， tables in a system schema can store lists of database users and their access permissions。

 information about the indexes on tables， De of any database partitions that exist and user definedfined database types。

A partitioned relational database is a relational database whose data is managed across multiple database partitions。

 You can partition tables that need to contain very large quantities of data into multiple logical partitions with each partition containing a subset of the overall data Data partitioning is used in scenarios that involve very large volumes of data such as data warehousing and data analysis for business intelligence。



![](img/c7de4960137690919e6f1728a6b4dafb_46.png)

![](img/c7de4960137690919e6f1728a6b4dafb_47.png)

Database objects are the items that exist within the database。

 The process of database design includes defining database objects and their relationships with each other。

 In most RDBMSses， you can create objects such as tables。

 logical structures consisting of rows and columns which store data Const within any business data is often subject to certain restrictions or rules。

 For example， an employee number must be unique。 Contraint provide a way to enforce such rules。 Ines。

 An index is a set of pointers used to improve performance and ensure the uniqueness of the data View A view provides a different way of representing the data in one or more tables。

 A view is not an actual table and requires no permanent storage and aliases。

 and alias is an alternative name for an object， such as a table。



![](img/c7de4960137690919e6f1728a6b4dafb_49.png)

![](img/c7de4960137690919e6f1728a6b4dafb_50.png)

![](img/c7de4960137690919e6f1728a6b4dafb_51.png)

![](img/c7de4960137690919e6f1728a6b4dafb_52.png)

It can be used to provide a shorter， simpler name to reference an object。

You can create and manage database objects through graphical database management tools。

 scripting or accessing the database through an API If you are using SQL to create or manage the object。

 you will use data definition language statements like createate or Al。In this video。

 you learned that an instance is a logical boundary for a database or set of databases where you organize database objects and set configuration parameters。

 A relational database is a set of objects used to store。

 manage and access data relationships between tables reduce redundant data and improve database integrity。

 A schema is a specialized database object that provides a way to logically group tables， View。

 nicknames， triggers， functions， packages and other database objects。

 Schemas provide naming contexts， so you can distinguish between objects with the same name。



![](img/c7de4960137690919e6f1728a6b4dafb_54.png)

![](img/c7de4960137690919e6f1728a6b4dafb_55.png)

User schemas contain database objects like tables， views and functions System schemas contain configuration information and metadata for the database。

 You can split very large tables across multiple partitions to improve performance。

 and database objects are the items that exist within the database， such as tables， constraints。

 indexes， views and aliases。

![](img/c7de4960137690919e6f1728a6b4dafb_57.png)