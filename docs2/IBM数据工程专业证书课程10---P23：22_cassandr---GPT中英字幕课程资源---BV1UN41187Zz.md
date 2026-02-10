# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P23：22_cassandra 查询语言 shell cqlsh 简介.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/60714bb083a5b64b8c85c987575bc159_0.png)

![](img/60714bb083a5b64b8c85c987575bc159_1.png)

Welcome to the introduction to the Cassandra Que languageguage She After watching this video。

 you will be able to describe the Cassandra query language。

 explain the different options for running CQL queries， describe the CQL shell。

 use some of the key command line options for the CQL shell。

 and describe the special commands available for the CQL shell。



![](img/60714bb083a5b64b8c85c987575bc159_3.png)

![](img/60714bb083a5b64b8c85c987575bc159_4.png)

Cassandra query language referred to as CQL is the primary language for communicating with Apache Cassandra clusters。

 CQL has a simple and intuitive SQL like syntax that allows the creation of key spaces， tables。

 inserts， updates， deletes and select queries。 While CQL syntax has similarities to SQL。

 there are many differences as well between what you can do in CQL versus SQL。

 One of the most notable differences is that CQL does not support join statements In Cassandra。

 if you need a join than you store the data already joined。 Also， although syntax wise。

 some operations seem similar to SQL， their behavior in Cassandra is different。 For example， inserts。

 updates and deletes are done in memory directly without prior reads to locate。



![](img/60714bb083a5b64b8c85c987575bc159_6.png)

Data。You will see as you go through the lab exercises that CQL keywords are case insensitive Idententifiers are also case insensitive unless they are enclosed in double quotation marks。

 For example， select in sentence case and select in uppercase are treated the same。

 If you enter names for identifiers， for example， a table name using uppercase letters。

 Cassandra will just store the names in lowercase anyway， As you can see in the examples。

 commented text denoted by a double forward slash will be ignored by CQL to run CQL queries you can do one of the following Run them programmatically using a licensed Cassandra client driver There are many options available including Java。

 Python and Scala。 The default driver is the open source Datastax Java driverAlternatively。

 you can run。

![](img/60714bb083a5b64b8c85c987575bc159_8.png)

![](img/60714bb083a5b64b8c85c987575bc159_9.png)

![](img/60714bb083a5b64b8c85c987575bc159_10.png)

![](img/60714bb083a5b64b8c85c987575bc159_11.png)

![](img/60714bb083a5b64b8c85c987575bc159_12.png)

![](img/60714bb083a5b64b8c85c987575bc159_13.png)

them on the CQL Shell client referred to as CQL SH that is provided with the Cassandra package CQLshH is a Python based command line shell that uses CQL for communicating with a Cassandra cluster the software is shipped with every cassandra package CQLSH connects to a single node either the one that the command is run on by default or the one specified as an option in the command line There are also other CQL editors on the market that communicate with Cassandra using CQL using CQL shell。

 you can create Al and drop key spaces， create Al and drop tables insertert update and delete data and execute queries using select but before we look at some CQLshH examples when launching CQLshH there are a number of command line options。



![](img/60714bb083a5b64b8c85c987575bc159_15.png)

![](img/60714bb083a5b64b8c85c987575bc159_16.png)

![](img/60714bb083a5b64b8c85c987575bc159_17.png)

You should know about let's just mention a few of them here help shows help about the options of CQLSH commands version in order to check the CQLSH version being used user and password for authentication。

 keyspace， keyspace to authenticate to file enables execution of commands from a given file and request timeout you can set a timeout for your queries。

 the default being 10 seconds let's see the CQLshH output for a simple example here we're just using the Intro underscore Cassandra keyspace and we select only the users from Group ID12 Then we insert a new record into the group' table for group ID12 and finally select only the users from Group ID12 and also view the inserted data。



![](img/60714bb083a5b64b8c85c987575bc159_19.png)

![](img/60714bb083a5b64b8c85c987575bc159_20.png)

![](img/60714bb083a5b64b8c85c987575bc159_21.png)

![](img/60714bb083a5b64b8c85c987575bc159_22.png)

![](img/60714bb083a5b64b8c85c987575bc159_23.png)

![](img/60714bb083a5b64b8c85c987575bc159_24.png)

And this would be the resulting output。

![](img/60714bb083a5b64b8c85c987575bc159_26.png)

