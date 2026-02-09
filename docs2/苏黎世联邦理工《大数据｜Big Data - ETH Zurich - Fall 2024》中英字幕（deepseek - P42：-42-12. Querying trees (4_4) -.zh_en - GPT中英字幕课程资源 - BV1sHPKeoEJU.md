# 苏黎世联邦理工《大数据｜Big Data - ETH Zurich - Fall 2024》中英字幕（deepseek - P42：-42-12. Querying trees (4_4) -.zh_en - GPT中英字幕课程资源 - BV1sHPKeoEJU

Welcome everybody in the lecture hall。 welcomelcome everybody on Zoom。

 welcomecome everybody from the future。😊，So yesterday。

 I gave a very boring lecture with all the Jsononic and so on and so on。

 and today well dive into the physical implementation of it。

 So no more details on the syntax of Jsononic whatsoever， alright。😊。

So I just wanted here to say that with Jsonic， it's very easy to create C SV or Park file。

 You already have everything you need to know。 You know， Jsound。

 so you can create skichemas like this。 And then you can use the command line the command line parameters to say that you want C SV as output that you want only one part。

 creates only one file and that you want the headout。

 Then it's beautifully opening up in any spreadsheet software like this。

 Then you can use Li or whatever other libraries you want， right so。😊。



![](img/72bcd4554055e332d11550d933ef8291_1.png)

It works with。Plenty of formats。Okay， so the physical implementation。So I was asked。

 and this is a common question to ask， what is the difference between Jason Nick and Ruble。

And how does it connect to Sp。 So this is， in fact， the， the goal of what I want to。

 to explain today。So the difference between Jsonic and Ruble D B is that Jsonic is a language like Json like a SQL。

 like Java， like C， like C plus plus， like Python。 So this is a language。

 A language is just a way you， you were， you were interact with a computer。

 but it's not an implementation of the language。And Ruble D B is the implementation of that language。

 So you know that you can either interpret or compile a language。

 but there is a difference between a language and an implementation。 So Jsononic is the language。

 Ruble D B is the implementation， and it implements it， it implements Jsononic on top of Sp。

 but that's what I will explain now。So all this work here has been the work of many。

 many students over the years。 So currently Macco is mastertais。

 and the architecture is actually quite a standout compared to many other querying engine。

 We have this incoming inquiry。 And the first thing we do is we backfi。

 who took a compiler class compiler Bo。 Okay， so everything you learn in compiler Bo。

 This is where it goes。 You write a grammar。 You have an EBNF this is the standout form of having the grammar of some language。

 And then you you does libraries saw that。 And then you get an abstract syntaxt 3 or AsD who has already heard of A SD abstracttract syntax 3。

 Okay， great， This is all modular。 So here we didn't invent the wheel。

 We just use the G4 or NR in order to do that。 Okay。

 but the abstract syntax 3 is only the first step。😊。



![](img/72bcd4554055e332d11550d933ef8291_3.png)

Then what you need to do is convert the abstract syntax  tree that is very close to the syntax to what's called an expression tree。

An expression tree can be seen as some cleaned up and tidid up version of the abstract syntax tree。

 So in the in the expression tree， you have all the expressions of the language。

 that from an abstract perspective。 And I told you last time I counted it in the in terms of Java classes。

 there are 37 expressions， right， So additive expression， multidicative expression。

 variable expression， all the literals， flower expressions， e else expressions， and so on and so on。

 So 37 of them。😊，And so what you do is that you you convert the abstract syntax tree to an expression tree。

 This is done with a visitor pattern who already heard of the visitor pattern。 I hope many of you。

 Yeah， awesome。 So visit of pattern， you visit the abstract syntax tree and you output an expression tree。

 And this is， this is beautiful。 This is my favorite part because here it's a beautiful mathematical high level representation of your of your query。

😊。

![](img/72bcd4554055e332d11550d933ef8291_5.png)

![](img/72bcd4554055e332d11550d933ef8291_6.png)

![](img/72bcd4554055e332d11550d933ef8291_7.png)

And I insist on representation， because at that point。

 there is absolutely nothing that is evaluated or executed。

 This is just a tree that that that has the content of the， of the query。



![](img/72bcd4554055e332d11550d933ef8291_9.png)

![](img/72bcd4554055e332d11550d933ef8291_10.png)

And it's typically at that point that you do a lot of optimizations。

 So I can give you a few of them the sort of things that that is done at that point。

 you can rewrite some inefficient formulations in the language。 In fact。

 one of you pointed to a beautiful example of that。 This is。

 for where when you have a join where you have blah， blah， bla， blah， blah， bla， blah， blah， blah。

 This is typically the point where you automatically detect the join。

 And then you modify the expression tree to make it explicit that it's a join。

 This is the sort of things that you can do。😊，What we also love to do at that point。

 not just from body bit， but many engines is to try to detect the static types。

 because you probably notice that you don't need types in Jsononic。 You can put them， of course。

 but you don't need them。And， and typically， an engine is going to try to detect the types。

 But I insist on static types because you don't execute anything。 You just at compound time。

 try to infer the the， the types of the， of the things。 And that allows you to do optimizations。

 For example， there is one optimization that I will discuss。What is the type system in Jsonic。

 It's all sequences of items， right， So it's a type system that is based not only on atomic， object。

 inte and so on。But also on cardities， you have the empty type for the empty sequence。

 You have a type of exactly one cardity of exactly one integer， exactly one string。

 You have a one or more cardinity with plus right， Integer plus is a sequence of one or more integers And star is for0 or more that we covered in the in the validation and data modeling lecture。

 But why am I saying that is that。😊，At compile time， for example， if you see an addition plus。

 then you know that what's going to come out of that is either0 or one item。

 But you're never gonna get two items out of an edition， right，0 or1。

