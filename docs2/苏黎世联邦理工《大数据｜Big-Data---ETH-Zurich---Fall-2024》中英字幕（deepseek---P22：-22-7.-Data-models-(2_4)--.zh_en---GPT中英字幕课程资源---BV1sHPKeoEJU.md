# 苏黎世联邦理工《大数据｜Big Data - ETH Zurich - Fall 2024》中英字幕（deepseek - P22：-22-7. Data models (2_4) -.zh_en - GPT中英字幕课程资源 - BV1sHPKeoEJU

So welcome back everybody so we were looking at this and I was asking who of you see the tree in there who will see the tree so it seems to be a bit half half so some of you actually see it and some others do not do not actually see it so the idea is that we can draw the tree together。

😊，The idea is that that's an object， right， You agree this is an object。

So we can put this object or a proxy for that object as a node。Indutry。

How many keys does that object have？You can directly say it。2， yes， twos， school and bar。

F is associated with the value true， that's an atomic value and bar is associated with an array you recognize the square brackets。

 right？😊，And in that array， how many ML do we have？😊，2， yes， indeed。 The first element is an object。

 And the second element is a nu， right， So you see in these are yellow rectangles。

 I'm putting the atomic values， So strings， nerves， bulloles and numbers。

 I'm putting the objects in purple and the arrays in a red， right， So now my object。

 How many key does it have。😊，Women。B bar who。So this is a tree， you agree， right？😊，So of course。

 biologists don't see trees in the same way， mathematicians don't see trees in the same way。

 the difference between mathematicians and computer scientists is that for a mathematician。

 a tree doesn't have a root， it's just subgraph that doesnt have some graph that doesn't have any cycles undirected。

But computer scientists consider that it's a rooted tree， right So we just say tree。

 but it's a root tree。 So it means that we do have a root here and that's directedarrow rows that go to the children。

 So this is a tree structure Now a comment the keys here are not nodes。

 these are just labels on the edges。 This is a node。

 all the rectangles are my nodes right And these little circles here。

 ellipses are basically just labeling the rows that come from an object to one of its value right Every time you have an object。

 you label the the the arrows that come from here to here。 for whom is that clear。



![](img/17f4d5d915cb83e727719ecd4bbdff22_1.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_2.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_3.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_4.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_5.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_6.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_7.png)

Who is able to do it for any Jason value I give you， You can draw a tree。Okay， you'll have exercises。

 but that would be easy once you've done it once or twice it's something that becomes very intuitive。

 but of course。The goal is not that you draw them。 The goal is that if I show you that the thing on the left。

 you immediately see the tree in your mind right So who。Let me ask this question， carefully。

Who answeredsled， no， I don't see the tree previously？😮，But now， sees it。Okay。

 so I have a good conversion rates。So that's my goal， I want you to see a tree。



![](img/17f4d5d915cb83e727719ecd4bbdff22_9.png)

Now this is another example and now I did the same slide that I had with CSV in the table now I have it with Jason in the table now you have a Jason document here Jason object you'll see later why I call that document but Jason object and that corresponds to the tree above so every time you see。

😊，The syntax of Jason， you should see in your head the tree。Now。

 let me introduce two verbs that are related to this ecosystem。These vers are parks and serialized。

Probably already helped them。 but this is basically what you call the two directions。



![](img/17f4d5d915cb83e727719ecd4bbdff22_11.png)

Basically， what happens is that you have this seat somewhere on your drive on HGFSS3 or whatever。😡。



![](img/17f4d5d915cb83e727719ecd4bbdff22_13.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_14.png)

What you have is a library， a JO library or an XMl library。



![](img/17f4d5d915cb83e727719ecd4bbdff22_16.png)

And what it does is that it uses some grammar， you know， context free grammar tool。



![](img/17f4d5d915cb83e727719ecd4bbdff22_18.png)

That is able to pass that and then it builds this in memory it means that what you see here is actually the inmemory representation that is actually built in the realm when you pass this these are memory pointers that you have here and these are for example Java objects that that are basically going to be here this is really what you have in memory So the idea the very important lesson is that even though on this you have JO or Xml you don't have JO or XMl in memory as text you have then as the three representation this is absolutely fundamental to understand。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_20.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_21.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_22.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_23.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_24.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_25.png)

Right， syntax is only syntax。

![](img/17f4d5d915cb83e727719ecd4bbdff22_27.png)

So this is called boxing and this is called serializing when you have the memory representation。

 you might for example， modify it or have some interaction with it and so on。

 when you write it down to this it is called serializing so boxing serializing。😊。



