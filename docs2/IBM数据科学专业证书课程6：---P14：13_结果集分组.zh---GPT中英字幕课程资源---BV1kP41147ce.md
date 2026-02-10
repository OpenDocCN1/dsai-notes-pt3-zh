# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P14：13_结果集分组.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

![](img/b3b9c8dd03b77b36b21ee3debec16021_0.png)

Hello and welcome to grouping select statement result sets In this video。

 we will learn about some advanced techniques in retrieving data from a relational database table and sorting and grouping how the result set displays at the end of this lesson。

 you will be able to explain how to eliminate duplicates from a result set and describe how to further restrict a result set。

😊。

![](img/b3b9c8dd03b77b36b21ee3debec16021_2.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_3.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_4.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_5.png)

At times， a select statement result set can contain duplicate values based on our simplified library database model in the author table example。

 the country column lists the two letter country code of the author's country。



![](img/b3b9c8dd03b77b36b21ee3debec16021_7.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_8.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_9.png)

If we select just the country column， we get a list of all of the countries。 For example。

 select country from author order by one。 The order by clause sorts the results set。



![](img/b3b9c8dd03b77b36b21ee3debec16021_11.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_12.png)

This result set lists the countries that authors belong to， sorted alphabetically by country。

 In this case， the result set displays 20 rows，1 row for each of the 20 authors。

 But some of the authors come from the same country。 So the result set contains duplicates。



![](img/b3b9c8dd03b77b36b21ee3debec16021_14.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_15.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_16.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_17.png)

However， all we need is a list of countries the authors come from。 So in this case。

 duplicates do not make sense。

![](img/b3b9c8dd03b77b36b21ee3debec16021_19.png)

To eliminate duplicates， we use the keyword distinct。



![](img/b3b9c8dd03b77b36b21ee3debec16021_21.png)

Using the keyword distinct reduces the results set to just six rows。



![](img/b3b9c8dd03b77b36b21ee3debec16021_23.png)

But what if we wanted to also know how many authors come from the same country。



![](img/b3b9c8dd03b77b36b21ee3debec16021_25.png)

So now we know that the 20 authors come from six different countries。



![](img/b3b9c8dd03b77b36b21ee3debec16021_27.png)

But we might want to also know how many authors come from the same country。



![](img/b3b9c8dd03b77b36b21ee3debec16021_29.png)

To display the results set listing the country and number of authors that come from that country。

 we add the group by clause to the select statement。



![](img/b3b9c8dd03b77b36b21ee3debec16021_31.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_32.png)

The group by clause groups result into subsets that has matching values for one or more columns。

 In this example， countries are grouped and then counted using the count function。

 Notice the column heading for the second column in the result set。 The numeric value。

 too displays as a column name because the column name is not directly available in the table。

 The second column in the result set was calculated by the count function。



![](img/b3b9c8dd03b77b36b21ee3debec16021_34.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_35.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_36.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_37.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_38.png)

Instead of using the column name too， we can assign a column name to the result set。



![](img/b3b9c8dd03b77b36b21ee3debec16021_40.png)

We do this using the as keyword。 In this example， we change the derived column name 2 to column name count using the as count keyword。

 This helps clarify the meaning of the result set。

![](img/b3b9c8dd03b77b36b21ee3debec16021_42.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_43.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_44.png)

Now that we have the count of authors from different countries。

 we can further restrict the number of rows by passing some conditions。 For example。

 we can check if there are more than four authors from the same country to set a condition to a group by clause。

 we use the key word having。

![](img/b3b9c8dd03b77b36b21ee3debec16021_46.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_47.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_48.png)

The havinglving clause is used in combination with the group by clause。

 It is very important to note that the where clause is for the entire result set。

 but the having clause works only with the group by clause。



![](img/b3b9c8dd03b77b36b21ee3debec16021_50.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_51.png)

To check if there are more than four authors from the same country。

 we add the following to the select statement， Having count country greater than4。

 Only countries that have five or more authors from that country are listed in the results set。



![](img/b3b9c8dd03b77b36b21ee3debec16021_53.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_54.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_55.png)

In this example， those countries are China with six authors and India， also with six authors。



![](img/b3b9c8dd03b77b36b21ee3debec16021_57.png)

![](img/b3b9c8dd03b77b36b21ee3debec16021_58.png)

Now you can explain how to eliminate duplicates from a result set and describe how to further restrict a result set。



![](img/b3b9c8dd03b77b36b21ee3debec16021_60.png)

Thanks for watching this video。

![](img/b3b9c8dd03b77b36b21ee3debec16021_62.png)