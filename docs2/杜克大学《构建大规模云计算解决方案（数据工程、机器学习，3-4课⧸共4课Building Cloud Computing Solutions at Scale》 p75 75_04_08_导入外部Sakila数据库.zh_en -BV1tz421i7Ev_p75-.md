# 杜克大学《构建大规模云计算解决方案（数据工程、机器学习，3-4课⧸共4课Building Cloud Computing Solutions at Scale》 p75 75_04_08_导入外部Sakila数据库.zh_en -BV1tz421i7Ev_p75-

![](img/550d3476bf28fec61dfa15cb017617b0_0.png)

Yeah。Here we have the Sula sample database that you can get documentation from from Mysql。

 it's always good to have a reference database where you go through and make sure you understand what's happening with a particular type of database in this case there are instructions where you can get it right you can go to dev。

mysql。com doc index hyphen other。 HTMLl you can download it and this is going to contain a schema file。

 a data file and also a dot mwB If we go ahead and we take a look at how this works here is that the do MwB is for MysqL workbench which we don't need to worry about。

And to connect to it via the terminal， you would type in MySQL， log in， and then source the schema。

 the full path to it， then source the data file。 So let's go ahead and do that in a terminal here。

 So we'll go ahead and first look at these files here if we say， you know D S H star。



![](img/550d3476bf28fec61dfa15cb017617b0_2.png)

This will show us that， in fact， the data file is pretty big and the schema file is much smaller。

 Now， we could also do for let's say， tail on the data file just to get a little bit of a view。 Okay。

 here we go。 we see there's some data inside of here。

And this just gives us a feel for what we're working with。 Now。

 the next thing that we'll do we'll type in my SQL dash U root， and we'll do dash P。

We'll type in our password。And then from here， this is where we would want to actually do that source command。

 So since it's a little bit of a long path， I'm going to go ahead and just past this in so I don't make a typo and we'll go ahead and piece this in。

 So first up we'll source the schema。There we go， and this will take a little bit of time right to build this out perfect。

And then next， what I'm going to do is I'm going to source the data。Perfect。Aice piece us in。Great。

 so now that we've got that， the next thing that we would want to do is actually go back to the documentation real quick and see what they say。

 So it says use。

![](img/550d3476bf28fec61dfa15cb017617b0_4.png)

Sacula， so let's go ahead and do that and then say show。



![](img/550d3476bf28fec61dfa15cb017617b0_6.png)

Full table。 so we'll go ahead and say use。Go back here。Peace in here。😔。

And we can see database changed， and then we can do the next command here。 Show full tables。 right。

 So this is always a good idea to， to look at the documentation for the reference database。

 And here we， here we see exactly what's going on。 We've got the actor。 We've got films。



![](img/550d3476bf28fec61dfa15cb017617b0_8.png)

![](img/550d3476bf28fec61dfa15cb017617b0_9.png)

We got the language， the category， etc ce。 and even further one of the nice things about the documentation is if you go to structure here。

 we can look at the table and you can actually break down each of these as well， for example。

 if I want to look what's inside of the actor table。

 I can see the columns and then as well we can look at the a map of the schema as well。

 So this is something that a database architect would do if you're a database engineer or a data engineer。

 this would be something that you would want to potentially spend some time on first before you start building out a structured database。



![](img/550d3476bf28fec61dfa15cb017617b0_11.png)

![](img/550d3476bf28fec61dfa15cb017617b0_12.png)

You need to figure out who's going to connect to what portion of the database and how you're going to create queries。

 And so this is where some experience about building a database comes into play。

 So now that we see that， the next thing we can do is play around a little bit with this so。

We can actually say， for example， describe the actor so we can say describe actor。

And this will show us the information about that particular table。

 This is typically a first step that you would do if you're going to query a particular part of the database where you would do it describe once you've got what that table has got inside of it。

 then you can actually do a little bit more so we could do is we could say， well， yeah。

 let's do a select star and then we'll say from and then we'll say actor and we'll say limit。5。

 so the idea here is that。When we want to do a select。

 we don't know yet how much we want or exactly what we're going to query。 So we'll put this limit。

 so we only get five and we can see here that we've got these five rows。

 Now we can change the limit as well。 we can do， let's say。

 20 and we can get a lot more actors from that particular table Now we could also practice a join here so this will take a little bit of time to type。

 So what I'm going to do is just paste this in and we can actually join the title， the rental rate。

 maybe the first name， the last name and actually put some other parameters in there as well。

 So let's go ahead and paste this in。So you can see here select title rental rate， first name。

 last name， and then we're going to join film actor。

And we're going to put this all together to create a more sophisticated set of information。

 In this case， we can see the title， we can see the rental rate。

 and we can see the first name and last name。 So we're basically grouping all this together because maybe we want to create a dashboard or something like that。

 Now， there's other things that we can do as well inside of here and a good one would be maybe looking at the number of things that are available。

 So one of the ways that you could do this is you could do a count。And you could say。

 from a particular table， let's say you're just exploring the database。

 I want to count how many films are inside of this particular database and we can see that theres a thousand and you could also then do a simpler join to get a little bit more information about that particular table and so one of the things that we could do is actually put in a little bit of a more simple join here and we can say select the title。

And the last name， and then we're going to join with the language ID here。

 let's go ahead and do that， and we can see from that query。

The the name of the film and actually what language it actually represents。

 So there are some nice things you can do as you start to interrogate this database。 And again。

 if you want to find a little bit more information about it， you can always go back to the diagram。

 look at some of the different things that you could query。



![](img/550d3476bf28fec61dfa15cb017617b0_14.png)

This is a really good way to。Enhance your skills because there's documentation about this sample database versus some random database you don't know necessarily everything that's going on。

 this is a great way to really dive into some of the details of a default database because we have such exhaustive documentation。



![](img/550d3476bf28fec61dfa15cb017617b0_16.png)