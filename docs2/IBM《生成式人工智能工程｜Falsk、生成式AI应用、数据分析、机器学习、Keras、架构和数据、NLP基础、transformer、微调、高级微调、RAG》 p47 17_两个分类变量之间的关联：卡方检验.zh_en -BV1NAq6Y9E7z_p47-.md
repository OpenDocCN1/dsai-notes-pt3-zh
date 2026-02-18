# IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p47 17_两个分类变量之间的关联：卡方检验.zh_en -BV1NAq6Y9E7z_p47-

In this video， we will learn how to find out if there is a relationship between two categorical variables。

When dealing with the relationships between two categorical variables。

 we can't use the same correlation method for continuous variables。

 We will have to employ the use of the Chii squared test for the association。

The chi square test is intended to test how likely it is that an observed distribution is due to chance。

It measures how well the observed distribution of data fits with the distribution that is expected if the variables are independent。

Before we go into an example， let's look through some important points。

The chi square tests a null hypothesis that the variables are independent。

The test compares the observed data to the values that the model expects if the data was distributed in different categories。

 by chance。Any time the observed data doesn't fit within the model of the expected values。

 the probability that the variables are dependent becomes stronger。

 thus proving the null hypothesis incorrect。The Chiis square does not tell you the type of relationship that exists between both variables。

 but only that a relationship exists。

![](img/0657af4b2f8f925df81279aff9c21958_1.png)

We will use the CA's data set， assuming we want to test the relationship between fuel type and aspiration。

 these are categorical variables。It is either the fuel type of the car， gas or diesel。

 And the aspiration is that either the car is standard or turbo。To do this。

 we will find the observed counts of cars in each category。This can be done by creating a cross tab。

 using the pandas library。A cross tab is a table showing the relationship between two or more variables。

When the table only shows the relationship between two categorical variables。

 the cross tab is also known as a contingency table。In our case。

 the cross tab or contingency table shows us the counts in each category。

A standard car with diesel fuel。A standard car with gas fuel。

 a turbo car with diesel fuel or a turbo car with gas fuel。

The formula for Chi Square is given as follows。The summation of the observed value， I。e。

 the counts in each group minus the expected value， all squared， divided by the expected value。

Expected values are based on the given totals。 That is。

 what can we say individual cells would be if we did not know the observed values。

To calculate the expected value of a standard car with diesel， we take the row total。

 which is 20 multiplied by the column total，168， divided by the grand total of 205。



![](img/0657af4b2f8f925df81279aff9c21958_3.png)

This will give you 16。39。 If we do the same thing for turbo cars with gas fuel。

 we will take the row total 185， multiplied by the column total 37。

 and we divide by the grand total of 205 to get 33。39。😊。

If we repeat the same procedure for all of them， we get these values。If we took the row totals。

 column totals and grand total， we will get the same values as the totals as the observed values。



![](img/0657af4b2f8f925df81279aff9c21958_5.png)

Now， going back to this formula， if we took a summation of all the observed minus the expected values all squared and divided by the expected value。

 we will get a chi square value of 33。2。On the Chi square table。

 we check on the degree of freedom equals  one row and find the value closest to 29。6。



![](img/0657af4b2f8f925df81279aff9c21958_7.png)

Here， we can see that 29。6 will fall in a P value less than 0。05。 Therefore。

 we can say the p value is less than 0。05。 Since the p value is less than 005。

 We reject the null hypothesis that the two variables are independent。 And therefore。

 we conclude that there is an association between fuel type and aspiration To do this in Python。

 we will use the chi square contingency function in the P psi pi dot statistics package。

 The function will print out the chi square test value 29。6。 The second value is the P value。

 which is very close to 0 and a degree of freedom of one。 If you remember。

 the chi square table did not give an exact P value， but a range in which it falls。

 Python will give the exact P value。 We can see the same results as in our previous slides。



![](img/0657af4b2f8f925df81279aff9c21958_9.png)

It also prints out the expected values， which we also calculated by hand。



![](img/0657af4b2f8f925df81279aff9c21958_11.png)

Since the P value is close to 0， we reject the null hypothesis that the two variables are independent and conclude that there is evidence of association between fuel type and aspiration。



![](img/0657af4b2f8f925df81279aff9c21958_13.png)