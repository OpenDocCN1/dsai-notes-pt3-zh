# 吴恩达《数据工程（导论，源系统、数据摄取和管道，数据存储和查询｜1-2-3课）｜DeepLearning.AI Data Engineering》 - P152：14_可选：与Juan Sequeda的对话.zh_en - GPT中英字幕课程资源 - BV1wTtWeeEH5

What's up what are you doing Great Joe are you doing good good so when I think of graphs and graph databases you're the first person that comes to mind so I figured let's let's have you educate the learners on graphs so I guess for further learners who don't know who you are do you want to give a quick intro by yourself Yes so I am Juda I am the principal scientist and the head of the AI lab at data world dataorl where enterprise data catalog but top on top of a knowledge graph architecture and graphs and knowledge graphs have been what I've dedicated my entire life career at so。

😊，So yeah I'm here to talk about all all things graphs and I can talk about this for hours。

 if not days， so I think we've had it about at least for hours before yes。

 so yeah let's it's up for square one so what's what's a graph。All right。

 so a graph is a data structure which consists of nodes and edges and if you think about it mathematically or actually from set perspective。

 you have a uninary predicate or a uninary imagine set only has one thing so just imagine like a table would only have one column a unary and then you have binaries which is going to be basically imagine a table has two columns so that one that has one column is going to be the node and the one that has two columns is going to be the edges and regard the bubbles。

 the dots that you draw and the lines are the edges which are going to be the relationships between those and that's the6 structure is this kind of like parent and child relationships is that a way to think about now now we're getting into semantics and stuff but yes。

 that's when you see that the setic the knowledge part。

Lives on top of the graphs because okay the moment that you start saying， hey， that edge。

 that relationship， there's a meaning to it and then which is more than just saying a is connected to B right so let me let's back up here so we have we have nodes and edges and then more nodes is that a way to think about it like node and then edge then note here or and what are these represent so technically a graph could be just you can have a graph which has only one node right dot that's it I can have a graph that has just a bunch of dots's it then I can say there's a graph and then there's edge that connects these things a line right that that's that relationship between two dots and then this is how things get start to grow and then you can start seeing the characteristics of a graph is how many edges does it have how are there clicks within a graph what are the paths between different nodes in a graph and those are the types of things that you'd be asking around just to graph structure。

Interesting and so let's get into this a bit then so there's graphs and then for the learners in this course we'll be using a graph database of what's how do these things relate to each other so let's go back into what is a database so a database right is is is a collection of data I remember I remember my first courses on database somebody pulled out remember those yellow books。

Somebody is this a database？It is you're collecting data in there right and and then you can do and then so that's the database is a collection of data so then we start thinking about a database management system of DBMS so database management system is a way how again I manage the data that's inside that collection and inside and then you have different types of management systems for databases the traditional one we hear about our relational databases and that's where you are using a particular model for the data called the relational model which is basically our table so we go do then you have a graph database right which is really a graph database management system where it's a system that is been designed to go manage data in the form of a graph and by management of data it's usually all the current operations right so I'm gonna create read update and delete anything inside that collection of data so graph databases then you have relational databases and then you have this whole era of no SQL data。

ase ended up being that people were basically saying they're not just the SQL relational ones so that's where graphs would come up you have the document databases which were really the JSON I mean heck there used to be the people would call XML databases back in the 80s we had objectoriented databases where a lot of the XML and kind of document stuff came out and a lot of the object database from the '80s has a lot of the graphs and stuff so。

That's a little bit of the where all this databases come from。Okay， so we could use a database。

And I guess query at graph then is that what you're saying Yeah so that's important thing is that one thing is that you have the storage right a database stores things but you also need to be able to go access them so that's when you have query languages right so you have a data query language databases have a manipulation language which is how you do inserts updates deletes and then they also have usually the schema right basically in SQL it's going to be your create table statements you want to go do so if you think about a relational databases you have your query language which your select from right and then you have your selects or where you're querying from you have how you can insert data delete data update data and then you have all your create table statements how you create the database you have the equivalent of those things also inside of other graph databases Go it。

