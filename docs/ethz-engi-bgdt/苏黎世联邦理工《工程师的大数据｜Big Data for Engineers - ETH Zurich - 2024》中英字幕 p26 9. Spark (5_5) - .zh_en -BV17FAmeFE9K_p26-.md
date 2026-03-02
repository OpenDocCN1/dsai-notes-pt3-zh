# 苏黎世联邦理工《工程师的大数据｜Big Data for Engineers - ETH Zurich - 2024》中英字幕 p26 9. Spark (5_5) - .zh_en -BV17FAmeFE9K_p26-

Welcome back， everybody， I hope you had a good break。So I'm going to finish this part of the lecture。

 I only have a few slides left， at least you can see it in the lecture hall 51， we are already at 46。



![](img/0ccf873205d186dd77168d711d25a22a_1.png)

![](img/0ccf873205d186dd77168d711d25a22a_2.png)

So if I summarize， what happened is that we had a system with RDDs and a Python API with transformations on these RDDs。

We saw that it's quite cool， right， It's more generic than map reduce。

 You can have more generic patterns in the data flow。😊。

But we also saw that the code can quickly become complex when you pilot lines of Python that chain the transformations well after the other and then writing all of these Lambbada。

 Lada Lada every time with Python code that navigates JO objects and so on can become cumbersome after a while。

We solved that and at the same time made it faster and more efficient by noticing that there is a use case in which the data in the RMDs are basically JSON objects and these JSON objects are even varied against the same schema we learned a few weeks ago that JSO objects valid against the same schema can be organized in a data frame if the schema is not too exotic。

😊，And data frames give us two things first they take less space on disk， for example。

 if you store it in packet， but they also take less space in memory because you can organize the storage in a column fashion so they are extremely efficient and second data frames are extraordinarily intuitive。

 they are just a generalization of relational tables。

 but unlike tables they can be nested the maindi with tables and who says tables says SQL now you have these high level language。

That is functional in declarative that you can use and write simple queries like select from where groupby having order by limit of set。

 and now you know that the groupai and the order by are going to cause the shuffling in the inoc cluster。

😊，All right， so far so good。 So now I sold you this and maybe if it were for sale。

 you would buy the product where technically it's not it free， but maybe I convinced you。

 but now I want to destroy what I've just been doing by showing you the limits of that。

 So whenever you see that something solves the problem。😊。

It's always interesting to see up to which point it solves the problem When do you hit the limit and when does it stop working。

 It's the same thing when you， when you do or when you later will do some research， for example。

 in systems， that you try to build something， It solves the problem。

But whenever you try to advertise or publish what you've done。People will ask， what are the limits。

How far can you scale it， when does it start becoming slower。

 Where does it start to be less easy to use and swap。

 So I'm going to do this now with SpSQL and show you that it works great in all of these cases。

 actually in 80% of the cases， but in some cases it becomes cumbersome。😊。

So the first thing is that you know that the data frame。😊，Can be nested。So in a data frame。

 you can have a array of strings， for example。 So in that case， I didn't draw it as a data frame。

 I could have drawn it as a data frame actually just would have taken less space。

 but these countries here， the third column on the on the top left， the third column。😊。



![](img/0ccf873205d186dd77168d711d25a22a_4.png)

Is not forgotten。Here， it's not just an atomic value， it's actually an array of streaks。



![](img/0ccf873205d186dd77168d711d25a22a_6.png)

It wouldn't be a radiational table anymore because it has to be flat。

 but it's a data frame right This would be a collection of four valid JSON objects。 This is a string。

 this is a string and this is an array of strings， right。😊，Now we can query it with SQL。

 but the thing is SQL wasn't made or nested data， so in languages like Sp SQL。

 what was done is that they extended the language in order to deal with a arrays and with objects right so it's an extension of SQL that allows you to deal with that。

😊。

![](img/0ccf873205d186dd77168d711d25a22a_8.png)

And in that case， one of the extensions that they added to the language that didn't exist， I mean。

 you would not find it in CosgsQn。😮。

![](img/0ccf873205d186dd77168d711d25a22a_10.png)

