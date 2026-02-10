# IBM数据工程专业证书课程4：《关系数据库导论（RDBMS）》｜introduction-to-relational-databases｜ - P2：1_信息和数据模型.zh_en - GPT中英字幕课程资源 - BV1Mj4116716

![](img/25f00940410300068b850cda4f0dd413_0.png)

![](img/25f00940410300068b850cda4f0dd413_1.png)

Welcome to information and data models After watching this video。

 you will be able to describe the difference between an information model and a data model。

 Explain the advantage of a relational model， and describe the difference between an entity and an attribute。

 This figure illustrates the relationship between an information model and a data model。

 and information model is an abstract formal representation of entities that includes their properties relationships and the operations that can be performed on them。

 The entities being modeled can be from the real world such as a library。

 Information models and a data models are different and serve different purposes。

 An information model is at the conceptual level and defines relationships between objects。

 data models are defined at a more concrete level。 Our specific and include details。😊。



![](img/25f00940410300068b850cda4f0dd413_3.png)

![](img/25f00940410300068b850cda4f0dd413_4.png)

![](img/25f00940410300068b850cda4f0dd413_5.png)

![](img/25f00940410300068b850cda4f0dd413_6.png)

![](img/25f00940410300068b850cda4f0dd413_7.png)

![](img/25f00940410300068b850cda4f0dd413_8.png)

![](img/25f00940410300068b850cda4f0dd413_9.png)

![](img/25f00940410300068b850cda4f0dd413_10.png)

![](img/25f00940410300068b850cda4f0dd413_11.png)

![](img/25f00940410300068b850cda4f0dd413_12.png)

A data model is the blueprint of a database system。



![](img/25f00940410300068b850cda4f0dd413_14.png)

There are several different types of information models。

 the most familiar is the hierarchical typically used to show organization charts。



![](img/25f00940410300068b850cda4f0dd413_16.png)

![](img/25f00940410300068b850cda4f0dd413_17.png)

As shown in this figure， the hierarchical model organizes its data using a tree structure。

 The root of the tree is the parent node followed by child nodes。



![](img/25f00940410300068b850cda4f0dd413_19.png)

![](img/25f00940410300068b850cda4f0dd413_20.png)

A child node could not have more than one parent。 However， a parent can have many child nodes。



![](img/25f00940410300068b850cda4f0dd413_22.png)

The first hierarchical database management system was the information management system released by IBM in 1968 and was originally built as the database for the Apollo space program。



![](img/25f00940410300068b850cda4f0dd413_24.png)

![](img/25f00940410300068b850cda4f0dd413_25.png)

The relational model is the most used database model for databases because this model allows for data independence。

 Data is stored in a simple data structure， tables。 This provides logical data independence。

 physical data independence and physical storage independence。

 an entity relationship data model or ER data model is an alternative to a relational data model。

 using a simplified library database as an example。

 This figure shows an entity relationship diagram or ERD that represents entities called tables and their relationships。

 There are authors who write books， borrowers who take books out on loan。

 various copies of each book， etc ce。 This is the final ER diagram。 But how do we get there。



![](img/25f00940410300068b850cda4f0dd413_27.png)

![](img/25f00940410300068b850cda4f0dd413_28.png)

![](img/25f00940410300068b850cda4f0dd413_29.png)

An entity relationship model proposes thinking of a database as a collection of entities。

 rather than being used as a model on its own， the ER model is used as a tool to design relational databases。



![](img/25f00940410300068b850cda4f0dd413_31.png)

![](img/25f00940410300068b850cda4f0dd413_32.png)

![](img/25f00940410300068b850cda4f0dd413_33.png)

In the ER model entities are objects that exist independently of any other entities in the database。

 it is simple to convert an ER diagram into a collection of tables。

 the building blocks of an ER diagram are entities and attributes。



![](img/25f00940410300068b850cda4f0dd413_35.png)

![](img/25f00940410300068b850cda4f0dd413_36.png)

![](img/25f00940410300068b850cda4f0dd413_37.png)

Entities have attributes， which are the data elements that characterize the entity attributes tell us more about the entity。



![](img/25f00940410300068b850cda4f0dd413_39.png)

In an ER diagram， an entity is drawn as a rectangle and attributes are drawn as ovals。

 Enities can be a noun， person， place or thing， using a simplified library as an example。

 a book is an example of an entity。 Attributes are certain properties or characteristics of an entity。

 and tell us more about the entity。The entity book has attributes such as book title。

 the edition of the book， the year the book was written， etc。

 Attris are connected to exactly one entity。 The entity book becomes a table in the database and the attributes become the columns in the table。



![](img/25f00940410300068b850cda4f0dd413_41.png)

Continuing the simplified library example， books are written by authors， book is an entity。

 and author is an entity for the entity author， the ER diagram would look like this。



![](img/25f00940410300068b850cda4f0dd413_43.png)

The entity author has attributes such as the author's last name， first name， email， city， country。

 and an author ID to uniquely identify the author。The entity author becomes a table in the database。

 and the attributes become the columns in the table in the simplified library database。

 you progress through the process of identifying entities。

 such as borrowers who take books out on loan， various copies of each book and copies of books out on loan。

 This is the final ER diagram。 Each entity becomes a table in the database。



![](img/25f00940410300068b850cda4f0dd413_45.png)

![](img/25f00940410300068b850cda4f0dd413_46.png)

![](img/25f00940410300068b850cda4f0dd413_47.png)

In this video， you learned that information models are abstract。

 formal representations of entities that include their properties， relationships。

 and the operations that can be performed on them。

![](img/25f00940410300068b850cda4f0dd413_49.png)

![](img/25f00940410300068b850cda4f0dd413_50.png)

![](img/25f00940410300068b850cda4f0dd413_51.png)

Data models are defined at a more concrete level， are specific and include details。

The relational model is the most used data model for databases because this model allows for logical data independence。

 physical data independence， and physical storage independence。

Entities are objects that exist independently of any other entities in the database。

Entities can be a noun， a person， place or thing， such as a book or an author。

And attributes are the data elements that characterize the entity， for example。

 the book entity will have attributes like author and title。



![](img/25f00940410300068b850cda4f0dd413_53.png)