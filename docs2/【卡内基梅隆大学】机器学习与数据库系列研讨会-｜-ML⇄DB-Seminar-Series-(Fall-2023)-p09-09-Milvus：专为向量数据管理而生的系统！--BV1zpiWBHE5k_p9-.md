# 【卡内基梅隆大学】机器学习与数据库系列研讨会-｜-ML⇄DB-Seminar-Series-(Fall-2023)-p09-09-Milvus：专为向量数据管理而生的系统！--BV1zpiWBHE5k_p9-

![](img/9205305a962aa02e613087b9ff6e1757_0.png)

🎼The databases for Machine Learning and Machine Learning for Dataases Sear series at Carnegie Mellon University is recorded in front of a live studio audience。

😊，🎼Funding for this program is made possible by。🎼Ggle。🎼And from contributions from viewers like you。



![](img/9205305a962aa02e613087b9ff6e1757_2.png)

🎼Thank you。Welcome guys we're here for another talk at seminar series we're excited today to have Lee Lu he's a principal software engineer at Zeals where he works and helps build the Middleless vector database system so as always if you have a question for Lee as hes giving us talk please unmute yourself take who you are and fire your question off at any time we appreciate him calling in from China to give this talk where it's currently 5 30 a so it's。

😊，It's not the record。 I think the latest we've ever had was somebody in India at， I think3，30 AM。

 but still it's very early for him。 we appreciate him getting up for us。 So again， Lee。

 thank you so much for being here。 The floor is yours。 Go for it。😊，Okay， okay。

 so however my froms the first I want to express my sincere yeah actually I you distinguished CMU alumni it's very terrible that's f to this Lee is CM alum。

 so we appreciate him coming back to talk about us。😊，Thank you thank you。 So yeah okay okay。

 I will just start so first I want just express my sincere gratitude to Andy for inviting me to revisit CMU I spent quite a happy time years before so so glad that I can share me with technology and as well as our industry insights with all of you today。

😊，Amii is one of the world's most famous vector database I'll say and is the most popular open source vector database with very super active community it is actually the world's first director database with five year history yeah five years it's quite a long time well it probably doesn't sound like very long time comparing with something the history of My Se and H base this kind of thing。

嗯。This is because vector database is a brand new field。

 So many design and concepts in the vector database area have have not have not been thoroughly tested yet。

 So always keeping this in mind as implies that on the other hand。

 there's still a lot of work to be done and plenty of opportunities。 So in today's talk。

 I would like to discuss the design principle within architecture。

 Hope that it will serve as both informative and inspiring。And yeah， something about myself。

 I'm from Zeals， and principal from an engineer from Zeals。Okay。

 before digging to the specific content， I like to leave you all with a question。

 So what is the relationship between traditional search and vector search and what is that of between traditional database and vector database。

 I'll put a video here。As a hint and we will revisit these two questions toward the conclusion of this talk。

Yeah， so I get a。Turkey cowboard。Is this just the audio， sorry for this。I know， it's just a video。

 I'm sorry， I didn't put any all inside it。So， yeah， this time we get a pule and。Last one。

Try to get a glass glasses。 That's pretty cool， and。You got the glasses。Allright。Yeah。

 thats a small video just about start to start everything。呃。Well。

 we'll cover three aspects in today's presentation。

 so first I will give a brief introduction of Muva's general architecture where where you may notice the uniqueness of Muva's architecture compares other similar products and then I will dig into the design of an important component of Ms the right part of it。

 and this this shows how Muva is designed with focus on machine learning。 Last and not least。

 I want to discuss our challenges and solutions in border context of machine learning booming。

 not only about the perspective of database designed for machine learning。

 but also from how machinery booming can promote vector database。All right。

 let's start with the introduction of views first。Before talking about the vector database。

 let me first introduce the concept of vector search I been previous talks have already covered this similar。

 So basically vector search is about finding similar vectors giving a query vector， for example。

 the algorithm is one of the most one of the famous vector search algorithm。

 I would say now let's let's get more practical and think about scenarios of how vector search is applied to our daily life。

We can image search is a classical example now just like one day I came across my a picture of our this memorable landmark。

 I would like to find more pictures of。From different perspective。

 But then walking to the sky was at tip of my tongue。

 So I simply track this picture to into Google just and search it and got so many pictures about walking to a sky behind the behind the scene if if functions follows。

 So first we。A deep learning model extract the embedding of the first work to sky images as its presentation vector。

