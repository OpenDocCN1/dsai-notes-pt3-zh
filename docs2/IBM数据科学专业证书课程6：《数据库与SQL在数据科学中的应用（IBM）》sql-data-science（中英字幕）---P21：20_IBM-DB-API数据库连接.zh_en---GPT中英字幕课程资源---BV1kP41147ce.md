# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P21：20_IBM DB API数据库连接.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

![](img/781814cf5b21b0f12bcb0436c98feea5_0.png)

Hello and welcome to connecting to a database using the IBM underscore DB API。

 After completing this lesson， you will be able to understand the IBM underscore DB API。

 as well as the credentials required to connect to a database using Python。

 We will also demonstrate how to connect to an IBM DB2 database using Python code written on a Jupiter notebook。

😊。

![](img/781814cf5b21b0f12bcb0436c98feea5_2.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_3.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_4.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_5.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_6.png)

The IBM underscore DBAP provides a variety of useful Python functions for accessing and manipulating data in an IBM data server database。

 including functions for connecting to a database， preparing and issuing SQL statements。

 fetching rows from results sets， calling stored procedures。

 committing and rolling back transactions， handling errors and retrieving metadata。



![](img/781814cf5b21b0f12bcb0436c98feea5_8.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_9.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_10.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_11.png)

The IBM underscore DB API uses the IBM data Ser driver for ODBC and CI APIs to connect to IBM DB2 and InformM。

We import the IBM underscore DB library into our Python application。

Connecting to the DB2 requires the following information， a driver name， a database name。

 a host DNS name or IP address， a host port， a connection protocol， a user ID， and a user password。

Here is an example of creating a DB2 database connection in Python。



![](img/781814cf5b21b0f12bcb0436c98feea5_13.png)

We create a connection object DS SN， which stores the connection credentials。

 The connect function of the IBM underscore DB API will be used to create a non persistent connection。

 The DSN object is passed as a parameter to the connection function。

 If a connection has been established with the database。 Then the code returns connected。

 As the output otherwise， the output will be unable to connect to database。

 Then we free all resources by closing the connection。

 Remember that it is always important to close connection so that we can avoid unused connections taking up resources。



![](img/781814cf5b21b0f12bcb0436c98feea5_15.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_16.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_17.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_18.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_19.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_20.png)

![](img/781814cf5b21b0f12bcb0436c98feea5_21.png)

Thank you for watching this video。

![](img/781814cf5b21b0f12bcb0436c98feea5_23.png)