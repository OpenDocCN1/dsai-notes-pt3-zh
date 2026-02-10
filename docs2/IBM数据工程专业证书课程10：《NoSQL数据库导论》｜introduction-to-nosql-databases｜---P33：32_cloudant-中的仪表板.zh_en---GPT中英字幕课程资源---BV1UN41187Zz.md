# IBM数据工程专业证书课程10：《NoSQL数据库导论》｜introduction-to-nosql-databases｜ - P33：32_cloudant 中的仪表板.zh_en - GPT中英字幕课程资源 - BV1UN41187Zz

![](img/19ce025cbd033ff0cb29d1aed5d2e772_0.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_1.png)

Welcome to Dashboards in Cloudant After watching this video。

 you will be able to access the Cloudon dashboard， describe the different elements that can be managed in the Cloudon dashboard。

 and use the Cloudon dashashboard to manage a Cloudant service instance。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_3.png)

After you sign up for a free Cloudant account and then log in。

 you will be taken to your resource list in the IBM Cloud dashboard in the resource list。

 you expand the services list and select the name of your Cloudant service instance on the Man tab。

 select Laun dashashboard to open your Cloudant dashashboard。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_5.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_6.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_7.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_8.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_9.png)

The dashashboard in Cloudant is a centralized administrative interface that enables you to create and manage your databases。

 configure replication， view active tasks， and monitor current operations denied requests and storage consumption。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_11.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_12.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_13.png)

In the database tab of the dashboard， you can create databases， and documents to a database。

 replicate a database， configurefi permissions for a database。

 delete a database and run queries on documents in a database。

 You use the replication tab of the cloud and dashboard to configure replication between source and target databases。

 When you perform a replication operation， it copies all changes from the source database to the target database。

 For example， if you add a document to or delete a document from the source database after replication completes。

 that document will also be added to or deleted from the target database。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_15.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_16.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_17.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_18.png)

When you configure replication， you need to specify several elements such as the source and target databases。

 the authentication used for the connection and the replication type replication types are either one time。

 which means replication occurs once immediately after replication is configured。

 but it does not continue to replicate after that time， which is the default replication setting。

 alternatively， you can configure replication to use the continuous type of replication where changes in the source database are replicated to the target database persistently until you specifically decide to cancel replication。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_20.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_21.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_22.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_23.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_24.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_25.png)

Replications can have a huge impact on the performance of your cloud and instance。

 so it is recommended to carry out some form of performance testing to identify any potential impact on your cloud and environment。

 Furthermore， if you configure the continuous type of replication in your environment。

 Then obviously， that potential impact will be constant。 Additionally。

 the extra system calls required to perform continuous replication will likely increase the cost to an organization running multi tenantant instances of IBM cloudant。

 This is why continuous replication is not enabled by default。Once replication has started。

 you can use refresh to update the state to identify when replication has completed When you go back to your databases tab。

 you will see any replicated databases in the list。

 You can use the active tasks tab of the cloudin dashboard to show a list of any tasks that are currently running。

 which may assist you in determining any issues you may have with system performance。

 The list of active tasks includes replication， compaction and indexing processes。

 You use the monitoring tab of the cloudon dashboard to view the consumption of provisioned throughput capacity and data storage currently being utilized by your applications in your cloudant instance。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_27.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_28.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_29.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_30.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_31.png)

On the three tabs available in the monitoring section， you can monitor current operations。

 These graphs show minute by minute consumption of your provisioned throughput capacity。

 This throughput capacity is broken up into reads per second。

 writes per second and global queries per second。 The dotted lines indicate the peak capacity limit allowed by your cloud and instance。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_33.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_34.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_35.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_36.png)

In your hands on labs， you will be using the light plan and therefore will not see any data in these graphs on this page as displayed in the screenshot on the left。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_38.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_39.png)

The screenshot on the right shows you an example of what the graphs might look like in a production environment。

Denied requests。 These graphs display minute by minute monitoring of received。

 denied request responses。 These responses are generated as 4，2，9， too many requests， messages。

 and they occur when the provisioned throughput capacity limit for a cloud instance is exceeded。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_41.png)

As in theCurrent operations tab， these denied requests are broken up into readTs per second。

 rights per second， and global queries per second。The storage graphs display a color coded daily record of the current storage capacity used by four elements of your cloud and instance。

 namely geospatial indexes， search indexes， views， and databases。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_43.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_44.png)

The first screenshot is currently only displaying information for the databases element。

 You can select each colored bar above the graph to toggle the display of each element on or off。

 The second screenshot is configured to display information for all four elements。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_46.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_47.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_48.png)

You can use the information displayed in these graphs to help you determine when capacity is being reached for an element of your cloud and instance in case you need to modify your capacity settings。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_50.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_51.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_52.png)

In this video， you learned that you use the Cloudant dashashboard to create and manage databases。

 configure replication， view active tasks， and monitor your cloudant instances。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_54.png)

![](img/19ce025cbd033ff0cb29d1aed5d2e772_55.png)

You use the databases section of the dashboard to create databases， add documents to databases。

 replicate databases， configure permissions for databases。

 delete databases and run queries on documents in databases。

 You use the replication section of the dashboard to configure replication between source and target databases。

 you use the view Act tasks section of the dashboard to view a list of currently running tasks to assist you in determining any issues with system performance。

And finally， you use the monitoring section of the dashboard to view the consumption of provision throughput capacity and data storage currently being utilized in your Cloud and instance。



![](img/19ce025cbd033ff0cb29d1aed5d2e772_57.png)