Ning， we search for similar vectors in database。 vector similar similarity often represent the similarity of this corresponding unstructured data behind it。

 So in this case， it' similarity of the images。 That's how we got the similar similar walk into sky pictures。

And then we they will get everything， yeah。And actually， besides image， besides image。

 vector searches applied to various of types of structure data like audio and documents and yeah。

 more videos。Alright， so when we talk about the vector search， we can。

 We cannot do this without mentioning face。 Yeah， this is a library at Facebook open source in 2017。

 with many sort of vector search algorithms ci。So here's a big question why on earth do we need an vector database like Ns that is also focused on vector search when we already have when we've already got something like face out there also do a sampling so let me try to break this down for you so first of all。

 F doesn't support delete and update this company so I believe this very common operations inside for any database。

And when things goes wrong， when the system fails， phase will be left hanging。

 he doesn' he doesn't have the persist persist to pick up the pieces。

And F act as algorithm library is not built for to handle the huge pile of data since it doesn't support complex distributed deployment。

So besides this， we still have so many other things we need we need for production production D or use cases like resources management。

 monitoring， data backup and so on。Okay， you may have noticed that。

 so vector Davis actually consists of vector search algorithm and database features face ands to similar to the relationship are similar toW and my。

 So how does Mis combine these algorithm and features and and what makes it So first distributed architecture allow it to handle huge amount of data。

 then I will says has a multile insert structures that provide the capability to balance the data freshness and efficiency at the same time。

 our will introduce more about this later。 Also Mis is equipped with many data driven optimization which to performance based on how the data is spell out and finally the batch processing capability supported to enable us to operate massive data and do some global optimization。

😊，Little quick question， do you do you guys like is the big vision because？

You want to have fast ingestions and do glnt updates。

 do you see middleist as being the databases of record or do you see it as like this like a elastic search kind of thing where like you have the primary database and then you stream updates to middle list and then you do all your vector surges on that。

We have both kind of this kind of I saw a lot of usage like you have a database and streaming your data into a developed database into search and also various but also get used to support this kind of very search without this backup data database。

 It's not a search engine or database。Okay， awesome， thanks。All right。Okay， so。Yeah。

 so Mis latest version is 2。3。2。 Yeah back to Mis 1。0。 It was actually a single node architecture。

 So it just simply adds some basic database features to a vector search algorithm like a face Mi 1。0。

 many includes four main modules， proxy storage index inquiry。

 and it can handle tens of millions vectors very easily。

 So which perfectly satisfied the requirement we received at that time。

 So but luckily we were we were able to foresee the huge amount of data we we got we got today and get prepared earlier。

😊，Two years ago， we began the shift of working a shift to distributed architecture。

 so each of the four modules are pulled out and transformed into individual distributed module and with a master slave pattern。

So then we introduced a message message Q interviewers like Kaafka or Pasa to decouple each modules。

 and now we get mill2。0 our current our current current architecture。When we insert data。

 it it first go through the proxy and quickly get into the messageQ and data now picks it up from there and does some segmentation storage work and this kind of storage work and so on and then put it back into the storage object storage。

The next index node takes data generated by a data node and start。

 build a index vector versus index and put it back into the object storage。Meanwhile。

 the Cur node pulls latest data from the messageQ to provide real time career support。

When we we do search the index build by index node is loaded is loaded by the current node from the object storage to local dis memory depends on what kind of index we were using。

 so along with some real time data pulled from the messageQ mentioned before and to provide the query service。

In this art design， I want to highlight some some some key points。 I'll say first。So。First。

 we separate storage and computations to boost flexibility name the whole class is micro micro serviced and managed by Kubernetes for automatic deployment and management so finally。

 I will say the messageQ helps helps decouple and all stateless couples。

And I like to go a bit deeper inside a separate of storage and computation。

This is very classical topic inside database area actually， but due to its complexity。

 most of system， including of the vector most of the vector database haven't implemented this very well。

 it took us several years of power to finally go distributed in the official release of 2。0。

 but it pays off since we've got plenty of sacred weapons for handling huge data in machine learning era。

First， I would say， for example， query index queryier and index building and storage can be scaled independently to meet different needs in different scenario。

 So second one is beside besides we will notice you may notice that the different row need different type of resources in our cases。

 props and data node IO bonded and query node is CPU and memory bonded because of the heavy vector distance calculation。

 and index node is also the heavy CPU CPU usage scenario。

 look at different resource to different roles can significant improve the cluster efficiency and reduce cost。

