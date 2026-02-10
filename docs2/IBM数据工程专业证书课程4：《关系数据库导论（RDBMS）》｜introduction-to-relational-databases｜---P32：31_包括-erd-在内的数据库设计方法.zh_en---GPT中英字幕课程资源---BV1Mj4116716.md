# IBM数据工程专业证书课程4：《关系数据库导论（RDBMS）》｜introduction-to-relational-databases｜ - P32：31_包括 erd 在内的数据库设计方法.zh_en - GPT中英字幕课程资源 - BV1Mj4116716

![](img/bf3db45cf7710eaad603ef683c652b70_0.png)

![](img/bf3db45cf7710eaad603ef683c652b70_1.png)

Welcome to Appro to Data Design。After watching this video。

 you will be able to describe the importance of good database design。

 explain the database design process， and describe the purpose of an ERD tool。



![](img/bf3db45cf7710eaad603ef683c652b70_3.png)

![](img/bf3db45cf7710eaad603ef683c652b70_4.png)

A well designed database is crucial to the success of any data driven project。

 the design of the database contributes to the integrity of data， the reduction of redundant data。

 application performance， and user satisfaction， which are all key markers of a successful project。



![](img/bf3db45cf7710eaad603ef683c652b70_6.png)

![](img/bf3db45cf7710eaad603ef683c652b70_7.png)

![](img/bf3db45cf7710eaad603ef683c652b70_8.png)

As such， it is essential that you spend the time upfront designing your database to avoid costly problems at a later date。



![](img/bf3db45cf7710eaad603ef683c652b70_10.png)

There are three key steps in the database design process， requirements analysis。

 where you analyze the data you are working with and the requirements for the use of that data。

 logical design， where you plan how to organize your data， and physical design。

 where you plan how to implement your logical design in the database management system you will be using。



![](img/bf3db45cf7710eaad603ef683c652b70_12.png)

![](img/bf3db45cf7710eaad603ef683c652b70_13.png)

![](img/bf3db45cf7710eaad603ef683c652b70_14.png)

![](img/bf3db45cf7710eaad603ef683c652b70_15.png)

During the first stage， you gather and analyze real world business information and policies。

 You need to identify the base objects in the data and the relationships between these objects。

 For example， in a library scenario， person borrows a book。



![](img/bf3db45cf7710eaad603ef683c652b70_17.png)

![](img/bf3db45cf7710eaad603ef683c652b70_18.png)

![](img/bf3db45cf7710eaad603ef683c652b70_19.png)

You also need to identify the information associated with these objects that you will use to interact with them for a book。

 this could be the title， description， ISBN and authors。



![](img/bf3db45cf7710eaad603ef683c652b70_21.png)

![](img/bf3db45cf7710eaad603ef683c652b70_22.png)

And for a person， it could be their name， address and contact details。



![](img/bf3db45cf7710eaad603ef683c652b70_24.png)

How you obtain this information can vary from project to project。

 but is likely to include reviewing any existing stores of this data， be that in a database。

 other electronic format or even a paper based system。

 interviewing users to determine how the business currently uses this data。

 and interviewing users and potential users to determine how the business could make better use of this data。



![](img/bf3db45cf7710eaad603ef683c652b70_26.png)

![](img/bf3db45cf7710eaad603ef683c652b70_27.png)

![](img/bf3db45cf7710eaad603ef683c652b70_28.png)

![](img/bf3db45cf7710eaad603ef683c652b70_29.png)

![](img/bf3db45cf7710eaad603ef683c652b70_30.png)

![](img/bf3db45cf7710eaad603ef683c652b70_31.png)

If the data currently resides in a database， when reviewing the existing structure。

 be sure to use it as a source of information about the data rather than a starting template for your own database design。



![](img/bf3db45cf7710eaad603ef683c652b70_33.png)

![](img/bf3db45cf7710eaad603ef683c652b70_34.png)

The output from your requirements analysis could be a report， a data diagram。

 or a presentation that you can share with stakeholders to validate your understanding of the system。



![](img/bf3db45cf7710eaad603ef683c652b70_36.png)

![](img/bf3db45cf7710eaad603ef683c652b70_37.png)

In the logical design phase， you take the requirements you identified in the analysis stage and map them to entities。

 attributes and relationships however， logical models should not specify any technical requirements so you should not be thinking about any implementation considerations at this stage。

The objects that you identified in the previous stage become entities。 General， entities are people。

 events， locations or things。 And if you find you have an object that doesn't fit into one of these categories。

 you should double check that it really is an object rather than a characteristic of another object。

The characteristics of the objects will become attributes。

So the book object becomes a book entity and the person object becomes a person entity。



![](img/bf3db45cf7710eaad603ef683c652b70_39.png)

At this stage， you should also try to think about the attributes of your entities。

 You may think of a person having a name， but in database terms。

 it is better to think of them having a first name and a last name。

 This makes it easier to search on and sort by either first or last name。

 And although the requirements analysis identified that a person has an address when you think about storing that address。

 you should divide it up into its constituent parts。



![](img/bf3db45cf7710eaad603ef683c652b70_41.png)

