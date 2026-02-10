# 苏黎世联邦理工《大数据｜Big Data - ETH Zurich - Fall 2024》中英字幕（deepseek - P25：-25-7. Data models (5_5) -.zh_en - GPT中英字幕课程资源 - BV1sHPKeoEJU

![](img/7442510f1c3446996399d9b1ffc7cf11_0.png)

All right， so let's start right away。 So where were we？嗯。

You might remember that I told you last time that one of the use cases of XML over J is by the publishing industry where you have documents that are actually scientific papers。

 books， and so on， where you use the elements to annotate， just like in LaX， for example。

 you annotate parts of the documents。

![](img/7442510f1c3446996399d9b1ffc7cf11_2.png)

In XMM schema， you can say so。With mixed equals true that basically says that's a complex type that has an element B that is a string so that would be this right。

 but in order to say that it's okay to have text around it So you basically say mixed true and that allows you so that basically says that you can annotate with B portions of text and you can even do it as many times as you want because maxo curls is unbounded right So this is how you control this text oriented or publication oriented XMl and that is one of the strength where XMl really shines。



![](img/7442510f1c3446996399d9b1ffc7cf11_4.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_5.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_6.png)

Okay what else do we have attributes How do you validate attributes Well you might be happy to learn that the types of the attributes that the same as the types of the elements。

 the atomic types of course because you cannot have complex types in attributes so the way you do it is you define here I put the whole schema an element person that is a complex type with a sequence of last tenfers that are strings so that's what you see here how can I add this birth attributes where just after the sequence I have this again it's static attributes the name of which is birth and the type is date because date is in this huge list of atomic types at your disposal right so this is it so the type for attributes and an elements that just have text inside is the same works in the same way with this type right we call them simple content when there's just text inside right this we call mixed content and this we call complex content right so complex content mixed content and。



![](img/7442510f1c3446996399d9b1ffc7cf11_8.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_9.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_10.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_11.png)

Simple contents here okay。All right，So now what I did is that just like I did for a reason I took the great language game converted it to XM so that's what you get when you converted it to XM it's one way of doing it right so this would be guest target country the choices you know with this way of using the pural form here and the singular or the repeated elements to basically have an array of strings so this is what I get now it's getting back to a question you have should I use an attributes should I use an element right for example guest target you could also use attributes。

😊，What I'm giving to you here is a taste of what people do in practice。 So somehow the sample here。

Kinds of is some sort of I in there right So this feels like you put it as an attribute in there because it's kind of a bit special kind of the meta data of the of this game and the others I just put them as elements。

 but there is no right or wrong。 I could have put these as attributes。

 I could have put this one as elements that's fine too But once I have made this decision I can just define my schema in this way you see games。

😊，Which is a sequence of elements called game in the singular。

 you can repeat game right as many times as you want， unbound it。

Game is a complex type with the sequence guess target country， which are strings， choices。

 which is a complex type it said you see nest here。

 a complex type a sequence of choice unbounded of type strings we can have here certainly not unbounded I put oh I put unbounded I could have put4 in there right because in that case it's just four so I could have put Maxo acrosss4 that would have worked too here。

😊，And then the element dates here which you see uses the excess date and then my attributes after the sequence sample which is of type hex binary I'm using yet another type hex binary that basically has it's a very good textbook example this is a lexal value right if you write for8 f90 that's a lexal value it's basically a hex that isim sequence but once you validate it against hex binary in memory you're not going to have this anymore in memory you're going to have a sequence of bits or a sequence of bytes right once you have past this so this is the sort of things that you do with annotation so you understand the difference lexical value typed value。

😊，Who does。All right， very good， most of you。Very good， okay。

 this is absolutely fundamental to schema validation in general。Okay， and here I have。 I'm a geek。

 I love these things。😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_13.png)

You might have wondered when I showed you that JO Schema is JON XMl schema Xml。

 is there a schema that validates schemas and the answer is absolutely yes。

And this here it exists' somewhere on the internet， this is a schema that validates the schemas。

 it also means it validates itself， so this is the instant and the schema yeah you can look at it。

 it's basically a curiosity right it validates itself you can do the same thing for JSO schema J soundund so define a schema that validates the schemas right。

