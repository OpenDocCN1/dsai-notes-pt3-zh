# IBM数据工程专业证书课程8：《使用Shell、Airflow和Kafka的ETL和数据管道课程（IBM）》｜etl-and-data-pipelines - P21：20_kafka 流程.zh_en - GPT中英字幕课程资源 - BV1Q94y1r7YG

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_0.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_1.png)

Welcome to Kafka Sting process After watching this video。

 you will be able to describe what the Kafka Streams API is and its main benefits。

 as well as describe what the Kafka streamream processing topology is。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_3.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_4.png)

In event streaming， in addition to transporting data。

 data engineers also need to process data through， for example， data filtering。

 aggregation and enhancement any applications developed to process streams are called stream processing applications。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_6.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_7.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_8.png)

F stream processing applications based on Kafka， a straightforward way is to implement an ad hoc data processor to read events from one topic。

 process them， and publish them to another topic Let's look at an example you first request rawwe JO data from a weather API and you start a weather producer to publish the raw data into a raw weather topic then you start a consumer to read the rawwe data from the weather topic。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_10.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_11.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_12.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_13.png)

Next， you create an ad hoc data processor to filter the raw weather data to only include extreme weather events such as very high temperatures。

 such a processor could be a simple script file or an application which works with Kafka clients to read and write data from Kafka Afterwards。

 the processor sends the processed data to another producer and it gets published to a processed weather topic and finally the processed weather data will be consumed by a dedicated consumer and sent to a dashboard for visualization。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_15.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_16.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_17.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_18.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_19.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_20.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_21.png)

Such ad hoc processors may become complicated if you have many different topics to be processed。

 a solution that may solve these challenges is Kafka。

 it provides the streams API to facilitate stream processing。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_23.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_24.png)

Kafka Streams API is a simple client library aiming to facilitate data processing in event streaming pipelines。

 it processes and analyzes data stored in Kafka topics。

 thus both the input and output of the streamams API are Kafka topics Additionally。

 Kafka Streams API ensures that each record will only be processed once。

 and finally it processes only one record at a time。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_26.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_27.png)

KafkaStream's API is based on a computational graph called a stream processing topology In this topology。

 each node is a stream processor which receives streams from its upstream processor。

 performs data transformations such as mapping， filtering formatting and aggregation and produces output streams to its downstream stream processors。

 thus the edges of the graph are the IO streams。

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_29.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_30.png)

There are two special types of processors On the left， you can see the source processor。

 which has no upstream processors。 A source processor acts like a consumer which consumes streams from Kafka topics and forwards the process streams to its downstream processors。

 On the right， you can see the sync processor， which has no downstream processors。

 A sync processor acts like a producer which publishes the received stream to a Kafka topic。

Let's redesign the previous weatherath streamre processing application with Kafka Streams API Sose you have a raw weather topic and a processed weather topic in Kafka Now。

 instead of spending a huge amount of effort developing an ad hoc processor。

 you could just plug in the Kafka streamreams API here。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_32.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_33.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_34.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_35.png)

In the Kafka Stres topology， we have three stream processors。

 the source processor that consumes raw weather streams from the raw weather topic。

 and forwards the weather stream to the stream processor to filter the stream based on high temperature。

 then the filtered stream will be forwarded to the sink processor。

 which then publishes the output to the processed weather topic。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_37.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_38.png)

![](img/a990128cb0be1d7c3c0fb69bd6b2da68_39.png)

Concluding， this is a much simpler design than an ad hoc data processor。

 especially if you have many different topics to be processed。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_41.png)

In this video， you learned that the Kafka Streams API is a simple client library to help data engineers with data processing in event streaming pipelines a stream processor receives transforms and forwards the streams Kafka Streams API is based on a computational graph called a stream Pro topology and in the topology each node is a stream processor well edges are the IO streams。

 and finally in this topology we find two special types of processors the source processor and the Snc processor。



![](img/a990128cb0be1d7c3c0fb69bd6b2da68_43.png)