![](img/17f4d5d915cb83e727719ecd4bbdff22_29.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_30.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_31.png)

Okay。😊，And a misconception， this is something that people have on XMM is that XMM is variables and so it's inefficient。

 no， because you never process the XMM text directly。

 you first pass it into memory as a tree and then you work on the tree in memory。😊，Okay。

 so packing serialerilizing now now this is Xml right so this would be some Xml document and you can see if you see the correspondence between the two you have the element A right here that corresponds to this that has D and E as D and C as children D has an attributes that I put like this here in red then C has this is that's text then there is an element B and then there is the the dot and the element B has itself text inside right and then in Xml what we do is we add an extra root node that called the document notes will come back to that Who sees that this when you pack it。



![](img/17f4d5d915cb83e727719ecd4bbdff22_33.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_34.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_35.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_36.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_37.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_38.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_39.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_40.png)

To memory， you get that tree， Who sees that。Okay， and so again， the other side is serialerizing。😊。



![](img/17f4d5d915cb83e727719ecd4bbdff22_42.png)

Now， do you see that I don't care if it's X or adjacent， that's the same thing。

 We just have syntax that gets passed into memory as a tree right and the considerations for using the one or the other are based on the use case。

 but this is really the one and same thing， right。

![](img/17f4d5d915cb83e727719ecd4bbdff22_44.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_45.png)

Okay。😊，嗯。There is a bit of a difference in the paradigm between the two and that Ill try to regularly make the comparison。

 is that when you have this JO in memory representations。



![](img/17f4d5d915cb83e727719ecd4bbdff22_47.png)

The object keys are on the edges， on the arrows right there， right there。



![](img/17f4d5d915cb83e727719ecd4bbdff22_49.png)

But in X M L， they are not on the edges。

![](img/17f4d5d915cb83e727719ecd4bbdff22_51.png)

They are on the notess。On the vertices。In other terms， in other words， an element node。

 well see that this is an element node knows how it's called。

 so this node knows that it's called who。

![](img/17f4d5d915cb83e727719ecd4bbdff22_53.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_54.png)

This one knows that it's called bar， however， this atomic value here does not know that it's called bar bar is really just in the relationship between the two。

 but imagine that this is the number 42 here。

![](img/17f4d5d915cb83e727719ecd4bbdff22_56.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_57.png)

F2 is just42 right it doesn't know that it's called bar by somebody and somebody else might call it fu bar。

 but this is just the number of42 and it doesn't have its name right there but who is that clear？



![](img/17f4d5d915cb83e727719ecd4bbdff22_59.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_60.png)

So labors on the edges for J， labors on the nodes for XL。

 This is one of the differences in the models。Okay， there is a question， yes。

So could you go back a slide please so why should the object not know the edge label I mean I think it's just as arbitrary as knowing its' parent right？

Both are okay both are okay， it's just that traditionally in J we tend to look at it like this whether it's kind of you could almost call it a cultural thing with the JN ecosystem that the model has the labels on the edges and an on XM it has the models on the nodes。

 you could of course if you want it， you could imagine a model in J that puts the labels on the nodes。

It's just that you wouldn't be in a majority， basically most of the people would put them on the edges。

 likewise in XmL， you could come up with a model that also puts the labels on the edges， but again。

 you wouldn't be in a majority。Yeah， I was。 I meant something slightly different。

 Oh Sorry you said in Jason， the， you know， the nodes don't know their parents because， you know。

 the， the labels are on the edges。 But， I mean， in this kind of intuition。

 why should you not know the edge label so let me explain that more precisely。嗯。😊。

I'm already getting into details here。

![](img/17f4d5d915cb83e727719ecd4bbdff22_62.png)

So theI意思。嗯。

![](img/17f4d5d915cb83e727719ecd4bbdff22_64.png)

When you define a model， this one or this one。You basically say what nodes you have so here for example。

 you have object nodes， you have number nodes and so on in XMM you have element nodes。

 you have text nodes and so on。

![](img/17f4d5d915cb83e727719ecd4bbdff22_66.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_67.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_68.png)

The next thing you do when you define these nodes is that you say what properties they have。

 it's a property， for example， a property of that node is that its name is full， right？



![](img/17f4d5d915cb83e727719ecd4bbdff22_70.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_71.png)

