# 苏黎世联邦理工《大数据｜Big Data - ETH Zurich - Fall 2024》中英字幕（deepseek - P3：-03-2. Lessons learned (1_3) -.zh_en - GPT中英字幕课程资源 - BV1sHPKeoEJU

So welcome back， we are now。Yeah I said that a lot we are now in the second part of the lecture it's called lessons learned why because that's all things that have been done 40 or 50 years ago。

And even though big data is new， a lot of things are not new because we have to learn from what people did before。

Learning what people have done in the past is an enormous accelerator probably link things because you don't remake the mistakes that they have already done。

 so this is the why we are going to take the time to go through the early databases。

Now I have to give you a word of warning because I want to make sure that you don't panic。So。

Two things are going to happen。In this lecture。Some of you。Will be bored today and tomorrow。

 they will be bored because you've already seen that in the database lecture in your bachelor's right take it as a brush up。

 just a refresher of things that you already know but it brings it back to your mind。

Some other people。We'd be scared。At the end of today and tomorrow's lecture。 And I want to tell you。

 do not this。Because the reason you're scared is that I'm going to dump at you a whole semester of material of relational databases and that's very scary because normally we don't take two hours to do it。

 we actually take maybe 28 hours for an entire semester。

But the reason you shouldn't panic and it's really not a big deal is that you actually don't need to know all of the details for the big data lecture。

 it' relatively independent of the rest， but I take it as a survey。

 So just speak back look get the main ideas of what was done in the relational database the main assignment that you have will be to learn SQL if you don't already know SQL and SQL is really not difficult to learn business people learn SQL。

 you don't need to be a computer science So I love business people I mean you cannot found startups without them right so you need everybody in the ecosystem what I want to say is you do not need to be a computer scientist to learn SQL right so I recommend that。

That you take the time in the exercises next week， you will have a few Jupyter notebooks to practice。

All right， who is ready？😊，Who is going to be bored？W's going to be scared。Okay， most man。

 if I'm happy if nobody's balled or scaredd， then this is， then this is。Okay。This is at Gwood。

Ed Gacott is considered the father of modern relational databases because he had the genius idea of separating between tables and manipulating tables and all the complexity of the implementation that nobody wants to care about。

This has a name， it's called data independenceence。



![](img/76d6a3838353c4815ff7e805319b9acc_1.png)

Data independence is the idea that whoever uses SQ and interacts with the database management system。

 so the whole world is relational database management system areD BMS if you see it somewhere。



![](img/76d6a3838353c4815ff7e805319b9acc_3.png)

![](img/76d6a3838353c4815ff7e805319b9acc_4.png)

So you just look at a table and interact with a table。

 it feels like interactive with a spreadsheet software like Excel right so that's a lot of people understand this。

😊。

![](img/76d6a3838353c4815ff7e805319b9acc_6.png)

![](img/76d6a3838353c4815ff7e805319b9acc_7.png)

The physical storage， you don't need to see it。 That's all hidden。

 It's implemented in C plus+ or Java or whatever。 You don't need to care about this because all you see is that this is called data independence。

 It means that you can implement exactly the same thing on top of a C plus plus local implementation or a clay tablet。

 Yes， absolutely you can do it。 It's going to be slower。

 but it also works you can also implement it on top of spreadsheets software in such a way。

 a single hub drive or a cluster of machines and still get exactly。



![](img/76d6a3838353c4815ff7e805319b9acc_9.png)

![](img/76d6a3838353c4815ff7e805319b9acc_10.png)

![](img/76d6a3838353c4815ff7e805319b9acc_11.png)

![](img/76d6a3838353c4815ff7e805319b9acc_12.png)

![](img/76d6a3838353c4815ff7e805319b9acc_13.png)

![](img/76d6a3838353c4815ff7e805319b9acc_14.png)

The same look and feel for the system。 That's the magic of data independence。 So remember。

 that's data independence。 That's absolutely fundamental。

 It's this idea of separating the logical layer。😊。

![](img/76d6a3838353c4815ff7e805319b9acc_16.png)

![](img/76d6a3838353c4815ff7e805319b9acc_17.png)

From the physical layer， you can even do it on DNA。People did it。嗯。

