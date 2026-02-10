# IBM数据工程专业证书课程7：《关系数据库管理（DBA）》｜relational-database-administration｜ - P8：7_备份策略.zh_en - GPT中英字幕课程资源 - BV1b14y1q7zT

![](img/3e9f971919422bbb1008eeb378e7cc61_0.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_1.png)

Welcome to backup policies。 After watching this video。

 you will be able to explain the difference between hot and cold backups and determine an appropriate backup policy。

 Ho backups or online backups or those performed on data when it is in use。

 The advantage of hot backups is that they have no impact on availability and users can continue with their activities throughout the backup period。

 However， hot backups can result in performance degradation for users while the backup is running and can impact data integrity if data changes during the backup process。

 The alternative to hot backups is to take the data offline while the backup is run。

 This is known as a cold or offline backups。 This eliminates the data integrity risks associated with hot backups。

 but has a greater impact on user availability and cannot be used in 24，7 environments。

 Ho backups are generally stored。😊。

![](img/3e9f971919422bbb1008eeb378e7cc61_3.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_4.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_5.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_6.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_7.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_8.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_9.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_10.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_11.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_12.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_13.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_14.png)

On an available server and often receive regular updates from the production database。

 This enables them to be brought online。 should the production server fail to ensure continuing availability to users。

 Col backups tend to be stored on external drives or on servers that are shut down between backup operations。

 This can provide greater data safety， but does mean that the recovery process will take longer than that of a hot backup。

 You have already seen that there are many decisions that you must make about how to implement your backup and restore policy。

 physical or logical backups， type of backup， Ho or cold backup， compression and encryption。

 You also need to consider how often you need to backup your data。

 This is dependent on the impact that any data loss would have on your business operations and how frequently your data is changing。

 For example， a table containing product information is likely to change less。



![](img/3e9f971919422bbb1008eeb378e7cc61_16.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_17.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_18.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_19.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_20.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_21.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_22.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_23.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_24.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_25.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_26.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_27.png)

ly than a table containing customer orders so you could back that up less regularly than the orders table。

 but if your orders table already contains a large amount of data。

 you won't want to be performing frequent full backups。

 so you should consider using differential or incremental backups for it。

 You also need to consider when to perform your backups。

 if your data is mainly accessed during the working day in one time zone。

 you should schedule your backup outside of those hours。 However。

 if it is accessed across the whole day， you could consider implementing full backups at the weekend and incremental or differential backups on a daily basis。

 because backups will be a regular task if your RDBm provides the availability to schedule or automate your backups。

 you should consider using it It is equally important to consider backing up your cloud databases。

 depending on the RDBMS that you are using。

![](img/3e9f971919422bbb1008eeb378e7cc61_29.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_30.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_31.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_32.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_33.png)

Backups might run automatically。 you may need to enable automated backups。

 You may need to run manual backups， or you may be able to use the techniques that you have learned about in this video to run your own backup strategy For example。

 the paid plans of Db2 on cloud run an encrypted backup every day and with the enterprise or standard plans。

 you can also run manual backups and perform point in time restores and when using Google Cloud Sql from my Sql Postgres and SQl server。

 you can enable automated incremental backups or perform onde backups。

 If you find your combination of RDBm and cloud provider does not support any of these options。

 there are thirdparty backup tools available to purchase。



![](img/3e9f971919422bbb1008eeb378e7cc61_35.png)

In this video you learned that hot or online backups allow data to be backed up while the database is active。

 whereas cold backups require the database to be offline。

 your backup policy should be determined from your recovery and availability needs and your data usage patterns and most managed cloud databases provide automated backup functionality with some configurable options。



![](img/3e9f971919422bbb1008eeb378e7cc61_37.png)

![](img/3e9f971919422bbb1008eeb378e7cc61_38.png)