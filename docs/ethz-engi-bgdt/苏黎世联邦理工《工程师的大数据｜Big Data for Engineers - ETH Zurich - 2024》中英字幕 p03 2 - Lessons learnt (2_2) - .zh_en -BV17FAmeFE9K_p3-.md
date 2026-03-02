# 苏黎世联邦理工《工程师的大数据｜Big Data for Engineers - ETH Zurich - 2024》中英字幕 p03 2 - Lessons learnt (2_2) - .zh_en -BV17FAmeFE9K_p3-

Welcome everybody in the lecture hall， welcome everybody on Zoom， welcome everybody from the future。

 so today we are going to brush up on SQL what we started last week and then we will continue with the cloud storage and I'd show you how we can store in the cloud very large quantities of data。

Before we start， I have a question， I'd like to revisit a bit what we did the week before to check that you understood everything。

And so to wake you up because it's quite early。So do you remember the shapes of data that I told you about。

 one of these is not the fundamental shape of data， is it the cube， the table。

 the tree of the circle？Alright， so let's see。What you voted。 and yes， the majority says the suck。

 indeed， I didn't say anything about soccerers so。We have the cubes， the tables， the trees。

 and the other two。Gras， and。Unstructial text， chat GPT。All right， so。This is what I wanted to。

 to check with you。 And， of course， in this in this。Whether I'm finishing today。

 we were talking about tables， because this is how it all started in the 1970s， right。

 because tables。Everybody understands them。So， let me come back。



![](img/9cb4f4505bef2ded2bc6961612046067_1.png)

Very well。ok。So there is this language SQL。 In fact， this is the focus of this app。

 you really have to make sure if you already know SQL， then that's good you can brush up。

 if you do not know SQL， you really have to learn it。

 they will be exercises this week release to you plenty of them it's practical exercises you can really interactively type in the notebook a SQL query and then you see the results coming out it's a great language。

 very popular， very easy to learn， I mean， even business people use SQL。

 some business people use SQL So you don't need a technical backgrounds to understand to understand the language。

 So on this slide， this is a summary of the order of the clauses in the SQL language So select from where group by having order by limit of set it's always in that order but the optional So you might not have all of them。

 but the order is important。 select C contents on that's basically the columns of the output that you put in there from that's the name of the table that you read。

Your data from。 So here persons。 Then you have where that filters the rules。

 So it only keeps the records or the business objects or the role satisfying the condition。

 his residence first。Then you have group by that's for aggregation is going to put the record in group and then within which each group is going to count some aggregate average and so on。

 So here we group by city。 so we are going to have one group for every city and all the records for the same city are together。

Then we only keep the groups for which the total count is less than 100000 or equal。

 And then we order all of the all of these groups by population descending。

 So the highest population first and then lower。 and then limit 10 offset set is for pagination。

 pagination is really imagine that you use a search engine over the Internet like Google。

 it will show you the first 10 results。 and then the next 10 and then the next 10 and then the next 10。

 this is what limit 10 of set are for， right So your first page is going to have limit 10 offset set 0 because it's the beginning。

 the second page will have limit 10 offset set 10， because you want to shift to the next 10 and so on。

 right， So again， imagine a search engine paginating the results for limit 10 offset。 Okay。

 so these other clause。 In fact， there are a few more things that you can do with SQL。

 If you have this set from where statements， you can take two of them。



![](img/9cb4f4505bef2ded2bc6961612046067_3.png)

Like select bla， blah blah。 and select blah， blah， blah and put a union in the middle。

 What that's going to do is take the， the output of the first select。

 the output of the second select and union them into a table， right。

 So it's just concatetnating the data sets as in here， right。呃。



![](img/9cb4f4505bef2ded2bc6961612046067_5.png)

You also have intersection， subtractions， all the mathematic on sets。That exists。

Something else you can do is called the joints。A join is when you have two tables that have different data。

 but somehow they are connected。For example， you might have a table of students。

