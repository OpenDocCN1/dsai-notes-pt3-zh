# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p121 4_准备数据集.zh_en [BV1Jr421w7wL_p121]

🎼。

![](img/0bd42eda6c240f46e665ee383e50e6fc_1.png)

Good work adding the pickup and drop off regions to the table of taxi trips。Data。

 exploration and preparation are important steps， as raw data is often poorly organized。

There are two more steps in the module to get the data ready for feature engineering。

Exploring and cleaning the data。In creating the grouped summary table。

You may recall from coursese 3 that some trips had recording errors。



![](img/0bd42eda6c240f46e665ee383e50e6fc_3.png)

A basic reprocessing function was used to remove these trips。



![](img/0bd42eda6c240f46e665ee383e50e6fc_5.png)

Such a cleaning process is required to ensure that your data only represents the reasonable trips that you want to include in your predictive model。



![](img/0bd42eda6c240f46e665ee383e50e6fc_7.png)

However， the cleaning done in Cose 3 is just a baseline。

And it is not the only cleaning that can be done。

![](img/0bd42eda6c240f46e665ee383e50e6fc_9.png)

For instance， the minimum allowed fare for a taxi trip in 2015 was $2。50。



![](img/0bd42eda6c240f46e665ee383e50e6fc_11.png)

So not only do the negative values represent recording errors。

 but it's likely the values below this lower limit do as well。



![](img/0bd42eda6c240f46e665ee383e50e6fc_13.png)

![](img/0bd42eda6c240f46e665ee383e50e6fc_14.png)

Can you think of other variables or combinations of variables that could indicate erroneous recordings？

Here is your chance to clean those absurd values。

![](img/0bd42eda6c240f46e665ee383e50e6fc_16.png)

After you've completed this initial cleaning step， you are ready to generate the grouped summary table that will be used for machine learning。



![](img/0bd42eda6c240f46e665ee383e50e6fc_18.png)

Several lessons from courses one and two are worth reviewing here。



![](img/0bd42eda6c240f46e665ee383e50e6fc_20.png)

To start， you'll need to group the taxi trips by hour。



![](img/0bd42eda6c240f46e665ee383e50e6fc_22.png)

You've already had practice with the date shift function to manipulate date time values in course 2。

 and it will be helpful here in assigning each trip to a specific hour。



![](img/0bd42eda6c240f46e665ee383e50e6fc_24.png)

Next， you can count the number of trips in a certain region and at a particular hour using the group summary function。



![](img/0bd42eda6c240f46e665ee383e50e6fc_26.png)

![](img/0bd42eda6c240f46e665ee383e50e6fc_27.png)

Like many of the Mat of functions that you've learned about so far。

 group summary can be used to do much more than what has been covered in this course。



![](img/0bd42eda6c240f46e665ee383e50e6fc_29.png)

You can learn more by exploring the documentation。

![](img/0bd42eda6c240f46e665ee383e50e6fc_31.png)

In this case， you can see how the group summary function can use multiple grouping variables at a time。



![](img/0bd42eda6c240f46e665ee383e50e6fc_33.png)

Which is useful if you need to group taxi trips by both region and our simultaneously。



![](img/0bd42eda6c240f46e665ee383e50e6fc_35.png)

Also， remember that your final summary table will need to represent the number of taxi trips in groups。



![](img/0bd42eda6c240f46e665ee383e50e6fc_37.png)

Defined by pickup region and hour。

![](img/0bd42eda6c240f46e665ee383e50e6fc_39.png)

As well as drop off region and hour。Each result will require its own use of the group summary function。



![](img/0bd42eda6c240f46e665ee383e50e6fc_41.png)

Once you have these values， as well as some summary statistics on the average trip distances。

 durations and fares。You'll likely need to join some tables together。

Remember that you practice combining data in Co 2。And the live task for joining tables may be useful here。



![](img/0bd42eda6c240f46e665ee383e50e6fc_43.png)

You can also direct the merging process by selecting multiple key variables。

 which is required in this case， because groups in the summary tables are defined by both region and hour。



![](img/0bd42eda6c240f46e665ee383e50e6fc_45.png)

![](img/0bd42eda6c240f46e665ee383e50e6fc_46.png)

Once you have a table with the pickup and drop off counts for each region。

You can start estimating the demand for taxis by calculating the net pickups。



![](img/0bd42eda6c240f46e665ee383e50e6fc_48.png)

The readings following this video explain the two tasks presented here。

As well as provide helpful links to previous materials in the specialization。



![](img/0bd42eda6c240f46e665ee383e50e6fc_50.png)

Good luck。

![](img/0bd42eda6c240f46e665ee383e50e6fc_52.png)