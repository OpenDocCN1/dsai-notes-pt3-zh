# Mathworks《实用数据科学与MATLAB（数据探索、特征工程、机器学习、毕业项目）｜Practical Data Science with MATLAB》 p33 32_执行分组计算.zh_en [BV1Jr421w7wL_p33]

🎼，In a previous lesson， you used categorical variables to filter tables and create visualizations like histograms。

You also calculated statistics on table variables。

![](img/90d117ff3b3c5852f5818a648ee7f54c_1.png)

Now you'll bring these concepts together and begin analyzing groups within the data。



![](img/90d117ff3b3c5852f5818a648ee7f54c_3.png)

To start， suppose you want to know the number of severe weather events and property damage for each month of the year。



![](img/90d117ff3b3c5852f5818a648ee7f54c_5.png)

You do this by performing group calculations。

![](img/90d117ff3b3c5852f5818a648ee7f54c_7.png)

A group calculation first involves grouping the data by some characteristic， like here， by month。

Then you compute a statistic for each group。In this example。

 the number of severe weather events and the sum of the property damage。



![](img/90d117ff3b3c5852f5818a648ee7f54c_9.png)

Finally， combine all the results in a table for analysis。



![](img/90d117ff3b3c5852f5818a648ee7f54c_11.png)

Now， let's performed the same computations on our 2013 severe storm events and create a table like the one here。



![](img/90d117ff3b3c5852f5818a648ee7f54c_13.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_14.png)

There are multiple ways of performing this calculation。You could filter your table for each month。

And some， the property cost variable。But this is a tedious task when there are many groups。



![](img/90d117ff3b3c5852f5818a648ee7f54c_16.png)

How can you do this without repeating the same steps over and over。



![](img/90d117ff3b3c5852f5818a648ee7f54c_18.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_19.png)

To see how， let's start with a live script that has the 2013 severe storm events data already imported into a table called data。

Additionally， the month categories are reordered chronologically。

Now let's take a look at the available live tasks。

![](img/90d117ff3b3c5852f5818a648ee7f54c_21.png)

Would provide interactive tools for common analyses， like cleaning outliers and smoothing data。

The goal is to compute group statistics， so insert the compute by group Live task into your script。



![](img/90d117ff3b3c5852f5818a648ee7f54c_23.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_24.png)

There are three main available options for this task。



![](img/90d117ff3b3c5852f5818a648ee7f54c_26.png)

Compute stats by group perform statistical calculations。

Transform by group is for transformations like normalizing data。

And filter by group removes rows based on a specified condition。



![](img/90d117ff3b3c5852f5818a648ee7f54c_28.png)

For our task， we'll use the first option。

![](img/90d117ff3b3c5852f5818a648ee7f54c_30.png)

In the live task， select the Se Stm Event Data set。And then rename the output to monthly damage。Now。

 group the data by month by selecting month from the drop down menu。

The next step is to select the type of statistical analysis you want to perform。



![](img/90d117ff3b3c5852f5818a648ee7f54c_32.png)

The Computs per group droprop down menu lists the different computations you can choose from。



![](img/90d117ff3b3c5852f5818a648ee7f54c_34.png)

Counts is selected as the default method。

![](img/90d117ff3b3c5852f5818a648ee7f54c_36.png)

These options have already produced a 12 by2 output table with the results。



![](img/90d117ff3b3c5852f5818a648ee7f54c_38.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_39.png)

The first variable in this table is a list of all the month。

The second variable group count is the number of observations in each group。



![](img/90d117ff3b3c5852f5818a648ee7f54c_41.png)

In other words， this is the total number of all severe storm events that occurred during that month。



![](img/90d117ff3b3c5852f5818a648ee7f54c_43.png)

Once the data is grouped， you're ready to perform additional statistical computations。



![](img/90d117ff3b3c5852f5818a648ee7f54c_45.png)

Since we want to know the total property damage in each month， select specified variables。



![](img/90d117ff3b3c5852f5818a648ee7f54c_47.png)

And then， property cost。Next， under computations per group， in addition to counts， select sum。



![](img/90d117ff3b3c5852f5818a648ee7f54c_49.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_50.png)

You now have a table that shows the number of severe storm events for each month and the total cost of the property damage caused by those events。



![](img/90d117ff3b3c5852f5818a648ee7f54c_52.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_53.png)

Finally， let's take a look at the generated code for the grouping task you just performed。

This code can be used to create the table of results without the need to open the live task。



![](img/90d117ff3b3c5852f5818a648ee7f54c_55.png)

You can also replace the live task with the code by clicking convertt Task to Editable code。



![](img/90d117ff3b3c5852f5818a648ee7f54c_57.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_58.png)

The computations you performed in the live task were done using the group summary function。

Notice that the function took four inputs。Your data set。The grouping variable。

Your choice of statistical computations。And finally。

 the variable that you want to perform the computation on。



![](img/90d117ff3b3c5852f5818a648ee7f54c_60.png)

But what if you need to create groups based on multiple variables like month and state。

 and you need to perform multiple calculations on the groups。



![](img/90d117ff3b3c5852f5818a648ee7f54c_62.png)

![](img/90d117ff3b3c5852f5818a648ee7f54c_63.png)

Can you do this？Of course。Let's try grouping the results using two category variables。

 month and state。

![](img/90d117ff3b3c5852f5818a648ee7f54c_65.png)

And also calculate the average cost of property damage。



![](img/90d117ff3b3c5852f5818a648ee7f54c_67.png)

Go back to the live task and click the plus button to add a new group by field。



![](img/90d117ff3b3c5852f5818a648ee7f54c_69.png)

From the droprop down menu， selectSt。And under computations per group。



![](img/90d117ff3b3c5852f5818a648ee7f54c_71.png)

In addition to counts and sum， select mean。

![](img/90d117ff3b3c5852f5818a648ee7f54c_73.png)

The output is a table with the total number of weather events for each pair of month and state。

 as well as the total and average cost of property damage。



![](img/90d117ff3b3c5852f5818a648ee7f54c_75.png)

To see how these options affected the generated code。Convert the task to editable code。



![](img/90d117ff3b3c5852f5818a648ee7f54c_77.png)

And notice how state and mean were added to the group summary function。Because there's more than one。

 they had to be enclosed in square brackets。You're now able to perform calculations by group。



![](img/90d117ff3b3c5852f5818a648ee7f54c_79.png)

Take some time to practice on your own。

![](img/90d117ff3b3c5852f5818a648ee7f54c_81.png)

For example。Try to group by event type。

![](img/90d117ff3b3c5852f5818a648ee7f54c_83.png)

And see which type caused the highest total amount of damage。What about the highest average。



![](img/90d117ff3b3c5852f5818a648ee7f54c_85.png)

。