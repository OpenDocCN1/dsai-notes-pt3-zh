# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P31：30_外部连接.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

Welcome to Outer join After watching this video， you will be able to describe left outer joins。

 right outer joins and full outer joins。Explain when to use each type of outer join。

And describe the syntax of the outer joint statement。Outer joins， unlike inner joins。

 return the rows from each table that have matching values in the join columns Unlike inner joins。

 outer joins also return the rows that do not have a match between the tables。

 SQL offers you three types of outer joins， left outer join， right outer join and full outer join。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_1.png)

In a left outer join， all the rows from the first table on the left side of the join predicate are included。

 and only the matching rows from the second table on the right side of the join predicate。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_3.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_4.png)

In this diagram， a left join matches all the rows from the left table and combines the information with the rows from the right table that match the criteria specified in the query。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_6.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_7.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_8.png)

In this diagram， a right join matches all the rows from the right table and combines the information with rows from the left table that match the criteria specified in the query a full join returns all rows from both the right table and the left table so the full join can return a very large result set in this diagram。

 the result set of a right join is all rows from both tables matching the criteria specified in the query plus all non- matchingching rows from the right table。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_10.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_11.png)

This is an example of the syntax of the select statement for a left join In this example。

 the borrower table is the first table specified in the from clause of the select statement。

 So the borrower table is the left table and the loan table is the right table in the from clause Ber is listed on the left side of the join operator。

 Therefore， you will select all rows from the borrower table and combine them with the contents of the loan table based on the criteria specified in the query。

 In this example， the criteria is the borrower IDd column。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_13.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_14.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_15.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_16.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_17.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_18.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_19.png)

For a left outer join， simply called a left join， you will select the following columns from the borrower table。

 Ber ID， last name and country， and you will also select the following columns from the loan table。

 borrower ID and loan date the left join selects each borrower ID in the borrower table and displays the loan date from the loan table。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_21.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_22.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_23.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_24.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_25.png)

The result set shows each borrower IDd from the borrower table and the loan date for that borrower。

 There is no loan date for the last three rows， so the borrower Id and the loan date show noll values。

 This is an example of the syntax of the select statement for a right join。 In this example。

 the borrower table is the first table specified in the from clause of the select statement。

 So the borrower table is the left table and the loan table is the right table。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_27.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_28.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_29.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_30.png)

In the from clause， the loan table is listed on the right side of the join operator。

 therefore you will select all rows from the loan table and combine them with the contents of the borrower table based on the criteria specified in the query In this example。

 the criteria is the borrower ID column for right join you will select the following columns from the loan table Ber ID and loan date。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_32.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_33.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_34.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_35.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_36.png)

And you will also select the following columns from the borrower table， borrower ID。

 last name and country where the borrower ID in the loan table matches the borrower ID in the borrower table。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_38.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_39.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_40.png)

The result set shows each borrower Id from the loan table and the loan date for the borrower。

 where the borrower Id in the loan table also exists in the borrower table For the last row。

 There is no matching row in the borrower table。 So the borrower I D last name and country show null values。

 This could indicate a problem for the library。 It indicates there is a book on loan to an unknown person。

 This is the syntax of the select statement for a full join。 For a full join。

 you select all rows from the borrower table and all rows from the loan table。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_42.png)

![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_43.png)

The results set shows all eight records from the borrower table listed with the corresponding data from the loan table。

 Once again， three rows return a null value because borrowers， Peters。

 Lee and Wang have never taken a book out on loan。The last row returns values for borrower I D and loan date from the loan table。

 but returns nulls from the borrower table。 In this instance。

 there is no match in the borrower table。 The borrower of this book is unknown。

In this video you learned that there are many varieties of outer join that you can use to refine your results set Left outer joins return all rows from the left table and all the rows from the right table that match when an inner join would return and all the rows in the first table that do not have a match in the second table。

 right or outer joins return all the rows that an inner join would return and all the rows in the second table that do not have a match in the first table。

 full outer joins return all matching rows from both tables and all the rows from both tables that don't have a match。



![](img/d7ddf8cf4b0b0bef6c2cb6738bd3931d_45.png)