Is the explode function， right， The explode function can be called on such a column that is an array of strings。



![](img/0ccf873205d186dd77168d711d25a22a_12.png)

And it's going to open the array and separate all of the items in there， all of the elements。

 in that case， one， two， three，4， five，6， then two， then three， then two。😊。



![](img/0ccf873205d186dd77168d711d25a22a_14.png)

What it does。Is that it's going to now display them as strings。 But one on every row， you see D， I。

 C， H， A， B， E， D， I， C， H， A， B。 Now it's one on every row。



![](img/0ccf873205d186dd77168d711d25a22a_16.png)

Right。But what happens with the other columns right because here we had Albert Einstein that was for all the six of them that's not a problem if you use the explode it's deuplicating the other columns right now you had Einstein Einstein Einstein Einstein but for every single one of the video then you have Ramanujan here with two of the videos then good three times and Miyaza cani two types right so this is what explode does who has an intuition now of explode if you call it on an array awesome。

😊。

![](img/0ccf873205d186dd77168d711d25a22a_18.png)

![](img/0ccf873205d186dd77168d711d25a22a_19.png)

So it looks simple， right， it does a simple thing。😊，嗯。So。No。

There is something a bit fancier that is equivalent。To express it to be more generic。

 That's called the lateral view。And a lateral view is when I start getting headaches and maybe you will start getting headaches。

 too， but technically。

![](img/0ccf873205d186dd77168d711d25a22a_21.png)

What it means is that you know that in from you can join tables， right。

 you can say from this table joint with that table right， who remembers joins？



![](img/0ccf873205d186dd77168d711d25a22a_23.png)

![](img/0ccf873205d186dd77168d711d25a22a_24.png)

Right， take two tables and you mix them into one table。



![](img/0ccf873205d186dd77168d711d25a22a_26.png)

What a lateral view is doing？

![](img/0ccf873205d186dd77168d711d25a22a_28.png)

Is that it's pretending that this is a separate table。 It's technically a column in the table。

 but it's pretending that it's like another table。 So it's as if you would join this and that。



![](img/0ccf873205d186dd77168d711d25a22a_30.png)

![](img/0ccf873205d186dd77168d711d25a22a_31.png)

And technically， if you imagine that other table join with that one。😊。



![](img/0ccf873205d186dd77168d711d25a22a_33.png)

This is， in fact， what you get。Because in your join。

 the Einstein would be matched to six records in this virtual table that doesn't really exist。



![](img/0ccf873205d186dd77168d711d25a22a_35.png)

![](img/0ccf873205d186dd77168d711d25a22a_36.png)

And you match it that way。 So the moment you look at this。

 what explode does as a sort of join against a table that doesn't exist， right。

 You just pretend that this is a table。 This is what you call a lateral view。

 A lateral view is really joining a table against some sort of abstraction of that part。😊。



![](img/0ccf873205d186dd77168d711d25a22a_38.png)

![](img/0ccf873205d186dd77168d711d25a22a_39.png)

![](img/0ccf873205d186dd77168d711d25a22a_40.png)

And then you say that in that virtual table， there is this column that you obtain from， from this。

 and and you， you were， you， you can even rename it like this。 Alright， so this is equivalent。

 Why am I telling you that。

![](img/0ccf873205d186dd77168d711d25a22a_42.png)

![](img/0ccf873205d186dd77168d711d25a22a_43.png)

Because the moment you have a lateral view， you know that when you have a join。

 you can do multiple joins， right， you can join with a third table with a fourth table and so you can do the same with lateral views。

 So imagine that now we have something more complex。😊。

Where we have even more nestedness right now we have continents and in every record we have a continent and inside that continents。

 we have a list story of continents in that case for Einstein， Europe and America。

 and in every continent， there is a list of countries right now we have the US in America。

 And then we have Germany， Italy， Switzerland and Australia and。😊，Belgium。

 probably in the in the in Europe， right， So now you have two levels。