Also， upgrades failure recovery or heavy usage of specific role will not affect the normal operation of other companies。

 improve the maintenance and robust robustness of the whole cluster。

So independent and state index nodes and data nodes can be pulled。

 so this can utilize different usage of different users to improve the resource utilization and index building speed。

 so this is very suitable for cloud services and it is currently adopted by by Z code。

 which is based on on MES。This is a high level overview of Mus architecture and main pathways。

 so in next I would like to dive into the right pathway to show you more details about Mus。So yeah。

 this is a。Right password。Alright， so when it comes to the design detail of the vector database。

 vector search algorithm is in available topic because many design decisions are made regarding to the attributes of algorithms。

 So vector search algorithm are heard of vector database in。

 we they consumed over 80% of the CPU usage。Unlike traditional database。

 traditional database that perform deterministic search。

 which means it has to be 100% accurate vector vector database。

 the main feature vector database vector searchbilistic will I will repeat this two words so many times within this talks later this means that most of time vector vector database don't require absolute top K nearest results instead we can treat precisions for higher performance in this picture on the left shows on the left shows nowhere vector search engine it is a plugboard adapters that supports various algorithm including face series scan from phase and GPU index from video raft and its also something like library like this andW。

I'm worried。For from algorithms perspective they can be roughly divided into three different categories The first one is blue4 search I like to I didn't put it on the left graph but it's very important in scenario there requires very high precision or some realtime data search because we don't need any building build time for it so the second categories is I series the main idea here is to split the vector into blocks and then speed up searches by ignoring less likely blocks。

And the third third type， third type is the graph based algorithm。

 They are the best choice if you need both high precision speed。

 We'll cover the the basic of this algorithm next。But just to be clear。

 so many of us can support all of these these categories and like so when I start using the system and I load in say a table。

 I specify what indexes I want to build or do you guys build all of them， how do I decide？

You can say you have just you have a API called C index and you can specify what kind of index you want to upgrade and what config what parameters should be。

And then in the hosted version of middleabus， like the cloud version。

 since you see people creating the indexes， can you say like what the distribution is is like are most people picking HNSW or they just choosing the default whats if the S what's the default。

 like what's the most common the index？Yeah， I in two aspects versus from cloud perspective。

 So we in how we we support something called all indexex because we want to cover complexity of decision making of the algorithm picking。

 and so the all index behind all index is some some our self developed algorithm is a graph based algorithm。

 So we don't open source。 And in us， we have so many different of like this different different kind of algorithm and other people to speak。

 And to our experience from open source community， theW and IVF series is the most popular one。

God the most about everyone。Okay， and then but in the cloud version。

 you guys have something that looks like H andSW， but it's proprietary。Yes， Okay， all right， thanks。

All right。Okay， first， let's start with the classical IF algorithm。During the index building stage。

 we sample we sample and cluster the data set to create some buckets。

 We usually do this with with a k orbit。 Next， we assign each vector into its closest bucket。

When it comes to search， we first identify the nearest bucket to the query vector we then we search within the bucket for the result we need Yeah that is IF。

Another category is graph based algorithm， which is very popular which is very popular and widely used nowdays in this algorithm。

 each vector is treated as a node and and the nodes are connected with edges。

 The process of building an index mainly involves connecting these nodes there are various graph algorithm and each one has its unique solutions So to this building process we will skip before now during this search phase we start from an entry point and at its neighbors to the candidate set。

 then we find the closest point to the query to the query vector from the candidates and repeat the process again and again the right side of the screen shows example of search process。

All right， so yeah。After introducing various algorithms we've we've go to talk about how do we use them in the actual application？

So there are various aspects to evaluate an index， such as build time， accuracy。

 performance and resource usage and so on。 So here I many mainly focus on two basic metrics。

 building build time and performance to represented by the QPS。So here's a table。

 So this table includes flat， which which is a proof force search and I have a flat that we just we introduced just now。

 and scan scan is an I flat algorithm with some compression and C acceleration and nation W。

 This is most commonly used graph graph based index。 You can see that。

We need to spend more time building an index to building the index to get better query efficiency。

 I like to call this a trade off between data freshness and efficiency。

 So it is difficult to ensure both with within a single algorithm。So currently。

 the majority of vector database are using AsianW as a main index。

Sacrifice data freshness in exchange for efficiency。 So heres a question。

Given a single algorithm cannot cheat both as mentioned， the tele freshness and the efficiency。

 is there any chance to do it within a more complicated system， yet this is what we are doing。

