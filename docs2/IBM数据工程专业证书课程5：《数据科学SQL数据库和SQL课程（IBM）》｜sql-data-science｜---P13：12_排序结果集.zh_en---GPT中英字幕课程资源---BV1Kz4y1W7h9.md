# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P13：12_排序结果集.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

![](img/db4ee1098dfe446cc4595a4388368be5_0.png)

Hello and welcome to sorting Select statement results sets In this video。

 we will learn about some advanced techniques in retrieving data from a relational database table and sorting how the results set displays。

😊。

![](img/db4ee1098dfe446cc4595a4388368be5_2.png)

![](img/db4ee1098dfe446cc4595a4388368be5_3.png)

At the end of this lesson， you will be able to describe how to sort the results set by either ascending or descending order and explain how to indicate which column to use for the sorting order。



![](img/db4ee1098dfe446cc4595a4388368be5_5.png)

![](img/db4ee1098dfe446cc4595a4388368be5_6.png)

The main purpose of a database management system is not just to store the data。

 but also facilitate retrieval of the data。

![](img/db4ee1098dfe446cc4595a4388368be5_8.png)

In its simplest form， a select statement is select star from table name。



![](img/db4ee1098dfe446cc4595a4388368be5_10.png)

Based on our simplified library database model and the table book select star from book gives a result set of four rows。



![](img/db4ee1098dfe446cc4595a4388368be5_12.png)

![](img/db4ee1098dfe446cc4595a4388368be5_13.png)

All the data rows for all columns in the table book are displayed。



![](img/db4ee1098dfe446cc4595a4388368be5_15.png)

We could choose to list the book titles only， as shown in this example， select title from book。

However， the order does not seem to be in any order displaying the results set in alphabetical order would make the result set more convenient to do this。

 we use the order by clause。To display the results set in alphabetical order。

 we add the order by clause to the select statement。



![](img/db4ee1098dfe446cc4595a4388368be5_17.png)

![](img/db4ee1098dfe446cc4595a4388368be5_18.png)

The order by clause is used in a query to sort the result set by a specified column。 In this example。

 we have used order by on the column title to sort the result set by default。

 The result set is sorted in ascending order。 In this example。

 the result set is sorted in alphabetical order by book title。



![](img/db4ee1098dfe446cc4595a4388368be5_20.png)

![](img/db4ee1098dfe446cc4595a4388368be5_21.png)

![](img/db4ee1098dfe446cc4595a4388368be5_22.png)

To sort and descending order， use the keyword des。 The result set is now sorted according to the column specified。

 which is title and is sorted in descending order。 Notice the order of the first three rows。

 The first three words of the title are the same。

![](img/db4ee1098dfe446cc4595a4388368be5_24.png)

So the sorting starts from the point where the characters differ。



![](img/db4ee1098dfe446cc4595a4388368be5_26.png)

Another way of specifying the sort column is to indicate the column sequence number。



![](img/db4ee1098dfe446cc4595a4388368be5_28.png)

In this example， select title pages from book order by two indicates the column sequence number in the query for the sorting order。



![](img/db4ee1098dfe446cc4595a4388368be5_30.png)

Instead of specifying the column name pages， the number two is used in the select statement。

 the second column specified in the column list is pages。

 So the sort order is based on the values in the pages column。



![](img/db4ee1098dfe446cc4595a4388368be5_32.png)

![](img/db4ee1098dfe446cc4595a4388368be5_33.png)

![](img/db4ee1098dfe446cc4595a4388368be5_34.png)

In this case， the pages column indicates the number of pages in the book。



![](img/db4ee1098dfe446cc4595a4388368be5_36.png)

As you can see， the result set is an ascending order by number of pages。



![](img/db4ee1098dfe446cc4595a4388368be5_38.png)

Now， you can describe how to sort the result set by either ascending or descendending order and explain how to indicate which column to use for the sorting order。



![](img/db4ee1098dfe446cc4595a4388368be5_40.png)

Thanks for watching this video。