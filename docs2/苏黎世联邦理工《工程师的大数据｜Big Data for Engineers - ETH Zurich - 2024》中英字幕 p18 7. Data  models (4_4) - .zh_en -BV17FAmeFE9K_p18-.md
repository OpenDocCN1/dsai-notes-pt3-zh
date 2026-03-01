# 苏黎世联邦理工《工程师的大数据｜Big Data for Engineers - ETH Zurich - 2024》中英字幕 p18 7. Data  models (4_4) - .zh_en -BV17FAmeFE9K_p18-

Welcome everybody on Zoom， welcome everybody in the lecture hall。

 welcome everybody from the future today we have this lecture to finish on data models and then we'll move over to data frames and map produce。

😊，But before that， I have。One question。Or you。I mean。Which is this question。So this is a document。

 and I'm asking you if it is well formed only or valid only or well formed and valid or neither of those。

To you the document again。Is it well some donut， Is it very donuts。have the first vote coming in。

Right， there are many more people than votes， actually， so on Zoom， you know。

 you can also participate via E you up app right， everybody can participate。😊，Alright。

AWe had well formed only and well formed and varied。So it is well formed。 indeed， you look at it。

 That's a perfectly fine document There's the XML declaration。

 doc type E that corresponds to the top level element。 This is good。 That's an attribute。

 That's nested text， nested element and so on。 So it is indeed well formed。

 But can anybody tell me why it is not valid。😊，Why you cannot say that it is valid。Anybody on Zoom。

 maybe does anybody know why I cannot say that it varies。Exactly， we are missing as scheemo。

The validityT can only be assessed with a schema。 You should dont have a schema。

 and you cannot say anything about validityT。 You can only say that it's well phone。

So now this is XML。 I haven't shown you how the schemas look like。

 but you will see it's pretty similar to Jason。Okay， so remember。

 wellformness that you can always say， yes or no， it's well formed or it's not。

 It passes or it doesn't。 But E BT can only be assessed with a schema。

 and it even depends on the schema。 right， If you change the schema。

 then you might change also whether it is valid or not。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_1.png)

Okay， so now I'm going to show you X keyY， not all of it。

 I'm just showing to you the the basics so that you get the idea of it。😊，Soれ's。Look at it。

 Let's look at what。嗯。On the top of the screen I do it similar to what we did for Jason I have what is called a an instance document。

 This is a document that we know is wellform right If it's not well formed then we would have stopped anyway so it is well formed and now I'm asking the question is it valid against the schema that you have Bi because again you need a schema for valid so is it valid against the schema that you have below。

But let's first take a step back and look at what's going on here。The schema。

 what syntax is it in first？It's XM I， right， It's exactly the same idea as for Json schema。

 the Json schema was in the Json syntax。 The XM M schema is also in the XM M syntax。 Of course。

 it doesn't have to be， right， it could have been different。

 but it turns out that we use exactly the same syntax。 Now， what do we have in this syntax。

 we have specific elements that are the the the the elements that are used by the schema。

 It's a language， right， It's the XM M schema language。 It's a specific XM M syntax。

And all of the elements that we that we use in the schema and the attributes。

 they are pretty fine somewhere。 It's specified fully。

 and it's easy to spot them because they are the ones that start with access。

Right so you see excess elements， they are excess schema， access attribute and so on。

 We nicely put them in the name space。 The namespace。

 think of it like a Python module or a Java package of something， right。

 we didn't get too much into the details of those。 But basically we use we use these specific elements。

 of the XM schema specification in order to declare schema。 It was a bit the same in in J， right。

 you have， for example， in J schema。 You have the Json keys。

 There's the Json key that's called the required another one that's called properties。

 another one that's called additional properties。 These are also defined in the Json schema specification。

 So it's the same thing， right。😊，Okay。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_3.png)

So we have a schema。 There's always an excess schema do top level right That's the name is space。

 and then we declare here an element， the name of which is who and the type of which is string What does it mean that name here is the name of my element right there The name is F The type is string。

 What does it mean it means that this here must be a string is that the case。 Yes。

 that's the case right， This is a string right What we would not allow， for example。

 is nested elements in there， right because that wouldn't be a string。

 but here is' a string So this instance document is valid against that schema with with me。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_5.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_6.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_7.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_8.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_9.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_10.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_11.png)