You have their countries listed inside continents， listed inside people。

 It's like the inception movie again， right， a dreaming a dreaming， a dreaming。

 a dream and you have an array， and a， an array。But now the cool thing that you can do since you have two levels is that you can explode once and then explode again on a second level and that gets you two lateral views。

 it's as if you had a table of names， a table of continents and a table of strings。

 but the tables of continents and of strings they don't really exist they are just taken from these arrays and so you can do these threeway join with a lateral view exploding the continents and then a lateral view exploding the countries。

😊，Right。Who has a headache？Okay， because I do。 but just this is basically showing to you what the limits are。

 it kind of works。 It does the trick。 you can do something with a race。

 but you see that it starts becoming complicated right It feels like the language wasn't really designed for that。

 So it's artificial， right。😊，Now we have the same thing for objects because that was about a race。

 right， so explode and lateral use。 Well， for objects。

 it shouldn't surprise you that we use a dots because that's a bit like in Python， like in Java。

 you navigate objects with the dots， right who's familiar with object oriented programming。😊。

Right many of you。 so we love dots， basically。And so the moment engineers need to make SQL work with objects。

 What do they do， They do SQL with dots， So they extend the SQL language with dots。

 And this is exactly what happened here， Now if you have this name that is now an object that would technically be astruct type in data frames that I just put objects in there。

We have two keys first and last， so it's a data frame right because it's really structured。

 it's always the same keys， it's always the same types and now we can say name dot first and name dot last and that is going inside the object and extracting the individual values who understands that。

😊，All right。Now it looks nice because we can deal with a arrays， we can deal with objects。

 we get a bit of headache along the way， but it's still working。😊。



![](img/0ccf873205d186dd77168d711d25a22a_45.png)

Now， let's break it even more because a headache technically is okay， right， it's， it's not pleasant。

 but it still works。 But here's when it stops working。Imagine that。You have now。Jason data。

That cannot even be put in a data frame。It exists， right， If you look at collections of there。

 data sets over there， Sometimes you cannot validate the Json data。 It's just not the same schema。

Why can it happen Well， for example， you can have a company that has 30 years worth of log。

 but the schema changed maybe every five years， every 10 years they change the format of the log so you basically have the first five years of data that look went away and then the next five years look different and so on in that case you cannot fit it in a data frame that doesn't work anymore because we saw that data frame that only for valid JO data against the same schema。

😊，So what happens with these data sets that are over such long periods that they don't even have any schema？

呃。Well， I have a good news and a bad news， and I don't know if the good news is actually a good news。

 but it's up to you to judge。The good news is that if you feed sparkock。

With a collection of Jason objects that is heterogeneous。It's not going to complain。

It's not going to reject it。Is going to take a big hammer and hit it strongly enough that it fits in a data frame。

This is where I start doubting。 It's actually a good news， but technically， this is what it does。



![](img/0ccf873205d186dd77168d711d25a22a_47.png)

And what is actually going to happen when it hits it with this hammer is that it's going to notice。

 okay this is often an integer， but it's not always an integer because here it's an array of integers right it's not a problem if we hit it strong enough with a hammer we can just fit it into a string and that's it so we basically serialize back that's into a string。

 this is a string containing the character one， this is a string containing square brackets three comma space for square brackets。

 we just put it all into a string and we make it a string column。😊。



![](img/0ccf873205d186dd77168d711d25a22a_49.png)

![](img/0ccf873205d186dd77168d711d25a22a_50.png)

![](img/0ccf873205d186dd77168d711d25a22a_51.png)

![](img/0ccf873205d186dd77168d711d25a22a_52.png)

![](img/0ccf873205d186dd77168d711d25a22a_53.png)

That first site is great because he didn't complain and it successfully imported the data frame。😊。

But do you see what just happens？It basically said， yes， okay， fine， fine， fine。

 I'm going to import that J object because you wanted it。

But now it's your problem to deal with it because now imagine you have to write the Python code that does something with these three。

4 and these two and so on。Do you already feel how complex that code is going to be。

 you're going to have to maybe write some transformation because forget about Sp SQl right Sp SQL will not know what to do with these strings or what's inside。