And you might have a table of courses， and you want to join the students with the courses that they are actually visiting。

 This is called joining。 Join means that you take a record and match it to a record on the other side that that that that they relate to。

 right， So it's not like you match all records on the left with all records on the right。

 An example is that if you take。😊，For example， what example do I have here。

 So if you join the last name of the captains or Kirk Ker and Genway and you join it on the captain name of the spaceship。

 So you have the people on the left and the spaceships on the right。

 Kirk is going to go with Kirk and Kirk。 So you see。



![](img/9cb4f4505bef2ded2bc6961612046067_7.png)

Right here， you're going to have that record right here。 James Kirk。

 which is going to be matched with this one and this one。 So this is the the two that you get here。

 that comes from here and that comes from there。

![](img/9cb4f4505bef2ded2bc6961612046067_9.png)

![](img/9cb4f4505bef2ded2bc6961612046067_10.png)

And Jane Way is going to be matched with this one。 That's the third match you have here。

 The ones marked in red。 They don't have a match because the valley crusher is not a captain。 And。

 and Piar here of the enterprise B is not in the in the list of the people on the left。

 So in that case， they are not in the outputs。 or whom does that make sense。



![](img/9cb4f4505bef2ded2bc6961612046067_12.png)

All right。Now， since I'm on the join， I'm going to say。

The very high level view on normal forms that I scared you with last week。 and then I told you。

 don't worry because we throw them anyway anyway away。But， in fact。Very， very。



![](img/9cb4f4505bef2ded2bc6961612046067_14.png)

Oversimplifying things， what a normal form means is that this here at least in the 70s should be avoided because that's way too big。

 there's too much information in them。

![](img/9cb4f4505bef2ded2bc6961612046067_16.png)

![](img/9cb4f4505bef2ded2bc6961612046067_17.png)

And a normal form means instead， we split it into several tables。

 This is what the normal form essentially means。 High normal form， right。

 High normal forms mean you have one table per。Stuff you're talking about high normal form means you have one table for people。

 one table for courseies， one table for spaceships and so on， this is high normal forms， right？

Low normal forms。 So if you drop the normal forms。 it means that instead of having all of these tables separately。

 you join them back into a very， very， very large table。

 This is what it it means to drop the normal forms。 So throw them away。

 you just put it back into a single giant table。 Now， in the 70s。

 that was consider very bad practice。 you should not do that。

 The good practice is to have plenty of small table that each do one thing and they do it right。

 because if you are in a low normal form。😊。

![](img/9cb4f4505bef2ded2bc6961612046067_19.png)

![](img/9cb4f4505bef2ded2bc6961612046067_20.png)

![](img/9cb4f4505bef2ded2bc6961612046067_21.png)

And have this giant table that tries to do everything。

 A lot of problems are going to to arise because you have a website， the tables evolve。

 they are alive and so on。 You're going run into duplicate issue inconsistency issues And so what I told you last time when we drop the normal form it means that when we do big data analytics。

 we actually love this。 We love this because the problems that people have when when they write a lot to the tables in big data。

 we don't care， because in big data， we are not going to modify the data or update the data we are just reading it。

 we don't load the data sets from the internet， and then we read it and that's it。

 So this is why in big data， we don't mind having data sets like this that are not normalized and that's totally fine。

 Now， why am I telling you about normal forms on a slide that is about join because that's related。



![](img/9cb4f4505bef2ded2bc6961612046067_23.png)

A normal form is basically the opposite of joining， right？

Dropping the normal forms can be seen as joining into a big table and going into higher normal forms means unjoining。

 so splitting the table right so this is how it relates you join。Or you unjoin your speed。

You deormalize or you normalize。 That is how joins and normalization relateates。 And again。

 we love that in the 70s when you modify your data a lot。In big data。

 we are going to work a lot with that kind of data sets that has everything together， okay。



![](img/9cb4f4505bef2ded2bc6961612046067_25.png)

