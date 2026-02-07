# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P15：14_内置数据库函数.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

🎼。Hello and welcome。In this video， we'll go over SQL functions built into the database。

 so let's get started。

![](img/28564982fe25b3b2fe488956586ca822_1.png)

![](img/28564982fe25b3b2fe488956586ca822_2.png)

While it is very much possible to first fetch data from a database and then perform operations on it from your applications and notebooks。

 most databases come with built in functions。

![](img/28564982fe25b3b2fe488956586ca822_4.png)

![](img/28564982fe25b3b2fe488956586ca822_5.png)

These functions can be included in SQL statements， allowing you to perform operations on data right within the database itself。



![](img/28564982fe25b3b2fe488956586ca822_7.png)

Using database functions can significantly reduce the amount of data that needs to be retrieved from the database。

 that is， reduces network traffic and use of bandwidth。When working with large datasets。

 it may be faster to use built in functions rather than first retrieving the data into your application and then executing functions on the retrieve data Note that it is also possible to create your own functions。

 that is user definedfined functions in the database， but that is a more advanced topic。

For the examples in this lesson， let's consider this pet rescue table in the database for a pet rescue organization。



![](img/28564982fe25b3b2fe488956586ca822_9.png)

![](img/28564982fe25b3b2fe488956586ca822_10.png)

It records rescue transaction details and includes the columns， ID， animal， quantity， cost。

 and rescue date for the purposes of this lesson， we have populated it with several rows of data as shown here。



![](img/28564982fe25b3b2fe488956586ca822_12.png)

![](img/28564982fe25b3b2fe488956586ca822_13.png)

![](img/28564982fe25b3b2fe488956586ca822_14.png)

What are aggregate or column functions， An aggregate function takes a collection of like values。

 such as all of the values in a column as input and returns a single value or null。



![](img/28564982fe25b3b2fe488956586ca822_16.png)

![](img/28564982fe25b3b2fe488956586ca822_17.png)

Examples of aggregate functions include sum， minimum， maximum， average， etc。

 Let's look at some examples based on the pet rescue table。



![](img/28564982fe25b3b2fe488956586ca822_19.png)

The sum function is used to add up all the values in a column to use the function。

 you write the column name within parentheses after the function name。



![](img/28564982fe25b3b2fe488956586ca822_21.png)

![](img/28564982fe25b3b2fe488956586ca822_22.png)

For example， to add up all of the values in the cost column， select some cost from Pet Rescue。



![](img/28564982fe25b3b2fe488956586ca822_24.png)

![](img/28564982fe25b3b2fe488956586ca822_25.png)

When you use an aggregate function， the column in the result set by default is given a number。

 It is possible to explicitly name the resulting column。 For example。

 let's say we want to call the output column in the previous query as sum of cost。

 Select sum cost as sum of cost from pet rescue。 Note the use of as in this example。



![](img/28564982fe25b3b2fe488956586ca822_27.png)

![](img/28564982fe25b3b2fe488956586ca822_28.png)

![](img/28564982fe25b3b2fe488956586ca822_29.png)

![](img/28564982fe25b3b2fe488956586ca822_30.png)

![](img/28564982fe25b3b2fe488956586ca822_31.png)

![](img/28564982fe25b3b2fe488956586ca822_32.png)

Minimum， as the name implies， is used to get the lowest value， Similarlyly。

 maximum is used to get the highest value， for example。

 to get the maximum quantity of any animal rescue in a single transaction。

 select Max quantity from Pet Recue。

![](img/28564982fe25b3b2fe488956586ca822_34.png)

![](img/28564982fe25b3b2fe488956586ca822_35.png)

![](img/28564982fe25b3b2fe488956586ca822_36.png)

Agreggate functions can also be applied on a subset of data instead of an entire column， for example。

 to get the minimum quantity of I column for dogs， select Min IDd from pet rescuescu where animal equals dog。



![](img/28564982fe25b3b2fe488956586ca822_38.png)

![](img/28564982fe25b3b2fe488956586ca822_39.png)

![](img/28564982fe25b3b2fe488956586ca822_40.png)

The average function is used to return the average or the mean value， for example。

 to specify the average value of cost as select average cost from pet Recue。



![](img/28564982fe25b3b2fe488956586ca822_42.png)

![](img/28564982fe25b3b2fe488956586ca822_43.png)

![](img/28564982fe25b3b2fe488956586ca822_44.png)

Note that we can perform mathematical operations between columns and then apply aggregate functions on them。

 for example， to calculate the average cost per dog。



![](img/28564982fe25b3b2fe488956586ca822_46.png)

![](img/28564982fe25b3b2fe488956586ca822_47.png)

![](img/28564982fe25b3b2fe488956586ca822_48.png)

Select average cost divided by quantity from pet rescue where animal equals dog。In this case。

 the cost is for multiple units， so we first divide the cost by the quantity of the rescue。

Now let's look at the scalar and string functions。 Scalar functions perform operations on individual values。

 for example， to round up or down every value in the cost column to the nearest integer。

 select round cost from pet rescue。

![](img/28564982fe25b3b2fe488956586ca822_50.png)

There is a class of scalar functions called string functions that can be used for operations on strings that is car and VarA values。



![](img/28564982fe25b3b2fe488956586ca822_52.png)

![](img/28564982fe25b3b2fe488956586ca822_53.png)

For example， to retrieve the length of each value in animal column， selectLth Anim from pet Rescue。

Uppercase and lowercase functions can be used to return uppercase or lowercase values of strings。

 for example， to retrieve animal values in uppercase， select uppercase animal from pet rescue。



![](img/28564982fe25b3b2fe488956586ca822_55.png)

![](img/28564982fe25b3b2fe488956586ca822_56.png)

![](img/28564982fe25b3b2fe488956586ca822_57.png)

Scaalar functions can be used in the wear clauses， for example。

 to get lowercase values of the animal column for cat。

 select star from pet Recue where lowercase animal equals cat。



![](img/28564982fe25b3b2fe488956586ca822_59.png)

![](img/28564982fe25b3b2fe488956586ca822_60.png)

![](img/28564982fe25b3b2fe488956586ca822_61.png)

This type of a statement is useful for matching values in the wear clause if you are not sure whether the values are stored in upper。

 lower or mixed case in the table。You can also have one function operate on the output of another function。

 for example， to get unique cases for animal column in uppercase。

 select distinct uppercase An from Pe Rescue。

![](img/28564982fe25b3b2fe488956586ca822_63.png)

![](img/28564982fe25b3b2fe488956586ca822_64.png)

![](img/28564982fe25b3b2fe488956586ca822_65.png)

![](img/28564982fe25b3b2fe488956586ca822_66.png)

In this video we looked at some built in SQL aggregate functions， such as sum， minimum。

 maximum and average， we also looked at scalar and string functions such as round。

 lowercase and uppercase Thank you for watching。

![](img/28564982fe25b3b2fe488956586ca822_68.png)

![](img/28564982fe25b3b2fe488956586ca822_69.png)

![](img/28564982fe25b3b2fe488956586ca822_70.png)