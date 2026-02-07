# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P7：6_关系数据库概念.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

🎼。Hello and welcome to database concepts In this video。

 we will learn about different types of models， how we use models to map data to tables and define relationships between tables。

 At the end of this lesson， you will be able to explain the advantage of the relational model Ex how the entity name and attributes map to a relational database table。

 De the difference between an entity and an attribute。

 identify some commonly used data types and describe the function of primary keys。😊。



![](img/0d0d636f72645077b32ede03fc984197_1.png)

![](img/0d0d636f72645077b32ede03fc984197_2.png)

![](img/0d0d636f72645077b32ede03fc984197_3.png)

![](img/0d0d636f72645077b32ede03fc984197_4.png)

The relational model is the most used data model for databases because this model allows for data independence Data is stored in a simple data structure。

 tables， This provides logical data independence， physical data independence and physical storage independence。



![](img/0d0d636f72645077b32ede03fc984197_6.png)

![](img/0d0d636f72645077b32ede03fc984197_7.png)

![](img/0d0d636f72645077b32ede03fc984197_8.png)

![](img/0d0d636f72645077b32ede03fc984197_9.png)

An entity relationship data model or ER data model is an alternative to a relational data model using a simplified library database as an example。

 this figure shows an entity relationship diagram or ERD that represents entities called tables and their relationships。

In the library example， we have books， a book can be written by one or many authors。

 The library can have one or many copies of a book。

 Each copy can be borrowed by only one borrower at a time。

An entity relationship model proposes thinking of a database as a collection of entities。



![](img/0d0d636f72645077b32ede03fc984197_11.png)

Rather than being used as a model on its own， the ER model is used as a tool to design relational databases in the ER model。

 entities are objects that exist independently of any other entities in the database。



![](img/0d0d636f72645077b32ede03fc984197_13.png)

![](img/0d0d636f72645077b32ede03fc984197_14.png)

![](img/0d0d636f72645077b32ede03fc984197_15.png)

The building blocks of an ER diagram are entities and attributes。 An entity can be a noun， person。

 place or thing。

![](img/0d0d636f72645077b32ede03fc984197_17.png)

![](img/0d0d636f72645077b32ede03fc984197_18.png)

In an ER diagram， an entity is drawn as a rectangle。 Enities have attributes。

 which are the data elements that characterize the entity。



![](img/0d0d636f72645077b32ede03fc984197_20.png)

![](img/0d0d636f72645077b32ede03fc984197_21.png)

Attributes tell us more about the entity in an ER diagram， attributes are drawn as ovals。



![](img/0d0d636f72645077b32ede03fc984197_23.png)

Using a simplified library as an example， the book is an example of an entity。

Attributes are certain properties or characteristics of an entity， and tell us more about the entity。

The entity book has attributes such as book title， the edition of the book。

 the year the book was written， etc cetera。 Attributes are connected to exactly one entity。

The entity book becomes a table in the database， and the attributes become the columns in a table。



![](img/0d0d636f72645077b32ede03fc984197_25.png)

A table is a combination of rows and columns。 While mapping， the entity becomes the table。

 Having said that， the table has not yet taken the form of rows and columns。

 The attributes get translated into columns in a table。

 providing the actual table form of rows and columns。 Later。

 we add some data values to each of the columns， which completes the table form。



![](img/0d0d636f72645077b32ede03fc984197_27.png)

![](img/0d0d636f72645077b32ede03fc984197_28.png)

![](img/0d0d636f72645077b32ede03fc984197_29.png)

![](img/0d0d636f72645077b32ede03fc984197_30.png)

Each attribute stores data values of different formats， characters， numbers， dates。

 currency and many more besides in the book table example， the title is made up of characters。

 As book titles vary in length。 We can set the variable character data type for the title column varar。

 for character columns that do not vary in length。 we use character or car。

 The addition and year columns would be numeric the ISBN column would be car because it contains dashes as well as numbers and so on。



![](img/0d0d636f72645077b32ede03fc984197_32.png)

![](img/0d0d636f72645077b32ede03fc984197_33.png)

![](img/0d0d636f72645077b32ede03fc984197_34.png)

![](img/0d0d636f72645077b32ede03fc984197_35.png)

![](img/0d0d636f72645077b32ede03fc984197_36.png)

![](img/0d0d636f72645077b32ede03fc984197_37.png)

Using the book Enity mapping as an example， we can create the tables for the remainder of our simplified library example。

 using entity names like author， author list， borrower， loan and copy。

 The entity attributes will be the columns of the tables。



![](img/0d0d636f72645077b32ede03fc984197_39.png)

![](img/0d0d636f72645077b32ede03fc984197_40.png)

![](img/0d0d636f72645077b32ede03fc984197_41.png)

![](img/0d0d636f72645077b32ede03fc984197_42.png)

Each table is assigned a primary key， the primary key of a relational table uniquely identifies each tuple or row in a table。

 preventing duplication of data and providing a way of defining relationships between tables。



![](img/0d0d636f72645077b32ede03fc984197_44.png)

![](img/0d0d636f72645077b32ede03fc984197_45.png)

Tables can also contain foreign keys， which are primary keys defined in other tables creating a link between the tables。



![](img/0d0d636f72645077b32ede03fc984197_47.png)

![](img/0d0d636f72645077b32ede03fc984197_48.png)

Now， you know that the key advantage of the relational model is logical and physical data independence and storage independence entitiesities are independent objects which can have multiple characteristics called attributes。



![](img/0d0d636f72645077b32ede03fc984197_50.png)

![](img/0d0d636f72645077b32ede03fc984197_51.png)

![](img/0d0d636f72645077b32ede03fc984197_52.png)

When mapping to a relational database， entities are represented as tables and attributes mapped to columns。



![](img/0d0d636f72645077b32ede03fc984197_54.png)

Common data types include characters such as car and Vcar。

 numbers such as integer and decimal and timestamps， including date and time。

A primary key uniquely identifies a specific row in a table and prevents duplication of data。

