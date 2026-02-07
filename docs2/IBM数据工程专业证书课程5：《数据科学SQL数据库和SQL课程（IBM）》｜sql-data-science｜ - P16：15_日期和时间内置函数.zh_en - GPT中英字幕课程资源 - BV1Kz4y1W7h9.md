# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P16：15_日期和时间内置函数.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

🎼。Hello and welcome in this video we'll go over date and time SQL functions built into the database。

 so let's get started。

![](img/092f64368038b1efb3dc4c6f3ca15bda_1.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_2.png)

Most databases contain special data types for dates and times。



![](img/092f64368038b1efb3dc4c6f3ca15bda_4.png)

DB2 contains date， time， and timestamp types。

![](img/092f64368038b1efb3dc4c6f3ca15bda_6.png)

In DB2， date has eight digits for year， month and day。 time has six digits， hours。

 minutes and seconds。

![](img/092f64368038b1efb3dc4c6f3ca15bda_8.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_9.png)

Timetamp has 20 digits， year， month， day， hour， minute， seconds and microseconds。

 where double x represents month and6 Z's or zs represents microseconds。



![](img/092f64368038b1efb3dc4c6f3ca15bda_11.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_12.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_13.png)

Functions exist to extract the day， month， day of month， day of week， day of year， week， hour。

 minute， and second。

![](img/092f64368038b1efb3dc4c6f3ca15bda_15.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_16.png)

Let us look at some examples of queries for date and time functions。

 The day function can be used to extract the day portion from a date。 for example。

 to get the day portion for each rescue date involving cat。

 Select day rescue date from pet rescue where animal equals cat。



![](img/092f64368038b1efb3dc4c6f3ca15bda_18.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_19.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_20.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_21.png)

Date and time functions can be used in the wear clause， for example。

 to get the number of rescues during the month of May， that is for month5。

 select count star from pet rescue where month rescue date equals 05。



![](img/092f64368038b1efb3dc4c6f3ca15bda_23.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_24.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_25.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_26.png)

You can also perform date or time arithmetic。 for example。

 to find out what date it is three days after each rescue date。

 Maybe you want to know this because the rescue needs to be processed within three days。

 Select rescue date plus three days from pet rescue。



![](img/092f64368038b1efb3dc4c6f3ca15bda_28.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_29.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_30.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_31.png)

Special registers， current time and current date are also available， for example。

 to find out how many days have passed since each rescue date till now。

 select current date minus rescue date from pet rescue。 The result will be in years， months， days。



![](img/092f64368038b1efb3dc4c6f3ca15bda_33.png)

![](img/092f64368038b1efb3dc4c6f3ca15bda_34.png)

In this video， we looked at different types of built in SQL functions for working with dates and times。

 thank you for watching。