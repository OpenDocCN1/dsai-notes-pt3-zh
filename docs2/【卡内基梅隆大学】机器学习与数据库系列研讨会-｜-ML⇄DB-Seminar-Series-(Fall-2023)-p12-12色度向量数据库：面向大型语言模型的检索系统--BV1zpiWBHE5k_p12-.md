# 【卡内基梅隆大学】机器学习与数据库系列研讨会-｜-ML⇄DB-Seminar-Series-(Fall-2023)-p12-12色度向量数据库：面向大型语言模型的检索系统--BV1zpiWBHE5k_p12-

![](img/04b5fbd6c5c44e9517911843683c8abd_0.png)

🎼The databases for Machine Learning and Machine Learning for databaseases Sear series at Carnegie Mellon University is recorded in front of a live studio audience。

😊，🎼Funding for this program is made possible by。🎼Ggle。🎼And from contributions from viewers like you。



![](img/04b5fbd6c5c44e9517911843683c8abd_2.png)

🎼Thank you。Hi guys welcome it's the last talk of the semester we're excited today to have to finish things off with the guys from Chroma so Hammaad and Liquan are from the founding team of Chroma and it's another vector database they're here to talk about what makes them special what makes them different So as always if you have any questions for the Chroma guys as they're giving a talk please unmute yourself and say who you are and feel free to do this any time that way they're not talking themselves for an hour own zoom So with that Hamad and Lequan。

 thank you so much for being here at the floor is yours go for it。

Awesome thanks Andy and thanks to the course staff for putting this on this is definitely something I wish existed when I was in school at school to hear from everyone and it's been really fun I've been following along with the course throughout the semester and watching everyone's talk so hopefully today you we're going to talk about chromroma hopefully won't be too much that you've already seen in other talks we'll keep it interesting and talk a little bit about what we think is our unique perspective on vector databases and specifically our unique perspective on what's needed to build a end- to- end retrieevval system for large language models。

So before I start I'll just talk a little bit about well here we go。

 talk a little bit about chromroma so the project itself was launched in February of this year。

 it's been a tremendous year for AI and it's like peak of the hype cycle right now but we've had roughly you know 850。

000 downloads just on pipeP alone per month and we're seeing like a million machines running Chroma per month we've had you know been used in over 12000 GiHub projects and it's been really cool to engage with the open source community there's like 80 full-time contributors that are helping us a lot with like small admit fixes giving us feedback and a core team of five and soon to be six7 people。

And I think when you think about retrieval， it's really important and when you think about my databases in the context of language models it's important to think somewhat about language models themselves so I'll start with the basics right what is a language model and naively we can look at it this way which is we have some query or some question and we get out to answer this really naive perspective of a language model but hopefully one that makes sense to everyone right now you've probably used things like chatGBT or planning of the open source models and you get some question and you get some answer and really what this looks like right we might ask the language model hey。

 what does relational algebra and perhaps perhaps the language model has been trained on Wioppedia and so it regurgitates to us the definition that we might see if we search relational algebra on Wikipedia which is a theory that uses algebra structures for modeling data and define inqueries on it with well-founded semantics but what is the language model actually do when we ask it this question what it does first off is it takes your text and it tokenizes there's various tokenization schemes but all of them basically amount to you have some fixed set of token。

Some n000 potential tokens that you can turn your text into and quite literally we just get an array of integers that's what we turn the text into and we pass that into a language model and it tells us the probability for all possible tokens that we've trained the model on what is we probability that we might generate the next one and we do this repeatedly in an autoregressive fashion generating the entire string and this is important to understand because if you do something in this way you're going to be quite prone to potentially generating the wrong piece of information so a huge problem with language models is that they store knowledge in their parameters it's this parametrically trained system we have potentially deep nested sequence of transformer encodes of decoders and we are creating a language model that learns the probability of certain strings but there's some problems with that we can't update them in real time。

 we can't update them deterministically we can't provide provenance for their knowledge so how do we get a language model to tell us where did you get this information from and also they have a。

see to hallucinate because they're just modeling language they're predicting the next most likely token while they do you know people argue whether or not these things are learning world models。

 we can debate that separately please email me if you're curious about these things I find them fascinating but some people you know will talk about how they have a tendency to hallucinate because they are just predicting the next token we are just always going to blindly sample the next most likely token in the most naive decoding scheme for a language model so a a technique that many people have been using is what's called retrieval augmented generation and the idea is pretty simple you combine parametric and non-parmetric memory and this comes from a paper from Patrick Lewis and team。

fairair I think like two years ago and the idea is pretty simple。

 as opposed to just taking some text and giving it to a language model can we now take some text。

 give it to a language model in addition to some documents that might help ground the language models generation to generate some output y and more concretely what this looks like is we have some corpusive documents we basically we try and figure out some scheme to help us like some subset of documents we literally can attach that to the input text for the language model。

 rerun our generation scheme and get some output text y。

And there's a couple of different decoding schemes for this right in the most naive decoding scheme what we might do is generate the entire sequence full shot with all all of the documents attached to the prompt so if you're asking the language model what is relational algebra。

 perhaps you might give it some sequences that seem relevant to answering that question and then you just have it one shot generate in another approach you might actually attach one of the documents and do many runs of the language model in parallel and then compute the marginal probabilities across all of those。