😊，Okay， but again， that's just the curiosity that I had to show that for completeness because it's cool。



![](img/7442510f1c3446996399d9b1ffc7cf11_15.png)

All right， which brings me to data frames， so you see I wasn't too long on X schema。

 it's much more complex than that， but I just wanted you to see the sort of things you can do with it and how you can add constraints to your documents。

Data frames who out of data frames。Wow， a lot of you who heard of data frames through pans。Oh wow。

 oh okay， awesome， who had a read through spark？Some of you， bless， okay。So now。

If you already know data frames from Ps， then today you are going to get a different formula approach to data frame but you will realize it's the same thing because I'm going to explain data frames in a completely different way。

In fact， I'm going to explain data frames。As a connection of valid Jasonson documents。

Under specific conditions。So let me explain what I mean with this。 So on the left here。

 you have a J soundund schema。

![](img/7442510f1c3446996399d9b1ffc7cf11_17.png)

That has three keys in there Integer string， Boan。 remember。

 and now maybe the puzzle starts adding up， this is closed， meaning that by default14 J sound。

 you don't allow extra properties。 So you know there will not be anything else than that。

 but they might be optional。

![](img/7442510f1c3446996399d9b1ffc7cf11_19.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_20.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_21.png)

So this is a JSO schema， imagine that now I have data and I have four documents like this。

 these are records in there， and ID here is an integer name is a string， living is a boan。😊。



![](img/7442510f1c3446996399d9b1ffc7cf11_23.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_24.png)

So now my question to you just to see if the pieces of the quaz added up。

If I give you the data frame representation on the right， turns out to be a table。

Could you reconstruct？The four JO documents that are valid against the schema on the left。

 and that would map to the table on the right， who would be able to do that？

We would not be able to do that。对。They don't see any race who doesn't know if they would be able to do that。

Who doesn't know if they know if they would be able to do that？Okay， so let's do it right。

 so let's take the first one。

![](img/7442510f1c3446996399d9b1ffc7cf11_26.png)

One Einstein force， so that would be adjacent object with ID colon one name Colon Einstein leaving Col force right who sees it now。



![](img/7442510f1c3446996399d9b1ffc7cf11_28.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_29.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_30.png)

Okay， so what I'm saying here is something really fundamental if we have a sequence of JSON documents that I might have in some text file。

 right JON lines for example， and these documents are successfully validated and annotate it against that schema that you see right here。

 then I can actually build a structure like this and look at that same data from a tabular perspective。

 who see it now。😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_32.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_33.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_34.png)

Okay， so this is why I'm saying that's a specific kind of data frame。😊。



![](img/7442510f1c3446996399d9b1ffc7cf11_36.png)

You can see a data frame as a sequence of JO object four of them here that are raied against a schema。

 and so this is why the intuition behind Js is that it gives you。



![](img/7442510f1c3446996399d9b1ffc7cf11_38.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_39.png)

A way to specify the schemema of the data frame itself。



![](img/7442510f1c3446996399d9b1ffc7cf11_41.png)

This is why we made it close by default。

![](img/7442510f1c3446996399d9b1ffc7cf11_43.png)

Because in a data frame you don't have any extra columns so if we had made it open allowing from extra properties we would no longer be able to map it to the data frame do you see it I can't remember who asked that question but this is the reason why we made it closed by default。



![](img/7442510f1c3446996399d9b1ffc7cf11_45.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_46.png)

Okay， here's another example more complicated because that is boring， it's a radiational table。

 you've already seen that in your bachelor， but the whole point of big data is that we break these rules right。

 so what if now name is a nested array of strings， an array of string。😊。



![](img/7442510f1c3446996399d9b1ffc7cf11_48.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_49.png)

You can also map this to a data frame in fact it would look like what you have on the right you see it basically the way you see it's a data frame but it's not a table basically it's not in the first normal form is you have lines that don't go all the way through right you see that here in that column you have multiple values in there multiple values in there this is my array of string here。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_51.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_52.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_53.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_54.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_55.png)

Who here sees what Jason documents validied against that schema would lead to that record。

 who sees it？😮。

![](img/7442510f1c3446996399d9b1ffc7cf11_57.png)