😡，So you will have to write Python then what you will have to do is to technically have some complex code that looks at the string and says。

 okay， does it start with a square bracket if yes， then let me try to pass it as an array and no no it's a digit so let me pass it as an integer。

😊，The thing is， Sp made it your problem。Now you have to write the Python code to deal with that complexity。

 These are the emit of Sp SQL here， if there's nestedness， a bit of nestedness is fine。

 a lot of nestedness causes headaches， although it still works。

 but if the data becomes heterogeneous。😊。

![](img/0ccf873205d186dd77168d711d25a22a_55.png)

Now it's it becomes a really serious problem this is both becoming unmanageable。

 These are the limits of Sp SQL and the key point here is to understand that you need other languages that are similar to SQL。

 but languages that understand trees because SQL where for tables and there's other languages that understand trees。

Wund of1，30 minutess。I guess all of them who feel headache here got up my point because that was my goal here。

 I want you to see that this is becoming scary here and even more here。



![](img/0ccf873205d186dd77168d711d25a22a_57.png)

Okay。

![](img/0ccf873205d186dd77168d711d25a22a_59.png)

Well， I had to the last slide just to tell you that。You know， I told you that under the hood。

 when you create data frames， Spk is magically converting them to RDDs in the background hidden from you。

😊，But you can also do it explicitly。 So if you have a data frame。😊。

You can first convert it to an RDD， you're just going to get an RDD。Of rose。

And the other way around you can take an RDD and turn it into a data frame but to turn an RD into a data frame。

 you need a schema， you need to help spark a little bit it's able to infer the schema automatically if you read data from CSV or Jason but it's not able to infer the schema if you start with an RDD that can be anything so here you need a you need to give a hint to Sp here make a data frame。

 but I'm helping you by providing you with the schema that I'm expecting。Okay。

 that's actually it or sparkies。 We have a question of all there。 Maybe we can throw the。😊。

I didn't quite understand why in the last slides。

![](img/0ccf873205d186dd77168d711d25a22a_61.png)

The issues is actually from Spk。 I would argue the the issues in the data itself。

 So Spk just tells you， okay， this is fine。 And then you have to check it。Yep。

 so let me comment about the whole ecosystem and the thinking about this。

You're saying there is a problem with the data。Yes。

 there is a problem with the data that I agree with this data has a problem because it doesn't have a schema。

So。As a database person， when I look at this data， I also feel like you a bit uneasy。

 Like this data is not very clean， right， So the what you're referring to is the click data that is not clean。

能。If you consider typical use cases， what do people prepare data for right you download the data from the internet。

 what do you use it for Well nowadays it's for machine learning right so you prepare the data。

 you get a data sets but to fit it into a machine learning algorithm。

 let's say a classical machine learning you need to have something that has features right you have。

 for example， I don't know if you want to classify animals then the number of legs。

 the number of ears and so on and so on right these are features and you have them arranged in columns and then some of the columns are the label saying this is an elephant。

 this is a cat， this is a dog and so on So when you want to input these data into a machine learning algorithm。

 it needs to be clean。If you give that to a classical machine learning algorithm that's not going to work because you assume that the data must be cleared。

 I'm not talking about the more recent things with ChGT， deep learning and so on where。

 you can fit pretty much anything whether it's a good ideas or another thing。

 but for classical machine learning algorithms， this data has a problem because you cannot fit it in there。

But that's precisely the point。It's precisely because this data has a problem。😊。

That you need to clean it。So what's actually going to happen in real life is that the data you get inside your company or from the logs or from the server of the company。

Is like this that you have no choice about， you get the data， it's not going to be clean。

 that's how it is。 You have no choice about that。What you need to do is clean it up。

Once it's cleaned up and it's nicely homogeneous and in the schema， and that's fine。

 You can use P Sql， you can use all of these things。😊，But there is a gap。

That we still have between unclean and clean。 How do we clean up the data。

And the thing is to clean up the data， at that point。

 I have no choice than to write a lot of code in Python that's going to be cumbersome to write。

 to clean it up。😊，And so what I'm saying is that to solve that problem of how do we clean up the data。

 there are languages that make it easier to clean up the data because these languages can directly deal。