In another scheme you might even do this lookup per token the point I'm trying to elucidate here is that there's many different small variations to the same strategy and developers often struggle with this。

 which one do I use， which one will work best， how do I reason about what's better for my specific use case。

 how do I try them in real time or online and evaluate the differences。

 and these are all problems that Chroma hopes to solve one day。

And specifically the way that we actually do this retrieval stuff。

 this problem of I have some set of documents and I w to want to get it。

 the technique that most people have been using is to use dense vector similarity search。

 so the basic idea is and I'm sure you're familiar we use some sort of dense encoding model usually a learned model when we map text passages to vectors then we perform similarity search which is usually just raw a nearest neighbor search for a given query similarity can be any metric in this case for the paper that I'm citing here it was the inner product which is like actually they trained an embedding model on the inner product and what you can quickly see is compared to like a naive rankings not naive but compared to a scalar ranking scheme like BM25 instantly the accuracy on many retrieval data sets jumps quite a bit so for example natural questions which is like a retrieval benchmark which I think highlights fans of Wikipedia based on human annotations we see that really quickly the learned embedding model performs a lot better even after only exposed to 1 thousand trading samples。

And after we expose it to all of the training samples。

 it performs about like 20% better and if you're curious you can read more in the paper but the point here I'm trying to make is that by using dense similarity search you can get much more accurate and contextual documents for the problem you're trying to solve at any given moment and what this actually looks like concretely is you input some documents D1 throughD and then you chunk these in the small chunks right so the embedding model has some fixed window that it can actually take some piece of text and turn it into an actual embedding and we take each chunk and tokenize and embed it and then we actually because if you remember in the previous slide。

 sometimes it's actually useful to combine like traditional Bm25 ranking with vector ranking so you might want to index them in a scalar fashion so perhaps you want to build a full text search index over the documents or perhaps you want to build some other sort of ranking index over the scalar components of your document and then we actually take each chunk and we index a vector component and then afterwards you might query these。

Using the vector index and maybe you apply some reranking using a learn reranking model。

 but this is generally the pipeline that people follow from raw document all the way through to retrieve results right it's a combination of many different pieces each with their own proof knobs and relevant strategies and tuning these is where developers spend a huge proportion of their time and run into a huge number of potential pitfalls。

And so our perspective。On this is that there should be tools in the market that exist for people to not have to think about these individual pieces in isolation to build each system in isolation。

 but end to end systems that help you do all of these together in an easy way and to iterate on the system as a whole slowly over time。

 as opposed to having to take each problem， decompose it into its own respective system and put them together manually。

So there's a couple use cases for this retrieval workflow that have been emerging for the last year or so the first is dialogue so we've all used chattTBT by now and you might just have some additional data that you put into the context of chattBT you want to have some dialogue with the model but also you want to give the model access to personalize or private data and so this data corpus is you know something that is personal to the specific user in mind or personal to the specific team that is using the product and another use case is the one of agents so this is more new and emerging but one that we're pretty excited about but the idea is you either have autonomous or somewhat manage agents that interact with external services and systems so one thing that is like a small like example perhaps you might have some sort of system that manages your DevOs you have an agent that understands your AWS setup you can just say hey I want to set up CICD for this workflow it just goes and does that because it knows how to look at your system and then it stores the skills that learns in a vector database and so this pattern of storing。

knownledge， sing learned experience and learned skills in a database is one that has been more recently started to become studied。

 a paper that we've been excited about is called Voyager that happened to use Chroma。

where they basically train a Minecraft agent to play the game of Minecraft and it stores its learned skills inside of a database and another one is auto completion or predictive AI。

 which is basically like if you're doing the most I think relatable example for this audience would be imagine like GitHub copilot so you're writing code and we're able to like predictively affect the right pieces of documents the right pieces of code in order to help ground a language model generation based on what you're seeing so if you're writing some code it might be useful to fetch similar code the code that you're writing to help give the language model a few shock prediction of what code it should suggest that you should write。

And these use cases entail a very specific workload shape and I think the argument I'll make is that this workload shape is rather different than I think what vector indices were originally created for but the vector search research I think traditionally focused on which was very large scale very high throughput data sets and usually it was one index you built it offline you update in batch and this workload is rather different we have a data where the QPS is relatively marginal right like we're not shooting for one index that has a very high queries per second most of our customers are okay with 100 to 1000 QPS on as a given index。

 but the data is also very real time it's not updated in batch and so the data lag that they're willing to tolerate is somewhere in the order of 100 milliseconds and their data scale is fundamentally relatively moderate so the data scale is on the order of one to 100 million vectors we're not dealing with data sets you know a personalized data for a chat dialogue but it doesn't have many billions of embeddings it has some。

on the order of  one to 100 million embeddings， but these embeddings might be frequently updated and deleted。

 so you might take， for example， the case of a document editing you know software and it needs to be able to frequently update and delete pieces of documents as users are editing them so that in an agent that is working with you in order to like suggest what you may or may not want to write。

 is able to respond to the updates and deletes in the document。But I think the most like to me。

 the most large difference is the one of the index。

 the number of indexes alone in any given data system。

 so you might actually end up having a index per user。

 and so you might have on the order of like 100 million indices for you know a reasonable workload。

At many companies and you want a very high recall target out of these because you're conditioning a language model degeneration and it's been shown that language models are quite poor at ignoring data that they don't understand to not be related to the task they're trying to perform so it's very important and we can't really tolerate you know deviance and recall and one thing that I think is also pretty different is because of the cursive dimensionality the vectors that we're dealing with are quite large if you go look at a lot of the literature on vector indices the dead dimensions of the vectors tend to be quite small so they're 96 to 120 dimensions and these are most of the benchmarks you'll see in most of the papers that have' been put out in the vector database world。

