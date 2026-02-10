# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P18：17_优化数据库.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/3317e4c59631b26db6854797b45592bb_0.png)

![](img/3317e4c59631b26db6854797b45592bb_1.png)

Welcome to Opimizing databases After watching this video you will be able to describe why you need to optimize your databases。

 describe the optimized table command for MySQL， describe the vacuum and reindex commands for PostgresQL。

 and describe the Runs staats and reorg commands for DB2。



![](img/3317e4c59631b26db6854797b45592bb_3.png)

![](img/3317e4c59631b26db6854797b45592bb_4.png)

First off， let's ask the obvious question， Why do you need to optimize your databases Well。

 over time as the volume of data stored in your databases increases and the operational workloads increase。

 data can become fragmented Ts can be left empty or partially empty and database performance can suffer by optimizing your databases。

 you can identify bottlenecks， fineted database queries and ultimately reduce database response times for your users。



![](img/3317e4c59631b26db6854797b45592bb_6.png)

![](img/3317e4c59631b26db6854797b45592bb_7.png)

![](img/3317e4c59631b26db6854797b45592bb_8.png)

![](img/3317e4c59631b26db6854797b45592bb_9.png)

![](img/3317e4c59631b26db6854797b45592bb_10.png)

![](img/3317e4c59631b26db6854797b45592bb_11.png)

![](img/3317e4c59631b26db6854797b45592bb_12.png)

Each relational database system has its own utilities or commands for optimizing its databases。

 for example， for MySQL databases， you can use the optimized T command for PostgresQL databases。

 you can use the vacuum and reindex commands and in DB2， you can use the Runstats and reorg commands。

If your MySQL database receives a significant number of insert update or delete operations。

 it can lead to fragmentation of your data files， meaning that a lot of unused space is wasted which in turn can impact your database's performance Therefore。

 it is recommended that database admins， defrag their MySQL tables on a regular basis In MySQL。

 the optimize table command reorganizes the physical storage of table data and associated index data to reduce storage space and improve input output efficiency when accessing a table to use the optimized table command。

 you need to have select and insert privileges for the tables you are working on This example would optimize three different tables in one operation you could also use a graphical tool such as PhP My admin to optimize tables in MySQL。



![](img/3317e4c59631b26db6854797b45592bb_14.png)

![](img/3317e4c59631b26db6854797b45592bb_15.png)

![](img/3317e4c59631b26db6854797b45592bb_16.png)

![](img/3317e4c59631b26db6854797b45592bb_17.png)

The vacuum command can be used on your PostgresQL database to perform garbage collection and optionally analysis tasks。



![](img/3317e4c59631b26db6854797b45592bb_19.png)

Vacuum reclaims lost storage space consumed by dead tus。

 which are not physically removed from their database tables after being deleted or made obsolete by an update during routine PostgresqL operations。

 regularly reclaiming this lost storage space can help improve your database's overall performance in PostgresqL Please note that if the auto vacuum feature is enabled。

 then PostresqL will automate the vacuum maintenance process for you。In these examples。

 when you run vacuum with no parameters， the command will free up space on every table in every database that the current user has the rights to perform this command on。



![](img/3317e4c59631b26db6854797b45592bb_21.png)

![](img/3317e4c59631b26db6854797b45592bb_22.png)

![](img/3317e4c59631b26db6854797b45592bb_23.png)

If you specify the name of a table， then the command will only process and free up space on that table without the full parameter。

 the vacuum command can run alongside normal read and write table operations as it does not require an exclusivity lock and any reclaimed space is retained for future reuse within the table it was vacuumed from however。

 if you specify the full parameter， the command will create a complete copy of the table contents and write it to disk with no unused space。

 which allows the space to be reclaimed by the operating system。

 So using the full parameter can reclaim more space for you。

 but it takes much longer to run and requires an exclusivity lock on each table while it is being processed。



![](img/3317e4c59631b26db6854797b45592bb_25.png)

