# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P9：8_创建表语句.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

![](img/21d6e3050ed9daea85b5d24448bc485c_0.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_1.png)

Welcome to Create Table statementment。At the end of this video。

 you will be able to explain how the entity name and attributes are used to create a relational database table。

 Now， let's look at the most common DDL statement。 C the syntax of the create table is shown here。

 You start with create table， followed by the name of the table you want to create。

 Then enclose the rest of the statement inside of pair of parentheses or round brackets。

 Each row inside the parentheses， specifies the name of a column。

 followed by its data type and possibly some additional optional values that we will see later。😊。



![](img/21d6e3050ed9daea85b5d24448bc485c_3.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_4.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_5.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_6.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_7.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_8.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_9.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_10.png)

Each attribute or column definition is separated by a comma。



![](img/21d6e3050ed9daea85b5d24448bc485c_12.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_13.png)

For example， if we want to create a table for provinces in Canada。

 you would specify createate T provinces， Open parentheses， ID Car2， primary key， not null， comma。

 name Var， 24 Close parentheses。

![](img/21d6e3050ed9daea85b5d24448bc485c_15.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_16.png)

In this example， the data types used are Car， which is a character string of a fixed length in this case。

2， and varar， which is a character string of a variable length。 In this case。

 the variable character field can be up to 24 characters long。



![](img/21d6e3050ed9daea85b5d24448bc485c_18.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_19.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_20.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_21.png)

Issuing this statement would create a table in the database with two columns。

 the first column ID for storing the abbreviated two letter province short codes such as A B， BC。

 etc， and the second column called name for storing the full name of the province， such as Alberta。

 British Columbia， etc。

![](img/21d6e3050ed9daea85b5d24448bc485c_23.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_24.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_25.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_26.png)

Now， let's look at a more elaborate example based on the library database。

 This database includes several entities such as author， book， borrower， etc。

 Let's start by creating the table for the author entity。



![](img/21d6e3050ed9daea85b5d24448bc485c_28.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_29.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_30.png)

The name of the table will be author and its attributes such as author underscore ID， first name。

 last name， etc， will be the columns of the table。

![](img/21d6e3050ed9daea85b5d24448bc485c_32.png)

In this table， we will also assign the author underscore IDd attribute as the primary key so that no duplicate values can exist。

 Re， the primary key of a relational table uniquely identifies each tuple or row in a table。

To create the author table， issue the following command， create table author open parentheses。

 author underscore IDd Car2 primary key N null， last name Varar 15 not null first name Varar 15 N null email varar 40 City varar 15。

 country Car 2， close parentheses。

![](img/21d6e3050ed9daea85b5d24448bc485c_34.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_35.png)

Note that the author underscore ID is the primary key。

 This constraint prevents duplicate values in the table。



![](img/21d6e3050ed9daea85b5d24448bc485c_37.png)

Also， note that the last name and first name have the constraint， not null。

 This ensures that these fields cannot contain a null value， Since an author must have a name。



![](img/21d6e3050ed9daea85b5d24448bc485c_39.png)

Now you know that Cate is a DDL statement for creating entities or tables in a database。

 and the Cate table statement includes definition of attributes of columns in the table。

 including names of columns， data types of columns and other optional values if required such as the primary key constraint thanks for watching this video。



![](img/21d6e3050ed9daea85b5d24448bc485c_41.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_42.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_43.png)

![](img/21d6e3050ed9daea85b5d24448bc485c_44.png)