But the vectors that we deal with are much larger than that。

 and this actually makes a really big difference when you're actually doing the number of distance comparisons that you end up doing when searching vector indices。

 so the dimensionality we deal with is on the order of somewhere between 7684 to 96 dimensions。

 which is much， much larger than traditionalrs sparse vectors or sorry much larger than the dense vectors you saw from from vector search in older workloads。

And。😊，And what usually what people do right is you use some sort of approximate nearest neighbors index to deal with the fact that you can't end up exhaustively searching the whole solution space and broadly there's two classes of algorithms that are used the first is inverted indices so the idea here is you create some centroids over your data and you assign data points to a given centroid usually this is used in conjunction with some sort of compression scheme usually product quantization so you're crossing the individual points and then you're assigning them to a given centroid of them all of these algorithms are basically trying to reduce the number of distance comparisons you're doing by pruning the search space that is eligibleeg to you the other commonly used algorithm class is a proximity graph。

I'm sure you've seen from from other people in industry which is we create a graph expressing neighbor relationships these are often approximating a delany or relative neighborhood graph these are like sort of the inspiration and the sort of mathematical intuition you can have there is that the Deinoinois the Dey is a dual to the Boroois and the Boronois obviously is a good tool for dividing up space and then the relative neighborhood graph is closely related to the Deis triangulation of any set of points and so that also gives us some intuition for how to think about why a graph where any point is connected to nodes in its local region might be useful as a way to divide up space and search through it。

So I'm going to talk a little bit more about inverted indices which are a commonly used index type in industry and what I like to do is walk through inverted indices and walk through commonly used proximity graphs and sort of talk about why they're not the best fit for the workflow that we're targeting and then i'll talk a little bit about what exactly we're doing and' how it's somewhat different so traditionally when people use inverted indices they do so with product quantization so the classic workflow is you take your chunks of documents that we discussed earlier they're of Ddimensality we run some sort of clustering algorithm called it kines and we'll end up with some list of centroids and then what we do is we quantize our chunks so we take our chunks they're de dimensionmensional we do some sort of quantization perhaps you know we divide them into six subspaces and we get a dimensionality reduction of6。

Then what we do is we take all of our chunks and we assign them to the closest centroids we then find at query time we find the closest end centroids so you have some query。

 you find your closest centroids and we compute the distance to it the assigned centroids and that's how we know which posting list to actually search and then we can rera because the quantization step actually reduces the precision of our comparisons for each posting list by quite a bit so we recompute the full precision distance for each final list and so this is a very commonly used approach one of the problems with it is it ends up suffering a lot from recall the recall or suffers quite a bit you don't get the answers as as accurately as you'd want so people end up doing is they weigh over query their index by an order of0 to sometimes a thousand x and then rera that list and if you just actually do the measurement on the number of distance comparisons you end up doing it begs the question of like are there things we could be doing that perhaps might be slightly better and other people have found these techniques。

But because when you say when you say way over query， you just mean like limit a thousand。Yes， okay。

 some Matt like they went 10， they'll do limit a thousand。Yeah。

 like sometimes 100 to 1000 x the number that they want to actually retrieve so they just set K quite high yeah thanks。

And so the other vector index that's commonly used is a proximity graph algorithm called HNSW or hierarchical naviable small Worlds。

 this is work from Garyri Macoff and Dimitri Yashhuunin and the idea is really really simple and really elegant。

 the idea is can you actually just build a traditional proximity graph so you have some graph and without getting too much into the details because what really matters for our conversation today is that it is a graph and graphs are poorly stored on disk oftentimes and so because it is a graph。

What they do is they build a proximity graph and they inspired by skip lists。

 they build layers in this graph， so the top layer of the graph has longest range connections。

 the bottom of the graph has smaller and smaller connections and the way you can think of this is that the diameter or the radius of your graph is shrinking as you go down with the number of hops from any one node to the furthest node is decreasingac。

And the other trick that they employ in addition to doing this hierarchy of graphs。

 which makes the search go from a polynomial time to logarithmic time。Is they have this heuristic。

 which I think is really important to pay attention to。

 which is oftentimes you end up as you're building proximity graphs。

 you end up with points that are on the edge between two clusters and so they have a heuristic that will encourage crosscl connections and this sort of problem comes up a lot when you're partitioning space and is also like we willll talk a little bit later about how the same heuristic you can apply to inverted indices and end up with something that's a little bit better than the traditional inverted index approach but the key thing here for our conversation even if you don't understand how hW works at all is that it's a graph and graphs are not that great to be sort on disk the access pattern is really random and people have done work for example on disk and then where you can build the graph in such a way that it's more amenable on disk but at the end of the day these things are really hard to reason about the fundamental access pattern of a graph is very random the graph is actually designed to have longrange connections to move all over the data and if you actually just looked at the page access if you divide。

your graph into some number of pages and you look at the page access across the graph。

 you end up touching a large， large percentage of the graph in terms of the number of pages you touch when you do a query and the problem with this so that what people do is they story a entiregraph in memory。

And that quickly becomes a bottleneck， both from a cost perspective， but also just from a。

