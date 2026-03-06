# 伊利诺伊大学【中英⚡商业分析｜Business Analytics Specialization】 p113 P113 03_基础 SQL 命令 -BV1z86nB9EGz_p113-

![](img/462042c07d7e681b448ad767da12d165_0.png)

In this video， we will introduce you to a database version of the techca data and show you how easy it is to extract data from that database using basic SQL queries before we start using the SQL queries。

 it's important to understand the different tables in a database and to understand how they're related So what we're looking at here is an entity resource diagram or ERD that is provided by working in a database specific IDE。

 and this particular one is D Beaavver。You don't need to understand how to operate D Beaaver。

 I'm just using it so that I can access this ERD here。So as we look at this ERD。

 we can see that there are six tables in this database。 The main table is this transaction table。

Connected to this transactions table directly is the sites table。

 the customer table and the products table， and then the products table is connected to the categories table。

 which is connected to the parent table。

![](img/462042c07d7e681b448ad767da12d165_2.png)

![](img/462042c07d7e681b448ad767da12d165_3.png)

Now， if you want to better understand a connection in an ERD。

 then you can click on the line that connects it。 And this particular line here shows that the transactions table can be connected to the products table。

By the product I column in the transactions table， as well as the product I column in the products table。

And then these different dots here indicate that there's one particular product ID that is connected with each row of the transactions table。

 but many rows in the transactions table that could be connected to any particular row in the products table。



![](img/462042c07d7e681b448ad767da12d165_5.png)

And then at the top of each of these tables， you can see what is known as the primary key and it's emboldened。

 and that's basically the column that uniquely identifies each row in the table。



![](img/462042c07d7e681b448ad767da12d165_7.png)

And then below that are the other column names。 One of the benefits of storing data in a database like this is that it can reduce the size of the data that is stored。

 So this particular file is less than half as big as the CSV file。 Now。

 there's two other things before we actually get to the SQL queries。

 The first thing is just to provide you a basic overview of what SQL queries look like and some things to keep in mind。

 some key concepts。So the first key concept is that there are simple key words that are used to perform SQL queries。

 And these words are words like select from limit where and or as and many more。

 So they're very easy to understand。 The second key concept is that SQL is not case sensitive like Python。

So it doesn't matter if you spell a column or a table name using all uppercase。

 a lowercase or a mixture。 However， by convention， the SQL commands are capitalized to help distinguish between what is a sQL command and what is a portion of a table。

The third key concept to keep in mind is that the SQL query language does include some special characters like asterisks。

 percentage signs and quotation marks。 So you will see some of those used throughout The fourth key concept is that oftentimes SQL queries are divided on multiple rows to make them easier to read。

 They don't have to be， but that's just something that is often done to make them easier to read。

 The fifth key concept is that SQL queries end with a semicolon。

 And that's useful so that you can divide up SQL queries onto multiple lines。

 And then the last key concept is to pay attention to details。

 Sometimes it'll be the smallest thing that'll lead to an error。 So， for instance。

 if you're missing a comma。 or if you're missing a space。

 or if your commands are not in the right order。 All of that can lead to errors in your SQL query。

All right， let's demonstrate how to interact with the techca database。

 And I'm going to demonstrate this in a shell environment。 Now。

 a shell environment is a very simple text environment that allows you to interact with your computer's operating system。

And typically， on a Windows machine， you can do this using the command prompt application。

 If you're on a Mac， you would use the terminal。So we can access either shell within Jupyter Lab by going down to the other section and selecting terminal here。

If I click on that， it opens its terminal window。 Now I'm going to use a few very simple commands。

 So the first command I'm going to use is the C D command， which allows me to change directories。

 And then I'm recording the full path to where the techca database is located on my machine。 Okay。

 now that I'm in here。 I can list the files by typing L S and hitting enter。

 And this allows me to see all the files It lists the files。

 And I just want to make sure that I'm in the same folder or directory where my techka dot D B file is。

 That's the SQLite techca database file。

![](img/462042c07d7e681b448ad767da12d165_9.png)

![](img/462042c07d7e681b448ad767da12d165_10.png)

![](img/462042c07d7e681b448ad767da12d165_11.png)

![](img/462042c07d7e681b448ad767da12d165_12.png)

All right。 Now I need to connect to my techca database。 So to do that。

 I'm going to type out sQLite 3 and then the name of the database。 So tech a dot D B。

 And I misspelled that。 So sQLite 3。T it about Db， okay。Now。

 you can tell I'm connected because it tells me what version I'm using and。

I've got the sQLite prompt tray here。 Now， a note here。

 If you're trying to follow along on a Windows operating system and it's not working for you。

 that's most likely because SQL light is not in your path environmentviron variable。

 And that's something that we can talk about in a different video。 But at this point。

 it's not critical。 I just want to demonstrate the simplicity of the sQLite command。Okay。

 so now that we're in this database， there is a command that I can use within the terminal here。

 and that's dot tables that allows me to see the six different tables in here。

 so you can see these table names， categories， parents， sites， customers， products， transactions。



