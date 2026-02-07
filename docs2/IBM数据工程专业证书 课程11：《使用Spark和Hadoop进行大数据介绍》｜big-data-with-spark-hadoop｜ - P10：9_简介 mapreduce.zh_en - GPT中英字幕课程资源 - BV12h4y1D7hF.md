# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜big-data-with-spark-hadoop｜ - P10：9_简介 mapreduce.zh_en - GPT中英字幕课程资源 - BV12h4y1D7hF

![](img/44e248622766c5d8474ae96e24dc5056_0.png)

![](img/44e248622766c5d8474ae96e24dc5056_1.png)

Welcome to Introduction to Ma Reduce。

![](img/44e248622766c5d8474ae96e24dc5056_3.png)

After watching this video， you'll be able to explain the terms map and reduce in map reduce。

 Describe why we use map reduce。 list the components of map reduce。

 outline examples of common use cases of map reduce。😊。



![](img/44e248622766c5d8474ae96e24dc5056_5.png)

![](img/44e248622766c5d8474ae96e24dc5056_6.png)

What is mapRduce， MapRduce is a programming model that enables massive scalability across hundreds or thousands of servers in a Hadoop cluster as the processing component。

 mapreduce is the heart of Apache Hadoop。 Mareduce is a processing technique and a program model for distributed computing。

 It is based on Java。 distributed computing is a system or machine with multiple components located on different machines。

 Each component has its own job， but the components communicate with each other to run on one system to the end user。

 The map Redduce algorithm consists of two important tasks。 map and Reduce。

 Many mapreduce programs are written in Java。 Map Redduce can also be coded in C plus plus Python Ruby R and so on。

😊。

![](img/44e248622766c5d8474ae96e24dc5056_8.png)

![](img/44e248622766c5d8474ae96e24dc5056_9.png)

![](img/44e248622766c5d8474ae96e24dc5056_10.png)

![](img/44e248622766c5d8474ae96e24dc5056_11.png)

As the name suggests， the mapRuce framework contains two tasks。

 map and reduce map takes in an input file and performs some mapping tasks by processing and extracting important data information into key value pairs。

 and these are the preliminary output list。 Some more reorganization goes on before the preliminary output is sent to the reducer。

 The reducer works with multiple map functions and aggregates the pairs using their keys to produce a final output。

 MapRuce keeps track of its tasks by creating unique keys to ensure that all the processes are solving the same problem。

😊。

![](img/44e248622766c5d8474ae96e24dc5056_13.png)

![](img/44e248622766c5d8474ae96e24dc5056_14.png)

![](img/44e248622766c5d8474ae96e24dc5056_15.png)

![](img/44e248622766c5d8474ae96e24dc5056_16.png)

![](img/44e248622766c5d8474ae96e24dc5056_17.png)

Let's look at the framework visually。 First， we have the map step。

 which takes a set of data and converts it into another set of data where individual elements are broken down into key value pairs。

 The key is the name and the value is the content。 The input data is a file that is saved in the Hadoop file system called HDFS。

 Now， let's assume we have an input file that contains names of people。

 and we would like to do a word count on the unique name occurrences。 First。

 the data is split into the following four files。 Each of them in key value pairs and are worked on separately。

 For example， for the first split line for Teju and Brianna。

 We have two key value pairs with one occurrence in each file。

 and it will do the same for all key value pairs。 We then have the reducer。

 The reducer processes the data that comes from the map After processing。

 it produces a new set of outputs which will be stored in the HDFS。😊。



![](img/44e248622766c5d8474ae96e24dc5056_19.png)

![](img/44e248622766c5d8474ae96e24dc5056_20.png)

![](img/44e248622766c5d8474ae96e24dc5056_21.png)

![](img/44e248622766c5d8474ae96e24dc5056_22.png)

![](img/44e248622766c5d8474ae96e24dc5056_23.png)

