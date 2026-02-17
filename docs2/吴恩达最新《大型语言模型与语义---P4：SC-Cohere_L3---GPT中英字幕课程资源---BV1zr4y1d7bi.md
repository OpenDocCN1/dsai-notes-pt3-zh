# 吴恩达最新《大型语言模型与语义搜索》｜Large Language Models with Semantic search｜中英字幕 - P4：SC-Cohere_L3.zh_en - GPT中英字幕课程资源 - BV1zr4y1d7bi

Welcome to lesson 3 on dense retrieval。 Now that we've learned about embeddings in the previous lesson。

 let's learn about how to use them for semantic search or search by meaning。

 This lesson is going to be in two parts。 In the first part。

 we'll connect to the same database that we used in lesson1。 But instead of doing keyword search。

 we will do vector search using the embeddings to do semantic search。 Then in the second part。

 having been comfortable with querying a vector database that's already been prepared for us。

 We will process the text from the beginning and see how we can build from scratch a vector index。😊。

Let's load up our API keys using the same code from before。 So before we do semantic search。

 let's start by importing。Go here。And let's set up the cohere Python SDK。 Let say cohere。

 got a client。 and then we just paste the。APpiI key access code。😔。

We'll do the same thing we did with setting up the WVA client and connecting to that exact same database up until here nothing is new。



![](img/db00d5bef4906711cee3eb00bb5bc65e_1.png)

Now， before we get to the code for searching by embeddings or dense retrieval。

 let's see what it means based on what we learned in the embeddings lesson。So we have the query。

 what is the capital of Canada， and we have， let's say five possible responses or sentences in our archive。

 the capital of Canada is Ottawa， the capital of France， Paris。

 we can plot these just like we did with the embeddings。

 and we can see that sentences that are similar in meaning， will be close to each other in the plot。

So if we plot all of these five， we can see that the sentences about the capitals of Canada and France are close to each other。

 and then the sentences about the colors are close to each other at the top right there。Now。

 where would this query be？If we project it into the same embedding space。

If we use an embeddings model that is optimized for search。

 it will be closest to the answer of that query。And so when we ask what is the capital of Canada。

 it will be closest to this point， the sentence that says the capital of Canada is Ottawa。

And that is how we use what we've learned in embeddings。

 these properties of similarity and distance into search。And that is dense retrieval。

 one of the two main ways of doing semantic search， the other one being rearbraers。



![](img/db00d5bef4906711cee3eb00bb5bc65e_3.png)

So let's look at how to do denser reval with wevi8 This is the code it will be very familiar to you if you've gone through lesson1 this is weviate API called the main difference here is that instead of using BM25 we're saying with near text。

Near text here， we pass the query to so we put the query in this Python dictionary。

 we call it near text and then we throw that variable at the query and then that is how we get the response back。

So this is how weviiate does vector search instead of PMm25 keyword search。 Once we execute this。

 we can start to send queries and see the results。 So let us now run a few queries and see what the database sends back。

So let's say we have this query who wrote Hamlet， we can run it。



![](img/db00d5bef4906711cee3eb00bb5bc65e_5.png)

So this is the first result， what happened here is that the embedding of all of this text was matched against the query。



![](img/db00d5bef4906711cee3eb00bb5bc65e_7.png)

And this is the text that is most similar to this query。 And in here。

 we can see that it talks about Shakespeare， writing hamlet。 And so this is the most relevant。



![](img/db00d5bef4906711cee3eb00bb5bc65e_9.png)

Text in the。Archiive for this query。

![](img/db00d5bef4906711cee3eb00bb5bc65e_11.png)

We can see in the second result as well， it mentioned Shakespeare and writing as well。

 so that's another relevant result here。

![](img/db00d5bef4906711cee3eb00bb5bc65e_13.png)

VV8 returns this distance number， this indicates how close the query is to the text here is。



![](img/db00d5bef4906711cee3eb00bb5bc65e_15.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_16.png)

Let us now try another query， which might be a little bit more difficult。

 So let's say what is the capital of Canada and we search and the first result is from the page Wikipedia page for Ottawa。

 which is the capital for Canada。 So let's look at how keyword search compares。



![](img/db00d5bef4906711cee3eb00bb5bc65e_18.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_19.png)