Allright。Now， don't be scared。 The XM schema is a bit ver is a bit complex。

 But the nice thing is that when you actually do a schema， you， you often do it with oxygen。

 and oxygen has this autocomplets。 It automatically tells you what you can put where and so on。

 So this is often computer assisted when you define them， right， So it can be very variables。

 but there is no reason to be scared。😊，Here's another one。 Do you see the difference。

 What I change is the type。Now， the type is no longer a string。 It's integer， right。So the integer。

 is it an integer， Yes， because you， you need to to look at the lexal value when for 2，8，5，7。

 This is in the lexal space of integers。 right， you can pass that as an integer。 So this is fine。

 right， So the type is。😊，嗯An in。We agree。Okay。Now。Here's another one where we have nested structures。

 so here we have a child element last and a child element first。

 both of them are strings right so last and first would be strings。

 So you see the corresponding declarations Last is a string first is a string。

 but we need to embed them into a type so we say that we have this element person right there。

 which is a complex type and that complex type is made of a sequence of these two elements right。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_13.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_14.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_15.png)

The other is very important。If you don't specify otherwise， then it must appear once。

And that gives you。As that needs documents， okay。So what you see is that there's always the top level access schema elements in the schema。

 and then you declare your elements。 Some elements are the top level。

 and some elements are nested inside other elements。 And this is this is what it looks like。

 So the document that you see at the top is valid against the schema that you see。😊，At the bottom。

 And again， last and first have a simple type string， a atomic type。

 but person doesn't have a atomic type。 It has a complex type because it's made of a sequence of of elements。

In fact， if you're familiar with with Java or that this kind of languages or C++。

 it's a bit the same as distinguishing between the atomy types and the object types， right。

 So person would basically if you if you would， if you were to map it to Java。

 there are ways to map it to languages， person would be an object and less than first would just be strings。

Alright。Here's another one。 So the new thing in there is the meanoc and the max occurss。

 you can actually change the control the number of times that each one of these elements appears。

 So you see the two to four element has a meanoc of two in a max occurss of four。

 it means that it can occur two，3 or thought types right I it the case yes。

 it's three times there and three is between two and false so that's fine and0 or one has a meanoc of two of two and a max occurss of one it's there one so this is signed it's also in the belt right So this document with a repeating element is valid against that one because I the repetition and I control the number of times that it repeats It's very similar to what I told you that in Json schema you can also control the number of times that the number of members that you have in a JsonN array right so here you can control that number by the way。

 just to simplify now I'm dropping this excess schema blah blah。

 bla I just only show the relevant part of the schema to not overall。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_17.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_18.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_19.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_20.png)

WithMy slide， right， So this complex type here would be the complex type for who and would have to go inside on Adam and who。

 right， But I just showed a complex type。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_22.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_23.png)

Yeah。Okay， so now you know how to declare elements that have an atomic。😊，Type。

 you know how to declare elements that have。A list of children elements in in。嗯。Now。

 what about empty content， you have many ways of doing that。

 The easiest one is to just declare a complex type， which has a sequence。

 But then you don't put anything in there， right， So you see here。The sequence has two elements。

 here， it has two。 And here you just leave the sequence empty， and that's it。

 right So that's that's how you declare it。嗯。How do you support mixed content。

 This is something you cannot do in Jason， But in nextM you can actually have text that is intersperssed with elements。

 This is specifically useful for the publishing industry where you are going to have scientific papers and then in these papers。

 you tag sections， subsections， bold Italy and so on like these kind of things。

 So this is why you need that kind of mixed content。How do you do it， It's actually easy。

 You only need to put these mixed equals true attribute in here。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_25.png)

You see complex like mixed equals true。 and these these are the magic worlds that allow you to have some text in addition to the children elements。

 If you did not have mixed equals true， you would only have this alloweds the be。

 but without the extra text in there， right， So this is what the mixed equals true gives you right。

 If mixed is not true， like in here， you cannot have text。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_27.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_28.png)

Before or in between the elements， right， you must have directly the elements and nothing else。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_30.png)

O。呃。Now， you can also validate attributes。 And the way you do that is that when you define your complex type。

 you have the sequence of children elements less than first。 And right after sequence。

 you add an excess attribute。The name of which is birth and the type of which is date， right？😊。

So this， yes， there is a question about there Do we have the year。Itch books， maybe。Let are you。

Yeah you just on the one before， I was wondering why fo wasn't defined。In the mix type。

