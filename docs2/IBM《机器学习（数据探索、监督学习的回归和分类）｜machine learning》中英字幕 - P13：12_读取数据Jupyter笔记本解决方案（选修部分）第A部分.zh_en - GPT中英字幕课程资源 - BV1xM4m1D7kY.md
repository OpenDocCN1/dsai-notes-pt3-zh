# IBM《机器学习（数据探索、监督学习的回归和分类）｜machine learning》中英字幕 - P13：12_读取数据Jupyter笔记本解决方案（选修部分）第A部分.zh_en - GPT中英字幕课程资源 - BV1xM4m1D7kY

All right， let's get started in our first notebook that'll teach us how to read the data from our different data sources。



![](img/3fab3db4190950b2686d26a66e0b8acd_1.png)

Our learning objective for this Ju notebook will be to create a SQL database connection to a sample SQL database and read records from that database。



![](img/3fab3db4190950b2686d26a66e0b8acd_3.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_4.png)

And we'll also explore some common input parameters for our We SQL function。



![](img/3fab3db4190950b2686d26a66e0b8acd_6.png)

The packages that we'll use are going to be pandas from pandas we're going to use the Read SQL function and we'll also use SQL 3。

 which is going to connect specifically to an SQL 3 database and we'll see in a second that that's going to be somewhat interchangeable with any of your other。



![](img/3fab3db4190950b2686d26a66e0b8acd_8.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_9.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_10.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_11.png)

SQL databases that you may be using at your workplace。



![](img/3fab3db4190950b2686d26a66e0b8acd_13.png)

So the first step is going to be to import the necessary libraries， S like3 is SQ3， panndadas。o。

sqL as PS and pandas as P。

![](img/3fab3db4190950b2686d26a66e0b8acd_15.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_16.png)

As I just mentioned， you may be working with a different database at your workplace such as Microsoft SQL Server。

 Postgress， MySQL DB2 family， so on and so forth， some common libraries that you can interchange here for SQL 3。

 our SQL alchemy that will work actually across a couple of them including Microsoft SQL Server。

 PschoPG2 is for Postgres， MysQL DB for MySQL。

![](img/3fab3db4190950b2686d26a66e0b8acd_18.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_19.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_20.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_21.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_22.png)

And our first step。

![](img/3fab3db4190950b2686d26a66e0b8acd_24.png)

Is going to be， as we want to connect to our database is just say where does our database actually live。

 So we'll pass that into a string here。 We have data forward slash classicro。 Db。

 That just means that we have a folder called data。 and in that folder。

 we have a file a database called classic rock Db。 and then we're going to set our connection。

 in order him to use our SQ3 library and do Sq3 do connection using that function。

 we just pass in the argument of our path。

![](img/3fab3db4190950b2686d26a66e0b8acd_26.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_27.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_28.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_29.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_30.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_31.png)

When I run this code。

![](img/3fab3db4190950b2686d26a66e0b8acd_33.png)

We've created a connection object， and I can show you here that that's just a SQite connection。



![](img/3fab3db4190950b2686d26a66e0b8acd_35.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_36.png)

And we're going to use that in a second right over here。

 so now that we've got our connection to our database。

 we can perform queries using the SQL syntax and load their results into a pandas data frame。



![](img/3fab3db4190950b2686d26a66e0b8acd_38.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_39.png)

So as mentioned， we're going to use that SQL syntax。

 and we're just going to set query this variable equal to this string， select star from rock songs。

 rock songs being at table within our classic rock database。



![](img/3fab3db4190950b2686d26a66e0b8acd_41.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_42.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_43.png)

We're then going to execute this query in order to do so， we do P， write Padas do readsQL。



![](img/3fab3db4190950b2686d26a66e0b8acd_45.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_46.png)

And all we're doing is reading in our data。

![](img/3fab3db4190950b2686d26a66e0b8acd_48.png)

We pass in the query。As well as the connection that we established earlier。



![](img/3fab3db4190950b2686d26a66e0b8acd_50.png)

And when I run this code。We set observations equal to this function pulling out that query from this connection that created our pandas data frame。

 and we can see the first five rows of that pandas data frame。 These are our different rock cls。



![](img/3fab3db4190950b2686d26a66e0b8acd_52.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_53.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_54.png)

Now we can run any supported SQL query， all we have to do is write the query appropriately using the right SQL syntax。



![](img/3fab3db4190950b2686d26a66e0b8acd_56.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_57.png)

