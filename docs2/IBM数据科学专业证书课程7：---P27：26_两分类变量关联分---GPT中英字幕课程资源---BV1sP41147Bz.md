# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P27：26_两分类变量关联分析（卡方检验）.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we will learn how to find out if there is a relationship between two categorical variables。



![](img/1fb001f0650f98d8c34f08457acdd8eb_1.png)

When dealing with the relationships between two categorical variables。

 we can't use the same correlation method for continuous variables。

 We will have to employ the use of the Chii squared test for the association。



![](img/1fb001f0650f98d8c34f08457acdd8eb_3.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_4.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_5.png)

The chi square test is intended to test how likely it is that an observed distribution is due to chance。



![](img/1fb001f0650f98d8c34f08457acdd8eb_7.png)

It measures how well the observed distribution of data fits with the distribution that is expected if the variables are independent。



![](img/1fb001f0650f98d8c34f08457acdd8eb_9.png)

Before we go into an example， let's look through some important points。



![](img/1fb001f0650f98d8c34f08457acdd8eb_11.png)

The chi square tests a null hypothesis that the variables are independent。



![](img/1fb001f0650f98d8c34f08457acdd8eb_13.png)

The test compares the observed data to the values the model expects if the data was distributed in different categories。

 by chance。

![](img/1fb001f0650f98d8c34f08457acdd8eb_15.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_16.png)

Any time the observed data doesn't fit within the model of the expected values。

 the probability that the variables are dependent becomes stronger。

 thus proving the null hypothesis incorrect。

![](img/1fb001f0650f98d8c34f08457acdd8eb_18.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_19.png)

The Chiis square does not tell you the type of relationship that exists between both variables。

 but only that a relationship exists。We will use the CA's data set。

 assuming we want to test the relationship between fuel type and aspiration。

 these are categorical variables。

![](img/1fb001f0650f98d8c34f08457acdd8eb_21.png)

It is either the fuel type of the car， gas or diesel。

 And the aspiration is that either the car is standard or turbo。



![](img/1fb001f0650f98d8c34f08457acdd8eb_23.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_24.png)

To do this， we will find the observed counts of cars in each category。



![](img/1fb001f0650f98d8c34f08457acdd8eb_26.png)

This can be done by creating a cross tab， using the panda's library。



![](img/1fb001f0650f98d8c34f08457acdd8eb_28.png)

A cross tab is a table showing the relationship between two or more variables。



![](img/1fb001f0650f98d8c34f08457acdd8eb_30.png)

When the table only shows the relationship between two categorical variables。

 the cross tab is also known as a contingency table。



![](img/1fb001f0650f98d8c34f08457acdd8eb_32.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_33.png)

In our case， the cross tab or contingency table shows us the counts in each category。



![](img/1fb001f0650f98d8c34f08457acdd8eb_35.png)

A standard car with diesel fuel。A standard car with gas fuel。

 a turbo car with diesel fuel or a turbo car with gas fuel。



![](img/1fb001f0650f98d8c34f08457acdd8eb_37.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_38.png)

The formula for Chi Square is given as follows。The summation of the observed value， I。e。

 the counts in each group minus the expected value， all squared， divided by the expected value。



![](img/1fb001f0650f98d8c34f08457acdd8eb_40.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_41.png)

Expected values are based on the given totals。 That is。

 what can we say individual cells would be if we did not know the observed values。



![](img/1fb001f0650f98d8c34f08457acdd8eb_43.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_44.png)

To calculate the expected value of a standard car with diesel， we take the row total。

 which is 20 multiplly by the column total 1068， divided by the grand total of 205。



![](img/1fb001f0650f98d8c34f08457acdd8eb_46.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_47.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_48.png)

This will give you 16。39。 If we do the same thing for turbo cars with gas fuel。

 we will take the row total 185， multiplied by the column total 37。

 and we divide by the grand total of 205 to get 33。39。😊。



![](img/1fb001f0650f98d8c34f08457acdd8eb_50.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_51.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_52.png)

If we repeat the same procedure for all of them， we get these values。



![](img/1fb001f0650f98d8c34f08457acdd8eb_54.png)

If we took the row totals， column totals and grand total。

 we will get the same values as the totals as the observed values。



![](img/1fb001f0650f98d8c34f08457acdd8eb_56.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_57.png)

Now， going back to this formula， if we took a summation of all the observed minus the expected values all squared and divided by the expected value。

 we will get a chi square value of 33。2。On the Chi square table。

 we check on the degree of freedom equals one row and find the value closest to 29。6。Here。

 we can see that 29。6 will fall in a P value less than 0。05。 Therefore。

 we can say the P value is less than 0。05。 Since the P value is less than 005。

 we reject the null hypothesis that the two variables are independent， and therefore。

 we conclude that there is an association between fuel type and aspiration。To do this in Python。

 we will use the Chi square contingency function in the Psi pi dot statistics package。

 The function will print out the Chi square test value 29。6。 The second value is the P value。

 which is very close to 0， and a degree of freedom of one。 If you remember。

 the chi square table did not give an exact P value， but a range in which it falls。

 Python will give the exact P value。 We can see the same results as in our previous slides。😊。



![](img/1fb001f0650f98d8c34f08457acdd8eb_59.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_60.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_61.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_62.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_63.png)

It also prints out the expected values， which we also calculated by hand。



![](img/1fb001f0650f98d8c34f08457acdd8eb_65.png)

Since the P value is close to 0， we reject the null hypothesis that the two variables are independent and conclude that there is evidence of association between fuel type and aspiration。



![](img/1fb001f0650f98d8c34f08457acdd8eb_67.png)

![](img/1fb001f0650f98d8c34f08457acdd8eb_68.png)