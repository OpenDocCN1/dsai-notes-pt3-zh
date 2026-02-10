# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P12：11_使用字符串模式和范围.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

![](img/56178b717cfc48258689e96643343010_0.png)

Hello and welcome to Retrieving data with select statement string patterns In this video。

 we will learn about some advanced techniques in retrieving data from a relational database table。

 At the end of this lesson， you will be able to describe how to simplify a select statement by using string patterns。

 ranges or sets of values。😊。

![](img/56178b717cfc48258689e96643343010_2.png)

![](img/56178b717cfc48258689e96643343010_3.png)

![](img/56178b717cfc48258689e96643343010_4.png)

![](img/56178b717cfc48258689e96643343010_5.png)

The main purpose of a database management system is not just to store the data。

 but also facilitate retrieval of the data in its simplest form。

 a select statement is select star from table name。



![](img/56178b717cfc48258689e96643343010_7.png)

Based on our simplified library database model and the table book。

 select star from book gives a result set of four rows。

 All the data rows for all columns in the table book are displayed。

 or you can retrieve a subset of columns。 for example， just two columns from the table book。

 such as book， underscore， I D and title。

![](img/56178b717cfc48258689e96643343010_9.png)

![](img/56178b717cfc48258689e96643343010_10.png)

![](img/56178b717cfc48258689e96643343010_11.png)

Or you can restrict the results set by using the wear clause。 For example。

 you can select the title of the book whose book underscore I D is B1。



![](img/56178b717cfc48258689e96643343010_13.png)

But what if we don't know exactly what value to specify in the wear clause？

The War clause always requires a predicate， which is a condition that evaluates to true。

 false or unknown。

![](img/56178b717cfc48258689e96643343010_15.png)

![](img/56178b717cfc48258689e96643343010_16.png)

But what if we don't know exactly what value the predicate is。



![](img/56178b717cfc48258689e96643343010_18.png)

For example， what if we can't remember the name of the author。

 but we remember that their first name starts with R。



![](img/56178b717cfc48258689e96643343010_20.png)

In a relational database， we can use string patterns to search data rows that match this condition。

Let's look at some examples of using string patterns。 If we can't remember the name of the author。

 but we remember that their name starts with R。 We use the wear clause with a like predicate。

 The like predicate is used in a wear clause to search for a pattern in a column。

The percent sign is used to define missing letters。

The percent sign can be placed before the pattern after the pattern or both before and after the pattern。

In this example， we use the percent sign after the pattern， which is the letter R。

 The percent sign is called a wild card character。A wild card character is used to substitute other characters。

So if we can't remember the name of the author， but we can remember that their first name starts with the letter R。

 we add the like predicate to the wear cloths。

![](img/56178b717cfc48258689e96643343010_22.png)

![](img/56178b717cfc48258689e96643343010_23.png)

For example， select first name from author where first name like R percentile。



![](img/56178b717cfc48258689e96643343010_25.png)

This will return all rows in the author table whose author's first name starts with the letter R。

 And here is the result set。 Two rows a return for authors， Raoul and Rph。



![](img/56178b717cfc48258689e96643343010_27.png)

![](img/56178b717cfc48258689e96643343010_28.png)

![](img/56178b717cfc48258689e96643343010_29.png)

What if we wanted to retrieve the list of books whose number of pages is more than 290。

 but less than 300。

![](img/56178b717cfc48258689e96643343010_31.png)

We could write the select statement like this， specifying the where clause as where pages is greater than or equal to 290。

 and pages is less than or equal to 300。

![](img/56178b717cfc48258689e96643343010_33.png)

![](img/56178b717cfc48258689e96643343010_34.png)

But in a relational database， we can use a range of numbers to specify the same condition。



![](img/56178b717cfc48258689e96643343010_36.png)

![](img/56178b717cfc48258689e96643343010_37.png)

Instead of using the comparison operators greater than or equal to。

 we use the comparison operator between and。

![](img/56178b717cfc48258689e96643343010_39.png)

Between and compares two values。 The values in the range are inclusive。



![](img/56178b717cfc48258689e96643343010_41.png)

In this case， we rewrite the query to specify the wear clause as where pages between 290 and 300。

 The result set is the same， but the select statement is easier and quicker to write。



![](img/56178b717cfc48258689e96643343010_43.png)

![](img/56178b717cfc48258689e96643343010_44.png)

![](img/56178b717cfc48258689e96643343010_45.png)

In some cases， there are data values that cannot be grouped under ranges。 For example。

 if we want to know which countries the authors are from。



![](img/56178b717cfc48258689e96643343010_47.png)

If we wanted to retrieve authors from Australia or Brazil。

 we could write the select statement with the Ware clause repeating the two country values。



![](img/56178b717cfc48258689e96643343010_49.png)

![](img/56178b717cfc48258689e96643343010_50.png)

However， what if we want to retrieve authors from Canada， India and China。



![](img/56178b717cfc48258689e96643343010_52.png)

The weare claws would become very long， repeatedly listing the required country conditions。



![](img/56178b717cfc48258689e96643343010_54.png)

Instead， we can use the in operator。 The in operator allows us to specify a set of values in a where clause。



![](img/56178b717cfc48258689e96643343010_56.png)

![](img/56178b717cfc48258689e96643343010_57.png)

This operator takes a list of expressions to compare against。 In this case。

 the countrys Australia or Brazil。

![](img/56178b717cfc48258689e96643343010_59.png)

Now， you can describe how to simplify a select statement by using string patterns。

 ranges or sets of values。

![](img/56178b717cfc48258689e96643343010_61.png)

Thanks for watching this video。

![](img/56178b717cfc48258689e96643343010_63.png)