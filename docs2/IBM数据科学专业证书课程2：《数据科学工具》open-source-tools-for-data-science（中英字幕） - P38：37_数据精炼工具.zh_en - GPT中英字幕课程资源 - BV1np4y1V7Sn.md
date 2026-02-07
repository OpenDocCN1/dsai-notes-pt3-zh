# IBM数据科学专业证书课程2：《数据科学工具》open-source-tools-for-data-science（中英字幕） - P38：37_数据精炼工具.zh_en - GPT中英字幕课程资源 - BV1np4y1V7Sn

Hi， I'm Sonali Serringgi Devev。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_1.png)

Data scientists often end up spending a lot of time doing mundane tasks， like cleansing。

 shaping and preparing data。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_3.png)

Typically， these tasks are roadblocks for starting the more enjoyable part of analyzing their data sets or building and training machine learning models。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_5.png)

This is because data sets typically are not enough format that can be readily used。

They first need to be cleansed refined before they are usable by a data scientist。

IBM Data Refry addresses this issue and simplifies the task of refining data and its workflows。

It provides a self service data preparation environment where you can quickly analyze。

 cleanse and prepare dataset sets。Data refineries available with Watson Studio on Public cloud。

 private cloud， and desktop。In the rest of the video。

 we will walk through a scenario and see data refinery in action In this scenario we will use data refinery to find the best deals using data about discounts offered over time。

We will then automate the analysis to run on a regular schedule。Before she starts。

 she looks at the data distribution and notices that the I column is missing data。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_7.png)

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_8.png)

She visualizes the offer column。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_10.png)

And notices that it contains valuable information about discounts。

Many fields contain the per of information。Some contained references to previous price。

 indicating a new reduced price being available。She decides to derive scene from offer。

She uses the conditional weekly operation。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_12.png)

To derive in the top。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_14.png)

不想信。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_16.png)

Next， she uses a fter operation。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_18.png)

To eliminate deals。That I'm not answer。Pick up the bargains。She uses the replace substr operation。

And provides a pattern that extracts the discounts from the offer。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_20.png)

After converting the discount values to a decimal。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_22.png)

She can visually see the discounts that were available。

 She needs to find the months that offered the best deals。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_24.png)

She visualizes the date updated and notices that the date field has a variety of formats。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_26.png)

Somevi dashes。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_28.png)

Someud slashes。And some with months as text。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_30.png)

She hopes data refinery can normalize the data and extract the month。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_32.png)

She uses the convert column operation。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_34.png)

To convert to date and select YMD。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_36.png)

Next， she extracts month。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_38.png)

And creates a derived column。Called discountment。The data now represents all brands and products providing sales and the month the offer was available。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_40.png)

The data scientist is only interested in her preferred brands Over time。

 she has built a list of preferred brands and has imported the data in her project。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_42.png)

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_43.png)

Data refinery provides relational operations。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_45.png)

Such as left， inner， right， full， semi and anti join。

To ensure that the data only contains her preferred brand， she uses a semijo operation。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_47.png)

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_48.png)

Which narrows the branch to match her preferences。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_50.png)

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_51.png)

She then selects the keys for the join。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_53.png)

And the resulting fields。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_55.png)

The visual result now confirms that the brands match a preference and the best possible deals she needs to perform some aggregations。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_57.png)

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_58.png)

Several features determine a good deal。 She is interested in the best offer and duration when the discounts are active。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_60.png)

Aggregating sale data will help understand the de。 She groups the columns by brand and discount fund。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_62.png)

And calculates the maximum discount。Finally， she thoughts the result。

Data refinery is now displaying the best deals by brand preferences and the duration。

 which the offer is available。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_64.png)

Yes。The last step is to execute the analysis on the full dataset set。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_66.png)

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_67.png)

She asked a full analysis。Which he can monitor。For the completion status。



![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_69.png)

It's time to automate the analysis so it runs on a regular basis。

 data in that database can grow over time。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_71.png)

She uses a personalized runtime。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_73.png)

To match the larger data volumes。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_75.png)

And sets his schedule for automation。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_77.png)

The hourly schedule reads from updated data。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_79.png)

From the database。 and writes。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_81.png)

To the target table， Peter refinery has helped her uncover deals in the raw data through a small set of operations and transformations with the bulk of the work done for her。

 Thank you for watching。

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_83.png)

![](img/4d1c7dfa0b92f7f0c5aaa4742b50ec9a_84.png)