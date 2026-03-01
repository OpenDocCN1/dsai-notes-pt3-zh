# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p24 24_01_08_使用AWS处理大数据.zh_en -BV1tz421i7Ev_p24-

![](img/f577c9d58b907ff3edb79b290d08bf87_0.png)

Processing big data， it's a big topic and the pun is intended。

 let's go ahead and get started right into the material here。

 we're going to talk about how to select big data processing frameworks that best support your workload we'll talk about Hadoop。

 EMR also about data processing in AWS and we'll also get into some things like Apache Hooty as well which is a newer product so first up here let's get into the concepts。



![](img/f577c9d58b907ff3edb79b290d08bf87_2.png)

![](img/f577c9d58b907ff3edb79b290d08bf87_3.png)

![](img/f577c9d58b907ff3edb79b290d08bf87_4.png)

In terms of the course in some of the data engineering so far。

 we've talked about this iterative workflow and how data is going to flow between the processing and storage and also how raw data is ingested。

 stored， transformed and processed and this data often is in a different format and the format of the data is used for analysis and visualization。

 so let's talk about some of these framework for processing big data and the services that are used to process the analytics and ML pipelines。

First up here， we have a architecture that we can consider that would be a multiple ETL or ELT pipeline that performs iterative processing of data for different types of preparation and consumption and then each pipeline would read the data from a storage layer and then process it using temporary storage as needed and then write it to the appropriate location within the other storage layer。

 so let's talk a little bit about how that would work。In terms of batch data processing。

 this is going to involve querying a huge amount of data typically which is like coal data。

 so it's infrequently accessed and with batch processing it could take hours to analyze the data to get the answer So a pretty good example this would be let's say Ka meanss clustering with Ke meanss clustering you would potentially discover an insight and let's say you wanted to discover some things that customers are buying and you have lots of customer data so you would do this k meanss operation maybe once a week Now the batch processing jobs would then have to scan all the new input data and they can tolerate data that is maybe partial or no structure and you also can have processing jobs that compute results from other available data sets like maybe a deep analysis data set or you could query over the different the same data sets but with slightly different queries and in that scenario a map。

Do system like？Maybe Hadoop or EMR could be some of the examples now other ones could also be AWS batch which is a batch service as well There's also stream data processing and this is where you're processing continuous data。

 maybe thousands of data sources and these could come in maybe in smaller sizes。

 and they could be a wide variety of data， it could be mobile and web apps e-commerce purchases in game analytics。

 maybe information from social networks it also could be financial trading data。

 geospatial telemetry。or even instrumentation in a data center， so like CPU， diso。

 those kinds of metrics or latency， and this data is going to be processed sequentially and incrementally on a record by record basis or even over a sliding window and so this is typically used in analytics or maybe doing some kind of pattern recognition。

 aggregations， filtering sampling。And some of the things that you could use for this would be， know。

 let's say， website clicks or geolocation or physical goods。

Now if we think about launching a cluster， one of the things we're going to have to do is figure out what is the framework that you're going to use in order to do your batch data processing and a few things to consider would be let's say Hadoop and Sp。

 these are very common framework for EMO and you can also use an application to process it as well So maybe it's something like databs or you're using some kind of rustbased wrapper and you also could use machine learning algorithms and you could make even stream processing or data。

Warehouse type applications and。There are many frameworks that are available for processing big data and new frameworks and enhancements are really released very commonly。

 so this is another issue is that do you have the right software installed。

 the right version number on your cluster because you could have one cluster potentially if you manage it yourself that had a node with a newer version and then other versions have a slightly older version and that could cause problems。



![](img/f577c9d58b907ff3edb79b290d08bf87_6.png)

Now， big data processing is generally divided into a couple categories， as we've discussed earlier。

Btch and streaming and the batch is going to be the infrequent cold data， maybe analytics。

 and the streaming is the hot or frequently accessed data。

 and that's going to have to be processed sequentially or incrementally。

