# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜big-data-with-spark-hadoop｜ - P9：8_hadoop 简介.zh_en - GPT中英字幕课程资源 - BV12h4y1D7hF

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_0.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_1.png)

Welcome to Introduction to Hadoop。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_3.png)

After watching this video， you'll be able to define Hadoop。

 Ex the history of Hadoop list reasons why Hadoop was the answer to big data processing。

 outline some of the challenges of Hadoop。😊。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_5.png)

Haadoop is an open source framework used to process enormous data sets。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_7.png)

Imagine this scenario。 You have 1 gigab of data that you need to process。

 perhaps customer sales records or survey responses。

 The data is stored in a relational database on your desktop， computer or laptop。

 Neither device has a problem handling this data set， and you can query the data with ease。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_9.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_10.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_11.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_12.png)

You have a great year， and you pick up a few more clients。 Your company starts growing very quickly。

 and that data grows to 10 gigabtes。😊。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_14.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_15.png)

Then，100 GB。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_17.png)

You pick up a big client， a retailer， perhaps with multiple databases。

 maybe you're a mine manager and a new executive decision means that you must now start processing data from equipment。

 front end loaders， excavators and haul trucks。 you also have data about the environment。

 data about soil and weather and data about safety and rock samples。

 or perhaps your company is a delivery service， and you attach sensors to your entire fleet。 Over。

 your clients drivers in their vehicles all start gathering data that you need to process when your data grows from 1 terabyte to 10 terabs and then 100 terabte。

 you are again quickly approaching the limits of your local computers。😊。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_19.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_20.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_21.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_22.png)

And maybe you need to process unstructured data coming from sources like Facebook， Twitter。

 Senensors and so on。 The senior leadership team at your company wants to derive insights from both the relational data and the unstructured data in order to make informed decisions。

 And they want this information as soon as possible。 How can you accomplish this task。

 Hadoop might be the answer。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_24.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_25.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_26.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_27.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_28.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_29.png)

Now， let's rewind before we use Hadoop to solve the problems。 let's understand what Hadoop is。

 Hadoop is a set of open source programs and procedures。

 which can be used as the framework for big data operations。

 It's used for processing massive data in distributed file systems that are linked together。

 It allows for running applications on clusters。 A cluster is a collection of computers working together at the same time to perform tasks。

 It should be noted that Hadoop is not a database， but an ecosystem that can handle processes and jobs in parallel or concurrently。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_31.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_32.png)

Haoop is optimized to handle massive quantities of data， which could be structured tabular data。

 unstructured data， such as images and videos， or semistructured data using relatively inexpensive computers。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_34.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_35.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_36.png)

In the 1990s， coming into the new millennium， the web grew significantly to millions of pages and different structures of data。

 Automation was needed to help handle simultaneously the differences in data structure and the Web searches in 1999。

 the Apache Software Foundation was established as a nonprofit。 In 2002。

 the Nuchwe search engine was created by Doug cutting and Mike Carafella Nut was created on the basis that it could handle multiple tasks across different computers at the same time while storing and processing the data in a distributed way so that the most relevant search would be returned faster In 2006。

 cutting joined Yahoo with the Nut project and the project was divided into the Web crawlwler and distributed processing。

 The distributed processing segment was called Hadoop and in 2008。

 Yahoo released Hadoop to the Apache Software Foundation。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_38.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_39.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_40.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_41.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_42.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_43.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_44.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_45.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_46.png)

Data is now in petabytes and exabytes， and big data is the term used to explain the complexity of the data。

 Hadoop has individual components for storing and processing data。

 The term Hadoop is often used to refer to both the core components of Hadoop。

 as well as the ecosystem of related projects。 The core components of Hadoop include Hadoop Common。

 which is an essential part of the Apache Hadoop framework that refers to the collection of common utilities and libraries that support other Hadoop modules。

 There is a storage component called Hadoop distributed file system， or HFS。

 It handles large data sets running on commodity hardware。 a commodity hardware is lowspecations。

 In grade hardware and scales a single Hadoop cluster to hundreds or even thousands。

 The next component is mapreduce， which is a processing unit of Hadoop and an important core component to the Hadoop framework。

 mapreduce processes data by split。😊。

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_48.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_49.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_50.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_51.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_52.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_53.png)

Large amounts of data into smaller units and processes them simultaneously For a while。

 Mapproduce was the only way to access the data stored in the HDFS。

 There are now other systems like hive and P and the last component is yarn。

 which is short for yet another resource negotiator。

 yarn is a very important component because it prepares the RAM and CPU for Hadoop to run data in batch processing stream processing。

 interactive processing and graph processing， which are stored in HDFS。

The drawbacks of Hadoop could not be left unnoticed by developers。

 Hadoop contained many smaller components。 although efficient at first glance。

 Hadoop failed its simple tasks。 Hadoop is not good for processing transactions due to its lack of random access。

 Hadoop is not good when the work cannot be done in parallel or when there are dependencies within the data。

 dependencies arise when record1 must be processed before record 2。

 Hadoop is also not good for low latency data access。 Low latency allow small delays。

 unnoticeable to humans between an input being processed and the corresponding output providing real time characteristics。

 This can be especially important for Internet connections utilizing services such as trading。

 On gaming， and voiceover I P。 Hadoop is also not good for processing lots of small files。

 Although there is work being done in this areas such as IBms adaptive map produce。 Lastly， Had。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_55.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_56.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_57.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_58.png)

Is not good for intensive calculations with little data to deal with the shortcomings of Hadoop。

 new tools like hive were built on top of Hadoop。 Hive provided SQL like query and provided users with strong statistical functions。

 PG was popular for its multi queryry approach to cut down the number of times that the data is scanned。

In this video， you learned that Hadoop is an open source framework for big data。

 The core components of Hadoop are H FS， mapp Reduce， yarn and Hadoop Common。

 The drawbacks of Hadoop outweighed the benefits。😊。



![](img/fd570886102a5ed2d8bbaa5ca9a6292c_60.png)

![](img/fd570886102a5ed2d8bbaa5ca9a6292c_61.png)