# IBM数据工程专业证书课程8：《使用Shell、Airflow和Kafka的ETL和数据管道课程（IBM）》｜etl-and-data-pipelines - P19：18_apache kafka 概述.zh_en - GPT中英字幕课程资源 - BV1Q94y1r7YG

![](img/4dc74382eaf58e24a15339393c5f675c_0.png)

Welcome to Apache Kafka Over After watching this video。

 you will be able to recognize Apache Kafka as an event streaming platform or ESP。

 describe the architecture of Apache Kafka， list common use cases for Apache Kafka。

 summarize the main features and benefits of Apache Kafka。

 and list popular Kafka based ESP as a service providers。By now。

 you should be able to describe what an event streaming platform and its core components are。

 and may think that it must be extremely difficult to implement an ESP from scratch， that is true。

 but we already have many great open source and commercial ESP solutions available that come with many built-in capabilities among these Apache Kafka。

 an open source project has probably the most popular event streaming platform。

Kafka is a comprehensive platform and can be used in many application scenarios Let's look at some of the common ones here。

Kafka was originally used to track user activities such as keyboard strokes， mouse clicks。

 page views， searches， gestures， screen time and so on。

 but now it is also suitable for all kinds of metric streaming such as sensor readings， GPS。

 as well as hardware and software monitoring for enterprise applications and infrastructure with a huge number of logs。

 Kafka can be used to collect and integrate them into a centralized repository for banks。

 insurance or fintech companies， Kafka is also widely used for payments and transactions。

These scenarios are just the tip of the iceberg， you basically can use Kafka in scenarios when you want high throughput and reliable data transportation services among various events sources and destinations all of these events will be ingested in Kafka and become available for subscriptions and consumption。

 including further data storage and movement to other online and offline databases and backups。

 real-time processing and analytics including dashboard， machine learning， AI algorithms and so on。

 generating notifications such as email， text messages and instant messages。

 or data governance and auditing to make sure sensitive data such as bank transactions are complying with regulations。

Kafka has a distributed client server architecture for the server side。

 Kafka is a cluster with many associated servers called brokers。

 acting as the event broker to receive， store and distribute events All those brokers are managed by another distributed system called zookeeper to ensure all brokers work in an efficient and collaborative way。

Kafka uses a TCP or transmission control protocol based network communication protocol to exchange data between clients and servers For the client side。

 Kafka provides different types of clients such as Kafka CLI command line interface。

 which is a collection of Shell scripts to communicate with the Kafka server。

 many high-level programming APIs such as Java， Scala。

 RE APIs and some specific thirdpart clients made by the Kafka community According you could choose different clients based on your requirements。

Now that you have a basic understanding of Kafka， let's see why Apache Kafka has become such a popular ESP Kafka has the following main features。

 it is a distribution system which makes it highly scalable to handle high data throughput and concurrency。

A Kafka cluster normally has multiple event brokers which can handle events streaming in parallel and as such。

 Kafka is very fast and highly scalable Kafka also divides event storage into multiple partitions and replications which makes it fault tolerant and highly reliable Kafka stores the events permanently。

 as such event consumption could be done whenever suitable for consumers without a deadline and Kafka is open source。

 meaning that you can use it for free and even customize it based on your specific requirements。

Even though Kafka is open source and well documented。

 it is still challenging to configure and deploy a Kafka without professional assistance Deing a Kafka cluster requires extensive efforts for tuning infrastructure and consistently adjusting the configurations especially for enterprise levelve deployments Fortunatelyly。

 several commercial service providers offering an on-ded ESP as a service to meet your streaming requirements。

 Many of them are built on top of Kafka and provide added value for customers some well-known ESP providers include confluent cloud。

 which provides customers with fully managed Kafka services either on- premises or on cloud IBM event streams。

 which is also based on Kafka and provides many addon services such as enterprise grade security disaster recovery and 247 cluster monitoring and Amazon managed streaming for Apache Kafka which is。

Also a fully managed service to facilitate the build and deployment of Kafka。In this video。

 you learned that Apache Kafka is one of the most popular open source ESPs Common Kafka use cases include user activity tracking。

 metrics and logs integrations and financial transaction processing Apache Kafka is a highly scalable and reliable platform that stores events permanently。

 and finally， popular Kafka based ESP service providers include confluent cloud IBM event streams and Amazon managed streaming。



![](img/4dc74382eaf58e24a15339393c5f675c_2.png)