sLet's take a look at how Mis tries to solve this problem first I need to introduce the data structure type types inside mirrors。

Under each collections or table in some other database concept。

 so we will have a laser called sh so each sh can read data from the message queue at the same time to speed up the data inflow so next next next is a segment so the segment is the smallest data structure unit inside of us。

 so we build one of the one of the indexes we mentioned above for each single segment。

There are two type of type types of segment， versus。Gy segment。

Cold reads data directly from the messageQ and generate this growing segment。

 we usually use the flat index to ensure the speed of insertion the growing segment is here to provide real time query capability and ensure data freshness。

The other is the sealed segment， so we when data data in the segment grows to a certain extent。

 data node will seal the segment make it immutable and then it will get handed off to the index node as mentioned before to create an index to provide the more efficient to provide more efficient queries。

The image on the right shows a general structure about one to talked。好的， oops。

So after the seal segment is indexed by index node。

 it get loaded into the current node and replace the growing segment to provide service。

 So at the same time， a new growing segment will be generated for this chart to continue support the refresh freshness。

😊，This complex structure brings benefits。But it also brings many challenges。 For example。

 how should we define the size of a segment。Should it be very large。

 So larger segments introduce challenges in distributed scheduling and failure recovery。

 so because adding segment transfer between nodes will be super expensive。 It takes forever。

 More importantly， they can be inqui slow， so let me introduce how Mils does a query with multiple layers of data structures mentioned before Mil quaries Mil quaries requires three layers of reduce operation。

So the first reduce occur at the coron level， so multiple top K results obtained from different segments on the same kernel node need to be merged into one merge into one result here。

The second reduction happened at sh level， so since segments within a shard can be distributed across different kernel。

 So the result produced by the kernels need to be transferred to the Sha leader node Sha leader is also one of the kernels for another round of this reduction。

So final aggregation takes place at the proxy level。

 results from multiple shardrks are combined here before return back to the client。Okay。

 the graph on the right shows the relation the relationship between index building time and segment size forW。

 This is most commonly use index。 larger segment result in longer index index building time。

 So and this will lead to an accumulation of growing segment mentioned before。 So remember。

W search speed is 500 times faster than the before search。

 So the growing segment could slow everything down and and effect the entire process significant。😊。

So。How do we solve this， Should we make the segment segments smaller。O。Let's make a guess。

 so which is faster， which is faster in a search operation， a larger segment or many small segments。

The chart below shows a search speed of ancient software at different size， ranging from to a 0。

25 million to 1 million vectors with 768 dimensions。 So maybe its anti intuition。

 There is there is almost no visible change in performance。

 He means with constant total amount of data， Each addition segment makes our search slower。

So in addition， since each segment requires its own met data。

 having too many small segments can greatly increase the pressure on met data storage E city in MIA'。

 therefore it seems that very small segment won't work at either， so what should we do then？

But just to be clear， the grown segment is it's a flat index， right， not the HNSW。Yeah， it's a yeah。

 because I are building is super slow so we need to make so so the growing segment need to serve a data freshness so it's's a flat Okay。

 okay， all right so like your diagram here looks like looks like your table like it looks like the graph structure of H andSW。

And this is okay，那 graphs try to explain that when when when no matter how big your your graph is。

The search time remains the same。So if you have so。So for HNSW or for flat。

The fluation sub its a graph okay， okay， but but you talking you're talking just be clear。

 but the small growing segment is the flat index， though。Yeah， when talk about small growing segment。

 Oh sorry， I， I say the title is a small growing segment。 There's a one more111，1。

1 more things behind is small growing segment leading to small sale segment。 Get， Okay。 alright。

 Thank you。Yeah。Okay，Since we prefer small segment when when in certain data and large segment。

 the larger segment once is the index key is built as mentioned before。

 because the growing we need to with the proof force。

 we need as small as possible and the the supply this kind of thing， We need to as large as possible。

 So why we not just build a small index first and they merge them together basically。

This is why we're doing， this is compaction mechanism is available。呃It sales呃呃。

In sales segment before they get in too big during the insertion process。

 you ensure the shop building time and data node actively merged more smaller segments together and which then passed to index node to build an index。

Finally finally， the kernel notes this loads this bigger index and replace the indexes of the small segments that were merged。

 Now we have a larger segments to support more efficient search。

It seems like we have solved this problem， but what if the index node is super busy for example。

 when the resources is limited or when the insertions when the inserts occurs rapidly？