Here a property of that node might be that it's an object right but bar is the property of the edge。

 it's not a property of the node here so formally it's a property of the edge the other thing that you define and now I'm coming to what I mean when I say doesn't know it's called an accessor an accessor is like a formal API it's a mathematical API it's not you cannot call it with a computer it's just a mathematical function an accessor for example you have an accessor here on an element node that returns the name of that element so the reason I'm saying that this node knows how it's called is because it has an accessor that is able to given that you have this stored in a variable you can access using the accessor the name。



![](img/17f4d5d915cb83e727719ecd4bbdff22_73.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_74.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_75.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_76.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_77.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_78.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_79.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_80.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_81.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_82.png)

What happens here？In these JON models is that if you have these in your hands。

 like this is what you have， you don't have any way of going backwards because this is anro that point here when youre here。

 you don't have any way of accessing any property or accessor that would bring you back here。😡。



![](img/17f4d5d915cb83e727719ecd4bbdff22_84.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_85.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_86.png)

RightIn fact， these values here the atomic values they don't have any physical identity42 is just42 you might have42 here and42 here it's meant logically but there is no notion of physical identity in there it's already advanced what I'm telling you but does it make sense。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_88.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_89.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_90.png)

Yeah， thanks。 Yeah， Oh， Oh， yes， you here you are。 Yeah， that's the idea。

 So it's really based whenever you have a model， in fact。

 that's the basic of what you design a query language。😊。



![](img/17f4d5d915cb83e727719ecd4bbdff22_92.png)

You have to be very clean about it the first thing you do when you design a query language is you define your data model。

 in that case， what are your node。How are they connected to each other？

What are the properties of the nodes， What are the accessor of the nodes and the one of the things the accessor can give you is the children。

 for example。

![](img/17f4d5d915cb83e727719ecd4bbdff22_94.png)

You could have here on that object an accessor that takes one argument， the name of the key。

 and you can call that accessor with who and is going to return this， right， That's again。

 like a mathematical or API that allows you to navigate the model。

 That is the first layer on top of which you can then build very powerful query language。

 functional and declar。

![](img/17f4d5d915cb83e727719ecd4bbdff22_96.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_97.png)

Okay。😊，Yes， so you also on the Jason side， you have oriented edgeggs and on XML side there are they are not oriented is that like Oh no no。

 I should add it it it should be oriented。It should be oriented in both directions that need be more precise。

 this is a very good question， so in XmL。

![](img/17f4d5d915cb83e727719ecd4bbdff22_99.png)

When you are here。You can you have an accessor that's called children。



![](img/17f4d5d915cb83e727719ecd4bbdff22_101.png)

Right and the children accessor gives you the risk of all the children， so this one。

 this one and so on， so knowing that node with the accessor， you can go here and you can go here。



![](img/17f4d5d915cb83e727719ecd4bbdff22_103.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_104.png)

In XML， you also have a parent accessor， so it means that when you are here。

 if you invoke the parent accessor， you can go back here。



![](img/17f4d5d915cb83e727719ecd4bbdff22_106.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_107.png)

It's very common。 So that's probably what I had in mind when I didn't put the row in here is that it is bi directionional。

 typically in XML， you can go。

![](img/17f4d5d915cb83e727719ecd4bbdff22_109.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_110.png)

Up and down in Jason， typically， you only go down， but there is no concept of of getting back up。

 I'm not saying everybody would do it。 You can always invent models or systems in which you add the notion of the parent。



![](img/17f4d5d915cb83e727719ecd4bbdff22_112.png)

The problem is that basically you have to give you the intuition behind this。

When you introduce the concept of the parents， you have to deal with physical identity。

You don't have to do it if you don't have the concept of a parent， for example， if you have Co2。

 that's just a number。

![](img/17f4d5d915cb83e727719ecd4bbdff22_114.png)

If you have the concept of the parent of 42， then that depends which 42 you're referring to it might be three times in the document and each one of these three uses of 42 has a parent but then you have to distinguish between the three right whereas if you don't need to worry about the parent you just have 42 and 42 is 42 right you can even reuse it so there's no notion of physical identity anymore。



![](img/17f4d5d915cb83e727719ecd4bbdff22_116.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_117.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_118.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_119.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_120.png)

And what I'm saying is that。

![](img/17f4d5d915cb83e727719ecd4bbdff22_122.png)

Having a parent accessor。And having to deal with the physical identity of the nodes。

Adding the cost in terms of performance and in terms of codes that you need to run。

 it's basically slowing things down。And taking more memory footprints， does that make sense？Yes。

 and maybe could you like give an example where you might need this notion of physical identity。Yes。

 so。That's already advanced。So don't worry， I'm going to answer。

 but don't worry if it's not entirely clear， we will also come back to it when we study Jsonic。

