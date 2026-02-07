# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P11：10_Python数据预处理.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

In this video， we'll be going through some data pre processing techniques。

 If you're unfamiliar with the term。 data pre processing is a necessary step in data analysis。

 It is the process of converting or mapping data from one raw form into another format to make it ready for further analysis。

 Data preprocessing is often called data cleaning or data wrangling。

 and there are likely other terms。 Here are the topics that will be covering in this module。 First。

 well show you how to identify and handle missing values。

 A missing value condition occurs whenever a data entry is left empty。 Then well cover data formats。

 Data from different sources may be in various formats in different units or in various conventions。

 We will introduce some methods in Python pandas that can standardize the values into the same format or unit or convention。

 After that will cover data normalization。 Different columns of numerical data may have very different ranges and direct comparison is often not。



![](img/5e1adff79923deee452f178457d15f7b_1.png)

![](img/5e1adff79923deee452f178457d15f7b_2.png)

![](img/5e1adff79923deee452f178457d15f7b_3.png)

![](img/5e1adff79923deee452f178457d15f7b_4.png)

![](img/5e1adff79923deee452f178457d15f7b_5.png)

![](img/5e1adff79923deee452f178457d15f7b_6.png)

![](img/5e1adff79923deee452f178457d15f7b_7.png)

![](img/5e1adff79923deee452f178457d15f7b_8.png)

![](img/5e1adff79923deee452f178457d15f7b_9.png)

![](img/5e1adff79923deee452f178457d15f7b_10.png)

![](img/5e1adff79923deee452f178457d15f7b_11.png)

![](img/5e1adff79923deee452f178457d15f7b_12.png)

Meingful。Normalization is a way to bring all data into a similar range for more useful comparison。

 specifically， we'll focus on the techniques of centering and scaling。

 and then we'll introduce data binning。 binning creates bigger categories from a set of numerical values。

 It is particularly useful for comparison between groups of data。 And lastly。

 we'll talk about categorical variables and show you how to convert categorical values into numeric variables to make statistical modeling easier In Python。

 We usually perform operations along columns。 Each row of the column represents a sample。 I。e。

 a different used car in the database。😊。

![](img/5e1adff79923deee452f178457d15f7b_14.png)

![](img/5e1adff79923deee452f178457d15f7b_15.png)

![](img/5e1adff79923deee452f178457d15f7b_16.png)

![](img/5e1adff79923deee452f178457d15f7b_17.png)

![](img/5e1adff79923deee452f178457d15f7b_18.png)

![](img/5e1adff79923deee452f178457d15f7b_19.png)

You access a column by specifying the name of the column。 for example。

 you can access symboling and body style。 Each of these columns is a panda series。

There are many ways to manipulate data frames in Python。 For example。

 you can add a value to each entry of a column to add one to each symboling entry。 Use this command。

 This changes each value of the data frame column by adding one to the current value。

