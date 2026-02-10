# IBM数据科学专业证书课程6：《数据库与SQL在数据科学中的应用（IBM）》sql-data-science（中英字幕） - P24：23_真实世界数据集处理.zh_en - GPT中英字幕课程资源 - BV1kP41147ce

。Hello and welcome In this video， we'll give you a few hints and tips for working with real world data sets。

😊。

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_1.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_2.png)

Many of the real world data sets are made available as dot CSV files。

 These are text files which contain data values typically separated by commas。 In some cases。

 a different separator such as a semicolon may be used。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_4.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_5.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_6.png)

For this video， we will use an example of a file called Dogs dot CSv。

 Although this is a fictional data set that contains names of dogs and their breeds。

 we will use it to illustrate concepts that you will then apply to real data sets。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_8.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_9.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_10.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_11.png)

Sample contents of the Dos dot CSv file are shown here。 The first row in the table， in many cases。

 contains attribute labels， which map a column names in a table In Do dot CSV。

 The first row contains the name of three attributes。I D is the name of the first attribute。

 and the subsequent rows contain I D values of 1，2， and 3。

 The name of the dog is the second attribute。 In this case， the dog names Wolfy。

 fluffy and Huggy are the values。And the third attribute is called breed。

 either the dominant breed or pure breed name。It has values of German Shepherd。

 Pomeranian and Labrador。As we've just seen， CSV files can have the first or a header row that contains the names of the attributes。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_13.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_14.png)

If you're loading the data into the database using the visual load tool in the database console。

 ensure the header in first row is enabled。

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_16.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_17.png)

This will map the attribute names in the first row of the CSV file into column names in the database table and the rest of the rows into the data rows in the table。

 as shown here， note that the default column names may not always be database or query friendly and if that is the case。

 you may want to edit them before the table is created。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_19.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_20.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_21.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_22.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_23.png)

Now， let's talk about querying column names that are lower or mixed case。

 That is a combination of upper and lower case。 Let's assume we loaded the Dogs dot CSv file using the default column names from the CSV。

 if we try to retrieve the contents of the I column using the query select lowercase I from dogs will' get an error。

 As shown， indicating the I is not valid。

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_25.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_26.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_27.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_28.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_29.png)

This is because the database parser assumes uppercase names by default。

 whereas when we loaded the CSV file into the database， it had the Id column name in mixed case I。e。

 an uppercase I and a lowercase D In this case， to select data from a column with a mixed case name we need to specify the column name in its correct case within double quotes as follows。

 select double quotes， uppercase I， lowercase D and double quotes from dogs。

Ensure you use double quotes around the column name， and not single quotes。Next。

 we'll cover querying column names that have spaces and other characters in a CSV file。

 If the name of the column contains spaces by default， the database may map them to underscores。

 For example， in the name of dog column。 There are spaces in between the three words。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_31.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_32.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_33.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_34.png)

The database may change it to name， underscore of underscore dog。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_36.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_37.png)

Other special characters， like parentheses or brackets， may also get mapped to underscores。Therefore。

 when you write a query， ensure you use proper case formatting within quotes and substitute special characters to underscores。

 as shown in this example， Select I D name of dog， breed， dominant breed。

 if not pure breed from dogs。Please note the underscore separating the words within double quotes。

 Also， note the double underscore between breed and dominant as shown。 Finally。

 it's also important to note the trailing underscore after the word breed near the end of the query。

 This is used in place of the closing bracket。 When using quotes in Jupiter notebooks。

 you may be issuing queries in a note by first assigning them to Python variables。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_39.png)

In such cases， if your query contains double quotes， for example。

 to specify a mixed case column name， you could differentiate the quotes by using single quotes for the Python variable to enclose this SQL query and double quotes for the column names。

 For example， select query equals， open single quotes。

 select ID in double quotes from Dos close single quote Now。

 what if you need to specify single quotes within the query for example。

 to specify a value in the where clause。In this case。

 you can use backslash as the escape character as follows。Select query equals open single quote。

 select star from dogs where open double quote， name of dog close double quote equals backslash。

 single quote， Huggy， back slash single quote， close single quote。

If you have very long queries such as join queries or nested queries。

 it may be useful to split the query into multiple lines for improved readability In Python notebooks。

 you can use the back slash character to indicate continuation to the next row。

 as shown in this example。

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_41.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_42.png)

Persent SQL， select ID D name of dog backslash from dogs backslash where name of dog equals Huggy。

It would be helpful at this point to take a moment to review the special characters， as shown。

Please keep in mind that you might get an error if you split the query into multiple lines in a Python notebook without the backslash。

When using SQL magic， you can use the double percent SQL in the first line of the cell in Jupiter notebooks。

It implies that the rest of the content of the cell is to be interpreted by SQL magic。 For example。

 double percent SQL new row， select I D name of dog， new row from dogs。

 new row where name of dog equals Hugy。Again， please note the special characters as shown。

When using double percent SQL， the backslash is not needed at the end of each line。At this point。

 you might be asking， how would you restrict the number of rows retrieved。

 It's a good question because a table may contain thousands or even millions of rows。

 and you may only want to see some sample data or look at just a few rows to see what kind of data the table contains。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_44.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_45.png)

You may be tempted to just do select star from table name to retrieve the results in a panda's data frame and do a head function on it。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_47.png)

But doing so may take a long time for a query to run。 Instead。

 you can restrict the results set by using the limit clause。 For example。

 use the following query to retrieve just the first three rows in a table called census data。

 Select star from census underscore data limit 3。

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_49.png)

In this video， we looked at some considerations and tips for working with real world data sets。



![](img/2fa47e05e4be5f71b44eb655ea65c7e0_51.png)

![](img/2fa47e05e4be5f71b44eb655ea65c7e0_52.png)

Thanks for watching。