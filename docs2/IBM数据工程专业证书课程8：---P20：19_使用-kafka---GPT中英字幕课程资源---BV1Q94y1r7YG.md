# IBM数据工程专业证书课程8：《使用Shell、Airflow和Kafka的ETL和数据管道课程（IBM）》｜etl-and-data-pipelines - P20：19_使用 kafka 构建事件流水线.zh_en - GPT中英字幕课程资源 - BV1Q94y1r7YG

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_0.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_1.png)

Welcome to Build Even streaming pipelines using Kafka After watching this video。

 you will be able to describe the core components of Kafka。

 use Kafka to publish or write and subscribe or read streams of events。

 use Kafka to consume events either as they occur or retrospectively。

 and describe an end to end event streaming pipeline example。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_3.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_4.png)

A Kafka cluster contains one or many brokers You may think of a Kafka broker as a dedicated server to receive store。

 process and distribute events Brokers are synchronized and managed by another dedicated server called Zookeeper For example。

 here we have a log topic and a transaction topic in Bro zero。

 a payment topic and a GPS topic in Bro 1 and a user click topic and a user search topic in Bro2 Each broker contains one or many topics you can think of a topic as a database to store specific types of events such as logs。

 transactions and metrics， for example。

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_6.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_7.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_8.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_9.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_10.png)

Brokers managed to save published events into topics and distribute the events to subscribed consumers。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_12.png)

Like many other distribution systems， Kafka implements the concepts of partitioning and replicating it uses topic partitions and replications to increase fault tolerance and throughput so that event publication and consumption can be done in parallel and with multiple brokers In addition。

 even if some brokers are down， Kafka clients are still able to work with the target topics replicated in other working brokers for example。

 a log topic has been separated into two partitions01 and a user topic has been separated into two partitions01 and each topic partition is duplicated into two replications and stored in different brokers。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_14.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_15.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_16.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_17.png)

The Kafka CLI or command line interface client provides a collection of powerful script files for users to build an event streaming pipeline The Kafka Top script is the one you will probably be using often to manage topics in a Kafka cluster。

 it is straightforward。

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_19.png)

Let's have a look at some common usages The first one is to create a topic here we are trying to create a topic called log underscore topic with two partitions and two replications One important note here is that many Kafka commands like Kaf topics require users to refer to a running Kafka cluster with a host and a port such as a local host with a port 9092。

After you have created some topics， you can check all created topics in the cluster using the list option。

 and if you want to check more details of a topic such as partitions and replications。

 you can use theDe option and you can delete a topic using the De option Next you will find out more about publishing events using Kafka producers。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_21.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_22.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_23.png)

Features of a Kafka producer。They are client applications that publish events to topic Partitions according to the same order as they are published when publishing an event in Kafka producer。

 an event can be optionally associated with a key， events associated with the same key will be published to the same topic partition and events not associated with any key will be published to topic partitions in rotation。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_25.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_26.png)

Let's see how you can publish events to topic Partitions using the following example。

 Sose you have an event So one which generates various log entries and an event source2 which generates user activity tracking records。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_28.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_29.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_30.png)

Then you can create a Kafka producer to publish log records to log topic Partitions and a user producer to publish user activity events to user topic partitions respectively when you publish events in producers。

 you can choose to associate events with a key， for example， an application name or a user ID。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_32.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_33.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_34.png)

Similar to the Kafka topic CLI， Kafka provides the Kafka producer CLI for users to manage producers The most important aspect is starting a producer to write or publish events to a topic here you start a producer and point it to the log topic then you can type some messages in the console to start publishing events For example。

 Lo1， Lo2 and log3 you can provide keys to events to make sure that the events with the same key will go to the same partition。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_36.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_37.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_38.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_39.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_40.png)

Here you are starting a producer to user topic with the Parse do key option to be true。

 and you also specify the key separator to become comma， then you can write messages as follows。

 key Use one value login website， key Use one value。

 click the top item and key Use one value logout website。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_42.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_43.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_44.png)

Accordingly， all events about userr One will be saved in the same partition to facilitate the reading for consumers。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_46.png)

Once events are published and properly stored in topic partitions。

 you can create consumers to read them。 Consumer are client applications that can subscribe to topics and read the stored events。

 Then event destinations can further read events from Kafka consumers。

 Consumer read data from topic partitions in the same order as they are published。

 Consumer also store an offset of each topic partition as the last red position with the offset。

 consumers are guaranteed to read events as they occur。

 A playback is also possible by resetting the offset to zero。 This way。

 the consumer can read all events in the topic partition from the beginning。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_48.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_49.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_50.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_51.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_52.png)

In Kafka， producers and consumers are fully decoupled， as such。

 producers don't need to synchronize with consumers and after events are stored in topics。

 consumers can have independent schedules to consume them。

To read published log and user events from topic Partitions。

 you'll need to create log and user consumers and make them subscribe to corresponding topics。

 then Kafka will push the events to those subscribed consumers and then the consumers will further send to event destinations。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_54.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_55.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_56.png)

To start a consumer is also easy using the Kafka consumer script。

 Let's read events from the log topic you just need to run the Kafka console consumer script and specify a Kafka cluster and the topic to subscribe to here you can subscribe to and read events from the topic log_ topic Then the started consumer will read only the new events starting from the last Partition Off after those events are consumed the partition Off for the consumer will also be updated and committed back to Kafka。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_58.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_59.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_60.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_61.png)

Very often， a user wants to read all events from the beginning as a playback of all historical events To do so。

 you just need to add the from beginning option。Now you can read all events starting from offset zero。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_63.png)

Let's have a look at a more concrete example to help you understand how to build an event streaming pipeline and to end Sose you want to collect and analyze weather and Twitter event streams so that you can correlate how people talk about extreme weather on Twitter here you can use two event sources IBM weatherath API to obtain realtime and forecasted weather data in JO format and Twitter API to obtain real-time tweets and mentions also in JO format。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_65.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_66.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_67.png)

To receive weather and Twitter Jason data in Kafka。

 you then create a weather topic and a Twitter topic and a Kafka cluster with some partitions and replications to publish weather and Twitter Jason data to the two topics you need to create a weather producer and a Twitter producer the events Jason data will be serialized into bytes and saved in Kafka topics to read events from the two topics you need to create a weather consumer and a Twitter consumer the bytes stored in Kafka topics will be decsialized into event Jason data If you now want to transport the weather and Twitter event Jason data from the consumer to a relational database youll use a DB writer to parse those Jason files and create database records and then you can write those records into a database using SQL insert statements。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_69.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_70.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_71.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_72.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_73.png)

Finally， you can query the database records from the relational database and visualize and analyze them in a dashboard to complete the end to end pipeline。

In this video， you learned that the core components of Kafka are brokers。

 the dedicated server to receive store process and distribute events， topics。

 the containers or databases of events， Partitions divide topics into different brokers。

 Replication duplicate Partitions into different brokers producers。

 Kafka clientient applications to publish events into topics， and consumers。

 Kafka clientient applications subscribe to topics and read events from them you also learned the Kafka Top CLI manages topics the Kafka Con producer CLI manages producers。

 and finally the Kafka Con consumer manages consumers。



![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_75.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_76.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_77.png)

![](img/2c3ac98b8f3916b5304dc58cd1f61e9e_78.png)