And so let's walk through a couple models here the one that comes to mind is something that I've seen called RDF and there might be another one called a property graph but what's the difference between these two so theyre do different types of graph models so again just to the analogy people get SQL all the time so SQL is just your tables and you have a language of standardized language called SQL and that's actually standardized by ISO so it's one of the organization has been standardizing this for 40 plus years or more so then what happens by the way the relational database of the model comes from the database theory by CAd that's where all it comes from the 70s so then you have that same type of theory and stuff that has developed in the graph world so two perspectives one is called RDF which stands for the resource description framework and the other one is called property graph which is really kind of originally was popularized a lot by the folks by Neo4j。

Very early on， like 10 almost 15 years ago， I would say。

So let's go down this the RDf route the RDf actually comes from the web so comes from the web community so what happens when the worldwide web consortium starts out as kind of the standard organization for the web the web is all about having it's a graph of documents right these HTML pages documents that can point to another document and what really happened was that the original vision of the web by Tim Berns Lee was it's not just about documents pointing to other documents I really want data to point to other data and be able to describe what this data means so RDf was the manifestation of the standard for data while HTML is a standard for text so you can imagine text web pages have HTML data has RDF so。

Because you're following the graph that you're following the web which is you have a page links to another page you're basically creating a triple that's where the triples come from so the RDF is a model based on triples which is subject prediiccate and object so very good object okay going back to the graph model node edge node。

😡，Subject predicate object and guess how we talk in it was in English you have subject verb object So these things are all very related to so that's what the RDf model comes in and it comes actually was originally kind of proposed presented back in the 90 I think like 98 actually and it was really a way to start the first uses of it was how do I describe what things on a webp page so it was basically adding with just metadata annotations on on a document and it was all just triples all just part of a graph so you were say hey this document was written by Joe Reese was written this document was written on was the date that it was written was on January 1 right so you're adding all the graphings。

What happened is that that was made for the web kind of for annotations and later on people said， oh。

 now we're creating more and more of this data on the web we need to have a way to go store it so that kind of the the database was't after the fact。

 so then database systems came to go manage RDF and you start seeing languages that were standardized by a W3C called Sparle so Spkle is the graphraph query language for RDF。

And then we started seeing how to go manage more of the semantics because these links have a meaning。

 I want to add the semantics， the meaning the modeling around this so just so you're saying kind of taxonomies and stuff those ended up being part of the standard and things like RDFS called RDF schema and then things like oL which is the web ontology language you can go more into that stuff。

 but so there's that whole standard over there on that kind of triple based model。

The property graph is something that it's again， also nodes and edges。

 but what you can think about them is that you have key value pairs that can be associated to a node or associated to an edge。

And that's really the other model they have and I think the way the property graph started was more was less about thinking about I want to share data on the web was more about oh I want to create graphy applications and and so so edges are firstclass citizens and I want to be able to store things around the nodes and the edges and so there were a database first mentality and I think originally Neo4j didn't even have a query language it was all three As and then they created a language called cipher and then other different。

Daatabase systems followed that property graph model which is key value pairs on nodes and edges and then I think there was this big movement to kind of create a standard for property for language and what Neo4j did was kind of open sourcer language they called opencipher and then in the last couple of years a lot of folks got together to say hey kind of different visions of things so I was part of a group called we created a group underneath the LDBC the Link Data benchmarkchmark Council to propose a language for property graphs and we called that GC and that's basically we kind of just sat together and saidy if we could design a language from scratch what would the ideal language look like so we developed that and then all of that went inside of the influence the ISO standard so right now the same way ISO is the standard for SQL ISO has not created a standard for theque languages for property graph called GQL and that's coming out soon that is the first time that it's ever standardized another career language ever 40 years so。

That's an indication of how the world is going。Yeah， it's crafts。So。

I guess for the lawyers out there， they've probably been exposed to the relational database or exposing them to variations of different types of database。

 but mostly things that storear data in rows and columns， right， or maybe semistructure data perhaps。

But the graph feels like it's a bit of a departure from these types of databases and storing data and querying it why would somebody want to use a graph database versus say a relational database。

