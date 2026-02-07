# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P15：14_内置数据库函数.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

。Hello and welcome。In this video， we'll go over SQL functions built into the database。

 so let's get started。

![](img/94957eef39b55bdf2096945069ff0e89_1.png)

![](img/94957eef39b55bdf2096945069ff0e89_2.png)

While it is very much possible to first fetch data from a database and then perform operations on it from your applications and notebooks。

 most databases come with built in functions。

![](img/94957eef39b55bdf2096945069ff0e89_4.png)

![](img/94957eef39b55bdf2096945069ff0e89_5.png)

These functions can be included in SQL statements， allowing you to perform operations on data right within the database itself。



![](img/94957eef39b55bdf2096945069ff0e89_7.png)

![](img/94957eef39b55bdf2096945069ff0e89_8.png)

Using database functions can significantly reduce the amount of data that needs to be retrieved from the database。

 that is， reduces network traffic and use of bandwidth。When working with large datasets。

 it may be faster to use built in functions， rather than first retrieving the data into your application and then executing functions on the retrieved data Note that it is also possible to create your own functions。

 that is user definedfined functions in the database， but that is a more advanced topic。

For the examples in this lesson， let's consider this pet rescue table in the database for a pet rescue organization。



![](img/94957eef39b55bdf2096945069ff0e89_10.png)

![](img/94957eef39b55bdf2096945069ff0e89_11.png)

It records rescue transaction details and includes the columns， ID， animal， quantity， cost。

 and rescue date for the purposes of this lesson， we have populated it with several rows of data as shown here。



![](img/94957eef39b55bdf2096945069ff0e89_13.png)

![](img/94957eef39b55bdf2096945069ff0e89_14.png)

![](img/94957eef39b55bdf2096945069ff0e89_15.png)

What are aggregate or column functions， An aggregate function takes a collection of like values。

 such as all of the values in a column as input and returns a single value or null。



![](img/94957eef39b55bdf2096945069ff0e89_17.png)

![](img/94957eef39b55bdf2096945069ff0e89_18.png)

Examples of aggregate functions include sum， minimum， maximum， average， etc。

 Let's look at some examples based on the pet rescue table。

The sum function is used to add up all the values in a column to use the function。

 you write the column name within parentheses after the function name。



![](img/94957eef39b55bdf2096945069ff0e89_20.png)

![](img/94957eef39b55bdf2096945069ff0e89_21.png)

For example， to add up all of the values in the cost column， select some cost from Pet Rescue。



![](img/94957eef39b55bdf2096945069ff0e89_23.png)

![](img/94957eef39b55bdf2096945069ff0e89_24.png)

When you use an aggregate function， the column in the result set by default is given a number。

 It is possible to explicitly name the resulting column。 For example。

 let's say we want to call the output column in the previous query as sum of cost。

 Select sum cost as sum of cost from Pe rescue。 Note the use of as in this example。



![](img/94957eef39b55bdf2096945069ff0e89_26.png)

![](img/94957eef39b55bdf2096945069ff0e89_27.png)

![](img/94957eef39b55bdf2096945069ff0e89_28.png)

![](img/94957eef39b55bdf2096945069ff0e89_29.png)

![](img/94957eef39b55bdf2096945069ff0e89_30.png)

![](img/94957eef39b55bdf2096945069ff0e89_31.png)

Minimum， as the name implies， is used to get the lowest value， Similarlyly。

 maximum is used to get the highest value， for example。

 to get the maximum quantity of any animal rescue in a single transaction。

 select Max quantity from Pet rescuecu。

![](img/94957eef39b55bdf2096945069ff0e89_33.png)

![](img/94957eef39b55bdf2096945069ff0e89_34.png)

![](img/94957eef39b55bdf2096945069ff0e89_35.png)

![](img/94957eef39b55bdf2096945069ff0e89_36.png)

Agreggate functions can also be applied on a subset of data instead of an entire column， for example。

 to get the minimum quantity of I column for dogs， select Min IDd from pet rescuecu where animal equals dog。



![](img/94957eef39b55bdf2096945069ff0e89_38.png)

![](img/94957eef39b55bdf2096945069ff0e89_39.png)

![](img/94957eef39b55bdf2096945069ff0e89_40.png)

The average function is used to return the average or the mean value， for example。

 to specify the average value of cost as select average cost from pet rescue。



![](img/94957eef39b55bdf2096945069ff0e89_42.png)

![](img/94957eef39b55bdf2096945069ff0e89_43.png)

![](img/94957eef39b55bdf2096945069ff0e89_44.png)

Note that we can perform mathematical operations between columns and then apply aggregate functions on them。

 for example， to calculate the average cost per dog。



![](img/94957eef39b55bdf2096945069ff0e89_46.png)

![](img/94957eef39b55bdf2096945069ff0e89_47.png)

![](img/94957eef39b55bdf2096945069ff0e89_48.png)

Select average cost divided by quantity from pet rescue where animal equals dog。In this case。

 the cost is for multiple units， so we first divide the cost by the quantity of the rescue。

Now let's look at the scalar and string functions。 Scalar functions perform operations on individual values。

 for example， to round up or down every value in the cost column to the nearest integer。

 select round cost from Pe rescue。

![](img/94957eef39b55bdf2096945069ff0e89_50.png)

There is a class of scalar functions called string functions that can be used for operations on strings that is car and VarA values。



![](img/94957eef39b55bdf2096945069ff0e89_52.png)

![](img/94957eef39b55bdf2096945069ff0e89_53.png)

For example， to retrieve the length of each value in animal column， selectLth Anim from Pe Rescue。

Uppercase and lowercase functions can be used to return uppercase or lowercase values of strings。

 for example， to retrieve animal values in uppercase， select uppercase animal from pet rescue。



![](img/94957eef39b55bdf2096945069ff0e89_55.png)

![](img/94957eef39b55bdf2096945069ff0e89_56.png)

![](img/94957eef39b55bdf2096945069ff0e89_57.png)

Scaalar functions can be used in the wear clauses， for example。

 to get lowercase values of the animal column for cat。

 select star from pet Ree where lowercase animal equals cat。



![](img/94957eef39b55bdf2096945069ff0e89_59.png)

![](img/94957eef39b55bdf2096945069ff0e89_60.png)

![](img/94957eef39b55bdf2096945069ff0e89_61.png)

This type of a statement is useful for matching values in the wear clauses if you are not sure whether the values are stored in upper。

 lower or mixed case in the table。You can also have one function operate on the output of another function。

 for example， to get unique cases for animal column in uppercase。

 select distinct uppercase An from Pe Rescue。

![](img/94957eef39b55bdf2096945069ff0e89_63.png)

![](img/94957eef39b55bdf2096945069ff0e89_64.png)

![](img/94957eef39b55bdf2096945069ff0e89_65.png)

![](img/94957eef39b55bdf2096945069ff0e89_66.png)

In this video we looked at some built in SQL aggregate functions such as sum， minimum。

 maximum and average。 we also looked at scalar and string functions such as round。

 lowercase and uppercase Thank you for watching。

![](img/94957eef39b55bdf2096945069ff0e89_68.png)

![](img/94957eef39b55bdf2096945069ff0e89_69.png)

![](img/94957eef39b55bdf2096945069ff0e89_70.png)