And that is super important information， because the moment。

 you know that an expression is going to return 0 or one item and not a billion。 then， you know。

 you know， you don't need stock for that。 So as soon as you detect。

 it's just one item that you can do locally on the machine。 For whom does that make sense。😊，Right。

And if you detect， it's a huge sequence， you know， could be could be billions of items。

 Then you will spread it over the cluster and parallelize it。 So I'll come back to that。

 This is the time where you figure these things out that you， you just look at the program。

 analyze it and try to to deduct these things。 Alright。

 So there's plenty of other optimization that are done there。😊。



![](img/72bcd4554055e332d11550d933ef8291_12.png)

![](img/72bcd4554055e332d11550d933ef8291_13.png)

And then comes the big moment where you convert this expression tree to a runtime iterator tree。

 This is the part that is executable， that you can actually trigger your press a button。

 and then it evaluates the whole thing。😊。

![](img/72bcd4554055e332d11550d933ef8291_15.png)

Again， it's a visitor。 You use a visitor， and the visitor is going to output a runtime iterator tree。

 It looks very similar in structure。 This is why we use the visitor， except that these iterators。

 they are not just an abstract， mathematically implement representation。

 They actually contain the execution codes that is able to to compute all the results of the queries。

 whom does that make sense。😊。

![](img/72bcd4554055e332d11550d933ef8291_17.png)

![](img/72bcd4554055e332d11550d933ef8291_18.png)

![](img/72bcd4554055e332d11550d933ef8291_19.png)

All right。This is very typical。 This is not specific to Ramble D B。

 We will find most querying engines have exactly that sort of that sort of implementation， right。

 even Po SQ L or even any， any database engine。 So this is。



![](img/72bcd4554055e332d11550d933ef8291_21.png)

Pretty st outs。Now， if we focus on the runtime iterator tree。

 because now I would like to tell you how it's actually executed。

 what actually is going to happen in your cluster。Or on your laptop。嗯。

Theseiterators that you see here。They are called iterators， because from a naive perspective。On the。

 you， you know， if you don't think of started execution or anything。When you have sequences of items。

You， your first idea is typically going to use the iterator pattern， the volcano iterator pattern。

 Who heard of that。Right， so let me tell you， because not all of you said yes。

It's when you have an API that basically has methods such as open， has next， next and close。

 already saw that。That is So， right。 So this is， this is typically an iterator。 In fact， they are so。

 so used and sort of other place that in Java。 they even they are even handles natively with just a column。

 You can iterate simplicity without even having to to call them because this is very common。😊，And so。

 indeed， one way to to execute a query like this that is in the form of a runtime iterator tree like that。



![](img/72bcd4554055e332d11550d933ef8291_23.png)

Is that。You go at the top over there。 That's basically the， the， the， the， the， the， the X。

 the the outer of your query。 And this is all the， the inner part of the query。



![](img/72bcd4554055e332d11550d933ef8291_25.png)

![](img/72bcd4554055e332d11550d933ef8291_26.png)

And when you put yourself here， you basically call open has next next， has next next。

 And you just pull the item。 It's a sequence of items， right， So you pull the item one by one， right。

 So as long as has next returns through like next next next next， you pull the items one by one。

 and then until the end。 And what's going to happen is that when you do that here。

 it propagates all over and then orchestrates a whole flow of items through the runtime iterators。

 right to， to computes the final one。 This is the reason why it's called the runtime iterator tree。😊。



![](img/72bcd4554055e332d11550d933ef8291_28.png)

![](img/72bcd4554055e332d11550d933ef8291_29.png)

![](img/72bcd4554055e332d11550d933ef8291_30.png)

![](img/72bcd4554055e332d11550d933ef8291_31.png)

![](img/72bcd4554055e332d11550d933ef8291_32.png)

![](img/72bcd4554055e332d11550d933ef8291_33.png)

![](img/72bcd4554055e332d11550d933ef8291_34.png)

Now， if you look closer， there is a subtlety。 There is a subtlety。

 because I told you every expression in Jsonique returns a sequence。😊。



![](img/72bcd4554055e332d11550d933ef8291_36.png)

![](img/72bcd4554055e332d11550d933ef8291_37.png)

Of。

![](img/72bcd4554055e332d11550d933ef8291_39.png)

Items， right。But the are paths of Jsonic that are not expressions。

 These are the clauses in the flower expression。 we have the foreclos， the lead clothes。

 the wear clothes， the counts clothes， the group by clothes， the other byclo。

 These are not expressions。 And you might remember that what they return。

 instead are variable bindings， right that we also call topples。

 These are the the things that look a bit like data frames。

 So when you have a four or wear or let and so on， you don't have sequences of items， then。😊。



![](img/72bcd4554055e332d11550d933ef8291_41.png)

![](img/72bcd4554055e332d11550d933ef8291_42.png)

![](img/72bcd4554055e332d11550d933ef8291_43.png)

![](img/72bcd4554055e332d11550d933ef8291_44.png)

