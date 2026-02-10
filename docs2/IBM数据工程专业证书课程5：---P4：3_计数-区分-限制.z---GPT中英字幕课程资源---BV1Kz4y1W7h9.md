# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P4：3_计数 区分 限制.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

🎼。Hello and welcome In this video， we'll briefly present a few useful expressions that are used with select statements。

😊。

![](img/94ba41dd7272c423c64a89ef24d0f92b_1.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_2.png)

The first one is count。Cot is a built in database function that retrieves the number of rows that match the query criteria。



![](img/94ba41dd7272c423c64a89ef24d0f92b_4.png)

For example， get the total number of rows in a given table。Select cow star from table name。



![](img/94ba41dd7272c423c64a89ef24d0f92b_6.png)

Let's say you create a table called Meals， which has a column called country。

 and you want to retrieve the number of rows where the metal recipient is from Canada。



![](img/94ba41dd7272c423c64a89ef24d0f92b_8.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_9.png)

You can issue a query like this。 Select count Count from medals where country equals Canada。



![](img/94ba41dd7272c423c64a89ef24d0f92b_11.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_12.png)

The second expression is distinct。 distinctct is used to remove duplicate values from a result set。

 example to retrieve unique values in a column。 Select distinct column name from table name。



![](img/94ba41dd7272c423c64a89ef24d0f92b_14.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_15.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_16.png)

In the medals table mentioned earlier， a country may have received a gold medal multiple times。



![](img/94ba41dd7272c423c64a89ef24d0f92b_18.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_19.png)

Example retrieved the list of unique countries that received gold medals。

 That is removing all duplicate values of the same country。



![](img/94ba41dd7272c423c64a89ef24d0f92b_21.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_22.png)

Select distinct country from metals where metal typed equals gold。



![](img/94ba41dd7272c423c64a89ef24d0f92b_24.png)

The third expression is limit。 Liit is used for restricting the number of rows retrieved from the database。

 examplele， retrieve just the first 10 rows in a table。



![](img/94ba41dd7272c423c64a89ef24d0f92b_26.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_27.png)

Select star from table name limitit 10。

![](img/94ba41dd7272c423c64a89ef24d0f92b_29.png)

This can be very useful to examine the result set by looking at just a few rows instead of retrieving the entire result set。

 which may be very large。

![](img/94ba41dd7272c423c64a89ef24d0f92b_31.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_32.png)

Example retrieved just a few rows in the metals table for a particular year。



![](img/94ba41dd7272c423c64a89ef24d0f92b_34.png)

![](img/94ba41dd7272c423c64a89ef24d0f92b_35.png)

Select star from Mes where year equals 2018， limit 5。



![](img/94ba41dd7272c423c64a89ef24d0f92b_37.png)

In this video， we looked at some useful expressions that are used with select statements。

 namely the count， distinct and limit built in functions。😊，Thanks for watching this video。



![](img/94ba41dd7272c423c64a89ef24d0f92b_39.png)