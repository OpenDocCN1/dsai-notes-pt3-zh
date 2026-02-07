# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P25：24_表结构与列信息获取.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

。Hello and welcome In this video， we'll look at how to get information about tables and their columns in a database。

😊。

![](img/e6b1bc7c812859e1d706e4d504d13586_1.png)

Now， how would you get a list of tables in the database？

Sometimes your database may contain several tables， and you may not remember the correct name。



![](img/e6b1bc7c812859e1d706e4d504d13586_3.png)

For example， you may wonder whether the table is called dog dogs or four legged mammals。



![](img/e6b1bc7c812859e1d706e4d504d13586_5.png)

Database systems typically contain system or catalog tables from where you can query the list of tables and get their properties。



![](img/e6b1bc7c812859e1d706e4d504d13586_7.png)

In DB2， this catalog is called CiscaAT tables in SQL Server， it information schema tables。

 and in Oracle， it's all tables or user tables。

![](img/e6b1bc7c812859e1d706e4d504d13586_9.png)

![](img/e6b1bc7c812859e1d706e4d504d13586_10.png)

![](img/e6b1bc7c812859e1d706e4d504d13586_11.png)

To get a list of tables in a DB2 database， you can run the following query。



![](img/e6b1bc7c812859e1d706e4d504d13586_13.png)

Select star from Cscat tables。This select statement will return to many tables。

 including system tables， So it's better to filter the result as shown here。 Select T schema， T name。

 create， underscore time from Ciscat tables， where tab schema equals ABC 1，2，3，4，5。

Please ensure that you replace ABC 12345 with your own DB2 username。

When you do a select star from Ciscat tables， you get all the properties of the tables。

Sometimes we're interested in specific properties， such as creation time。

Let's say you've created several tables with similar names。 For example， dog1， dog underscore test。

 dog test 1， and so on。 But you want to check which of these tables was the last one you created。



![](img/e6b1bc7c812859e1d706e4d504d13586_15.png)

![](img/e6b1bc7c812859e1d706e4d504d13586_16.png)

![](img/e6b1bc7c812859e1d706e4d504d13586_17.png)

To do so， you can issue a query like select Tab schema， Tab name。

 Cate underscore time from CisCAT tables， where tabab schema equals QCM 54853。



![](img/e6b1bc7c812859e1d706e4d504d13586_19.png)

![](img/e6b1bc7c812859e1d706e4d504d13586_20.png)

The output will contain the schema name， table name， and creation time for all tables in your schema。



![](img/e6b1bc7c812859e1d706e4d504d13586_22.png)

Next， let's talk about how to get a list of columns in a table。

If you can't recall the exact name of a column， for example。

 whether it had any lower case characters or an underscore in its name in D B2。

 you can issue a query like the one shown here。

![](img/e6b1bc7c812859e1d706e4d504d13586_24.png)

Select star from Ciscat columns where tabab name equals dogs。



![](img/e6b1bc7c812859e1d706e4d504d13586_26.png)

For your information， in my Sequel， you can simply run the command， show columns from dogs。



![](img/e6b1bc7c812859e1d706e4d504d13586_28.png)

Or you may want to know specific properties like the data type and length of the data type in DB2。

 you can issue a statement like select distinct name。

 call type length from cis IBM cis columns where T B name equals dogs。

Here we look at the results of retrieving column properties for a real table called Chicago Crime data from a Jupiter notebook。

Notice in the output， you can tell certain column names show different cases。 For example。

 the column titled Ar has an uppercase A， and the rest of the characters are lowercase。

So keep in mind that when you refer to this column in your query。

 not only must you enclose the word arrest within double quotes。

 you must also preserve the correct case inside the quotes。In this video。

 we saw how to retrieve table and column information。 Thanks for watching。😊。



![](img/e6b1bc7c812859e1d706e4d504d13586_30.png)