![](img/72bcd4554055e332d11550d933ef8291_45.png)

![](img/72bcd4554055e332d11550d933ef8291_46.png)

You have toppers or variable bindings。 Topper is just the W3 C your name for variable bindings。

 right， So instead， you flow variable binding。 So this is why here I put a different color。 So。

 in fact， in this iterator3， you have most of the time sequences of items flowing。

 And in the special case of within a flower expression， Then you have toled streams。

 variable binding。 But Who is that here。😊。

![](img/72bcd4554055e332d11550d933ef8291_48.png)

![](img/72bcd4554055e332d11550d933ef8291_49.png)

![](img/72bcd4554055e332d11550d933ef8291_50.png)

![](img/72bcd4554055e332d11550d933ef8291_51.png)

Right， okay。All right。But now， let me get into the details， because if it were not。

 an engine based on Sp， if it were， let's say a previous generation engine。

 So there are a few engines that that do that， then that will just peak to open has next next。

 and you're done with it And that's it you release it。

 And you have an engine that is able to iterate。😊。

![](img/72bcd4554055e332d11550d933ef8291_53.png)

![](img/72bcd4554055e332d11550d933ef8291_54.png)

![](img/72bcd4554055e332d11550d933ef8291_55.png)

![](img/72bcd4554055e332d11550d933ef8291_56.png)

![](img/72bcd4554055e332d11550d933ef8291_57.png)

But。If you want to bring parallelism and more optimization。

You need to actually be more flexible than that。 because， in fact。

 you have more than one way of executing or evaluating the same expression。

 And I'm going to show you now three ways。😊，They are mathematically equivalent。

 They will give you the same results that what's going on in the machines is not the same thing。So。

The first model that I'm going to give you is called the materialized execution， materialized。



![](img/72bcd4554055e332d11550d933ef8291_59.png)

Materialized means that I'm looking at one specific iterator here more exactly that's what's going on between the four iterator and the return iterator。

 So that's the output of the fork clauses that goes into the return clause。

 And that is a stream of toppers。

![](img/72bcd4554055e332d11550d933ef8291_61.png)

![](img/72bcd4554055e332d11550d933ef8291_62.png)

Imagine that this you can take for granted。 This is recursive that comes from below。 and from below。

 you have a sequence of Json objects， right， So this is the query I've taking。

 You're basically reading from Json file objects or Json L。

 you're iterating and you're just navigating to the feed。

 So what you would expect to get are the integers in there， right， Who is that here。😊。



![](img/72bcd4554055e332d11550d933ef8291_64.png)

![](img/72bcd4554055e332d11550d933ef8291_65.png)

![](img/72bcd4554055e332d11550d933ef8291_66.png)

![](img/72bcd4554055e332d11550d933ef8291_67.png)

It's very simple query now。

![](img/72bcd4554055e332d11550d933ef8291_69.png)

What this iterator will do， if this is a materialized execution is that this here is going to be materialized。

 It means that I take the first object that comes from here and I bind it to I。

 So this is the first binding， right？ Then a second one。



![](img/72bcd4554055e332d11550d933ef8291_71.png)

![](img/72bcd4554055e332d11550d933ef8291_72.png)

![](img/72bcd4554055e332d11550d933ef8291_73.png)

Then the third one and this one， and this one。

![](img/72bcd4554055e332d11550d933ef8291_75.png)

Why am I saying it is materialized， I'm saying it's materialized because this actually is a structure that exists in the memory that looks exactly like this。

 You materialize it in memory， and you have this in here， it's a list， but you can consider it more。

 let's say physically or data frame。 right， This is materialized in the memory。

 You can actually look at the memory and you see that。😊。



![](img/72bcd4554055e332d11550d933ef8291_77.png)

![](img/72bcd4554055e332d11550d933ef8291_78.png)

![](img/72bcd4554055e332d11550d933ef8291_79.png)

And then you do the same here。 If you go further down，1，6。



![](img/72bcd4554055e332d11550d933ef8291_81.png)

For 3，2。 And again， this is materialized。 You have an actual list。

 an actual array with all the items in memory， right。

 So this is called a materialized execution when you do it like this。😊。



![](img/72bcd4554055e332d11550d933ef8291_83.png)

![](img/72bcd4554055e332d11550d933ef8291_84.png)

嗯。Can anybody tell me some drawbacks of the materialized execution， like the biggest drawback。

Go ahead。It's sequential。 So that is the first drawback。 and do you have another one？

The memory usage and the memory usage。 Youre both right。 These are two drawback。

 I'm going to focus for now on the memory usage， because this is the one we are going to solve。

 And then we will solve the the sequential aspect。😊，So indeed。

 it takes a lot of memory because you really have to imagine if it's millions of objects that you have or even billions of objects。

That you're gonna have in the memory， this huge lists with a billion of objects。

 this huge data frame with billions of records and this huge list with billions of objects。

 That takes a lot of memory， right， So this is exactly the problem。😊，How do we solve it。

We solve it the Netflix way。 When you watch Netflix， you don't download the whole series well。

 except if you want to watch it offline， of course。

 But most people watch Netflix in a streaming fashion， right， you just download the next few seconds。

 And as you make your way through an episode， it's downloading the next seconds， the next seconds。

 But all the past episode， they get thrown away， right。

 So it doesn't eat that much memory because you only need to have in memory the seconds that you're actually watching right now。

 right， This is why it's called streaming。 and streaming is not only for Netflix。

 It's also for databases。😊，So if you stream， then this is going to happen instead。

