# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P16：15_日期时间函数.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

。Hello and welcome in this video we'll go over date and time SQL functions built into the database so let's get started。



![](img/4e673ac29708bbec11aa079b28f9282c_1.png)

![](img/4e673ac29708bbec11aa079b28f9282c_2.png)

Most databases contain special data types for dates and times。



![](img/4e673ac29708bbec11aa079b28f9282c_4.png)

DB2 contains date， time， and timestamp types。

![](img/4e673ac29708bbec11aa079b28f9282c_6.png)

In DB2， date has eight digits for year， month and day， time has six digits， hours。

 minutes and seconds。

![](img/4e673ac29708bbec11aa079b28f9282c_8.png)

![](img/4e673ac29708bbec11aa079b28f9282c_9.png)

Timetamp has 20 digits， year， month， day， hour， minute， seconds and microseconds。

 where double x represents month and six Z's or zs represents microseconds。



![](img/4e673ac29708bbec11aa079b28f9282c_11.png)

![](img/4e673ac29708bbec11aa079b28f9282c_12.png)

![](img/4e673ac29708bbec11aa079b28f9282c_13.png)

Functions exist to extract the day， month， day of month， day of week， day of year， week， hour。

 minute， and second。

![](img/4e673ac29708bbec11aa079b28f9282c_15.png)

![](img/4e673ac29708bbec11aa079b28f9282c_16.png)

Let us look at some examples of queries for date and time functions。

 The day function can be used to extract the day portion from a date。 for example。

 to get the day portion for each rescue date involving cat。

 Select day rescue date from pet rescue where animal equals cat。



![](img/4e673ac29708bbec11aa079b28f9282c_18.png)

![](img/4e673ac29708bbec11aa079b28f9282c_19.png)

![](img/4e673ac29708bbec11aa079b28f9282c_20.png)

![](img/4e673ac29708bbec11aa079b28f9282c_21.png)

Date and time functions can be used in the wear clause， for example。

 to get the number of rescues during the month of May， that is for month5。

 select count star from pet rescue where month rescue date equals 05。



![](img/4e673ac29708bbec11aa079b28f9282c_23.png)

![](img/4e673ac29708bbec11aa079b28f9282c_24.png)

![](img/4e673ac29708bbec11aa079b28f9282c_25.png)

You can also perform date or time arithmetic。 for example。

 to find out what date it is three days after each rescue date。

 Maybe you want to know this because the rescue needs to be processed within three days。

 Select rescue date plus three days from pet rescue。



![](img/4e673ac29708bbec11aa079b28f9282c_27.png)

![](img/4e673ac29708bbec11aa079b28f9282c_28.png)

![](img/4e673ac29708bbec11aa079b28f9282c_29.png)

![](img/4e673ac29708bbec11aa079b28f9282c_30.png)

Special registers， current time and current date are also available。 for example。

 to find out how many days have passed since each rescue date till now。

 select current date minus rescue date from P rescue。 The result will be in years， months， days。



![](img/4e673ac29708bbec11aa079b28f9282c_32.png)

![](img/4e673ac29708bbec11aa079b28f9282c_33.png)

In this video， we looked at different types of built in SQL functions for working with dates and times。

 thank you for watching。