What is defined Oh who just the like general Yes， youre absolutely right。

 It's just that I'm only showing the complex side path that that's what I said it's just to keep the slides easy。

 You would normally you would need to have this excess schema access element name who and so on。

 and you see the complex type that's only that path that I'm showing here。

 Yeah that's the reason right， just because otherwise the slide would be enormous。Right。There一 go。

Thank you。Okay。呃。So yes， so the attributes。 Now you see the way you validate an attribute is similar to how you validate an element with a symbol type。

 you have this name in this type。 and that's it right， the name is above。 the type is date。

 How do you validate This is here the lexical value， it's just text right。

 But since you now say it it should be a date， then you check， I it a date， Yes。

 because you have dig dig dig dig dash digit digit dash dig digit。 So yes。

 that's a date And after the validation and annotation， this will be an actual date in the memory。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_32.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_33.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_34.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_35.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_36.png)

Now that this excess integer access string access date。

That part of this menu that I showed you earlier， right。

 It's the same list of types for X M M schema as it is in J Sound。

 as we would see in Jsonic and so on。 It's exactly the same list of of types。Okay。嗯。

Here's a concrete example。 Do you remember this great language game that I showed you in Jason。

 where people have to guess the language in which they hear a recording。嗯。

I just converted it to XM it's adjacent data set normally but I just built an XML equivalent where you have the games and then game game game game game and then inside you have guest target country choices I just try to do it in an equivalent way in XML there's not necessarily only one way of doing that there can be several but here that's one sensible way of doing that。

And you have on the right this schema don't be scared again， it's very ver。

 but actually if you look at the details it kind of makes sense right let's let's look at it together So you always have this excess schema。

 the top level， then you have these elements games that's the top level element that you have here。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_38.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_39.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_40.png)

Then it's a complex type with a sequence。 what we have inside is。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_42.png)

Game right， below games。 There is game in the singular。

 It's a very common pattern to have a pural form here。 and then a singular form for the repetition。

 So we say game and max occurs unbounded。 This is how I say I can have as many million games that I want in there。

 right， So this is unbounded。 Then if we look at game， It's a complex type with a sequence。

 What do we have inside， guest target country choices date， guest target， country choices date。

 right， So we list them。 guest target and country， These are just strings。

 You see choices that's a complex type。 So choices。

 we must say it's a complex type with a sequence nested in there。 It's again， this p form。

 singular form。😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_44.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_45.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_46.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_47.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_48.png)

Idea here。 Well have choices that is again， a complex type of sequence。 Here。

 We have choice of type string here， it's it's just a string。 Max occurs unbound it。 You see。

 you can have technically， it's 4。 I didn't do it， We could also add some constraints that say it's exactly for date is an excess date。

 So， yes， that taxes as a date and the attribute sample of type excess hex binary。

 this sequence of bytes。 but in base 16， right？ So you see this is in the lexical space of hex binary。

 So that's my schema。 Do we have a question on zoom， I think I saw。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_50.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_51.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_52.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_53.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_54.png)

Yes， there is a question asking， why is it complex。The it is asking why it is so complex。

 so complex means that you don't have just text， but you have nasty elements。Right， so for example。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_56.png)

This guest target country choice， these are all just strings， right， So this is called a simple type。

 The element has a simple type。 date also has a simple type here。

 but choices is complex because it has nest elements。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_58.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_59.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_60.png)

Game is complex because it has nasty elements。 Games is also complex because it has nasty elements。

 right， So simple means there's just text and you try to pass it as a specific atomic type。

 Complex means there are nasty elements。😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_62.png)

Right。Okay， does he answer your question， then I'll come to you。On Zoom。Yeah， yes， okay， correct。Yes。

 that's a good question。 So mixed equals true means that you mix text and elements。

 but at the same level。😊，So that's the reason here， there is in the text here。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_64.png)

But that text appears nicely in between element text right mixed would mean that between guess and targets。

 there would be something here in between there would be text in between there would be text in between there would be text and in between there would be text at the same level of the elements。

 then if there were text between these text， then game would be a mixed mixed type right？



![](img/ffe5337fdb30d4edd2958be52ed6a43f_66.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_67.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_68.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_69.png)

But here it's， again， it'， it's just not mixed because there are only elements as direct children。

 really， again， the direct children and not all the descendants， just the direct children。Right。

And this is the gekyba because I love these things。嗯。😊，The schema is itself an X document， right？😊。