A usability perspective like how do you think about deploying something when everything that you have to touch will always live in memory and then another problem with H andSW is because of its design deletes tend to degrade the graph and the like commonly used solution for this is you just end up rebuilding the H andSW index entirely so let's say 20% the graph that deleted will just entirely rebuild it and then inverted indices also have their own set of problems the kvs clustering step often poorly partitions in the space and so you suffer from low recall it's also very hard to think about how many centroids to search and then it's often used in conjunction of PQ and then this has this over querying problem that I mentioned and this is very hard for people to think about in terms of tuning every different queries might have a different number of probes a different number of centroid lists that you actually want to search and also if you have real-time data which is quite important to us when you do the centroid step your data can drift quite a bit if you are indexing data over time the centroids have to be a represent。

of the distribution of the data at all times， but you are only building these centroids a piece at a time。

 and that's going to lead the drift in your actual centroid clustering set。

 which makes the inverted index have poorer recall over time。

So there's some interesting work done at Microsoft about two years ago and theyve made this algorithm called Sp。

 where they take the idea of how can we combine these two approaches。

 which is we store the centroids in a graph and memory and then we keep the posting lists on disk。

 so we do our centroid search， but we don't do root force over the centroids。

 we store them in an approximate nearest neighbors algorithm and then we store the actual posting lists on disk。

And what's interesting here is they keep a very high centroid count。

 so 10 to 20% of the data is actually put into centroids so if you had a million scale data set you would have 100。

000 centroids。This actually saves you a lot of memory unless you you know push a lot of the workload to disk。

 but also what happens is。Now you have a very fast layer in memory and you can keep your lists very small and when you can keep your list very small because you have a very high centroid count。

 it's very easy to reason about the disk accessces pattern because you know exactly how many are going to be accessed。

 you can find your i really well and you can fetch these posting lists off disk quite effectively and then what they do is the other tricks that they employ and you'll recall that I mentioned this notion of points on a boundary so what you can do is you can assign points to multiple centroids we call this closure clustering the idea is really simple if you're assigning a point to a centroid when when you actually do assign it only assign it to another point if it's distance to that point is less than the distance to the closest point plus some epsilon so we only want to attach a point to another point if we will attach a point to multiple centroids if we feel like it might be on the boundary between multiple centroid clusters and then we also follow a relative neighborhood graph rule for centroid assignment so we don't want to over。

populate all of our centralroid lists if a point over is overly specified on a boundary so what we do is we see we're going to skip assigning a point to a cluster if the distance between that point and the cluster is greater than the point the distance between that point and between the two clusters so in this diagram here right we have this orange point it's being assigned to potentially this bottom left cluster and this bottom right cluster and we don't actually assign it to this bottom left cluster because the distance between the two clusters the cluster it's already been assigned to is less than the distance between。

This point and the cluster itself and that means that the clusters probably overlap and so at query time when we go to look up a point in this region。

 we're probably going to end up looking in this list and this list anyways。

 so it doesn't make any sense to store this point twice really simple rule but if you actually go do the quick analysis of how many lookups that saves you it's quite a bit and then the last thing they do is they observe that when you query not all points need to visit the same number of centroids so they apply the same pruning rule we applied for building the centroids for assigning points to centroids so they apply it at query time and the observation is that different queries only need to access at different number different number of centroids and so you can actually prune the centroids when you're doing the query using the same distance rule we won't query a point unless we find that the centroid that we want the other centroid that we want to query is within some epsilon of us and the centroid that is closest to。

And these three tricks make a huge difference in terms of the recall performance you get out of inverted indices and so what you'll see is on the bottom here we have a graph where the blue line is traditional inverted indices。

 I forget what data set this is to be frank， but trust me the results hold。

You have a blue line that you know is just the result of traditional inverted inice season then what we do is we assign it to another four centroids and then eight centroids and 10 centroids and really quickly you can see a very large jump in the recall performance with this really simple trick of dealing with points on the boundary。

And then。Another small trick that we've been playing with is called8D sampling and the observation here is that a bulk of the time searching is spent rejecting candidates based on distance comparisons and the idea is that when you actually look at the time spent the majority of the time you're spending is spent rejecting candidates so we have graphs here of distance comparisons on negative operations in H andSW and IF you can see the bulk of the time these DCCOs pair operations is spent on rejecting candidates and the idea is that when you're actually sampling your graph all you care about is the point I'm looking at further away from the closest from the the top of the stack or the closest points I've seen is it worth adding it to my top K list and so what you can do is instead of having to do the full distance comparison can we just compare a subset of the dimensions right intuitively like if you have point in Euclidean space and these two points are really far apart。

You don't need to actually do the math for each dimension at some point the math for some subset of dimensions meet some threshold where you can just prune that that point from your search entirely and so what they do in this paper。

Is they use a result in highdimensional analysis and is the Johnson Lyden Str dilemma。

 which lets you basically say that if you're going to take a point and apply some random Euclidean transformation to it。

 you can then prune that point from you basically can bound the distance of that point。

 the norm of that point by some epsilon and so they invent a hypothesis and they come up with a hypothesis testing procedure based on this bound from the Johnson  Lyden Str dilemma that lets them basically flexibly when they're doing their search only compare a subset of the dimensions for any given point and this ends up speeding the search up quite a bit。

