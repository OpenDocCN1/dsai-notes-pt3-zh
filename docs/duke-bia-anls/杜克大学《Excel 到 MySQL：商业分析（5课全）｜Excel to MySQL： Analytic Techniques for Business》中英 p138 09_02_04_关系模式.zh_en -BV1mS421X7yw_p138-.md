# 杜克大学《Excel 到 MySQL：商业分析（5课全）｜Excel to MySQL： Analytic Techniques for Business》中英 p138 09_02_04_关系模式.zh_en -BV1mS421X7yw_p138-

![](img/dfccaf44edb28d648b4ffc0e369e2bf5_0.png)

嗯。In the last video， we learned how to read ER diagrams。

ER diagrams represent the concepts that database architects have to implement。

 but they don't yet represent how a database is actually organized。

 although a well designed database will have an ER diagram that looks very similar to what the corresponding database ends up looking like。

To describe the model of what a database truly looks like， you use a relational schema In this video。

 we will learn how to interpret and make these relational schemas。

The critical components of a relational schema are tables， primary keys and foreign keys。

To get a feel for how these components relate to the information in an ER diagram。

 let's examine how one of the ER diagrams we saw in a previous video would be translated into a relational schema。

You can see that in general， each entity in the ER diagram has been turned into a table in the relational schema。

Before I use that word table again， though， I have to tell you that some people would not approve of using that word when talking about relational schemas。

Let me explain their disapproval。Relational schemas can be thought of as blueprints for a database。

 A blueprint for a car tells you important information about how a car is going to be built。

 but it isn't equivalent to a built car。 The reason why is that building a car takes a lot more work and draws upon a lot more information than is included in the blueprint。

Plus， the blueprint is a representation of something that will be made in the future。

 but the car is a concrete object that already exists。Likewise。

 a relational schema tells you important information about how a database is going to be organized。

 but it isn't equivalent to a built database。Building the database requires more work and detailed information than is represented by the relational schema。

Plus， a relational schema is usually a plan， but a database is something that is already made。

If it is important to you to differentiate between the logical ideas behind a database design and the physical implementation of those ideas in a database。

 you will use different vocabulary for the concepts used in the database design versus the steps used in database creation。

This is the reason some people would get upset at the idea of describing the box in a relational schema as a table。

The technical term for the phenomenon represented by a box in a relational schema is relation。

 which is a term that once again comes from set theory。

A relation is a logical idea that serves as the organization for the physical basis of the database。

For our purposes in this course， it is not important to emphasize the difference between the theoretical design of a database and its physical implementation。

 So I will refer to the relation as a table。In general， in fact。

 I will tell you what the technical descriptions of the phenomena depicted in relational schema are。

 but I， like many database users as opposed to database designers。

 will use common names to talk about them。This will make it much easier for us to achieve the goals of the course。

 which is to learn SQL， not to make databases。Nonetheless。

 you should be aware that many people in the database world feel strongly that words like table。

 rows and columns are not appropriate for describing relational schemas。

I'll make sure you know the technical terminology too。

 in case you need to communicate with people who have that view。With that issue out of the way。

 let's turn back to what I usually call tableples and relational schemas。

Each table or relation in theoretical terms， has a set of columns which can also be called fields。

These columns represent the attributes we saw in the R diagrams before。

 and it turns out that they are formerly called attributes and relational schemas as well。

Each entry in a table is a row or a record， the ph logical term for an entity in a table or a relation is a tuple。

In theory， no tuple can be duplicated in a relation in practice， though。

 rows can be duplicated in tables annoyingly for analysts。In both theory and practice。

 the columns in a table are not allowed to have a particular order。

 no matter what it might look like sometimes， the rows in a table do not have a particular order either。

Both columns and rows must be independent for set theory to work and for the database to be able to return queries correctly and as quickly as possible。

 As a consequence， remember that you can never trust the order in which data are output from a query unless you specifically tell the query to output them in a certain way。

The critical thing to look out for in a relational schema is that each table must have a primary key。

The primary key for a table will be one of the columns we talked about in a previous video that has a unique identifier for every row in that table。

The primary key will be underlined in a relational schema just like it was inR diagrams。

A critical difference betweenR diagrams and relational schemas， though。

 is that although you are supposed to underline all unique attributes in the R diagram。

 only one unique column in a table of a relational schema or database can be labeled as a primary key。

The only exception is if you need multiple columns to make each row in a table unique。