This principle of data independence will actually follow us throughout the semester。

 it's true for relational database management systems going to be true almost at every level of the stack when we build something that will be an upper path and a lower path and the U path will be the logical implemented on top of the physical layer right and you can do it even with many more layers than two。

It's something quite natural to do for a computer scientist actually to reason and abstract in this way。



![](img/76d6a3838353c4815ff7e805319b9acc_19.png)

So this is data independence。Then we saw data shapes already。

 So I told you that there are these five fundamental shapes， right， So trees stables， cubes。

 graphs and。

![](img/76d6a3838353c4815ff7e805319b9acc_21.png)

![](img/76d6a3838353c4815ff7e805319b9acc_22.png)

Unstructure text from which maybe vector databases will spin off at some point。

And today we'll focus on this right the brush on tables we'll have plenty of time throughout the semester to explore this and this we explored in information review。



![](img/76d6a3838353c4815ff7e805319b9acc_24.png)

![](img/76d6a3838353c4815ff7e805319b9acc_25.png)

Okay， so I'm focusing on the tables and don't worry， because people did it 4000 years ago。

 that's something very natural to look at。

![](img/76d6a3838353c4815ff7e805319b9acc_27.png)

![](img/76d6a3838353c4815ff7e805319b9acc_28.png)

So the general idea for tables and we'll see it's also true for all the other shapes。

 if I oversimplify everything。

![](img/76d6a3838353c4815ff7e805319b9acc_30.png)

We basically have a layer of storage that we store it in bits then we have a layer of computes like CPUs and so on then we have a layer of modeling this is describing what a table is and then we have a layer of language that is basically a query language like a SQL you could put an LLM also on top that's probably going to happen at some point but this is the idea of these four layers right。

😊。

![](img/76d6a3838353c4815ff7e805319b9acc_32.png)

![](img/76d6a3838353c4815ff7e805319b9acc_33.png)

![](img/76d6a3838353c4815ff7e805319b9acc_34.png)

![](img/76d6a3838353c4815ff7e805319b9acc_35.png)

So let's focus on the model because this is basically as you might have guessed。

 this is where data independence comeve into play right you basically do the curve here。

 this is the logical path， this is the physical path。



![](img/76d6a3838353c4815ff7e805319b9acc_37.png)

![](img/76d6a3838353c4815ff7e805319b9acc_38.png)

![](img/76d6a3838353c4815ff7e805319b9acc_39.png)

So when you define a model， like the relational model， as it is called for a relational tables。

 you need two components。 You first need to say。What data looks like， you need to describe a table。😮。

And you need to say what you can do with that data。

 So the manipulation primitives that you can apply to that data。

You would see it's actually pure bath。In fact， you can do an analogy with cooking。

 you can define what food looks like， so all the ingredients， something that can be eaten。😊。

And what you can do with it， that's all the verbs that you will find in recipes， right， you can mix。

 pork， break， dry bake， grill， melt， mincs， mix and so on。We see that it's the same thing for tables。

 we describe tables。 the words we use will be。Project， select， group， sort， and so on。

 we will also have the verbs that we can apply to。

![](img/76d6a3838353c4815ff7e805319b9acc_41.png)

Okay， so now again， now I keep repeating the same thing， but it's very important。

How does data independence work？It works because。

![](img/76d6a3838353c4815ff7e805319b9acc_43.png)

Back in the 70s。😊，Putting myself here， yeah， here。 back in the 17s， This is what we had。

 You have a single computer， single hard drive， single CPU back then。

 we didn't have all the the multiple cars。 and you implement a relational table with sQl on top。



![](img/76d6a3838353c4815ff7e805319b9acc_45.png)

![](img/76d6a3838353c4815ff7e805319b9acc_46.png)

![](img/76d6a3838353c4815ff7e805319b9acc_47.png)

What do we do now， what did we do maybe 10 or 20 years ago。

 we kept exactly the first two layers as they are， but we swapped the two bottom layers with the data center。



![](img/76d6a3838353c4815ff7e805319b9acc_49.png)

![](img/76d6a3838353c4815ff7e805319b9acc_50.png)

We didn't change anything there plus we did the same vacuums for trees for graphs and so on that's the beauty of data independence you can change the physical layer but without it actually changing the logical layer you might still notice a change from the logical layer what you might notice is that it's certainly faster that's what you might notice and you think okay maybe somebody didn't improvements on the physical layer but the behavior should be exactly the same。