And so our index combines these two approaches， we divide the data into realtime and historical segments。

 we index real-time data into an HNSW graph， we compact historical data into inverted indices using the few tricks from the span paper that I just mentioned to you pleasure clustering and a neighborhood graph in flexible query sampling or flexible query pruning and then when we query we use 80 sampling in order to reduce the overall distance computations required to do any one query we store the centroids in HNSW and then we store a posting list separately and allow and using an inverted index approach while increasing the latency of our queries a little bit allows us to separate the storage and compute layers of our architecture。

And this leads to a lot of benefits for both developer experience。

 but also just general operational flexibility， and so now I'll pass it off to Laquan to talk a little bit more about the four architecture and how the index actually lives inside of the full distributor architecture。

Yes cool think yeah I'll share my screen I think before we go to that part quick question Hamman that was excellent so far this is really great。

😊，Could you shed a little light on how much you go into quantization。

 I know there was a slide you presented a few slides back that said in general people do quantization。

 how aggressively do you use that in your overall scheme or if you're going to answer that question later you could differ it to。

Yeah， that's a good question so we actually don't use quantization at all and the reason being that it is's really hard to reason about the performance of your system when you use quantization and so what people end up doing because they end up tuning the quantization scheme or the overqueery scheme to deal with the recall loss that you face in quantization and the problem is if we were just running our own system I think that would be easy for us to reason about but because we have a lot of developers who are being exposed to these concepts for the first time we've been in search for a solution that doesn't leverage quantization and so that's why we have these sort of other set of tricks that allows us to avoid having to quantize the data at the expense of at the expense of some latency obviously。

Thank you。😊，Hi a quick question Martin Palmer from University of Wisconsin Madison so you mentioned a lot of talk about using the distance metrics have you looked into any of the alternative approaches where you specifically train a separate model to do all of your distance calculations and then you rely on this distance measuring model。

Instead of the more traditional approaches。Yeah that's something that we've been interested in。

 but to be honest have not spent that much time investigating and personally really curious about how those those approaches perform。

 but we haven't used them ourselves Okay thank you。Oh， I think we can get started。 thank you， Hamd。

 for the introduction of the problem， the workload and the index。we are trying to build。

 I think this is one of the cornerstones of a vector database and also like one of the cornerstones of the retrieval architecture for large language models。

 I think another cornerstone， really the distributed distributed protocols that we build in order to ensure the safety and liveness properties of the system and we'll talk about a few problems and the solution we propose to achieve safety and liveness。

 But before that， Ill quickly talk about the chromma architecture。 And I'll start with a single node。

 the single node of chroma is pretty simple。 It has。

A server content of front end and also metlate index and met index。

 And then when people send the nearest neighbor queries。

 they will first go to the metada index and then carry the vector and then return the results。

And there are a couple highlights of the single node like architecture currently by using the HNSW SR index and also we use a Site as our metadata index。

 and we also store the system level catalog。We we call it system Db using S light。

 This is a single node version In a distributedive version。

 we basically decompbo those component into separate services。 For example。

 we have a coordinator that basically the system catalog and we will introduce a financial servers。

 which are kind of like the proxy serving sending queries to the logs and servers。

 depending on whether this reader rights。We introduced a defeat log as a database and distributed log basically serving the rights and row the rights will go to the distributed log first。

 and then the index node and query node will tail the distributed log and then build the views and indexes incrementally。

嗯。Yes。Next， I'll talk about the read and write pass for the chroma。

 So the red pass will first go to log and index node。 will tell those logs。

 and once it reach a certain side threshold， it will flush to the to the object storage like S 3。

And then that that the right pass。The read pass will be like the front end servers will figure out the assignment of the。

activective segments and heat segments and draw the information to the right node。

So we we are using a harshing scheme to reduce the global coordination。

 so basically the idea is that basic distributed log like Kacal pauseer has a concept of those like topics and then based on the topic ID we'll assign the topic to different nodes and for the historic segments also has ideas and based on the ID we'll assign them to different nodes。

Here I want to talk about a few like highlights of the system is there different like today compared10 days before ago that there's a lot of ecosystem we can leverage to build distributed systems。

 for example， we can use object storage， we can use distributed logs and we can also leverage Kubernetes to actually manage the membership and。

And and do not vacations。So that is our one principle basically。

 we want to leverage ecosystem of possible。 However。

 I also want to build like critical capabilities like the。

Kind of information propagation protocols as well as like topic reconciliationconfigregation protocols。

To ensure that the system has certain safety and allowing its property。

And we highly leverage harsh in currently in our system to reduce global coordination。Yeah。

Next talk about one problem we are solving。嗯。Which is called。

 we call this resultinging information propagation， so。In our right path， basically。

We have like one I segment that tellss the log， and then it increments the data and then build indexes。

And once it reach a certain threshold， it becomes a historical segment。

 you can think about like all the segments are。Generated from the active segment。

And I think this is important for us to making sure that during the segment generation splits。

 the final serverwards will always get the most up to date information so that the query will query all the data for the collection so that we don't have like data miss or have a partial query during this IQ segments split or node the additional node deletion and the protocol we are building is we build a monotonic protocol to ensure node query the query data。

Because from the server， because this is essentially a synchronous system and what the index node does is that as it tail the data as it flush to the disk。

 it will register the membership to the coordinator。

And the coordinator will broadcast the new term of APEC。To the front server。

 the term is the class wide term indicating a new assignment。To the member list。

And the term is only incr in response to no additional removals。And I is a per collection concept。