And so you might ask yourself， can we also validate the XML schema against another XML schema right。

 what if now we consider that on the right this is an XM document and we try to build the schema or the schema on the right？

😊，Right and in fact， yes， the answer is absolutely yes。😊。

There is what is called the schema of schemas。 There is an X M S schema， and basically， it validates。

All the schema。 So all the， the schema documents seen as an instance validates against the schema of schema。

 But what's beautiful is that the schema of schema validate against itself。😊，This is beautiful。

 So this is the instance and the schema at the same time， right， you You can see if you look closer。

😊，嗯。You have。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_71.png)

an element that's called schema。 That's the one right there。 Then you have it's a complex type and。

 You have an element called element that is itself actually， the type of which is top level element。

 which is defined somewhere else。 Then you have the element complex type。

 You know that's the one that we saw a complex type right there。

 So there is there is a meta level of the schema of schemas。 So here it it's very theoretical。

 This is not really something you need to worry about。 It's more like a curiosity。 And by the way。

 the same goes in Json。 You can also have a JSson schema that validates all JSson schemas。

 you can also have a J sound schema that validates all J sound schema as。 So again。

 just for your curiosity。 I'm showing you that。😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_73.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_74.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_75.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_76.png)

Okay。But again， what do I want you to remember from XMM schema is that it works pretty much the same way as Json schema。

 the paradigm is slightly different because it's about elements and attributes rather than about objects and array race。

 But the idea is the same。 So now you can f in an XM document。

The text to be of a specific atomic type， you can f the elements to have a specific specific children in a specific order and with specific names and a specific repetition and so on and so on。

Okay， so there will be exercises to train you a little bit with that。

 We don't go really into the deep details because Xms schema can be very complex。

 The goal is just for you to understand what it is to validate the documents against the schema and that this is really about constraining the structure of the documents And typically when you have a schema like that。

 you don't just validate one documents。 you typically validate millions of documents right so you have a collection with a million documents and a single schema and you want every single document in that collection to be valid against the schema right this is the idea。

对。All right， so now I'm going to link it to data frames now you can forget about XmL because this is really the J part that I'm linking to data frames。

😊，I think I already asked you like who knows Poas data phrase， already heard of that。 Okay。

 so this is what I'm now linking it to but now you you're going to have a theoretical understanding。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_78.png)

It to be。They exp right there。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_80.png)

De。So what I want to show you。Is that a data frame， in fact。

Is nothing else than a collection of valid Jason documents。That's what it is about。

 So I'm going to show you。On the left， what do we have， it's a J sound schema。

What we accept with that schema is JO objects that have three optional keys。

 ID name and leaving ID must be associated with some integer like 42 name must be associated with any string。

And living must be associated with either two offers a bullan。 So this is the JOund schema。

 You can use that J soundund schema to validate one JON document。

But what if you validate four JO documents， Imagine you have four JO documents， they all have an ID。

 name and leaving。And it fulfills these types。Do you see that in fact what you see on the right is pretty much that but in a visual way right on the right I have it's actually a data frame。

 it has four records in the first record the ID is one。

 the name is Einstein living is false in the second record the ID is two the name is meza canid living is false and so on has four equals records。

😊，U。Who here？Would be able if I give you a paper and a pen or even on your computer。

To convert what you have on the right。To score J objects。

That correspond to the same data for JSON objects that would be varied against the JSO who would be able to do that。

Okay， most of you， very good。It would just be， for example， let's do the first one。

 it would be Curly Brace， ID Colon one， coma name Colin Einstein， coma leaving Colon first。

 close Curly Bra right and you can do it for all the four。😊，So what do we learn here。

 We learned that。For specific JO schemas that's constrained the structure in a certain way。

Once we have validated JSO documents against that schema。

 we are able to visualize it at something that kind of looks like a table in fact here it's exactly a table right so these small documents that we would validate corresponds to that table。

 this is what we call a data frame。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_82.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_83.png)

I will explain why data frame and not table because it's actually more general than a table。

 as we will shortly see here's why it's more general than a table。Now。

 imagine that I slightly modify my schema。😊，And the name now is an array of strings。Right。

 so this is the J sound that corresponds to that。 It's relatively easy to to， to pass。

 So name is a sequence of strings。 Do you see that now。

 I would still be able to draw it nicely as something that looks a bit like a table。😊，Imagine here。

 for example， that in my first J document ID is one name is an array of two strings。

 so that would be name square bracket open Albert Comma， Einstein close square bracket。