But they both benefit from specialized data processing frameworks。



![](img/f577c9d58b907ff3edb79b290d08bf87_8.png)

First up， let's talk about Hadoop， kind of the classic and Hadoop is open source。

 it uses a distributed processing architecture， Hadoop will map to a cluster of commodity servers and there's forming components。

 there's the HDFS or Hadoop distributed file system。



![](img/f577c9d58b907ff3edb79b290d08bf87_10.png)

There's yarn， which is yet another resource negotiator， there's map Reduce。

 and then there's Hadoop Common， and the Hadoop clusters will consist of a main node and then the worker nodes。

 And in this format， the main nodes are the orchestrators and the worker nodes are actually doing the work。

 So why would you care about Hadoop， well you can have essentially infinite data。

You're not required to preproces the data beforehand， there's a lot of flexibility。

High fault tolerance。Also the infrastructure is scalable， like for data processing， computing。

 you can add more nodes， you can also process structured， unstructured semistructured。

 but there are also challenges and a few of them are that it's open source。

 there could be stability issues， there could be challenges from maybe you can only run the latest version versus an older version and also Java is not a very modern language。

And so Java asked some things that。Maybe are not optimal with some of the newer languages as well。

 like garbage collection could be one of the performance issues， there could be security issues。

 also maybe authentication encryption。

![](img/f577c9d58b907ff3edb79b290d08bf87_12.png)

So the HDFS is a distributed file system of Hadoop and you can use it to distribute stores across the entire file system and it's also used by applications that have large data sets to have high aggregate data bandwidth and this data velocity really gives you the ability to split the data into small blocks and then share those blocks across several nodes of the cluster and then each block would reside in a different data node when possible and to avoid using。

A scenario or getting into a scenario where you're losing data if a cluster node fails。

 the HCFS would replicate the block several times to different nodes。

 so there's a lot of fault tolerance built into the Hadoop architecture。

Now yarn is an interesting thing because it has several primary components。

 it's a large scale distributed operating system that is used inside of Hadoop。

 and it makes sure that the data that's stored in HDFS is accessible for different processing compute units and it dynamically coordinates the use of the resources so as the scheduler so let's dive into those resources。

 first up， the resource manager， this is the control。

 the resources and manages the containers that are launched on each cluster node and its side of that there's two subcomponents which is the scheduler and this allocates the resources to the running application。

Based on the resource requirements of the applications， and then there's the application manager。

 which accepts job submissions， negotiates the first container to run the application leader。

 and then provides the service to restart application leader on failure。

 There's also the node manager which controls the use of resources within a single Hadoop cluster node。

 There's also application leader which works with resource manager and node manager to acquire those cluster resources for processing。

 and then there's the containers which are the collection of cluster resources like memory and compute。

 and these are allocated from a single cluster node to perform a signed processing activity。



![](img/f577c9d58b907ff3edb79b290d08bf87_14.png)

Now map reduces a framework for processing large data sets with a parallel distributed algorithm on a cluster and it simplifies writing parallel distributed applications by handling all the logic So what this means is that you just provide the map and the reduce functions and the map function is going to map the data to a set of keyvalue pairs and this is an intermediate results and then the reduced function is going to combine the intermediate results like maybe additional algorithms and then it's going to produce the final output so the idea here is that map is where the distributed compute happens and the multiple framework available like hive for example。

 can automatically generate map and reduce programs and the mapre framework is really at the core of Hadoop and provides the scalability and also designed again for fault tolerance where each worker node will report its status to the leader node so that you don't send a job that's going to fail because you have the status of that node and the。

Notode can then redistribute work if a node is not working， for example。

 And when you're running a big data job， the processes begin as mapre splits。Into discrete tasks。

 and then those tasks can also be a run in parallel。

 and then the mapper phase would then map it to key value pairs。

 And then as soon as the Maper phase is finished， the next step is to shuffle to sort the data。