So that's about joints and normal forms。 Now， just so you know。

 if you do not want these red cells over there to be thrown away because they don't have any matches。

 you can still include them。 All you need to add is this outer joint， full outer join。

 then you will have them in the results。 But of course， since they don't have any match。

 there's going to be a lot of a lot of what we call nerves in there。

 So we do have the valley crusher in the output。 But since we don't have any values there。

 we fill them with nerves。 Ns is kind of whatever we put when we don't know the value。

 it's a special value in tables。 The same goes for this spaceship with peak art。

 We don't have any image over there。 So we feel with nerves。 So again。

 if you don't say full outer join， but just join you throw away those that don't have any match。

 if you do for the full outer join， you keep them。 But then you're gonna be feeding the rest of the columns with nerves。

 for whom does that make sense。

![](img/9cb4f4505bef2ded2bc6961612046067_27.png)

![](img/9cb4f4505bef2ded2bc6961612046067_28.png)

![](img/9cb4f4505bef2ded2bc6961612046067_29.png)

![](img/9cb4f4505bef2ded2bc6961612046067_30.png)

![](img/9cb4f4505bef2ded2bc6961612046067_31.png)

![](img/9cb4f4505bef2ded2bc6961612046067_32.png)

![](img/9cb4f4505bef2ded2bc6961612046067_33.png)

对。😊，Now， there is also the notion of natural join。

![](img/9cb4f4505bef2ded2bc6961612046067_35.png)

A natural join is just the same， but that's the case where the names of the columns are the same。

 you see， last name， last name。

![](img/9cb4f4505bef2ded2bc6961612046067_37.png)

When that happens， you just say natural join and that it。

 You see here it was not the same last name Captain name。

 So you need to explicitly say that you are matching the records based on that。

 But in a natural join， you just rely on the names and say whatever current are the same。

 you use that as the as the matching criterion。 That's called the natural join， right。😊。



![](img/9cb4f4505bef2ded2bc6961612046067_39.png)

![](img/9cb4f4505bef2ded2bc6961612046067_40.png)

![](img/9cb4f4505bef2ded2bc6961612046067_41.png)

And finally， when you use SQL， you can actually。😊，W a select statement。

 a select from where statement inside another select select from where statement inside another select from where statement。

 it's like the inception movie all over again right in the same way that you can have a table in a table in a table in a table when you are not in the first normal form。

You can have a query in a query in a query in a query， right And that's very common to do。

 You will see the exercises if you try， but but this this actually makes。



![](img/9cb4f4505bef2ded2bc6961612046067_43.png)

A lot of sense， right。

![](img/9cb4f4505bef2ded2bc6961612046067_45.png)

The one thing I recommend you at that point is just if you're not familiar with SQL。

 just sort the exercises， get as much practice as you want with the exercises。

If you have trouble learning， I realize that chat GT is really good at explaining SQL so if you you can literally take the questions of the exam and the schemas and drop them into chat GPT and saying like this is my query or this is what I want to do。

 Please give me the query it will even explain you need to be very careful Can how you seen it it can make mistakes。

 but I think that for learning it can be a good help and of course we are also here and the T AT。

I haven't tried EL with with SQL。 It might be that Ather is also capable of doing that。 In fact。

 if you try it and have feedback， we we would be very happy to hear it。😊，Alright， so again。

 nothing replaces doing it。So practicing， practicing， practicing。

 practicing as many queries as you can in order to understand what is going。



![](img/9cb4f4505bef2ded2bc6961612046067_47.png)

Okay。😊，No。You don't have to worry too much for that course， but just so you know。

 there is math behind SQLs。 So when you write a which query like this。



![](img/9cb4f4505bef2ded2bc6961612046067_49.png)

A lot of things are happening behind the scenes that you don't see。 And， in fact。

 what's happening is that the query engine with stuff replacing everything with Greek letters all over other the place。

 sigma for the selection， gamma for grouping pi for selection projection。

 sorry for the select keyword。😊。

