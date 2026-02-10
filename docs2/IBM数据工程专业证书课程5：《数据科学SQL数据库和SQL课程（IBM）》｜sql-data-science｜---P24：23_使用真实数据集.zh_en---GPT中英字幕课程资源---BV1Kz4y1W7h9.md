# IBM数据工程专业证书课程5：《数据科学SQL数据库和SQL课程（IBM）》｜sql-data-science｜ - P24：23_使用真实数据集.zh_en - GPT中英字幕课程资源 - BV1Kz4y1W7h9

🎼。Hello and welcome In this video， we'll give you a few hints and tips for working with real world data sets。

😊。

![](img/9798c5590d88ccb9513ec3fdc3b1341b_1.png)

Many of the real world data sets are made available as dot CSV files。

These are text files which contain data values typically separated by commas。 In some cases。

 a different separator， such as a semicolon may be used。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_3.png)

For this video， we will use an example of a file called Dogs dot CSv。

 Although this is a fictional data set that contains names of dogs and their breeds。

 we will use it to illustrate concepts that you will then apply to real data sets。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_5.png)

Sample contents of the Dos dot CSv file are shown here。 The first row in the table， in many cases。

 contains attribute labels， which map to column names in a table in Dogs dot CSV。

 The first row contains the name of three attributes。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_7.png)

I D is the name of the first attribute， and the subsequent rows contain I D values of 1，2， and 3。

 The name of the dog is the second attribute。 In this case， the dog names Wolfy。

 fluffy and Huggy are the values。

![](img/9798c5590d88ccb9513ec3fdc3b1341b_9.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_10.png)

And the third attribute is called breed， either the dominant breed or pure breed name。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_12.png)

It has values of German Shepherd， Pomeranian and Labrador。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_14.png)

As we've just seen， CSV files can have the first or a header row that contains the names of the attributes。

If you're loading the data into the database using the visual load tool in the database console。

 ensure the header in first row is enabled。

![](img/9798c5590d88ccb9513ec3fdc3b1341b_16.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_17.png)

This will map the attribute names in the first row of the CSV file into column names in the database table and the rest of the rows into the data rows in the table。

 as shown here， note that the default column names may not always be database or query friendly。

 and if that is the case， you may want to edit them before the table is created。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_19.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_20.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_21.png)

Now， let's talk about querying column names that are lower or mixed case。

 That is a combination of upper and lower case。 Let's assume we loaded the Dogs dot CSv file using the default column names from the CSV。

 if we try to retrieve the contents of the I column using the query select lowercase I from dogs will'll get an error。

 As shown， indicating the I is not valid。

![](img/9798c5590d88ccb9513ec3fdc3b1341b_23.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_24.png)

This is because the database parser assumes uppercase names by default。

 whereas when we loaded the CSV file into the database， it had the Id column name in mixed case， I。e。

 an uppercase I and a lowercase D In this case， to select data from a column with a mixed case name。

 We need to specify the column name in its correct case within double quotes as follows。

 Select double quotes， uppercase I， lowercase D and double quotes from dogs。

Ensure you use double quotes around the column name， and not single quotes。Next。

 we'll cover querying column names that have spaces and other characters in a CV file。

 If the name of the column contains spaces by default， the database may map them to underscores。

 For example， in the name of dog column， there are spaces in between the three words。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_26.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_27.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_28.png)

The database may change it to name， underscore of underscore dog。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_30.png)

Other special characters， like parentheses or brackets， may also get mapped to underscores。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_32.png)

Therefore， when you write a query， ensure you use proper case formatting within quotes and substitute special characters to underscores。

 as shown in this example， Select I D name of dog， breed， dominant breed。

 if not pure breed from dogs。

![](img/9798c5590d88ccb9513ec3fdc3b1341b_34.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_35.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_36.png)

Please note the underscore separating the words within double quotes。 Also。

 note the double underscore between breed and dominant as shown。 Finally。

 it's also important to note the trailing underscore after the word breed near the end of the query。

 This is used in place of the closing bracket。 When using quotes in Jupiter notebooks。

 you may be issuing queries in a note by first assigning them to Python variables。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_38.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_39.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_40.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_41.png)

In such cases， if your query contains double quotes， for example。

 to specify a mixed case column name， you could differentiate the quotes by using single quotes for the Python variable to enclose this SQL query and double quotes for the column names。

 for example， select query equals， open single quotes。

 select ID in double quotes from dogss close single quote Now。

 what if you need to specify single quotes within the query for example。

 to specify a value in the where clause。In this case。

 you can use backslash as the escape character as follows。Select query equals open single quote。

 select star from dogs where open double quote， name of dog close double equals backslash。

 single quote， Huggy， back slash single quote， close single quote。

If you have very long queries such as join queries or nested queries。

 it may be useful to split the query into multiple lines for improved readability In Python notebooks。

 you can use the back slash character to indicate continuation to the next row。

 as shown in this example。

![](img/9798c5590d88ccb9513ec3fdc3b1341b_43.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_44.png)

Persent SQL， select I D name of dog backslash from dogs backslash where name of dog equals Hugy。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_46.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_47.png)

It would be helpful at this point to take a moment to review the special characters， as shown。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_49.png)

Please keep in mind that you might get an error if you split the query into multiple lines in a Python notebook without the backslash。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_51.png)

When using SQL magic， you can use the double percent sQL in the first line of the cell in Jupiter notebooks。

It implies that the rest of the content of the cell is to be interpreted by SQL magic。 For example。

 double percent SQL new row， select ID D name of dog， new row from dogs。

 new row where name of dog equals Hugy。Again， please note the special characters as shown。

When using double percent SQL， the backslash is not needed at the end of each line。At this point。

 you might be asking， how would you restrict the number of rows retrieved。

 It's a good question because a table may contain thousands or even millions of rows。

 and you may only want to see some sample data， or look at just a few rows to see what kind of data the table contains。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_53.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_54.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_55.png)

You may be tempted to just do select star from table name to retrieve the results in a panda's data frame and do a head function on it。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_57.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_58.png)

But doing so may take a long time for a query to run。 Instead。

 you can restrict the results set by using the limit clause。 For example。

 use the following query to retrieve just the first three rows in a table called census data。

 Select star from census underscore data limit 3。

![](img/9798c5590d88ccb9513ec3fdc3b1341b_60.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_61.png)

![](img/9798c5590d88ccb9513ec3fdc3b1341b_62.png)

In this video， we looked at some considerations and tips for working with real world data sets。



![](img/9798c5590d88ccb9513ec3fdc3b1341b_64.png)

Thanks for watching。