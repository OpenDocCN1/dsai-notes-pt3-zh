# IBM 数据分析师专业证书课程 1：《数据分析简介》｜introduction-to-data-analytics｜ - P18：17_数据集市，数据湖，ETL和数据管道.zh - GPT中英字幕课程资源 - BV18P411p7Qj

嗯。Earlier in the course， we examine databases， data warehouses and big data stores now we'll go a little deeper in our exploration of data warehouses。

 data mars and data lakes， and also learn about the ETL process and data pipelines。



![](img/42d08c4e20c8c2528630f2867eb67aaa_1.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_2.png)

A data warehouse works like a multipurpose storage for different use cases。

 By the time data comes into the warehouse。 It has already been modeled and structured for a specific purpose。

 Mean it is analysis ready As an organization， you would opt for a data warehouse when you have massive amounts of data from your operational systems that need to be readily available for reporting and analysis。

 Data warehouses serve as the single source of truth。

 Storing current and historical data that has been cleansed， Coned and categorized。

 A data warehouse is a multipurpose enabler of operational and performance analytics。😊。



![](img/42d08c4e20c8c2528630f2867eb67aaa_4.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_5.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_6.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_7.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_8.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_9.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_10.png)

A data mart is a subsection of the data warehouse built specifically for a particular business function。

 purpose or community of users。 The idea is to provide stakeholders data that is most relevant to them when they need it。

 For example， the sales or finance teams accessing data for their quarterly reports and projections。

 Since a data mart offers analytical capabilities for a restricted area of the data warehouse。

 It offers isolated security and isolated performance。

 The most important role of a data mart is business specific reporting and analytics。



![](img/42d08c4e20c8c2528630f2867eb67aaa_12.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_13.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_14.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_15.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_16.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_17.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_18.png)

A data lake is a storage repository that can store large amounts of structured。

 semistructured and unstructured data in their native format， classified and tagged with metadata。

 So while a data warehouse stores data processed for specific need。

 A data lake is a pool of raw data where each data element is given a unique identifier and is tagged with meta tags for further use。

 you would opt for a data lake if you generate or have access to large volumes of data on an ongoing basis。

 but don't want to be restricted to specific or predefined use cases。 Unlike data warehouses。

 a data lake would retain all source data without any exclusions。

 and the data could include all types of data sources and types。

 data lakes are sometimes also used as a staging area of a data warehouse。

 The most important role of a data lake is in predictive and advanced analytics。



![](img/42d08c4e20c8c2528630f2867eb67aaa_20.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_21.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_22.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_23.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_24.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_25.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_26.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_27.png)

Now， we come to the process that is at the heart of gaining value from data。 the extract。

 transform and load process or ETL。 ETL is how raw data is converted into analysis ready data。

 It is an automated process in which you gather raw data from identified sources。

 Ex the information that aligns with your reporting and analysis needs。 Clean。

 standardize and transform that data into a format that is usable in the context of your organization and load it into a data repository。

 While ETL is a generic process。 The actual job can be very different in usage。

 utility and complexity。 Extract is the step where data from source locations is collected for transformation。

 Data extraction could be through batch processing。

 meaningan source data is moved in large chunks from the source to the target system at scheduled intervals。

 To for batch processing include stitch and blendo。😊。



![](img/42d08c4e20c8c2528630f2867eb67aaa_29.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_30.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_31.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_32.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_33.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_34.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_35.png)

Stream processing， which means source data is pulled in real time from the source and transformed while it is in transit。

 And before it is loaded into the data repository， tools for stream processing include Apache Samsa。

 Apache storm and Apache Kafka Transform involves the execution of rules and functions that convert raw data into data that can be used for analysis。

 For example， making date formats and units of measurement consistent across all source data。

 Re duplicate data， filtering out data that you do not need， enriching data， for example。

 splitting full name to first middle and last names， establishing key relationships across tables。

 applying business rules and data validations。 load is the step where process data is transported to a destination system or data repository。

 It could be initial loading。 That is populating all the data in the repository。



![](img/42d08c4e20c8c2528630f2867eb67aaa_37.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_38.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_39.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_40.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_41.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_42.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_43.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_44.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_45.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_46.png)

Incremental loading， that is applying ongoing updates and modifications as needed periodically or full refresh。

 That is erasing contents of one or more tables and reloading with fresh data。 load verification。

 which includes data checks for missing or null values。

 Ser performance and monitoring load failures are important because of this process step。

 It is vital to keep an eye on load failures and ensure the right recovery mechanisms are in place。

 E T L has historically been used for batch workloads on a large scale。 However。

 with the emergence of streaming E TL tools， they are increasingly being used for real time streaming event data as well。

😊。

![](img/42d08c4e20c8c2528630f2867eb67aaa_48.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_49.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_50.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_51.png)

It's common to see the terms E TL and data pipelines used interchangeably。

 And although both move data from source to destination。

 data pipeline is a broader term that encompasses the entire journey of moving data from one system to another of which E TL is a subset。

 Data pipelines can be architected for batch processing for streaming data and a combination of batch and streaming data。

 in the case of streaming data， data processing or transformation happens in a continuous flow。

 This is particularly useful for data that needs constant updating， such as data from a sensor。

 monitoring traffic， a data pipeline is a highper system that supports both longrunning batch queries and smaller interactive queries。

 the destination for a data pipeline is typically a data lake。

 although the data may also be loaded to different target destinations。

 such as another application or a visualization tool。



![](img/42d08c4e20c8c2528630f2867eb67aaa_53.png)

There are a number of data pipeline solutions available。

 most popular among them being Apache beam and data flow。



![](img/42d08c4e20c8c2528630f2867eb67aaa_55.png)

![](img/42d08c4e20c8c2528630f2867eb67aaa_56.png)