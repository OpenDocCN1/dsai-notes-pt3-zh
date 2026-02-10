# IBM数据工程专业证书课程8：《使用Shell、Airflow和Kafka的ETL和数据管道课程（IBM）》｜etl-and-data-pipelines - P13：12_apache airflow 概述.zh_en - GPT中英字幕课程资源 - BV1Q94y1r7YG

![](img/5cb118c5edba878f11e5d6a6467cd3c2_0.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_1.png)

Welcome to Apache Airflow Over After watching this video。

 you will be able to recognize Apache Airflow as a platform to programmatically author。

 schedule and monitor workflows， list the main features and principles of Apache airflow and list common use cases for Apache airflow。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_3.png)

Apache Airflow is a great open source workflow orchestration tool that is supported by an active community it is a platform that lets you build and run workflows such as batch data pipelines with Apache airflow。

 a workflow is represented as a DAG a directed acyclic graph and contains individual pieces of work called tasks arranged with dependencies and note that unlike big data tools such as Apache Kafka。

 Apache Stor， Apache Spark or Flink， Apache airflow is not a data streaming solution it is primarily a workflow manager。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_5.png)

Let's take a look at a simplified overview of Apache Airflow's basic components Airflow comes with a builtin scheduler which handles the triggering of all scheduled workflows The scheduler is responsible for submitting individual tasks from each scheduled workflow to the executor The executor handles the running of these tasks by assigning them to workers which then run the tasks The web server serves airflow's powerful interactive user interface from this UI you can inspect trigger and debug any of your DAs and the individual tasks The DAG directory contains all of your DAg files。

 ready to be accessed by the scheduler， the executor and each of its employed workers Finally。

 Airflow hosts a metadata database which is used by the Schr executor and the web server to store the state of each dag and its tasks。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_7.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_8.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_9.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_10.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_11.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_12.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_13.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_14.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_15.png)

A dag specifies the dependencies between tasks and the order in which to execute them。

 The tasks themselves describe what to do In this example， Dg， the tasks include data ingestion。

 Data analysis， saving the data， generating reports and triggering other systems such as reporting any errors by email。

 Let's have a look at the lifecycle of a task state。 In this diagram。

 you can see how Apache airflow might assign states to a task during its lifecycle。 No status。

 The task has not yet been queued for execution Sch。

 the scheduler has determined that the task dependencies are met and has scheduled it to run removed for some reason。

 the task has vanished from the daAg since the run started。 upstream failed。

 an upstream task has failed。 queued。 the task has been assigned to the executor and is waiting for a worker to become available。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_17.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_18.png)

Running， the task is being run by a worker Su。 The task is finished running without errors， failed。

 The task had an error during execution and failed to run and up for retry。 the task failed。

 but has retry attempts left and will be rescheduled。Ideally。

 a task should flow through the scheduler from no status to scheduled。

 to queued to running and finally to success。Now let's have a look at the five main features and benefits of Apache airflow。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_20.png)

Pure Python create your workflows using standard Python This allows you to maintain full flexibility when building your data pipelines。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_22.png)

Useful UI， monitor， schedule and manage your workflows via a sophisticated web app offering you full insight into the status of your tasks Inegration Apache Airflow provides many plug and play integrations such as IBM Cloudant that are ready to execute your tasks。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_24.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_25.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_26.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_27.png)

Easy to use anyone with Python knowledgeled can deploy a workflow Airflow does not limit the scope of your pipelines。

 and finally， the open source feature whenever you want to share your improvement。

 you can do this by opening a pull request Airflow has many active users who are sharing their experiences in the Apache airflow community。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_29.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_30.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_31.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_32.png)

Apache airflow pipelines are built on four main principles。 They are scalable。

 Airflow has a modular architecture and uses a message queue to orchestrate an arbitrary number of workers It is ready to scale to infinity Dy airflow pipelines are defined in Python and allow dynamic pipeline generation。

 Thus your pipelines can contain multiple simultaneous tasks extensible you can easily define your own operators and extend libraries to suit your environment and lean airflow pipelines are lean and explicit Parameterization is built into its core using the powerful ginja templating engine。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_34.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_35.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_36.png)

Apache Airflow has supported many companies in reaching their goals， for example。

 Sft used airflow for defining and organizing machine learning pipeline dependencies SeniorLink increased the visibility of their batch processes and decoupled them Xperity deployed airflow as an enterprise scheduling tool and one football used airflow to orchestrate SQL transformations in their data warehouses and to send daily analytics emails。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_38.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_39.png)

In this video you learned that Apache Airflow is a platform to programmatically author。

 schedule and monitor workflows the five main features of airflow are its use of Python its intuitive and useful user interface。

 extensive plug and play integrations， ease of use and the fact that it is open source you also learn that Apache airflow is scalable。

 dynamic， extensible and lean and finally defining and organizing machine learning pipeline dependencies with Apache airflow is one of the common use cases。



![](img/5cb118c5edba878f11e5d6a6467cd3c2_41.png)

![](img/5cb118c5edba878f11e5d6a6467cd3c2_42.png)