Great question and I'd love to dive into this。If you think about the relational database one of the things is that you have to define the schema upfront right so now again if you're starting to to store JO blobs in there then you're really not really using the relational schema somehow you're just kind of you're making so the point is where is your application where is the logic going to be embedded right so your logic of what things mean should be inside your relational schema and if you have fixed requirements you have a fixed application that you're building then do you use a relational database for that that's exactly what it's meant for you you have the requirements you know what it is you know what are the types of questions people are asking you can optimize for those query workloads and so forth that's what a relational database is for now when it comes to graphs。

I think first of all there's the graph model itself。

 these triples these nodes and edges by nature they're very flexible right it's something I can just go I can easily add nodes and edges without that think about it in a relational database not have to change the schema schema have problem at the table right if something was one to one I'm going make it one to many I got to go refactor all these things right so there's a lot of work they to do if there's a lot of changes that are going to happen or if you have a lot of you have some known requirements but you know that there's things are going to be changing a lot so the graph is a very flexible nature just flexible by nature so if you have requirements where things are changing then already graphs is one of the reasons why you want to go deal with things the other aspect is that。

It's a minimal it's a higher level of abstraction so if they always think about a computer science is always about finding different levels of abstraction and as a technologist in computers。

 you kind of find where you're comfortable and your level abstraction and that's kind of where you dedicate your career at basically or something to become a compiler right I work great between these two levels of abstractions or I'm an expert in moving between levels of abstraction so you work in UI right you work all the way down at the bits and the chip level right or this is how these all changes now when it comes to graphs I think it's just a higher level abstraction。

So when you talk to users and hey how do you think about something let's go draw it on the whiteboard you end up drawing bubbles and lines so I think you have this higher level abstraction that you want that you want to be able to kind of what I call bridge the data meaning gap so I think if you want to be able to focus a lot more on what is this stuff mean and this mean is changing that's where graphs come in and then also if you have all this let's call it just graphy type of questions right I want to know the paths between something I don't therere one of know other clicks I of the centrality around things right these are applications are I mean graphic type of applications recommendations right you want to go do fraud detection network analysis around that。

😡，Then the other thing is that graphs is this minimal common denominator I can turn any other model that I want into a graph you can take tables turn into a graph。

 you can take JsonN XMl treebased structures turn into a graph when you do NLP and you want to codify it you're going to extract entities relationships turn into a graph so a graph is this common denominator that if you want to start integrating data coming from so many different sources known sources and unknown sources it's just has all the great features around that and then I would argue if you are trying to go do that inside of a relational database you're going be doing so many changes that you're going to end up building a graph model inside of a relational database and therefore when you start seeing that you're like well you should have started with the graph so I think that's why if you're doing a lot of data integration metadata management cataloging that's why data world is on an anothergraph because it's all about bringing metadata from so many different places and you really want to manage all types of。

Data that graph is the ideal structure， so my long one answer to say if you have very fixed very fixed requirements。

Stick with do you create your application a relational database if you're bringing in data from so many places and things arere going to change it and evolve。

😡，Then you're naturally going to be thinking about a graph。

And one word that you use a lot when we hang out and one word you post online a lot is the word knowledge。

What's a knowledge graph and how does it differ from a graph？

So I think so a graph consider it just as the data right the points around how and they're related the knowledge really is capturing the meaning given me first way to think about it having a schema right and this schema can start evolving to have more richer information so for example you can say there are orders and there are customers okay orders are placed by customers then I can start adding some type of cardinality it can say hey an order can only be purchased exactly by one customer but a customer can purchase many can place many orders and then you can start thinking about adding more information around taxonomy so for example we have geographies and I want to know things about cities and states and regions and so forth I have orders include the products that I'm selling there's a product taxonomy around these things so I want to be able to start connecting all that stuff and together I want to be able to then do some reasoning if I'm。

Interested some I don't know in cosmetics， for example。

 right in cosmetics is a superclass lipstick is a subclass of cosmetics and stuff like that right so you're starting to get all those relationships right those hierarchies in there and you can get much more richer and richer information and that's what I mean by knowledge right there so if you think about just the graph per se you're thinking about just like the raw data but then the knowledge parties was actually bringing in all those semantics that meaning and it's connected to what users how the users think about are thinking about that domain。

Interesting。And。I guess you know we're filming this in 2024 and large language models are incredibly popular yeah and I know that you've done some research recently on the impact of knowledge graphs on large language models you kind of walk their learners through the impacts of knowledge graphs on LONs so what's happening right now is that。

