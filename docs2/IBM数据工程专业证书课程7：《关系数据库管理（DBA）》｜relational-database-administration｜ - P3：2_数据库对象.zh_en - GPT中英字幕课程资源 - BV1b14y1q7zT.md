# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P3：2_数据库对象.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/5edce115bcd5f6c3dfe13fd22df98edf_0.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_1.png)

Welcome to database Ob After watching this video， you will be able to recall the hierarchy of database objects。

 describe an instance of a database， define the term schema and list commonly used database objects。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_3.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_4.png)

Relational database management systems or RDBMSs contain many objects that database engineers and database administrators must organize。

 storing tables， constraints， indexes and other database objects in a hierarchical structure allows DBAs to manage security。

 maintenance and accessibility。

![](img/5edce115bcd5f6c3dfe13fd22df98edf_6.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_7.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_8.png)

This example hierarchy gives you an overview of how RDBMSss are structured。

 although slight variations may occur between products， most RDBMSss begin with an instance。

 a single way of organizing the database and everything it contains many RDBMSss permit more than one database within a single instance。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_10.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_11.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_12.png)

You will generally find at least one schema at some level in the hierarchy A schema is a logical grouping of objects within a database。

 Schemas define how database objects are named and prevent ambiguous references Some RDBMSss consider the schema a apparent object of a database and others consider it a database object within a schema are the database objects including tables。

 constraintsstrain and indexes。

![](img/5edce115bcd5f6c3dfe13fd22df98edf_14.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_15.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_16.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_17.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_18.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_19.png)

Now， an instance is a logical boundary for a database or set of databases where you organize database objects and set configuration parameters every database within an instance is assigned a unique name。

 has its own set of system catalog tables which keep track of the objects within the database。

 and has its own configuration files。

![](img/5edce115bcd5f6c3dfe13fd22df98edf_21.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_22.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_23.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_24.png)

You can create more than one instance on the same physical server。

 providing a unique database server environment for each instance。

 the databases and their objects within one instance are isolated from those in any other instance。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_26.png)

You can use multiple instances when you want to use one instance for a development environment and another instance for a production environment。

 restrict access to sensitive information or control high level administrative access。

Not all RDBMSs use the concept of instances， often managing database configuration information in a special database instead。

 in cloud based RDBMSs， the term instance means a specific running copy of a service。

A schema is a specialized database object that provides a way to group other database objects logically。

 a schema can contain tables， indexes， constraints， and other objects。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_28.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_29.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_30.png)

When you create a database object， you can assign it to a schema in most R DBMSSs。

 the default schema is the user schema for the currently logged on user。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_32.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_33.png)

Many RDBMSs use a specialized schema to hold configuration information and metadata about a particular database。

 for example， tables in a system schema can store lists of database users and their access permissions。

 information about the indexes on tables， details of any database partitions that exist and user definedfined database types。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_35.png)

Datase objects are the items that exist within the database。

 the process of database design includes defining database objects and their relationships with each other。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_37.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_38.png)

You can create and manage database objects through graphical database management tools。

 scripting or accessing the database through an API If you use SQL to create or manage the object。

 you will use data definition language statements like C or Al。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_40.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_41.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_42.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_43.png)

In most RDBMSs， you can create objects such as tables。

 logical structures consisting of rows and columns which store data constraints within any business data is often subject to certain restrictions or rules for example。

 an employee number must be unique constraints provide a way to enforce such rules。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_45.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_46.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_47.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_48.png)

Indexes an index is a set of pointers used to improve performance and ensure the uniqueness of the data Keys。

 a key uniquely identifies a row in a table keys enable DBAs to define the relationships between tables。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_50.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_51.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_52.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_53.png)

Views a view provides a different way of representing the data in one or more tables。

 A view is not an actual table and requires no permanent storage。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_55.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_56.png)

Aliases an alias is an alternative name for an object such as a table DBAs use aliases to provide shorter。

 simpler names to reference objects Even an event is a data manipulation language。

 DL or data definition language DDL action on a database object that can initiate a trigger triggers a trigger defines a set of actions performed in response to an insert。

 update or delete on a specified table and finally。

 log files log files store information about transactions in a database。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_58.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_59.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_60.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_61.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_62.png)

In this video， you learned that an instance is a logical boundary for a database or set of databases where you organize database objects and set configuration parameters a schema is a specialized database objects that provides a way to group other database objects logically schemas also provide a naming context for database objects。

 and database objects are the items that exist within the database such as tables， constraints。

 indexes， keys， views， aliases， triggers， events and log files。



![](img/5edce115bcd5f6c3dfe13fd22df98edf_64.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_65.png)

![](img/5edce115bcd5f6c3dfe13fd22df98edf_66.png)