So it's about a growing index。 Still remembers table。

 our choice are not only limited to the proof force search and graph graph algorithm。

What about IF and scam。As a middle solution for growing segments。

The indexing time for scale is less than one fifth of AsianW。

 but its performance is 200 times comparing with the Google search。To adapt this idea。

 Mi supports using initial part of the data inside a growing segment as a sample for classroom as mentioned in the algorithm part before。

 to build a bucket and then all subsequent inserted the data in this growing segment in this growing segment will be simply placed into this corresponding bucket。

 so it will be super fast。You might still concern whether the build speed is fasting enoughvada。

This chart shows the relation between the amount of inserted data and type with three lines representing proof4 search。

 I flat and scan representative。The bound in the the bound in the middle of this line indicates the start of the clustering due to the system overhead such as massQ。

 write and Ra， network communication， and so on。 So there's actually no significant speed difference between the three different solutions。

 This means that no insert speed degradation。 but 200 times faster in growing segment。 Yeah。

 this is a good way to go。In additions， we these design ensure that the final index in is mutable。

 Therefore， we can choose choose the most suitable optimization strategies based on data distribution during the index building time。

 such as some compression and pruning strategies。 and also even if the seal index。

 the seal index isF or scan， which is same as a growing one， because because in the chlor segment。

 we only use the initial vectors as as sample。 this will make the quality of the index get effective。

 So reining the immutable segment is still very necessary。W。

 sounds like we have solve the issues of both state freshness and efficiency data data balanced the segment size and accelerated the growing segment。

 So anything else。In a typical vector database， application scenario。

 unstructured data is transformed into into embeddings through a model and then inserting into mus to provide search capability。

 However， as model are frequently iterated， vectors need to be regenerated and result a large batch of offline a batch of offline vectors that need to be reimported to mus。

 So how do you mills deal with this offline import scenario。

In addition to support online scenarios with streaming insertion mission before。

 Rams also support some offline scenarios through batch insertion。

Okay mainly through mainly through three password first is allow the direct transfer transfer for of raw data to the object storage this can help keep complex insertion process from proxy to messageQ and data node need to be read by read out by the data node and get part and then get rid into the object all this kind of stuff and also index node also this approach can bypass bypass the issues associated with compactions and growing segments。

 the index node can directly read the data to build the index and it can greatly improve the efficiency of data rating。

So you speak very clearly， so this is saying that like if you could have some spark job that is ingesting data from something else。

 and then you have it right out to S3 or whatever object store you're using and it's writing out into a middle of a specific file format or is it is it just like parquet files or something？

It's pa。 So you put p here and the index that we' arere doing that。 for you。 Okay， awesome。Alright。

 let's continue。 so the second pathway is is a spark。

 so data can be imported from imported intova via spark。

 So in Sp users can define some data pre tasks such as embedding instruction from the unstructure data data filter and so on。

The third pass we data can be can be batch can be batch export froms to spark processed and then imported back to to intos。

 we can perform some optimization based on global distribution of this data。 So for example。

 the code will period export all vectors froms。 And remember the IVF index。

 we mentioned multiple times before。 So in Sp will perform a global IF indexing and make segment each segment bucket。

So， and then import the data back to back to As to during the search。

 we can skip most of the segments based on their distance from the from the query point。

 So this achieve performance improvement。Okay， now we have finished the introduction of Mu's data writingri path。

 and I would like to briefly review how the features we've discussed support machine learning。

A simple machinery pipeline can be roughly divided into offline data process preparation。

 or model training。And online model deployment and it efforts。

So from the offline offline perspective， a typical use case is data mining through similarity search。

 So let's take autonomous driving as an example。 So imagine an autonomous driving vehicles encounter a bear on the road。

 So it is unable to recognize what is what is the what what this and unable to take the appropriate actions。

 So in my large closely。And get a bear pissed off， which is quite dangerous to make sure we we don't mess up next time we see a bear on the road。

 So we need to first improve the capability of our perception models in f classification to recognize the bear。

To achieve this， we need to add images of bears crossing the street in our training data。

 as you as you know， we don't， we don't see bears crossing the street every。 Yeah rare。

 So rare data rare， rare data like this requires specific data mining。 and commonly。

Comp use approach， company use approach is extract the embedding of the bare image。

 then search search for image with similarity embedding in the databases comms and which usually contains thousands of hours of driving records。

