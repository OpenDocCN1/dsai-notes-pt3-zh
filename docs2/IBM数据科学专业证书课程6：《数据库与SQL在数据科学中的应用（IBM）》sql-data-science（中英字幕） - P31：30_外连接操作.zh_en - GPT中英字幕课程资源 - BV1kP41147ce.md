# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P31：30_外连接操作.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

Welcome to Outer join After watching this video， you will be able to describe left outer joins。

 right outer joins and full outer joins。

![](img/de1f6d95b2b6e5bec625da4ad4728da4_1.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_2.png)

Explain when to use each type of outer join。And describe the syntax of the outer joint statement。

Outer joins， unlike inner joins， return the rows from each table that have matching values in the join columns。

 Unlike inner joins， outer joins also return the rows that do not have a match between the tables。

 SQL offers you three types of outer joins， Left outer join， right outer join and full outer join。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_4.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_5.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_6.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_7.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_8.png)

In a left outer join， all the rows from the first table on the left side of the join predicate are included。

 and only the matching rows from the second table on the right side of the join predicate。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_10.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_11.png)

In this diagram， a left join matches all the rows from the left table and combines the information with the rows from the right table that match the criteria specified in the query。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_13.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_14.png)

In this diagram， a right join matches all the rows from the right table and combines the information with rows from the left table that match the criteria specified in the query a full join returns all rows from both the right table and the left table so the full join can return a very large result set in this diagram。

 the result set of a right join is all rows from both tables matching the criteria specified in the query plus all non-matching rows from the right table。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_16.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_17.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_18.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_19.png)

This is an example of the syntax of the select statement for a left join In this example。

 the borrower table is the first table specified in the from clause of the select statement So the borrower table is the left table and the loan table is the right table in the from clause Ber is listed on the left side of the join operator。

 Therefore， you will select all rows from the borrower table and combine them with the contents of the loan table based on the criteria specified in the query。

 In this example， the criteria is the borrower ID column。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_21.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_22.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_23.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_24.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_25.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_26.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_27.png)

For a left outer join， simply called a left join， you will select the following columns from the borrower table。

 Ber ID， last name and country， and you will also select the following columns from the loan table。

 borrower ID and loan date the left join selects each borrower ID in the borrower table and displays the loan date from the loan table。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_29.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_30.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_31.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_32.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_33.png)

The result set shows each borrower ID from the borrower table and the loan date for that borrower。

 there is no loan date for the last three rows， so the borrower ID and the loan date show null values。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_35.png)

This is an example of the syntax of the select statement for a right join In this example。

 the borrower table is the first table specified in the from clause of the select statement。

 So the borrower table is the left table， and the loan table is the right table。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_37.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_38.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_39.png)

In the from clause， the loan table is listed on the right side of the join operator。

 therefore you will select all rows from the loan table and combine them with the contents of the borrower table based on the criteria specified in the query In this example。

 the criteria is the borrower ID column for right join。

 you will select the following columns from the loan table Ber ID and loan date。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_41.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_42.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_43.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_44.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_45.png)

And you will also select the following columns from the borrower table， borrower ID。

 last name and country where the borrower ID in the loan table matches the borrower ID in the borrower table。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_47.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_48.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_49.png)

The result set shows each borrower I D from the loan table and the loan date for the borrower。

 where the borrower I D in the loan table also exists in the borrower table For the last row。

 there is no matching row in the borrower table。 So the borrower I D。

 last name and country show null values。 This could indicate a problem for the library。

 It indicates there is a book on loan to an unknown person。

 This is the syntax of the select statement for a full join。

 For a full join you select all rows from the borrower table and all rows from the loan table。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_51.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_52.png)

The results set shows all eight records from the borrower table listed with the corresponding data from the loan table。

 Once again， three rows return a null value because borrowers， Peters。

 Lee and Wang have never taken a book out on loan。The last row returns values for borrower Id and loan date from the loan table。

 but returns nulls from the borrower table。 In this instance。

 there is no match in the borrower table。 The borrower of this book is unknown。

In this video you learned that there are many varieties of outer join that you can use to refine your results set Left outer joins return all rows from the left table and all the rows from the right table that match when an inner join would return and all the rows in the first table that do not have a match in the second table。

 right or outer joins return all the rows that an inner join would return and all the rows in the second table that do not have a match in the first table。

 full outer joins return all matching rows from both tables and all the rows from both tables that don't have a match。



![](img/de1f6d95b2b6e5bec625da4ad4728da4_54.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_55.png)

![](img/de1f6d95b2b6e5bec625da4ad4728da4_56.png)