![](img/76d6a3838353c4815ff7e805319b9acc_52.png)

。In fact， this is what we do in big data， as you might have guessed， that's say。



![](img/76d6a3838353c4815ff7e805319b9acc_54.png)

But in the bachelor's， you basically study this architecture。



![](img/76d6a3838353c4815ff7e805319b9acc_56.png)

All right。So then。Let's start。Describing what the table is。

That you't need to worry about I could do it in a primary school to third graders。

 what I'm about to say。What is the table。But it is something that looks like this。Thank you。



![](img/76d6a3838353c4815ff7e805319b9acc_58.png)

Right。😊，Now there's plenty of ways you can call it you can call it a table but you can also call it a collection or relation or relational tables these are just synonyms right that you might find in the literature we just call it a table typically collection you might find a lot in a big data context that you consider a table to be a collection al right so this is a table looks like this。



![](img/76d6a3838353c4815ff7e805319b9acc_60.png)

![](img/76d6a3838353c4815ff7e805319b9acc_61.png)

![](img/76d6a3838353c4815ff7e805319b9acc_62.png)

Now， another concept that belongs to the relational model is the concept of a role。



![](img/76d6a3838353c4815ff7e805319b9acc_64.png)

A row， something like this， right， horizontal that's made of multiple values。



![](img/76d6a3838353c4815ff7e805319b9acc_66.png)

Like this。 Some people call it business object item entity document recordpper。

 the business people call it business objects。 I actually hope that a lot in company environments。

 records is also very often encounter a document where we see why it's also called the document when you denormalize the data an entity in the entity relationship model。

 a tople could also be called a tople。 we see why， but these are all meaning the same thing。

 This is really this is here a record or。😊。

![](img/76d6a3838353c4815ff7e805319b9acc_68.png)

![](img/76d6a3838353c4815ff7e805319b9acc_69.png)

Okay。Then we have a column like this。

![](img/76d6a3838353c4815ff7e805319b9acc_71.png)

A column is also called an attribute， a field， a property， a key。

 be careful if you call it key that's in the context of Jason。

 but not to be confused with primary keys， come to that。



![](img/76d6a3838353c4815ff7e805319b9acc_73.png)

![](img/76d6a3838353c4815ff7e805319b9acc_74.png)

Attribute and column maybe are the ones we should call in a relational model context right so this is the column so the row and the column and the intersection of the row and of the column gives you a cell and we'll talk more about the content of the cell a little bit later what's also important and I'll come back to that is that if you look at a single column the values in there tend to be on the of the same type right tell you more about that。



![](img/76d6a3838353c4815ff7e805319b9acc_76.png)

![](img/76d6a3838353c4815ff7e805319b9acc_77.png)

![](img/76d6a3838353c4815ff7e805319b9acc_78.png)

![](img/76d6a3838353c4815ff7e805319b9acc_79.png)

So table row， column。

![](img/76d6a3838353c4815ff7e805319b9acc_81.png)

Some of the Collins。Might be a bit special can be one， it can be two。

It can be special because it identifies the record。

 imagine you stock people in a table and you have a column that is the Social Security number。

 the Aha file number， let's say youre the tax office right you're the tax office。

 you have the list of everybody who visits a tax return， you have the list。

The Social Security number is a special column because it's different for every record。

 That means that if I give you the Social Security number， you know the records。

 that's called a primary key。😊，Who heard of them， you studied relational database。

 who never heard of a primary key。Everybody heard of a primary key， wow。If you didn't。

 so really think of the Social Security number， the Ahafo number in Switzerland。



![](img/76d6a3838353c4815ff7e805319b9acc_83.png)

Some people call it a raw ID in the context of No SQL， a name or so a key， sometimes secondary key。

 but instead later primary key is really the main one。



![](img/76d6a3838353c4815ff7e805319b9acc_85.png)

![](img/76d6a3838353c4815ff7e805319b9acc_86.png)

If you go to a real systems， it's very often that the primary key has a single column with a letter ID like EID could be person ID if it's let's say it's a list of computers。

 then it's going to be CID computer ID so this is kind of a common practice if you lack imagination and you just want to make up some name for the column here？



![](img/76d6a3838353c4815ff7e805319b9acc_88.png)