We're all obviously in the hype of LLMs and I think what's really important to understand is that these LLMs are trained and they know they quote unquote no。

 they do seem to know here， things that are they've been trained on and a lot of it is just the data and stuff that's on the web。

Now it doesn't necessarily know what's inside of your organization Now a lot of people are saying oh I should just train this thing with me I'm like I should just train it with my data I'm like only a handful of people in the world can probably start training things and that really you don't even people don't even have the time or the money the people to go do this stuff that's kind of really not that feasible now even if you were to train that your data is getting updated all the time so you can't something not very feasible at this moment so what these LLMs don't have is the context the semantics。

 the meaning of your organization so a lot of the what people are really interested right now with these large language models is to go chat with their data and I think a lot of the chatting been doing over documents over text and being able to do embeddingies and put those into vector databases forth vector data and other database databases to manage vectors so what happens with your data that is in your structured formats or data that actually。

rich meaning around that so people that's where the whole text to SQL thing comes around。

And a lot of the kind of the thoughts we are having is like oh I can just use LLMs to generate give it a question and generate the SQL query for me I think that's where people have been at kind of their mind was that probably a year ago and many of us were like yeah technically it could work but how well does that work and how do we improve that accuracy and the hypothesis was always well these knowledge graphs actually have all that context so a lot of the experience that we did late last year was to be able to test this question answering over using LLMs and saying hey if you want to go answer questions over your SQL database and if you want to if you add a knowledge graph if you don't add a knowledge graph what's the difference Well long story short with the research that we did was like three times more accurate if you actually are putting a questions in terms of the knowledge graph and specifically I mean you're taking the question and you say translate it to a sparkle graph query given the ontology and you compare that take that question and translate it to a SQL query given your SQL schema。

Just with that very simple prompt it was already three times more accurate using the knowledge graph now this is just a baseline this is just a starting point and what we're seeing is so many people have been validating that work and showing oh they're not only just validd。

 but they're finding ways to go improve it。Now one of the things that hypothesize why this is actually better because really don't know what's happening inside of LLM is that language right LLMs are language and we started off saying hey these are subject bird object these cripples are a subject predicate object so they have this kind of language in there so that's one thing and second is the relationships in the graph are firstclass citizens right's something that you're managing that you understand what this relationship is and you're giving it a name。

 giving it semantics meaning while in a relationshipal database it's really implicit inside of the foreign keys and that's even assuming you tell it what the foreign keys are and maybe the names of the codes that are being used。

 the column names are not really that descriptive so you're like well I just have more context inside of the knowledge graph。

And I effectively tell people that if you're trying to go add all that context to your relational database。

 you're going to be building a knowledge work anyways。

 so invest in your knowledge graph from the beginning and that really is that context and that's the engine that's going be powering a lot of these AI apps that want to go talk to your structured data。

Seem to be the case I guess closing out is there anything else you would tell somebody who is new to graphs or knowledge graphs and maybe some advice you'd give them on learning more about them Yeah so first of all。

 this is a paradigm shift。It's a social technical paradigm shift and I think one if we always look at tables and tables always been our lives right then you think everything can be solve with tables and so I think the quote I use in my book is the limits of my language are the limits of my world from losing right so changes hard so my suggestion is let's be open let's go try things let's try to get out of our comfort zone and see some and try to try to figure out see things outside of our bubble that's number one another thing is。

This isn't just the latest greatest thing that people are inventing right now graphs have。

Centurries right and the history of knowledge graphs go back to long time and I encourage people to just look at I wrote a paper a couple couple years ago talking about the history of knowledge graphs and I think it's just a great pointers of where you can go back and a lot of the things that we're trying to go do today。

Or just things that we have been doing in the past。

 so just remind ourselves that we want to stand on the shoulders of giants and let's not spend too much time reinventing the wheel and understand what's been out there and it it doesn't mean that what's out there is perfect we can use it but we should just go build on top of that instead of just thinking that we're just it doesn't exist and we start from scratch and be proud of building something from scratch when you've really just wasted time。

Awesome， that's my honor yes， suggestions。😊，That's awesome well thanks for your time onem sure that learners will get a lot out of this discussion so thank you very much all right thank you for having me anytime。

😊。