Imagine that youre already like a few weeks in the future and you start manipulating these trees。So。

 for example， you might， you might have a tree like this。



![](img/17f4d5d915cb83e727719ecd4bbdff22_124.png)

And then you take that object right here。And you want to copy it over and attach it to some other object that's part of the query you're writing。

 so you basically take that object and put it in another tree below another object。



![](img/17f4d5d915cb83e727719ecd4bbdff22_126.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_127.png)

If you don't have to deal with the parent access or anything like that。

 you can use the same physical object in memory， you don't even need to clone it or anything。

 you just have the both parents point to the same one and it doesn't matter。

 you won't see the difference because your model doesn't have the concept of parents。

 so you will not see the difference by not cloning them， however。

If your model does require that you can go back and up in the JS tree and you want the ability to go back up。

That foxes you to do a clone of when you do it， you basically would need to take that object。

 clone it， copy it over， it has a performance penalty for that and then it's the clone that you attach then this one when you say parents will return this and the clone when you say parents will return something else but there is a cost because it takes more memory you need to clone it and you need to keep track of the physical identity。



![](img/17f4d5d915cb83e727719ecd4bbdff22_129.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_130.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_131.png)

Does it make sense？Yeah， yes， thank you。 Yeah awesome that's already a very advanced question This is really as soon as you start designing query languages you have to consider this sort of these sort of things。

 right？😊，A question on XML， is there anything that XML attributes can do that XML children can't。

 it seems like with a nesting ability， the ability to have duplicate tags， all these things like。

Having children seems to be a pretty complete solution， so I'm kind of unsure what attributes。

 what role they serve。So I told you two weeks ago that if you want to tro an Internet forum ask the question is Jason simplyr an XML and then look at the heated discussion that follows。

 there is a second way to tro an internet forum， ask if you should use attributes of our elements and that you also guaranteed get a discussion。

嗯。So the idea is that。You could consider that the model is a bit redundant in the sense that you have a choice。

 you have a design alternative when you have to put your data in there。

And there is no right and wrong， right， you could decide to put the data in an element or field in an element or you could decide to put the field in an attribute。

 so there is a bit of redundancy and redundant design。

but there are cases in which you don't have a choice and when you have nested data。

 then you have to use an element because in an attribute you cannot nest anything the attribute value has to be atobic。

 right？😊，So you see how've i'm using this term atomic a lot right this notion of atomicity the atomicity here is the limits that of the tree it's basically all the values that don't have any children are the atomic values does it answer your question yeah I guess'm。

😊，It seems like attributes can do like they can have the like turn a tag into a map essentially where all the values are yes absolutely atomic absolutely I'm kind of unsure why like why this is necessary as a language feature if you're able to have say duplicate tags and deep nesting。

 is it beneficial to force that you have unique keys have a one to one mapping and not have nesting in the attributes。

嗯。There are multiple ways to interpret that。 so one way is。

 why don't we have nesting in the attributes， is it？

What do you mean I guess what I'm saying is why do we have attributes at all if that okay covers a super set of the attribute features you want to get rid of the attributes yeah this is what you want you could absolutely you could get rid of the attributes and and then you could basically put everything in the elements。

What you would lose them if I'm thinking about the consequences。You wouldn't have any built in check。

That you can't have multiple time the same the same field。

 because you might remember that elements can repeat so you can have multiple time elements with the same name together。

 It's very common in XML。But attributes cannot be redundant attribute names cannot be redundant so you would lose this check basically if you do that this is one thing that could happen but in principle I mean you could you could get get rid of attributes in fact there are people that tried to simplify Xm you know Xml is already a simplification of HTMLml which was even more complicated and there are people who tried to simplify XmL by dropping all sorts of things that we think we don't need there are suggestions I think one of that is called simple XmL I think that is out there。

The one thing that is in the way is the universal acceptance。

The problem is that none of these proposals managed to get universal acceptance。

 So there are multiple out there。 None of them convinced everybody。 And here you see that。

One of the benefits of using X Json？Is not so much because it's perfectly designed。

 because they are not perfectly designed。 It is because it is universal accepted。

 There is one J standardout There is one Xml standardout。

 and you have thousands of Paar libraries out there that everybody is using。

 You can write down an XmL file。 Everybody in the world can read it。 You can write down a J file。

 Everybody in the world can read it。😊，Now， if you require a simple imagine you design a tool and you require a simple XML documents now the people who want to send you documents。

 they're going to have a problem with interoperability because then it's atonout it's basically a subset of XML that is not a universal standout and then you get into this trouble that you don't have that many libraries out there that do it so I'm kind of half answering your question but basically the take home messages is。

