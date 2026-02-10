# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P9：8_CREATE TABLE建表语句.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

![](img/46eb72a7ac22cfd2827952266a44e7aa_0.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_1.png)

Welcome to create table statement。 At the end of this video。

 you will be able to explain how the entity name and attributes are used to create a relational database table。

 Now， let's look at the most common DDL statement。 C the syntax of the create table is shown here。

 You start with create table followed by the name of the table you want to create。

 Then enclose the rest of the statement inside of pair of parentheses or round brackets。😊。



![](img/46eb72a7ac22cfd2827952266a44e7aa_3.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_4.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_5.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_6.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_7.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_8.png)

Each row inside the parentheses specifies the name of a column。

 followed by its data type and possibly some additional optional values that we will see later。



![](img/46eb72a7ac22cfd2827952266a44e7aa_10.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_11.png)

Each attribute or column definition is separated by a comma。



![](img/46eb72a7ac22cfd2827952266a44e7aa_13.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_14.png)

For example， if we want to create a table for provinces in Canada。

 you would specify createate T provinces， Open parentheses， ID Car2， primary key， not null， comma。

 name Var， 24 Close parentheses。

![](img/46eb72a7ac22cfd2827952266a44e7aa_16.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_17.png)

In this example， the data types used are car， which is a character string of a fixed length in this case。

2， and varar， which is a character string of a variable length。 In this case。

 the variable character field can be up to 24 characters long。



![](img/46eb72a7ac22cfd2827952266a44e7aa_19.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_20.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_21.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_22.png)

Issuing this statement would create a table in the database with two columns。

 the first column ID for storing the abbreviated two letter province short codes such as A B， BC。

 etc ce， and the second column called name for storing the full name of the province。

 such as Alberta， British Columbia， etc。

![](img/46eb72a7ac22cfd2827952266a44e7aa_24.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_25.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_26.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_27.png)

Now， let's look at a more elaborate example based on the library database。

 This database includes several entities such as author， book， borrower， etc。

 Let's start by creating the table for the author entity。



![](img/46eb72a7ac22cfd2827952266a44e7aa_29.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_30.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_31.png)

The name of the table will be author and its attributes such as author underscore ID， first name。

 last name， etc， will be the columns of the table。

![](img/46eb72a7ac22cfd2827952266a44e7aa_33.png)

In this table， we will also assign the author underscore IDd attribute as the primary key so that no duplicate values can exist。

 Re， the primary key of a relational table uniquely identifies each tuple or row in a table。

To create the author table， issue the following command， create table author open parentheses。

 author underscore IDd Car2 primary key N null， last name Varar。

15 not null first name Var 15 N null email varar 40 City varar 15， country Car 2， close parentheses。



![](img/46eb72a7ac22cfd2827952266a44e7aa_35.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_36.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_37.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_38.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_39.png)

Note that the author underscore ID is the primary key。

 This constraint prevents duplicate values in the table。



![](img/46eb72a7ac22cfd2827952266a44e7aa_41.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_42.png)

Also， note that the last name and first name have the constraint， not null。

 This ensures that these fields cannot contain a null value， Since an author must have a name。



![](img/46eb72a7ac22cfd2827952266a44e7aa_44.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_45.png)

Now you know that Cate is a DDL statement for creating entities or tables in a database。

 and the Cate table statement includes definition of attributes of columns in the table。

 including names of columns， data types of columns and other optional values if required such as the primary key constraint thanks for watching this video。



![](img/46eb72a7ac22cfd2827952266a44e7aa_47.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_48.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_49.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_50.png)

![](img/46eb72a7ac22cfd2827952266a44e7aa_51.png)