CQLSH also has some special commands， let's take a quick look at some of them。



![](img/60714bb083a5b64b8c85c987575bc159_28.png)

Capture captures the output of a command and adds it to a file。

 consistency shows the current consistency level and sets a new one Copy copies data to and from Cassandra describes the current cluster of Cassandra and its objects。

 Ex terminates the CQL session paging enables or disables the paging of query results and tracing enables or disables request tracing while in your handson sessions。

 you will get to experience some of these。 We will now look in a bit more detail at the consistency and copy commands。



![](img/60714bb083a5b64b8c85c987575bc159_30.png)

![](img/60714bb083a5b64b8c85c987575bc159_31.png)

![](img/60714bb083a5b64b8c85c987575bc159_32.png)

![](img/60714bb083a5b64b8c85c987575bc159_33.png)

![](img/60714bb083a5b64b8c85c987575bc159_34.png)

![](img/60714bb083a5b64b8c85c987575bc159_35.png)

![](img/60714bb083a5b64b8c85c987575bc159_36.png)

Let's take a detailed look at the consistency command。 Cassandra is tunable consistent。

 but what does that mean， Well， it means you have the ability to set Cassandra consistency at an operations level。

 consistency in Cassandra means the number of nodes out of the total replicas that need an answer to a request。

 write or read in order for the operation to be considered successful amongst the options available for the consistency command are1。

2 or three nodes， Qrum， which is a majority of nodes out of all replicas in the cluster。

 All replicas， and finally， local underscore quorum。

 which is a majority of nodes from the local data center。

 according to the specified data center set replication for the key space。 So for example。

 if we have a Cassandra cluster of eight nodes and two data centers， one data。



![](img/60714bb083a5b64b8c85c987575bc159_38.png)

![](img/60714bb083a5b64b8c85c987575bc159_39.png)

![](img/60714bb083a5b64b8c85c987575bc159_40.png)

![](img/60714bb083a5b64b8c85c987575bc159_41.png)

![](img/60714bb083a5b64b8c85c987575bc159_42.png)

![](img/60714bb083a5b64b8c85c987575bc159_43.png)

![](img/60714bb083a5b64b8c85c987575bc159_44.png)

![](img/60714bb083a5b64b8c85c987575bc159_45.png)

![](img/60714bb083a5b64b8c85c987575bc159_46.png)

With replication factor 2 and the other one with replication factor 3， then overall， replication is5。

If we set consistency quorum on a right operation， first of all。

 Qrum means a majority of nodes out of the replicas。

 so a majority here would be three right operations would go to all five replicas。

 but a minimum three nodes from both data centers out of the five replicas need to answer in order for the operations to be successful。

 another important command in CQLSH is the copy command。

 while bulk copy in Cassandra should be done through special procedures if you would like to just test your model or you're working with a smaller text delimited data set。

 then you can use copy from or copy two operations to bring data in and export data out of Cassandra。



![](img/60714bb083a5b64b8c85c987575bc159_48.png)

![](img/60714bb083a5b64b8c85c987575bc159_49.png)

![](img/60714bb083a5b64b8c85c987575bc159_50.png)

![](img/60714bb083a5b64b8c85c987575bc159_51.png)

Copy2 export data from a table into a Cv file。 Each row is written to align line in the target file with fields separated by the delimiter Copy from imports data from a Cv file into an existing table Each line in the source file is imported as a row。

 All rows in the data must contain the same number of fields and have values in the primary key fields。

 The process verifies the primary key and imports data accordingly。 In this video。

 you learned that CQL is the primary language for communicating with Apache Cassandra clusters。

 CQL keywords and identifiers are case insensitive。

 CQL queries can be run programmatically using a Cassandra client driver or they can be run on the Python based CQL shell client provided with Cassandra using the CQL。



![](img/60714bb083a5b64b8c85c987575bc159_53.png)

![](img/60714bb083a5b64b8c85c987575bc159_54.png)

![](img/60714bb083a5b64b8c85c987575bc159_55.png)

ShellYou can create alter and drop key spaces and tables， insert， update and delete data。

 and execute queries using select CQL Shell has several special commands。

 including the consistency and copy commands the consistency command can be used to tune the consistency of your data。

 and the copy command can be used to import data into and export data out of Cassandra。



![](img/60714bb083a5b64b8c85c987575bc159_57.png)