I generate a first binding of I to field1。And I immediately generate my first item that comes out of the written itator。

 That is one。 It the item 1。😊，Then I generate a second binding。But you see what happens here。

 I threw away the Fox 1。 It's really like watch that Netflix episode。

 and you already threw away what you've already watched。 So now I have sticks here， and I generate 6。

4，4，3，3，2，2。😊。

![](img/72bcd4554055e332d11550d933ef8291_86.png)

![](img/72bcd4554055e332d11550d933ef8291_87.png)

And I'm done。Who sees that this iss less memory。Right， this is exactly the good。

 So think of Netflix streaming。 it's even the same well。

And a drawback of this is exactly what you said。 It takes time because this is sequential， so。

You could actually process an unlimited number of items in this way。

 You could even process a trillion items or quite tri items because it doesn't stay in memory， right。

 So it doesn't matter even if you have little memory。

 you could have well1 GB of Ram and you could process a trillion of items this way。

 The problem is that you might still be here in two years。

 if you try to do it sequentially like that， right。

 So this is the problem of this one is that it can take a lot of time。😊，And for this reason。

 what do we do， we。We batch yes， and we。Pahales， right， So the two of them batch and Pahalite。

 absolutelysutely correct。So that means that now we get to use a data center where we have all of these machines。

 And what I'm going to do is that all of these objects that come from that file。

 they are basically spread all of all the machines。😊，You know how， because we studied H GFS。

 You know that H GFS is storing all of that in blocks of1 208 MB that has spread all of other cluster。

 So， in fact， what's beautiful is that when I'm saying we spread them all of other cluster。

 we don't even need to spread it， It's already spread because if it's in S3 or H GF。

 It's already done that it that it's like this。 So it is all of other machines。

 And then what we do is we process in parallel。 So now I can get these data frames like this。

 But you know， it's only a subpar of it nicely in parallel。 And then I get again in parallel。

 What I can do at the end is then write it back with GFS or S3 and it' going to be shard this is going to be one file。

 This is going to be one file。 Or if it's small enough because I had some filtering。

 I could also collect it。😊。

![](img/72bcd4554055e332d11550d933ef8291_89.png)

![](img/72bcd4554055e332d11550d933ef8291_90.png)

![](img/72bcd4554055e332d11550d933ef8291_91.png)

To a local list， right。So these are three examples。 It' materialized， streams and parallelhalel。

 for whom is that clear。Right， beautiful。 So what's very important to understand here is that this is data independence。

In the sense that we don't really care which one is chosen， the results are always the same。

 It's always correct。 So the only difference it makes is in terms of memory usage and the time that it's going to take to execute the query。

And Ramble D B is going to do exactly that。 It's going to。A ranch， the choice between Pahals。

 streamed， materialized and so on。Under other constraints that the results must be correct。Right。

 the user should get correct results。 But Ru B is going to try to make it as fast as possible by making decisions on whether。

Parallel， stream， and so on。A knife thing thinking might be。 we should always parallellyize。 But no。

 that's not true。 If you parallellyize for billions of items， Yes， that makes sense。

 But there are cases where you're reading just a small file。Or you just have a few items。

In that case， you should materialize or you should stream if it's very， very few items。

 because parallelzing has a fixed cost， right， If you parallelize you you， you have the。

 you have to iniate the executors and so on。 It takes a bit of time。

 So it's not always the case that parallelism actually wins。



![](img/72bcd4554055e332d11550d933ef8291_93.png)

对。And of course， it takes a lot of machines。To， to do that。So the idea of Ruble G B。

We rename it to Ruble D B， by the way， just so that people find it on Google。

 because if you just find this。Pixar actually at some point released the movie with that name。

 and we will not even receive it anymore， yes。So is that either parallel execution or streaming or co。

 could it be also an a combination of both a combination of both。 Okay， In fact。

 within the same query， you can have everything is's going to parallellyise and then it's going to materialise somewhere and then parallellyise again。

 It's totally able to do it in a hybrid fashion。 Alright， okay， thank you。

In what cases would it make sense to use a stream execution， but not parallelize and not materialize。

 Like， if it the data is small enough that you don't want to parallelize， why not just materialize。

That is a good question。So。Perhaps I would say that。Streaming has the advantage of the。

 of flexibility and simplicity。 If you， if you have a small data， but it growing。

 then it doesn't put a hard limit。So it means that you don't have。 Let's call it a singularity。

 You know， if， if you were always materializing。Then you would basically have to handle a singularity because if it fits the memory。

 then it suddenly crashes。When you use streaming， it has the advantage that it's not going to crash。

 It's going to take longer and longer and longer， but it's not going to crash。

 So this is why we stream whenever we want to avoid that singularity。

 that would be the intuition I would say now you're asking an excellent question， because basically。

 if I try to formalize this。 if you would only consider， let's say streaming and parallelism。

 And you try to find the breakeven points， right， This is what we typically do in research papers。

 right， you basically plot depending on the size of the data set。

 the time it takes to stream and the time it takes to parallelize。

 And then for small amounts of data streaming is faster and for a large amount of data parallel is faster。

 and then it crosses in the middle， right。Now， you can do that for streaming and parallelhael。

 and you can do it for materializing parallelhael。 And now the formal question that you're asking is。

 is there any point in time in which streaming is actually both faster than materialized and that and then than Pahael。

 right？ So this is this is something that that I you think about that。😊，But does that make sense。

 The justification I give it to intuition， yeah。Maybe one comment。 I。

 I think there are cases where we need to be sequential for correctness。

 And then it makes sense to do streaming to have his few or a small memory usage。