Data mining and model training are always accomplished with very large dataset set。 for， Tesla。

 as far as I know， Tesla's training that said is is in of billion is size meals flexible distributed architecture and can handle large scale vectors quite very well and these batch processing pathways provide fast insertion speed and more convenient ETL pipeline。

 These two factors together give meals capability to handle scenario at the billion scale level。

On the online side， in addition to classic search and recommendation。

 vector database vector database are also important in hottest domain L， the large models。

 So in this area， agent is typically the agent is typically scenario。

 an agent is an AI system based on LM that can auto complete all complete complex tasks through multiple round of dialogues with LM and the third party interface call。

 So in in an agent system。 So the M is forgetful brain while the vector database is hippocampus。

 the memory loss the memory loss makes every interaction with LM like starting over again again from scratch in a close in closed book design。

 This prison。The presence of vector database turns this processing into our overbook MLLC。

On the other hand， the agent， the agent system can browse domain knowledge and private data and provide provide to LM to make answer more accurate。

 and also the agent can recall its own operations history。

 better understanding the user's in and achieve better personalization。

This scenario has high demands on real time insert speed。

 performance and database of a very database and these issues numerous streaming insertion scenarios Act seek to address。

Yeah， so because we don't want to say we have a rubber here and we talk with them and he reacts super slowly。

Well， this seems like Mus has converged on the pathway to supporting in machine learning。

 we must feel very sick to stick where we are here， their cheers。No。

 so vector database is completely new field where so where all solutions are far away from mature to。

 So also， new challenges have just arrived in era of AI as machine learning develops faster and faster。

 we also need to constantly think and change to catch up with development。

So next I want to share with you some my thoughts about DP for machine learning and machine learning for DB and the directions we need to consider in also the directions we need to consider in the future。

There are no clear answers and solutions for these questions here。

 and I hope this can bring some food for sorts。With machine learning technologies evolving models rapidly enhance their capability to understand more complex semantics。

 meanwhile， search technologies are that boosted by machine learning also get involved。For example。

 once I once I found an incredible comfortable pillow at a friend one of my friend's house。

 then I decided to buy a similar one and try to search for a search for it online。

 think how let think about what would happen in different development stage of search First。

 in the first stage of the keyword search。 I would just type a pillow as comfortable as a cow。

 And what is the result。😊，Yeah， maybe I will get a claw shape cookie cutter and will some pillows or of course。

 it can also be a pillow that looks like a cloud。 Yeah， okay。

 so next step is to browse through all products one by one。 that takes a forever。😊。

Moving to an access stage。 So now we have image search。

 I just remember that I happen to take a photo of my friend's pillow。 Okay。

 it looks like I can do image search with that。All we got， Yeah。

 at least I get a lot of pillows at least had no cookie cutters。 Okay， so let's browse。Next step。

 now we have some multimodal search， we can provide an image and as description a pillow as comfortable as called。

What I get this time。 the search isn't just about simple image matching animals。

 commentsments and descriptions on softness of the pillow are also taken into consideration in this search result。

 So finally， we get in this time， we found the target pillow。

 It looks like it looks similar and to the what I saw and super soft。

To keep up with fast growing machine learning， so vector database also need to be more smart when searching for similar images。

 we would prefer the search searching result to be similar to the original image at a semantic level。

 not just a similar outlook。Let's take a look how how vector database define similarity。

 So currently almost all vector database define similarity between two vectors based on。

The distance of the vectors are in L2， I P and cosine space。 it will I will I。

 I will call itman similar。Semantic similarity and corresponding mathematical se similarity and correspondingly。

 semantic similarity represents a real object similarity of two data。

 The current presumption is in vector database is that these two type of similarity are equal equivalent。

 So the question is are are they the same。As I'll say， it depends and or or say most most not。

In fact， the academic award has a lot of search in this area try to solve this problem。

 so there are many solutions， for example， using user defined distance calculation。

 it can even be a machine learning models or you can directly use a model inside a model inside of the inside of an algorithm as an index to do a similar search。

So the feasibility of these approaches and how implement how to implement them or whether they are any better method to address these semantic understanding issues in database。

 all these directions we need to explore and find answer to。

Next one is about some dimensionality curve。 So as model grow larger and more complex the dimensions of embeddings。

 the extractor are also increasing。 So at the same time。

 to repeat more complex to to represent more complex semantic info。

 vector dimensions are also getting larger， larger。