So here we'll select the artist。 We'll select release here。



![](img/3fab3db4190950b2686d26a66e0b8acd_59.png)

We'll select the count of that unique combination， and we'll call that the number of songs by that combination。



![](img/3fab3db4190950b2686d26a66e0b8acd_61.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_62.png)

We will get the average play count for those songs using our average function and call that average plays or pulling it from rock songs we group by our artist and release year。



![](img/3fab3db4190950b2686d26a66e0b8acd_64.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_65.png)

And we're going to order it by our number of songs。

 and we're going to make that descending from largest to small us。



![](img/3fab3db4190950b2686d26a66e0b8acd_67.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_68.png)

Then again， all we have to do is do P， we could do PDS or PDd。 readsQL。

 we pass in the query and the connection， this is our new query and the same connection as before。



![](img/3fab3db4190950b2686d26a66e0b8acd_70.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_71.png)

And received see for the first five values， the Beatles in 1967 released 23 songs。

 and they had an average number of 6。5 plays。

![](img/3fab3db4190950b2686d26a66e0b8acd_73.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_74.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_75.png)

So there are a number of common parameters that can be used to read in SQL data with formatting。



![](img/3fab3db4190950b2686d26a66e0b8acd_77.png)

We can coerce float， attempt to force numbers into float types， we can parse dates。

 so within that we'd want to list columns that we know should be brought in as dates into our pandas data frame and then chunk size we can define the number of rows to include in each chunk。



![](img/3fab3db4190950b2686d26a66e0b8acd_79.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_80.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_81.png)

So let's have a look at using some of these parameters， we're going to use the same query as before。



![](img/3fab3db4190950b2686d26a66e0b8acd_83.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_84.png)

And then we have our observations generator， we're going to create a generator object here。

 so we're going to do pulling in chunk sizes of five PD。 readsQL， our query。



![](img/3fab3db4190950b2686d26a66e0b8acd_86.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_87.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_88.png)

Our connection Coerce flow equals true， this won't affect this data set because the floats are already correctly parse。



![](img/3fab3db4190950b2686d26a66e0b8acd_90.png)

Parse dates， we want the release here to be brought in as a date value。



![](img/3fab3db4190950b2686d26a66e0b8acd_92.png)

And then chunk size equals 5 allows for streaming results as a series of shorter tables。

 So we're going to get chunks of five rows at a time。



![](img/3fab3db4190950b2686d26a66e0b8acd_94.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_95.png)

When we pull this in。 and that's why this is a generator object。 generator object。

 just as review is just similar to an iterator， such as a list， something that you can pass through。

 but it won't save the entire list in memory。 It'll just pull out the。



![](img/3fab3db4190950b2686d26a66e0b8acd_97.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_98.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_99.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_100.png)

Pull out as you call out that value so you won't have to waste as much memory in using that object compared to an iterator such as a list。



![](img/3fab3db4190950b2686d26a66e0b8acd_102.png)

So four index comma observations in enumerate observation generator。

 so enumerate what that's going to do is as we pull out each object from that generator。

 it's also going to pull out a number， so it'll be 0 and then first object one。

 and then the second object。

![](img/3fab3db4190950b2686d26a66e0b8acd_104.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_105.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_106.png)

Right， so at first index will be 0。 Observations will be the first observations object。

 Then it will be one。 then the second observations object。



![](img/3fab3db4190950b2686d26a66e0b8acd_108.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_109.png)

And we're going to only do that up until five， right， So if index is less than 5。

 then we're going to print both the index。

![](img/3fab3db4190950b2686d26a66e0b8acd_111.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_112.png)

And we're going to pass in that number here。As well as displaying the five rows for that observation from our observations generator。



![](img/3fab3db4190950b2686d26a66e0b8acd_114.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_115.png)

So let's run that to see。Here we see。The five rows that are pulled out。 the Beatles， LED Zepppelin。

 the Beatles， again， using that artist and releaseier group by。

 we now have also the releaseier before we saw that it just had a number as a float。 Now。

 it's parsed as a date。

![](img/3fab3db4190950b2686d26a66e0b8acd_117.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_118.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_119.png)

Actually， a date time object。 so as date and time。

![](img/3fab3db4190950b2686d26a66e0b8acd_121.png)

And then we see the next five values， so on and so forth up until our index is less than five。



![](img/3fab3db4190950b2686d26a66e0b8acd_123.png)

![](img/3fab3db4190950b2686d26a66e0b8acd_124.png)