And then during this step， similar words maybe are shuffled and sorted and grouped together。

 and then finally the reduced phase would count the number of occurrences in the words， for example。

 if you're going I don't know do web stats or something and then generate the output file。



![](img/f577c9d58b907ff3edb79b290d08bf87_16.png)

So if you use HFS to store data， Hadoop is going to automatically split the data inside of the HFS for you。

 and if you use S3 to store the data， Hadoop will split the data by reading the files in multiple you know parts of the file system and then that split data is then used to read and write to S3 Now the EMR version is also a component of this system as well。

So that's something to be aware of and large numbers of tasks， for example。

 maybe have different characteristics and a smaller number of tasks。

 and so those are some of the tuning characteristics that you have to be aware of now。

An important thing to be aware of is that a default split maybe would be 128 mebytes and then8 mapper processes could process the data。

 but big data because it has to you know maintain the pace with the volume and the velocity of the data。

 maybe you use 500 mebit split。 So there are some tunings that you have to do depending on the size of your data。



![](img/f577c9d58b907ff3edb79b290d08bf87_18.png)

And then there's also other frameworks。One of them is Apache Flink。

 which is a streaming data flow engine that builds real-time streaming processes for big data and Flink would perform transformations on data like kinesis data streams or Apache Cassand or databases and it uses a data streaming runtime engine and pipeline parallelism to perform operations and the engine itself can do both batch and streaming and even has a little bit of SQL support as well。

 and also the actions are similar to distributed collections in Hadoop or Spar now Flink's APIs also categorized datas and data streams and datas are transformations on sets or collections of distributed data and these data streams or transformations on streaming data like Amazon kinesis。

Also， EMR supports Flink as a yarn application so you can manage it that way as well。

There are more though， there is also Apache hive， which is an open source SQL like database that runs on top of Hadoop。

 and it also offers some limited data warehouse capabilities and the reason for using hive is that you can avoid complexities of writing the map reduce in a lower levell language like Java so instead you can write SQL and maybe you're a data scientist and you can prototype things out quicker Presto is another one that is an open source distributed in memoryory SQL query engine。

And this is similar to Hve because they're both SQL or SQL like query engines。

 and Presto doesn't run on mapreduce， instead it runs in memory。

 there also is another one which is Apache P， and that's a simple high levell textual data flow language that uses parallel processing to perform analysis on large data sets in the script developers who need。

 let's say， an intuitive way to prototype and develop jobs。

 could use PG as a possible processing framework。All right。

 let's talk a little bit more now about Apache Hadoop。



![](img/f577c9d58b907ff3edb79b290d08bf87_20.png)

And wrap it up here， you know Hadoop is its own distributed file system or HDFS when you store HDFS。

 Hadoop splits the data into smaller data blocks by using MapRduce。

And then Mapreduce will process large data sets with a parallel， distributed algorithm on a cluster。

 and Mapreuce splits jobs into discrete tasks so those job tasks can be run in parallel。



![](img/f577c9d58b907ff3edb79b290d08bf87_22.png)

![](img/f577c9d58b907ff3edb79b290d08bf87_23.png)

All right， let's dig into Apache Spark now。So Spark is an open source distributed processing framework that is actually built to address the limitations of map Red。

And Spark has data in memory reduces the number of steps in a job。

 reduces data across multiple parallel operations， and with Spar， there's only one step needed。

 and that's basically read into memory and then operations are performed and the written back。

 So there's a lot faster processing。 and because it's a cluster framework and programming model for processing big data workloads you can run it on Amazon EMR you can even use the EMR file system to directly access the data in S3 and Spark supports multiple interactive query modules like SparSQL and Spark also reuses data with an in-memory cache。

 So let's say email algorithms are repeatedly called on the same data set So's one of the benefits of this cache。