And then leaving course here we have an array of one string here we have again。

 an array of two strings。 and here we have again， one string。

Who would be able to give me the j for that？ you should do it as an exact size if you if you if you if you were cannot do it visually。

 but this is the idea that this is one JO document， a second JO document。

 a self Json document and a fourth Json document， but nicely visualized like this。

 Now you see it's not exactly a table right because you see the horizontal line here is only here doesn't go the whole way。

 So technically， it's no longer a relational table right So this is what we call a data frame。

 And you can see that every column corresponds to a key I would just be an integer name would be an array of strings。

 So here you you can have several and living would be a boolean。

 Is there a question of the zoom chat be possible。So there is a question on the chat saying that。

 would it possible to accept a string or an array。In JSM yes， so with S union types。

 it's also true in JSOM schema it's also true in XML so you can absolutely build a schema that is flexible and that accepts at the same place a string or rate this is entirely possible。

But when that's the case。You can no longer visualize it like this in a general way right so there are a few constraints on the schema to be able to map it to a data frame in that way I will tell you a bit later but one of these constraints is that you cannot have unions of types it really must be a specific type for every column for every key and again in an array you must have a specific type and so on right so you are not allowed to use item。

 for example you cannot say an array of items it has to be an array of strings an array of integers and array of dates。

Does that answer your question？Yes， yes。Okay， so this is the case of nested array and here you see the vertical list of cells。

😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_85.png)

Now， nested objects。Nested objects I would have， for example， name that is now an object。

 first is a string and last is a string。The way we map it here is that it almost looks like your table right So this is ID D1 name first Albert Les Einstein leaving course。

 but the way we actually do it is that in the headers we draw these lines。

 but then in this header here I have a horizontal line here and then first here last here So this is nested thir is nested in name last is nested in name right and then living is again farbus who would be able to give me the fall Jasonson objects here。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_87.png)

Okay， if you can't then think about it and try to do it as an exercise because this is again a visualization of four JSO objects。

 but again this is a data frame。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_89.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_90.png)

Then we have an array of objects。 Remember that the array of objects that's for nested tables right。

 So how can we have nested tables in in this way， who is an array and every object in that array must have a key name that is a string and a type that is a string。

 it's optional， of course， But if the key are there， they be they must be strings。

And now you've see in the data frame instance what we have the column ID is E， the colon living。

 this is easy right these are all integral these are all booleans and now in who I have an nested header name and an nested header type and I also have this horizontal lines that go don't go the whole way right so it means that here I have an array of two objects the first object has name Albert's type first and then the second object in that array has the name Einstein type last right so it's an array of two object here it's an array of one object here it's an array of two object and here it's an array of one object。

😊，Okay， for whom is that there。Right and now you see these are in fact nesty table。

 this is a nest table， this is a nesty table， this is a nesty table， this is a nest table。😊。

But previously， when we had nested table， I put the headers of the nested table every time。

But here these are nest table that all have the same schema， so this is why we put it here。

 the headers instead。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_92.png)

Okay， so again， as an exercise， try to figure out the four J documents that would correspond to this data frame instance。

 a very good， very good exercise。嘅。Now let me try to tell you the sort of constraints that we have on the JSON schema for these two work。

 because otherwise it doesn't always work。The first con is that you must have closed object types。

You cannot have a schema that accepts unknown keys。

 right it's these additional properties of JO schema。

 so you must have a schema that doesn't allow for extra columns or extra keys。 otherwise。

 you can no longer draw it such so nicely。嗯。Optional keys are fine right then you just leave the cellMT or you just put anner in there。

 but basically it would work。嗯。You must also have only。What's called an instantiable type。

And I we explain what that means。嗯。It means that。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_94.png)

Here。I have integer， I have string， I have string， I have gus。

 these are instantangable types right you can all have directly these values that are of these types。

😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_96.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_97.png)

What you cannot not have。Our。Two generic types。 for example， you cannot just say item。

 item is too generic。 an item could be an integer。 It could be a string。 It could be a date。

 It is too generic。So this really requires that you put very specific atomic types from the menu in there。

Right。😊，So this this is the idea and basically it means that there is really a mapping between the notion of a schema algorithm a data frame and JE you can actually use JE。

To describe a data frameram in this way。嗯。Now there are schema languages specific to data frames。

 but it's not really standardized， we' see that in Sp there is a specific way of defining a data frame schema。

 there is another one in pretty much any library in Pos and so on。

 so there is not really a specification or anything it's really highly dependent on the library that you are using。