It means that each time when we are split or we generate the historical segment。

 the epic will be incremented because the system isynchronous。

 the front answer server may receive the updated terms of Eex in the delayed fashion similar with the workers。

 then how do we make sure that the system always query the right information。

 and we basically has the pull and push as well as a reconciliation rule。

P means that when the new front and server starts， you will pull the coordinator for the latest term and epic for certain collections。

Put me that when there's a new。Membership or there's new cannot like a segment generated will push the updates to the old friender servers and workers。

 The reconciliation means that all the queries will attach the。Term and epic observed by the worker。

 And then you will check whether the epic and term。

In the query is smaller or bigger or equal to the eye on the worker。 If it' smaller。

 which means that the。Funal servers are lagging behind。

 and each need to query the coordinator to fetch the most up to date information。I think with pool。

 push and reconciliation， we'll guarantee。The query alwaysque the complete data for the collection。

In the asyn Curous fashion。Yeah， this is one problem which I thought the second problem that of facing。

 as Hamman mentioned， were dealing with a large number of collections。And also， even。

We are using the CA P。 They have their own limitations on number topics。

 which means we can not just simply assign one topic to a one collectional one topic。

 We have to use some sort of like a data multipling。

 meaning that we be assign multiple collections to assign the topics。

And then but the challenge is that how do we make sure that as the system grows。

 as the number of collection grows？The we can re， reconfigure the collections over topics。

And this is in general a pretty challenging problem and the problem is basically like that during this reconfiguration。

 because the order of rights is very important because you don't want to you delete。

data show up again because of redering， so you have to guarantee the orders。Of the rights。

 even in the change， even in case of changing the number of topics。

And we have designed a protocol inspired by。The paperign。Basically。To ensure that。

During the topic re risk configuration， the data。Observed by the index workers are ordered by the configuration and offset from the topics。

 and this is critical to ensure the quantities of the data and the user experience。

And here's the hell overview overview of the protocol。

 it's actually basically solving two subtle problems。

 one is's a reconfiguration or rechar decision and we use a coordinator to make a decision and once the coordinator decide we have to do a topic reconfiguration you have to。

Be executed， This is similar as the prepare like stage in the two phase commit vertical。

And then the coordinator broadcasts a new topic list to the producer。

And when the producer receive those like your topic list and new configuration。

 it will communicate with the consumers by writing a。Message called film。To the to the topics。

 indicating that it will not produce messages with Paris configuration。 and then the configuration。

 the consumers will buffer the messages。And then one， it received the。Like a thin messages。

 If you know that which collections I will not。Receive the messages for the previous configurations。

 then I can deliver those messages to the investment worker after I deliver the messages of the current configuration for this collection。

Here's the thumb examples。It's like two producers are responsible for two collections。

And in the configuration we there will have one topic and both other producers will produce to the old topic and the consumer basically will consumer messages from this topic。

And then we want to change this configuration to use two topics。And the protocol is like that。

 so the coordinator makes decisions and it broadcasts to the category and change to all the producers。

And when the producer receive the。Messages you send the the thing to the old topic。For example。

 let's say producer one， responsible Collect one。And then once consumer received the message from producer1 to knows that collection 1 will no longer have。

Messages。For collection one with configuration with0， this is very important。

And then it can expose data。To the index worker and once it receive the producer too。

The same message from producer too， then it can expose the information for collection， too。

And this is very important and we do have some， this is not going to work all the time。

 but we do need to have some like assumptions。Basically。

 the assumption we need to make is that the consumer know how many producers are producing into this collection。

 and this cannot be changed during the configuration change。

 and the way we can do it is to disallow node addition and node the removal。

During the recontegration stage。 and also， we can use some kind of static membership mechanism in case of like node crashes。

 we recover the state， the node in into a state that is the same as before。 In this case。

 we can ensure that。The configuration during the we can have like a configuration change without any blocking of of the producers and without blocking to the consumers。

So that is是 like。A protocol we developed， and we are going to verify with the T plus。

So our philosophy basically like we think that because of distributed system all about reaching consensus。

And loudnesses。Without。With the minimum， I would say lies synchronization between systems。

So we need to make sure that those protocols are right from day one so that we don't run into situations that we have to do patch and patch again of the system of the protocol that is not pre designed。

 So we will make sure that those information， those protocols are designed number are verified。

On day one with carry plus so that we make sure that the protocols are very solid and then we'll be implementing them。

The other thing we are doing focusing on quickness is that even in the single node Chma。

 we take a lot of like effort implementing the propertybased testing and model based testing and the ideas very simple is came from like the lightweight lightweight formal verifications from AWS and we basically have a model for the metadata and mail model for the data and we have like reference implementations for example。

 like in memory map for the metadata and we have like preferred index in memory for the data and then we compare。

We we created a state machine that randomly。Prop like operations。

 both on the reference implementation， as well as the implementation and compare the result within certain bond。

 And we actually did quite， this is quite helpful in terms of improve our product capability。

 And we fixed quite a few bugs with those kind of like。

Property based testing in the model based checking。

And I think this also serve as a foundation when we build different systems because we don't want our system to you know。

 de quality or have like credit issues， and this is a solid foundation for us to move。Okay。

 NASA I'm going to talk about。Road maps。 and I think as Hamman mentioned。

 we want to be a end to end system for retrieal for lu models。

 I think white to search is only part of it。And ratio itself is not sufficient。