Neither XL nor JS are perfect or perfectly designed and that's okay because the real top benefit we get is the fact that they are stone outs and their libraries。

 does it make sense？有。Okay， thank you。But it's a good question。

 it's good to have the critical thinking。😊，All right， so XmL， Jason， any more questions on Zoom？Okay。

 but this is great because we got in the depth already at that point where it was supposed to only be an introduction。

 but we've already gotten far in terms of these things。



![](img/17f4d5d915cb83e727719ecd4bbdff22_133.png)

Okay。嗯。So now let me dive into the X information set， What is it？😊。

It is a st out called the memory representation。Of XM called the E XM information set。

So the idea it's about drawing the tree， we take a document right here， for example。

 that is an XML document passes right I mean it is well found so you can pass it。😊。

And the idea is that we need to define the nodes， I told you that whenever we define the data model。

 we need to define what other possible nodes you can have in there and what other the properties and accessoriesors right this is exactly what the X information set is doing。

 it's telling you what kinds of nodes you have。

![](img/17f4d5d915cb83e727719ecd4bbdff22_135.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_136.png)

Turns out that you have 11 of them， but I'm not going to borrow you with all 11 of them because some of them could be considered a bit deprecated or obsolete in their use。

 So I'm just going to focus on four of them and you will see it easy because it maps to the syntax we've learned So therefore I'm going to focus on are document node。

 element node， attribute notes and character notes where they don't call them nodes they say information item because it sounds fancier document information item。

 element information item， attribute information item so but basically these are the kinds of node you have right。



![](img/17f4d5d915cb83e727719ecd4bbdff22_138.png)

嗯。😊，And focus on these four。So first， that's the document。Note。And these here are properties。

 there is the children property there is the version property and there's many of them but I'm just showing to you the most important ones right and then I'm just visually drawing it like Doc here and that's a document information item。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_140.png)

So the first property is the children， and it has one side。 that is an element information item。

 That's metadata。 That's that's this here。 Okay， and the version is 1。0， which is taken from here。

 And then on top of this， But I'm not showing to you when you have a query language。

 you have accessor on top of that， which is get the children， get the version and so on。

 These are the accesses。

![](img/17f4d5d915cb83e727719ecd4bbdff22_142.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_143.png)

All right， so this is the document information item。😊。

Then you have elements information item the properties are a bit different。

 there's more than that I'm just showing you four of them so one of the property of the element information item is the local name is metadata right I didn't want to confuse you with namespaces so I keep namespaces out of there so local name is metadata the children two of them title and publisher these are the two elements that are in here。

😊，Attributes there's none。 and parent is the document information item。

 I told you you can navigate back， right， we can go all the way up。

 So the parent property is the document information item， Who agrees。😊。

Right okay I'm simplifying you a bit， but this is to give you the spirit then we have another one that's title same properties。

 but now the local name is title the children there's just some text in the in title the attributes there's two of them language English and year 2022 and the parent is metadata right it's this bidirectional navigation that you can go up or down to one or the other then we have publisher the local language publisher the children that's just Eth the week you can just see in the syntax attributes I don't see anything and the parent is metadata right so they have the same parent right。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_145.png)

Then we have an attribute information item so for a year 2022 should correct that。

 So the local name is a year normalized value is 2022 Why normalized because you typically trim the spaces if you have spaces at the beginning or the end you trim them So that sort of thing So this is why you normalize the value of the attribute right get rid of the extra spaces and the parent it's called owner element。

 but it's really the parent is the element information item title because that attribute is inside the title element then we have language E which the local name is language the normalized value is E and honor element is title。

😊，Then we have the text information item， systems group。The characters is just a string。

 it's a sequence of bytes sequence of characters， so S Y S， DEMSS space and so on right I said bys。

 I shouldn't say bytes， I should say uncode code points or characters。

And then the honor elements is title okay and the same for ETH ZurI。

 which has these characters and these honor elements， for whom is this there？

You can see them as Java classes， basically all of these kinds。

 and then these are actual objects that instantiate the classes and the properties would be fields of the class。

😊，But the cool thing is that once you have done that。

 you can use the parent owner element and children properties to draw。



![](img/17f4d5d915cb83e727719ecd4bbdff22_147.png)