![](img/462042c07d7e681b448ad767da12d165_14.png)

![](img/462042c07d7e681b448ad767da12d165_15.png)

These are the same table names that are displayed in this ER R D that I showed you from D Beaavver。

 Now， another thing that's really useful is to look at the schema。

 So if I type out dot schema and hit enter， gives me a lot of information。

 And this is basically the SQL queries that I need to perform to recreate this database。

At least the database structure。

![](img/462042c07d7e681b448ad767da12d165_17.png)

So to create the parent table， I would use this SQL query right here and this tells me that I created the parent table and the columns are a parent ID integer。

 This is a primary key column， and then the parent name and it's a text value or a character string basically and it should not be null。



![](img/462042c07d7e681b448ad767da12d165_19.png)

Okay， so we can see that information for each of the tables here。

 It's a lot harder to process than an entity resource diagram， but it does provide that information。

 For instance， if we look at the next table categories， we've got the parent I D column。

 It's an integer type。

![](img/462042c07d7e681b448ad767da12d165_21.png)

![](img/462042c07d7e681b448ad767da12d165_22.png)

And it tells me that this is a foreign key， and it references。

The parent I D column of the parent table。 All right。

 so you can reconstruct the E RD from the schema， but it's a lot harder。 It's not as pretty。

 All right， one other thing that we need to do before performing the sQL command is change the mode。

To column。 And that's just going to make it prettier for when we perform the sQL queries。 All right。

 let's go ahead and type out the sQL queries。 Let's explore this sites table right here。 All right。

 so I'm going to start by just typing out a command that will return every row from that site table。

 So select star。 That means every column。

![](img/462042c07d7e681b448ad767da12d165_24.png)

From sites。 and then a semi colonlon。 So I don't have to capitalize select。

 but I'm doing that because that's a key word in SQL。 same with from。 But if I hit enter。

 it returns every single row from that table right there。

 So this allows me to see the different columns。

![](img/462042c07d7e681b448ad767da12d165_26.png)

And I finally get up to the top here， I can see each of the different columns。

And the information that's in there。 So rather than display every row。

 let's say I want to just look at the top five row。 So I can do that by adding on to it this limit。



![](img/462042c07d7e681b448ad767da12d165_28.png)

And then the number of rows I want to display。 So if I say limit 5。

 then it'll display just the first five rows。

![](img/462042c07d7e681b448ad767da12d165_30.png)

Now， you may have noticed that I didn't have to type out everything again。 If you hit the up button。

 you can cycle through the different queries or commands that you've used before。

 And that holds true for all of the terminal interactions。 Okay， so this is good。

 let's say I want to order these values by the values in the site I D call。 So if I。



![](img/462042c07d7e681b448ad767da12d165_32.png)

![](img/462042c07d7e681b448ad767da12d165_33.png)

Type out order by。And then sight I D。 I'm going to get an error， And it tells me where it's from。

 but it's important to recognize that it will tell you if something's wrong。

 And the problem is that I don't have that statement in the right order。

 So I need to move it up here and type out order by and then cite underscore I D。



![](img/462042c07d7e681b448ad767da12d165_35.png)

Okay， now you can see that it orders those first five rows by the site I D column。

 So order by is pretty simple to use to sort your data。 Okay。

 let's say that I want to filter the rows of data that are returned from my query。

 specifically from the sites table。 What if I only want rows where the status is closed。All right。

 so what I can do。Is go back to my initial one， select star from sites and just use this where command。

And I'll indicate the name of the calm site status。Equals in a quotation marks。Closed。

 then hit enter。And I misspelled sight status。Okay。

 so now you can see that what's returned is only those that are equal to close。

 So it's pretty intuitive to filter the data just by using that where command。

 So let's say that I want to use the where command to filter the data based on two conditions。Well。

 that's also pretty easy to do。 I'm going rather than look at site status equals closed。

 I'll say where latitude is greater than or equal to 40。And the latitude column。Is less than 41。Okay。

 so this returned those rows that equal those conditions。 So anyway。

 it's easy to add multiple conditions to filter the data by。

 So another thing that I can do is filter the rows of data based on a sub string。

 So let's say I want to look at the sites that are located on a street that has the word main in it。

 So I can do that by saying where。A dress is like。And then in quotation marks。

 I'm going to add a percent sign and then type out the substr that I want main and close it with percent and a quotation mark。

So now when I return that， you can see that all the observations have main somewhere in the address column。

 so at the conclusion of this lesson。

![](img/462042c07d7e681b448ad767da12d165_37.png)

I hope you have a better understanding of what the database environment is like and really the key thing is to get a feel for how easy it is to use the structured query language。

 It's really easy to understand。 and once you have the basics down。

 it's pretty easy to combine these basic commands to create more complex queries。

It's also worth noting that we had to connect to the database In later lessons。

 we'll talk more about how you can interact with SQL databases directly from a Python environment。

 rather than using the terminal or a database I D E like D Beaavver。



![](img/462042c07d7e681b448ad767da12d165_39.png)