This process brings a significant challenge to the storage and computation of vector database。Also。

 high dimension can result in distribution of the data to become extremely sparse。

 This makes semantic inference more difficult to be measured by the existing existing metrics like L2 or IP these countries。

 This is a perspective of curve of dimension I。Therefore。

 how to reduce a dimension and compress a data is very important topic in the related fields。

 So there are some dimension reduction algorithm on the model side trying to solve it such as PC and T SNE discussinging。

So if in the field of vector search， there are also many different quantization algorithms such as PQ and SQ and AQ discussing thing this algorithm sacrifices accuracy for better storage usage and performance。

However， the sacrifice accuracy is from the perspective for mathematical similarity。

 so therefore very important challenge is how to compress and reduce dimensions while retaining as much semantic information as possible。

😊，In addition to the database catching up to support machine learning。

 machine learning can also help enhance the database。

Machine learning based auto machine learning ML based auto tune is one of the most mature scenario just like auto tune what this audit is doing。

 right now so。In fact， compared to the deterministic search method of traditional search。

 ever tuning can。Can can play a greater or bigger role in that vector database area。

 as it's a probabilistic search allow for more for flexibility。

 So aside from the performance improvement， vector database need to maintain relatively stable accurate accuracy under different searches to support business scenarios。

 And this is another area where machine learning M20 is needed。😊，Taking taking the IF index as。

 as mentioned earlier as an example。 So from the from the performance perspective。

 besides a high level adjustable parameter， similar to traditional database。

 there is also a big space in the algorithm side。 user can adjust the number of sample。

 the number of bucket， the number of bucket involving in the search type of compression used in each bucket and the extent of compression this or and so on。

 So， and from the using usability perspective。😊，When we try to search the top K nearest the points。

 the different value of k， the top K how many K you want to get will affect both performance and accuracy。

 So for example a larger K obviously require us to search for more buckets to ensure the accuracy so therefore we need to dynamic assign different strategies to each query different parameters。

 different how many bucket discounts into each query so is this called when user to search we will have model that will take the size of segment the number of segment the type of algorithm and size of k all this comes into consideration and dynamic and generate parameter to ensure the accuracy accuracy stay within a relatively stable range。

But isn't a challenge though because it's like approximate it's not like like like using audittri example。

 like there's a hard objective measurement we can use to say is is the AI making the system better like is the P99 latency going down in your case it's this fuzzy thing where it sounds like you're adjusting you they how many K items you look at but like the end user won't be able to say oh yeah。

 like this is better than I would have had before because like it's a subjective response anyway。

 the answer is like you know its subjective to the context of the person what they care about so it seems like auzz fuzzy thing to measure to try to improve。

Actually， I think the most important necessary is from the userability perspective as mentioned before。

 so when you do a search。Maybe it's subjective that the record the precision accuracy is what is what。

 And， but you will have some underlying expectation that the result will be like this。 For example。

 if you if you have a very very big and you only you only browse to bucket as mentioned here。

 So the accuracy will be super low。 and sometimes you search on Google that this time it is yeah relevant。

 it is good result And the next time you try to search more。

 you it more pages and un irrelevant at all。 So that is not totally not acceptable in real productions never。

 So it is super important to maintain the accuracy in in a original range。

But what's the feedback mechanism to know that you're doing， you're doing well。

 you're doing better than maybe you were before？No complaining from customers。 So if you do nothing。

 of course， you will get some because， because the accuracy will change。

 The accuracy will varies with a different K。Okay， all right， thanks， keep going。Yeah。So finally。

 let's let's get back let's go back to the two questions posed at the beginning of this talk。

 question one is what is the relation between traditional search and vector search。First of all。

 vector search is not replacement of the traditional search。

 but complementary traditional search focuses on more on keyword matching while vector search focuses more on the context of a sematictic matching。

Soly， many search system contains both keywords keyword search system and sematictic search system it gets when it gets result from both modules。

 there will be a post process step working on result merging and reranking。

This is most is a common perspective， and we start to rethinkration between traditional search and ver search。

We divide our keyword search into two parts， spa vector extraction and spa vector similar to search。

So we can simply use a traditional sta based method like BM25 TFIDF these channelsops to extract the spa sparse vector and use a proof force on the sparse vector on vector search to replace a classic keyword search。

This structure can brings more flexibility， for example。

 for from the perspective of spa vector extraction。

 learning based method can also be used to enhance understanding of hidden semantic informations。