![](img/9cb4f4505bef2ded2bc6961612046067_51.png)

嗯。And this is actually math， it's called the radiational algebra。

 you can actually convert a query to a complicated mathematical formula that is just a sequence of operations that you apply to the data。

 Why is it doing that Because the math can be rewritten。

You can actually change it to equivalent formulas， but in such a way that it's faster to compute and so this is the power of having a language like this that is declarative is that inside the engine is going to do the math and optimize this whole set of formulas to make it as fast as possible。



![](img/9cb4f4505bef2ded2bc6961612046067_53.png)

![](img/9cb4f4505bef2ded2bc6961612046067_54.png)

![](img/9cb4f4505bef2ded2bc6961612046067_55.png)

对。A few more things that are good to know is that logic in SQL shouldn't be an S there logic in SQL is three valued who heard of logic true force or not end。

Some of you。 So this is， you know， in computer， there are zeros and one。

 So everything is based on zeros and ones， true and false， but usually it's only two values right。

 either it's true or it false。 But in SQL， it has to do with this neuralll that I told you about。

 Sometimes users just don't know。And when you don't know it's just the third value。

 so something can be true， something can be false or you don't know if it's true or false。

 and then you have or and end and not that work in the same way so again just so you know。



![](img/9cb4f4505bef2ded2bc6961612046067_57.png)

Let me drop you two abbreviations so that you're aware of that。In a language they sQL。

We differentiate between two parts of the language。There is a data definition language。

That is used to build new tables。So you create a table that has this and that and this and that columns with this and that type。

 right， So you create the schema of your table。You can change the schema by renaming columns by dropping columns and so on。

 that's called the data definition language DDL。Or you can manipulate data select from where that's the MLL that's called data manipulation language。

 right so DDL is for the schema of your table， the skeleton of your table， What columns do you want。

 What types do you want and so on。Data man language is about manipulating the contents of the table right so it's the the select fromware statements or even inserting and removing rules。

 which I didn't show you， but there are also comments to do that。

 but for the exam we don't care for the exam we just query。

 So this is why I didn't bother you with inserting and removing or creating schemas。



![](img/9cb4f4505bef2ded2bc6961612046067_59.png)

All right。Something else that is good to know。 but we'll come back to that in a few weeks。

 So so that that's okay if， if if you only get it on a high level。

 it's the concept of index or the poor form is indices。😊。

It's actually very easy to explain already saw at the end of a book。

 an alphabetical list of words and the pages on which you find them。😊，many of you。

 that's called an index， thats is。 So we have the same thing in databases。

 We also build structures like this。😊，If you look at that at the end of the book。

 what's the goal is to very quickly find where some words are located。

 An index in the database is the same thing。 You build something。

 It's just like an alphabet equal list of words。 And then you can very。

 very quickly locator records among billions of records。 but very quickly。 Okay。

 so just have the in mind the end of the book with the alphabet equal list of of words。

 That's an index， makes things faster。 We'll come back to it。😊。



![](img/9cb4f4505bef2ded2bc6961612046067_61.png)

嗯。Now this here is related to what I told you about throwing away the normal forms and I told you that in the context of do you read the data or do you modify the data and this is all based of the real life。

 what do you do in real life in real life there are times where you modify the data a lot that's the case of the web like diggiitech galaxies whenever they are setting something the database gets updated So with millions of customer on the website。

 it's very right intensive the data keeps being modified。

 modified modified that's called OLTP right online transaction processing This is when you want the normal forms。



![](img/9cb4f4505bef2ded2bc6961612046067_63.png)

![](img/9cb4f4505bef2ded2bc6961612046067_64.png)

![](img/9cb4f4505bef2ded2bc6961612046067_65.png)

![](img/9cb4f4505bef2ded2bc6961612046067_66.png)

![](img/9cb4f4505bef2ded2bc6961612046067_67.png)

![](img/9cb4f4505bef2ded2bc6961612046067_68.png)