😊，With heterogeneity right so in summary， I totally agree with you that there is a problem with the data。

 but it's precisely in order to fix that problem that we need to make it easy to fix that problem right so we need to provide easy ways to clean up the data。

😊，Does it help that make sense awesome， thank you man that was a good question。

 it's very good to think critically。😊，Right。😊，And again， I repeat。 This is real life in the logs。

 but a lot of data there is actually structured， right， The one you actually use。

 I would call it curated， right， the data sets on the Internet are often curated。

 But it's because somebody went through the effort of of cleaning it up right。

 And that I would call more raw data。 That is， as it is。😊，Any other questions？On zoom。Last call。

Before boarding。All right， then I'm moving on to， oh， yes， the one I had before。

 the one you had before， was there a question before？😊，Yeah。

 so each cell is seen as a table or the whole economy is seen as a single table。

Oh for the virtual join。

![](img/0ccf873205d186dd77168d711d25a22a_63.png)

Yeah， yeah， so。Technically。There's multiple ways to look at it。嗯。If you look at the lateral view。😊。

One way to look at it。Is to consider that。The continent table is itself a different table。

 but a single table for all the data。In that table， you basically will have。

The currents you see here sea and countries that would be the two。Colonons of that table。

 plus a third column。That would be the primary key pointing back to the people。

 maybe even two columns because you have first and last。

 so you can view the entire column that is an array as a separate table with all the data in the same table so this is one way to look at it。

 in fact if if you if you denmalize no sorry if you normalize the data。

 you would get a single table for the entire column。

But there is another way to look at it and if you look at it from a denormalized perspective。

 then you will see a table in every cell， so you can also see four tables here。

 one table in every cell， but when you normalize the data and get a separate table。

 then you get a single one for all of them。😊，But the thing is， what's important to a understand。😊。

Is that。In order to be able to see a single table。

![](img/0ccf873205d186dd77168d711d25a22a_65.png)

To put all of that into a single table。😮。

![](img/0ccf873205d186dd77168d711d25a22a_67.png)

You need the same schema everywhere that only works if it's homogeneous right thats only working it if it's homogeneous。

 if it's heterogeneous or if the tables do not look the same。

 then you cannot do this and then you have no other choice than seeing a separate table in every cell。



![](img/0ccf873205d186dd77168d711d25a22a_69.png)

![](img/0ccf873205d186dd77168d711d25a22a_70.png)

Right。And as an intuition。What happened is that if the data is homogeneous and you can actually turn the whole column into a single table rather than a table for every cell。

 things become faster and more productive and easier to write The moment you start having tables that behave differently in every cell。

 I think it's called the correlated query in in the world of languages it's actually complex it's not easy to implement it's not easy to write and in fact many systems do not support that sort of queries right So the short answer survey is you can see it in both ways。

 you can either see it as one table per cell， or you can say it as a single virtual table across the entire column。

And when you do a lateral review， you see technically as a single table across the entire column。

All right。Who is reading the textbook。good。 I see a few raised heads on Zoom。

 who is reading the textbook。Very good。 You need to read it， right。

 The lecture is complementary to the textbook。 I'm telling the same things。

 The goal of the lecture is to motivate you。 give you the big picture。

 But the textbook has all of the all of the details。😊，O。Very good， by the way。

 you know what somebody did， I saw a professor in the US university。What they did is that。They wrote。

In the textbook， in the middle of the textbook， that there is a $50 note in that locker in that place with that code。

😊，At the end of the semester， he went to the locker and the bill was still there。

 The bank note was still there。 I think it was very very smart。

 but I know that you're reading the textbook that is something that that I trust。😊。



![](img/0ccf873205d186dd77168d711d25a22a_72.png)

Okay。

![](img/0ccf873205d186dd77168d711d25a22a_74.png)

And I wrote the textbook for you。 I mean， it was a request by students a couple of years ago。

 They they wanted one。 And so I， I granted that wish by。



![](img/0ccf873205d186dd77168d711d25a22a_76.png)

Providing you with one。 All right。

![](img/0ccf873205d186dd77168d711d25a22a_78.png)