Whereas with parallelise， it would be incorrect。 And if futures materialise。

 it would use a lot of memory。Yeah， that might also， that might also play a role， yeah。Right。

 so we're already going a lot into the details here。 But I really need to think about that because I。

 I hadn't， I hadn't thought of it this way。 If there are cases where it's always worth materializing。

Allright。So Ruble D B allows you to query data on S 3 on HF S on on H T， TP， on local flight system。

 on Asia and so on。 of plenty of formats。 J， C SV Rob Park Carewoods and so on and so on， right。



![](img/72bcd4554055e332d11550d933ef8291_95.png)

![](img/72bcd4554055e332d11550d933ef8291_96.png)

![](img/72bcd4554055e332d11550d933ef8291_97.png)

![](img/72bcd4554055e332d11550d933ef8291_98.png)

Now， more details about the implementations。嗯。There are cases。 If you think of this static typing。

 Sometimes you have the information that an expression is just going to return just one。



![](img/72bcd4554055e332d11550d933ef8291_100.png)

![](img/72bcd4554055e332d11550d933ef8291_101.png)

Item or 0。In that case。

![](img/72bcd4554055e332d11550d933ef8291_103.png)

You don't even need an iterator。 It can be a simple method call。 You call the method。

 Get the result and that's it。 right， So this is the， the something we didn't have at the beginning。

 we were always iterating， But iterating when there's only one item is ridiculous。

 So we use a simple method call。

![](img/72bcd4554055e332d11550d933ef8291_105.png)

![](img/72bcd4554055e332d11550d933ef8291_106.png)

![](img/72bcd4554055e332d11550d933ef8291_107.png)

Then when it's a few items， we can have this volcano iterator。 we， we iterate through them。

 and then you basically can use the same thing if you have a filter here。

 you basically use a volcano iterator that's going to iterate Ex the filter in sequentially。

 then get get a sequence here so。

![](img/72bcd4554055e332d11550d933ef8291_109.png)

![](img/72bcd4554055e332d11550d933ef8291_110.png)

Simple method called volcano iterator。 There is no spark in there。 It's just pure Java。

 It's implemented in Java。 It's pure Java， alright。



![](img/72bcd4554055e332d11550d933ef8291_112.png)

Something that came to my mind because I'm still processing the question that you asked in the middle of thinking。

 The usage of memory also in the cost， allocating the memory and so on。

 when you want to allocate let's say a large array and so on。 that also has a cost in memory。

 You have the the Java garbage collection and so on and so on。

 So that I think would also play a role in the in the making a difference between streaming and and materializing in V M is as a。

😊，As a database implementer， I really have the intuition that streaming is more is more lightweight and less costly than than materializing。

 right， Does it also make sense。Alright， I just thought of it while explaining that。 alright。Now。

 so this is the case where it's local。😊，What happens now when you start having a lot of data。

 So you read a file from from H GF S。 Let's say this is the Json lines file， and it has， let's say。

 a billion objects。Adjason lines files is not necessarily valid against a schema。

 It could be a huge mess， right， So by default， if you're just reading a file and you have no idea if it's messy or not。

 you just make an RDD out of it physically internally， right。

 So remember D B is going to open that as an RDD in Sp。

 it's going to use basically a text file in Sp to get text。

 then it's going to pass to today J objects， and then to instances of item classes， right。

 And then you get an RDD of items。😊，And here we use the power of polymorphism。

 Have you heard of polymorphism in object orient programming。

 An item can be an object and a ran and spark R DDs totally work with polymorphism。

 So this is where it works very well。 And now we have an R DD of items in the， in the memory。😊。

If I now have an expression， that is the lookup， the， the navigation， I validate two countries。

Then what Rammber D B is going to do is use the flat map transformation。



![](img/72bcd4554055e332d11550d933ef8291_114.png)

And it's going to use the flatm requires the lada， right， some， some function。

 That is the mapping function。 And for that， we use what's called in Java， a user defined function。

 It means that whenever we use a flatmap， Ramble D is going to create some Java code that implement the mapping function。

 It's not totally trivial， but it involves the the navigation to countries that is all packed in a user defined function that gets serialized over the network at broadcast to the whole cluster so that it can be executed on all machines in Bahael。

 And then。😊。

![](img/72bcd4554055e332d11550d933ef8291_116.png)

![](img/72bcd4554055e332d11550d933ef8291_117.png)

![](img/72bcd4554055e332d11550d933ef8291_118.png)

![](img/72bcd4554055e332d11550d933ef8291_119.png)

What you get is again， an R of items。 And again， prettymoic， right。

 You see a string and a array and so on。 But this is no problem at all for Rammji。



![](img/72bcd4554055e332d11550d933ef8291_121.png)

![](img/72bcd4554055e332d11550d933ef8291_122.png)

Then you have this array onboxing。 It's， again， all done with RDs and using a flat map transformation。

 This time， it's a UDF that does the unboxing。 Then you get this。 And that's that's how it's done。

 right， And then when you have functions， let's say distinct values。

 You want all the distinct values in there。

