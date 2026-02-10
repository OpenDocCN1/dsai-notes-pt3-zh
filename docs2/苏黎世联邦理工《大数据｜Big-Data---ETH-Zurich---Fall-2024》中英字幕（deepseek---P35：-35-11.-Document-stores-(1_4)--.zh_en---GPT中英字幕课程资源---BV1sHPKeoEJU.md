# 苏黎世联邦理工《大数据｜Big Data - ETH Zurich - Fall 2024》中英字幕（deepseek - P35：-35-11. Document stores (1_4) -.zh_en - GPT中英字幕课程资源 - BV1sHPKeoEJU

Welcome back。So now I'm going to。Continue where we left off。In S equalQl。

 So I showed you that with tax equalQl， if the data。Is highly structured data frames？

You can use Sp SQL and Sp transformations。But I also told you that if the data is nested。

 you can still use P SQL， but it becomes a bit more difficult， you need these lateral view。

 explode and so on and the dots for objects。I also showed you that if the data is heterogeneous。

Then Spark makes it your problem， basically puts everything in a string。

 and then it's up to you to pass the string again and deal with it。

 So it means that we need something else to deal with heterogene E and also better deal with nestness。

 So the next two lectures ongo Mongo Db or document stars and then then Jonic basically deal with exactly that with heterogeneous data and hyena data。

So in order to explain the the problems So or at least the solutions we have。

 because people have already been doing things in the past 50 years。

If I look at the relational algebrabra as the S brushup we did at the beginning。

 I can manipulate tables。😊。

![](img/99f61ee507d8bb2afd42b43133006845_1.png)

![](img/99f61ee507d8bb2afd42b43133006845_2.png)

Known as Sness， all homogeneous， I can project， select， join groups， soft and so on。

 Get another table， right， That's the radiational algebra。



![](img/99f61ee507d8bb2afd42b43133006845_4.png)

Then I have syntaxes right I can use CSV as a means to stock tables like that。

 I think many people prefer to export the content of the database as a SQL scripts rather than CSv。

 but that works too， but basically we have a syntax and that's the underlying syntax for this model。

 the relational model。

![](img/99f61ee507d8bb2afd42b43133006845_6.png)

![](img/99f61ee507d8bb2afd42b43133006845_7.png)

![](img/99f61ee507d8bb2afd42b43133006845_8.png)

![](img/99f61ee507d8bb2afd42b43133006845_9.png)

Then we have languages。 so in that case， SQL was made to process tables and manipulate tables and output tables。



![](img/99f61ee507d8bb2afd42b43133006845_11.png)

![](img/99f61ee507d8bb2afd42b43133006845_12.png)

So this is the beautiful world of the relational model， the relational algebra。

 the relational query languages and so on， and it works very。

 very well within that domain if you have homogeneous and data in the first normal form。😊。



![](img/99f61ee507d8bb2afd42b43133006845_14.png)

![](img/99f61ee507d8bb2afd42b43133006845_15.png)

So for this， we are doing really well， we've already even rebuilt that stack in the case of SQL。

 you know we did all of that， even data frames， if it's not nested， then that's a table。

 we can use Sp， you saw how you can select project join group and so on with Sp on the physical level with Hb we saw that we can also store the data。



![](img/99f61ee507d8bb2afd42b43133006845_17.png)

![](img/99f61ee507d8bb2afd42b43133006845_18.png)

![](img/99f61ee507d8bb2afd42b43133006845_19.png)

In a way that looks like table， even though it's not a fullflged query language and it's still very physical because all the values are binary values。

 And then for querying， we can use SQL people did it。

 people put SQL on top of H basease if you look into hive for example。

 you can do data warehousing on top of H base right and we also SQL on top of Sp with T SQL So for tables。

 this is very well known right we know exactly how to do But the thing is if the data is nested and or heterogeneous。

 then we still have a bit of work to do here we are still stuck here and we need to figure out out of that path in the case that the data is nested heterogeneous and now you associated。

 I hope the idea of nestedness and heterogeneity with Xml Json and that whole ecosystem so this is this is really the idea。



