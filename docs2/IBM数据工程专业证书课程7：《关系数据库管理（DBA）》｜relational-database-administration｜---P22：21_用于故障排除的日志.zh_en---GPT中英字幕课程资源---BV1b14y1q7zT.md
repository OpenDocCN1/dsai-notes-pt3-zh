# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P22：21_用于故障排除的日志.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_0.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_1.png)

Welcome to Using logs for troubleshooting。

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_3.png)

After watching this video， you will be able to describe diagnostic logs and their purpose list various types of diagnostic logs。

 identify types of information included in database diagnostic logs。

 and explain where diagnostic logs are stored and how to access them。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_5.png)

Troublesshooting is a systematic process used to locate the cause of a fault in a computer system to provide details on correcting the relevant hardware and software issues。

 approaching troubleshooting， using a logical and systematic approach is essential to a successful resolution。

 troubleublesshooting is one of the main reasons people create logs When a problem occurs。

 you'll want to diagnose it to understand why it happened and what the cause was。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_7.png)

A diagnostic log tracks what is happening in a system component or an application such as a web server or a database。

 it contains information about an event or a problem encountered when processing requests。

The diagnostic log is a record of significant events and errors in chronological order and is very useful for diagnosing and troubleshooting problems。

 For example， if a web server receives a request to load a file that is missing。

 This error and its details can be logged to the Web server log。

 The diagnostic logs are also sometimes referred to as troubleshooting logs。

 error logs or event logs， It is essential to recognize that they may contain events。

 informational message， warnings or errors and their details。

 an event might be when a user connects to the database or an informational message that includes information on a particular subsystem status。

 Additional events may be a warning message that might indicate that disk space for the database volume is running low or an error message that contains details about a failed database backup operation。

 Some logs may have fewer or more categories of diagnostic。

Such as and panic as additional classes of errors or may label them differently， for example。

 note or notice instead of information。A database administrator needs to be familiar with various types of diagnostic logs in the system。

 these include logs for server components， storage and other hardware devices， network。

 operating system， applications， and databases。

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_9.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_10.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_11.png)

While the systems administrator may monitor the other logs。

 the DBA needs to be intimately familiar with the database diagnostic logs and review them frequently these database diagnostic logs are generally separate from the database transaction logs or query logs。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_13.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_14.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_15.png)

In most cases， you can configure the location of the log files， however。

 certain logs such as system log files may have a fixed location。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_17.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_18.png)

Many log files are recorded in plain text， and any text editor will do just fine to open them。

 For example， on a machine with a Windows operating system。

 double clicking on the log file will open notepad by default。 However。

 some log files are machine readable and may require particular viewers to view their contents。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_20.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_21.png)

Diagnostic logs can contain a variety of information。

 Some typical components of messages in a diagnostic log include the type and severity of issue。

 whether it is an event， informational warning or an error， the corresponding error code and message。

 the location， URL or subsystem where the error occurred， a timestamp， the user's IP and user agent。

 and finally any additional information depending on the event or error。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_23.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_24.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_25.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_26.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_27.png)

Here is an example of a message in the DB2 diagnostic log file called DB2Dag。 log。

 which is in ASI or plain text format in which you can view using a text editor it includes a timestamp of when the message was logged the type of message in this case it is an event related to starting the database manager initiated by running the Db2star。

ex it also includes additional details such as the DB2 software fixpack and operating system levels and information about system resources。

 CPUs and memory using the DB2 database manager configuration you can configure the location of the DB2 diagnostic log and the severity or diagnostic level of message to log。

Similarly， the Postgresql database typically logs all events like startup and shutdown， errors。

 connection issues and so on。 you can configure the location where the log entries are stored using the log destination parameter in the PostgresqL。

 co the ciss log in case of Linux and UniX systems。

 the event log in case of Windows systems to a CSv log file that you can easily import into a table and query the log entries using standard SQL statements or to st error short for standard error which is the default and typically outputs to the console that can be configured using log directory parameter to specify a particular location the default being PG log you can also select the format of the log file name that names the log files based on a specific string pattern that can include a timestamp。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_29.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_30.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_31.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_32.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_33.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_34.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_35.png)

In MySQL， distinct from the binary or the transaction logs that are used for recoverability。

 you can use other server logs for troubleshooting problems， these include the general query log。

 which logs connections and queries received from clients， the S query log。

 which has the name implies logs queries that take longer than a specified time to execute。

 and most importantly， the error log file that contains diagnostic and error messages from MySQLD。

 the MySQL demonmon or server process。

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_37.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_38.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_39.png)

In addition to the error messages， the MySQL error log also includes warnings and notes during database server operation。

 startup and shutdown you can configure MySQL to write messages to the Windows Even log。

 which is the default setting， the Ss log or system log on Linux and Uniix like System。

 the Stud error or standard error， which is the default on Linux and UniX or to a specified file。

 you specify the file name for logging messages using the log error option in MySQLD。

 or the MySQL configuration file。

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_41.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_42.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_43.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_44.png)

DbaAs can configure how much information is stored in the error log。

 choosing between level 1 errors only， levell 2 errors and warnings and level 3 errors warnings and notes。

 Lel 3 is the default。 The verbosity of messages is specified using the log error verbosity option In this example。

 the log error verbosity setting is two errors and warnings only。



![](img/cc30f1a0cf8bac9279d63f911b74c0f6_46.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_47.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_48.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_49.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_50.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_51.png)

In this video you learned that a database administrator needs to be familiar with many types of logs。

 especially the database diagnostic logs， a database diagnostic log file also known as an error log or troubleshooting log contains timeted messages for various types of informational events。

 warnings and error details most diagnostic logs are textbased and can be viewed on the console or in a text editor。

 but some may require special tools or viewers to view and filter their contents most databases provide settings for enabling and configuring diagnostic and error logging such as setting log file names and locations and verbosity of messages and some databases like mySQL offer more than one diagnostic log。

 for example， the error log and S query log。

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_53.png)

![](img/cc30f1a0cf8bac9279d63f911b74c0f6_54.png)