So if you think about building application with language models。

 there are three kind of like things you are thinking about three components。

 The first one is really the logic or the chain of like prompts the second one is the data including the retrieal as well as your structured data and third thing that is very important is also like the feedback evaluation so that you can find the right strategy of chunking embedding kind of reranking。

And for that， you can have a right， kind of like a。U。

Production grade language model for your application。So this is come。So with chroms like roadmapists。

 we want to expand chromma API to allow user defined function for chunking， embedding。

 indexing and reranking。And also we allow more sophisticated retrieval strategies to be pushed down closer to the data。

 Right now， I think Chma is focusing on the vector search part， but later we also want to。

Include API of chunking， embedding， storage and reranking。

 and in the following slide Ill talk about a few examples。

And the first example will be material evaluation。So。You。

 you have some query and you have some retreat result and also the generation result。

 and there can be。Some feedback around those results。

 and we can directly save those feedback into Cha。And this feedback will be useful in many kind of use cases。

It can be used to fine the embeddings。And different layers and different steps， for example。

 these feedbacks can be used to finding the model， these feedbacks can be fitted to the adapter metrics。

 and we can also build re ranking and filtering mechanism based on those feedback。

And based on those feedback， people can build better。Kind of like安 systems。AndAnother thing。

 Chmal is aiming to support with the pipeline API is。

Allow users or automatically generate the best kind of chunking strategy。

 The chunking strategy is very important， but is often overlooked。But however。

 the chunking is very important because it is actually tells the system what information they need to embed and there are many historical chunking strategies based on the document structure。

 but however， what is the optimal chunking strategy depends a lot on the task and the data set and way I think promise experimenting with the use of language models and larger approaches to perform or optimal chunking at injectiongestion。

And then， based on those。呃。Feedback and also we can can also include the re ranking model at the end to end。

 Re stack。And the relevance really depends on the specific query or tasks。

As well as the underlying insight so。After we reach the data。

 I think we can allow users to experiment with different ranking models to generate the result that has a。

Most relevant results。And that's all。 Thank you。I will clap on behalf of the audience。

 we have time for a couple questions if the audience wants to go for it。

I was running connecting back to some of the discussion earlier on Hamad you had mentioned how。

The vectors that you use sometimes go up to 4K and that's driven by the workload could you and Nquan tell a little bit more about the diversity of the workloads that you see obviously people get those vectors probably acquiring some of the LLM or some other method to do that is that what's driving it or is there something else that's going on with the diversity that you see in the vectors？

Yeah， I think it's mostly coming from the large variety of models that we're seeing in the open source landscape and then also from multimodal so nowadays we're seeing like video embedding models that for example so the 4K embedding models that I mentioned are specifically video embedding models and those just have by their nature of much higher dimensionality but then they also have a temporal nature to them which makes them a kind of difficult to reason about sometimes so the first is just multimodal embedding on the second is there's a huge resurgence of open source embedding models and so people are pulling them off the shelf and these are often trained in ways where it's a language model and then some part of it is removed and then fine tuned at the end or it's you know a language in embedding model trained specifically for this purpose and just the nature of the architecture leads to a much higher dimensionality now to say we have seen that you can reduce the dimensionality quite a bit and get the same performance so I do think there is a lot of headroom in dimensionality reduction when you have specific task and domain in mind。

AndI think that's like very much in line with the kinds of problems that we want to solve because it doesn't make sense for you to have a embedding model that is you know generically good at all of human language if all you're trying to do is do code retrieval it makes sense for you to fine tune and embedding model down to a much smaller dimension and focus it on that very narrow task so I think that that's kind of where things are going is we'll have these foundation embedding models that are trained on a wide purpose of data and people will fine-t them to their specific task and then that process can also do dimensionality reduction and it's kind of silly sometimes how simple it is to do that dimensionality reduction you really can just add a linear layer to the end of your embedding model and finet it down to a smaller dimension and get surprisingly good results which is simple binary classification as your training data set so that's where we end up seeing a lot of people do。

Any other questions with the audience oh I think you're muted sorry two more questions one is how big do some of these databases get in terms of number of vectors on some of the larger end applications that you see and then I'll wait for the answer for asking the next one。

Sure， I think that。The biggest data sets that we've seen are like。

Right under a billion data points just like the biggest data set that I've per index in the Cha but that's like very much on the tail case。

 so I think the large majority of our data is on the order of several hundreds of thousands to several millions of vectors but then again the key part is that they're growing quite they're being updated quite frequently both in terms of additions but then also in terms of mutations both updates and deletes and that leads to some challenges in the underlying vector index algorithm that you use。

But yeah I think several millions of vectors seems to be where a lot of these things are converging and I think that comes out from the fact that when you end up chunking a reasonable corpus of documents。

 say say like 10 to 1000 documents when you end up chunking them and then processing them。

 you end up somewhere in that regime and so for most of the use cases that we're seeing be it chat your documents so you have some internal knowledge base that you want to chat over or like code retrieval or know augmenting a language model with knowledge specific about some new tool that you're developing so it can assist users with that task。

 those corpus of data tend to be not trivially small to where you can root force but know not insanely large where we have to start getting into how do we do billion scale vector search on a single node。

Great， and then the follow up question was， do you run through issues where someone has a。

Longstanding application where they're not just creating these vector databases for a small amount of time。

 but they're really building on it more like a database and they go ahead and switch the model that they're using for embedding maybe they switch from G 3。

5 to4。Oh。Do the users take care of migrating the database to this new embedded model or do you provide tools to allow them to do that？