And the edges of the tree basically correspond to children and parents and ownered， who sees that？



![](img/17f4d5d915cb83e727719ecd4bbdff22_149.png)

So what we've done is we've just done some formal definition of the kinds of nodes you can have and the properties you can have。

 which gives us an inme representation that looks like this in once we have passed the documents。

 so this is called XM information set or XM info set for those who are familiar and that's also a specification。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_151.png)

Of the， of the W3。All right。When I'm telling you I mean here I'm showing you with XML。

 the principles are general， the ID that you define the kinds of nodes in your tree。

 the properties they have， the accessoriesors they have and that you can draw a tree this is universal this is true for XML for Jason for Yamel you can do as an exercise take a Yael document they draw a tree try to come up with the kinds of nodes and the properties they have for Yael for example you might notice you're going to end up with the same thing as Jason you can use the same model for Jason and Yamel kind of there might be minor differences but they're almost the same。



![](img/17f4d5d915cb83e727719ecd4bbdff22_153.png)

Okay。So that closes the part on drawing trees and realizing that XmL documents and JSON documents are in fact trees and we can formally define how these trees look like in memory and that means that whenever you start reading an XML or JSON document。

 the first thing you're going to do is pass it into memory into a tree。

 everything else will be done in the memory on that tree。

 you forgot well forget about the syntax at that point you don't care anymore about the syntax。Okay。

The next step。That we can do once we have it in memory。

 is called validation validation not to be confused with its sibling called。When。Fmedness exactly。

 do not confuse the two。Wellformness is the first step Wellformness is basically a yes no question that says can I pass it and build a tree if it's wellform yes。

 I can pass it and build a tree if it not if it's not wellform you will not be able to build a tree the Paar will fail it will tell you theres a syntax error somewhere it will refuse to build the tree so wellformness is the requirement for being able to build a tree。

😊，Then we have a second step， once we have been the tree after that， that's called validation。



![](img/17f4d5d915cb83e727719ecd4bbdff22_155.png)

So you see it's a two level， yes， no is it well formed and if it is well formed， yes。

 no is it valid but I need to explain of course what valid means。😊。



![](img/17f4d5d915cb83e727719ecd4bbdff22_157.png)

V it has to do with the structure of the document in fact I kind of told you about it when I introduced the namespace right remember HTML XHt mathth ML and so on I told you there are constraints on the structure well this is kind of what validation means you want to validate that this is validates HTML or this is valid mathth ML it means the structure is actually correct。

All right， so if you use XmL， it changes in every version。

 but the colors of the buttons are just like in matrix right you have the choice between the red one and the blue one so the blue one gives you well fromness。

😊，Do you know metrics or am I too， you know metrics， okay？So validity on the left。

 the red one and wellform nest， the blue one， even if it's at some other places。

 they usually stick to that code， so oxygen tells you if it's well formed and if it's valid。



![](img/17f4d5d915cb83e727719ecd4bbdff22_159.png)

Now。What validation does， we will go into the details of that is it tells you if the document that you already made a tri of in memory respect a specific structure。

 so there are constraints that that element is only allowed to have decent that child。

 these object must have a key that is called age and that must be a number， that sort of things。

 this is a constraint on the structure。So。In the very narrow sense of validation。

 validation is a yes no answer that tells you yes， that document checks all the boxes of the constraints that you impose on it。

 it is valid， or no it is not valid。The other thing that you can do when you validate and typically is' done at the same time is called annotation。

An notation means you take the tree that you've just built。When you passed your well phone document。

 you built a tree。And notating the tree means you modify the tree and build another tree or you modify it in place。

 its the same。嗯。For example， you might have a text node that says 42。

 right that's the text characters4 and2。You might have your validation constraint that says that text node must be a literal that represents a number。

 it means it will accept 4 and2 because that's a number 42。

 but it will not accept4 FOO because that's not a number。

And what you typically do when you have a constraint that says it must be a number is that in your tree。

 you actually make it a number， it means that instead of the text node Co2。

 you replace that text node with another node that is basically typed and here you have an integer so it means that in your memory instead of having a string with the character4 and the character2。

 you replace that for example， with a 64 bit integer and that's an actual integer。

 why is that good because then you can you can use arithmetics and all kind of things on it and it is already in a number representation in memory that is called annotation annotation means that you modify your tree so that now you have typed value because you validated that the values correspond to specific types and then you can annotates that tree with the types。

Or whom does that make sense？Okay， so validation in the narrow sense is a yes no。

 and annotation means you slightly modify the tree to add all the types that you have resolved。😊。

