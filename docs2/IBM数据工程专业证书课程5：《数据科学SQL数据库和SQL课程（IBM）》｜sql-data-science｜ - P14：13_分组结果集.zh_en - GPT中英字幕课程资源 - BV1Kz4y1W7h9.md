# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P14：13_分组结果集.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

![](img/2b293320e2298e9630af6877d2fecd7f_0.png)

Hello and welcome to grouping select statement result sets In this video。

 we will learn about some advanced techniques in retrieving data from a relational database table and sorting and grouping how the result set displays at the end of this lesson。

 you will be able to explain how to eliminate duplicates from a result set and describe how to further restrict a result set。

😊。

![](img/2b293320e2298e9630af6877d2fecd7f_2.png)

![](img/2b293320e2298e9630af6877d2fecd7f_3.png)

![](img/2b293320e2298e9630af6877d2fecd7f_4.png)

![](img/2b293320e2298e9630af6877d2fecd7f_5.png)

At times， a select statement result set can contain duplicate values based on our simplified library database model in the author table example。

 the country column lists the two letter country code of the author's country。



![](img/2b293320e2298e9630af6877d2fecd7f_7.png)

![](img/2b293320e2298e9630af6877d2fecd7f_8.png)

![](img/2b293320e2298e9630af6877d2fecd7f_9.png)

If we select just the country column， we get a list of all of the countries。 For example。

 select country from author order by one。 The order by clause sorts the result set。



![](img/2b293320e2298e9630af6877d2fecd7f_11.png)

![](img/2b293320e2298e9630af6877d2fecd7f_12.png)

This result set lists the countries that authors belong to， sorted alphabetically by country。

 In this case， the result set displays 20 rows，1 row for each of the 20 authors。

 But some of the authors come from the same country。 So the result set contains duplicates。



![](img/2b293320e2298e9630af6877d2fecd7f_14.png)

![](img/2b293320e2298e9630af6877d2fecd7f_15.png)

![](img/2b293320e2298e9630af6877d2fecd7f_16.png)

![](img/2b293320e2298e9630af6877d2fecd7f_17.png)

However， all we need is a list of countries the authors come from。 So in this case。

 duplicates do not make sense。

![](img/2b293320e2298e9630af6877d2fecd7f_19.png)

To eliminate duplicates， we use the keyword distinct。



![](img/2b293320e2298e9630af6877d2fecd7f_21.png)

Using the keyword distinct reduces the results set to just six rows。



![](img/2b293320e2298e9630af6877d2fecd7f_23.png)

But what if we wanted to also know how many authors come from the same country。



![](img/2b293320e2298e9630af6877d2fecd7f_25.png)

So now we know that the 20 authors come from six different countries。



![](img/2b293320e2298e9630af6877d2fecd7f_27.png)

But we might want to also know how many authors come from the same country。



![](img/2b293320e2298e9630af6877d2fecd7f_29.png)

To display the results set listing the country and number of authors that come from that country。

 we add the group by clause to the select statement。



![](img/2b293320e2298e9630af6877d2fecd7f_31.png)

![](img/2b293320e2298e9630af6877d2fecd7f_32.png)

The group by clause groups result into subsets that has matching values for one or more columns。

 In this example， countries are grouped and then counted using the count function。

 Notice the column heading for the second column in the result set。 The numeric value。

 too displays as a column name because the column name is not directly available in the table。

 The second column in the result set was calculated by the count function。



![](img/2b293320e2298e9630af6877d2fecd7f_34.png)

![](img/2b293320e2298e9630af6877d2fecd7f_35.png)

![](img/2b293320e2298e9630af6877d2fecd7f_36.png)

![](img/2b293320e2298e9630af6877d2fecd7f_37.png)

![](img/2b293320e2298e9630af6877d2fecd7f_38.png)

Instead of using the column name too， we can assign a column name to the result set。



![](img/2b293320e2298e9630af6877d2fecd7f_40.png)

We do this using the as keyword。 In this example， we change the derived column name 2 to column name count using the as count keyword。

 This helps clarify the meaning of the result set。

![](img/2b293320e2298e9630af6877d2fecd7f_42.png)

![](img/2b293320e2298e9630af6877d2fecd7f_43.png)

![](img/2b293320e2298e9630af6877d2fecd7f_44.png)

Now that we have the count of authors from different countries。

 we can further restrict the number of rows by passing some conditions。 For example。

 we can check if there are more than four authors from the same country to set a condition to a group by clause。

 we use the key word having。

![](img/2b293320e2298e9630af6877d2fecd7f_46.png)

![](img/2b293320e2298e9630af6877d2fecd7f_47.png)

![](img/2b293320e2298e9630af6877d2fecd7f_48.png)

The having clause is used in combination with the group by clause。

 It is very important to note that the where clause is for the entire result set。

 but the having clause works only with the group by clause。



![](img/2b293320e2298e9630af6877d2fecd7f_50.png)

![](img/2b293320e2298e9630af6877d2fecd7f_51.png)

To check if there are more than four authors from the same country。

 we add the following to the select statement， Having count country greater than4。

 Only countries that have five or more authors from that country are listed in the results set。



![](img/2b293320e2298e9630af6877d2fecd7f_53.png)

![](img/2b293320e2298e9630af6877d2fecd7f_54.png)

![](img/2b293320e2298e9630af6877d2fecd7f_55.png)

In this example， those countries are China with six authors and India， also with six authors。



![](img/2b293320e2298e9630af6877d2fecd7f_57.png)

![](img/2b293320e2298e9630af6877d2fecd7f_58.png)

Now you can explain how to eliminate duplicates from a result set and describe how to further restrict a result set。



![](img/2b293320e2298e9630af6877d2fecd7f_60.png)

Thanks for watching this video。

![](img/2b293320e2298e9630af6877d2fecd7f_62.png)