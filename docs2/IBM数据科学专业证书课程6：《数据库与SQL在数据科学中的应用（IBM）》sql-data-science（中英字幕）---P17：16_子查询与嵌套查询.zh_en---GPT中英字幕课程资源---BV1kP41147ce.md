# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P17：16_子查询与嵌套查询.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

。Hello and welcome In this video， you'll learn how to write subqueries or nested select statements。😊。



![](img/8e4382c49997b3dcee87c670c8d6aecd_1.png)

Subqueries or sub selects are like regular queries。

 but placed within parentheses and nested inside another query。



![](img/8e4382c49997b3dcee87c670c8d6aecd_3.png)

This allows you to form more powerful queries than would have been otherwise possible。



![](img/8e4382c49997b3dcee87c670c8d6aecd_5.png)

An example of a nested query is shown。

![](img/8e4382c49997b3dcee87c670c8d6aecd_7.png)

In this example， the subquery is inside the war clauses of another query。



![](img/8e4382c49997b3dcee87c670c8d6aecd_9.png)

Consider the employeess table from the previous video。The first few rows of data are shown here。

The table contains several columns， including an employee ID， first name， last name， salary， etc。

We will now go over some examples， involving this table。

Let's consider a scenario which may necessitate the use of subqueries。

Let's say we want to retrieve the list of employees who earn more than the average salary。



![](img/8e4382c49997b3dcee87c670c8d6aecd_11.png)

To do so， we could try this code。 select star from employees where salary is greater than average salary。



![](img/8e4382c49997b3dcee87c670c8d6aecd_13.png)

However， running this query will result in an error like the one shown。

 indicating an invalid use of the aggregate function。

One of the limitations of built in aggregate functions like the average function is that they cannot always be evaluated in the war clause。



![](img/8e4382c49997b3dcee87c670c8d6aecd_15.png)

So to evaluate a function like average in the wear clauses。

 we could make use of a sub select expression， like the one shown here。



![](img/8e4382c49997b3dcee87c670c8d6aecd_17.png)

![](img/8e4382c49997b3dcee87c670c8d6aecd_18.png)

Select employee ID， first name， last name， salary from employees where salary is less than open parenthesis。

 Select average salary from employees Close parenthsesis。

Notice that the average function is evaluated in the first part of the sub queryry。

 allowing us to circumvent the limitation of evaluating it directly in the where clause。



![](img/8e4382c49997b3dcee87c670c8d6aecd_20.png)

The subselect doesn't just have to go in the where clause。

 It can also go in other parts of the query， such as in the list of columns to be selected。



![](img/8e4382c49997b3dcee87c670c8d6aecd_22.png)

![](img/8e4382c49997b3dcee87c670c8d6aecd_23.png)

Such subqueries are called column expressions。

![](img/8e4382c49997b3dcee87c670c8d6aecd_25.png)

Now， let's look at a scenario where we might want to use a column expression。



![](img/8e4382c49997b3dcee87c670c8d6aecd_27.png)

Say we wanted to compare the salary of each employee with the average salary。

 We could try a query like select employee I D salary。

 average salary as average salary from employees。

![](img/8e4382c49997b3dcee87c670c8d6aecd_29.png)

![](img/8e4382c49997b3dcee87c670c8d6aecd_30.png)

![](img/8e4382c49997b3dcee87c670c8d6aecd_31.png)

Running this query will result in an error indicating that no group by clause is specified。

We can circumvent this error by using the average function in a sub queryry placed in the list of the columns。



![](img/8e4382c49997b3dcee87c670c8d6aecd_33.png)

For example， select employee ID， Sal， open left parenthsesis。

 select average salary from employees closed right parenthsesis as average salary from employees。



![](img/8e4382c49997b3dcee87c670c8d6aecd_35.png)

Another option is to make the subquery be part of the from clause。



![](img/8e4382c49997b3dcee87c670c8d6aecd_37.png)

Subqueries like these are sometimes called derived tables or table expressions。

 because the outer query uses the results of the sub queryry as a data source。



![](img/8e4382c49997b3dcee87c670c8d6aecd_39.png)

![](img/8e4382c49997b3dcee87c670c8d6aecd_40.png)

Let's look at an example to create a table expression that contains non sensitiveensitive employee information。



![](img/8e4382c49997b3dcee87c670c8d6aecd_42.png)

![](img/8e4382c49997b3dcee87c670c8d6aecd_43.png)

Select star from selectEmploy ID， first name， last name。

 department ID from employees asEmploy for all。

![](img/8e4382c49997b3dcee87c670c8d6aecd_45.png)

The derived table in the subquery does not include sensitive fields like date of birth or salary。

This example is a trivial one， and we could just as easily have included the columns in the outer query。

 However， such derived tables can prove to be powerful in more complex situations。

 such as when working with multiple tables and doing joins。



![](img/8e4382c49997b3dcee87c670c8d6aecd_47.png)

In this video， you have seen how subqueries and nested queries can be used to form richer queries and how they can overcome some of the limitations of aggregate functions。



![](img/8e4382c49997b3dcee87c670c8d6aecd_49.png)

![](img/8e4382c49997b3dcee87c670c8d6aecd_50.png)

You also learn to use subqueries in the where clauses in the list of columns and in the from clauses。



![](img/8e4382c49997b3dcee87c670c8d6aecd_52.png)

Thanks for watching this video。