# 041：IBM《生成式人工智能工程｜Falsk、生成式AI应用、数据分析、机器学习、Keras、架构和数据、NLP基础、transformer、微调、高级微调、RAG》 p41 11_在Python中将分类变量转换为定量变量.zh_en -BV1NAq6Y9E7z_p41-

In this video， we'll discuss how to turn categorical variables into quantitative variables in Python。



![](img/000c0136f4b5294dc07ced81b9a469dc_1.png)

Most statistical models cannot take in objects or strings as input and for model training。

 only take the numbers as inputs。In the card data set。

 the fuel type feature as a categorical variable has two values， gas or diesel。

 which are in string format for further analysis， Jerry has to convert these variables into some form of numeric format。



![](img/000c0136f4b5294dc07ced81b9a469dc_3.png)

We encode the values by adding new features corresponding to each unique element in the original feature we would like to encode in the case where the feature fuel has two unique values。

 Ga and diesel。 We create two new features。 Ga and diesel。

 When a value occurs in the original feature。 We set the corresponding value to one in the new feature。

 The rest of the feature are set to 0。 In the fuel example for car B。 The fuel value is diesel。

 Therefore， we set the feature diesel equal to one。 and the gas feature to 0。 Similarlyly， for car D。

 the fuel value is gas。 Therefore， we set the feature gas equal to one。

 and the feature diesel equal to 0。 This technique is often called one hot encoding in pandas。

 we can use get underscore dummies method to convert categorical variables to dummy variables。



![](img/000c0136f4b5294dc07ced81b9a469dc_5.png)

In Python， transforming categorical variables to dummy variables is simple following the example PD dot get。

 underscore dumm'ies method gets the fuel type column and creates the data frame dummy underscore variableable。

 underscore 1。The get underscore dummies method automatically generates a list of numbers。

 each one corresponding to a particular category of the variable。



![](img/000c0136f4b5294dc07ced81b9a469dc_7.png)