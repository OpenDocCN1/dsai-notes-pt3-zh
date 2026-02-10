# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜big-data-with-spark-hadoop｜ - P4：3_并行处理 扩展和数据并行.zh_en - GPT中英字幕课程资源 - BV12h4y1D7hF

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_0.png)

Welcome to Para Pro and Scalability for Big Data。

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_2.png)

After watching this video， you'll be able to explain why big data requires parallel processing。

 identifydent the differences between linear and parallel processing。

 I why parallel processing is apt for big data。 Explain parallel processing and scalability。

 Describe the motivation for horizontal scaling。 De embarrassingly parallel。

 Explain fault tolerance in parallel computing。😊。

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_4.png)

You can do lots of things with data at various sizes， right， in any normal analyticsna cycle。

 the functionality of the computer is to store data and move that data from its storage capacity into a compute capacity which includes memory and back to storage once important results are computed with big data。

 you have more data than will fit on a single computer。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_6.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_7.png)

Parallism or parallel processing can best be understood by comparing it to linear processing。

 Linear processing。 Linear processing is the traditional method of computing a problem where the problem statement is broken into a set of instructions that are executed sequentially till all instructions are completed successfully。

 If an error occurs in any one of the instructions。

 the entire sequence of instructions is executed from the beginning after the error has been resolved。

 It's evident from the processing method that linear processing is best suited for minor computing tasks and is inefficient and timecon when it comes to processing complex problems such as big data。

 Para processing。 The alternative to linear processing is parallel processing here， too。

 the problem statement is broken down into a set of executable instructions。

 The instructions are then distributed to multiple execution nodes of equal processing power and are executed in parallel。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_9.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_10.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_11.png)

Since the instructions are run on separate execution nodes， errors can be fixed and executed locally。

 independent of other instructions。As noted on the previous slide。

 parallel processing offers significant advantages when dealing with complex problems such as big data。

 Some of the other benefits of using parallel processing are reduced processing times。

 parallel processing can process big data at a fraction of the time compared to linear processing。

 Le memory and processing requirements， Since the problem instructions are executed on separate execution notess。

 memory and processing requirements are low， even while processing large volumes of data。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_13.png)

Flexibility， the biggest advantage of parallel processing is that execution notes can be added and removed as and when required。

 This significantly reduces infrastructure cost。Data scaling is a technique to manage。

 store and process the overflow of data。 You can get a larger single node computer。

 but when your data is growing exponentially， eventually。

 it will outgrow the capacity that is available。 Iing the capacity of a single node as a means of increasing capacity is called scaling up。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_15.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_16.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_17.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_18.png)

A better strategy， or at least the one most people ultimately choose。

 is to scale out or to scale horizontally。 This simply means adding additional nodes with the same capacity until the problem is tractable。

 The individual nodes arranged in this way are called a computing cluster。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_20.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_21.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_22.png)

Compute clusters can solve problems that are known as embarrassingly parallel calculations。

 These are the kind of workloads that can easily be divided and run independent of one another。

 If any one process fails， it has no impact on the others and can easily be rerun。

 An example would be to say， change the date format in a single column of a large data set that has been split into multiple smaller chunks that are stored in different nodes of the cluster。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_24.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_25.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_26.png)

Sometimes sorting a large data set adds significant complexity to the process。

 Now the multiple computations must coordinate with one another because each process needs to be aware of the state of its peer processes in order to complete the calculation。

 This requires sending messages across a network to each other or writing them to a file system that is accessible to all processes on the cluster。

 The level of complexity increases significantly because you are basically asking a cluster of computers to behave as a single computer。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_28.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_29.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_30.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_31.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_32.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_33.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_34.png)

Most calculations in enterprise environments are considered embarrassingly parallel with some not so easy calculations。

 While this statement is true to varying degrees， it has guided the design of underlying frameworks。

 in the Hadoop ecosystem， the concept of bringing compute to the data is a central idea in the design of the cluster。

 The cluster is designed in a way that computations on certain pieces or partitions of the data will take place right at the location of the data when possible。

 The resulting output will also be written to the same node。😊。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_36.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_37.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_38.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_39.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_40.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_41.png)

Computers break outages happen， and you need to be prepared。 In such cases。

 faultult tolerance comes into play。 Fult tolerance refers to the ability of a system to continue operating without interruption when1 or more of its components fail。

 This works for Hadoop primary data storage system HDFS and other similar storage systems like S3 and object storage a system like the one we showcase here。

 Consider the first three partitions of a data set labeled P12 and P3 which reside on the first node。

 In this system， copies of each of these data partitions are also stored on other locations or nodes within the cluster。

 If the first node ever goes down， you can add a new node to the cluster and recover the loss partitions by copying data from one of the other nodes where copies of P1 P2 and P3 partitions are stored。

 Clearly， this is an extraordinary complex maintenance process。 but the Hadoop file system as a。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_43.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_44.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_45.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_46.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_47.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_48.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_49.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_50.png)

![](img/fcd7b747e445fd3c3bec22ce62bc7fad_51.png)

Robust and time tested framework it can be reliable to5 nine99。999%。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_53.png)

In this video， you learned that big data requires parallel processing on account of massive volumes of data that are too large to fit on any one computer。

 Linear processing is sequential while parallel processing works on multiple instructions at the same time。

 Para processing has significant advantages over linear processing。

 and it is best suited for processing big data。 Paraism in big data is parallelization across multiple processors in parallel computing environments。

 It focuses on distributing the data across different nodes operating on the data in parallel。

 Horal scaling or scaling out is a strategy to increase the capacity of a single node as a means of increasing capacity。

 Embarrassingly， parallel calculations are the kinds of workloads that can easily be divided and run independently of one another。

 If any one process fails。 it has no impact on the others and can simply be rerun fault。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_55.png)

Tolerance is the property that enables a system to continue operating properly in the event of the failure of some of its components。



![](img/fcd7b747e445fd3c3bec22ce62bc7fad_57.png)