# 延世大学《新兴技术从智能手机到物联网再到大数据Emerging Technologies From Smartphone to IoT to Big Data》 - P9：8_2.5 Hadoop.zh_en - GPT中英字幕课程资源 - BV18hpFewEcG

![](img/6d093a3beae936c49b4e9803006f17c2_0.png)

어。🎼Yeah。In this lecture， we will look into Haddu。Haadoop is an open source version of Google's Mareduce。

MaapRduce is the technology that was used in the Google search window。

 and since we've all used it before， we know how powerful it is。Currently。

 it is an open source version software that is in the Yahoo'os Apache group。

Hauc is the name of a yellow elephant toy。 That's why we have that logo down there。

Which is owned by the son of the creator of the Hadoop group， which was dog cutting。

Who decided to use this name because it was meaningless。 It was easy to spell and pronounce。

 In addition， it was not used elsewhere。These are some other Hadop related systems that eventually you'll hear about。

 so let's get some relations to them。HBase is a Java based open source， non relational。

 distributed database developed as a part of the Apache Haddu project。

Hbase was modeled based on Google's big table and runs on HDFS。

 which is the Hadop Dis file system to enable fault tolerance storing of large quantities of sparse data。

Apache F provides services to efficiently collect， aggregate and move large amounts of log data in a reliable。

 distributed way。Flume uses a simple and flexible data flow streaming mechanism that is fault tolerant by using Cnable reliability mechanisms and recovery schemes。

The word flume means a human made channel of water。

 which refers to flexible data flow streaming features of flume。

They make human made channels of water in order to move logs when there is no natural flow of water。

And that's where the name flume came about。In addition， there is Apache Mahaute。

 which provides free implementations of distributed and scalable machine learning algorithms that can provide collaborative filtering。

 clustering and classification data and also provides Java libraries for common math operations。

So Hadub has support of Apache Mahat， which basically can support machine learning。

 artificial intelligent technology。The word mahat means elephant rider。

 and that's where that logo comes from。 A rider is on a yellow elephant。

And this means a trainer or keeper， and this is related， of course， to the Hadjune。Then there's high。

 this was developed by Facebook to enable its programmers。

Among the programmers who are not really Java programming experts to easily write cur codes in SQL to emulate on demandman SQL operations on Hadoop。

 Very soon， I will talk about Hadop and also SQL in further details。 So just wait a little。

How you storage， access analysis of datas。This is the main focus。

Hard drive storage capacity has tremendously increased。

But the data read and write speeds to and from the hard drives have not significantly improved yet。

Simultaneous parallel reads and writes of data with multiple hard disk require advanced technology。

 and that is where Hadoop comes in to be extremely effective。Challenge one， hardware failure。

 When using many computers for data storage and analysis。

 the probability that one computer will fail is very high。

I'm going to say that when I say many computers， I'm looking at hundreds， thousands of computers。

 maybe tens of thousands of computers in a parallel distributed fashion where the way I control them and manage them are in big clusters。

 So when I say many computers， I really mean many。Next is cost。

To avoid data loss or computed analysis information loss， using back computers and memories needed。

 which helps the reliability， but is very， very expensive。Then we have challenge three。

 which is combining analyze data。 combiningbining the analyze data is very， very difficult。

 In one part of the analyze data。 If it's not ready。

 then the overall combining process will need to wait until that part is actually done。

 That will create a delay。In addition， if one part has errors。

 what are you going to do then if you combine them， what will happen to the final combined result。

 How faulty will it be， These are all serious issues。Hayop is a reliable。

 shared storage and analysis system。It is a combination of HDFS。

 which is the Hadop distributed file system。And mapR。

 which is a combination of a map function and a reduced function。When I say HDFS。

 Hadjuop Dis file system， evidently the DFS， the distributed file system is on there。

 it is a designed system used for storage management based on a network of computers。

It is optimized to store huge files with streaming data access patterns。

It is designed to run on a cluster of general computers， commodity server systems。

HDFS was designed to be optimal in its performance based on a warm pattern。

 This is a write once and read many times pattern， which is an efficient data processing pattern。

 So you'll see that we will put it in there as the data comes in。 Just store it as it is。

And then every time we have a query， we want to extract some type of information or statistics out of this data。

 We will read it and read it and read it again。 This is what I mean by warm， read write once。

 and read many times。HDFS was designed， considering the time to read the whole data to be more important than the required time to read the first record。

Filees in HDFS are divided into block size chunks。A 64 MBgabyte default block size is the size that is used。

 It is the minimum size of data that can be used to read or write。

And it simplifies the storage and replication process。

It provides fault tolerance and also speed enhancement for larger files。

The default replication factor in Hadoop is 3， and I will talk more about this， including an example。

 very soon。HDFS clusters use two types of nodes， one is the master node。

 which is called the name node， the other one is the worker node that actually does the work。

 which is called the data node。The name node is in charge of the file system namespace。😡。

It maintains the file system tree and the metadata for all the files and directories in the tree。

It stores the local disk using two file formats， one is the namespace image and the edit log。

 these two need to be protected and recorded well。Data nodes。 This is the workhor of the file system。

 It is used to store and retrieve blocks。Which are the default size of 64 mebytes when requested by the client or the name node。

Then it needs to report back to the name node periodically with lists of blocks that were stored。😡。

Data nodes send heartbeat signals to the name node every three seconds to ensure connection and to report operation status。

MapReduce is a program that abstracts the analyst problem。From store data。

MaapRduce transforms the analysis problem into a computational process that uses a set of keys and values。

Keys and values。Maapreduce was designed for tests that consumed several minutes or hours。Also。

 it processes data on a set of dedicated， trusted computers。Connected with a high speed network。

In addition， it is managed by a single master data center。

MaapRduce uses a somewhat brute force data analysis approach。😡。

The entire data set or a big part of the data is processed every query。

This is what we mean by brute Forcece。It is a batch query processor model。 It saves it in a batch。

 and then this is overall analyzed every time a query is requested。

MaabRduce enables the ability to run an ad hoc query against the whole data set within a scalable time。

So that is why it is so powerful。 You will not just use sample data。

 You will search across the overall data。Many distributed systems combine data from multiple sources。

 which is very difficult， but Mareduce does this in a very effective and efficient way。

Technical terms used in mappRduce。We'll first look into seek time。

 See time is the delay in finding a file。Transfer rate is the speed to move a file。

Transfer rate has improved significantly more， and this means that the networking equipment and the networks that support this have much more bandwidth。

 much higher throughput， and are much faster and much more reliable。On the other hand。

 we have seen very little improvement in the seek time。So still。

 the seek time within a database is still relatively slow。

 looking at what we have and as an advantage in transfer rate and as still a disadvantage in seek time。

😊，Haadoop system was maximized in its performance， considering these two factors。

Mareduce gains performance enhancements through optimal balancing of seeking and transfer operations。

Reducuce Si operations， effectively use transfer operations more。To gain a higher performance。

In the next lecture， we will compare MaRuce with traditional RDBMS relational database management systems。

These are the references that I use， and I recommend them to you。 Thank you。😊。



![](img/6d093a3beae936c49b4e9803006f17c2_2.png)