Some people might use the word validation in a broader sense to include a notation。

 so they basically basically validate a document but they also annotate it at the same time。

 so this is why it depends on the context what you mean with validation could include a notation。😊。



![](img/17f4d5d915cb83e727719ecd4bbdff22_161.png)

Okay， so now I'm on the high level now I will get into the details of the languages that allow you to validate。

Maybe not today but next week， but what I would like to say。Is that。What you validate。

Might be Jason objects。Or XmL documents。That are part of the collection。

 you might have a collection with a million JO objects， one per line， for example。

 that's a collection of objects， or you might have a collection with a million XML documents。😊。

So typically when you validate a document， you actually don't validate just a document。

 you validate millions of documents with the same constraints that means that if you don't have any validation so I'm hiding this thing in there if you don't have any validation。

 your collection of JON documents could be very heterogeneous。

 it could be even a huge mess right you could have all kinds of documents that don't even look alike and that's totally fine you can absolutely have that。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_163.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_164.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_165.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_166.png)

If you bring validation into the picture， that basically ensures that all of your documents in your collection have the same structure。



![](img/17f4d5d915cb83e727719ecd4bbdff22_168.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_169.png)

For example， if these documents represent people， you might want that every person has a first name。

 or last name and agent on and so on， then you validate that and if all of the objects in your collection follow that that are value against the same constraints。

 the same schema， you basically have a homogeneous collection， whom does that make sense？



![](img/17f4d5d915cb83e727719ecd4bbdff22_171.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_172.png)

All right， so if you don't validate the collection can be heterogeneous。

 the moment you validate all the objects with the same constraints you get a homogeneous collection。

 it could fail， it could also tell you no that collection is really heterogeneous and we cannot validate it because the validation fails and then you just stay with that right？

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_174.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_175.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_176.png)

And that's actually fine because in some cases you actually do want to use the heterogeneous collection and deal with it。

 for example， your heterogeneous collection might be the logs that a company accumulated over 20 years right and they might not be valid or because it evolved over time so it might not all look alike and maybe in some cases you still want to be able to look at it and query even if it's not homogeneous right。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_178.png)

But the real nice thing。If you manage to validate that and build a homogeneous collection like this。



![](img/17f4d5d915cb83e727719ecd4bbdff22_180.png)

You get a lot of very nice performance box because the moment you manage to validate it。

 you can use even more efficient memory structures than the trees。😊。



![](img/17f4d5d915cb83e727719ecd4bbdff22_182.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_183.png)

And so that I will talk a little bit about。 But certainly， the moment you've done that。



![](img/17f4d5d915cb83e727719ecd4bbdff22_185.png)

When you deal with that， everything suddenly becomes faster。



![](img/17f4d5d915cb83e727719ecd4bbdff22_187.png)

RightSo the idea this is a bit slower and this can become much。

 much faster because of the regular structures that you have in there and in big data we have everything we like it if it's heterogeneous。

 we like it if it's homogeneous， we just associate it with performance if it's homogeneous just comes with better performance because you can store it more efficiently in memory okay so that's an example of documents。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_189.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_190.png)

That would be difficult to validate。To create a schema， why am I saying that because？



![](img/17f4d5d915cb83e727719ecd4bbdff22_192.png)

You see in this array here， there's a bit of everything。



![](img/17f4d5d915cb83e727719ecd4bbdff22_194.png)

You have a string， you have a boolean you have a null， you have an object。

 So if you would like to specify what kind of type it is you would say it's an array of whatever but you cannot say really an array of what it's not an array of strings it's not an array of boolean but this is fine right but it's just that this is this is this has less structure here too you have an integer and integer and an array so it's not an array of integers it's also not an array of array of integers it's just an array of whatever right so this is the idea here so this。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_196.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_197.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_198.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_199.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_200.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_201.png)

Would basically be absolutely okay。 Jason aose that。

 and you might actually have data that looks like that。

 but it might not be super fast to process with this heterogeneity。 This， on the other hand。

 This is the intuition I want to give you。 has a bit more structure。

 How do I see that it has more structure。

![](img/17f4d5d915cb83e727719ecd4bbdff22_203.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_204.png)

Well， here， I can see that I have an array and I have three objects in my array。

 It's already a good stuff。 These are on the object， so it's an array of objects。

 but if I look inside the object， I also see that these objects all have a key fo associated with always a string。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_206.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_207.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_208.png)