![](img/72bcd4554055e332d11550d933ef8291_124.png)

![](img/72bcd4554055e332d11550d933ef8291_125.png)

This can also be pushed down to Sp。 Remember， D B doesn't bother to compute the distinct values itself。

 It uses instead the distinct transformation in Sp to do that。

 So it's all pushed down to the cluster。 And we use Sp to do the the parallel execution。All right。

 so far so good， who' is with me？😊，Alright， so now we have the local execution。

 We have the RDD execution， and then we have the data frame execution。

When the data happens to be valid。For example， because we read a packet file。

 and then we have a schema in there。Then it's preferable to use a data frame than an RD because it's much smaller in memory。

 data frame takes much less memory than an RD。😊，So what we do in that case is A Ru D B is going to use Sp to read the packet file and get a data frame out of it。

 Now， it's no longer an out to it。 So data frame。 And you see the。

 the data is beautifully easily I it here。😊，And then when you process it like you could navigate on it。

 then it's going to be a data frame transformation instead of an RD transformation。

What's very important is that all of that is physical。 It's internal to Rumble D B。

 The user doesn't notice that it only notices it faster and that it takes less memory。 but。

 but to the outside world， all we see sequences of items。 It doesn't matter if it's no code。

 if it's hard is， if it's data frames， that's just a physical detail。😊。



![](img/72bcd4554055e332d11550d933ef8291_127.png)

So to summarize， if we have heterogeneous data， we're going to physically internally use RDDs。

 If we have homogeneous data that is valid， then we are going to internally and physically use data frames。



![](img/72bcd4554055e332d11550d933ef8291_129.png)

Okay。

![](img/72bcd4554055e332d11550d933ef8291_131.png)

All right。So this is for handling sequences of items， right， Local execution， LD data frame。

What about flower expressions， Because flower expressions are like the。

 the most important expression in in Jsonic。 It's the equivalent of the select from where in the sequel。

 even more general。😊，So whenever we have flower expressions like this， by the way。

 the one at the bottom right gives you an example of this generalized s， right。

 where you can have arbitrary sequences of the， of clauses。

Then we also need to process the variable bindings that flow from close to close。But this。

 you already have a issue about because you saw that these variable bindings。

 they already look like data phrase where every column corresponds to a variable and every row corresponds to a variable binding。



![](img/72bcd4554055e332d11550d933ef8291_133.png)

So this is the reason why we do also use data frames for the， for the variable binding。

 for the to frames。

![](img/72bcd4554055e332d11550d933ef8291_135.png)

Between the clause。 So let's take an example。

![](img/72bcd4554055e332d11550d933ef8291_137.png)

I have a J file here。 I don't know if it's valid or not。 So I'm just going to make an RD out of it。

 right。Then it is in a fork loss。

![](img/72bcd4554055e332d11550d933ef8291_139.png)

So the forkclo needs to generate a variable binding。 At that point， there's only one variable person。

 So it's just one column。 And here in there， in that data frame。

 we need to put all of these all of these objects。

![](img/72bcd4554055e332d11550d933ef8291_141.png)

![](img/72bcd4554055e332d11550d933ef8291_142.png)

Now， we have a first challenge here， because normally data frames are structured。

 So if you naively think of it， that would only work if my data would be valid and homogeneous。

 right， But， in fact， the trick。Is that you can turn all of these objects into bits zero and ones and make the type of that column just a binary type。

And what that means is that it's a bit of a performance penalty because you need to serialize two bits and then decsize from bits back and forth between the。

 the items and the。And the the bits， But， but it works， right？

 And here what you learn here is if the data is messy performance penalty because of this。

 it's lower， but it still works。So。We have an LED， and we have a second floor。



![](img/72bcd4554055e332d11550d933ef8291_144.png)

Right， perhaps because we want to do a join or something。

 So this is going to be obtained with a transformation that adds the second column to the data frame。



![](img/72bcd4554055e332d11550d933ef8291_146.png)

![](img/72bcd4554055e332d11550d933ef8291_147.png)

Because of my other variable， I have another column。 and all of that。



![](img/72bcd4554055e332d11550d933ef8291_149.png)

In fact， Rumble D B does with Sp Sql。 Rumble D B generates Sp SQl queries internally all hidden from the user on the fly to basically create this new data frame with this extra column。

😊，And then it continues where that's also going to be in stock SQl with a where clause。

 So the where in Jsononic translates to a where in SQL。

Then you have a let that you can also handle with some SQL query， right。

 adding a third column that is using an extended projection to do that。

And then return is going to evaluate in parallel the， the， the expression。 So in that case。

 notrara's name。And it's going to just keep the laughter name。 That would be this， right。

 So that gets turned back into an RD。

![](img/72bcd4554055e332d11550d933ef8291_151.png)

![](img/72bcd4554055e332d11550d933ef8291_152.png)

Right， so this is how it works in T。

![](img/72bcd4554055e332d11550d933ef8291_154.png)

And again， the user doesn't see that。 The user just types this。

 and then it's all going to be executed in Than。

![](img/72bcd4554055e332d11550d933ef8291_156.png)

So， for the frog clauses。If it's in parallel， we use data frames。



![](img/72bcd4554055e332d11550d933ef8291_158.png)

But if it's very little data and it's not enough to justify running in parallelhalel。

 you can also have a local execution of the flower expression。 In that case。

 there won't be any data frames involved。 Its just going to iterate next， next， next， next， next。

 It just flows through the bindings。