Okay， who's with me on that？Who has now this intuition？That。

A collection of many valid Jason documents。Can be drawn in this way， who has this intuition？

Very good so now when you see a data frame think of it as a collection of valid JSN document this is really what it is and a data frame is more general than a relational table because we allow for more nested nest right this wouldn't be a relational table right because the headers are not relational headers you have these horizontal lines that don't go the whole way so it is more generic than that and this is a data frame。

😊，Okay。We'll query them later， I' come back to that with Apache Sp， we'll see how to query them。

 but this is the connection I wanted to make。😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_99.png)

Now， let's talk about formats。😡。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_101.png)

嗯。When we did with trees and it doesn't matter if it's XML， if it's JON， if it's data frames。

 if it's whatever it is。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_103.png)

In general， from an abstract perspective， what we have is a list of maps。A collection of documents。

 The collection is a list， right， The collection of things can be seen as a list of things。

 And every document inside that is a map， right， We saw that a J object is a map。

 It maps every key to a value。 So from an abstract aspect here。

 Any data sets that you download from the Internet is going to be a list of maps。😊。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_105.png)

Now let's try to understand what these data sets look like and how we can classify them。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_107.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_108.png)

A first。Way to classify them is to distinguish between flats data sets and nested data sets。

 That shouldn't be new to you， writer We've already discussed that before in a flat data set。

 you don't have any nested structures。 Every single cell that you have in there is atomic。

 You can have strings dates integers and so on。 Every single one of these 12 cells is an atomic value。

 Nothing nested。 We say that it's flat。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_110.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_111.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_112.png)

We can have nested data sets that you can draw like this。 Again。

 I could also put this name living up there together with people and draw it in that way， right。

 This is again， then even more structured。 But basically here， we have nested。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_114.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_115.png)

Nest， right， So this is a nasty data set。In terms of J。

 a flat data set just means that all the values that you have in your object are atomic。

 but in a nested JO data set you can have nested objects， nested arrays。

 nested arrays of objects and so on， so the first distinction is flat versus nested。

So this is what it looks like in J on the left you have a flat JON data set。On the right。

 you have a nested Json data set because you can see that people is an array of objects and it has further structure。

What's very important is that this distinction。Its the same whether you look at this visualization or whether you look at this in the J syntax。

 you have exactly the same visualization， this ear is the same thing right this is the syntax。

 this is the visualization。Here's another one， it's another way to distinguish。

 we distinguish between homogeneous。And heterogeneous data sets in a homogeneous data sets。

 all of the records look alike in a heterogeneous data set， you can have missing missing keys。

 You can have additional keys that you don't have in the schema。

 you can have also types that don't even match each other。

 Like you can have an integer in the date in the same color and so on。 This is heterogeneous。😊。

So this is the visualized version， visualized version of heterogeneous homogeneous。

 this is the syntax distinction you see on the top left you have a homogeneous data set has exactly the same keys everywhere and on the bottom right you have a heterogeneous data set because you have missing keys。

 additional keys and you could even have different types for the same key across the collection。Okay。

 so that's homogeneous， heterogeneous。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_117.png)

And then you can。Cumulate the two。 so you can have a flat and homogeneous data set。

 That's actually a relational table。And on the right。

 you have a nested heterogeneous data set here you have everything， you have nested arrays。

 you you have missing values， so you can see here there is a missing value here。

 there is an additional value right there here it's also heterogeneous because in the same cell you have a table and a string right so this is heterogeneous because these are two different it's basically JO an array that contains an object and a string。

😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_119.png)

So nested and heterogeneous。 So this is the visualization of flat and homogeneous versus nested and heterogeneous。

 but again， you can also look at it in Jason where you have on the top left a flat homogeneous。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_121.png)

Jason data set。 and the， on the right， you have a nested heterogeneous。Data set。

 so you can see here what I was saying earlier。You have an array that has an object and a string。

 right， So this is heterogeneous。Okay， so this is how you look at these data sets。嗯。