![](img/99f61ee507d8bb2afd42b43133006845_21.png)

![](img/99f61ee507d8bb2afd42b43133006845_22.png)

![](img/99f61ee507d8bb2afd42b43133006845_23.png)

![](img/99f61ee507d8bb2afd42b43133006845_24.png)

![](img/99f61ee507d8bb2afd42b43133006845_25.png)

![](img/99f61ee507d8bb2afd42b43133006845_26.png)

![](img/99f61ee507d8bb2afd42b43133006845_27.png)

![](img/99f61ee507d8bb2afd42b43133006845_28.png)

Now when we step into that world of nested slash heterogeneous data sets。

 some things change a little bit compared to the relational world in the relational world this is how it works。

 you can pass a CSV file and so on， you have a schema。

 you need a schema in a relational table in PoQ you don't have a choice， you need a schema。

 then you have tables that you can manipulate。

![](img/99f61ee507d8bb2afd42b43133006845_30.png)

Now， in the。Weorld of nested slash heterogeneous data we also call it semi structure you don't have to validate it's optional。

 you might remember that right you can have JO or XMM that's not validated at all it's heterogeneous and you just shock circuit kit the whole thing and you can directly query it with x query Jsononic and so on but you have a choice you can also validate it if you prefer and then you end up with a data frame or something like this that is a bit more efficient then you can query it but the idea is that it's faster that's really a question of speed this is going to be slower and this is going to be faster because it's compressed in memory textless space you can optimize a lot of things or whom is that here。



![](img/99f61ee507d8bb2afd42b43133006845_32.png)

![](img/99f61ee507d8bb2afd42b43133006845_33.png)

![](img/99f61ee507d8bb2afd42b43133006845_34.png)

![](img/99f61ee507d8bb2afd42b43133006845_35.png)

![](img/99f61ee507d8bb2afd42b43133006845_36.png)

![](img/99f61ee507d8bb2afd42b43133006845_37.png)

Right， so that's the high level。 And we see in the technology we are now going to look at at Mongo Dbi。



![](img/99f61ee507d8bb2afd42b43133006845_39.png)

![](img/99f61ee507d8bb2afd42b43133006845_40.png)

We'll see that this is a load MongoDb allows you to validate its JON schema I think that it uses。

 you can specify your JON schema to validate the data in collection， but you can do it later。

 you can just put the data in your collection without validation and later you try with a schema and then you can even enfl it for the future inserts into the collection。

😊。

![](img/99f61ee507d8bb2afd42b43133006845_42.png)

![](img/99f61ee507d8bb2afd42b43133006845_43.png)

![](img/99f61ee507d8bb2afd42b43133006845_44.png)

![](img/99f61ee507d8bb2afd42b43133006845_45.png)

Now， whenever you have something like this and here I put my data engineering hats， you know。

 that's basically the very early days of that before Mongodibi existed and so on。

 when the first people noticed that we need something else for nested heterogeneous data set。

There is an automatic thought that data engineers have。

Before trying to build a system completely from scratch。

 you should try to see if you cannot exploit existing systems。

 maybe you can just reuse Postgsql or something in a certain way to tweak it and reuse 90% of it and then on top of that you basically have this nested and heterogeneous data when people tried it and they fail but let me show you how。



![](img/99f61ee507d8bb2afd42b43133006845_47.png)

The idea is that you can try to map it two tables right so that shouldn't be a surprise to you if you have a flat JasonO like that。

 then you can map it to a flat relational record or whom is that here。

 hope for everybody by now right。The same for XML right this is the same you can map it so in some cases you can map it right then you if you have a collection of several in that case X documents and they have the same schema then you can put them like this you can even map the XM schema to a relational schema who agrees that this XM schema here would basically map to this postreQ and schema。