You don't want two big tables。 You want smaller tables。 You want to unjoin the tables。

 split them and be in high normal form right， and the SQL query will use joins but on an as needed basis。

 right， but the tables are split。 So here is's in high normal form。



![](img/9cb4f4505bef2ded2bc6961612046067_70.png)

![](img/9cb4f4505bef2ded2bc6961612046067_71.png)

But in our case， big data we love to read data without actually modifying it that's called OLAP online analytical processing read intensive in that case we drop the normal forms we don't care about them so we love to have big tables in fact there is a technology called big table that we' see in a few weeks so we drop the normal forms we don't care about them and we just read the data in that seat right so that's OAP OLTP that's a lot of abbreviations right DDl。

 Dl， LTP orL and so on but it's good to know because then you understand when people talk about them。

😊。

![](img/9cb4f4505bef2ded2bc6961612046067_73.png)

![](img/9cb4f4505bef2ded2bc6961612046067_74.png)

![](img/9cb4f4505bef2ded2bc6961612046067_75.png)

Next， a concept that he also taught in relational database systems in the bachelor's is the transactions。

There is a word ACID ACID is just a way on Izos Bo。

 I think it's called in German to remember what it means ACID atomicD consistency isolation durability。

These are all the good things that you get out of of the database management system like Postgrith QL or or Ral。

 IBM， Microsoft SQL server。😊。

![](img/9cb4f4505bef2ded2bc6961612046067_77.png)

It's actually very convenient。 So let me tell you what they mean just so that you you know。

Atomomicity means。That you might want to execute multiple queries。

But you either want all of them to succeed or all of them to fail and not be applied。

 You don't want some of them to succeed and some of them to fail。

Here there is also a very very good example right Imagine that you go to websites to book your train and there is a query that books the amount on your credit card but then the query that actually books your seat in the train fails you're not going to be very happy right what you want is that either your credit card is booked de booked booked Yeah your credit card is debited sorry and you get a seat in the train or your credit card is not booked and you do not get a seat in the train that is that toy C。

😊。

![](img/9cb4f4505bef2ded2bc6961612046067_79.png)

Then we have consistency， it means that the database is always in a consistent state in the case of the train。

 it means that you don't have two people on the same seat， right that would be consistency。😊。

During a transaction， it might be that it's temporarily inconsistent， but at the end。

 it must be consistent。 You don't want two people on the same seat in the train。 Now。

 I don't know its that's a good example because in reality companies do of our book and that can happen。

 but normally that basis you can you can prevent that。



![](img/9cb4f4505bef2ded2bc6961612046067_81.png)

嗯。Now， isolation， isolation means。If you are on the。

 I don't know on the digititech shop and you want to order something。嗯。When you are on the website。

 it should feel to you like you're the only person in the world placing an order with them。

That's called isolation there are millions of people at the same time reading the database you should not notice that's called isolation and the database management systems。

 they are good at making you feel unique that you're the only user using the system。

How otherwise would you know where if it's in the middle of a transaction。

 you start seeing data that is modified， but it wasn't you。

 and then it doesn't feel isolated because you see the effect of other people， right？

But a good system， while you are doing your transaction should isolate you from the rest and make you feel like you're the only person using the system。

 That's a user experience。

![](img/9cb4f4505bef2ded2bc6961612046067_83.png)

Big。And finally durability is once you have booked the city in the train。

 you don't want this to disappear right and then arrive on the there where you deb and then the city is not booked。

 this is called durability right even if the computers are shut down or whatever the update must stay forever in the system。

 this is durability。So this is AC IDD， we can spend actually four or five hours teaching this in bachelor lectures。

 that's just the overview but there's plenty of math behind that in order to actually make it happen。

 but just now you know right if you hear AC in the context of databases now you know that this is what it means。

So that's the end of the wrappper and in fact， the next steps are actually pretty easy because what I told you about is the good old database of the 1970s。

 SQL， relational tables and so on。😊，So what's going to happen now。