![](img/76d6a3838353c4815ff7e805319b9acc_89.png)

![](img/76d6a3838353c4815ff7e805319b9acc_90.png)

![](img/76d6a3838353c4815ff7e805319b9acc_91.png)

![](img/76d6a3838353c4815ff7e805319b9acc_92.png)

Okay， it's quite simple， actually you right， we have a table， we have rows， we have columns， we have。

😊。

![](img/76d6a3838353c4815ff7e805319b9acc_94.png)

Some of the coordinates that are special， by the way， it can be several doesn't have to be just one。



![](img/76d6a3838353c4815ff7e805319b9acc_96.png)

Imagine for example， the number of plates， the license plates on the cows， in Switzerland。

 you need two columns， you need the content plus the number that would be two columns that together identify a car。



![](img/76d6a3838353c4815ff7e805319b9acc_98.png)

Okay， and finally， yes， the intersection of the row column is a cell or a value or a scal。

 it's the same term that we use， for example， for vector spaces when you have a simple real number as opposed to a vector。

 so a scal， a characteristic effects that when you do data cubes that you tend to do this。

 but let's just say a cell or a value that is in there right？



![](img/76d6a3838353c4815ff7e805319b9acc_100.png)

![](img/76d6a3838353c4815ff7e805319b9acc_101.png)

![](img/76d6a3838353c4815ff7e805319b9acc_102.png)

So this is it this is table row column primary key and value so at first it looks easy and intuitive what's incredible is that when you start applying the math defining it mathematically you can actually build a beautiful theory called database design theory that you can teach across several weeks in a semester it looks very very simple but actually you can derive a lot of incredibly complex and useful things out of something that simple。

😊。

![](img/76d6a3838353c4815ff7e805319b9acc_104.png)

So that's the model， right？The second part of the model is what you can do with tables。

 and now we have a very fancy name， it's called an algebrabra。

It's an algebra just like you can take numbers and add them and multiply them and you can take you know vectorect space。

 the scalag products and so on where you can do the same with tables。

 you can take tables and you can apply things to them you can transform a table into another table and so on that's called the relational algebra who remembers the Greek letters Ima gamma。

 what on wellow okay。So。Before we get to that， let me explain why it's called radiational table。



![](img/76d6a3838353c4815ff7e805319b9acc_106.png)

It's actually cool that way。😊，Because one of the ways you can define a table that's very common in textbooks is as a mathematical relation。

 who knows where the mathematical relation is？😊。

![](img/76d6a3838353c4815ff7e805319b9acc_108.png)

W forgot what it is？😮，Okay format its technically the subset a subset of the catn products right basically what you do is you define a domain。

 a set that has all the possible values you can have here。

 another domain that has all the possible values you can have here and another domain that has all the possible values that you can have here。



![](img/76d6a3838353c4815ff7e805319b9acc_110.png)

![](img/76d6a3838353c4815ff7e805319b9acc_111.png)

![](img/76d6a3838353c4815ff7e805319b9acc_112.png)

When you do that。😮，And you look at a single record。

 a single row and you think of it what is it mathematically， well mathematically it's a topper。

 why is it a topper because if you think of it it's one value taken from that domain。

 one value taken from that domain， one value taken from the sub domain that is called the topper in mathematics。

😊。

![](img/76d6a3838353c4815ff7e805319b9acc_114.png)

![](img/76d6a3838353c4815ff7e805319b9acc_115.png)

![](img/76d6a3838353c4815ff7e805319b9acc_116.png)

![](img/76d6a3838353c4815ff7e805319b9acc_117.png)

And a relation is a set of topperpers。If the Tupper is in the set， then the relation exists。

 if it's not in the set， then it's voice， you can also view it like a prediiccate。



![](img/76d6a3838353c4815ff7e805319b9acc_119.png)

![](img/76d6a3838353c4815ff7e805319b9acc_120.png)

So if you do the math and consider that the relation is a subset of the cartrogen product。

 it's just a set of topperpers。 but， of course， you are not going to view them like this。

 You are going to display them like that， okay。

![](img/76d6a3838353c4815ff7e805319b9acc_122.png)

![](img/76d6a3838353c4815ff7e805319b9acc_123.png)

![](img/76d6a3838353c4815ff7e805319b9acc_124.png)