![](img/72bcd4554055e332d11550d933ef8291_160.png)

![](img/72bcd4554055e332d11550d933ef8291_161.png)

It can be streamed。 It can be materialized to give you an intuition。



![](img/72bcd4554055e332d11550d933ef8291_163.png)

The forkclo， we can stream it。 The LED clothes， we can stream it。 The wear clothes， we can stream it。

😊，The group by clause， we have to materialize it。The order by clause， we have to materialize it。

Who has the intuition of why。Yes， can you tell us or anybody。好。For group guys。

 you need to wait it for out of the rows， which fall into the group。 And similarly for order by。

 you know， it's sort of blocking in some way exactly。

 That's exactly the idea When you generate a group of something that comes out with of group in a group by。

You need to。 you need data from many different places。And you never know if your group is complete。

You really need to consume all of the data to be absolutely sure that it's complete。

It's exactly the same reason why the shuffle path in rumble in map Red。

 the shuffle path can only sorry， the reduce path can only start after the mapping path is over。

 The mapping phase。 right， It's exactly the same idea。😊，So for this reason。

 as soon as you have a group by class and you execute it locally。Then you have to materialize there。

 You don't have a choice。 You cannot stream anymore。

 And the same goes for order by because when you order。

 you really need to to the the entire data in order to know what the next is going to be。

So to summarize here we stream or we materialize， depending on the clauses。



![](img/72bcd4554055e332d11550d933ef8291_165.png)

And what it translates to inhalel， when you would have to materialize here。

 that translates to shuffling， right？ So if here you can stream。

 then that would be a narrow dependency here。 And you can just group them in in stages， right。

 as we spend with back。 if here you need to materialize。 then typically here。

 it means you need to shuffle， right， So there is a connection between materializing and shuffling。

 And between streaming and narrow dependencies， right， Who has the intuition of that。



![](img/72bcd4554055e332d11550d933ef8291_167.png)

![](img/72bcd4554055e332d11550d933ef8291_168.png)

![](img/72bcd4554055e332d11550d933ef8291_169.png)

![](img/72bcd4554055e332d11550d933ef8291_170.png)

![](img/72bcd4554055e332d11550d933ef8291_171.png)

If you don't have it yet， then think about w it， right Again。

 streaming narrow dependencies and materializing shuffling。



![](img/72bcd4554055e332d11550d933ef8291_173.png)

![](img/72bcd4554055e332d11550d933ef8291_174.png)

There is a connection in there。And then for the expressions， it's what I already told you。

 you have the Java direct method called if it's just one item like plus you have the local iterations。

 next has next and so on。 You have the RD transformations。 if it's messy。 But Pahael。

 you have the data frame transformations。😊。

![](img/72bcd4554055e332d11550d933ef8291_176.png)

If it's valid data， it's sufficiently homo homogeneous。

 and we have one that I haven't told you about yet。

 It is that there are cases in which we do not even need to bother creating data frame transformations or whatever。

 we can literally compile the entire or entire parts of the Json query in native spa Sql。

 native spa Sql。 And that is the fastest that you can ever have when when you're able to do that。

 For example， this is a case where that is easy to do。

 because this in SQL translates directly to Foless one。😊。



![](img/72bcd4554055e332d11550d933ef8291_178.png)

![](img/72bcd4554055e332d11550d933ef8291_179.png)

![](img/72bcd4554055e332d11550d933ef8291_180.png)

Okay。

![](img/72bcd4554055e332d11550d933ef8291_182.png)

So if I summarize a little bit。 what's going on behind the scene is that we pass the query using G4 or NCR。

 right， the compiler Bu， we create the these abstract syntax 3 and so on。 At that point。

 we have a static context， It's basically all the variables you have in scope and so on， right。

 But you know， at compile time， then you statically in further types。 So you know。

 if it's only one item， if it's more than one item， if it's an integer。

 if it's a sequence of objects and so on。

![](img/72bcd4554055e332d11550d933ef8291_184.png)

![](img/72bcd4554055e332d11550d933ef8291_185.png)

![](img/72bcd4554055e332d11550d933ef8291_186.png)

![](img/72bcd4554055e332d11550d933ef8291_187.png)

![](img/72bcd4554055e332d11550d933ef8291_188.png)

![](img/72bcd4554055e332d11550d933ef8291_189.png)

Then you determine the execution mode。 Is it parallelel。 Is it low。 Is it just a method called。

 Is it native spa query， Is it a data frame， Is it an RD， It's also determined here at compile time。

 And then you create runtime iterator of three。 Having already decided on what is parallel and not parallelel。

 And then it's going to just be executed on the cluster。 And as I said。

 that's the question you asked earlier in the same query。

 keep going back and forth between local Rds data frames， it's fully hybrid。

 It just picks the best option depending on on the knowledge right So this is a visual the sort of things that you get。

 again， for this query here， you get this runtime iterator of tree。 And really， you need to see。

 So here there that's the clause。 So there are streams of the pe for the expression you have sequences of items。

 But look here we do a simple method called。 here we use RDds here we use data frames Here we use data frames。

 Here it's an RD。 Here is just a method call。 It's a plus Here it's a method。😊。



![](img/72bcd4554055e332d11550d933ef8291_191.png)

![](img/72bcd4554055e332d11550d933ef8291_192.png)

