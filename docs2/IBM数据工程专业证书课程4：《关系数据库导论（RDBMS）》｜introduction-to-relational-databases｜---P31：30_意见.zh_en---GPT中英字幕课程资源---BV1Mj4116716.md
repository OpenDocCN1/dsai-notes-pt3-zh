# IBM数据工程专业证书课程4：《关系数据库导论（RDBMS）》｜introduction-to-relational-databases｜ - P31：30_意见.zh_en - GPT中英字幕课程资源 - BV1Mj4116716

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_0.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_1.png)

Welcome to Views After watching this video you will be able to describe views， create and use a view。

 explain how materialized views differ from regular views， and create and use a materialized view。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_3.png)

A view is an alternative way of representing data from one or more tables or other views。

 You can interact with views in the same way as you interact with tables， inserting。

 updating and deleting data as required。

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_5.png)

Views are a useful way of limiting access to sensitive data， simplifying data retrieval。

 and reducing access to underlying tables。For example。

 you could create a view to include the name and the email columns from these two tables。

Users can then easily access this data without needing to know that it is stored into different tables and without being given access to the sensitive salary information in Pg admin。

 you create views within a schema。 So in the tree view on the left hand side。 right click views。

 click create， and then click view。 This opens the create view box in which you first need to name the view and then on the code page you enter the SQL code that defines the view and then click save。

 You'll then see your view in the View folder and you can expand the view to display the columns included in it。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_7.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_8.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_9.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_10.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_11.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_12.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_13.png)

To run the view， right click the view name， click View Edit data， and then click All rows。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_15.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_16.png)

You will then see all the rows included in the view。PostgresQL also supports another type of view。

 a materialized view。

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_18.png)

When you refresh a materialized view for the first time。

 the results set is materialized or saved for future use。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_20.png)

This materialization does mean that you can only query the data and cannot update or delete it。

However， it also enhances performance for future querying of the view because the results set is readily available。

 often stored in memory。Creating a materialized view is a similar process to creating a regular view。

 but you must ensure that you start in the materialized View folder in the tree View。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_22.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_23.png)

After entering the name for the view on the definition page， enter the code to define the view。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_25.png)

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_26.png)

This example includes just the employee ID and salary columns from theEmploy_ detailstail table to anonymize the salary information。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_28.png)

Then click saveve and the materialized view is added to the folder。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_30.png)

Because the view stores the data before using it， you need to refresh it with the current rows。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_32.png)

And then you can use the view to access the data it holds。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_34.png)

You can refresh the data in the view at any time to update it with the data in the underlying tables。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_36.png)

In this video， you learned that views are an alternative way of representing data。

 you can use views to limit access to sensitive data and simplify data retrieval。



![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_38.png)

Materialized views store the results set for quicker， subsequent access。And you can insert。

 update or delete rows via a materialized view。

![](img/1e7ded3c9cd5cc4d67fb2f0171cad4e1_40.png)