Wonderful。 So I D coma 1 coma name coma open square brackets， Albert Koma Einstein。

 low square brackets， coma leaving column force close objects， right， And you can do the same here。

 It's an array of just one string， an array of two string and so on。 Okay。

 so you see now how the schema as map to data frame schema as， and you can do this。

 Here's another example。

![](img/7442510f1c3446996399d9b1ffc7cf11_59.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_60.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_61.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_62.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_63.png)

Now， I have nested objects or nested objects。So。

![](img/7442510f1c3446996399d9b1ffc7cf11_65.png)

I basically would do it as a visualization by splitting my colon headers。

 I have name and below that I have first and last and now I have name do first and name do last here who sees the frog Jason documents here valid against the schema give me that。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_67.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_68.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_69.png)

Many of you wonderful right so you have ID1 name Col object first Col Albert Nice Colon Einstein close object leaving Col course right and you can do the same for the others This is again a data frame with the nested object right now you see the nested object in the headers that you have a line that doesn't go all the way through but in the headerss。



![](img/7442510f1c3446996399d9b1ffc7cf11_71.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_72.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_73.png)

More complicated， what about a fully nested table meaning an array of objects so here I have who is an array of objects with name and type and I can very nicely draw that in my data frame with who name and type plus I also have here these nested sequences。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_75.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_76.png)

Now it's not complicated。😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_78.png)

Who can rebuild the adjacent objects that would lead to that record？You can do it awesome。

Let me tell you how just for everybody else， you basically have ID colon one。

 who colon square brackets。😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_80.png)

Open an object， Na Albert type first， close object， commma， open another object， name Albert type。



![](img/7442510f1c3446996399d9b1ffc7cf11_82.png)

呃， last。

![](img/7442510f1c3446996399d9b1ffc7cf11_84.png)

Cose object。 Close array leaving。First， I don't know why I thought before saying that。

 but yes leaving voice。

![](img/7442510f1c3446996399d9b1ffc7cf11_86.png)

嗯。So this is it。 that's more complicated。 So you see， I can map all of these to data frames。😊。

And in fact， I can do that。Very often there's just a few constraints， for example。

 I'm not allowed to use item， I have to specify all of the type if I put item I can no longer map this to a data frame。

 I'm not allowed to open the objects I'm not allowed to say for example additional properties is true or close these source so it has to be closed so there's a few constraints like that but basically they map very well to each other right。

😊，Just so you see that imp mismatch， there's this other way that maps to the same visual。

 who sees that it also maps to that visual。 Now I have an object。

That has name that is an array of string type。 That is an array of strings。

Who sees that it maps to the same visual wonderful okay so of course the JO objects would look differently in fact that is something you see in practice we did it with sound data I think at some point the sound data was looking like this like that was the collisions of all the particles that were thought like this and we converted it to this because that is easier to understand from a data modeling perspective so this is the sort things you do see in practice this duality between these two representations。

😊，Okay。😊，Yep， that's it， so who agrees now data frames are collections of value adjacent objects。😊。

Okay， wonderful， that's what I wanted to show you。Why am I saying that？

Because once you have a data frame， there are more efficient ways to store it than J。

Which brings me to parquet and other syntaxes because there's other syntes out there。And in fact。

 one of the automatic things that I would like you to think of。

 if you download the adjacent data set from the internet that has a schema that looks like this end that can be converted to a data frame。

 meaning your entire collection with billions of objects can be converted to a data frame and you want to query it。

The first thing you should do。Is validated， annotated， converted to Bque or a format like that， why。

 because the space on disk is much smaller than the J style。

 So just because it was J doesn't mean you should keep it as Jason right and Bque will come back to that it's much more efficient because you have less to read from disk plus there's many optimizations you can do with that sort of of format If you read the dreel paper that's directly related to this right Drremel gives you a way of efficiently storing these things in binary form。



![](img/7442510f1c3446996399d9b1ffc7cf11_88.png)

Okay， which brings me to the formats。So basically， we are looking at lists of maps， right。

 what is the collection of objects， it's a list of maps。



![](img/7442510f1c3446996399d9b1ffc7cf11_90.png)

So basically， you can make a few high level distinctions when you do that sort of things。

 for example。

![](img/7442510f1c3446996399d9b1ffc7cf11_92.png)