![](img/3317e4c59631b26db6854797b45592bb_26.png)

![](img/3317e4c59631b26db6854797b45592bb_27.png)

![](img/3317e4c59631b26db6854797b45592bb_28.png)

![](img/3317e4c59631b26db6854797b45592bb_29.png)

![](img/3317e4c59631b26db6854797b45592bb_30.png)

![](img/3317e4c59631b26db6854797b45592bb_31.png)

![](img/3317e4c59631b26db6854797b45592bb_32.png)

![](img/3317e4c59631b26db6854797b45592bb_33.png)

In PostwesQL， you can use the reindex command to rebuild one or more indexes Reinex rebuilds an index using the data stored in the index'es table and replaces the previous older version of the index it can be used when software bugs or hardware failures have corrupted an index or when an index has become bloated and contains numerous empty or nearly empty pages you need to be the owner of the index or the table or the database in order to reind it。



![](img/3317e4c59631b26db6854797b45592bb_35.png)

![](img/3317e4c59631b26db6854797b45592bb_36.png)

![](img/3317e4c59631b26db6854797b45592bb_37.png)

![](img/3317e4c59631b26db6854797b45592bb_38.png)

When you use re index， it builds the index contents from scratch， and therefore。

 it has a very similar effect as dropping and recreating an index。 However。

 the way that lockson reads and writes works on them is different。

 Here are some re index usage examples。The first example will rebuild the index named My index。

 The second example will rebuild all the indexes on the table named My table。In DB2。

 the Runstats command updates statistics in the system catalog about the characteristics of a table。

 associated indexes or statistical views these characteristics include number of records。

 number of pages and average record length The optimizer uses these statistics to determine access paths to the data。



![](img/3317e4c59631b26db6854797b45592bb_40.png)

![](img/3317e4c59631b26db6854797b45592bb_41.png)

For a table， call the Runstats command when the table has had many updates。

 or after the table is reorganized for tables， this command collects statistics for a table on the database partition from which it is invoked If the table does not exist on that database partition。

 the first database partition in the database partition group is selected。For a statistical view。

 call the Runstat's command when changes to underlying tables substantially affect the rows that are returned by the view。

 the view must be previously enabled for use in query optimization by using the altar view statement。

For views， this command collects statistics by using data from tables on all participating database partitions。

Here are some usage examples， the first example collects statistics on the table only with distribution statistics on the employee ID and employee name columns。

 and the second example collects statistics on a set of indexes。



![](img/3317e4c59631b26db6854797b45592bb_43.png)

In DB2， the reorg T command reorganizes a table by reconstructing the rows to eliminate fragmented data and by compacting information。



![](img/3317e4c59631b26db6854797b45592bb_45.png)

![](img/3317e4c59631b26db6854797b45592bb_46.png)

On a partition table， you can reorganize a single partition in terms of its scope。

 the reorg table command affects all database partitions in the database partition group。

 Here is a simple usage example。 This example will reorganize a table to reclaim space by using a temporary table space named My T1。

In DB2， the reorg index command reorganizes indexes。

 you can reorganize all indexes that are defined on a table by rebuilding the index data into unfragmented。

 physically contiguous pages。

![](img/3317e4c59631b26db6854797b45592bb_48.png)

On a data partition table， you can reorganize a specific non-partitioned index on a partitioned table。

 or you can reorganize all the partitioned indexes on a specific data partition if you specify the cleanup option of the index clause cleanup is performed without rebuilding the indexes。

 you can clean up a specific index on a table or you can clean up all of the indexes on the table In terms of its scope。

 the reorg index command affects all database partitions in the database partition group。

In this video， you learned that optimizing your databases can improve response times and increase overall performance relational database management systems provide their own utilities or commands for optimizing databases in My SQL。

 you can use the optimized table command in PostgresQL you can use the vacuum and reinex commands。

 and in DB2 you can use the Runstats and reorg commands。



![](img/3317e4c59631b26db6854797b45592bb_50.png)