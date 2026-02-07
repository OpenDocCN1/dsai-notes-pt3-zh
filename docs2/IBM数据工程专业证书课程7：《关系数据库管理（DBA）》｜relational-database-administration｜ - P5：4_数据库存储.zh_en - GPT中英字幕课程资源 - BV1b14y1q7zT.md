# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P5：4_数据库存储.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/ce81e28b47ef6b604676d37be3cddd45_0.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_1.png)

Welcome to database Stor After watching this video you will be able to differentiate between physical and logical storage。

 describe table spaces and explain their benefits， describe storage groups and their function。

 and identify when to use partitions。

![](img/ce81e28b47ef6b604676d37be3cddd45_3.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_4.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_5.png)

As a DbaA， you'll be responsible for ensuring that your database has enough storage space for all the data that it needs to store。

 you must determine the capacity required for the database and plan for growth in cloudbased databases expanding your storage space is performed through an API or a graphical console One of the advantages of using a cloudbased database is that it is so easy to scale up and scale down in terms of storage space In a self-managed or onpres environment。

 you can also plan storage space for improved performance。

 storing competing resources on different disks。 R DBMSs is separate the physical storage of data files on disk from the logical design of the database allowing more flexibility in managing the database files you can manage the data through a logical object without being concerned about the nature of the physical storage For example。

 you can issue a command to back up。

![](img/ce81e28b47ef6b604676d37be3cddd45_7.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_8.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_9.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_10.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_11.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_12.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_13.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_14.png)

A database without having to specify all the physical disks that store the database。



![](img/ce81e28b47ef6b604676d37be3cddd45_16.png)

Table spaces are structures that contain database objects such as tables， indexes。

 large objects and long data DBAs use table spaces to logically organize database objects based on where their data is stored T spaces define the mapping between logical database objects and the physical storage containers that house the data for these objects a storage container can be a data file a directory or a raw device。



![](img/ce81e28b47ef6b604676d37be3cddd45_18.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_19.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_20.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_21.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_22.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_23.png)

Tablespaces contain one or more database objects In this example。

 Tablespace1 contains multiple small tables， whereas T Space 2 only houses a single large table。

 and table Space 3 contains frequently used indexes。

DBAs configure one or more storage containers to store each table space In this example。

 container1 stores table Space1， containers2 and3 store table Space2。

 and container4 stores table Space 4。By using the combination of table spaces and containers。

 you can keep logical database storage separate from physical storage and manage the disk layout of a database and its objects This results in several benefits performance you can use table spaces to optimize performance For example。

 you can place a heavily used index on a fast SSDAlternativelyly you can store tables containing rarely accessed or archived data on a less expensive but slower magnetic hard drive。



![](img/ce81e28b47ef6b604676d37be3cddd45_25.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_26.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_27.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_28.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_29.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_30.png)

Recoverability Tablespaces make backup and restore operations more convenient using a single command。

 you can make a backup or restore all the database objects without worrying about which storage container each object or table space is stored on and storage management。

 the RDBMS creates and extends the data files or containers depending on the need when necessary。

 you can also manually expand the storage space by adding another storage path or container to the table space。



![](img/ce81e28b47ef6b604676d37be3cddd45_32.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_33.png)

Some RDBMSSs provide storage groups， a storage group is a grouping of storage paths or containers based on similar performance characteristics This allows you to perform multi-temper data management more easily In this context temperature refers to the frequency of data access Ho data is accessed very frequently。

 warm data is accessed somewhat frequently and cold data is accessed infrequently。



![](img/ce81e28b47ef6b604676d37be3cddd45_35.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_36.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_37.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_38.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_39.png)

By using storage groups， you can organize your data and storage based on temperature In this example。

 very frequently accessed hot tables can be placed in tablespace H。

 which is distributed on a group of fast storage devices。

 somewhat frequently accessed tables in tablespaces W1 and W2 can be stored on a warm storage group。

 and the least frequently accessed tables in tablespace C can be stored on slower and less expensive storage devices in a cold group。

 U storage groups helps with optimizing performance for frequently accessed data and reducing costs for storing infrequently accessed data。



![](img/ce81e28b47ef6b604676d37be3cddd45_41.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_42.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_43.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_44.png)

A partitioned relational database is a relational database whose data is managed across multiple database Partitions you can partition tables that need to contain very large quantities of data into multiple logical partitions with each partition containing a subset of the overall data database partitioning is used in scenarios that involve very large volumes of data。

 such as data warehousing and data analysis for business intelligence。



![](img/ce81e28b47ef6b604676d37be3cddd45_46.png)

In this video you learned that database storage is managed through logical database objects and physical disk files tablespaces are structures that organize database objects based on where their data is stored。

 storage groups are groupings of storage paths or containers based on similar performance characteristics。

 and partition store subsets of data from a very large database to improve performance。



![](img/ce81e28b47ef6b604676d37be3cddd45_48.png)

![](img/ce81e28b47ef6b604676d37be3cddd45_49.png)