Let's import the keyword search function that we built in lesson one and pass the same query to that function。

 and let's see what the results are。

![](img/db00d5bef4906711cee3eb00bb5bc65e_21.png)

The first result returned is about the monarchy of Canada。

 so kind of relevant but not really the capital of Canada。

 The second page is about the early modern period， and the third result is about the flag of Canada。

 So kind of in the same space， all talking about Canada， maybe not this one as much。



![](img/db00d5bef4906711cee3eb00bb5bc65e_23.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_24.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_25.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_26.png)

But not really the answer to the query that we want and not really the most relevant passages from the data to this query。



![](img/db00d5bef4906711cee3eb00bb5bc65e_28.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_29.png)

Let's look at one more example， one more comparison between keyword search and。

Dense retrieval on another query。 So let's say the query we want to look at now is。

Tallest person in history。

![](img/db00d5bef4906711cee3eb00bb5bc65e_31.png)

If we run keyword search on this， we get something about the history of Japan。 We get 7 summits。



![](img/db00d5bef4906711cee3eb00bb5bc65e_33.png)

And we get something about。

![](img/db00d5bef4906711cee3eb00bb5bc65e_35.png)

Ahammamed binhaiffa Al Tni， which none of these are really relevant to the query that we have。



![](img/db00d5bef4906711cee3eb00bb5bc65e_37.png)

Now， if you do this with dense retrieval， what would the results be。

 let's copy the code and then just change the query。



![](img/db00d5bef4906711cee3eb00bb5bc65e_39.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_40.png)

Let's say。Tllest person in history。

![](img/db00d5bef4906711cee3eb00bb5bc65e_42.png)

And dense retrieval is able to give us Robert Wadlow， who is。

The man who was the tallest person in recorded history。For whom there is irrefutable evidence。

And so this is another example where densr trival really was able to capture the intent of the query and return the best result for it。



![](img/db00d5bef4906711cee3eb00bb5bc65e_44.png)

Another thing to showcase here where densor reval really helps with is multilingual。

 so this is how you can support search in multiple languages。

 so let's say we have this same query from before， but let's say we write it in a different language so the model that we have been using for embeddings here is a multilingual model so it's able to match a query in German with results in in any other language and we can choose what language the results are in it can accept the query in any language and so let's use the Arabic translation。

 let's say of this same query so which would be。Like。This。And when we execute this。

 so this is the tallest person in history， only written in Arabic。

And it's able to return to us the same result。

![](img/db00d5bef4906711cee3eb00bb5bc65e_46.png)

Another really cool thing I love to do with searching by embeddings is exploration。

 so you can say film about a time travel paradox。

![](img/db00d5bef4906711cee3eb00bb5bc65e_48.png)

And you can explore the results that you get back。 And so this is a film called about time。

 Let's say this is another one called the time machine。

 This is maybe based on the novel about time again。

 So you can spend really a lot of time exploring datasets like this。 I find this fascinating。

 I spend a lot of time exploring datasets using semantic search like this。



![](img/db00d5bef4906711cee3eb00bb5bc65e_50.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_51.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_52.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_53.png)

So this is a good time to take a few minutes and explore。

 you can change the queries and look for various pages inside of Wikipedia using semantic search。

And that is the end of part1 where we were just consuming a vector database。

 let's now start with part two where we actually build our own vector search database。

Let's start by importing some of the libraries we'll need The main one here is this library called Hannoi。

 which is a nearest neighbor library。It's kind of similar to Wviiate， but it's a little simpler。

 We'll talk about the difference between nearest neighbor libraries and vector databases。

 and then we'll import a few of Python's famous libraries。



![](img/db00d5bef4906711cee3eb00bb5bc65e_55.png)

NowBecause this is a simple example， we'll use the text from the interstellar page。

 So let's copy a bunch of this。

![](img/db00d5bef4906711cee3eb00bb5bc65e_57.png)

Text， and will'll paste it in the notebook。 Now， this is the text we copied over from Wikipedia。

 We just added it to this variable called text。 and it's just copied and pasted。



![](img/db00d5bef4906711cee3eb00bb5bc65e_59.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_60.png)

