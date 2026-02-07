# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P17：16_监控使用和性能第 2 部分.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/e8498730e396f7eb6d9f6c1f24406d40_0.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_1.png)

Welcome to Monitoring U and Perance Part 2。

![](img/e8498730e396f7eb6d9f6c1f24406d40_3.png)

After watching this video， you will be able to describe key database usage and performance metrics。

 describe the in product tools available for reviewing metrics。

 and describe several third party monitoring tools。



![](img/e8498730e396f7eb6d9f6c1f24406d40_5.png)

Some of the key metrics for monitoring the usage and performance of your database include the following database throughput is one of the most significant metrics of database performance。

 It indicates how much total work is being taken on by your database and is typically measured by the number of queries executed per second。

 database resource usage monitors the database resource usage by measuring the CPU memory。

 log space and storage usage。 This summary metric represents the database resource usage by two aspects。

 Average max latest number and time series number。 database availability signals whether the database is up or down that is available or unavail It is typically a summary metric that represents the historical data on available time as a percentage databasease responsiveness shows how well the system is responding to inbound requests and is another of the more commonly used database performance metrics。



![](img/e8498730e396f7eb6d9f6c1f24406d40_7.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_8.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_9.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_10.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_11.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_12.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_13.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_14.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_15.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_16.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_17.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_18.png)

It provides DBAs with information on the average response time per query for their database servers。

 indicating how quickly they respond with query results databasease contention indicates whether there is any contention between connections by measuring lock weights and concurrent database connections database contention is the term used to describe what happens when multiple processes are competing to access the same database resource at the same time and units of work tracks what transactions or units of work are consuming the most resources on the database server。



![](img/e8498730e396f7eb6d9f6c1f24406d40_20.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_21.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_22.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_23.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_24.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_25.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_26.png)

Here are some more key metrics Connections can display all kinds of network connection information to a database management console and can indicate whether a database server might fail due to longrunning queries or having too many open connections database connections are network connections that enable communication between clients and database software。

 Open connections are used for sending commands and receiving responses in the form of results sets。

 Most frequent queries， tracks the most frequent queries received by your database servers。

 including their frequency and average latency。 That is how long they take to be processed。

 It can help DbaAs optimize these queries to gain substantial performance improvements。



![](img/e8498730e396f7eb6d9f6c1f24406d40_28.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_29.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_30.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_31.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_32.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_33.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_34.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_35.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_36.png)

Locked objects shows detailed information about any locked processes and the process that blocked them Locks and blocks stop several concurrent transactions for maxene an object at the same time they put contending processes on hold until that object has been released and is accessible again。

 stored procedures displays the aggregated execution metrics for procedures， external procedures。

 compiled functions， external functions， compiled triggers and anonymous blocks invoked since database activation。



![](img/e8498730e396f7eb6d9f6c1f24406d40_38.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_39.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_40.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_41.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_42.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_43.png)

Buffffer poolols tracks the usage of buffer pools and table spaces a directory server uses buffer pools to store cached data and to improve database performance when the buffer pool fills up。

 it removes older and less used data to make room for newer data and top consumers shows the top consumers of a systemss resources and can help DBAs with capacity planning and resource placement。



![](img/e8498730e396f7eb6d9f6c1f24406d40_45.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_46.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_47.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_48.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_49.png)

Please note， this is just a small selection of the numerous metrics available in most database management systems。



![](img/e8498730e396f7eb6d9f6c1f24406d40_51.png)

To review these key database performance metrics， you will use different outof the box tools depending on your database For example。

 in DB2 you can use tools such as the DB2 Data Management console。

 the workload manager and snapshot monitors in PostgresQL you can use the PG admin dashboard which is a very popular open source Que Mon tool for PostgresQL systems in MySQL you can utilize the Per dashboard。

 performance reports and Que Staistics tools in the MySQL Workbench。

 and you can use the MySQL Queery Pror to identify Srunning queries。



![](img/e8498730e396f7eb6d9f6c1f24406d40_53.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_54.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_55.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_56.png)

There are several third party performance and query monitoring tools available to help you monitor queries。

 optimize performance and speed up your database， some of them may also provide performance tuning and query optimization capabilities as well。



![](img/e8498730e396f7eb6d9f6c1f24406d40_58.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_59.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_60.png)

For PostgresQL systems， there is the PG Ana tool which provides automatic insights into query plans。

 query analysis， database visualization， and dashboards。

 log insights and performance optimization and monitoring。



![](img/e8498730e396f7eb6d9f6c1f24406d40_62.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_63.png)

And if you have a PostgresQL， MySQL， SQL server， or Oracle database。

 and need a query monitoring tool， you could try PRTG Network Monitor。



![](img/e8498730e396f7eb6d9f6c1f24406d40_65.png)

![](img/e8498730e396f7eb6d9f6c1f24406d40_66.png)

Many of the third party tools are available for multiple database systems such as SQL Server， Oracle。

 Sibase， DB2， MySQL and PostgresQL to name but a few。

SolarWds offers a subscription based monitoring solution called database Perance Anar。

Fglight for databases from Quest enables you to proactively monitor your complete database environment and view the state of all database platforms in a single comprehensive interface。

 and Datadog is a SaS platform that includes multiple system monitoring tools it has more than 450 builtin integrations to connect to multiple different database systems。

In this video， you learned that there are many different metrics you can use to monitor the usage and performance of your databases。

 and there are several different tools available to monitor your databases and queries。

 some of which are included with your database product， while others are thirdpart offerings。