![](img/72bcd4554055e332d11550d933ef8291_193.png)

CallBecause there's only one item。 here it's a method call。 and here it's a volcano iterator。

 You see in the same query， we use everything。And with the power of data independence。

 the user doesn't notice all of that。 This is all hidden。



![](img/72bcd4554055e332d11550d933ef8291_195.png)

Right， so here's an example of a very simple query that is just one line。

 So very easy to write for the user。 But you see it's going to be R is all over place followed by a pushdown to spark for computing the sum of our billions of items。



![](img/72bcd4554055e332d11550d933ef8291_197.png)

![](img/72bcd4554055e332d11550d933ef8291_198.png)

All right。So the general idea now， if I zoom out on， on what's going on in the。

 in the community and in the database community。There is an ongoing convergence。

That that has been happening now for a couple of years。 And Ruble D B is is a on that same idea。

It used to be， I would say， like 10 years ago。That there was really two kinds of database system。

 There was the database systems for structured data， SQL data warehousing， data cubes and so on。

 And then there were the no SQL systems。 The cool ones with the startups and so on。 So Mongo D B。

 couchbase and so on and so on。 And these two worlds were not really talking to each other。 right。

 And then。😊，Something happened is that now people start merging this into a single system。



![](img/72bcd4554055e332d11550d933ef8291_200.png)

A single system that can handle the whole spectrum。And the whole idea behind that。

And the way that Rom DB also works is。If the data happens to be homogeneous and nicely structured。

It's just going to be magically faster。 If the data is a bit messy and more heterogeneous and nesty and so on。

 it still works， but it's going to be a bit slower， right， And so we see this convergence of systems。

 And there was an article in 2021 by it's by the data breaks， people。

 the ones who are who are behind Sp。😊。

![](img/72bcd4554055e332d11550d933ef8291_202.png)

![](img/72bcd4554055e332d11550d933ef8291_203.png)

Who called that the data lake house。 So a warehouse。

 This is well for the data cubes and the highly structured data。

 A lakehouse is this idea of combining everything。 You have a single system that has a data lake that has unstructured data。

 a huge mess。 And at the same time， it can construct structured reports and even involves machine learning and and so on in the picture。

 right， So a single integrated system。 So if you， who already heard of lakehouse。😊，Okay， some of you。

 So this might be a well that is going to to spread more into the， into the， the。

 the community with with time。 It's already three years old now。



![](img/72bcd4554055e332d11550d933ef8291_205.png)

Okay， so when we did Rumble D B， it was really the the coolest part with the older students that worked on it。

 We did performance， the checks， which we we looked at is it fast。 It is slow and so on。

 We compared it to other other querying engines。 And and we found that it's it's。

 it has a perfectly respectable performance compared to the to the other engines。 So。😊。

Means that the students did a great work implementing all of that。

And one of the very cool that's my last slide。 I just want to， to tell you， what cool project we had。

 also a master student。😊，Jhan， who implemented machine learning inside Rumble D B。And here。

 the main idea was that I told you the items can be atomic items， object items or array items， right。

 Then I said it can also be function items。 And so the idea is to realize that machine learning models can just be put in the function items。

 And then you can write a J query。😊。

![](img/72bcd4554055e332d11550d933ef8291_207.png)

Where you take a data set， you can clean it up because it can deal with messiness。

 Then you can validate the data and so on。 And then you take from some library of machine learning transformers。

 And then you can just manipulate it using， where can I find an example。😊。



![](img/72bcd4554055e332d11550d933ef8291_209.png)

诶。Yes， so you get an estimator that is came in， for example。

 And then this is where you do the training。 You basically fit the data inside the estimator。

 get a model out of it。 And then you can take that model。 And again， execute it。 So here。

 I did something very bad。 I used the training set as a test set。

 But that's because I just wanted to write an example query。

 And you can basically call the the resulting trained model on on some other data， right。

 So it works very， very nicely in the in in this ecosystem as well。

 This is obviously not material for the course right， I'm just I'm just saying that this this exists。

 And it was it was a really exciting master thissis。😊，嗯。Okay。😊，And exactly on time。

 do you have any questions， anything。That is unclear。All right。😊，So。

I recommend you read the the textbook that you were， that you train yourself with the tutorials。

 There's plenty of Jsonic tutorials that I shared in the car。 There is also some online。 make。

 make sure you can write Jsonic queries and that that you practice it。 This is really the best way。

 The T A team has prepared exercises for you。😊。

![](img/72bcd4554055e332d11550d933ef8291_211.png)

![](img/72bcd4554055e332d11550d933ef8291_212.png)

![](img/72bcd4554055e332d11550d933ef8291_213.png)

![](img/72bcd4554055e332d11550d933ef8291_214.png)

So thank you very much， everybody for attending。 I'm done with this。 next week。

 We'll talk about graph databases。 The week after that， we'll talk about data cubes。

 and we'll even have some oracle people who are going to come talk about vector databases。

 in the context of L L Ms。 It's very exciting to consider also these shapes。😊。



![](img/72bcd4554055e332d11550d933ef8291_216.png)

![](img/72bcd4554055e332d11550d933ef8291_217.png)

![](img/72bcd4554055e332d11550d933ef8291_218.png)

So thank you very much。 Thank you， Tobias， for moderating。

 And thank you for the great questions during the， during the lecture。 Have a great week。

 See you next Tuesday。😊。