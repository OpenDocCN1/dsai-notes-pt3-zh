# IBM数据工程专业证书课程9：《数据仓库和BI分析入门》｜getting-started-with-data-warehousing-and-bi - P5：4_数据仓概览.zh_en - GPT中英字幕课程资源 - BV1bN41187mr

![](img/cd5584c4350d74ee47b1d89773165329_0.png)

![](img/cd5584c4350d74ee47b1d89773165329_1.png)

Welcome to Datamarts overview After watching this video you will be able to define what a data Mart is。

 give examples of datamarts， compare datamarts to transactional databases and enterprise data warehouses。

 and describe data pipelines for loading data Mars。



![](img/cd5584c4350d74ee47b1d89773165329_3.png)

A data Mart is an isolated part of the larger enterprise data warehouse that is specifically built to serve a particular business function。

 purpose or community of users for example， the sales and finance departments in a company may have access to dedicated data mars that supply the data required for their quarterly sales reports and projections the marketing team may use data marts to analyze customer behavior data。

 and the shipping manufacturing and warranty departments may have their own data Mars。



![](img/cd5584c4350d74ee47b1d89773165329_5.png)

![](img/cd5584c4350d74ee47b1d89773165329_6.png)

![](img/cd5584c4350d74ee47b1d89773165329_7.png)

![](img/cd5584c4350d74ee47b1d89773165329_8.png)

![](img/cd5584c4350d74ee47b1d89773165329_9.png)

So what are data mars used for Datamars are designed to provide specific support for making tactical decisions As such。

 datamars are focused only on the most relevant data。

 which saves and users the time and effort that would otherwise be spent searching the data warehouse for insights。

 The typical structure of a datamart is as follows。

 It is a relational database with a star or more often a snowflake schema。

 which means it contains a central fact table consisting of the business metrics relevant to a business process which is surrounded by a related hierarchy of dimension tables that provide context for the facts。



![](img/cd5584c4350d74ee47b1d89773165329_11.png)

![](img/cd5584c4350d74ee47b1d89773165329_12.png)

Let's look at some typical differences between three types of data repositories， data Marts。

 transactional databases， and data warehouses， starting with data Marts and databases。

 both data Mars and data warehouses are online analytical processing or OLAP systems that are optimized for read intensive queries and operations。

 whereas transactional databases or online transaction processing or OLTP systems that are optimized for right intensive queries and applications。



![](img/cd5584c4350d74ee47b1d89773165329_14.png)

![](img/cd5584c4350d74ee47b1d89773165329_15.png)

![](img/cd5584c4350d74ee47b1d89773165329_16.png)

Data marts use transactional databases or data warehouses as data sources。

 while in transactional databases， operational applications such as point of sales systems serve as the sources of data a data mars stores validated。

 transformed and cleaned data while a database will have raw data that has not yet been cleaned Data mars accumulate historical data that can be used for trend analysis while transactional databases may not always store older data a data mart is much like a data warehouse。

 except that it has a smaller tactical scope Data warehouses broadly support the strategic requirements of the enterprise Data mars are lean and fast compared to data warehouses。

 which can be very large and hence can be slower。

![](img/cd5584c4350d74ee47b1d89773165329_18.png)

![](img/cd5584c4350d74ee47b1d89773165329_19.png)

There are three basic types of data mars， dependent， independent and hybrid。

 the difference between these three kinds of data mars depends on their relationship with the data warehouse and the sources used for supplying each of them with data dependent data mars draw data from the enterprise data warehouse。

 while independent data mars bypass the data warehouse and are created directly from sources。

 which may include internal operational systems or external data from vendors or other sources outside the enterprise。



![](img/cd5584c4350d74ee47b1d89773165329_21.png)

![](img/cd5584c4350d74ee47b1d89773165329_22.png)

![](img/cd5584c4350d74ee47b1d89773165329_23.png)

![](img/cd5584c4350d74ee47b1d89773165329_24.png)

![](img/cd5584c4350d74ee47b1d89773165329_25.png)

![](img/cd5584c4350d74ee47b1d89773165329_26.png)

Hybrid data mars only depend partially on the enterprise data warehouse。

 they combine inputs from data warehouses with data from operational systems and other systems external to the warehouse。



![](img/cd5584c4350d74ee47b1d89773165329_28.png)

![](img/cd5584c4350d74ee47b1d89773165329_29.png)

![](img/cd5584c4350d74ee47b1d89773165329_30.png)

Depenent data marts offer analytical capabilities within a restricted area of the enterprise data warehouse。

 thus they inherit the security that comes with the enterprise data warehouse。

 and since dependent data mars pulled directly from the data warehouse where data has already been cleaned and transformed。

 they tend to have simpler data pipelines than independent data mars。



![](img/cd5584c4350d74ee47b1d89773165329_32.png)

![](img/cd5584c4350d74ee47b1d89773165329_33.png)

![](img/cd5584c4350d74ee47b1d89773165329_34.png)

Independent data Mars differ from dependent data Mars because they require custom， extract。

 transform， and load data pipelines to carry out the transformation and integration processes on the source data。

 since it is coming directly from operational systems and external sources。

 and independent data Mars may also require separate security measures。



![](img/cd5584c4350d74ee47b1d89773165329_36.png)

![](img/cd5584c4350d74ee47b1d89773165329_37.png)

![](img/cd5584c4350d74ee47b1d89773165329_38.png)

Whatever the type of data mark you may have， its purpose is to provide end users with relevant data when they need it。

 accelerate business processes by providing efficient query response times。

 provide a cost efficient method for informing data drivenven decisions。

 and ensure secure access and control over your data。



![](img/cd5584c4350d74ee47b1d89773165329_40.png)

![](img/cd5584c4350d74ee47b1d89773165329_41.png)

![](img/cd5584c4350d74ee47b1d89773165329_42.png)

![](img/cd5584c4350d74ee47b1d89773165329_43.png)

In this video you learned that a datamart is an isolated part of the larger enterprise data warehouse that is specifically built to serve a particular business function。

 purpose， or community of users， is designed to provide specific timely and rapid support for making tactical decisions and typically has a star or Snowflake schema。

 you also learned that unlike an OLTP database， an OLAP datamart stores clean and validated data and accumulates historical data。

 and you can categorize datamarts in terms of their dependence on the enterprise data warehouse。

 a datamart can be completely dependent on the data warehouse。

 a completely independent standalone mini data warehouse or a hybrid of the two。



![](img/cd5584c4350d74ee47b1d89773165329_45.png)

![](img/cd5584c4350d74ee47b1d89773165329_46.png)