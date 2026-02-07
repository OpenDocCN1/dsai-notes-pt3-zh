# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P22：21_创建表 加载数据和查询数据.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

Hello and welcome to creating tables， loading data and querying data After completing this lesson。

 you will be able to understand basic concepts related to creating tables。

 loading data and querying data using Python， as well as demonstrate an example of how to perform these tasks using the IBM DB2 on Cloud databasease and Jupiter notebooks。



![](img/690be835baf172cdc7704cdc53e724de_1.png)

![](img/690be835baf172cdc7704cdc53e724de_2.png)

![](img/690be835baf172cdc7704cdc53e724de_3.png)

![](img/690be835baf172cdc7704cdc53e724de_4.png)

For this example， we will be using DV2 as the database。



![](img/690be835baf172cdc7704cdc53e724de_6.png)

We first obtain a connection resource by connecting to the database by using the connect method of the IBM underscore DB API。



![](img/690be835baf172cdc7704cdc53e724de_8.png)

![](img/690be835baf172cdc7704cdc53e724de_9.png)

There are different ways of creating tables in D B2。



![](img/690be835baf172cdc7704cdc53e724de_11.png)

One is using the Web console provided by DB2， and the other option is to create tables from any SQL R or Python environments。

 Let's take a look at how to create tables in Db2 from our Python application。

 Here is a sample table of a commercial Trus database。

 Let's see how we can create the Trus table in the DB2 using Python code to create a table We use the IBM underscore Db Exec underscore immediate function The parameters for the function R connection which is a valid database connection resource that is returned from the IBM underscore Db Connect or IBM underscore DBP connect function。

😊。

![](img/690be835baf172cdc7704cdc53e724de_13.png)

![](img/690be835baf172cdc7704cdc53e724de_14.png)

![](img/690be835baf172cdc7704cdc53e724de_15.png)

![](img/690be835baf172cdc7704cdc53e724de_16.png)

![](img/690be835baf172cdc7704cdc53e724de_17.png)

![](img/690be835baf172cdc7704cdc53e724de_18.png)

![](img/690be835baf172cdc7704cdc53e724de_19.png)

Statement， which is a string that contains the SQL statement and options。

 which is an optional parameter that includes a dictionary that specifies the type of cursor to return for result sets。

 Here is the code to create a table called trucks in Python。



![](img/690be835baf172cdc7704cdc53e724de_21.png)

![](img/690be835baf172cdc7704cdc53e724de_22.png)

![](img/690be835baf172cdc7704cdc53e724de_23.png)

![](img/690be835baf172cdc7704cdc53e724de_24.png)

We use the IBM underscore DB Exec underscore Imediate function of the IBM_ DB API。



![](img/690be835baf172cdc7704cdc53e724de_26.png)

The connection resource that was created is passes the first parameter to this function。

The next parameter is the SQL statement， which is the Cate table query used to create the Tru's table。

The new table created will have five columns。 Serreal underscore no will be the primary key。 Now。

 let's take a look at loading data。 We use the IBM underscore D B。

 Exec underscore immediate function of the IBM underscore D B， API。

 The connection resource that was created is passed as the first parameter to this function。



![](img/690be835baf172cdc7704cdc53e724de_28.png)

The next parameter is the SQL statement， which is the insert into query used to insert data in the trucks table。

 A new row will be added to the trucks table。 Similarly。

 we add more rows to the trucks table using the IBM underscore Db Exec underscore immediate function。

 Now that your Python code has been connected to a database instance。

 and the database table has been created and populated with data。

 Let's see how we can fetch data from the trucks table that we created on Db2 using Python code。



![](img/690be835baf172cdc7704cdc53e724de_30.png)

![](img/690be835baf172cdc7704cdc53e724de_31.png)

![](img/690be835baf172cdc7704cdc53e724de_32.png)

We use the IBM underscore DB Exec underscore Imedia function of the IBM_ DB API。



![](img/690be835baf172cdc7704cdc53e724de_34.png)

The connection resource that was created is passed as the first parameter to this function。

 The next parameter is the SQL statement， which is the select from table query。



![](img/690be835baf172cdc7704cdc53e724de_36.png)

![](img/690be835baf172cdc7704cdc53e724de_37.png)

The Python code returns the output， which shows the fields of the data in the truck's table。



![](img/690be835baf172cdc7704cdc53e724de_39.png)

You can check if the output returned by the select query shown is correct by referring to the DB2 console。



![](img/690be835baf172cdc7704cdc53e724de_41.png)

Let's look at how we can use pandas to retrieve data from the database tables。

 Padas is a popular Python library that contains high level data structures and manipulation tools designed to make data analysis fast and easy in Python。



![](img/690be835baf172cdc7704cdc53e724de_43.png)

![](img/690be835baf172cdc7704cdc53e724de_44.png)

![](img/690be835baf172cdc7704cdc53e724de_45.png)

We load data from the trucks table into a data frame called D F。

 A data frame represents a tabular spreadsheet like data structure containing an ordered collection of columns。

 each of which can be a different value type。

![](img/690be835baf172cdc7704cdc53e724de_47.png)

![](img/690be835baf172cdc7704cdc53e724de_48.png)

![](img/690be835baf172cdc7704cdc53e724de_49.png)

Thanks for watching this video。