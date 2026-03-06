# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p117 P117 04_Python中的SQLite探索性查询 -BV1z86nB9EGz_p117-

![](img/1263b41adf93f46f9494837d82682e51_0.png)

In this lesson， I want to demonstrate how you can perform some exploratory queries using SQL that are similar to using the info and head methods in Python to explore a data frame。

Now， this is really important to be able to do with SQL queries because many times tables in a database have so much data in them that you can't download everything to your computer and analyze it there。

So we're going to need to use SQL queries to identify how we can filter the data that we do read into our computer。

All right， so let's go ahead and demonstrate this from a Jupiter lab environment just using Python。

 which is really important because it will simplify the process if we can keep it within the same file。



![](img/1263b41adf93f46f9494837d82682e51_2.png)

So the first thing we're going to do is import functions from the pandas and SQLite 3 modules since we're going to interact with a SQLite database。

 and then we're going to establish a connection。 Now， for our purposes。

 this is a connection for the techca database。

![](img/1263b41adf93f46f9494837d82682e51_4.png)

And so I'm going to use the SQL dot connect function and just refer to that database name。

 If you were using a MySQL database， then you'd have to change that connection there。

But once we're connected to it， we can go ahead and perform some exploratory queries。

So one of the first things that you'll want to do in a database environment is understand the tables that are in the database and how they're related to each other。

Now， the best thing is to have an entity resource diagram like this one。

 but if we're operating from within a Python environment， we can't really get that easily。

 but you can get some information that can help you reconstruct that or remind you of some important details。



![](img/1263b41adf93f46f9494837d82682e51_6.png)

So we're going to use this panndas Read SQL function。

 and in here there is this query that only works with SQLite databases。

 if you're using a MySQL database or MysQL server or Postgres。

 then you'd need to use a different query。But for any SQLite database。

 you can use select star from SQLite master where table equals in quotation marks table。Alright。

 so I've got the connection object in there， I'm going to save it as a data frame。

 and then I'm going to set the row names or the index values equal to the values from the name column and display that data frame。



![](img/1263b41adf93f46f9494837d82682e51_8.png)

![](img/1263b41adf93f46f9494837d82682e51_9.png)

Okay， so from here you can see that I've got six tables。



![](img/1263b41adf93f46f9494837d82682e51_11.png)

And these are the same six tables that you see in the entity resource diagram here。 That's helpful。

 But let's say I want to identify the columns in each of these tables。 Well。

 let's narrow down to a specific table。 Let's look at the transactions table。



![](img/1263b41adf93f46f9494837d82682e51_13.png)

In this data frame， I've got the SQL column。 and in here， I've got the schema just for that table。



![](img/1263b41adf93f46f9494837d82682e51_15.png)

So I can simply use the filtering approach that I want to use。 In this case。

 I'm going to use the Lo method。

![](img/1263b41adf93f46f9494837d82682e51_17.png)

And I'm going to indicate that I want the transactions row and the values in the SQL column。

 And then I'm going to include that within this print function so that it looks nice。



![](img/1263b41adf93f46f9494837d82682e51_19.png)

All right， so this tells me the SQL command to create this table。

 So this is the schema here for this table。And this allows me to see the different columns。

Their data type， So unique ideas is an integer。 And this one also happens to be the primary key。

And I've got all these other columns and their data types， and importantly， for databases。

 I can see which columns are foreign keys。 So for instance， this customer ID column。

 which is a text type。References the customer I D column in the customer's table。Alright。

 so I can make linkages there。 Allright， so this is part of the info method。

 basically of a panda's data frame， but it doesn't tell me some other things。

 So what if I want to also find out the number of rows in this table。Well。

 I can use this select count star from transactions that query right there。



![](img/1263b41adf93f46f9494837d82682e51_21.png)

And that will tell me the number of rows。 So if I take that query and embed it within the read SQL function and add the connection object。



![](img/1263b41adf93f46f9494837d82682e51_23.png)

It'll return a single value as a data frame。

![](img/1263b41adf93f46f9494837d82682e51_25.png)

And this tells me I've got 150000 rows in this table here。

 What if I want to look at the first five rows of this without having to download everything and then use the head method。



![](img/1263b41adf93f46f9494837d82682e51_27.png)

![](img/1263b41adf93f46f9494837d82682e51_28.png)

I can use a query that you're probably already familiar with。

 I can select every column from the transactions table and then limit it to just the first five rows。



![](img/1263b41adf93f46f9494837d82682e51_30.png)

Alright， so if I do that， I can real quickly see what this data looks like。 All right。

 Now when I look at this， there's something that I see that stands out。

 And one of the important things that we often want to look at is a number of missing values。

 And again， the pandas info method for a data frame tells us that really quickly。



![](img/1263b41adf93f46f9494837d82682e51_32.png)

But there's not something exactly like that with Sequel。

But we can create a query that will tell us the number of missing values in a column。

 So let's go ahead and run this next query to identify the number of missing values in the customer I D column。

What we're going to do is we're going to select and then count the number of values。

 so you saw that before this is just counting out the number of values。From the transactions table。

 where。The customer Id column is null。 Allright， so that's important that you can recognize you can identify null observations。



![](img/1263b41adf93f46f9494837d82682e51_34.png)

And when I do that， it tells me that there are no missing values。 Well。

 the reason why it says there's no missing values， even though we can see them。

 is because if we go back up here， look at the customer I D。 This is a text column。

Or a character string column。 So these are not missing values。 It's， well， they are。

 but they're stored as N A N， that text。 So if I just change this to。



![](img/1263b41adf93f46f9494837d82682e51_36.png)

![](img/1263b41adf93f46f9494837d82682e51_37.png)

N A N and run that。 you can see that I'm not using equals here。 I can use is as well。

 It tells me how many basically missing values there are。 So 782896。 at this point。

 let's say that we have decided on the data that we want to read in as a result of exploring this。

 Now we can go ahead and read in the data。 So I'm going to create a query。

 I'm going to read in every column from the transactions table where the revenue。

 the value of the revenue column is greater than two。



![](img/1263b41adf93f46f9494837d82682e51_39.png)

Alright， so I'll create that as a variable named query。And then。

I'll use that in my Read SQL function， save as a data frame， look at information。Okay。

 this looks good。 I've got 570，174 rows looks like exactly what I want， we'll assume that's the case。

 and so I can now go ahead and close the connection and continue with my calculations and analysis for this data。



![](img/1263b41adf93f46f9494837d82682e51_41.png)

So really， I wanted to highlight how you can explore tables in a database。

 as well as a database itself all from within the Python environment。

 Hopefully that' cell will foray so you don't have to try and download everything and overflow your computer's memory。



![](img/1263b41adf93f46f9494837d82682e51_43.png)