Is we are going to look at what happens if we have systems that have。Lots of row。

 what if we have billions， trillions， qua billions of row。

 then a relational database system doesn't work anymore。 so what happens if we have lots of rules。Or。

What happens。If we have lots of columns。If my laptop would be so kind as to display the next slide。

Please。😊，Yeah， thank you。 So you can have lots of columns。 So lots of columns。

 typically a relational database management system supports up to 256 columns That's already a lot of columns。

256， right。😊，But what happens if you want even more columns than that and your table is very spars。

 meaning that some columns are used on some rows， but some not on some others。

 we will see systems that are able to do that right that's the one called big table， In fact。

 it can have even millions of columns if you want it's very spars of course。

 but it can do it and finally lots of nesting。 This is when you break even the first normal form。



![](img/9cb4f4505bef2ded2bc6961612046067_85.png)

And you have a table in a table， in a table in a table， in a table。 So that's called nesting。

 you nest a table in a table。 And that also we will see， In fact。

 what we will see is that when you start doing that， this is no longer a table。

 it's a collection of trees。 So this is why we are going to see a lot of trees in that lecture。😊。



![](img/9cb4f4505bef2ded2bc6961612046067_87.png)

And now if you actually map what's going to happen。

 then pretty much everything we are going to do in the semester either has to do with a lot of rules。

 a lot of columns or a lot of nesting。That's it。 Do you have any questions on that stuff spot。

 and move over to the next one。Who understood kind of。Okay， who。

 for whom was it just walking the park because you already knew it？

Some of you for who was it totally new。who is lost10 scales？Okay， nobody。

 so again I have only one piece of advice do the exercises and write as much SQL as you can write this is the this is the thing we are going to use SQL again later in the course and it's really really worth learning learning SQL。

😊，Okay， so if if。If you don't have any questions， then I will close here that special section again。

 this is an unusual section because that one was just。

 I basically threw at you 14 weeks worth of material of information systems for engineers。

now we are moving to more this one is a question Yes。

 and so it said the chapter 3 was updated in October， but on the website。

 the last version is from June。 So is there a newer version of the book。 Oh。

 it was in October for the because I added the dynamo DB。 I should。 Oh。

 I forgot to write that dynamo D B。 So the part on Q you start is specific to the master's course for big data。

 but we don't have it in the lecture。 I I will add to the modelle。

 So this update that you mentioned in October is something that is unrelated to that course。



![](img/9cb4f4505bef2ded2bc6961612046067_89.png)

![](img/9cb4f4505bef2ded2bc6961612046067_90.png)

![](img/9cb4f4505bef2ded2bc6961612046067_91.png)

![](img/9cb4f4505bef2ded2bc6961612046067_92.png)

![](img/9cb4f4505bef2ded2bc6961612046067_93.png)

I will tell you exactly I will modify the modelles it's the second half of the chapter basically that is not part of the material for that course right If you read it then that's good I mean it's interesting but through that I should have mentioned it so the book that you see on research gate is the latest version the PDF right and if you find mistakes let me know I will upload a new version every time you always see the date on the first page at which it was it was published right。



![](img/9cb4f4505bef2ded2bc6961612046067_95.png)

![](img/9cb4f4505bef2ded2bc6961612046067_96.png)

![](img/9cb4f4505bef2ded2bc6961612046067_97.png)

![](img/9cb4f4505bef2ded2bc6961612046067_98.png)

Okay， so thank you for， thank you for asking。Okay。By the way， the PDF always have the latest version。

 the printed copy I put it there because some people like it in written。

 but this one will not be updated as frequently right like once a year or something。

 so it's really the online PDF that is the important one。



![](img/9cb4f4505bef2ded2bc6961612046067_100.png)

![](img/9cb4f4505bef2ded2bc6961612046067_101.png)

![](img/9cb4f4505bef2ded2bc6961612046067_102.png)

![](img/9cb4f4505bef2ded2bc6961612046067_103.png)

All right， so let me stop the recording。