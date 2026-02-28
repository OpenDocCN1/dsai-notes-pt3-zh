# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p23 23_01_07_AWS数据工程设计原则导论.zh_en -BV1tz421i7Ev_p23-

![](img/a8b4a168086cabb79fb3db2e16b8a523_0.png)

Design principles and patterns for data pipelines， This is a course from AWS Academy data engineering that I'm going to go through and annotate First up here we can dive right into what we're going to cover and we're going to cover the design principles and patterns。



![](img/a8b4a168086cabb79fb3db2e16b8a523_2.png)

![](img/a8b4a168086cabb79fb3db2e16b8a523_3.png)

And this includes the well architected framework， also we're going to think through milestones in data stores and data architectures。

 also components of modern data architectures， and we'll also look at AWS design considerations and key services for streaming pipelines。

So the module over overview here is well architected framework， evolution of data architectures。

 modern data architecture， streaming pipelines， and let's go ahead and talk about the well architectected framework pillars so the idea here is that you're always starting from this framework with AWS you have operational excellence。

 security， reliability， performance efficiency， cost optimization and sustainability。

 this is a good way to think about a system you're building。

And if we think about the well architected lens， this would include things like extending the guidance to specific domains。

you can even look at those domains inside of the well architected framework page。

 the data analytics lens is specific to architected analytic workloads and provides a lot of information about those kinds of workloads。

Let's go ahead and talk about this well architected framework here。

 so in a nutshell again it's the six pillars and it also has some guidance that's very specific with the data problem。

 which is things like volume， velocity， variety， veracity and value。



![](img/a8b4a168086cabb79fb3db2e16b8a523_5.png)

So let's talk about the evolution of data architectures here。

 If we think about a distributed system here， you know we have things like mainframes。

 clients Internet3 tier cloudbased microservices so this has been evolving for the past 50 years or so and if we take a look at how data stores are working these originally were very rigid right because everything was designed around a SQL database in the Internet era we got some non-relational databases and then in the big data era。

 let's say 2010 or so that's when you started to get these data lakes so you can distribute the CPU and diskcao and storage and then now 2020 and above we're starting to see purpose built cloud systems。

And this includes things like microservices。Now， if we look through the data architectures that are evolving to handle the volume and the velocity here。

 some of the things to really think about is that in the old 198080s era。

 it would be that the databases were overwhelmed。In maybe the 2000 era。

 the relational databases weren't really designed for AIML。

 and then with the newer systems in big data， they couldn't keep up with real time and what we're starting to see here is this need for even further evolution and modernization and we can see that AWS could be one of the solutions that will solve the problem if it's done correctly。



![](img/a8b4a168086cabb79fb3db2e16b8a523_7.png)

So really the takeaways here are that the data store and architectures evolve to adapt to the demands of the volume variety and velocity。

 the modern data architectures continue to use different types of data。

 and the goal is to unify these different sources to maintain a single source of truth。

So in terms of a modern data architecture on AWS。We can think about some of the key design characteristics。

 and the idea here is that you've got a centralized location for your data。

 it's available to all the consumers to perform analytics and to also run AIML。

 but it doesn't mean that you only have one data store or that there's a single source of truth。

The data lake does provide a centralized repository。

 but it's possible that the data might be queried from the lake or it could be moved to another purpose built system。

 for example， No SQL database。Now， if we look at outside。

 that's when an organization stores the data in a purposebuilt data store like a data warehouse or a database。

 inside out is when an organization stores the data in a data lake and then moves a portion of that data to a purpose-built data store and then around the perimeter is when an organization moves data directly from the other data store components that are integrated with the data lake without needing to access the data lake itself。

A good example would be copying the product catalog to a database so that there's a search that's easier done through the product catalog。

So modern data architectures are going to address a lot of these problems in one architecture。Now。

 if we think through AWS purpose build data St and analytics。

 a few things to consider with the Amazon S St service or S3。

 this provides storage for structured and unstructured data。

And is the storage service of choice to build a data lake on AWS with Amazon S3。

 you can cost effectively build and scale a data lake of any size。

Amazon Athena is shown on the data lake to illustrate that it provides interactive querying。

The architecture as well could use things like Amazon Redshift for fully managed data warehouse。

 Amazon Open search， for purpose built datastore， Amazon EMR for big data processing。

 Amazon Aurora for a relational database engine that's built for the cloud Dunlo DB is a nonreal database that is designed to run high performance applications。

 and then SageMaker is an AI ML service that democratizes ML processing。If we look at lake formation。

 this was something that was built to make it easier to manage time consuming tasks that are related to load。

 monitor， and manage data lakes， and lake formation helps catalog data and classify as secure for different types of access。

