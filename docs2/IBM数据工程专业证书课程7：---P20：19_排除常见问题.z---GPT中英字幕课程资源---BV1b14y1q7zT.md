# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P20：19_排除常见问题.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/2c4cf232da3a4794baec513aae5e5131_0.png)

![](img/2c4cf232da3a4794baec513aae5e5131_1.png)

Welcome to troubleubshooting common Iss。

![](img/2c4cf232da3a4794baec513aae5e5131_3.png)

After watching this video， you will be able to describe common performance configuration and connection issues。

 describe basic troubleshooting and solutions for common issues， and describe tools used to identify。

 prevent and solve common database issues。Troublesshooting is a process of identifying and solving a problem；

 it begins by answering the following questions。

![](img/2c4cf232da3a4794baec513aae5e5131_5.png)

What are the symptoms， Who or what is reporting the problem， Where is the problem happening。

 Is it specific to a platform environment， application or something else。

 When does the problem happen， Does it happen at a specific time multiple times or under specific conditions Also under which conditions does the problem happen and is the problem reproducible。



![](img/2c4cf232da3a4794baec513aae5e5131_7.png)

![](img/2c4cf232da3a4794baec513aae5e5131_8.png)

The most common problems encountered with databases are typically caused by one or more of the following。



![](img/2c4cf232da3a4794baec513aae5e5131_10.png)

Poor performance Poor performance can result in slow response to user queries or applications accessing the database Iroper configuration。

 improperly configured clients， servers or databases can cause a wide range of problems。

 including poor performance， crashes， errors or even database corruption， poor connectivity。

 poor connectivity can cause poor performance， timeouts or a variety of errors when interacting with the database。



![](img/2c4cf232da3a4794baec513aae5e5131_12.png)

![](img/2c4cf232da3a4794baec513aae5e5131_13.png)

![](img/2c4cf232da3a4794baec513aae5e5131_14.png)

![](img/2c4cf232da3a4794baec513aae5e5131_15.png)

![](img/2c4cf232da3a4794baec513aae5e5131_16.png)

![](img/2c4cf232da3a4794baec513aae5e5131_17.png)

Poor performance is usually caused by high latency for diskreads and write。

 slow processing time by the server or a poor connection between the server and client Any of these could be rooted in one or more of the following In server hardware or configuration For example。

 the server could be running out of disk space， memory or processing power。

 I these resources on the database server is called vertical scaling。

 adding additional database partitions and shards to improve performance is called horizontal scaling。



![](img/2c4cf232da3a4794baec513aae5e5131_19.png)

![](img/2c4cf232da3a4794baec513aae5e5131_20.png)

![](img/2c4cf232da3a4794baec513aae5e5131_21.png)

![](img/2c4cf232da3a4794baec513aae5e5131_22.png)

![](img/2c4cf232da3a4794baec513aae5e5131_23.png)

Immpproper configuration a poorly configured database may be operational but still unable to meet demand。

 For example， it may need to allow more connections or it may need changes to its buffering and indexing settings to keep up with queries and return results quickly。



![](img/2c4cf232da3a4794baec513aae5e5131_25.png)

![](img/2c4cf232da3a4794baec513aae5e5131_26.png)

![](img/2c4cf232da3a4794baec513aae5e5131_27.png)

Connectivity， a slow or poor network connection or limited bandwidth between the client and database can cause high latency and processing times。

 or queries and application logic a poorly written database query or improper application logic such as unnecessary locking of database objects can also result in performance issues。



![](img/2c4cf232da3a4794baec513aae5e5131_29.png)

![](img/2c4cf232da3a4794baec513aae5e5131_30.png)

An improperly or suboptily configured client server or database can cause any number of problems that can manifest in many ways。

 for example， a user with an incorrectly configured client or incorrect driver may be unable to connect to the database。

 a poorly or incorrectly configured server can reduce performance。

 cause timeouts or any number of possible errors， or the database may need to be configured to allow more connections or other settings like caching or indexing and may need to be adjusted to correct problems or improve overall performance。



![](img/2c4cf232da3a4794baec513aae5e5131_32.png)

![](img/2c4cf232da3a4794baec513aae5e5131_33.png)

![](img/2c4cf232da3a4794baec513aae5e5131_34.png)

![](img/2c4cf232da3a4794baec513aae5e5131_35.png)

![](img/2c4cf232da3a4794baec513aae5e5131_36.png)

![](img/2c4cf232da3a4794baec513aae5e5131_37.png)

![](img/2c4cf232da3a4794baec513aae5e5131_38.png)

![](img/2c4cf232da3a4794baec513aae5e5131_39.png)

Common issues with client configuration can be caused by incorrect logging credentials。

 an incorrect host name or IP address， or even a corrupt or outdated connection driver to fix these problems。

 check the client's driver configuration and verify the following the username and password specified in the connection settings are correct be sure to verify that the client is also configured to use the correct type of authentication such as Windows or SQL authentication for example。



![](img/2c4cf232da3a4794baec513aae5e5131_41.png)

![](img/2c4cf232da3a4794baec513aae5e5131_42.png)

![](img/2c4cf232da3a4794baec513aae5e5131_43.png)

![](img/2c4cf232da3a4794baec513aae5e5131_44.png)

![](img/2c4cf232da3a4794baec513aae5e5131_45.png)

![](img/2c4cf232da3a4794baec513aae5e5131_46.png)

The connection configuration settings such as IP address， host name and server name are correct。

 and the driver version for the database application is up to date and correct。



![](img/2c4cf232da3a4794baec513aae5e5131_48.png)

![](img/2c4cf232da3a4794baec513aae5e5131_49.png)

