# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P6：5_更新和删除语句.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_0.png)

Hello and welcome to the update statement and the delete statement。 In this video。

 we will learn about altering and deleting data in a relational database table。

 At the end of this lesson， you will be able to identify the syntax of the update statement and delete statement and explain the importance of the where clause in these statements。

😊。

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_2.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_3.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_4.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_5.png)

After a table is created and populated with data， the data in a table can be altered with the update statement。

 The update statement is one of the data manipulation， language， or D M L statements。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_7.png)

DML statements are used to read and modify data。Based on the author entity example。

 we created the table using the entity name author and the entity attributes as the columns of the table。

Rowose were added to the author table to populate the table。Sometime later。

 you want to alter the data in the table。To alter or modify the data in the author table。

 we use the update statement。 The syntax of the update statement looks like this update table name set。

 column name equal to value where condition。

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_9.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_10.png)

In this statement， table name identifies the table。

 The column name identifies the column value to be changed as specified in the where condition。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_12.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_13.png)

Let's look at an example。In this example， you want to update the first name and last name of the author with author underscore I D A2 from Raav Ahuja to Lakshmi Kata In this example。

 to see the update statement in action， we start by selecting all rows from the author table to see the values。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_15.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_16.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_17.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_18.png)

To change the first name and last name to Lukshmi Kata， where the author I D is equal to a 2。

 enter the update statement as follows。 Up author set last name equal to Kata。

 first name equal to Lukshmi， where author I D is equal to a 2。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_20.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_21.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_22.png)

Now， to see the result of the update， select all rows again from the author table。

 And you will see that in row 2， the name changed from Rab Ahuja to Lakshmikata。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_24.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_25.png)

Note that if you do not specify the wear clauses， all the rows in the table will be updated。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_27.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_28.png)

In this example， without specifying the war clauses。

 all row in the table would have changed the first and last names to Lashmikata。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_30.png)

Some time later， there might be a need to remove one or more rows from a table。

 The rows are removed with the delete statement。 The delete statement is one of the data manipulation language statements used to read and modify data。

 The syntax of the delete statement looks like this。 Delete from table name， where condition。

 The rows to be removed are specified in the where condition。



![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_32.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_33.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_34.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_35.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_36.png)

Based on the author entity example， we want to delete the rows for author ID A2 and A3。

 Let's look at an example。

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_38.png)

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_39.png)

Delete from author where author I D in A2， A3。 Note that if you do not specify the wear clauses。

 all the rows in the table will be removed。Now， you can identify the syntax of the update statement and delete statement and explain the importance of the where clause in these statements。

Thanks for watching this video。

![](img/57a2e45ac98e7fe687d8d2f76a1bd6aa_41.png)