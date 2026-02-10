# IBM数据工程专业证书 课程11：《使用Spark和Hadoop进行大数据介绍》｜big-data-with-spark-hadoop｜ - P23：22_使用 dataframe 的 etl.zh_en - GPT中英字幕课程资源 - BV12h4y1D7hF

![](img/dce642d330d54dbc5f3b7a0895d7aab1_0.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_1.png)

Welcome to usingsing Data frames with real world data。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_3.png)

After watching this video， you'll be able to identify the basic data frame operational steps。

 apply basic data frame operations on real world data， apply Sp data frames to real world data。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_5.png)

Let's begin with basic data frame operations， reading， analysis， transformation， loading and writing。

 First， Spark reads in the data and loads the data into a data frame。 Next。

 you can analyze the data sets starting with simple tasks such as examining the columns， data types。

 number of rows and optionally working with aggregated stats， trend analysis and other operations。

 If needed， you can transform the data by filtering the data to locate specific values。

 sorting the data based on specific criteria， or by joining this data with another data。

 Then you can load your transform data back to a data or a file system and write the data back to disk。

 This process is commonly also referred to as ETL extract transform load ETL is an essential process in any data processing pipeline as the first step makes data accessible to data warehouses。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_7.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_8.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_9.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_10.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_11.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_12.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_13.png)

machine learning models， downstream applications or other services Let's talk about another standard process ELT extract。

 load and transform This process emerged as a result of big data processing with ELT all of the data resides in a data lake a data lake is a vast pool of raw data for which the purpose of the data is not predefined when a data lake exists。

 each project forms individual transformation tasks as required in contrast to anticipating all necessary transformation requirements usage scenarios as done with ETL and a data warehouse organizations often use a mixture between ETL and ELT。

Let's take a closer look at each basic data frame operation when reading the data you can directly load data into data frames or create a new Spark data frame from an existing data frame。

 the displayed code sample shows how to load a data set into a pans data frame in Python and then load the same data into a Spk data frame object。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_15.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_16.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_17.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_18.png)

Let's continue the example that uses the data set about car models and performance。

 This data set contains columns for parameters such as miles per gallon， number of cylinders。

 horsepower and other auto related parameters。

![](img/dce642d330d54dbc5f3b7a0895d7aab1_20.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_21.png)

Here you can view the first few rows of the dataset set。Next is analyzing the data First。

 examine the data frame column data types or the schema using the print schema method。

 take note of each column's data types， for example， the miles per gallon is a double type。

 while the first column indicates the car model name is a string。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_23.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_24.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_25.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_26.png)

You can also examine a specified number of data frames using the show function。

You can apply the select function to examine data from a specific column in detail this example applies the select function to view the first five rows of the MPG column。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_28.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_29.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_30.png)

After analyzing the dataset， your next step is to plan for any needed dataset transformations。

 the goal of a transformation is to retain only relevant data transformationform techniques can include filtering the data joining with other data sources or performing columnar operations。

 columnar operations or actions such as multiplying each column by a specific number converting data from one unit to another such as converting miles per gallon to kilometers per liter。

 Another common transformation technique is to group or aggregate data Sometimes a downstream application may require aggregated data such as a quarterly sales report that does not need to display every transaction but needs to show the aggregated total quarterly sales and revenue numbers Many transformations or domain specific data augmentation processes。

 The effort needed can vary depending on the domain and the data， For example。

 scientific data sets involving。

![](img/dce642d330d54dbc5f3b7a0895d7aab1_32.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_33.png)

Multiple differing measurements may require more columnar operations and unit conversions。

 while financial data can require more aggregation and averaging tasks。

Here are some simple examples of transformations on the MT CarRS dataset。

 the filter function helps locate specific criteria within the data in this case。

 the task is to filter the data for cars that have a mileage or MPG of less than 18 miles per gallon。

Here is an example of aggregating data In this example。

 the transformation aggregates all the records with the same number of cylinders。

 as seen in the CL column counts the number of vehicles with the specified number of cylinders and sorts the data to list the number of units for each cylinder category in ascending order。

 We can see that 14 cars have an8 cylinder engine and 11 cars have a four cylinder engine。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_35.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_36.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_37.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_38.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_39.png)

The ETL pipeline's last step is to export the data to disk or load it into another database。

 like reading the data and extracting the data， you can write the data to the disk as a JSON file or save the data into another database such as a Postgres database。

 you can also use an API to export the data to another database such as a Postgres database。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_41.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_42.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_43.png)

In this video you learn that basic data frame operations are reading analysis， transformation。

 loading， and writing， you can use app pandas data frame in Python to load a data。

 you can apply the print schema， select function or show function for data analysis for transform tasks keep only relevant data and apply functions such as filters。

 joins， column operations， grouping and aggregations and other functions。



![](img/dce642d330d54dbc5f3b7a0895d7aab1_45.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_46.png)

![](img/dce642d330d54dbc5f3b7a0895d7aab1_47.png)