Server configuration also significantly impacts performance and operation Some examples of things you might change or configure to improve performance or correct a problem include add more physical RA or increase the memory assigned to the server add more physical disk space or assign additional disk space to the server consider upgrading the CPU or assigning more processing power to the server。

 consider def fragmentmenting the hard disk， fragmented data degrades overall performance。

 sometimes configuring the storage system appropriately can alleviate performance issues。

 for example， placing frequently access tables on a faster disk。

 and bugs in operating systems or in RDBMS software can result in errors and server crashes so ensure you regularly apply software patches and security updates to guard against this。



![](img/2c4cf232da3a4794baec513aae5e5131_51.png)

![](img/2c4cf232da3a4794baec513aae5e5131_52.png)

![](img/2c4cf232da3a4794baec513aae5e5131_53.png)

![](img/2c4cf232da3a4794baec513aae5e5131_54.png)

![](img/2c4cf232da3a4794baec513aae5e5131_55.png)

![](img/2c4cf232da3a4794baec513aae5e5131_56.png)

![](img/2c4cf232da3a4794baec513aae5e5131_57.png)

![](img/2c4cf232da3a4794baec513aae5e5131_58.png)

The configuration of the database is something you need to monitor and continually evaluate to ensure it meets demand。

 some examples of configuration settings you might need to change or correct are increase the number of allowed connections to the database to meet increasing demand。

 change database buffering to improve performance or change database indexing to improve performance。



![](img/2c4cf232da3a4794baec513aae5e5131_60.png)

![](img/2c4cf232da3a4794baec513aae5e5131_61.png)

![](img/2c4cf232da3a4794baec513aae5e5131_62.png)

![](img/2c4cf232da3a4794baec513aae5e5131_63.png)

![](img/2c4cf232da3a4794baec513aae5e5131_64.png)

Poor connectivity between the client and the database server can cause a wide range of problems。

 including poor performance， error messages or loss of function Some of the most common connectivity problems are typically caused by one of the following the database server cannot be reached or is not running properly the database instance on the server is not running properly。

 the client login credentials are incorrect or missing security settings such as for SSL connections。

 or the client configuration is incorrect。

![](img/2c4cf232da3a4794baec513aae5e5131_66.png)

![](img/2c4cf232da3a4794baec513aae5e5131_67.png)

![](img/2c4cf232da3a4794baec513aae5e5131_68.png)

![](img/2c4cf232da3a4794baec513aae5e5131_69.png)

Here are some common methods to help troubleshoot and solve basic connectivity issues。

 verify that the database server is running properly。

 the exact procedure depends on your configuration and environment。



![](img/2c4cf232da3a4794baec513aae5e5131_71.png)

![](img/2c4cf232da3a4794baec513aae5e5131_72.png)

For example， you may need to physically check on an on premiseise server。

 or you may need to verify that a virtual machine in a cloud service is running。



![](img/2c4cf232da3a4794baec513aae5e5131_74.png)

![](img/2c4cf232da3a4794baec513aae5e5131_75.png)

Next， verify that the database instance on the server is running This process varies depending on operating system and database。

 for example， on a Windows based system you could use the task manager to verify that the instance is running or on a DB2 configuration you could run DB2cd。

 and then issue commands in the command line。

![](img/2c4cf232da3a4794baec513aae5e5131_77.png)

![](img/2c4cf232da3a4794baec513aae5e5131_78.png)

![](img/2c4cf232da3a4794baec513aae5e5131_79.png)

![](img/2c4cf232da3a4794baec513aae5e5131_80.png)

Verify that the database can be reached from the client a common method is to use the Ping command from the client to communicate with the server's IP address or host name and finally。

 verify that the client connection driver is configured correctly for example。

 make sure the username and password for the connection are correct。

 and that the settings like IP address or host name or security and encryption protocols are also correct。



![](img/2c4cf232da3a4794baec513aae5e5131_82.png)

![](img/2c4cf232da3a4794baec513aae5e5131_83.png)

![](img/2c4cf232da3a4794baec513aae5e5131_84.png)

Performance monitoring， reports and server and database logs help identify performance bottlenecks and determine the best way to correct them performanceform monitoring helps identify potential network server and database issues before they occur and helps determine where improvements can be made Dashboards can monitor databases in real time and provide an early warning system for problems before they affect users in addition to tracking historical performance and other metrics。

 and server and database logs help identify a problem and when it occurred。



![](img/2c4cf232da3a4794baec513aae5e5131_86.png)

![](img/2c4cf232da3a4794baec513aae5e5131_87.png)

![](img/2c4cf232da3a4794baec513aae5e5131_88.png)

![](img/2c4cf232da3a4794baec513aae5e5131_89.png)

![](img/2c4cf232da3a4794baec513aae5e5131_90.png)

![](img/2c4cf232da3a4794baec513aae5e5131_91.png)

In this video you learned that the most common problems encountered with databases are caused by poor performance in proper configuration or poor connectivity poor performance is typically caused by high latency for diskreads and writes。

 slow processing time by the server or a poor connection between the client and server。

 server configurationgu issues such as inadequate hardware resources or misconfigured settings can significantly impact performance some of the most common connectivity problems are not being able to connect to the database server。

 the database server or instance not running properly and client login credentials being incorrect。

 and finally， performance monitoring reports and server and database logs can help identify performance bottlenecks and determine the best way to correct them。



![](img/2c4cf232da3a4794baec513aae5e5131_93.png)

![](img/2c4cf232da3a4794baec513aae5e5131_94.png)

![](img/2c4cf232da3a4794baec513aae5e5131_95.png)