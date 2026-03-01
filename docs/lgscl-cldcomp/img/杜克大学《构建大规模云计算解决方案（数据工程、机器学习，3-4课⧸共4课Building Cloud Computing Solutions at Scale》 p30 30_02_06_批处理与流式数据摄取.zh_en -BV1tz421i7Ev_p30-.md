# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p30 30_02_06_批处理与流式数据摄取.zh_en -BV1tz421i7Ev_p30-

![](img/0090f757d2a31e90ce27b60512a7d16a_0.png)

。Ingesting by batch or by stream， let's dive into some AWS a data engineering concepts here。

 Let's first talk through what we mean by batch and by stream So we're going to talk through the key tasks for a data engineer。

 how you can use AWs services， things like glue， kinesis。

 also how streams can help you as well with Amazon knesesis streams and also we'll talk a little bit about IoT core and IoT analytics。

 All right， so first up， let's talk through the difference between batching and streaming ingestion workflows。

 So if we want to think through batch ingestion， it's going to involve running batch jobs that query a source move the resulting datas or。



![](img/0090f757d2a31e90ce27b60512a7d16a_2.png)

The data to durable storage in the pipeline and then perform the transformations。

And if we think about how this would work， they could be started on demand on a schedule or initiated by an event。

 So this is really a classic way to think about many of the things that we've been doing for the last several decades for example。

 dashboard would work really well for batch processing and traditional extract transform and load is going to use batch processing Now if we think about some of the differences though。

 with streaming， one of the things that you would want to consider is that once a stream is active。

 the records could arrive and be put on the stream continuously and then the consumers would then read the records off of the stream and process them and a sliding window of time and this means making them available for real-time analytics immediately。

So if we think about some of the drivers here。Of this process。

 whether it's going to be batch or ingestion is that you think about the volume of the data that the pipeline is going to handle at an interval。

So for example， if you need to ingest a continual stream of data that's going to have a impact on the choices that you make。

 also if you want to ingest larger individual records that are going to arrive periodically that's going to have an impact and so in both cases this is a high volume of data but the velocity would be really different so let's talk about some of the ways we can identify these differences。

So， for example， batch processing is running jobs that query a source。

 transform it and load into a pipeline， and traditional ETL is used for that。

 streaming records arrive and are put on the stream continuously and consumers would process them as they're available so that big advantage of a streaming ation is the opportunity to review results and take action immediately and the data is going to be ready for analysis with low latency。

 so the idea with stream processing is that you're going to handle high volume。

 high velocity unstructured data。So let's talk now about batch into a little bit more detail here。

The ingestion and preparing data process is going to do things like connect your data source and select the data to be ingested。

 you're going to identify the source schema and define the target schema so you can map the fields properly。

 you're going to transfer the data securely into the pipeline and then you're also going to perform transformations and load the process data into durable storage So the idea here is that you're going to perform a set of tasks each month and you're going to write scripts to perform those steps and rather than just doing it over and over again on the command line。

 you want to have a way to do that automatically。So if we think about a development framework。

 we're going to have needs for flexibility， we also want non-developers to use it。

 so there's a bunch of different parameters here to think about and one way to ensure the efficiency of processing and also the data integrity is to make sure that you're using orchestration tools that will handle the dependencies as well。

 so this is a big problem and data processing is not only do you have to do your automation but do you have the dependencies as well。

So if we think about this， batch ingestion allows you to write scripts to perform ETL and create jobs。

Workflow orchestration is going to help you manage the dependencies of jobs and handle failure management。

 and so when you select components for batch ingestion。

 you're going to consider the use for a team who needs to use the system。

The volume and types of data to be ingested and whether scaling and cost structure makes sense for your use case。

Okay let's talk through here about data sources and batch processing options。

 a few of them to consider would be you know Amazon Appflow would be one AWS DMS which is a ability to synchronize different data sources。

 AWS data exchange and so if we think about some of the things you can do it's really thinking about purpose built tools versus broadbased tools and one of the ways to really get into which purposebased tool is the best is to really dive into those tools so let's talk first here about Amazon Appflow it's a SaS service and the things you can do it we do with it are create a connection that reads from a SaS source and then filter it so this is pretty useful because you know a lot of times you would do something like this yourself but now the service does it for you and you would perform validations on the records you could securely。

Transfer that data to S3。We also have AWS DMMS or database migration service。

 something I've definitely used before in production。

 What's nice about it is you can point it to a data source like a database， you can filter it。

 map the tables and then ingest it into， let's say， an internal AWS database。

 So this works really well for things like you have a database in another cloud and you want to move it into the AWS platform。

 The AWS data syncnc is a great way to ingest data from file systems and you can do things like add filters to a subset of files or transfer data between self-manage storage systems and storage services and also use CloudWtch metrics to monitor the performance of file transfers。

