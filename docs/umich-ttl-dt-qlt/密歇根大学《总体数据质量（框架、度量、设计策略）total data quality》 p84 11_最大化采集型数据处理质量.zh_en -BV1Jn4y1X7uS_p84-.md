# 密歇根大学《总体数据质量（框架、度量、设计策略）total data quality》 p84 11_最大化采集型数据处理质量.zh_en -BV1Jn4y1X7uS_p84-

![](img/98ac4ddf4805f4cf9eec029d51097548_0.png)

![](img/98ac4ddf4805f4cf9eec029d51097548_1.png)

Hello， everyone。In this lecture， you will learn how to maximize data processing quality for gather data。



![](img/98ac4ddf4805f4cf9eec029d51097548_3.png)

First， let's check where we are in the big picture。In previous lectures。

 you have learned how to maximize data processing quality for design data。

Now we turn our tension to gather data。In order to maximize data processing quality。

 we need to characterize data processing problems a study by Dr。

 Saik suggests that data profilings any measures to maximize data processing here data profiling means identification。

 detection and characterization of data processing errors using a consistent framework。

A useful framework is to profile data using two dimensions， single or multi source。

 an instance or schema level。For example， data errors can occur in a single data source at an instance level。

This can be data entry error or redundant information。Some errors may be systematic。

 this applies to the case of multi source schema level errors。

Data processing errors occur because data sources use different data schema， for example。

 when you combine two user data from to US based and EU based data providers。

 data fields can be recorded in different formats for data。

US data record date in the order of month day and two or four visit years。

 while EU data may record in the order of four visit years followed by month and date。

This illustrates that processing errors while integrating the two data sets can occur due to different schemas across multiple sources。

Once you complete data profiling， you can now apply measures to correct processing errors。

In data science， this step is called in a variety of terms， but mostly referred as data cleaning。

Data cleaning includes standardization data by controlling vocabularies， data types。

 and value formats。We may need to deduplicate or consolidate entries if they are merged or split by inconsistent identifiers。

To address the systematic issue in data processing errors。

 data providers may need to implement consistent data schema。

There are a few open source interactive tools to help you maximize data processing quality。

Regular expression is widely used to detect correct values that do not conform to a correct format。

You can use open source regular expression tools listed in the slide to test regular expressions you create to filter information that match a specific pattern。

If tested to work properly， the regular expressions can be implemented on our gathered data to find and correct instances that contain errors predefined by the regular expressions。

Another north word tool is open refine。You can own data in a spreadsheet format and passse and clean them on the open refinefind platform。

SQite is used for checking integrity constraints。For more details。

 please refer to the website introduced in the slide。

Although the open source tools can be very helpful in maximizing data processing quality。

 you might need to consider using script languages such as Python and Pro for large scale versatile data processing Sc languages provide users with various packages that contain data cleaning functions。

This means that you don't need to reinvent the wheel to maximize data processing quality For example。

 a python package can be used to fix many broken characters due to encoding problems as illustrated in the slide for the sentence with strange characters though monoa Lisaa doesn't have eyebrows。

 especially popular python packages， pandas and nuy can speed up time consuming data processing in large scale data that contain millions of instances。

Next， we will look at an example of maximizing data processing quality in real world gather data。

We will use open source Python packages for the demonstration。



![](img/98ac4ddf4805f4cf9eec029d51097548_5.png)

![](img/98ac4ddf4805f4cf9eec029d51097548_6.png)

![](img/98ac4ddf4805f4cf9eec029d51097548_7.png)