What I want to say here is that it doesn't matter if it's Jason。If it's X M L。

 it's exactly the same idea of these nestededs， not nested， homogeneous， heterogeneous。

 It works in exactly the same way。 and in fact。There is a whole universe of schema technologies and formats and so on that more or less follow these principles。

 You have some are allow forness， some allow for heterogeneity， some don't。So there are many， many。

 many。 So Jason and X XML we covered Yael， I only showed it to you during the syntax lecture。 CV。

 you know about it。 This only does stable， so it doesn't CV， for example。

 doesn't do nested nest data frames cover nested nest。

 but they do not cover heterogeneity because otherwise you run into issues trying to draw them Libs VM is for machine learning。

 This is also a structured one Avropa protocol buffers。

 This is by Google who heard about protocol buffers。It's by Google。

 It's basically a binary version of Jason and XML。So but it's exactly the same idea。

 So you see what I try to do in this lecture about data models is to teach to you in a generic way。

 the notion of atomic types the notion of schemas and so on I did use X and J you know specifically to show you how it looks like but you really need to take a step back and understand that this is not particularly tied to X of J right it might even be that in 10 years there is another one that takes over。

 but the principles are there you have a collection of documents that you can validate against schema。

书。If you look now at the formats themselves， if you want to classify them。

 so here that was about the classification of data sets， right。

 but how we classify now the formats themselves。😊，A format means think of it as a file extension right PDF is a format open Office spreadsheets that's a format right a text5 dot TxD that's a format right so think of it that way dot Jason is a format dot XM is a format right so data format。

Now we can classify these formats。😊，Nested flat。CSV， for example， is a flat format。 CSV。

 you cannot have nested structures。 Jason and XM L are nested formats， right。

 Protocol Bels is a nested format。 data frames。 that's also nested， Yaml。 That's nested and so on。

 right， So nested versus flat， whether it a lose or not for nested nest。

The second distinction between formats is is it a text format or is it a binary format？X。

 M M and Jason are text formats， right， You can open it in a text editor and see it as text。 In fact。

 we spent an entire week looking at them as text。 Yamer is also text。 CSV is also text。😊。

Protocol buffers is not text， that's binary if I give you a protocol buffer file。

 you can not open it in the text editor right that's fully binary， highly compressed and encoded。

Pque is binary， Avro is binary and so on， right？😊，So this is the second way you can distinguish。

W is it important？😮，It's because typically。A binary format will be more efficient than a text format。

Which is the reason why a good practice when you download a data set from the Innet， for example。

 I don't know from the website of the federal Office of Statistics。

 you can download aON or X and so on， but if you want to query it to query that data repeatedly。

And in turns out to be valid against some schema， then it's usually a very good idea to con that data。

To a binaryary format。So a very common thing to do is to take， for example。

 a data set like the great language game。😊，You don't believe us Jason。

And then you basically use a tool that converts it to Bque， for example。Why would you do that？😮。

You would do that because the size of the file would be much smaller if you convert the same data from adjacent format to a packet format。

 the size in bytes in kilobytes in megabytes will be smaller and a lot smaller so you save space it also means you can squeeze more on your hard drive you can have more data on your hard drive。

 but also。It means that you can read more data every seconds， right because again， the bottom leg。

 we will see when you look at mapreuce， the problem we solve with map Reduce and Sp is that we cannot read data fast enough。

But if you save your data in a format that is smaller。

 then it means you can read more information every second because you compress your data。

 So this is why these binary formats are， in fact， very， very useful。😊。

But they are very easy to learn because you know what the collection of documents is。 You know。

 Jason， you know the distinction between atomic types and complex types。

 arrays and objects and so on。 You know that a data frame is a collection of valid。Jason documents。

 So you basically know Paque。 I did not even teach you Paque。

 but you know Paque because Paque is just a binary format for storing connections of valid Jason documents。

 In fact， collections of data frames， sorry data frames。Okay。

 so that's the second distinction text versus binary。

 the third distinction is whether or not they require a schema， let's look at that。

Jason and XML do not require a schema， you can， but you're not obliged to if you don't want any schema。

 you can absolutely still use Jason and XMl Yamer alone Su dozen't。CV。

Kind of require a schema because you need your columns， but on the other hand。

 CSV is not going to complain if you have mismatching types right it's just going to be hard to open in a spreadsheets software maybe but so CSV is kind of in between protocol buffers do require a schema。

Pque does require a schema as well。 That's how we can actually efficiently store it in binary A also need a schema and so on。

 protocol buffer， in fact。It's kind of like bucket。Right， it's。

 it's like the Google version of of packet。 It's a bit more complex than that。 but basically。

 protocol buffer is also a binary format that stores collections of valid records just like Buck。

