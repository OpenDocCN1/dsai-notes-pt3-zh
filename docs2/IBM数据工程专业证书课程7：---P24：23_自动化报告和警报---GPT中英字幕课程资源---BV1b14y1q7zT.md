# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P24：23_自动化报告和警报.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/fafeb7c76e13c12a40a6153b1e93272d_0.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_1.png)

Welcome to Automating reports， notifications and alerts After watching this video you will be able to distinguish between reports。

 notifications and alerts， describe how DBAs use reports， notifications and alerts。

 identify some common alerts based on best practices， and explain some ways of automating reports。

 notifications and alerts。

![](img/fafeb7c76e13c12a40a6153b1e93272d_3.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_4.png)

Imagine you're a DbaA working for a small company and each week you need to give your bosses the status of the databases for which you are responsible How will you get that information and what should you include are DBMSss include reporting functionality that gives you insights into the health of your databases like the number of users connecting successfully or failing to connect the amount of space used and the rate of increase and the number of queries executed against the database you can create and configure reports with specific metrics to give you the information you need running reports on database health allows you to address issues before they become serious problems while allowing you to keep track of trends over time and help you to predict future needs and prepare for them you can automate reports to run daily。

 weekly or monthly depending on your needs。

![](img/fafeb7c76e13c12a40a6153b1e93272d_6.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_7.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_8.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_9.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_10.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_11.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_12.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_13.png)

In larger companies， an entire department may manage automated reports， while in smaller companies。

 a few DBAs or in some cases， only one DBA might perform that task。

 some companies use third party reporting tools that provide extra options and features。



![](img/fafeb7c76e13c12a40a6153b1e93272d_15.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_16.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_17.png)

Whereas reports give a regular overview of database health notifications are used when an issue should be tracked。

 but doesn't require your immediate attention。 Notifications give you the DBA an opportunity to track specific database events。

 you might choose to be notified when a user attempts to log in but fails。

 A few events like this are part of daily life as users forget or mistype their passwords。

 but a cluster of login failure notifications may indicate a malicious attempt to gain access to data you can receive automated notifications through SMS messages。

 email or via a dashboard you need to configure your preferred option。



![](img/fafeb7c76e13c12a40a6153b1e93272d_19.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_20.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_21.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_22.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_23.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_24.png)

Alerts quickly make you aware of issues that require your urgent attention。

 They are triggered by events like catastrophically low drive space or memory。

 schedule jobs that have failed too complete or error level events in the error log。

 you need to determine which alerts are appropriate for your environment and configure them to immediately reach the DBA on duty when configuring alerts and notifications。

 be careful not to set so many that you cannot respond to them all you should evaluate which ones are vital and configure them accordingly。



![](img/fafeb7c76e13c12a40a6153b1e93272d_26.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_27.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_28.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_29.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_30.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_31.png)

Alerts use two or more thresholds to help communicate the severity of an event。

 A warning threshold when the system sends a warning message and a critical threshold when the system sends a critical alert message。

 A best practice is to send out warning alerts when the threshold for the specified event reaches 85%。

 and a critical alert when the threshold reaches 95%。

 You can customize these values to suit your environment。



![](img/fafeb7c76e13c12a40a6153b1e93272d_33.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_34.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_35.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_36.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_37.png)

Now that you know a little about reports， notifications， and alerts。

 let's see how to automate these features。

![](img/fafeb7c76e13c12a40a6153b1e93272d_39.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_40.png)

Most RDBMSSs enable you to configure the content and frequency of reporting through a graphical interface。

 Many provide sample reports and enable you to configure your own if necessary notifications and alerts function similarly。

 and you can configure them through a graphical interface， a command line tool or a script。

 the process of automating reports， notifications and alerts varies depending on which RDBMS you are using。



![](img/fafeb7c76e13c12a40a6153b1e93272d_42.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_43.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_44.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_45.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_46.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_47.png)

In this video， you learned that reports give a regular overview of database health notifications give a forewarning of a situation that could become troublesome if not addressed。

 alerts bring awareness to an issue that needs immediate attention and DBAs automate reports。

 notifications and alerts to suit the needs of their environment。



![](img/fafeb7c76e13c12a40a6153b1e93272d_49.png)

![](img/fafeb7c76e13c12a40a6153b1e93272d_50.png)