So some of the takeaways here are that a data lake provides central storage and is integrated with the purpose built data storage and processing tools。

 so the idea is that the data lake has essentially infinite capacity for doing whatever it is you need to do。

The data moves into the data lake that's outside in， and then from the data lake to other stores。

 this is inside out， and it might also move directly from purpose built stores around the perimeter。

 Amazon S 3 provides the data lake and lake formation and glue will provide the seamless access。



![](img/a8b4a168086cabb79fb3db2e16b8a523_9.png)

Now we can talk about a modern data architecture pipeline， which is ingestion and storage。

And to first start out， we'll talk about the ingestion layer and you can match AWS services to source data so you can more easily bring in different types of data。

And these services also integrate directly with the storage layer components。

 and the storage layer has two sublayers。The first one would be storage and the other one would be a catalog so you can look at the metadata。

 you can look at the data sets。And then from there。

 you can look at how we can dig into it in more detail， so to dig into this in more detail。

Amazon Appflow can ingest from a SaS application like Salesforce or Zendesk。

 AWS Dataase Mi or AWS DMMSS can ingest from operational databases like OLTP， ERRP， CRM。

 or line of Business database and the AWS Data Sync can ingest from file shares。

 and Amazon kinesis Data streams and kinesis Data Fire hose ingest from streaming Data sources。

So really thinking through this modern data architecture storage layer。

 we first have the data storage layer looking through providing durability scalability。

 costeffective components and in this EWS architecture redshift and S3 will provide that unified and also natively integrated storage layer。

 the catalog layer in the storage layer is responsible for storing business and technical metadata about the data。

 So this is critical for things like data governance the metadata supports the ability defined find and query the data that's stored in the data lake and data warehouse without doing expensive operations just to find that data it's already done once and then you can go through and find the data from the catalog and in this architecture。

 the lake formation in AWS glue will work together to collect。

And store this metadata and make it available when needed。Now， in terms of。The data in a warehouse。

 it's normally going to be ingested from highly structured sources like a transactional system relational database on a regular cadence。

 but with redshift it also supports semistructured data into staging tables and this can be done if you're going to do some kind of analytics on it right so you could put this in to the staging table and then at that point do some other processing。

 So the data in the data lake。That typically drives machine learning or data science would be a good place for this。

 and in terms of the Amazon S3 data lake， it also supports storage of data in both structured。

And semi structured and finally even unstructured formats。

 and it can scale automatically behind the scenes and this is really the infinite capacity。

And the native integration between S3 and Redshift means that you can adjust data into S3 and prepare it for the data warehouse as needed。

Now， if we think through stored zone， this is an important component of S3 is that zones include things like landing。

 raw， trusted and curated， and the data could pass through each of the zones as it's cleaned。

 it's normalized， It's augmented， It's transformed。

 and then that transform data is stored into a zone that matches the readiness for consumption。

 a good example would be data that's being adjusted in Amazon S3 data lake arrives at a landing zone。

 then it's cleaned and stored into the raw zone for permanent storage because the data that's destined for a data warehouse needs to be highly trusted and conforms to a schema you might even have to do further processing。

 So additional transformations could。Do things like applying the schema， maybe partitioning。

 and you could also do other transformations like renaming certain fields。

 and then the processing layer would then prepare that data for the curated zone by modeling and augmenting it to be joined with other dataset sets so this would be called enrichment and then it would store that data in a way that could allow for it to be transformed and validated and these data sets from the curated layer are ready to be ingested into a warehouse making them available for low latency access or complex SQL querying。

Now， in terms of the cataloging and we have the AWS glue service that helps you simplify data movement and transformation with a pipeline and you can use glue to generate schemas。

 and then you also can use AWS glue data crawlers to automatically discover the schema as well and generate metadata。

 So this is probably the best possible way to look at your data lake is that the schema is inferred that inferred schema then gets put into a catalog。

 And then in the case of the AWS glue data catalog。

 it can then send that data and metadata to lake formation。

 Then the lake formation service could simplify the setting up the accessing and the securing of the data lake and what's critical with。

The data lake is that you have proper data governance so that you understand who has access to what parts of the data and're not leaking data or breaking the law by giving access to the data in a way that is not legally going to fit the needs of your organization。

 you can also use Amazon Redshift spectrum， and that can allow users to write SQL queries that combine data from the data lake in the data warehouse。

 and then when a user makes a query request， spectrum gets the schema information from the lake formation catalog and uses it to query the data lake。



![](img/a8b4a168086cabb79fb3db2e16b8a523_11.png)

So in a nutshell， some of the key takeaways here are that the AWS modern data architecture uses purpose built tools to ingest data based on the characteristics of the data。

 The storage layer includes two layers。 The first is a storage layer that uses redshift as its data warehouse and Amazon S3 for its data lake。

 and then that second catalog layer uses AWS glue and lake formation and then finally。