All right， so you see sometimes the schema is required， sometimes it is optional in the format。

 but there is a a common feature is that usually when the format is binary。

 it does require a schema because it doesn't really make sense to stock something in a binary format。

 if you don't have a schema， the whole point of the binary format is that with a schema it can compress it can compress the whole thing so that usually goes hand in hand to require the schema in a binary format。

Now， what I'm showing to you here is not material for cost。

 I just want to show you that now that we've covered a lot of that。

 this type system for JSO JSON Schema X Sche up。If now you were to use one of these formats and you want to understand how it works and so on。

 you will look at the documentation， where I want you to see is that it's going to be easy when you do it。

 it's going to be very easy and to show you how easy it's going to be。

 this is what you'd find in the packet documentation， you look at the packet documentation。

 what other types。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_123.png)

Now， of course， you're going to cities these are names that are weird right。

 so in 96 in 64 white we didn't cover them。 but if you look closer。

 you will actually see that this menu of Pque is actually pretty similar to what we've seen， right。

 Look， you have Booles。 you have numbers。😊，They are different types。

 but these are still number types。 you have double， you have decces strings， you have UTF H。

 So this is just the encoding right， but this is a string type binary， you also have a binary type。

 you have a date type and so on。 So if you don't focus on the exact names of the types and on the exactly stuff types and you just look at it from far away。

 This is actually not new。😊，It's just the list of atomic types and the categories of atomic types are exactly what you would expect。

 You can look at any other like protocol buffers and so on Avro it's going to be the same。

 So of course you would have to learn the exact types when you use it and look at the documentation。

 but the idea is there。😊，If you look at the structure， these are the atomic types of ta。

 what about the structural types？Surprise surprise， it has least 10 maps。 it calls them least 10 map。

 But look， at least it's just an array。 a map is just an object。 So that again， makes it easy。

Why do they not have8 and 16 bits。 I actually don't know。

 This is exactly the part that I told you look at the documentation， see what they have。

 maybe they have a maybe maybe they are there。 and I just didn't find them。 Maybe they are not there。

 but that's just what you have。But the answer to your question is basically I don't know if I summarize。

行。Okay。Again， this is like what I told you with Swiss German， right？

 It's like imagined that I just told you a Tuli Titch。 and then you go to Bail。

 and then they speak Bail dch It's slightly different。 It's slightly different names that， in fact。

 you can still understand what's going on。 So it's like a different dialect。And here again。

 these1 maps， but again， these are just like arrays and maps sound just like objects。

 So Parque basically has the same type system or a very similar type system to JON and JSO and JO schema and so on。

 and this is the reason why you can create schema as well and you can also store data that is valid against that schema just going to be binary。

😊，This is yet another example， this is a schema， but in protocol beels。😊，But here too。

 you shouldn't be scared of anything because even though the exact syntax would be slightly different。

 let's say that's bandage， but if you look at the details， what do we have here， we have a person。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_125.png)

That is basically a complex type， like a JO object or a complex type in XM schema。 It has four keys。

 sorry for his last name first name title and bus these are four key and they have types。

 Last name has type string first name has type string title thats again。

 a complex type that would be defined somewhere else。

 bus is a person that's again a complex type defined somewhere else。

 And here you have this required that just like the exclamation Mac in JSO right it's the or the required in JO schema you have the repeated repeated would be either like a Json array or it would be like the max O unbounded。



![](img/ffe5337fdb30d4edd2958be52ed6a43f_127.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_128.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_129.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_130.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_131.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_132.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_133.png)

In XML schema， optional would be thats the default in Json， right， that it's optional in XML schema。

 that would be min curves equals 0。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_135.png)

![](img/ffe5337fdb30d4edd2958be52ed6a43f_136.png)

But basically， you have exactly the same features， it just looks different， it's a different syntax。

But the idea and the way it works is exactly the same。

 so now if you were to have projects that you work on and you need to use protocol buffers。

 that would be very， very easy， right？嗯。So this is the idea that some have schemas and are homogeneous。

 especially the binary formats and some are heterogeneous。

 you deserve the break because now I talk so much that we are slightly over。

 but I'm done with the part on data models and validation and data frames。

 I'll give you the full break So I will see you at 19 past past 9 to make sure you have the food rests and we'll do mapreuce Thank you。

😊。

![](img/ffe5337fdb30d4edd2958be52ed6a43f_138.png)

Yeah。