# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜big-data-with-spark-hadoop｜ - P22：21_催化剂和钨.zh_en - GPT中英字幕课程资源 - BV12h4y1D7hF

![](img/1cbcba039f33582cde974a066a7be542_0.png)

![](img/1cbcba039f33582cde974a066a7be542_1.png)

Welcome to SparkSQL Meory Opim using Catalyst and Tngsten。



![](img/1cbcba039f33582cde974a066a7be542_3.png)

After watching this video， you will be able to describe the goals of Apache's Spark SQL optimization。

 Describe how catalystta and tungsten benefits Sp SQL。

 Explain how Spark performs SQL and memory optimization using catalyst and tungsten。😊。



![](img/1cbcba039f33582cde974a066a7be542_5.png)

![](img/1cbcba039f33582cde974a066a7be542_6.png)

The primary goal of Spark SQL optimization is to improve the SQL query runtime performance。

 reducing the query's time and memory consumption， saving organizations time and money。



![](img/1cbcba039f33582cde974a066a7be542_8.png)

![](img/1cbcba039f33582cde974a066a7be542_9.png)

![](img/1cbcba039f33582cde974a066a7be542_10.png)

SparkSQL supports both rule based and Co based query Op Catalyst， also known as the Catat Opr。

 is the SparkSQL built in rule based query Opr based on scholar functional programming constructs。

 Catalys is designed to easily add new optimization techniques and features to SparkSQL Develop can extend the optimizer by adding data source specific rules and support for new data types。



![](img/1cbcba039f33582cde974a066a7be542_12.png)

![](img/1cbcba039f33582cde974a066a7be542_13.png)

![](img/1cbcba039f33582cde974a066a7be542_14.png)

During rule based optimization， the SQL Opr follows predefined rules that determine how to run the SQL query。

 Exles of predefined rules include validating that a table is indexed and checking that a query contains only the required columns。



![](img/1cbcba039f33582cde974a066a7be542_16.png)

![](img/1cbcba039f33582cde974a066a7be542_17.png)

![](img/1cbcba039f33582cde974a066a7be542_18.png)

![](img/1cbcba039f33582cde974a066a7be542_19.png)

With the query itself optimized cost based optimization measures and calculates cost based on the time and memory that the query consumes。

 The catalyst optimizer selects the query path that results in the lowest time and memory consumption because queries can use multiple paths。

 these calculations can become quite complex when large data sets are part of the calculation。

 Consider the analogy of a car and your travels。 a car owner can optimize the vehicle's performance with the right oil。

 tires， fuel and so on。 These actions are similar to rule based optimization。

 when it's time to plan a travel route that can save both time and wear and tear on your car。

 Those actions or a form of cost based optimization。😊。



![](img/1cbcba039f33582cde974a066a7be542_21.png)

![](img/1cbcba039f33582cde974a066a7be542_22.png)

![](img/1cbcba039f33582cde974a066a7be542_23.png)

![](img/1cbcba039f33582cde974a066a7be542_24.png)

![](img/1cbcba039f33582cde974a066a7be542_25.png)

![](img/1cbcba039f33582cde974a066a7be542_26.png)

![](img/1cbcba039f33582cde974a066a7be542_27.png)

![](img/1cbcba039f33582cde974a066a7be542_28.png)

![](img/1cbcba039f33582cde974a066a7be542_29.png)

In the background， the Catalys Opr uses a tree data structure and provides the data tree rule sets to optimize a query。

 Catalyt performs the following four high level tasks or phases， analysis， logical optimization。

 physical planning， and code generation。

![](img/1cbcba039f33582cde974a066a7be542_31.png)

![](img/1cbcba039f33582cde974a066a7be542_32.png)

![](img/1cbcba039f33582cde974a066a7be542_33.png)

![](img/1cbcba039f33582cde974a066a7be542_34.png)

![](img/1cbcba039f33582cde974a066a7be542_35.png)

Let's review the four catalyst phases In the analysis phase， Ca analyzes the query， the data frame。

 the unresolved logical plan and the catalog to create a logical plan。

 During the logical optimization phase。 The logical plan evolves into an optimized logical plan。

 This is the rule based optimization step of SpsQL and rules such as folding push down and pruning are applied here。

 During the physical planning phase， Cata generates multiple physical plan on the logical plan。

 A physical plan describes computation on data sets with specific definitions on how to conduct the computation。

 A cost model then chooses the physical plan with the least cost。

 This is the costbased optimization step。 The final phase is code generation。

 Ca applies the selected physical plan and generates Java byte code to run on each node。😊。



![](img/1cbcba039f33582cde974a066a7be542_37.png)

![](img/1cbcba039f33582cde974a066a7be542_38.png)

![](img/1cbcba039f33582cde974a066a7be542_39.png)

![](img/1cbcba039f33582cde974a066a7be542_40.png)

![](img/1cbcba039f33582cde974a066a7be542_41.png)

![](img/1cbcba039f33582cde974a066a7be542_42.png)

![](img/1cbcba039f33582cde974a066a7be542_43.png)

![](img/1cbcba039f33582cde974a066a7be542_44.png)

![](img/1cbcba039f33582cde974a066a7be542_45.png)

![](img/1cbcba039f33582cde974a066a7be542_46.png)

![](img/1cbcba039f33582cde974a066a7be542_47.png)

Let's now examine how Tngsten provides costbased optimization and Spk Tngsten optimizes the performance of underlying hardware focusing on CPU performance instead of IO Java was initially designed for transactional applications Tngsten aims to improve CPU and memory performance by using a method more suited to data processing for the JVM to process data。



![](img/1cbcba039f33582cde974a066a7be542_49.png)

![](img/1cbcba039f33582cde974a066a7be542_50.png)

![](img/1cbcba039f33582cde974a066a7be542_51.png)

![](img/1cbcba039f33582cde974a066a7be542_52.png)

To achieve optimal CPU performance， Tngsten applies the following capabilities。

 Tngsten manages memory explicitly and does not rely on the JVM object model or garbage collection。

 Tngsten creates cache friendly data structures that are arranged easily and more securely。

 using stride based memory access instead of random memory access。

 Tngsten supports JVM bytecode on demand。 Tngsten does not enable virtual function dispatches。

 reducing multiple CPU calls。 Tngsten places intermediate data in CPU registers and enables loop unrolling。

😊。

![](img/1cbcba039f33582cde974a066a7be542_54.png)

![](img/1cbcba039f33582cde974a066a7be542_55.png)

![](img/1cbcba039f33582cde974a066a7be542_56.png)

In this video you learn that Catalyst is the SparkSQL builtt in rule based Que Opimr Catalyst performs analysis。

 logical optimization， physical planning， and code generation Tngsten is the Spark built in cost based optimizer for CPU and memory usage that enables cache friendly computation of algorithms and data structures。



![](img/1cbcba039f33582cde974a066a7be542_58.png)

![](img/1cbcba039f33582cde974a066a7be542_59.png)

![](img/1cbcba039f33582cde974a066a7be542_60.png)