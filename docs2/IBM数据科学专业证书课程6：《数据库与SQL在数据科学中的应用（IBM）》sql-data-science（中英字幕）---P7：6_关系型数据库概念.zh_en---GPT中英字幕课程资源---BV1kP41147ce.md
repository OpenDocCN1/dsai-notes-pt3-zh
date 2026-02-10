# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P7：6_关系型数据库概念.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

。Hello and welcome to database concepts In this video， we will learn about different types of models。

 how we use models to map data to tables and define relationships between tables。

 At the end of this lesson， you will be able to explain the advantage of the relational model。

 Ex how the entity name and attributes map to a relational database table。

 Describe the difference between an entity and an attribute， identify some commonly used data types。

 and describe the function of primary keys。😊。

![](img/afa3e3463f1571d693ad12a112c4d7f3_1.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_2.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_3.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_4.png)

The relational model is the most used data model for databases because this model allows for data independence Data is stored in a simple data structure。

 tables。 This provides logical data independence， physical data independence and physical storage independence。



![](img/afa3e3463f1571d693ad12a112c4d7f3_6.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_7.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_8.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_9.png)

An entity relationship data model or ER data model is an alternative to a relational data model。



![](img/afa3e3463f1571d693ad12a112c4d7f3_11.png)

Using a simplified library database as an example， this figure shows an entity relationship diagram or ERD that represents entities called tables and their relationships。



![](img/afa3e3463f1571d693ad12a112c4d7f3_13.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_14.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_15.png)

In the library example， we have books， a book can be written by one or many authors。

 The library can have one or many copies of a book。

 Each copy can be borrowed by only one borrower at a time。



![](img/afa3e3463f1571d693ad12a112c4d7f3_17.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_18.png)

An entity relationship model proposes thinking of a database as a collection of entities。



![](img/afa3e3463f1571d693ad12a112c4d7f3_20.png)

Rather than being used as a model on its own， the ER model is used as a tool to design relational databases in the ER model。

 entities are objects that exist independently of any other entities in the database。



![](img/afa3e3463f1571d693ad12a112c4d7f3_22.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_23.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_24.png)

The building blocks of an ER diagram are entities and attributes， an entity can be a noun， person。

 place or thing。In an ER diagram， an entity is drawn as a rectangle。 Enities have attributes。

 which are the data elements that characterize the entity。



![](img/afa3e3463f1571d693ad12a112c4d7f3_26.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_27.png)

Attributes tell us more about the entity in an ER diagram， attributes are drawn as ovals。



![](img/afa3e3463f1571d693ad12a112c4d7f3_29.png)

Using a simplified library as an example， the book is an example of an entity。

Attributes are certain properties or characteristics of an entity， and tell us more about the entity。

The entity book has attributes such as book title， the edition of the book。

 the year the book was written， etc cea。 Attributes are connected to exactly one entity。

The entity book becomes a table in the database， and the attributes become the columns in a table。

A table is a combination of rows and columns。 While mapping， the entity becomes the table。

 Having said that the table has not yet taken the form of rows and columns。

 The attributes get translated into columns in a table providing the actual table form of rows and columns。

 Later， we add some data values to each of the columns， which completes the table form。



![](img/afa3e3463f1571d693ad12a112c4d7f3_31.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_32.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_33.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_34.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_35.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_36.png)

Each attribute stores data values of different formats， characters， numbers， dates， currency。

 and many more besides in the book table example， the title is made up of characters as book titles vary in length。

 We can set the variable character data type for the title column varar for character columns that do not vary in length。

 we use character or car The addition and year columns would be numeric。

 the ISBN column would be card because it contains dashes as well as numbers and so on。



![](img/afa3e3463f1571d693ad12a112c4d7f3_38.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_39.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_40.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_41.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_42.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_43.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_44.png)

Using the book Enity mapping as an example， we can create the tables for the remainder of our simplified library example。

 using entity names like author， author list， borrower， loan and copy。

 the entity attributes will be the columns of the tables。



![](img/afa3e3463f1571d693ad12a112c4d7f3_46.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_47.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_48.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_49.png)

Each table is assigned a primary key， the primary key of a relational table uniquely identifies each tuple or row in a table。

 preventing duplication of data and providing a way of defining relationships between tables。



![](img/afa3e3463f1571d693ad12a112c4d7f3_51.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_52.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_53.png)

Tables can also contain foreign keys， which are primary keys defined in other tables creating a link between the tables。



![](img/afa3e3463f1571d693ad12a112c4d7f3_55.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_56.png)

Now， you know that the key advantage of the relational model is logical and physical data independence and storage independence entitiesities are independent objects which can have multiple characteristics called attributes。



![](img/afa3e3463f1571d693ad12a112c4d7f3_58.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_59.png)

When mapping to a relational database， entities are represented as tables and attributes mapped columns。



![](img/afa3e3463f1571d693ad12a112c4d7f3_61.png)

Common data types include characters such as car and Vcar。

 numbers such as integer and decimal and timestamps， including date and time。



![](img/afa3e3463f1571d693ad12a112c4d7f3_63.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_64.png)

![](img/afa3e3463f1571d693ad12a112c4d7f3_65.png)

A primary key uniquely identifies a specific row in a table and prevents duplication of data。