And the data reuse is accomplished by creating data frames。

 which is an abstraction over the resilient distributed data or RDD。

 and the data frames are a collection of objects that are cached in memory and reused in multiple spark operations。

 and this is a dramatic lowering of latency， and it makes spark multiple times faster than that produceduce。

 especially for ML and interactive analytics。So a spark cluster spark applications。

 they run as independent sets of processes， and a Sp context object resides within the driver and coordinates these processes and this Sp connects to a cluster manager and it acquires executors from the nodes and then these executors are responsible for running the computations and then storing the data in the cache for the application。

 and the Sp context object communicates directly with the executors sending them tasks to be processed。



![](img/f577c9d58b907ff3edb79b290d08bf87_25.png)

So if you think about the name of Sparkco， it's the foundation of the platform and it's responsible for a few things like memory management。

 fault recovery and scheduling， distributed and monitoring jobs。

 also interacting with storage systems and Spark core is exposed through APIs built for Java， Scala。

 Python and are and there's even other languages coming as well。

 and these APIs hide the complexity of the distributed processing behind simple。

 yet highle operations。Now SparkSQL is a distributed query engine that provides low latency interactive queries。

 let's say 100 times faster than map produce， and SparSQL is cost based optimizer， columnar storage。

 cogen for fast queries， and it scales to thousands of nodes。

Spark graphra X is distributed a graph processing framework。

 which which is a very powerful new feature。 and then Sp streaming as real time solution。

That uses Sparks corere for streaming and then Spk MLlib is a library for algorithms on ML data at scale。

 So， for example， clustering， that would be a classic one。



![](img/f577c9d58b907ff3edb79b290d08bf87_27.png)

So Apache Spark does address some of the limitations of a dupe by doing things in memory。

 reducing the number of steps in a job， and then reusing data across multiple parallel operations。

 and then the cache can speed up things like ML algorithms again， let's say like clustering。



![](img/f577c9d58b907ff3edb79b290d08bf87_29.png)

Okay， let's talk a little bit now about Amazon EMR。

So EMR is a managed cluster platform and this simplifies big data frameworks like Spark and AWS can then process and analyze huge amounts of data and really it's equivalent in some sense too you have MySQL database and then you run it inside of RDS。

 same thing， this is a managed version of Spark， and what it does is it gives you the ability to launch a cluster in minutes。

 deploy the cluster， resize it etc ce without you having to manually do it yourself。

And so let's dive into the main components with Amazon EMR。 there's a cluster。

 which is a collection of Amazon El compute nodes。 There's the main node。

 which is responsible for managing the cluster。And then every cluster has a main node。

 and you can create a single node cluster that only has a main node。

 and the core nodes are responsible for running tasks and storing the data in HFS。

And then the task nodes， which are optional， will only run the task。

 and these task nodes will not store the data in each DFS。

 and you can add them at cluster launch or even add them to an already running cluster。

In terms of the storage layer， a few things to consider with HCS and EMRFS is that the layer includes the local file system of any locally connected disk。

 and the EC2 instance with the cluster has preconfigured block storage known as instance storage which is going to persist for the duration of the instance existence。

And the cluster resource management layer is going to be responsible for managing the cluster resources as scheduling data processing jobs。

 yarn is the default component that EMR uses， but you could actually use other frameworks as well。

 and then in the data processing layer， the main framework as do map reduce and Sp and then the application and programming layer is where the applications that are discussed earlier are used。

 and this is where you do ML algorithm， stream processing， data warehouse。

Now in terms of launching a cluster， you can choose frameworks and applications to install data processing needs and to process the data in the EMR cluster。

 you can submit the jobs or queries directly to the application。

 a few things to consider would be submit an input data for processing。

 process the output of the first step by using PIG。

 maybe process second input data by using hive and then write an output data set。



![](img/f577c9d58b907ff3edb79b290d08bf87_31.png)

So you can use EMR to perform automated installations of clusters for even petabyte scale data。

 interactive analytics， and ML projects。

