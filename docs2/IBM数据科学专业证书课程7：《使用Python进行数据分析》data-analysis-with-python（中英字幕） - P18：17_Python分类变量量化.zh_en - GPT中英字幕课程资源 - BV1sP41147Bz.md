# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P18：17_Python分类变量量化.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/6f044586857f731162ae0f0971abca13_0.png)

In this video， we'll discuss how to turn categorical variables into quantitative variables in Python。



![](img/6f044586857f731162ae0f0971abca13_2.png)

Most statistical models cannot take in objects or strings as input， and for model training。

 only take the numbers as inputs。

![](img/6f044586857f731162ae0f0971abca13_4.png)

![](img/6f044586857f731162ae0f0971abca13_5.png)

In the card data set， the fuel type feature as a categorical variable has two values， Ga or diesel。

 which are in string format for further analysis。 Jerry has to convert these variables into some form of numeric format。



![](img/6f044586857f731162ae0f0971abca13_7.png)

![](img/6f044586857f731162ae0f0971abca13_8.png)

![](img/6f044586857f731162ae0f0971abca13_9.png)

We encode the values by adding new features corresponding to each unique element in the original feature we would like to encode in the case where the feature fuel has two unique values。

 Ga and diesel。 We create two new features。 gas and diesel。

 When a value occurs in the original feature。 We set the corresponding value to one in the new feature。

 The rest of the feature are set to 0。 in the fuel example for car B。 the fuel value is diesel。

 Therefore， we set the feature diesel equal to one。 and the gas feature to 0。 Similarlyly， for car D。

 the fuel value is gas。 Therefore， we set the feature gas equal to one and the feature diesel equal to 0。

 This technique is often called one hot encoding in pandas。

 we can use get underscore dummies method to convert categorical variables to dummy variables。



![](img/6f044586857f731162ae0f0971abca13_11.png)

![](img/6f044586857f731162ae0f0971abca13_12.png)

![](img/6f044586857f731162ae0f0971abca13_13.png)

![](img/6f044586857f731162ae0f0971abca13_14.png)

![](img/6f044586857f731162ae0f0971abca13_15.png)

![](img/6f044586857f731162ae0f0971abca13_16.png)

![](img/6f044586857f731162ae0f0971abca13_17.png)

![](img/6f044586857f731162ae0f0971abca13_18.png)

![](img/6f044586857f731162ae0f0971abca13_19.png)

![](img/6f044586857f731162ae0f0971abca13_20.png)

![](img/6f044586857f731162ae0f0971abca13_21.png)

![](img/6f044586857f731162ae0f0971abca13_22.png)

In Python， transforming categorical variables to dummy variables is simple。 Following the example。

 P D dot get， underscore dummies method gets the fuel type column and creates the data frame dummy underscore variable。

 underscore1。

![](img/6f044586857f731162ae0f0971abca13_24.png)

![](img/6f044586857f731162ae0f0971abca13_25.png)

![](img/6f044586857f731162ae0f0971abca13_26.png)

The get underscore dummies method automatically generates a list of numbers。

 each one corresponding to a particular category of the variable。



![](img/6f044586857f731162ae0f0971abca13_28.png)

![](img/6f044586857f731162ae0f0971abca13_29.png)