# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P13：12_审计数据库活动.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/54e3341095c9bfa723201a7893ee52b2_0.png)

![](img/54e3341095c9bfa723201a7893ee52b2_1.png)

Welcome to Aiting Data activity After watching this video。

 you will be able to explain why auditing is important， describe how to audit database access。

 and describe how to audit database activity。

![](img/54e3341095c9bfa723201a7893ee52b2_3.png)

![](img/54e3341095c9bfa723201a7893ee52b2_4.png)

Auditing or monitoring database activity is a key part of any security plan。

 even though auditing doesn't directly protect the database。

 it can help you to identify gaps in your security system and to track errors in privilege administration。



![](img/54e3341095c9bfa723201a7893ee52b2_6.png)

![](img/54e3341095c9bfa723201a7893ee52b2_7.png)

![](img/54e3341095c9bfa723201a7893ee52b2_8.png)

In some industries and countries， it is even a requirement to audit access to sensitive data you should consider implementing auditing in all your database solutions。

 whether they be on premise or in the cloud Aing a database involves recording the access and the activity of database users on your database objects by reviewing such records also known as logs。

 you can identify suspicious activity and quickly respond to any security threats you find。



![](img/54e3341095c9bfa723201a7893ee52b2_10.png)

![](img/54e3341095c9bfa723201a7893ee52b2_11.png)

![](img/54e3341095c9bfa723201a7893ee52b2_12.png)

If an unauthorized user accesses your database， they have already overcome one or more of the levels of security in your system。

 Therefore it is imperative that you track who accesses your database and review the information to identify any unauthorized users you should also track failed attempts to access the database as these can help you to identify potential attacks such as brute force attempts on your system Most database systems provide functionality that you can use to audit database access For example。

 in DB2 on cloud， you can use the user validation category of the built-in audit facility to log user authentication events In my SQL。

 the audit log plugin tracks connect and disconnect events。



![](img/54e3341095c9bfa723201a7893ee52b2_14.png)

![](img/54e3341095c9bfa723201a7893ee52b2_15.png)

![](img/54e3341095c9bfa723201a7893ee52b2_16.png)

![](img/54e3341095c9bfa723201a7893ee52b2_17.png)

![](img/54e3341095c9bfa723201a7893ee52b2_18.png)

![](img/54e3341095c9bfa723201a7893ee52b2_19.png)

![](img/54e3341095c9bfa723201a7893ee52b2_20.png)

![](img/54e3341095c9bfa723201a7893ee52b2_21.png)

![](img/54e3341095c9bfa723201a7893ee52b2_22.png)

Sometimes authorized users may find that they can view and edit data that they should not have permissions on If you track all user activity。

 you can then use the output reports to review which users are accessing which tables and check whether those actions match your security plans to audit database activity some RDBMSSs use triggers These are special stored procedures that automatically log the activity after a DL statement event such as an insert occurs Other systems enable you to attach actions to the events that occur in the database in DB2 on cloud you can use the change history event monitor to enable auditing on specific tables or objects and in Postgres you can use the downloadable PG audit tool to log individual action types or all actions in a database you should ensure that whatever auditing implementation you use meets the compliance required。



![](img/54e3341095c9bfa723201a7893ee52b2_24.png)

![](img/54e3341095c9bfa723201a7893ee52b2_25.png)

![](img/54e3341095c9bfa723201a7893ee52b2_26.png)

![](img/54e3341095c9bfa723201a7893ee52b2_27.png)

![](img/54e3341095c9bfa723201a7893ee52b2_28.png)

![](img/54e3341095c9bfa723201a7893ee52b2_29.png)

![](img/54e3341095c9bfa723201a7893ee52b2_30.png)

![](img/54e3341095c9bfa723201a7893ee52b2_31.png)

![](img/54e3341095c9bfa723201a7893ee52b2_32.png)

![](img/54e3341095c9bfa723201a7893ee52b2_33.png)

![](img/54e3341095c9bfa723201a7893ee52b2_34.png)

![](img/54e3341095c9bfa723201a7893ee52b2_35.png)

Of your customer or region。In this video， you learned that auditing does not directly protect your database。

 but does identify gaps in your security， some industries。

 customers or regions may require that audit logs are created and retained。

 you should audit both successful and failed attempts to access your database。

 and you should audit and review all activity in your database。



![](img/54e3341095c9bfa723201a7893ee52b2_37.png)

![](img/54e3341095c9bfa723201a7893ee52b2_38.png)

![](img/54e3341095c9bfa723201a7893ee52b2_39.png)