![](img/bf3db45cf7710eaad603ef683c652b70_42.png)

![](img/bf3db45cf7710eaad603ef683c652b70_43.png)

![](img/bf3db45cf7710eaad603ef683c652b70_44.png)

![](img/bf3db45cf7710eaad603ef683c652b70_45.png)

When analyzing the requirements， you identify that a person borrows a book。 However。

 a person may borrow many books and a book may be borrowed by many people。

 So this is a many to many relationships， which can lead to ambiguity in a database。

 The easiest way to solve this is by creating two separate one to many relationships by introducing an associative entity in between the existing ones。



![](img/bf3db45cf7710eaad603ef683c652b70_47.png)

![](img/bf3db45cf7710eaad603ef683c652b70_48.png)

![](img/bf3db45cf7710eaad603ef683c652b70_49.png)

![](img/bf3db45cf7710eaad603ef683c652b70_50.png)

In the book to person scenario， you can add in a loan entity。

 One person can have many loans and one book can be loaned many times。

 The loan entity will contain attributes from the book table and the person table。

 as well as some loan specific ones。

![](img/bf3db45cf7710eaad603ef683c652b70_52.png)

![](img/bf3db45cf7710eaad603ef683c652b70_53.png)

![](img/bf3db45cf7710eaad603ef683c652b70_54.png)

You could relate these entities by their matching attributes。 However。

 none of those are guaranteed to be unique in the book entity。 the IBn will be unique。

 so you could use that as the primary key。 you can then use the ISBN instead of the book title in the loan entity to identify the borrowed book。

 There are no unique attributes in the person entity。

 so you can add an identifier your attribute to that entity and use that to link the loan to the person。

 and you can add a loan ID to the loan entity to uniquely identify each loan。

 Now that you have your view of your entities and attributes。 you can consider normalization。

 Most OLTP systems are normalized to the third normal form for optimal transactional performance。

 whereas OLAP systems are generally deormalized to enhance read performance。



![](img/bf3db45cf7710eaad603ef683c652b70_56.png)

![](img/bf3db45cf7710eaad603ef683c652b70_57.png)

![](img/bf3db45cf7710eaad603ef683c652b70_58.png)

![](img/bf3db45cf7710eaad603ef683c652b70_59.png)

![](img/bf3db45cf7710eaad603ef683c652b70_60.png)

![](img/bf3db45cf7710eaad603ef683c652b70_61.png)

![](img/bf3db45cf7710eaad603ef683c652b70_62.png)

![](img/bf3db45cf7710eaad603ef683c652b70_63.png)

![](img/bf3db45cf7710eaad603ef683c652b70_64.png)

![](img/bf3db45cf7710eaad603ef683c652b70_65.png)

![](img/bf3db45cf7710eaad603ef683c652b70_66.png)

To adhere to first normal form， you need to remove the potential of two or more author's names being listed in the author's attribute for an individual book。



![](img/bf3db45cf7710eaad603ef683c652b70_68.png)

![](img/bf3db45cf7710eaad603ef683c652b70_69.png)

One option is to split this into author  one and author two attributes。 However。

 there's no guarantee of a maximum number of authors for a book。

 and this would not adhere to second normal form。 So a better way is to create a separate author's entity with a many to one relationship to the book entity。

 when you have finished normalize your entities。 you can move on to the physical design stage how your database will actually look。



![](img/bf3db45cf7710eaad603ef683c652b70_71.png)

![](img/bf3db45cf7710eaad603ef683c652b70_72.png)

![](img/bf3db45cf7710eaad603ef683c652b70_73.png)

![](img/bf3db45cf7710eaad603ef683c652b70_74.png)

At this stage， you can start to consider the impact that your choice of database management system will have on your design。

 For example， the data types it supports the naming rules it implements and the indexes and constraints it supports when you are thinking about naming rules。

 you should also consider implementing your own convention so that anyone working with your data will understand your schema So the person entity from your logical design will become a person table in your physical design with each attribute becoming a typed column and keys being defined。



![](img/bf3db45cf7710eaad603ef683c652b70_76.png)

![](img/bf3db45cf7710eaad603ef683c652b70_77.png)

![](img/bf3db45cf7710eaad603ef683c652b70_78.png)

![](img/bf3db45cf7710eaad603ef683c652b70_79.png)

![](img/bf3db45cf7710eaad603ef683c652b70_80.png)

![](img/bf3db45cf7710eaad603ef683c652b70_81.png)

![](img/bf3db45cf7710eaad603ef683c652b70_82.png)

![](img/bf3db45cf7710eaad603ef683c652b70_83.png)

You can use an ERD designer to create your entity relationship diagrams PG admin includes the ERD tool in which you can design your ERD and then generate an SQL script that will create your database and objects based on your design。

In this video you learned that it is important to spend time designing your database before you start the implementation。

 there are three stages of database design， requirements analysis。

 logical design and physical design and using an ERD designer can simplify the design process。



![](img/bf3db45cf7710eaad603ef683c652b70_85.png)

![](img/bf3db45cf7710eaad603ef683c652b70_86.png)