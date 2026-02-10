# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜big-data-with-spark-hadoop｜ - P32：31_监控应用程序进度.zh_en - GPT中英字幕课程资源 - BV12h4y1D7hF

![](img/ab1668f01de5f7f75f10794c27ec57ec_0.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_1.png)

Welcome to Monit A Progress。

![](img/ab1668f01de5f7f75f10794c27ec57ec_3.png)

After watching this video， you'll be able to define parts of the application workflow。

 utilize the UI web server to monitor application progress， describe a sample workflow from the UI。



![](img/ab1668f01de5f7f75f10794c27ec57ec_5.png)

Running a Sp application can sometimes take a long time and have many possible points of failure When an issue arises。

 say a faulty worker node is causing the occasional task to fail。

 It is essential to find and address the problem quickly so that cluster resources do not stay idle。

 The Spar application UI is a great way to monitor a running application。

 The application UI centralizes critical information。

 including status information and organizes information logically。

 resulting in convenient and fast access。 You can quickly identify failures。

 then drill down to the lowest levels of the application to find out the root causes of failures。

 Besides failures， the UI can also help you quickly locate and analyze application processing bottlenecks。



![](img/ab1668f01de5f7f75f10794c27ec57ec_7.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_8.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_9.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_10.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_11.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_12.png)

A Spk application can consist of many parallel and often related jobs。

 including multiple jobs resulting from multiple data sources， multiple data frames。

 and the actions applied to the data frames， workflows can include jobs created by the Spar context in the driver program。

 jobs in progress running as tasks in the executors and completed jobs transferring results back to the driver or writing to disk。



![](img/ab1668f01de5f7f75f10794c27ec57ec_14.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_15.png)

First， spark jobs divide into stages which connect as a directed ascyclic graph or dag tasksask for the current stage are scheduled on the cluster。

 When the stage completes all of its tasks， the next dependent stage in the Dg begins。

 the job progresses through the dag。 all stages are completed。

 If any of the tasks within a stage fail After several attempts。

 Spark marks the task stage and job as failed and stops the application。



![](img/ab1668f01de5f7f75f10794c27ec57ec_17.png)

Let's look at an example， the application first creates a job。



![](img/ab1668f01de5f7f75f10794c27ec57ec_19.png)

Next， Spk divides the job into one or more stages。 The first stage stage 0 has no dependencies。

 so Spark sends its tasks to the executors。

![](img/ab1668f01de5f7f75f10794c27ec57ec_21.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_22.png)

Stage 0 now has two tasks started。 The width of the task indicates the elapsed run time。



![](img/ab1668f01de5f7f75f10794c27ec57ec_24.png)

Two more tasks that are dependent on zero and1 run。

 but do not require a shuffle such as map operations， for example。

 so they remain part of stage  zero and run independently。



![](img/ab1668f01de5f7f75f10794c27ec57ec_26.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_27.png)

The end of stage 0 now marks the beginning of the next stage 1。

 This boundary exists because a shuffle was required。

 which means that all tasks for stage 1 must wait for all tasks in stage 0 to finish before starting。



![](img/ab1668f01de5f7f75f10794c27ec57ec_29.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_30.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_31.png)

Here you can see that tasks 4 and 5 have different run times。

 Their runtime differ because each task is running independently and on different data partitions。

 However， the stage is not complete until all tasks have finished。



![](img/ab1668f01de5f7f75f10794c27ec57ec_33.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_34.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_35.png)

With this job completed， Spark can begin a new job in this example。

 job one depends on the data from job zero。

![](img/ab1668f01de5f7f75f10794c27ec57ec_37.png)

The next job consists of one stage and starts tasks six and7。



![](img/ab1668f01de5f7f75f10794c27ec57ec_39.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_40.png)

Since tasks within a stage can run independently， when taskask 7 completes。

 the executor running taskask7 can immediately start taskask 8 while taskask 6 continues to run when the application completes tasks 8 and9。

 the stage and job are complete， marking the end of this application workflow。



![](img/ab1668f01de5f7f75f10794c27ec57ec_42.png)

Next view this example application to see how the code translates to a workflow you can monitor using the UI This application's single data source is a parquet file loaded from disk to produce a data frame using that same data frame two columns are selected。

 the caching action is specific to this example the application groups the data by the country column and then aggregates the data by calculating the mean of the salary column Next。

 the collect action runs this action triggers the job creation and schedules the tasks as the previous operations are all lazily computed。



![](img/ab1668f01de5f7f75f10794c27ec57ec_44.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_45.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_46.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_47.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_48.png)

After you submit the application， start the Spark application UI and view the Jobs tab。

 which displays two jobs， one job reads the parquet file from disk。

 the second job is the result of the action to collect the grouped aggregate computations to send to the driver。



![](img/ab1668f01de5f7f75f10794c27ec57ec_50.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_51.png)

On the Jobs tab， click a specific job to display its job details page Here you can see the number of stages and the DAg that links the stages。

 This example has two stages connected by a shuffle exchange which is due to grouping the data by country in the application。



![](img/ab1668f01de5f7f75f10794c27ec57ec_53.png)

Select a stage to view the tasks， the stage details timeline indicates each task's state using color coding。

 view the timeline to see when each task was started and the task's duration Use this information to quickly locate failed tasks。

 see which tasks are taking a long time to run and determine how well your application is parallelized。



![](img/ab1668f01de5f7f75f10794c27ec57ec_55.png)

The task list provides even more metrics， including status。

 duration and amount of data transferred as part of a shuffle here you see two tasks that read one and two records as part of a shuffle you see these two tasks because by default for a shuffle spark repartitions the data into a larger number of partitions you can also access a task's executor logs the data used in this example is small Therefore many tasks only have a small number of records to process。



![](img/ab1668f01de5f7f75f10794c27ec57ec_57.png)

When all application jobs are complete and the results are sent to the driver or written to disk。

 the Spk context can be stopped either manually or automatically when the application exits when the application UI server shuts down the UI is no longer available to view the application UI after the application stops。

 Even logging must be enabled， this means that all events in the application workflow are logged to a file and the UI can be viewed with the Spark history server。



![](img/ab1668f01de5f7f75f10794c27ec57ec_59.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_60.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_61.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_62.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_63.png)

To view the application UI with the history server， first verify that event logging is enabled。

 enter the event log path as seen using the properties displayed on screen before submitting the application When the application completes the application UI populates the log files in the event log directory to start the history server apply the command shown on screen Once the history server is started。

 connect to the history server by typing the history server hosts URL followed by the default port number 18080 you can see a list of completed applications and select1 to view its application UI。



![](img/ab1668f01de5f7f75f10794c27ec57ec_65.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_66.png)

![](img/ab1668f01de5f7f75f10794c27ec57ec_67.png)

In this video， you learned that the Spk application workflow includes jobs created by the Spark context in the driver program。

 jobs in progress running as tasks in the executors and completed jobs transferring results back to the driver or writing to disk The Spark application UI centralizes critical information。

 including status information。 you can quickly identify failures。

 then drill down to the lowest levels of the application to discover their root causes。



![](img/ab1668f01de5f7f75f10794c27ec57ec_69.png)