Yeah this is something that we've been thinking a lot about we don't have any explicit tools to help with that today。

 but I think there's sort of three flavors of problems that all align with this the first is the actual language model drifts over time without you knowing so if you're using some API service provider the behavior of the language model might change in and of itself without you even knowing and that can be a bit strange to monitor for so I think monitoring tools or something that the ecosystem is working on and perhaps might make sense for Chrome but I'm not entirely sure and there's a really good paper actually from Databricks where they measure like over three months how does the performance of a language model on a fixed benchmark of tasks change over time So I think that's the first class of problems and the second class of problems is as you mentioned it like you change the embedding model yourself and you have to sort of manage you these different versions of the same task workflow that you're trying to perform and I think that in that case the way that we think about it is people are going to be doing that both for experimentation but then also for valid use cases or maybe it makes sense to online AT。

two different embedding models and perform you know a comparison and then see which one's performing better maybe you fine tuned something and you want to run an experiment so I think in that case we do think that there needs to be a way to for the system itself to handle that for you and I think that's sort of an experimentation platform that could live inside of chromromo but then also of course you could just do that on your own using the same data model and I think the way that ends up manifesting is the fundamental data structure or like data model chromroma as a collection of data and you just create multiple and then the idea is like how can we somehow allow those to share indices to start but then if you mutate them or change them over time you know do some sort of copy onright scheme So I think that' that's what potential approach is you don't need to you don't need to duplicate all the data just the data that matters for your specific variation and then I think。

The third class of problems that people run into is they you know are changing other strategies so they're not changing the embedding model but perhaps they like are changing the actual you know that they're changing the chunking strategy or they're changing the re rankinging strategy or they're actually just updating a document so a huge problem we see is like I took this document I broke it into ten chunks then I actually update the source document what's like the best way to update all the individual chunks of the document without having to redo all the processing that I just did in was a bunch of compute in the case of very large documents how how do we do like a different embed is like an active problems so I think those are sort of the three areas where we see some sort of drift in either embedding model providers or language model providers resulting in issues or actual just drift from the person using the database themselves potentially causing the issues and and I do think that it's necessary that whatever system emerges to solve these problems hopefully Chroa makes those things easy for you。

Yeah， thank you and I just loved how you had so many connections made to papers and thats just fantastic loved it awesome talk。

All rightAny other questions with the audience？So I wanted to go back to the sort of the distributedtri assessment protocol you're running to do the reconfiguration。

 is this something specific to Chma or is this like just a limitation in Kafka？

That like you do this reconfiguration and you need to update a bunch of people that are feeding from it in a sort of atomic manner。

yeah， this is a limitation from Kafka I think there was a proposal about like topic expansions in Kafka。

 probably in P as well， but this is in general a pretty hard problem in the sense that you need to codinator the producer。

 the broker， the consumer。So I think this is like how we have to build on top limitations private Kafka。

 I think the the the I think the， on high level， the intuition is that。呃。

Assuming that you are dealing with even time processing with out of order， like messages。

And message can arrive kind of like in a fashion that can be delayed。

 but you want to make sure that for example， you want to compute the number of like the spend on an hourly basis and then the hourly basis can really arrive late maybe in 24 hours late。

 you basically need to keep all the windows open before you can send the right answer to the downstream right this is how this is basically the paradigm of fllink or like spark streaming but now the idea is that you always output the correct answer to the downstream and the way to do it to figure out what they call a frontiers。

 which is the latest of the lower bound of even timest that will happen in the future and once you know like the frontier。

 then everything before this timet is kind of like you're already know the answer and youre not going to change everything you send out the downstream will berevoable the。

Here is that this is basically a high idea。 And the way we do it is to make sure that we know all the producers are producing this this collection。

 and we know that all the we need to keep track of how many producers already。

Make the configurationuring change。 And then the producer once。

 they are absolutely sure that they'll receive all the。

A kindin of acknowledgement from producers that we are no longer producing the data。Before。

 then I can safely。Sing data to the downstream without violating any。Like audit in guarantees， yeah。

mean I mean how expensive would it stop the world be in this like to do re configurationration in this case is I think there's there won't be any big like stop the word the first step you need to know because we probably won' use two code path for the normal case as well as the ring configurationfi case I think the only thing you need the like a two stage consensus is we need to make sure that everyone is entering is make sure that we are executing a configurationuring change and the we switch to the。

Conration change code pass similar yeah， that is only then after that， everything is asynchronous。

 If you make sure that there's no like no additional removal or crashes。 Yeah， okay， that's not idea。

And then the beginning of the talk you guys went through a bunch of different optimizations that a Jnesssh said appreciate you guys putting citations in the papers。

 but like you didn't show is it possible to show like for all those optimizations like which one gave the most bang for the buck in terms of engineering or compute time。

 like if someone's going to implement all those optimizations。

 which one should they start with first Yeah I think the biggest one is if you're doing inverted indices。

 the closure clustering what they call closure clustering in this fan paper where you sign a point to multiple centroids based on a adapting condition that that changes inverted indices from something that is very hard to reason about the performance of basically working almost as good as HSW in most cases it was quite surprising to us when we implemented it is like a very simple idea like you have points on the boundary just assign them to multiple centroids it' very simple heuristic。

 but it changes the recall performance by like 20 to 30% in some cases and it' it's quite a large and drastic jump。



![](img/04b5fbd6c5c44e9517911843683c8abd_4.png)