Takes a bit of thinking， actually， to， to， to understand the the the mapping between tus and the and and tables。

 Who does see that。Okay， who doesn't？Okay， even if you don't。

 you don't have to worry too much because this is the definition that you find in textbooks。

I don't like this definition。The reason I don't like it is because it has a few limitations。

 It seems to do the job at first， that one of the things， for example， that it doesn't do。



![](img/76d6a3838353c4815ff7e805319b9acc_126.png)

That when you define a mathematical relation， there is an order between the set。

 that's the first value， that's the second value， that's the third value right so there is really a first column a second column and a third column mathematically。



![](img/76d6a3838353c4815ff7e805319b9acc_128.png)

But in a relational database management systems， normally the other of the columns doesn't matter if you swap the columns they will have a name。

 if you swap for example， the first name and the last name and you put the last name before the first name still the same data doesn't change the setics of the data。

So this is why mathematicalely it has a few limitations。😊，But still。

 it gives you the origin of the why it's called relational database management systems and why it's called a relational theory。

There's a simpler definition that actually prefer to use in the context of big data。

 and another reason I like to use this one as we will see is that it naturally leads to big data more naturally than this one。



![](img/76d6a3838353c4815ff7e805319b9acc_130.png)

![](img/76d6a3838353c4815ff7e805319b9acc_131.png)

![](img/76d6a3838353c4815ff7e805319b9acc_132.png)

So how do we define now a relational table， it's like this first thing you need is it's called a scheite a set of attributes right here you say。

 okay， I have four columns， PID last first and country。😊。



![](img/76d6a3838353c4815ff7e805319b9acc_134.png)

![](img/76d6a3838353c4815ff7e805319b9acc_135.png)

And then you define that part， it's called an extension， that's the contents of the table。😊。



![](img/76d6a3838353c4815ff7e805319b9acc_137.png)

And it's going to be a set of topperpers here it's a set of six topperpers there's the tople1 Einstein Albert C that basically populates the attributes。

 This says the Ph P ID is one， the last is Einstein first is Albert and counts is country is C right Do you agree this is a set of six toppers Who agrees。



![](img/76d6a3838353c4815ff7e805319b9acc_139.png)

![](img/76d6a3838353c4815ff7e805319b9acc_140.png)

Okay， great。Now there is a bit of freedom in whether we call it a set or a list or a bag and that really depends there's many ways to do it。

 it depends if the order matters， do you consider that the order of the records is important then you should take it as a list of toppers then there's a first topper a second toper and one if you don't care about the order at all and you don't have the duplicates that's just a set of toppers if you shuffle the records here it doesn't matter imagine the tax office and you shuffle the table that has the people finding their taxis nobody will see the difference。



![](img/76d6a3838353c4815ff7e805319b9acc_142.png)

![](img/76d6a3838353c4815ff7e805319b9acc_143.png)

![](img/76d6a3838353c4815ff7e805319b9acc_144.png)

![](img/76d6a3838353c4815ff7e805319b9acc_145.png)

Right it's just the same data， so there is a bit of freedom。



![](img/76d6a3838353c4815ff7e805319b9acc_147.png)

In order to say a table。Is a set of topperpers， a bag of topper or a least of topper。

 What is a bag Who knows what a bag is。

![](img/76d6a3838353c4815ff7e805319b9acc_149.png)

Yes。😊，To be sorted and can exactly yeah so the bag is like a list because it's sorry it's like a this because it can have duplicate but it's also like a set because it's not sorted so it's midway intermediate between set and list if you were in the information retrieval you already remember that right you alreadyt know that。

😊。

![](img/76d6a3838353c4815ff7e805319b9acc_151.png)

![](img/76d6a3838353c4815ff7e805319b9acc_152.png)

![](img/76d6a3838353c4815ff7e805319b9acc_153.png)

Okay。The original relational model is a set of toppers in the original version it was defined as a set of topper。

 but if you look at the actual implementations of the systems like PoSQA and so on they all have an order in fact you can even sort the consents of the table with an order or by statement so for this reason where you actually have in practice is more like a list of topper implementation if you are a mathematician and you really want the purest form of a relational model then that would be a set。



![](img/76d6a3838353c4815ff7e805319b9acc_155.png)

![](img/76d6a3838353c4815ff7e805319b9acc_156.png)