The AWS data Exchange allows you to find and subscribe to sources， preview a data dictionary。

 copy data sets to S3， and also receive events from AWS data Exchange。

So some of the takeaways here are that the ingestion tools are going to really partner with the kinds of data you use。

 and the data exchange is going to simplify the finding and using of third party data sets。

Let's talk through glue here next for batch ingestion。

Glue is a great service because it allows you to automate and perform ETL operations and put those into your pipeline pretty easily and the automatic schema generation from semiconductorstructure data is one of the advantages。

And what I like about the glue system is that you can just point it at some data source like S3 or database and then create that schema and then it ties into these other services like Athena。

 and allows you to orchestrate complex ETL tasks， also lets you monitor， troubleshoot， etc。

The glue data catalog is going to store the metadata。Including the schema。

 So this allows you to see like the types， for example。 And then once you have the metadata there。

 then it allows you to do all kinds of really powerful things。

 So Glue Studio is pretty interesting because it gives you a GuI for authoring ETL jobs。

 And that means that you can do things like pull data from S3 kinesis or a JDBC source。

 you can transform it， sample it， specify target via the schema。You can also look at managed' jobs。

 etc ce， and the AWS glue runtime is going to use the open source Apache Sp system as well。

 so if we think about some of the ETL processes with glue。

 a few things to consider would be that you can use it to design multijob or multicrawler ETL processes and then you can also run the workflow on demand or even on a schedule。

Now， if we think about some of the things you can do as well。

 you can also do job bookmarks so you can process new data when you're rerunning on a schedule interval as well。

 and also it integrates with Cloudtrarail so you can record who's doing what so this is really nice for data governance。

Now， in a nutshell here， Glue is going to simplify ETL through features because it can generate in catalog scheme information。

 automatically create the ETL scripts， and then run those batch jobs in in an Apache sparkar runtime。

So let's talk about scaling， though， for batch。One of the issues with batch is that you're going to need to complete the job in a specific timeframe and you also want to do it on a given budget and with accuracy。

 So this is when you have to figure out some of the details here and so you can take a best guess when you're initially scaling it or you can actually have some auto scaling take care of that for you and so one of the ways you can do this is that you can actually use the glue auto scaling and so with glue auto scalinging。

 you're only going to pay for the E job time versus you know thinking about it from manually doing it yourself。

 So data processing units or DpUs are the unit of measurement and the single DPU as a worker so glue has a few different kinds of workers and they're geared really for different types of problems so if you wanted to get rid of a out of memory error。

 for example， you can pick a larger worker that has more memory。

So if you think about the trade offs for file size and compression。

 there's another one and generally speaking， the file formats are going to be a big factor in how this actually plays out。

So sparkk could process。You know， a lot of files in parallel。

 but then that adds a little a bit of overhead versus。Maybe doing a single large file。

 So these are some of the trade offs you have to think about。

A good example of this trade off is Apache parquet， because。

It can be a splittable file format and it's also open source。

And you can also use that to scale workers by using that kind of format。

So some of the things to consider here are that the performance goals for batch processing should focus on use case and glue jobs have options for scaling horizontally or vertically。

Well， if we think through some of the things that would happen with kinesis as well。

 this would be a good thing to cover and if we think about streaming pipelines。

 the main idea would be that the producers would put the records on the stream and the stream provides the durable storage。

 and then the consumers would read the records from a stream and process them in batches。

 So this is called a producer consumer workflow。And streaming pipelines are going to support real time processing of high velocity data。

 and as the data moves through the inGest or process and analysis phase。

 they're going to build components independentlyly and loosely couple them。

We also can think about Amazon kinesis data streams as a streaming service that meets the characteristics of a traditional streaming service。

 and if we think about the producers， they're going to put the data on a kinesis data stream stream。

Which is going to provide the durable storage for that data。

 and more than one producer can write to the stream。

 and the consumers can get the data from the stream and process it。

 So the stream is basically like a buffering between the incoming data and the processors of that data。

 and a stream can have multiple consumers。We also can think about how kinesis data streams are data records and the records are stored in shards。

 and the records can have unique sequence numbers， partition keys， data blobs。

 we also can think about Amazon Kinesis clientient library or KCL to read data from the stream and process it。

 and AWS Lambda functions can also be the consumers of a stream。

And so streaming is going to ingest and process things in a secure manner by default。

 and you can also configure kinesis to use the EWS identity and access management policies to。

Grrant access and also to encrypt the sensitive data automatically。Now。

 Kinsesis data Firehose is designed to ingest and deliver streaming data to data lakes on Amazon S3 and also handles things like data stores and analytics services like Redshift and Amazon Open search service。

 and the Kinesis data Firehose also has the ability to run built in transformations as well。