And a key bar that turns out to be optional， it's not always there。

 but it's always associated with an array of integers。

 Do you see that here it's something where I can very naturally define a schema saying it's an object A is an integer B is the Boy and C is an array of objects of which a required keys who associated with a string and a optional key bar is associated with an array of integers。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_210.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_211.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_212.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_213.png)

For whom does that make sense？What I've just described to you is called a schema。

 a schema would tell you exactly that structure。And then you can validate against a schener。

So far so good。 everybody's following。 So there is one question。

So can you define a schema for a heterogeneous array where you say it's exactly this length and the first element is of this type。

 maybe the first element is a string， the second one is boolean。Et cetera， et cetera， or yes。

But I have to explain a little bit in fact， it's a great way to use the last five minutes because then I don't have to open the next start。

嗯。So the first thing that I will say is that there are multiple schema technologies。

 they compete with each other。We look into a few of them JasonO schema is one XML schema。

 but there's also relaxing or relax energy and I don't know how it's pronounced。

 so there's alternate technologies， so there's different schema technologies。

These technologies do not necessarily have the same features。 They might be a bit different。

 Some technologies will allow you to do things that other technologies will not allow you。However。

 in the context of XM and J， most of these technologies have sufficient flexibility。

To allow you to still manage to validate something like this。In two ways。



![](img/17f4d5d915cb83e727719ecd4bbdff22_215.png)

The first way。Is when I when I said what is the type of B， I say a bit casualty。

 it's an array of whatever， right， an array of whatever。



![](img/17f4d5d915cb83e727719ecd4bbdff22_217.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_218.png)

But。In fact， most schema technologies allow you to say it's an array of whatever。



![](img/17f4d5d915cb83e727719ecd4bbdff22_220.png)

You're allowed to say that。And then it will validate that successfully as an array of whatever。

 and that's totally fine。 So this is the first answer to the question and here to you could say it's an array of whatever and that it。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_222.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_223.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_224.png)

嗯。But of course the consequence is that if you have a string with a number in there it will not annotate it because you just say whatever sorry okay whatever I'm just leaving it as it is but if you said it's an array of integers then it would be able to also recognize the integers and store them so that's the difference so that's the first part of the answer to your question most schema technologies allow you to say things like an array of whatever without further specifying or constraining the content。

😊。

![](img/17f4d5d915cb83e727719ecd4bbdff22_226.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_227.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_228.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_229.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_230.png)

![](img/17f4d5d915cb83e727719ecd4bbdff22_231.png)

The second reason where you can do it。Is that many schema technologies。

Also allow you to write code describing the construct。

It means that you could say not only be is an array of whatever。

 but you could write actual code that says the first one is a string， the second one is a boan。

 the third one is an earth， the first one is an object with who associated with a string and nothing else。

The thing is you would have to write it yourself， it's an extra piece of code that the user have to write and many schema technologies allow you to do that it's kind of a user defined or generic con it's less convenient of course that than all the constraints that are much like saying this is an integer is much easier but you can do it right so in this two way you can say an array of whatever and you can also provide some computer code that describes more precisely exactly what you want then it's duringcomplete basically。

😊，Okay， thank you。 We also have more time for a question。 Yeah， maybe the last one。

 then we I have to let you go。So you mentioned about the performance that when we have like a sma will improve the performance but intuitively speaking like when you have the validation you have to add the validation for every time you write it so in terms of like inserting more you will have to have an additional step so how would that compare because it will add some overhead of checking so this is an excellent question and again this is anticipating on some things we will see later。

Indeed， we will see that the behavior of validation。

Is different from the behavior you have in a traditional relational database in a traditional relational database like PostgSQl。

 you have to validate the data you don't have any choice the first thing you need to do is create table。

 you have to specify the column and the types so you have a schema， you have to do it。

In the case of big data in XM and J， you're not obliged to。

 you can also have a collection without any schema。

You can add the schema later like a week later you can come with a schema and say from now on I would like to enf that schema you are absolutely correct that from the moment you add a schema that enfoxes a penalty when you write new data because it has to validate that data it becomes slower when you write but it becomes faster when you read it again it's always a compromise there's no free lunch it's like time and space or algorithmic complexity that's the general ID but I'll come back on that many times because you already opened a very interesting topic in there with your question。

😊，Okay。😊，So that brings us to the end of this hour。

 tomorrow I'll talk about types and the type system of schema technologies until then have a nice evening and see you tomorrow。

 thank you。

![](img/17f4d5d915cb83e727719ecd4bbdff22_233.png)