Okay， does it make sense。So what we call a tople， either you know that this is what a tuple is or you don't care and you just call it a records。

 you can also say a set of records if you prefer to say a set of records。

 but this is basically these are the roles。Now， why did I say a table is a collection because now we can say a table is a collection of rules and collection。

 a collection can be with set bag or list symmantics， who is following me。



![](img/76d6a3838353c4815ff7e805319b9acc_158.png)

![](img/76d6a3838353c4815ff7e805319b9acc_159.png)

![](img/76d6a3838353c4815ff7e805319b9acc_160.png)

Okay， very good， so I haven't scale you yet。

![](img/76d6a3838353c4815ff7e805319b9acc_162.png)

Now， if I do a little bit of math， what is tud here is basically a function that assigns the attributes to the values。

 for example， let's take this one。

![](img/76d6a3838353c4815ff7e805319b9acc_164.png)

![](img/76d6a3838353c4815ff7e805319b9acc_165.png)

Mathematic， So we。This one， second one。I can write it down mathematically， like this。

As a partial function， why partial because it only maps four attributes。

 but the set of possible attributes would be very large。

 it's any string right but it's partial so it assigns the V2 to PAD。

 Ramanjanniva to first and India to the country。

![](img/76d6a3838353c4815ff7e805319b9acc_167.png)

For the notations， it's not official right but I tend to use s for strings and V for value。

 but it's not very important， but basically decide what the tu is iter signs。



![](img/76d6a3838353c4815ff7e805319b9acc_169.png)

![](img/76d6a3838353c4815ff7e805319b9acc_170.png)

AV。Two attributes， That's the top。That's also a top sound strike。Yeah， that's the same thing。

 it's just a difference syntax， but it's exactly the same thing。This is look here。



![](img/76d6a3838353c4815ff7e805319b9acc_172.png)

Sorry。

![](img/76d6a3838353c4815ff7e805319b9acc_174.png)

Yeah， do you see the same thing， this is the mathematical way。😊，This is a synt， What is it called。

 do you know？Jason， this is Jason， so this is a syntactic representation of the tor right we'll come back to that。



![](img/76d6a3838353c4815ff7e805319b9acc_176.png)

But in fact the database people prefer to view it in that way because that J is actually flat but we come back to that。

 this is the way to visualize it as a row in a table right so this is the intuitive display and a table is just a set of these things。



![](img/76d6a3838353c4815ff7e805319b9acc_178.png)

Yeah。Okay， so now。

![](img/76d6a3838353c4815ff7e805319b9acc_180.png)

呃。There's a few things。

![](img/76d6a3838353c4815ff7e805319b9acc_182.png)

A few constraints that we put on our tables， because if we don't have this constraint。

 it's not really a table， it looks like a table， but it's not really a table。So if I stay。

I take a collection of toppers， set back honest， take a collection of toppers。

 and I try to assemble them together。Will it work， sometimes yes， sometimes not， if you think of it。

 if you really want to table the toppper that you have in your collection。

They should all have the same attributes。

![](img/76d6a3838353c4815ff7e805319b9acc_184.png)

Do you agree with this？In the same table， they all have the same attribute。

 So this here pers the criterion that's called relational integrity。 I call it relational integrity。

 It means that all the tables that I have in my collection， they all have the same attributes。😊。



![](img/76d6a3838353c4815ff7e805319b9acc_186.png)

The fancy world for that is super。 the partial function。 They all have the same attributes。

 So this is the first checkbox。 there's three in total。

 that the first check it has relational integrity for this reason。

 I can actually compact it to this right because it's the same attributes every time。

 So I'm not going to repeat them So I just put it like this And this is a relational table。😊。



![](img/76d6a3838353c4815ff7e805319b9acc_188.png)

![](img/76d6a3838353c4815ff7e805319b9acc_189.png)

嗯。

![](img/76d6a3838353c4815ff7e805319b9acc_191.png)

This。Is an example where relational integrity is broken。 It's not respected。

 Do you see what's going on here。There is in the second row， the topper doesn't have any name。

In the third row， it doesn't have any value for his insist。

 whereas it has an extra value for country。That breaks relational integrity。 That's not a table。

 right， Who agree that's not a table。 so that's not a table because it breaks the first rule。

 so this is an whole when relational integrity， thes have the same attributes。



