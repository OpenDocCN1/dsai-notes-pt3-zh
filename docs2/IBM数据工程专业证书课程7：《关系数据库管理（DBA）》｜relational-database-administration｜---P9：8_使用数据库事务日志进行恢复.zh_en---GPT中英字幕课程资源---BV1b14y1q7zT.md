# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P9：8_使用数据库事务日志进行恢复.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_0.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_1.png)

Welcome to using database Trans logs for recovery After watching this video you will be able to describe database transaction logs。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_3.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_4.png)

Explain the primary uses of transaction logs， indicate where transactional logs are stored and how to access them。

 and identify the typical structure of a transactional log。Separate from the diagnostic log。

 a database management system or DBMS uses transaction logs to keep track of all transactions that change or modify the database the information stored in these transaction logs can be used for recovery purposes when data is accidentally deleted or a system or hardware failure such as a discra occurs in case of such events。

 the transaction log in conjunction with a database backup can help restore your database back to a consistent state at a specific point in time。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_6.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_7.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_8.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_9.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_10.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_11.png)

For example， in this timeline at time T1， you issue the backup command to make a full copy of your database。

 users then continue working and the information about their activities is kept in transaction logs。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_13.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_14.png)

At time T2， there is a problem that damages the database， so at time T3。

 you issue a store command using the backup image you took at time T1。

 This allows you to get the database back to the point in time that the backup was taken。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_16.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_17.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_18.png)

Then at Time T4， you apply the transaction logs for a period of time between T1 and T2 to the restored database This process of applying committed transactions from transaction logs is called roll Forward Recover and it returns your database to the point just before the crash happened。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_20.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_21.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_22.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_23.png)

You typically specify where you want transaction log files to be stored using the database configuration Here is an example location of a DB2 transaction log file directory in an SQ log Deer subdirecty on a Windows system。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_25.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_26.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_27.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_28.png)

In PostgresQL， the log files default to being stored in the PGX log subdirecty In PostgresQL。

 the transaction log file is referred to as a write a head log or wall。

 because before the database manager writes the database changes or transactions to database files。

 the DBMS first writes them to the wall。A recommended best practice。

 at least for production databases is to place the transaction log files on storage volumes that are separate from where the database objects like table spaces are stored。

 this not only helps with performance， so database rights are not competing with log rights。

 but also improves recoverability since it isolates logs from crashes or the corruption of database volumes。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_30.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_31.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_32.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_33.png)

For even more enhanced recoveryability in business critical databases。

 some relational database management systems or RDBMSs provide the ability to automatically mirror logs to a second set of storage devices。

 or you can write scripts to copy or ship logs to remote replicas or standby systems in a process called log shipping。

In many RGBMSSs， like DB2 and SQL Ser， transaction logging is enabled by default。

 but you still may want to change the default settings for improved recoverability and performance In other RGBMSSs like my SQL transaction logging is disabled by default and may need to be manually configured。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_35.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_36.png)

For My SQL， you can run the show binaryary logs command to check if logging is enabled， and if it is。

 you will see a list of the log files。Unlike other types of logs。

 such as diagnostic and error logs that are mostly in text format and human readable。

 the database transaction logs are typically in binary formats that are sometimes encrypted and require specialized tools to format and display contents。

For example， in MySQL， you use the MySQL bin Lo tool to view the contents of MySQL transaction log files。

 also known as binary logs， the sample output shows a log file entry for an insert statement。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_38.png)

And for DB2， you use the DB2 FMT log tool for formatting and displaying log file information。

 The sample output shows a record for a DDL statement to create a table。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_40.png)

A log file contains multiple entries and the information they contain may vary depending on the RGBMS。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_42.png)

For example， a typical database log record in DB2 is made up of a log transaction ID number。

 which is a unique ID for the log record， the database record type。

 which describes the type of database log record， a log sequence number which is a reference to the database transaction generating the log record。

 a previous log sequence number is a link to the last log record。

 this implies that database logs are constructed in linked list form。

 and information which details the actual changes that trigger the log record to be written。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_44.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_45.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_46.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_47.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_48.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_49.png)

In this video， you learned that database transaction logs keep track of all activities that change the database structure and record transactions that insert。

 update or delete data in the database transaction logs assist with recovery of databases in case of a system failure。

 disc corruption or accidental deletion， by applying or replay transactions in the log。

 the database can be recovered or rolled forward to a point in time before a database catastrophic event a good practice is to store log files in a location separate from database volumes by changing default settings in the database configuration and the format of transaction logs varies by RGBMS but each log entry typically contains a log record ID and details about the database activity or transaction that modified the database。



![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_51.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_52.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_53.png)

![](img/2f8d031b8cf7aa9b7a6d5b1f7e05b74b_54.png)