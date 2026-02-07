# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P18：17_使用多个表.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

🎼。Hello and welcome In this video， you will learn how to write queries that access more than one table。

😊。

![](img/8b8b2c11ac19f3b990de5640fb811bc2_1.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_2.png)

There are several ways to access multiple tables in the same query， namely using subqueries。

 implicit join and join operators， such as inner join and outer join。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_4.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_5.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_6.png)

In this video， we'll examine the first two options。

 The third option is covered in more detail in other videos。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_8.png)

Let's consider the employees and departments tables from a previous video。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_10.png)

The employee's table contains several columns for categories such as employee I D， first name。

 last name and salary to name a few。The department's table contains a department ID， department name。

 manager ID， and location ID。Some sample data from these tables is shown here。

 We will utilize these tables for the examples in this video。In a previous video。

 we learned how to use subqueries。 Now， let's use subqueries to work with multiple tables。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_12.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_13.png)

If we want to retrieve only the employee records from the employee table for which a department ID exists in the department's table。

 we can use a subquery as follows。

![](img/8b8b2c11ac19f3b990de5640fb811bc2_15.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_16.png)

Select star from employees where Department ID in， select Department ID department from departments。

Here， the outer query accesses the employees table and the subquery on the department's table is used for filtering the result set of the outer query。

Let's say we want to retrieve only the list of employees from a specific location。

 We do not have any location information in the employees table。

 but the department's table has a column called location I D。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_18.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_19.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_20.png)

Therefore， we can use a subquery from the department's table as input to the employee table query as follows。

Select star from employees where department ID in， select Department ID department from departments where location ID equals L 0002。

Now， let's retrieve the department ID and department name for employees who earn more than $70，000。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_22.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_23.png)

To do so， we will need a subquery on the employees's table to satisfy the salary criteria and then feed it as input to an outer query on the department's table in order to get the matching department info。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_25.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_26.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_27.png)

Select department ID department， department name from departments。

 where department I Department In Select Department ID from employees where salary is greater than 70。

000。

![](img/8b8b2c11ac19f3b990de5640fb811bc2_29.png)

We can also access multiple tables by specifying them in the from clause of the query。

 Consider the example， select star from employees departments。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_31.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_32.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_33.png)

Here we specified two tables in the from clauseuse。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_35.png)

This results in a table join， but note we are not explicitly using the join operator。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_37.png)

The resulting join in this example is called a full join or Cartesian join。

 because every row in the first table is joined with every row in the second table。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_39.png)

If you examine the results set， you will see more rows than in both tables individually。

We can use additional offerings to limit the results set。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_41.png)

Let's look at an example where we limit the results set to only rows with matching department IDs。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_43.png)

Select star fromEmploy departments， whereEmploy department ID equals departments。

 department ID department。

![](img/8b8b2c11ac19f3b990de5640fb811bc2_45.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_46.png)

Notice that in the wear clauses， we prefix the name of the column with the name of the table。

This is to fully qualify the column name， since it's possible that different tables could have some column names that are exactly the same。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_48.png)

Since the table names can sometimes be long， we can use shorter aliases for table names as shown here。

Select star fromEmploys E departments D， where E department ID equals D department ID department。

Here we define the alias E for employees table and D for departments table。

 and then use these aliases in the warehouse clause。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_50.png)

If we wanted to see the department name for each employee， we would enter the code as follows。

 SelectEmploy ID Department name fromEmploys E departments D。

 where E department ID equals D department ID department。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_52.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_53.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_54.png)

![](img/8b8b2c11ac19f3b990de5640fb811bc2_55.png)

Similar to before， the column names in the select clause can also be prefixed by aliases as shown in the query。

 Select EEmployee ID D Department ID department fromEmploys E departments D where E department ID equals D department ID department。

In this lesson， we have shown you how to work with multiple tables using subqueries and implicit joins。



![](img/8b8b2c11ac19f3b990de5640fb811bc2_57.png)

Thanks for watching。