# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P12：11_字符串模式与范围查询.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

![](img/98654e0c9ac31f9b0d58ca614c239e66_0.png)

Hello and welcome to Retrieving data with select statement string patterns In this video。

 we will learn about some advanced techniques in retrieving data from a relational database table。

 At the end of this lesson， you will be able to describe how to simplify a select statement by using string patterns。

 ranges or sets of values。😊。

![](img/98654e0c9ac31f9b0d58ca614c239e66_2.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_3.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_4.png)

The main purpose of a database management system is not just to store the data。

 but also facilitate retrieval of the data in its simplest form。

 a select statement is select star from table name。



![](img/98654e0c9ac31f9b0d58ca614c239e66_6.png)

Based on our simplified library database model and the table book。

 select star from book gives a result set of four rows。

 All the data rows for all columns in the table book are displayed。

 or you can retrieve a subset of columns。 for example， just two columns from the table book。

 such as book， underscore I D and title。

![](img/98654e0c9ac31f9b0d58ca614c239e66_8.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_9.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_10.png)

Or you can restrict the results set by using the wear clause。 For example。

 you can select the title of the book whose book underscore ID D is B1。

But what if we don't know exactly what value to specify in the wear clause。



![](img/98654e0c9ac31f9b0d58ca614c239e66_12.png)

The wear clause always requires a predicate， which is a condition that evaluates to true。

 false or unknown。

![](img/98654e0c9ac31f9b0d58ca614c239e66_14.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_15.png)

But what if we don't know exactly what value the predicate is。



![](img/98654e0c9ac31f9b0d58ca614c239e66_17.png)

For example， what if we can't remember the name of the author。

 but we remember that their first name starts with R。



![](img/98654e0c9ac31f9b0d58ca614c239e66_19.png)

In a relational database， we can use string patterns to search data rows that match this condition。

Let's look at some examples of using string patterns。 If we can't remember the name of the author。

 but we remember that their name starts with R。 We use the wear clauses with a like predicate。

The like predicate is used in a wear clauses to search for a pattern in a column。

The percent sign is used to define missing letters。

The percent sign can be placed before the pattern after the pattern or both before and after the pattern。

In this example， we use the percent sign after the pattern， which is the letter R。

 The percent sign is called a wild card character。A wild card character is used to substitute other characters。

So if we can't remember the name of the author， but we can remember that their first name starts with the letter R。

 we add the like predicate to the wear cloths。

![](img/98654e0c9ac31f9b0d58ca614c239e66_21.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_22.png)

For example， select first name from author where first name like R percentile。



![](img/98654e0c9ac31f9b0d58ca614c239e66_24.png)

This will return all rows in the author table whose author's first name starts with the letter R。

 And here is the result set。 Two rows are returned for authors， Raoul and Rph。



![](img/98654e0c9ac31f9b0d58ca614c239e66_26.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_27.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_28.png)

What if we wanted to retrieve the list of books whose number of pages is more than 290。

 but less than 300。

![](img/98654e0c9ac31f9b0d58ca614c239e66_30.png)

We could write the select statement like this specifying the where clause as where pages is greater than or equal to 290。

 and pages is less than or equal to 300。

![](img/98654e0c9ac31f9b0d58ca614c239e66_32.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_33.png)

But in a relational database， we can use a range of numbers to specify the same condition。



![](img/98654e0c9ac31f9b0d58ca614c239e66_35.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_36.png)

Instead of using the comparison operators greater than or equal to。

 we use the comparison operator between and。

![](img/98654e0c9ac31f9b0d58ca614c239e66_38.png)

Between and compares two values。 The values in the range are inclusive。



![](img/98654e0c9ac31f9b0d58ca614c239e66_40.png)

In this case， we rewrite the query to specify the where clause as where pages between 290 and 300。

 The result set is the same， but the select statement is easier and quicker to write。 In some cases。

 there are data values that cannot be grouped under ranges。 For example。

 if we want to know which countries the authors are from。



![](img/98654e0c9ac31f9b0d58ca614c239e66_42.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_43.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_44.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_45.png)

If we wanted to retrieve authors from Australia or Brazil。

 we could write the select statement with the Ware clauseuse repeating the two country values。



![](img/98654e0c9ac31f9b0d58ca614c239e66_47.png)

![](img/98654e0c9ac31f9b0d58ca614c239e66_48.png)

However， what if we want to retrieve authors from Canada， India and China。



![](img/98654e0c9ac31f9b0d58ca614c239e66_50.png)

The weare clauses would become very long， repeatedly listing the required country conditions。



![](img/98654e0c9ac31f9b0d58ca614c239e66_52.png)

Instead， we can use the in operator。 The in operator allows us to specify a set of values in a where clause。



![](img/98654e0c9ac31f9b0d58ca614c239e66_54.png)

This operator takes a list of expressions to compare against。 In this case。

 the country Australia or Brazil。Now， you can describe how to simplify a select statement by using string patterns。

 ranges or sets of values。

![](img/98654e0c9ac31f9b0d58ca614c239e66_56.png)

Thanks for watching this video。

![](img/98654e0c9ac31f9b0d58ca614c239e66_58.png)