![](img/f577c9d58b907ff3edb79b290d08bf87_33.png)

Al right， let's talk about managing EMR though so really if you think about managing EMR。

 you can create an EMR cluster in the console in a few ways。

 one of them is you just manually click and start the other way you can do it is you can do command line。

 which is a pretty powerful way as well you just open up the AWSCLI and launch a cluster。

 and then there's API mode which allows you to let's say programmatically on an event you could launch the AWS EMR instance。

And the cluster is often used for long running analytics。

 so this would be maybe a persistent cluster。So by default。

 the clusters are going to be long running so they can keep taking work so in a bigger organization you may have a cluster that runs 24/7 so that you can do interactive analytics There's also transient clusters though and that allows you to maybe terminate something after doing let's say step functions or AWS Slamda calls it and what's nice about that is Amazon would manage it for you。

In terms of an EMR cluster， the main node is an EC2 instance that coordinates the EC2 instances that are running the task and the core nodes and that main node would expose a public DNS name。

And you can connect to it。 And by default， EMmar creates security group rules for the main node and the core and the task。

 So this is very nice because it simplifies what could be a very complex cluster setup。

 and then you can connect to the main node only while the cluster is running when it terminates the EC2 instance that acts as the main node is also terminated and is's no longer available to connect to the main node you have to authenticate it to the cluster and you could use crboros for authentication or even specify an Amazon Ec2 key pair private key when you launch the cluster and the EC2 key pair private key is specified in the security and access section of the cluster。

 Now by default， the elastic mapreduce main security group does not permit inbound SSH So you might need to add。

 let's say a port 22 rule if you're going access it that way。

You can also adjust the number of EC2 instances that are available to Amazon EMR。

And when you scale the resources， there are a few things to consider。

 like you can't scale the number of nodes after your cluster has been configured。

 although you can scale core and task nodes within the cluster。

other consideration is you can't reconfigure and resize an instance at the same time。

That means if you initiate a resize， so you want a bigger node， the instance group is， you。

 basically you have to wait until your reconfiguration is done。



![](img/f577c9d58b907ff3edb79b290d08bf87_35.png)

So there's three available methods available to launch EMware clusters， theres interactive mode。

 theres commandlan mode and there's API mode， and Amazon EMware clusters are long running by default。

 and then finally all external connections to EMR clusters have to be made through the main note。



![](img/f577c9d58b907ff3edb79b290d08bf87_37.png)

Okay， let's talk about Apache Hooty， which is a open source data management framework。

 and this is used to simplify incremental data processing and data pipeline development by providing record level insert update。



![](img/f577c9d58b907ff3edb79b290d08bf87_39.png)

Ubstt and delete capabilities， so up means the ability to insert records into an existing data set if they don't already exist or to update them if they do。

And you can do this even in near real time by managing S3， and so it's integrated with Apache Spark。

 hive， Presto， and then EMR can even install it automatically for you。

So the COW stores your data in a columnar format， and this is the Apache parquet format and then each update to the data。

Creates a new version of file during the right process。

 And this is the default type of storage for Hooty， and it's well suited for Re heavy workloads。

And it also provides you three logical views to access your data， a read optimized view。

 incremental view and real time view。

![](img/f577c9d58b907ff3edb79b290d08bf87_41.png)

So to summarize here， it provides the ability to ingest and update data in near real time。

By organizing S3， and it maintains metadata the actions that are performed to make sure that they're both atomic and consistent。

 All right， we talked about a lot of stuff。 let's go ahead and wrap things up here。

 We focused on processing frameworks and AWS services for supporting big data。

 We also talked about how to compare processing frameworks。 talked about Hadoop。 We talked about EMR。

 we also talked about managing EMR clusters。

![](img/f577c9d58b907ff3edb79b290d08bf87_43.png)

![](img/f577c9d58b907ff3edb79b290d08bf87_44.png)