So what is a common use case for kinesis data Fire hose。

 it's to stream the data into a data lake and then convert it into a format that's required for analysis without having to do anything else。

 so that's a pretty useful use case。If we think about kinesis data analytics。

 it's a purpose built analytics system for streaming data。

And it also has sliding time window capabilities， and then you can write the results to a service like open search service Amazon Flink is a popular framework for processing stream data as well。

And basically kinesis datalytic is providing the underlying infrastructure for a Flink application。

 this means it's going to handle the core capabilities like provisioning compute and automatic scaling。

 and you can use Java， you can use Scala， you can use SQL for your Flink applications。

 and there's also kinesis data analyticstic Studio。

 which will run and produce Flink applications for you。

 and that means you can use a notebook and you can do SQL， Python and Scala。

So really to summarize here。Stream records are stored in shards。

 and they include a sequence number and partition key and a data blob The kinesis。

 producer library or KPL simplifies the writing producers that put records on a kinesis data stream and the kinesis data Fire hose is designed to deliver streaming data directly to storage and kinesis data analytics is a purpose built system to perform analytics on streaming data for realtime analytics。

So what are some scaling characteristics for stream processing， great question。

 well basically it's a way of thinking about streams using metrics to check that the processing is not being throttleled and you if you think about how that would indicate a need for read to write capacity。

 those metrics would then highlight expireiring records and then you can make sure that your stream is running long enough for the consumers to get them and then also to process the data。

Now， if you think about the kinesis data streams。The retention period is a critical component。

 so by default it's 24 hours， but you can even increase it up to 365 days。

And the right capacity is controlled by how many shards are allocated to the stream。

 and the recapac is going to scale through the thoroughput for consumers of the stream。

If we think about Cloudtrail and CloudWch， they're integrated with kinesis data Stre。

 and this means that you can look at metrics for a kinesis data stream and align the scaling considerations for those。

The kinesis data streams will allow you to scale how long the data remains on the stream。

 the stream's read capacity in the stream's write capacity。

The IoT data is often ingested by stream and this could allow you to ingest data by batch as well and so it's up to you to really tune that and now if we think about getting into IoT here a little bit some of the things to consider would be five categories。

 there are devices so this would be hardware like know something that's going to have a microcontroll or CPU memory。

 there's the interface and that could be a sensor， there's a communication so it could be communicated over a protocol like the HGDP protocol。

 there's also going to be cloud services。And then there's going to be apps。

So if we get into the IoT system here， it's going to use a MQTT messagequeuing telemetry transport protocol。

 and it has a pub sub model and this decouples the message creator from the message consumers。

So what that means is the publishers don't need to know anything about the subscribers they just publish to the topic。

And with AWS IoT Co， you can connect， process and act upon device data even when devices are offline。

So what this means is that IoT Co is really at the heart of IoT on AWS。

And some of the things to consider with IoT core are the device gateway is going to be an entry point for IoT devices to AWS。

The message broker is going to provide secure mechanism for devices。

 The registry is a catalog of static metadata， the rules engine。Is going to use rule actions。

 the identity service is going to provide the shared responsibility for security in AWS Cloud。Now。

 some of the things to consider would be that the kinesis data Fire hose is going to insert data into a denimmo Db table。

 and also a common scenario would be that IoT data in Amazon S3 is going to stream into kinesis streaming service and also the streaming pipeline is going to work as well with kinesis for stream processing。

And this is really part of the IoT feedback loop。Now if we think about IoT analytics。

 it's going to have multiple components so it's going to have a channel and this is going to collect data from a topic。

 it's going to have a pipeline and this is going to consume messages from the channel and do processing on it。

 then the pipeline is going to store the processed。

 made a message in a data store and so the data store is not like a data it's basically like a S3 bucket and if you retrieve the data from the data store this is going to be done by creating a data set and that data could even contain the SQL that you would use to query it and then finally you could use IoT analytics and query your data from Amazon Quicksite。

Now， if we think about IoT devices using a Ps model to communicate with each other， in a Psubmod。

 the publishers send messages to a topic and the subscribers subscribe to that topic。

Really in a nutshell here， we've covered quite a bit of data and let's go ahead and wrap it up and so we've talked about focusing on processes to build an ingestion layer that supports batch or streaming。

 We also talked about the different AWS services involved。

 including ways to simplify batch ingestion tasks like Amazon Appflow。

 AWS DMMSS data syncnc and AWS data exchange。 We also talked about AWS glue and how you can use it to automate batch ingestion。

And we also looked at some of the characteristics of kin cistrium products。

And we went through some of the things you can do with AWS gluelu。

 kinesis data streamams and also we talked at the end about AWS IoT core and also AWS IoT analytics。

 and those all tied together with the previous services as well as part of ingesting and transforming streaming IoT data。



![](img/0090f757d2a31e90ce27b60512a7d16a_4.png)