The reason you can only have one primary key is that the database software uses the primary key in special ways to ensure data integrity。

To maintain this integrity， primary keys are configured so that they cannot contain any missing values。

 although missing values can sneak in occasionally if a database is configured too flexibly。

In contrast， other unique columns can be configured to allow for null values。

 Despite the vanillall valuess， you can still link tables using unique columns that are not primary keys。

 though， when you run those queries to help you with these links。

 it is useful to mark unique columns in your schema with a U next to their column titles so that you know which ones can be used to link tables in your queries。

The next important concept to know about is the concept of a foreign key。

Foreign keys are used to link tables to other tables；

 they accomplish this by having values that refer to unique IDs and other tables。

In our Egarers Rose coffeeoff example， contact ID was a foreign key in the orders table that let us link each order with information about the customer contact and the customer contact table。

You indicate foreign keys and relational sches by drawing arrows from the foreign key in one table to the primary key it refers to in another table。

It is good practice to write the abbreviation FK next to the name of a foreign key column as well。

 but some people do leave that out。Its important to know that foreign keys and primary keys to which they match up do not have to use the same title。

Hopefully， a good database designer will at least make the name seem similar。

 but you can't rely on that being the case。 So that's one of the reasons relational schemes can be so helpful to you as an analyst trying to query your data。

Now that you know the basic components of relational schema。

 let's look at some additional examples of relational schemas and see if we can figure out what they mean。

 We'll start with a relatively straightforward one。Here。

 our database is keeping track of employees and their phone numbers。

 Each employee is identified by his or her own unique employee ID。

 Each phone number is unique on its own。In a query。

 phone numbers can be matched up to employees using the employee ID number that exists in both tables。

One thing you might notice though， is that there is nothing in the relational schema that says how many employees can match up with a phone number。

It's possible that two employees could live together and share the same home phone number。

 It's also possible that a single employee could have provided multiple phone numbers。

 This version of the relational schema doesn't provide that information。

A version that did include this information would use the same notation as we learned about ERR diagrams。

 As an example， here we see that each employee。Must have a minimum of one phone number that can have multiple phone numbers。

Each phone number。Must be linked up to exactly one single employee。

Many relational schemas do not include garden information。

 that's another reason why it's useful to understand both ERR diagrams and relational schemas and why you should ask for both when you start working with a database。

Let's look at how a weak entity would be represented in a relational schema。

Here our database is keeping track of buildings and apartments。

 Each apartment is uniquely identified by a combination of the apartment number and the apartment table with the building ID and the building table。

You can discern this from the fact that both apartment ID and building ID are underlined in the apartment table and that in addition。

 building ID in this table is a foreign key to the building ID and the building table。

You might remember this example because the relational schema we just made depicts the weak entity we discussed in this ER diagram in a previous video。

Let's look at one more example of relational schema。Here。

 our database is keeping track of students and classes。

It also has another table called Enrolled in that only has foreign in keys as attributes。

This type of mapping table has to be implemented when the entities in the corresponding ER diagram have what is called a many to many relationship。

In this case， each student can enroll in many classes。

 and each class can have many students enrolled in it。Under these circumstances。

 there is no way to follow the rule that primary keys must not be duplicated and still include a foreign key in the same table as the primary key。

Therefore， a mapping table that has nothing but one composite primary key is made。

The composite key is made up of two foreign keys that link to the primary keys of the two tables of the many to many relationship。

Whenever you see a mapping table like this in a database。

 it's a clue of the columns and the tables it links up can have multiple instances of one another。

I have included some relational schema exercises with the course materials that were once again donated by Nana Juicch。

 professor at Quinlan School of Business at Loyola University of Chicago。

These exercises are derived from his textbook pictured here。Like the ER diagram exercises。

 you are not required to complete these， but I highly recommend that you do so。

Pay particular attention to the location of foreign keys。

 and then carefully about what columns you would need to reference if you wanted to link columns separated into different tables together。

Since relational schemas are the closest thing you have to a map of your database。

 learning how to read them comfortably will make it much easier to navigate your database with effective queries later。

You should also be aware that you will often be given access to a database without a relational schema or any kind of description of what is in the database。

 When this happens， it will be useful for you to know how to generate a relational schema yourself so that you can refer to it when you start doing your data analyses in the next video we will show you how to make one using ERD plus an online tool that Nd createdd to help people design databases。



![](img/dfccaf44edb28d648b4ffc0e369e2bf5_2.png)