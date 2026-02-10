# 延世大学《新兴技术从智能手机到物联网再到大数据Emerging Technologies From Smartphone to IoT to Big Data》 - P21：20_3.10 Spark核心 3.11 Spark变量序列化.zh_en - GPT中英字幕课程资源 - BV18hpFewEcG

![](img/d466ea251365b05b837e53bff28513a4_0.png)

Yeah。The Spark core。The Spark coreps is an underlying general execution engine for the Spark platform。

All functions are built upon the sparkark corep。And it provides fast RAM based in memoryory computing。

Provdes referencing data sets so external storage systems can be used。

Spark Core is a foundation of the Spark system that supports。Cluster based parallel operations。

 test distribution and dispatching， scheduling and coordination， input and output functions。

RDD operations support。Control of shared variables。A broadcast variables and accumulators。

 and this is also used and supported by the core。In operations of RDD。

 a spark cluster consists of multiple nodes。Each node has an executor， a JVM， a Java virtual machine。

 running inside。Executors operate multiple cores， which can be used for various transformations and tasks。

In Spar， parallel processing is based on multiple threads， as I have explained before。

 and being operated on multiple cores on the multiple executors。

 on multiple nodes of the cluster simultaneously in parallel。So therefore， once again。

 the concept of cluster has multiple nodes。A node has multiple executors。

And an executor will have multiple cores that it uses to process the data。

And there are threads that the application actually runs and is processed on the course。

 so we have multiple thread based core computing on the executor of each node that exists within the cluster。

And this is a concept that we will be using。A thread what is a thread Well。

 this is a sequence of programmed instructions that are independently managed by a scheduler。

Threads are commonly used in operating systems， so on your smartphone and on your personal computer。

 on your laptop computer， on your iPad or tablet computer。

 all of the processes are operated based on multiplecore threads。

 you have multiple threads executed on multiple core and some share and some are independent。

A process commonly requires multiple threads to be executed simultaneously sharing memory。

Multiple threads may share a core to be processed or may be assigned to its own core。

A core is a computing component with an independent processing unit that reads and executes program instructions。

Multip corere processors have multiple cores on a single computing component， for example。

We have a dual core CPU， has two cores。A quad core CPU has four cores。

A big little processor has heterogeneous cores that share the same instruction set。

Big cores have high computing capability and use relatively more energy than the little cores do。

 and the little cores have much more energy saving capabilities， but they are slower。

So more computation burden tasks are assigned to the big course where the light operations。

 including the demon。Processes that run in the background are executed on the little course。

And an example of a big little CPU that's running on your computer or smartphone。

 if you bought it recently， then it probably has four big cores and four little cores operating altogether。

Spark variables and serialization。There are these two shared variables that Spark uses。

Broadcast variable and an accumulator。In broadcast variables。

 an application can send a read only value set to all worker notes。

 and that will be a broadcast variable。An accumulator is an aggregated value of multiple worker nodes。

 only the driver can access the accumulator variable。Tasks can only write to accumulator variables。

 and the tasks cannot use or read the accumulator variables。Some broadcast variable examples。

 a data set is small enough to fit inside memory within a single executor。

A data set can be loaded up on the driver as a lookup hash table。

A broadcast variable is broadcasted to all executors。

 and these are some of the examples where a broadcast variable would be used。In addition。

 map transformations on the executors can just reference the broadcast variables to do data set lookups。

Helps to avoid shuffle processes when joining data sets， and it saves a lot of time and processing。

 that's why it's used so effectively。Some accumulator examples。

 it's used to count events that are occurring during the execution， used frequently in debuing。

Serialization is a process that converts the state of an object， which is a data， a database， a app。

 a program， or something else。Into a stream of bys。

Serialized byte stream can be reconverted back into the original identical copy of the program or the object or the database。

Seralization is used for the purposes of data transfer over the network。

Saving RDD data to a solid state drive or a hard disk drive。And persisting operations。In addition。

 it's used for broadcasting variables。Java Serization is the default serialization scheme。

 it is the most commonly applied one。Various object types can be supported。

And you can support large serialized formats。It's relatively slow， so for production apps。

 faster serialization tools may be required。These are the references that I use and I recommend them to you。

 Thank you。

![](img/d466ea251365b05b837e53bff28513a4_2.png)

![](img/d466ea251365b05b837e53bff28513a4_3.png)