![](img/76d6a3838353c4815ff7e805319b9acc_193.png)

Then we have rule two。Rule two is called atomic integrity。

Atomic integrity has to do with what we put in those cells。What I can put in the cells。Are strings。

 dates， Buurians， numbers， you know， anything that's called by database people Atomic。

It's best to und what is meant with atomic with a counter example of what is not atomic。



![](img/76d6a3838353c4815ff7e805319b9acc_195.png)

And that is a counter example。Because I put a table， you see here。😮。

This is a table in a table I like to compare it with the inception movie you know a dream in a dream in a dream you can have a table in a table in a table in a table。

 it's not a lot in the good old world of relational database management systems that breaks atomic integrity you cannot have structuress inside the cells so here it's broken this is rule number two atomic integrity。

😊。

![](img/76d6a3838353c4815ff7e805319b9acc_197.png)

Then there is a third rule。That's called domain integrity。

Doomain integrity basically says that the topperpers。Always have or a specific attributes。

 the same type of value， so you're able to assign types to the columns to the attributes such that all the valuess in there have that type。

In that case， it has domain integrity because I'm able here to say these are strings。

 these are strings， these are bulloleans， these are integraltes， so this has domain integrity。😊。

A counter example would be this。

![](img/76d6a3838353c4815ff7e805319b9acc_199.png)

Here I can't because here I have a number and here I have a boan right so of course you could always tell me I mean if you're a mathematician。

 you will tell me that then you can just put the set of everything in there and that it's right it has domain integrity that's not how it works。

 You really need to have these kind of domains here that actually meaningful for a database person。😊。



![](img/76d6a3838353c4815ff7e805319b9acc_201.png)

![](img/76d6a3838353c4815ff7e805319b9acc_202.png)

Okay， so here it's broken here there's also a 4y2 that that is in the year， so this is broken。

 This is rule number three。If we put them together。



![](img/76d6a3838353c4815ff7e805319b9acc_204.png)

We have domain integrity， relational integrity， anatomic integrity， so known as teeth structures。

 all taps have the same attributes and within the same attributes， the value are of the same type。

 the intersection of these three gives you the beautiful world of SQL and relational database management systems of the 70s。

 the intersection of the three， then you have a relational table。



![](img/76d6a3838353c4815ff7e805319b9acc_206.png)

![](img/76d6a3838353c4815ff7e805319b9acc_207.png)

![](img/76d6a3838353c4815ff7e805319b9acc_208.png)

![](img/76d6a3838353c4815ff7e805319b9acc_209.png)

Why do I like to present it like this。Because in this course。

 we are going to break all of the three rules， the three of them， yes。Oh。

 I was wondering if I could just ask for atomic integrity。

 how do we enforce that like mathematically， how do we describe that we don't have nestings of tables and tables。

 Do we also like sort of have a strict sort of data type enforcement， like with domain integrity or。

So in practice， you can enf it by saying that the domains must be atomic， right？

Now you can start a philosophical debate because in fact， if you interact， so I'm a data scientist。

 right？If you interact with computer scientists and let's say high school teachers who teach computer science。

 now it's taught in high school or even in the bachelor's degree。哔哔 clean。A string of characters。

 A string。Is not going be considered atomic。 If you think of it in Java， a string is a class。

String is a class。 String is an object。 It's not like inbuan and so on that are actually primitive values。

So you could start a whole philosophical debate on what is atomic and what is not atomic right it started in ancient Greece you know thousands of years ago。

If you want to be rigorous mathematically， it does require some sort of standardization or agreements on what is atomic and not atomic now I'm not teaching a mathematics class so I don't need to give a formal definition in practice when when we say non atomic。



![](img/76d6a3838353c4815ff7e805319b9acc_211.png)

It's defined negatively what we really mean with nonatomic is tables， objects， arrays。

 you know all kinds of more elaborate structures， but everything like a string a number of dates and so on these are all considered atomic right so I would say in order to answer your question。



![](img/76d6a3838353c4815ff7e805319b9acc_213.png)

We basically defines extensively what is atomic and what is not I basically can give you a close list of the domains of what is atomic。

 everything that's not in the least that's not atomic， you could view it in this way。

We'll see in a few weeks that the types you can have are actually pretty sted out。

 it's always the same ones， so it means that the question is more simple than it actually looks。Okay。