You have cases in which your data set is flat。 It's in the first normal form， right。

 You don't have any nested data as opposed to nested data sets where you have these。



![](img/7442510f1c3446996399d9b1ffc7cf11_94.png)

We have vertical lines that don't go all the way， which is a sign that you have a data frame。



![](img/7442510f1c3446996399d9b1ffc7cf11_96.png)

That's not a table， so who sees that tables are a very particular type of data frame when it's in first normal form。

😊，Very good so flat nested right take a mental snapshot of the two this is a distinction some case in some cases it's all flat things are magically faster down when that happens and sometimes it's nested。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_98.png)

Now this is what the JasonO would look like， so what I would want you to see when you look at that kind of JasonO。

 if you look at the JON on the left， you should automatically see that it's flat right and if you look at the JasonO on the right you should see that it's nested who sees that。



![](img/7442510f1c3446996399d9b1ffc7cf11_100.png)

Right， very good， so there's no nest nest in the one on the left。Second distinction， homogeneous。

 heterogeneous， homogeneous on the left means that it's all the same columns and attributes everywhere。

 and they have the same types。 domain integrity， relational integrity on the right。

 it's heterogeneous， because you have missing values in here and you might have an extra property in there that wasn't in there。

 but that is not captured by data frames。 Data frames do not do that， right。

 They do not allow for extra properties。However， there is a recent feature that was added to some data frames。

 Snowflake indeed now I don't know if you saw the announcement of Sppo。

 but they also now support heterogeneity with the variant type because if you make a colon variant。

 you are in fact making it heterogeneous， meaning that you allow different types。

 so you see the heterogeneity is starting to make its way even into data frames。

I didn't check if Pomas has variant， does Poas have variants， anybody knows？

Will check would be an interesting thing to check， I'm sure one day they do it when there is demands。



![](img/7442510f1c3446996399d9b1ffc7cf11_102.png)

All right， and now this is the Jason who sees that the Jason on the top is homogeneous and the one at the bottom is heterogeneous。

Very good okay And finally， you can mix that。 So I have something on the left that's flattened homogene also known as a relational table in the first normal form。

 Well feeds the three constraints。 And on the right。

 you have something that breaks all of the rules that it can break right It's nested。

 It's heterogene。 It has extra missinging attributes。

 it has array arrays that are filled with different values， different types of values and so on。

 In fact on the right， you wouldn't even bother with a schema in there right It's just your data living its own life without a schema that's totally fine no sQl to do that。

 You don't have to have a schema。😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_104.png)

But the price to pay is if you don't have a schema， things will be a bit slower。

 right if you have a schema， then you make things faster because then you can use PAque or that kind of the formats。



![](img/7442510f1c3446996399d9b1ffc7cf11_106.png)

Okay， so now this is an example who sees that it's flat and homogeneous on the left and nested heterogeneous on the right。

Very good。 I really want you to see that spontaneously。 Now， this is Jason。

 You can do the same in X Ml works exactly in the same way。😊。



![](img/7442510f1c3446996399d9b1ffc7cf11_108.png)

And in fact， you have an enormous list of formats， the validation languages and so on， CSV。

 when that's for flat things， Yammer， I mentioned it a couple of weeks ago， data frames in Pos。

 Park and so on， Libbe's VM for machine learning， PAque works like magic to compress your valid J that looks like a data frame protocol B who heard of them。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_110.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_111.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_112.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_113.png)

Comes from Google Probs also works in the same way Avro and so on and so on and so on you can classify them on the high level。

 some of them you nestedness， some others don't some are a text format like XmL CSsV JN。

 some are binary like PAque protocol buffers， some require a schema。

 some do not require a schema right。

![](img/7442510f1c3446996399d9b1ffc7cf11_115.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_116.png)

So this is it and the good news I have for you is that I'm not even going to teach you the others。

 why because with everything I taught you now it's a walk in the park， you can go look at them。

 read the documentation， you will see you already have all the concepts to understand them right I taught you what I told you is really generic。



![](img/7442510f1c3446996399d9b1ffc7cf11_118.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_119.png)

