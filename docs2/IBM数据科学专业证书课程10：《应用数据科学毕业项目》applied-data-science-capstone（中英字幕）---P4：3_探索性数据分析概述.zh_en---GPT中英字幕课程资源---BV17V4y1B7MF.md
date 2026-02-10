# IBM数据科学专业证书课程10：《应用数据科学毕业项目》applied-data-science-capstone（中英字幕） - P4：3_探索性数据分析概述.zh_en - GPT中英字幕课程资源 - BV17V4y1B7MF

![](img/b7c0d9db9a5e911f809c92fbec54159e_0.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_1.png)

In this video， we will review exploratory data analysis。



![](img/b7c0d9db9a5e911f809c92fbec54159e_3.png)

Expllororatory data analysis is the first step of any data science project in the first lab you will perform some exploratory data analysis using a database in the second lab you will see if the data can be used to automatically determine if the Falcon 9 second stage will land。



![](img/b7c0d9db9a5e911f809c92fbec54159e_5.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_6.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_7.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_8.png)

Some attributes can be used to determine if the first stage can be reused。

 we can then use these features with machine learning to automatically predict if the first stage can land successfully。

 for example。

![](img/b7c0d9db9a5e911f809c92fbec54159e_10.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_11.png)

You can observe that the success rate since 2013 has improved。

 we can incorporate this as a feature via launch number。



![](img/b7c0d9db9a5e911f809c92fbec54159e_13.png)

We see that different launch sites have different success rates as a result。

 they can be used to help determine if the first stage will land successfully CCAFSLC40 has a success rate of 60%。

 while KSCLC 39A and VAFB SLC4E have a success rate around 77%。



![](img/b7c0d9db9a5e911f809c92fbec54159e_15.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_16.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_17.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_18.png)

Combining attributes also gives us more information If we overlay the result of the landing outcomes as a color。

 we see that CCAFSLC40 has a success rate of 60%， but if the mass is above 10，000 kilograms。

 the success rate is 100% therefore we will combine multiple features。



![](img/b7c0d9db9a5e911f809c92fbec54159e_20.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_21.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_22.png)

In the lab， you will determine what attributes are correlated with successful landings The categorical variables will be converted using one hot encoding。

 preparing the data for a machine learning model that will predict if the first stage will successfully land。



![](img/b7c0d9db9a5e911f809c92fbec54159e_24.png)

![](img/b7c0d9db9a5e911f809c92fbec54159e_25.png)