![](img/44e248622766c5d8474ae96e24dc5056_24.png)

![](img/44e248622766c5d8474ae96e24dc5056_25.png)

![](img/44e248622766c5d8474ae96e24dc5056_26.png)

![](img/44e248622766c5d8474ae96e24dc5056_27.png)

![](img/44e248622766c5d8474ae96e24dc5056_28.png)

![](img/44e248622766c5d8474ae96e24dc5056_29.png)

![](img/44e248622766c5d8474ae96e24dc5056_30.png)

The reducer starts with shuffling。 shuffling sorts the key and a list of values in a list。

 For example， you will see the key Taju and a corresponding list of values from the previous step。

 We will have Taju 11，1。 This is because the name Tajuu occurred three times in the map step。

 It does the same for the rest of the names counting how many times they appeared in the map step。

 The reducer layer then aggregates the values in the list and saves them。

 Then the final output is saved in an output file。😊。



![](img/44e248622766c5d8474ae96e24dc5056_32.png)

![](img/44e248622766c5d8474ae96e24dc5056_33.png)

![](img/44e248622766c5d8474ae96e24dc5056_34.png)

![](img/44e248622766c5d8474ae96e24dc5056_35.png)

![](img/44e248622766c5d8474ae96e24dc5056_36.png)

The advantage of Maproduce is its ability to allow for a high level of parallel jobs across multiple nodes。

 A node is an independent computer used for processing and storing big volumes of data in Hadoop we have two types of nodes。

 the name node and the data node。 Mareduce allows for splitting and running independent tasks in parallel by dividing each task which in turn saves time。

 Mareduce is very flexible and can produce data that come in tabular and nontular forms。 Therefore。

 Mareduce provides business value to organizations regardless of how their data is structured。

 It also offers support for different languages and provides a platform for analysis。

 data warehousing and more。

![](img/44e248622766c5d8474ae96e24dc5056_38.png)

![](img/44e248622766c5d8474ae96e24dc5056_39.png)

![](img/44e248622766c5d8474ae96e24dc5056_40.png)

![](img/44e248622766c5d8474ae96e24dc5056_41.png)

![](img/44e248622766c5d8474ae96e24dc5056_42.png)

![](img/44e248622766c5d8474ae96e24dc5056_43.png)

![](img/44e248622766c5d8474ae96e24dc5056_44.png)

![](img/44e248622766c5d8474ae96e24dc5056_45.png)

![](img/44e248622766c5d8474ae96e24dc5056_46.png)

MaapRduce has a couple of use cases And here we have some of them displayed。

 Mapproduce can be used for social media platforms like LinkedIn and Instagram to analyze who visited。

 viewed and interacted with your profile posts。 Maproduce is used by Netflix to recommend movies based on what you have watched in the past by using the users's interest。

 It is also used in financial institutions like banks and credit card companies to flag and detect anomalies in user transactions。

 It can also be used in the advertisement industry to understand a user's behavior by how they engage with ads。

 Google Ad work by using Mapproduce to understand the engagement of users with an ad。😊。



![](img/44e248622766c5d8474ae96e24dc5056_48.png)

![](img/44e248622766c5d8474ae96e24dc5056_49.png)

![](img/44e248622766c5d8474ae96e24dc5056_50.png)

![](img/44e248622766c5d8474ae96e24dc5056_51.png)

![](img/44e248622766c5d8474ae96e24dc5056_52.png)

In this video， you have learned that map produces a framework used in parallel computing。

 It contains two major tasks， map and reduce map processes data into key value pairs。

 sorts and organizes the data。 The reducer aggregates and computes a set of results and produces a final output。

 It is flexible for all data types like structured and unstructured data and can be applied to multiple industries such as social media。

 entertainment and many more。😊。

![](img/44e248622766c5d8474ae96e24dc5056_54.png)

![](img/44e248622766c5d8474ae96e24dc5056_55.png)