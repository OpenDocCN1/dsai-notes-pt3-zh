# IBM数据工程专业证书课程4：《关系数据库导论（RDBMS）》｜introduction-to-relational-databases｜ - P23：22_标准化.zh_en - GPT中英字幕课程资源 - BV1Mj4116716

![](img/8445a390060be20ba438fc5bfc0f49b4_0.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_1.png)

Welcome to normalmalization。After watching this video。

 you will be able to explain the purpose of normalization， describescribe first normal form。

 describe second normal form， and describe third normal form。



![](img/8445a390060be20ba438fc5bfc0f49b4_3.png)

When you keep records of data， such as books in a bookshop。

 you will inevitably have some inconsistencies and duplicate information。



![](img/8445a390060be20ba438fc5bfc0f49b4_5.png)

Such duplication can cause extra work and inconsistencies if the data is updated because you must change it in more than one place。

Normalization is the process of organizing your data to reduce redundant data。

 often by dividing larger tables into multiple related tables。



![](img/8445a390060be20ba438fc5bfc0f49b4_7.png)

Normalization helps speed up transactions because you perform updates， additions。

 and deletes only once on the normalized database。It also improves data integrity because it reduces the chance of a change being made in one place。

 but not in another As you begin the normalization process。

 it's important to recognize that you focus on normalizing each table until you reach the required normal form level。

Normalization usually results in creating more tables， and once all the tables are normalized。

 you will have a normalized database。There are several forms of normalization。

 and most data engineers will need to be familiar with first normal form， second normal form。

 and third normal form。For a table to be in first normal form， each row must be unique。

 and each cell must contain only a single value。 First normal form is also called1 and F。



![](img/8445a390060be20ba438fc5bfc0f49b4_9.png)

Let's look at how you would normalize a simple table。In this example。

 the book table contains some basic information about books， including title。

 formats and authors to meet first normal form requirements， each cell must contain a single value。

 not a list。 In this example， you can see that all formats of a book are listed in the same cell。



![](img/8445a390060be20ba438fc5bfc0f49b4_11.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_12.png)

To normalize this table， you can add an extra row and split the two formats of patterns of software into their own row。

 So now you have a row for the paperback version and a row for the hardback version。

 Each cell in the table now has only one entry。 And so the table is in first normal form。



![](img/8445a390060be20ba438fc5bfc0f49b4_14.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_15.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_16.png)

To be in second normal form， the database must already be in first normal form。



![](img/8445a390060be20ba438fc5bfc0f49b4_18.png)

Second normal form specifies that you should separate groups of values that apply to multiple rows by creating new tables。



![](img/8445a390060be20ba438fc5bfc0f49b4_20.png)

Second normal form is also referred to as2 NF。For clarity。

 this example shows just a subset of the data in the book table。



![](img/8445a390060be20ba438fc5bfc0f49b4_22.png)

Book 401 comes in both paperback and hardback format。 so in the current form。

 it must be listed twice once for each format。

![](img/8445a390060be20ba438fc5bfc0f49b4_24.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_25.png)

In this case， the format column contains values that apply to both rows that reference book 401。

 and so there is some data duplication to meet the requirements for second normal form and achieve just one row for book 401。

 you can split the book table so that the format information for the book is separated from unrelated information such as title and author。



![](img/8445a390060be20ba438fc5bfc0f49b4_27.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_28.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_29.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_30.png)

Each resulting table is in1 and F。

![](img/8445a390060be20ba438fc5bfc0f49b4_32.png)

To maintain a relationship between the two tables， identify a primary key for one table that will be used as a foreign key in the other。

 In our example， the book underscore Id is unique to each book。

 so you can make that the primary key in the book table and include it as a foreign key in the format table。

 Now， you can use it to link between the two tables to find the different formats of each of the unique books。



![](img/8445a390060be20ba438fc5bfc0f49b4_34.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_35.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_36.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_37.png)

To meet the requirements for third normal form， the database must already be in first and second normal form。

 Next， you must eliminate any columns that do not depend on the key。



![](img/8445a390060be20ba438fc5bfc0f49b4_39.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_40.png)

Third normal form is also referred to as3NF。Let's consider some additional data about books。

 the publisher and where the book ships from。 Each publisher ships books from warehouses in their own location。

 So where the book ships from depends on the publisher， not the book I D。 Therefore。

 the book table is not in3 and F， because the ships from data does not depend on the primary key。



![](img/8445a390060be20ba438fc5bfc0f49b4_42.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_43.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_44.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_45.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_46.png)

To meet the requirements of 3 NF， you must separate the publisher and ships from information into a publisher's table。

 Both tables are now in third normal form， which is as far as most relational databases go。

 There are also higher normal forms， such as voice cod normal form or B NF。

 which is an extension to the third normal form， as well as fourth and fifth normal forms。

 which may be needed for specific scenarios。

![](img/8445a390060be20ba438fc5bfc0f49b4_48.png)

In transactional systems， OLTP， where data is both read and written frequently。

 you typically normalize the data to 3NF OLTP systems need to efficiently process and store transactions。

 as well as query transactionsal data， and normalizing the data to 3 NF helps the database to efficiently process and store individual transactions。



![](img/8445a390060be20ba438fc5bfc0f49b4_50.png)

![](img/8445a390060be20ba438fc5bfc0f49b4_51.png)

In analytical systems， OLAP， where the usages mostly read only。

 databases are optimized for read performance rather than write integrity。



![](img/8445a390060be20ba438fc5bfc0f49b4_53.png)

And hence， the data may have undergone some deormalization to a lower normal form before being loaded into the analytical system。

 such as a data warehouse。In data warehousing， data engineers are focused on performance。

 which can benefit from having fewer tables to process。In this video。

 you learned that normalization reduces redundancy and increases consistency of data In first normal form or1 NF。

 each row must be unique， and each cell must contain only a single item。

 In second normal form or two NF。 you must create separate tables for sets of values that apply to multiple records。



![](img/8445a390060be20ba438fc5bfc0f49b4_55.png)

And in third normal form or3 NF， eliminate any columns that do not depend on the key。



![](img/8445a390060be20ba438fc5bfc0f49b4_57.png)