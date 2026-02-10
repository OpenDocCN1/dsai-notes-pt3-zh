# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜big-data-with-spark-hadoop｜ - P31：30_apache spark 用户界面.zh_en - GPT中英字幕课程资源 - BV12h4y1D7hF

![](img/579e1be6bb83b9f34f911146c7647a62_0.png)

![](img/579e1be6bb83b9f34f911146c7647a62_1.png)

Welcome to the Apache Spark user interfaceface。

![](img/579e1be6bb83b9f34f911146c7647a62_3.png)

After watching this video， you'll be able to explain how to connect to the Apache Spark user interfaceface web server。

 navigate basic elements of the Spark user interface。When a Spk application is being run。

 as the driver program creates a spark context， Spark starts a web server that serves as the application user interface。

 You can connect to the UI web server by entering the host name of the driver。

 followed by port 4040 in a browser once the application is running。

 the web server runs for the duration of the Spar application。 So once the Spk context stops。

 the server shuts down and the application UI is no longer accessible。



![](img/579e1be6bb83b9f34f911146c7647a62_5.png)

![](img/579e1be6bb83b9f34f911146c7647a62_6.png)

![](img/579e1be6bb83b9f34f911146c7647a62_7.png)

![](img/579e1be6bb83b9f34f911146c7647a62_8.png)

The Spark user interface provides valuable insights organized on multiple tabs about the running application。

 The jobs tab displays the application's jobs， including job status。

 The stages tab reports the state of tasks within a stage the storage tab shows the size of any RDDs or data frames that persisted to memory or disk。

 The environment tab information includes any environment variables and system properties for Spar or the JVM。

 The executor tab displays a summary that shows memory and disk usage for any executors in use for the application。

 Additional tabs display based on the type of application in use。 For example。

 if the application performs SQL queries， the SQL tab displays and shows metrics for each query。😊。



![](img/579e1be6bb83b9f34f911146c7647a62_10.png)

![](img/579e1be6bb83b9f34f911146c7647a62_11.png)

![](img/579e1be6bb83b9f34f911146c7647a62_12.png)

Let's take a closer look at the jobs tab The top of the window displays the event timeline and shows when the driver and executor processes start and when the jobs are created In this example。

 the application has completed two jobs These two jobs appear in the list at the bottom which also has additional job related information such as duration number of stages and number of total tasks for all stages the job list also displays description hyperlinks to view the job details。



![](img/579e1be6bb83b9f34f911146c7647a62_14.png)

![](img/579e1be6bb83b9f34f911146c7647a62_15.png)

![](img/579e1be6bb83b9f34f911146c7647a62_16.png)

![](img/579e1be6bb83b9f34f911146c7647a62_17.png)

![](img/579e1be6bb83b9f34f911146c7647a62_18.png)

![](img/579e1be6bb83b9f34f911146c7647a62_19.png)

Now let's view job details for information about the different stages of a specific job。

 The timeline displays each stage where you can quickly see the job's timing and duration below the timeline display。

 you'll see completed stages in the parentheses beside the heading you'll see a quick view that displays the number of completed stages then view the list of stages within the job and job metrics。

 including when the job was submitted input output sizes。

 the number of attempted tasks the number of succeeded tasks and how much data was read or written because of a shuffle This example shows two stages separated by a shuffle So stage1 wrote shuffle data and stage two read that data to view more details about a specific stage within a job click the stage ID description hyperlinks。



![](img/579e1be6bb83b9f34f911146c7647a62_21.png)

![](img/579e1be6bb83b9f34f911146c7647a62_22.png)

![](img/579e1be6bb83b9f34f911146c7647a62_23.png)

![](img/579e1be6bb83b9f34f911146c7647a62_24.png)

![](img/579e1be6bb83b9f34f911146c7647a62_25.png)

![](img/579e1be6bb83b9f34f911146c7647a62_26.png)

![](img/579e1be6bb83b9f34f911146c7647a62_27.png)

![](img/579e1be6bb83b9f34f911146c7647a62_28.png)

![](img/579e1be6bb83b9f34f911146c7647a62_29.png)

![](img/579e1be6bb83b9f34f911146c7647a62_30.png)

The stages tab shows a list of all stages in the application grouped by the current state of either completed。

 active or pending。 This example displays three completed stages。

 Click the stage ID D description hyperlinks to view task details for that stage。😊。



![](img/579e1be6bb83b9f34f911146c7647a62_32.png)

![](img/579e1be6bb83b9f34f911146c7647a62_33.png)

![](img/579e1be6bb83b9f34f911146c7647a62_34.png)

The storage tab displays details about RDDs that have been cached or persisted to memory and or written to disk。

 This example image shows one RDD that's been cached to memory only。



![](img/579e1be6bb83b9f34f911146c7647a62_36.png)

![](img/579e1be6bb83b9f34f911146c7647a62_37.png)

![](img/579e1be6bb83b9f34f911146c7647a62_38.png)

The Enviment tab has several lists to describe the environment of the running application。

 These lists include the spark configuration properties and resource profiles。

 as well as properties for Hadoop and the current system properties。



![](img/579e1be6bb83b9f34f911146c7647a62_40.png)

![](img/579e1be6bb83b9f34f911146c7647a62_41.png)

The Executors tab displays a summary table at the top that shows metrics on all active or dead executors。

 along with a full range of metrics on the task numbers， data IO。

 disk and memory usage at the bottom is a list of all executors。

 including the driver that have been in use during the application again with a full range of metrics This list also provide links to the STD out and STD error log messages of the executor process。



![](img/579e1be6bb83b9f34f911146c7647a62_43.png)

![](img/579e1be6bb83b9f34f911146c7647a62_44.png)

If the application runs SQL queries， the UI displays and populates the SQL tab。

 click the SQL description hyperlink to display thequeries's details。



![](img/579e1be6bb83b9f34f911146c7647a62_46.png)

![](img/579e1be6bb83b9f34f911146c7647a62_47.png)

You can view the SQL query plan when you click the De Exper arrow。



![](img/579e1be6bb83b9f34f911146c7647a62_49.png)

You can also view the Queery's DAG， including the logical physical plans as determined by the optimizer。



![](img/579e1be6bb83b9f34f911146c7647a62_51.png)

![](img/579e1be6bb83b9f34f911146c7647a62_52.png)

In this video you learned that the Jobs tab displays the applications's jobs。

 including jobs status and the stages tab reports the state of tasks within a stage the storage tab shows the size of RDDs or data frames that persisted to memory or disk。

 the environment tab information includes any environment variables and system properties for Spark or the JVM The Executors tab displays a summary that shows memory and disk usage for any executors in use If the application runs SQL queries。

 select a SQL tab and the description hyperlink to display the queries's details。



![](img/579e1be6bb83b9f34f911146c7647a62_54.png)

![](img/579e1be6bb83b9f34f911146c7647a62_55.png)