😊。

![](img/99f61ee507d8bb2afd42b43133006845_49.png)

![](img/99f61ee507d8bb2afd42b43133006845_50.png)

![](img/99f61ee507d8bb2afd42b43133006845_51.png)

Right the same with JSound so this is a JSound schema that would map elegantly to this table。

 so you agree that probably if I have a collection of Xml or that looks like this。

 then I can use PostreQware right I can just put it like this as it is and it's just going to work I just need to map everything to relational schemas and to the relational records。

😊。

![](img/99f61ee507d8bb2afd42b43133006845_53.png)

![](img/99f61ee507d8bb2afd42b43133006845_54.png)

![](img/99f61ee507d8bb2afd42b43133006845_55.png)

The problem is that it stops working when the data starts having nestedness and heterogeneity。



![](img/99f61ee507d8bb2afd42b43133006845_57.png)

People try to fix it。 You can try to fix it。 For example， you might have nested nest here。

 and you notice that you have objects in a array。 So these are what I told you is actually tables in tables in tables。

 So you could see it as a nested table here。

![](img/99f61ee507d8bb2afd42b43133006845_59.png)

![](img/99f61ee507d8bb2afd42b43133006845_60.png)

![](img/99f61ee507d8bb2afd42b43133006845_61.png)

And when you notice that there's still a bit of homogeneity right here， it's nested。

 but it's homogeneous because it's always the same the same feeds in there。

 Then if you think a little bit that you can deal with， you can map it two table， How do you do it。

 you just do two tables， one table for the top level and one table for the nested nest here and then you have a foreign key and a primary key you basically link them via join to link it back So Snivaar andja and called Gerel。

 they link back to here Alboang2 v right so you can fix it but it's a case by case basiss。

 you look at this then you can map it two table。😊。

![](img/99f61ee507d8bb2afd42b43133006845_63.png)

![](img/99f61ee507d8bb2afd42b43133006845_64.png)

![](img/99f61ee507d8bb2afd42b43133006845_65.png)

![](img/99f61ee507d8bb2afd42b43133006845_66.png)

![](img/99f61ee507d8bb2afd42b43133006845_67.png)

If you're missing fit， so that would be the case of heterogeneity， you can basically just put nerves。

 right， That's fine。 But then you're going to end up with a lot of nerves if you。

 if you have really heterogeneous data， right， So again， it works up to a certain point。😊。



![](img/99f61ee507d8bb2afd42b43133006845_69.png)

![](img/99f61ee507d8bb2afd42b43133006845_70.png)

![](img/99f61ee507d8bb2afd42b43133006845_71.png)

But then you try， you try， you try， and it's impossible to do it in the general case right it just doesn't work。

 And it's like putting a square peg into a round hole right So this was unsuccessful。

 and this is the reason why after trying that。It was decided to invent new systems that can natively process all of these things。

 We can still use a lot of lessons and practices， but this is why new systems actually appeared and that includes Mongodb。

 which we will look into next week because now it's I was checking the time it's almost 10。😊。



![](img/99f61ee507d8bb2afd42b43133006845_73.png)

![](img/99f61ee507d8bb2afd42b43133006845_74.png)

So yes， that was the appetizer to what we would do next week。 We look at documents stores in Mongodi。

 So thank you Macco for the moderation。 Thank you everybody for coming。 Enjoy the exercise session。

 If there's anything ask questions on the Moodle or directly send emails。

 Thank you for those of you who found typos in the book。

 I will fix them and add your name to the acknowledgement section。😊。



![](img/99f61ee507d8bb2afd42b43133006845_76.png)

![](img/99f61ee507d8bb2afd42b43133006845_77.png)

![](img/99f61ee507d8bb2afd42b43133006845_78.png)

![](img/99f61ee507d8bb2afd42b43133006845_79.png)

Thank you and goodbye have a good week。

![](img/99f61ee507d8bb2afd42b43133006845_81.png)