So really think nonatomic means you have a table in a table， you have an object in a table。

 an array in a table that is nonatomic and that's breaking the first normal form。

I'll come back to it so many times we'll have more opportunities。 Did I answer your question。😊，好some。

Okay。

![](img/76d6a3838353c4815ff7e805319b9acc_215.png)

So now the beauty is now we can break the rule， so in the whole course I'm going to break these rules and we are going to venture I there。

 I there， out there， I there， out there。

![](img/76d6a3838353c4815ff7e805319b9acc_217.png)

![](img/76d6a3838353c4815ff7e805319b9acc_218.png)

And even out there。So this is the world of no SQL， which means not on this sQL。But not today。

 we'll have enough time during the semester to actually do this This is the reason why I prefer to give that second definition of the table because it allows us to basically drop these three wordss。



![](img/76d6a3838353c4815ff7e805319b9acc_220.png)

![](img/76d6a3838353c4815ff7e805319b9acc_221.png)

Okay。It's approaching the end of today， but it just continue tomorrow。



![](img/76d6a3838353c4815ff7e805319b9acc_223.png)

So let's look at the intersection again at the intersection， we have tables。

 the three rules are fulfilled。😊，And we have a beautiful way of manipulating these tables that fulfill the three woods that's called a relational algebra。

😊，You can just like numbers or matrices or whatever， we just do it with tables。



![](img/76d6a3838353c4815ff7e805319b9acc_225.png)

We can actually have some sort of classification of the sort of things that you can do。

 you can do the union of two tables， intersection， the subtraction。

 you can filter our project tables， you can rename the columns， rename the table。

 you can group or sort a table and call them shuffling， youll see why in the lecture。



![](img/76d6a3838353c4815ff7e805319b9acc_227.png)

![](img/76d6a3838353c4815ff7e805319b9acc_228.png)

![](img/76d6a3838353c4815ff7e805319b9acc_229.png)

Or you can join tables， you can take two tables that you bring together in order to join them。

 the tax office does that with the list of people and the list of tax declarations that's an example。



![](img/76d6a3838353c4815ff7e805319b9acc_231.png)

But let's go a little bit through them just to give you an intuition and again that's very high level you can give the complex mathematical definitions of that we can actually do this in the baachelor of lecturectures or but here is just a visual。

This is a selection， what is a selection， it means that I pick certain rows and not some others Imagine that。

 for example， I take these two。The selection criterion could be the ID is at least five right if it's at least five then these two survive and I get this table right here dip the selection by the way。

 the sort of things you can do in Excel right take a table you activate the data filter and then you check and select values and that does exactly this right that's called the selection。

The second one。

![](img/76d6a3838353c4815ff7e805319b9acc_233.png)

It's called a projection， It's the same thing but on the columns。

In a projection you say I want to keep these two columns in X you would hide this column and hide that column。

 then you get this table， that's called the projection。



![](img/76d6a3838353c4815ff7e805319b9acc_235.png)

ok。😊，Grouping is when you want to aggregate things it's very powerful imagine you're the statistical office of Switzerland and you want to compute aggregated data over other country by content imagine that these other contents Fu bar and Fubar and you want to aggregate them so food for example in green 19 plus4 plus 46 you aggregate it as a single value that's called grouping。



![](img/76d6a3838353c4815ff7e805319b9acc_237.png)

![](img/76d6a3838353c4815ff7e805319b9acc_238.png)

Okay，It's very， very useful in databases。😊。

![](img/76d6a3838353c4815ff7e805319b9acc_240.png)

I'm going to。Stop here just to to not overload you I think who survived today this thing the two complicatedlicate idiot right okay so I'll continue this tomorrow I will talk to you a little bit about normal forms tomorrow that's the most scary part of it all but you will see that you won't have to worry too much about the normal forms Thank you very much for attending the course today I see you tomorrow in this lecture hold over here at 915 a。

m Thank you。

![](img/76d6a3838353c4815ff7e805319b9acc_242.png)

![](img/76d6a3838353c4815ff7e805319b9acc_243.png)

![](img/76d6a3838353c4815ff7e805319b9acc_244.png)

![](img/76d6a3838353c4815ff7e805319b9acc_245.png)

![](img/76d6a3838353c4815ff7e805319b9acc_246.png)