And then we come into one of the more important questions around semantic search。

 so we need to break this text down into chunks。But how big are these chunks。

 Do we split it into sentences or do we split it into paragraphs or what is the best way to chunk it。

 And this is a question that is commonly asked。 and it's really the answer is different for every task。

 A couple of the common ways is to split， let's say， at every dot。

 So we know this text is very clean。 All the sentences are separated by periods。

 So we can split on on the period。 But in real life， if you're dealing with a lot of noisy text。

 you might need to process it a little bit beforehand。

 And then you might also be needing to use libraries that actually split at various sentences in more complicated or advanced ways than just splitting at the period。

 So this is one option。 and let's see what happens if we execute it。 So what are the texts here now。



![](img/db00d5bef4906711cee3eb00bb5bc65e_62.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_63.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_64.png)

So we can see that every sentence。Is。A string inside of this list。

 And so this is one way of chunking where every sentence is a list。



![](img/db00d5bef4906711cee3eb00bb5bc65e_66.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_67.png)

Now， the way that the actual data set， the open source data set that we've been working with is it's actually split on paragraphs。

So we're not doing。

![](img/db00d5bef4906711cee3eb00bb5bc65e_69.png)

Periods we're doing paragraphs。 and so each chunk。Is actually a whole paragraph。

Now which one is right for you that really depends in general you want each chunk to maybe contain one idea。

But that really depends on， on the use case that you have。 But this is one way of doing it。

 Let's go back to。

![](img/db00d5bef4906711cee3eb00bb5bc65e_71.png)

The sentence split， I want to show you one thing here。



![](img/db00d5bef4906711cee3eb00bb5bc65e_73.png)

So let's say we split it by sentences， do you see this sentence here？

It says it received a claim for its performance， direction， screenplay， musical score。

 visual effects， ambition themes and emotional weight Now this sentence is devoid of context if you just embed this sentence we just send this to an embedding model。

 it really does not know what you are talking about。

Now the good thing about Wikipedia is that we have the title so we can add the title。

 we can append the title of the page to the sentence， so it gives it a little bit more context。



![](img/db00d5bef4906711cee3eb00bb5bc65e_75.png)

So to add that context， one thing we can do is copy the title。



![](img/db00d5bef4906711cee3eb00bb5bc65e_77.png)

After we copy the title， we can add it to this variable and then just append it to the beginning of each of these chunks。



![](img/db00d5bef4906711cee3eb00bb5bc65e_79.png)

And then， that looks like this。

![](img/db00d5bef4906711cee3eb00bb5bc65e_81.png)

And so。It has received a claim for its performance。

 we know that that is now about interstellar the fill。

This is a heuristic we've done here for Wikipedia， but then with every database or data that you have to break or chunk。

 you need to think about these design choices to recap a little bit of what we looked at with chunking。

 we have a Wikipedia page， we can break it down into paragraphs or into sentences。

 and then we embed each one of these， we'll go through the code to do that next。



![](img/db00d5bef4906711cee3eb00bb5bc65e_83.png)

So each one of these has its own embeddings vector。And then once we have our query。

 we embed that query， and then the search is just finding the nearest。

Neighbor or the nearest article。To that query in the embedding space。 And in this case， if we ask。

 do transformers have a recurrent structure， this article。

Is the one that outlines that and contains the answer for that query。



![](img/db00d5bef4906711cee3eb00bb5bc65e_85.png)

Now that we have our chunks， let's move on to the next step， which is embedding the texts。

To do that with the cohere。APpiI we say code dot embed。And we give it the texts。You say this is text。

 to list。😔，Dot embeddings。Now， this response contains the vectors representing these texts that we had in the past。

 Let's look at what it looks like。 So let's say， embeds equal。

I like to work with nuumpy arrays because we can inspect them as such and see their dimensions。

So we have the 15 sentences and then each one is represented by a vector of 4，000 numbers。

 that's the vector that captures the meaning of each of these sentences。

Now that we have these embeddings， we can throw them at a search library and start to be able to search them。

To do that， this is the code for annoy， we define an index。

And then we iterate over the embeddings that we have， and we insert them into the search index。

And then we have it build them and then save the index2 file to disk。

 so this is what test do ANN and ANN stands for annoi。

 but it also stands for approximate nearest neighbor。With that。

 we have our vector search index ready and we can send queries to it and it will be able to return to us the nearest results from the 15 documents that it has。

