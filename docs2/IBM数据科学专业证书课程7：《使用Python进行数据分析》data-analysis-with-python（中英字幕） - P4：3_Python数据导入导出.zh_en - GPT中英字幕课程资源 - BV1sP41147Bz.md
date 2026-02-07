# IBM数据科学专业证书课程7：《使用Python进行数据分析》data-analysis-with-python（中英字幕） - P4：3_Python数据导入导出.zh_en - GPT中英字幕课程资源 - BV1sP41147Bz

![](img/acf4810ea40926154766d4a56a7c2344_0.png)

In this video， we'll look at how to read in data using Python's panda's package。

 Once we have our data in Python， then we can perform all the subsequent data analysis procedures we need。



![](img/acf4810ea40926154766d4a56a7c2344_2.png)

![](img/acf4810ea40926154766d4a56a7c2344_3.png)

Data acquisition is a process of loading and reading data into notebook from various sources to read any data using Python's Pada's package。

 there are two important factors to consider format and failpath。



![](img/acf4810ea40926154766d4a56a7c2344_5.png)

![](img/acf4810ea40926154766d4a56a7c2344_6.png)

![](img/acf4810ea40926154766d4a56a7c2344_7.png)

Format is the way data is encoded。 We can usually tell different encoding schemes by looking at the ending of the file name。

 Some common encodings are CS V， Jason， X， L， S， X， H F， and so forth。



![](img/acf4810ea40926154766d4a56a7c2344_9.png)

![](img/acf4810ea40926154766d4a56a7c2344_10.png)

![](img/acf4810ea40926154766d4a56a7c2344_11.png)

The path tells us where the data is stored。 Usually it is stored either on the computer we are using or online on the Internet。

 In our case， we found a data set of used cars， which was obtained from the web address shown on the slide。



![](img/acf4810ea40926154766d4a56a7c2344_13.png)

![](img/acf4810ea40926154766d4a56a7c2344_14.png)

When Jerry entered the web address in his web browser， he saw something like this。

Each row is one data point。A large number of properties are associated with each data point。

Because the properties are separated from each other by comms， we can guess the data format is CSV。

 which stands for comma separated values。At this point。

 these are just numbers and don't mean much to humans。 But once we read in this data。

 we can try to make more sense out of it。In pandas。

 the RECSV method can read in files with columns separated by comms into a panda's data frame。



![](img/acf4810ea40926154766d4a56a7c2344_16.png)

Reading data in pandas can be done quickly in three lines。 First， import pandas。



![](img/acf4810ea40926154766d4a56a7c2344_18.png)

Then define a variable with a file path。

![](img/acf4810ea40926154766d4a56a7c2344_20.png)

And then use the read CSV method to import the data。



![](img/acf4810ea40926154766d4a56a7c2344_22.png)

However， Read CSV assumes that the data contains a header。



![](img/acf4810ea40926154766d4a56a7c2344_24.png)

Our data on used cars has no column headers， so we need to specify read CSV to not assign headers by setting header to none。



![](img/acf4810ea40926154766d4a56a7c2344_26.png)

![](img/acf4810ea40926154766d4a56a7c2344_27.png)

After reading the data set， it is a good idea to look at the data frame to get a better intuition and to ensure that everything occurred the way you expected。



![](img/acf4810ea40926154766d4a56a7c2344_29.png)

Since printing the entire data set may take up too much time and resources to save time。

 we can just use data frame dot head to show the first N rows of the data frame。



![](img/acf4810ea40926154766d4a56a7c2344_31.png)

![](img/acf4810ea40926154766d4a56a7c2344_32.png)

Similarly， data frame dot tail shows the bottom N rows of data frame。



![](img/acf4810ea40926154766d4a56a7c2344_34.png)

Here we printed out the first five rows of data。 It seems that the data set was read successfully。

 We can see that pandas automatically set the column header as a list of integers because we set header equals none when we read the data。

😊，It is difficult to work with the data frame without having meaningful column names， however。

 we can assign column names in pandas。

![](img/acf4810ea40926154766d4a56a7c2344_36.png)

In our present case， it turned out that we have the column names in a separate file online。

We first put the column names in a list called headers。

 Then we set D F dot columns equals headers to replace the default integer headers by the list。

 If we use the head method introduced in the last slide to check the data set。

 we see the correct headers inserted at the top of each column。At some point in time。

 after you've done operations on your data frame， you may want to export your panda's data frame to a new CSV file。



![](img/acf4810ea40926154766d4a56a7c2344_38.png)

You can do this using the method to underscore CSV to do this， specify the file path。

 which includes the file name that you want to write to。For example。

 if you would like to save data frame D as automobile。 CSv to your own computer。

 you can use the syntax D。2 underscore CSV。For this course， we will only read and save CSV files；

 however， panndas also supports importing and exporting of most data file types with different data set formats。



![](img/acf4810ea40926154766d4a56a7c2344_40.png)

![](img/acf4810ea40926154766d4a56a7c2344_41.png)

The code syntax for reading and saving other data formats is very similar to read or save CSV file。

 Each column shows a different method to read and save files into a different format。



![](img/acf4810ea40926154766d4a56a7c2344_43.png)

![](img/acf4810ea40926154766d4a56a7c2344_44.png)

![](img/acf4810ea40926154766d4a56a7c2344_45.png)