Like a displayed model。 it's a very hot models these days and admission mentioned here。

 So for spa vector search search， in addition to use exactly exactly search like before。

 we can also apply some similar to search similar searches like what we do in the dense vector tree these trees a little bit of accuracy to accelerate a search search process。

 So I like to call this process of vector rising traditional search。Following is。

 let's think about the second question。 One is the relation between traditional database and back database。

 So let me give an example What what what can we do if we need to use a picture of dog to find three most similar type of dogs。

A conventional vector search would return three most similar talk images。

 which in our case are snowy 1， snowy 2 and snowy 3。 Okay。

 you might notice that this is a classic group by scenario because you don't want a snowy。

 you want three different kinds and this is classic group by scenario so。

It looks like we can try blue by dogc's name and link search for most seminar image J in each group in each group。

 and now we getnoy， coffeeoff and Pluto。Let's， let's take one step further。 So what is。

 what if the database doesn't have the name column for us to provide。嗯。Yeah， so then we guess be 13。

1，2，3 because we don't have the name on。 So sounds like we need some need to group by the image directly。

 So this means that besides a determin stream matching。

 we also need a capability to group vector through probabilistic similarity。Now。

 let's simply group by the image vector themselves and the the vector database will group similar snowies together and brings coffee and pluton back。

呃， now let's呃 let's呃 beside besides a group I。BesidesBesides group I we can also have aggregation based on it or join operations and other functionalities。

 so we can see that the features required for traditional database also apply to their database。

It is just that we need to reimment them in a probabilistic way rather than traditional deterministic way。

 So similar similarly， just like vectorizing traditional search this。

 I'd like to call this virtualization of traditional database。

 So actually in the era of machine learning， we we we we vectorized text into token image into queries and we vectorize everything。

 So。I like to leave a question here， so what else the can we think of that is on the way to be vectorized in the future？

Yeah。Yeah， that is all from my all of my tops and thanks to any questions。

I will applaud on a half of everyone else again， thank you Lee so much for being here we have time for one or two questions from the audience if anyone wants to go for it。

All right， so I'll ask my question and maybe you might have mentioned this I just missed it the you guys have the ability to do like searches with the。

Like the non the non embedding like so if I want to say show me all of the documents that have this sort of keyword semantic search piece and that goes to the transformer that gets an embedding and you do the approximate you know sulator search and the vectors on that。

 but then I also want to filter where the document is older than 10 days。

 how do you guys handle that are you embedding the additional metadata or the attributes about every entity or object in the index itself are you doing a separate search。

 how does that work for you guys？Oh， so， so so sorry。 So do you mean if the data is pretty old。No。

 no， no， I mean just like how do you handle combining these semantic search based on the vectors plus the or sorry simulatory search based on the vectors plus additional like scalar attributes to do additional filtering like where clauses like where age is greater than this or where country equals equals Canada or something like that？

Okay okay， so this is we called filter search。 So we also we will have do a same。

 So we will have I would say vector database is not replacement or something of traditional database just extension because we also support something traditionally。

 have this scalar column and we will do some have some we can we will do filter with inside and we will generate a indicate in this vector segment which point is get filter and then we pass this to the to the algorithm。

 algorithm will use it to do the search and this is how we do the to the filter you filter on the scalar values first。

 then do similar search actually it on our roadmap tube。

Make it more complicated because we notice that pre filter and new filtering and filtering means that we I want to mention before。

 So we do the calculation before calculation before。

 and then we do a vector and in filter means we do the vector and in the meanwhile。

 we do the scale one And some some post they have different they are suitable for different kind of scenarios。

 and we need some analyze here to say which one to go at the first at the very beginning。 So yes。

 this on our roomm。Okay， so then does that mean do you have？

Do you have a notion of of selectivity of the cardinity of predicates beforehand？ And like。

 is that like for scalar， for Scalar column， you know。

 there's wellknown textbook techniques to do this。 But for like the indexes， the vector indexes。yeah。

 it's hard。 And and also it's very it's a little complicated inside the vector because for different kind of algorithm。

 the filter will have different kind of problem to solve for example。

 I have things this bucket based obviously thing is you need to enlarge bucket involved to get very good accuracy and for the graph based things another problem is if the filter rate is too high which means so many things out and you need to decide whether you want to use this you want to go through this filter point or not if the answer is yes。

 you will be super slow and the answer is no there will be island you inside your graph。

 you cannot go out。 So the accuracy is super super low。

 you should have some special solutions for it。 And also this is what we are doing right now。



![](img/9205305a962aa02e613087b9ff6e1757_4.png)