Let's now define the basic search function。And here's what it does， we'll send it a query。

It will embed that query， so it sends it to the language model and gets back a embedding for the query。

That embedding is then sent to the。Factor search index， and then we get the top three results。

 so the nearest three neighbors。To this query。And then here we just format them and print them。

So let's run this code and then start to show some。Querries。So this is one query。

 we can ask how much did the film make， so we have 15 sentences about the film interstellar。

 are we going to be able to find a sentence that talks about the gross。

 even if it doesn't use those keywords？We printed the results twice so we got retrieved the top three results。

 This is the full text of it， so the first result says the film had a worldwide gross over 60077 million which is the correct thing that were looking for and in here we also printed it again showing the distance so we have this scoring mechanism of how close the text is to the query。



![](img/db00d5bef4906711cee3eb00bb5bc65e_87.png)

![](img/db00d5bef4906711cee3eb00bb5bc65e_88.png)

So now that we've seen how to do dense retrieval， let's talk about vector search。

Using a tool like annoy that we just saw， which is approximate nearest neighbor and talk about how it compares to this other type of vector search。

Tool called a vector database。 Den rerieval really works by finding the nearest neighbors to a search query。

Now to make it optimized for speed， we actually search for approximate nearest neighbors。Finally。

 the exact nearest neighbor is taxing and computation。

 but we have a lot of really highly optimized algorithms that can get you the approximate nearest neighbor and that's why they're called ANN or approximate nearest neighbors。

We talked about the Anoi library， but there are a bunch of other ones。 there are also open source。

 so annoys from Spotify P is another popular one from Facebook and scan from from Google are all choices for approximate nearest neighbor vector search libraries on the other hand。

 the vector databases， theres a lot more variety there and options So wevi8 is one of them。

 there are a couple of other ones that are also online services like Pinecone and a couple more open source ones some of the common choices include quadrant Vespa Chroma but if you are familiar with databases like Postgresql there are extensions for Postgres that do vector search Now a common question is to wonder what is the difference between these two so the approximate nearest neighbor vector search library is usually simpler to setup up so you saw how any setting it up。

And installing it is maybe a little easier than the other choices。

 These vector search libraries also tend to only store the vectors。

 so they don't store the text with the weviiate example。

 you saw that we gave it a search query it returned to us the text so it manages that and it stores the text and it is able to retrieve the text that we want so it does a little bit more it's a little bit more feature rich Another major difference between these libraries and the vector databases is that the databases are easier to update so if you want to add new records or modify records if you're using a library。

 you need to rebuild your index while if you're using a database the database handles that for you。

Tectctor databases also allow us to filter and do more advanced queries。

 kind of like what we saw by filtering by the language。

 these are all useful things that vector databases allow us to do。Now， in the real world。

 you don't need to really replace keyword search completely with vector search。

 They complement each other。 You can use them both together in the same pipeline as hybrid search。

 What that entails is that when you get a query， you do keyword search and vector search on it in the same time。

 and you can see how a language model is going to power the vector search component。

Both these search components would then give a score。

 I assign a score to each document in the text archive。

 and then we can aggregate these scores and present the best results。

Do you see these other signals on the right？This is where you can inject other signals into the search results。

Google， for example， has its famous Page rank algorithm that assigns an authority score to various web pages and websites based on how many other pages link to them。

So you can treat that as an additional signal。Search engines have tens， hundreds。

 sometimes even thousands of signals that feed into the decision of how they order the search results。

 so this is just how you can encompass text relevance with other signals by this aggregation step In the next lesson you'll see how reranking fits in after the search step and how it can vastly improve this ranking and the relevance of the query to the search results。

If you want to learn more about the history of dense retrieval in the last few years。

 this is a really good resource to book in a paper called Pretrained Transformers for Tex rankinging。

 Birt andBeyond， I recommend looking into it if you are interested in the development of these models over the last few years。

Now that we've seen how denser crrieval works， which is one of the two main ways of doing semantic search with language models。

 let's go to the next lesson where we will learn about the second type， which is called reranking。



![](img/db00d5bef4906711cee3eb00bb5bc65e_90.png)