That catalog could maintain metadata。And also provide the schema to end users。

 modern data architectureure， pipeline processing and consumption。

Let's talk through a few of the things here， first we have processing and consumption layers。

In the modern data architecture， that prepare data and make it available to consumers。

This consumption layer would equate。Things like analysis and visualization。Of a data pipeline。

 and also it's a reference architecture and it could be referred to as the consumption layer。Now。

 if we look through the processing side， one of the things to consider is that each pipeline would read data from storage layer。

 and it would process it using temporary storage as needed。

 and then it would write to the appropriate location in the storage layer。

And if we group this into three main types， it would be a SQL based processing using the data warehouse like Redshift。

 a big data processing using big data tools like Amazon EMR or AWS gluelu or something like Databricks or snowflake。

And then you have the real time processing using streaming like Amazon Kinineesis data Analytic or Spark streaming。

If we look at the consumption layer， the data consumption layer is responsible for scalable and performant components that use unified interfaces to access all the data and metadata in the storage layer。

 and that consumption layer would democratize access to data sets for different types of users。

Across the organization and enable different analysis methods。

 and each method has the ability to combine data from data warehouse。

 which is stored in traditional schemas and also the data in the lake。

 which is stored in open formats。If we look at consuming data by using interactive SQL。

 some of the things to consider would be using tools for the business analysts and the data scientists and this would include a tool like Redshift and Redshift Specrum and Athena and what's really powerful is that you can store the data in one spot but then query it using interactive SQL。

 so the SQL language even though it's been developed initially in the early 1970s you can use that same query language across these sophisticated systems。

Where there are no servers that you're actually running up。

 you're actually having the catalog itself do a lot of the hard work。

 as well as the behind the scenes serverless big data systems。If we take a look at Quicksite。

 it's a serverless system that helps you create and publish interactive business intelligence dashboards and Quickightite is one of the BI tools that an organization could use to derive business intelligence and also it can enrich dashboards and visualizations with automated email insights like forecasting an anomaly detection。

 so even even have to be an expert with machine learning you can point it to a data and it' will give you some predictions。

Now in terms of consuming data for machine learning。

 the interfaces that are available in this architecture sim data preparation steps。

 and so a data scientist after they prepare the data they can develop train and deploy the models by connecting ML tools to the storage layer。

 and SageMaker is going to connect the storage later layer to access the training feature sets。

 and SageMaker is a fully managed service that provides components to build train and deploy models using an integrated development environment or IDE called Amazon SageMaker Studio。

 and in studio， you can upload you can create new notebooks can train in tune models and you even can use a code editor to actually get inside of the SageMake interface and build things that way as well。

So in a nutshell， some of the key takeaways here are that the processing layer is where the data is transferred for some type of consumption and the modern data architecture supports three general types of processing SQL based ETL。

 big data in near realtime ETL， and then the consumption layer。

 includes components that access to the data in metadata in the storage layer。

Including the data that's transformed by the processing layer and the consumption layer supports three analysis methods。

 interactive SQL queries， BI dashboard and ML。

![](img/a8b4a168086cabb79fb3db2e16b8a523_13.png)

Now let's talk about a streaming analytics pipeline and it's worth diving into what this really means。

In a nutshell， it means that。The same general rules are followed。

 but there are a few unique considerations。 And to start with， let's look at the data sources。

 This includes clickstream logs， mobile apps， existing application databases， Iot。

 anything where it's going to be used in real time and also analysis later。

 So the producer would ingest the records into the stream。

 And the producer are going to be integrations that collect data from a source and loaded into a stream。

 The consumers would then process those records。 So again， going back to the Iot example。

 of the producer could be an Iot device like some sensor thats sending packets constantly。

 and then the consumer is then going to process that record。

In the pipeline that's depicted in this you know kind of canonical story， it would be。

 you know an Amazon CloudWch event and the producer would then put that CloudWch event onto a stream and then kinnesesis data streams would provide the storage。

 So with real time streaming analytics， the records on the stream are typically processed sequentially and incrementally by record over a sliding time window。

 and in a pipeline， it's a way to think about this。

On AWS is called Knesesis data Analytics and it's a consumer of the stream and process streaming data that's used for either a custom application or even standard SQL。

 and you could even send the results to open search service and they could be used to visualize realtime insights with open search dashboards immediately。



![](img/a8b4a168086cabb79fb3db2e16b8a523_15.png)

So the key takeaways here are that streaming analytics include producers who put things on a stream and consumers who get the things off the stream。

 a stream provides temporary storage to process incoming data in real time for delivery to realtime applications like realtime dashboards and the results of streaming analytics might also be saved to a more durable storage system for additional processing downstream。



![](img/a8b4a168086cabb79fb3db2e16b8a523_17.png)