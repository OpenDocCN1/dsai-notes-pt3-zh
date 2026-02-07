# IBM数据工程专业证书课程9：《数据仓库和BI分析入门》｜getting-started-with-data-warehousing-and-bi - P10：9_事实和维度建模.zh_en - GPT中英字幕课程资源 - BV1bN41187mr

![](img/2c06c95d36184bd079fcb2cbda36a81b_0.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_1.png)

Welcome to facts and dimensional modeling After watching this video。

 you will be able to define what facts are in context of data warehousing。

 define what a fact table is， define what dimensions are in context of data warehousing。

 define what a dimension table is， and describe an example of a fact and its dimensions。



![](img/2c06c95d36184bd079fcb2cbda36a81b_3.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_4.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_5.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_6.png)

Data can be lumped into two categories， facts and dimensions facts are usually quantities which can be measured。

 such as temperature， number of sales or millimeters of rainfall。

 but facts can also be qualitative in nature。

![](img/2c06c95d36184bd079fcb2cbda36a81b_8.png)

Dimenssions are attributes which can be assigned to facts。 Demenions provide context to facts。

 which makes facts useful。 For example， a temperature such as 24 degrees Celsius all by itself is not meaningful information。

Let's look at a familiar example here we have a weather report obtained by Googling weather in Kuala Lumpur The facts here are things like the temperature。

 humidity， probability of precipitation and wind speed Notice that these are all quantities。

 but there are other facts here such as this icon which means partly cloudy or the statement clear with periodic clouds and these other icons which indicate forecasted conditions such as thunder showers。

 all of these nonnumeric facts are examples of qualitative facts to make sense of these facts we need to provide context。



![](img/2c06c95d36184bd079fcb2cbda36a81b_10.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_11.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_12.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_13.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_14.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_15.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_16.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_17.png)

Context is provided by dimensions， which includes things like the location， Kuala Lumpur。

 Malaysia and the date and time Tuesday at 3 AM。 The statement 24 degreesC in Kuala Lumpur。

 Malaysia on Tuesday August 17 at 3am means something。



![](img/2c06c95d36184bd079fcb2cbda36a81b_19.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_20.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_21.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_22.png)

A fact table typically consists of the facts of a business process。

 and it also contains foreign keys which establish welldefined links to dimension tables。

 usually facts are additive measures or metrics， such as dollar amounts for individual sales transactions A fact table can contain detail level facts。

 such as individual sales transactions or facts that have been aggregated such as daily or weekly sales totals。



![](img/2c06c95d36184bd079fcb2cbda36a81b_24.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_25.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_26.png)

Fact tables can contain aggregated facts and are called summary tables。 For example。

 you could summarize sales transactions by summing overall sales for each quarter of the year。

An example of a foreign key might be store ID。Accumulating snapshot fact tables are used to record events that take place during a welldefined business process For example。

 suppose you have finished configuring a custom computer for yourself online and you have just placed your order the order date and the order amount are recorded in a snapshot table by the manufacturer a unique order ID is also assigned。



![](img/2c06c95d36184bd079fcb2cbda36a81b_28.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_29.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_30.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_31.png)

Once your order is verified， your payment is processed。

 the amount paid and the date paid are then recorded。



![](img/2c06c95d36184bd079fcb2cbda36a81b_33.png)

After payment verification， the computer specifications are sent to the manufacturing department once the computer is in production。

 the build start date is entered， and once the computer is built。

 the build end date is recorded Finally， once your computer is ready to be sent。

 the ship date is recorded。All these fields are stored in a single row of the table。

 which is uniquely identified by the order ID。Now， a dimension is a variable that categorizes facts Demens are called categorical variables by statisticians and machine learning engineers Demenions enable users to answer business questions the main uses for dimensions in analytics include filtering grouping and labeling operations For example。

 commonly used dimensions include names of people， products and places and date or timestamps。



![](img/2c06c95d36184bd079fcb2cbda36a81b_35.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_36.png)

A dimension table thus stores the dimensions of a fact and is joined to the fact table via a foreign key。

Some examples of various types of dimension tables include product tables which describe products such as make model。

 color and size， employee tables which describe employees such as name， title and department。



![](img/2c06c95d36184bd079fcb2cbda36a81b_38.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_39.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_40.png)

Temporal tables， which describe time at the level of granularity or precision at which events are recorded。

And geography tables for location data such as country， state， city， and postal or zip code。

Let us look at an example of a schema with both fact and dimension tables to help illustrate their relationships。



![](img/2c06c95d36184bd079fcb2cbda36a81b_42.png)

We could have a fact table for recording sales at a car dealership this table would store facts about each car sale。

 such as the sale date and sale amount as well as a primary key sale ID for each sales transaction。

 we also need to record its dimensions like the vehicle sold and the salesperson who sold it。



![](img/2c06c95d36184bd079fcb2cbda36a81b_44.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_45.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_46.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_47.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_48.png)

The attributes of these dimensions， such as the vehicle make and model。

 or the salesperson's first and last name are stored in separate vehicle and salesperson tables。



![](img/2c06c95d36184bd079fcb2cbda36a81b_50.png)

![](img/2c06c95d36184bd079fcb2cbda36a81b_51.png)

However， we link them with the sales table by recording the vehicle ID and the salesperson ID as for in keys in the fact table this way we typically end up with multiple dimension tables for each fact table。



![](img/2c06c95d36184bd079fcb2cbda36a81b_53.png)

In this video， you learned that business data falls into two categories。

 facts and dimensions facts are usually numerical measures of business processes such as sale amounts and dollars。

 dimensions such as sold by and store ID， categorized facts， such as who sold the product。

 when and which store was sold from。

![](img/2c06c95d36184bd079fcb2cbda36a81b_55.png)

Dimensions are categorical variables that provide context for facts and are used for filtering。

 grouping and labeling， and facts and dimension tables are linked together by foreign and primary keys。



![](img/2c06c95d36184bd079fcb2cbda36a81b_57.png)