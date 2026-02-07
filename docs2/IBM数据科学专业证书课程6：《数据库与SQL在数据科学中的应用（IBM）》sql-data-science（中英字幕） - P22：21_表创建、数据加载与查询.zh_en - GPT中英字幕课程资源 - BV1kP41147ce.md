# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P22：21_表创建、数据加载与查询.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_0.png)

Hello and welcome to creating tables， loading data and querying data After completing this lesson。

 you will be able to understand basic concepts related to creating tables。

 loading data and querying data using Python as well as demonstrate an example of how to perform these tasks using the IBM DB2 on Cloud database and Jupiter notebooks。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_2.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_3.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_4.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_5.png)

For this example， we will be using DV2 as the database。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_7.png)

We first obtain a connection resource by connecting to the database by using the connect method of the IBM_ DB API。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_9.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_10.png)

There are different ways of creating tables in D B2。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_12.png)

One is using the Web console provided by DB2， and the other option is to create tables from any SQL R or Python environments。

 Let's take a look at how to create tables in Db2 from our Python application。

 Here is a sample table of a commercial trucks database。

 Let's see how we can create the Trus table in the DB2 using Python code to create a table We use the IBM underscore Db Exec underscore immediate function。

 The parameters for the function R connection which is a valid database connection resource that is returned from the IBM underscore Db Connect or IBM underscore DbP Connect function。

😊。

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_14.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_15.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_16.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_17.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_18.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_19.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_20.png)

Statement， which is a string that contains the SQL statement and options。

 which is an optional parameter that includes a dictionary that specifies the type of cursor to return for result sets。

 Here is the code to create a table called trucks in Python。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_22.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_23.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_24.png)

We use the IBM underscore DB Exec underscore Imediate function of the IBM_ DB API。

The connection resource that was created is passes the first parameter to this function。

The next parameter is the SQL statement， which is the Cate table query used to create the Tru's table。

The new table created will have five columns。 Seral underscore no will be the primary key。 Now。

 let's take a look at loading data。 We use the IBM underscore D B。

 Exec underscore immediate function of the IBM underscore D B API。

 The connection resource that was created as passed as the first parameter to this function。

The next parameter is the SQL statement， which is the insert into query used to insert data in the trucks table。

 A new row will be added to the trucks table。 Similarly。

 we add more rows to the trucks table using the IBM underscore Db Exec underscore immediate function。

 Now that your Python code has been connected to a database instance。

 and the database table has been created and populated with data。

 Let's see how we can fetch data from the trucks table that we created on DB2 using Python code。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_26.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_27.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_28.png)

We use the IBM underscore DB Exec underscore immediate function of the IBM_ DB API。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_30.png)

The connection resource that was created is passed as the first parameter to this function。

 The next parameter is the SQL statement， which is the select from table query。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_32.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_33.png)

The Python code returns the output， which shows the fields of the data in the truck's table。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_35.png)

You can check if the output returned by the select query shown is correct by referring to the DB2 console。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_37.png)

Let's look at how we can use pandas to retrieve data from the database tables。

 Padas is a popular Python library that contains high level data structures and manipulation tools designed to make data analysis fast and easy in Python。



![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_39.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_40.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_41.png)

We load data from the trucks table into a data frame called D F。

 A data frame represents a tabular spreadsheet like data structure containing an ordered collection of columns。

 each of which can be a different value type。

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_43.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_44.png)

![](img/b59e4ffcb8d8dbd1e8b4cb5f1c887f66_45.png)

Thanks for watching this video。