Alright， so you just need to understand when you discover a new one ask yourself these three questions that is one of the starting points here's an example that's not part of the material I just want you to see it imagine you want to learn park it right you want to see the documentation and so on so you're going to find in the documentation or list of atomic types。



![](img/7442510f1c3446996399d9b1ffc7cf11_121.png)

And here hopefully you're going to have an aha moment because that list of atomic types is familiar Juliaian in 32 in 64 double decimal UTF8 inum a bit out of the ordinary binary。

😊，This is familiar， right。It has different names but it's the same thing is that going to values and hearing values all。

 but in fact it's the same it's almost the same language right so what I want you to see is that you already know that you just need to read the documentation but that's it you're already equipped with the knowledge。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_123.png)

What about the structural types it's just called differently arrays areor lists and objects are called maps。

 some of them also have a record type and the record just means that you can have keys that are not strings right this is another way of doing that。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_125.png)

Okay， that's protocol buffers you also see you also know all all these things already that's like a schema last name is a string first name is a string title that's a recurive structure and you see this required repeated optional works like the Mincurs maxocurs in Xm schema warmer sends that schema。

😊，RightAnd I didn't even teach it to you， I don't even need to teach it to you right because that looks exactly like any of the schemas we've seen just look up the documentation and you will see it would be very easy to understand so you can basically with prographs define a schema like this and you can plug it into C++ into Python into any languages and you can basically instantiate classes and then write your data to some binary format and read it back into your programming language that is just yet another schema validation technology that is binary instead of textual。

😊。

![](img/7442510f1c3446996399d9b1ffc7cf11_127.png)

All right， I think that's the last slide， so I want to conclude by basically saying that。



![](img/7442510f1c3446996399d9b1ffc7cf11_129.png)

By default in SQL insQL you don't have any schema， it's heterogeneous。

 you might do it in textual format， JON， X and so on。

 the moment you see a structure and you validate it if your schema is constrained enough。

 you basically get a data frame， then it's homogeneous again， and then you get high performance。



![](img/7442510f1c3446996399d9b1ffc7cf11_131.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_132.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_133.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_134.png)

Low memory footprints and so and so on， but the beauty of big data。



![](img/7442510f1c3446996399d9b1ffc7cf11_136.png)

And no sQL is that you can go from the one to the other。



![](img/7442510f1c3446996399d9b1ffc7cf11_138.png)

Bynaically on the fly， right so。It's not like SQL where you also you only have in SQL the right hand side。

 but not the lefthand side right and so many technologies like MongoDb give you the choice in MongoDb you can create a collection of objects we study it in a couple of weeks you don't need a schema but if you want a schema。

 you can have a schema and then it will then force the schema in the collection you can also create a schema later you first put the data in the collection。

 then build the schema and then validate it JasonO schema， for example and and thats it。Right。

So this concludes the data modeling impact。Any questions？行。O2 cents。



![](img/7442510f1c3446996399d9b1ffc7cf11_140.png)

Oh， I need to go back。This one Okay， so do we have to account for the order？



![](img/7442510f1c3446996399d9b1ffc7cf11_142.png)

In the name columns， for example。The order of the Kos know， but the order of the row。

 yes of the values yes， the order of the rose is important because they are in they ares in in Jason。

 it's an array of string but the last verse and Albert。I mean， so these are the same like。

The J sound definition here they second。So this one accounts for the order and the other one with arrays so here it's the order of the objects it accounts for the order of the name and type but this one I think I see no name and type don't have any order because they are key in objects you don't have any order said the string value。



![](img/7442510f1c3446996399d9b1ffc7cf11_144.png)

it。Can be。In here， can have a。Just给 my friend。First， last last first first so oh。

 no you would it has to be the way it's displayed it's first and then last and Albertber and then Einstein yeah。



![](img/7442510f1c3446996399d9b1ffc7cf11_146.png)

![](img/7442510f1c3446996399d9b1ffc7cf11_147.png)

It's just just a visual。 But the way you see that the other material is because it's an array。

 that's how you know。

![](img/7442510f1c3446996399d9b1ffc7cf11_149.png)

When you're having an ir raal。Okay。All right。It's perfect because we have enough time to start map Red with the little surprise that I have for you。



![](img/7442510f1c3446996399d9b1ffc7cf11_151.png)

So let me stop the recording here。