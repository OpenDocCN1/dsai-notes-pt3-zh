# 吴恩达《智能体驱动的知识图谱构建｜Agentic Knowledge Graph Construction》Claude-4-s翻译 - P11：11.knowledge-graph-construction-–-part-ii.zh_en - GPT中英字幕课程资源 - BV1AShCzoENH

![](img/7479beb84ff34a83faf6d4c678d9097c_0.png)

In this lesson， you will continue the knowledge graph construction。

The previous lesson created the domain graph from CV files according to the construction plan。 Now。

 you will process the markdown files， Ching them up into the lexical graph and extracting entities into the subject graph。



![](img/7479beb84ff34a83faf6d4c678d9097c_2.png)

You will learn how to use the Newuverj GraphraG Library to perform the chunking and entity extraction。

 you'll also learn about techniques for doing entity resolution。



![](img/7479beb84ff34a83faf6d4c678d9097c_4.png)

Ultimately， this will not be an agent part of the workflow。

 this is going to be handled entirely by tools， so we're going to define some tools and also some helper functions that those tools need to actually do their work。

The two tools we need are one actually constructing a knowledge graph builder。

 we're going to have one builder per file and have it process the files to do the chunking and extraction。

The other function that you'll define is correlate subjects and domain nodes。

 these two tools together will do the graph construction out of the markdown files and then take the resulting extracted entities and correlate those between the subject graph and the existing domain graph that was previously created from the CSV files。

That might be a lot to take in right now。 It'll make sense as we go through each step。

 As with the other note bookss， you will begin by importing the needed libraries。

 So let's go through doing the common setup。

![](img/7479beb84ff34a83faf6d4c678d9097c_6.png)

All the libraries that you need。Wait for those to import。



![](img/7479beb84ff34a83faf6d4c678d9097c_8.png)

Good， make sure that open eye is ready to go。And also check the Ne forjs ready。



![](img/7479beb84ff34a83faf6d4c678d9097c_10.png)

That all looks good。Now as part of the setup here， we need more than just the previous state that we had in the previous lessons that were created because now we're not just doing the workflow。

 the previous lesson actually created part of the graph in Ne for J。

 So because Ne forj will be fresh when we load this notebook we need to add actually some of the product nodes that were created in the previous lesson and we've got a helper function for that。

 So this helper function load product nodes， we can just go ahead and load it and then call it and what we're going to expect is that the only nodes that exist inside of the graph have the label product。

Okay， that worked correctly， that's super。Now you do need some of the initial state for this agent and the initial state should be part of what was created from the previous parts of the workflow and the same kinds of things we had loaded before。

 we need the construction plan and the approved files to actually work with。

 and also because we've done some of the planning for the entity extraction。

 we need the approved entities and the approved fact types。

So we're going to create each of those initial states。 Here' is the approved construction plan。



![](img/7479beb84ff34a83faf6d4c678d9097c_12.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_13.png)

。Here are the approved files。

![](img/7479beb84ff34a83faf6d4c678d9097c_15.png)

The approved entities and the approved fact types。Okay。

 you can now start to define all of the different functions that we need for actually creating a pipeline that's going to do all the processing of the markdown files。

 doing the chunking up and then extracting the entities。 Now。

 the new4j graphraphra library has a convenient， simple Kg pipeline。

 which you can use to do all the processing of the chunks and entity extraction。

 So for all the markdown files you'll be processing。

 you'll createe some helper functions to actually get that set up correctly。 But first。

 let's take a look at the interface for the simple Kg pipeline。



![](img/7479beb84ff34a83faf6d4c678d9097c_17.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_18.png)

Now， this is just a little sample code that， of course。

 won't run because it doesn't have valid values here。

 but just to show the shape of actually what it means to actually create an instance of the simple Kg pipeline。

 it needs to have an Lm， of course， we're actually doing some of the entity extraction。

 It needs a driver from your4j to actually write the graph out to You're going to need a better interface that could be the same LM or a different one if you want to。

 and because we're processing markdown files instead of Pdfs。 This is only say from Pdf is false。

 but it's actually kind of true because we're going to use a custom Pf loader instead of loading Pdfs。

 we're gonna to load markdown files。 So this is just a little quirk about the way the interface works。

 but we're going to end up being saying true here。 We will define a custom loader that we're going to add into this part here for the Pdf loader。

 we're gonna have a custom splitter as well， because we have some notion of what the markdown looks like。

 And if you've done any kind of chunking before， you know that just doing text splitting itself as an art。

 There's probably multiple courses on deep learning here that you can take a look at。



![](img/7479beb84ff34a83faf6d4c678d9097c_20.png)

To actually really dig into that topic， we're going to do a simplified version making some assumptions about the data that we have。

 You can also pass in a schema， and the schema is， of course。

 going to be based on what the previous lesson had done for setting up a proposed schema for what kinds of facts and kinds of entities can be pulled out of the text。

 And then， of course， to put all that stuff together。

 We're going to have a custom prompt that we pass in that's going to let the LM know exactly what we're looking for and how to think about doing the extraction。



![](img/7479beb84ff34a83faf6d4c678d9097c_22.png)

Let's walk through the end to end workflow of the Ne4j K G builder to help you understand what these components do。

 First， each document is loaded。 there's built in support for Pfs。

 but you'll use a custom markdown loader。 Next， a text splittter component will perform chunking。

 This is the common chunking that happens in many different frameworks for each chunk。

 the chunk and better will calculate a vector bedding。 The chunk is then analyzed using an L L M。

 as instructed by the entity and relationship extractor。 Now。

 this component will be configured to align with our knowledge extraction plan。

 Once the graph has been constructed， an optional graph pruner can be used to clean up the graph。

 This all happens in memory。 A K G writer is the component responsible for saving the in memoryory graph into Ne4j itself。

 Finally， an entity resolver component will merge nodes that are likely the same entity。



![](img/7479beb84ff34a83faf6d4c678d9097c_24.png)

Okay， so now you can start to define some of these custom functions we're going to need to pass into the pipeline。

 And the first thing we'll do is set up a custom text splitter。

 And if you remember the markdown files that we had。



![](img/7479beb84ff34a83faf6d4c678d9097c_26.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_27.png)

The Mar of P had an H1 kind of header at the beginning。

 and then they have these page breaks basically for splitting up the reviews。

 And so we're going to use a simple regular expression text splitter。

 So for near for J There's this base class called text splitter。

 you can extend that with custom functionality。 And so that's what we're going to do here。

 we're going to extend text splitter。 and then in the run function for text splitter because it's part of the pipeline。

 Here's where a custom functionality is going to be put in place we're just going to use a regular expression that's going to split the text。



![](img/7479beb84ff34a83faf6d4c678d9097c_29.png)

Based on this regular expression， it's been defined。

 that's going to be passed into the function itself。

 So for any kind of regular expression that's passed in， you can use that as the。

 the split points within the text。

![](img/7479beb84ff34a83faf6d4c678d9097c_31.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_32.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_33.png)

The final part that it does here is go ahead and just use a list comprehension for taking each of those plain text splits and putting them into an object that the Ne4j graphraag library expects called text chunk。

 Tex chunk will just have the text or the string itself in index for that particular chunk of text。

 and that's just going to turn into a single list with these text chunk objects that the list is going to be called text chunks。



![](img/7479beb84ff34a83faf6d4c678d9097c_35.png)

You'll also be loading the markdown files with a special data loader and similar to the text splitter。

 this is going to extend a base class from the Nevaj Graphag library。



![](img/7479beb84ff34a83faf6d4c678d9097c_37.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_38.png)

And there's a couple of these that are available， but we're going to find a special one here ourselves。

 So we're going to import the data loader base class and also these kind of types that actually need to be used for the output。

 we're going to make it look as if we have in parsing a PDFf documents or we're going to load up a Pf document type in this markdown data loader。

 the key thing that it's really going to be doing here。



![](img/7479beb84ff34a83faf6d4c678d9097c_40.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_41.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_42.png)

Is that we know that there's some metadata within the markdown that we actually want to be able to extract and add to the context of the data loading when the chunking is happening。

 So we've got an extra utility function inside of the class called the extract title。

 It's going to use a very basic regular expression to just kind of assume that the first time it finds a single H1 headline。

 It's going to use that as the title for the document。



![](img/7479beb84ff34a83faf6d4c678d9097c_44.png)

And so when the run function is called here and the run is really the thing it's going to load the data from some data source。

 So it's going to load from the file system， it's going to take the markdown text and just read the entire file。

 extract the title and then turn all that into this document info here。

 and it's the document info that really the interesting part。

 This is the kind of the metadata for the document that gets combined with the text of the document which we've loaded here into markdown text and put into this Pf document class。



![](img/7479beb84ff34a83faf6d4c678d9097c_46.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_47.png)

So the other things that you need to set up the knowledge graph construction pipeline is of course need an LLM。

 We ready we have that， but we're going to be using openaiI again。

 of course we're going to be using open AI for the embe as well。

 and then we have to grab the Ne4j driver So this is using Ne4j Grara libraries for that。

 So Ne4j has support of course， for Open AI and other bottles as well we're going to use open AI for both the LLM and also for the embeddings So we're just going to create instances of those LLM for Ne4j。

 the embe as well and we're going to grab the Ne4j driver from our Gdb Singleton that we've been using for just sending queries to Ne4j So Sleton lets you grab the internal driver that it uses so that's what we're doing here。



![](img/7479beb84ff34a83faf6d4c678d9097c_49.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_50.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_51.png)

Okay， you've defined some of the utility functions needed for the knowledge graph pipeline and also some of the other components like the LLM and the embeder as well。

 and now we're going to turn to the context required fact doing the knowledge graph entity extraction and we're going to start with the entity schema。

So the entity schema of required by the Neo4j graphra package has a couple different components。

 One is it wants to know the node types that it should look for inside of the text。

 And here we're just gonna to make a copy or just really an alias of the approved entities。

We're also going to get the sche of relationship types。 And for that。

 we're going to go ahead and extract from the approved fact types that we have。

 All those approved fact types actually exist inside of the dictionary or the key in the dictionaries actually the relationship type itself。

 So we're just going to extract all of the keys that should be the schemeche of relationship types。

 and you can see them here。 You're also going to use the approved fact types。

 but as what's called schema patterns by the knowledge graph builder pipeline。

 and it's really just a repackaging of the exact same information。

 So from each of the facts we're going to turn that into a list that has the subject label。

 the predicate label and the object label， and we're going to turn the predicate label。

 we're going to make that uppercase， which is the convention inside of Ne4j。



![](img/7479beb84ff34a83faf6d4c678d9097c_53.png)

The complete schema then required by the Knowledge graph builder is here it's got the node types。

 relationship types， the patterns about how those fit together。

 and we're going to set this flag to fall saying only use these types that we've just defined。

 don't go adding new things。

![](img/7479beb84ff34a83faf6d4c678d9097c_55.png)

The next part that's important for getting the context for the entity extraction or we're going to create a custom prompt that's going to be injected with both the text within each of the chunks。

 but also the schema is going to be added to that and also we're going to be having a special utility function that's going to be adding in the file context the pipeline will be processing an individual chunk and the context from the overall file will be added to the prompt so that the LLM knows when it's looking at this chunk what is the document that it was part of。

So for that file context， we're going to have this little helper function here。

 All this is really doing is going to grab the first couple of lines of the text from the file that's going to include the title of the file and also a little bit of introduction and information that'll give enough context for each of the individual chunks。



![](img/7479beb84ff34a83faf6d4c678d9097c_57.png)

Then you can define the prompt itself。 And here we're going to look at the prompt as kind of one big chunk of text。

 It's going to follow roughly the same format that we've done before。 We have some notion of。

 you know what is the role of the LLM and its current work and what's the goal that's actually after。

 But then a lot of this is setting up both some design hints and also the context and the context includes both the schema definition and also that little bit of the file that we're going to extract。

 So as you look through this prompt。 you'll see that it's got instructions about the role and goal。

 It's got some design instructions here about what it should do。

 It also has some specifications about what the output format should look like。

 And here also and for every chunk， the schema is going to be injected。

 And once all of that's been put in place。 then as part of the output where we're going to ask it to do unique ideas for each of the nodes as it's creating those nodes。



![](img/7479beb84ff34a83faf6d4c678d9097c_59.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_60.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_61.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_62.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_63.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_64.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_65.png)

And also， we're giving you some instructions here about what to do with each of the properties you can see in the output here that we want to know output to have some Is。

 We want to know what the label is that it's picked and also what are the properties that should be assigned to that entity。



![](img/7479beb84ff34a83faf6d4c678d9097c_67.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_68.png)

Also then this is where the context from the file so the document level context is going to be injected and here because this is the helper function that's going to create the overall prompt。

 we're going to just actually inject that here as kind of static text so it's not going to be injected each time the chunk is created it's going to be part of the static text and then finally the chunk data itself will be placed into this template format here。



![](img/7479beb84ff34a83faf6d4c678d9097c_70.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_71.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_72.png)

Okay， with all the context that we've set up with all the different helper functions that the knowledge graph builder needs for doing the pipeline processing。

 we can go ahead and make the knowledge graph builder and then use it。

So because we're going to create a knowledge graph builder for every file so that we have a specialized prompt based on the file content。

 here's how we're going to set that up in a helper function。

 we're going have helper function that is going to make the knowledge graph builder and the app of it will be a simple knowledge graph pipeline that's the Neverta graphraphra class and the first thing we're going to do inside this helper function is get the document level context and that's going to be using this file context utility that we'd created and again that's going to grab just the first couple of lines of the data file and then from that it's going to create the contextualized prompt passing in that context is the only argument that we're going to get the full prompt that we want to use。



![](img/7479beb84ff34a83faf6d4c678d9097c_74.png)

So when we create the simple knowledge graph pipeline， we're going to grab the LM that was defined。

 the driver were using the embedder。 We're going to pretend that we're processing a PDF because we've got a custom PDF loader that's actually going to be loading markdown or a custom splitter that's going to be using a regular expression。

 And here the regular expression is just going be looking for dash dash dash That's the markdown page break that if you look at the markdown files that we saw earlier。

 that's how each of the reviews are split up。 So we're going to use as the text splitting。



![](img/7479beb84ff34a83faf6d4c678d9097c_76.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_77.png)

The schema that resembled as the entity schema， and then finally this contextualized prompt that was constructed just up here。

 putting all that together， we got a complete pipeline that can then do the chunking up and then the entity extraction。



![](img/7479beb84ff34a83faf6d4c678d9097c_79.png)

Now that you have a helper function for generating the knowledge graph pipeline for a particular file。

 now you just need to go ahead and loop through all the files。



![](img/7479beb84ff34a83faf6d4c678d9097c_81.png)

In the import directory。

![](img/7479beb84ff34a83faf6d4c678d9097c_83.png)

And for each of those， we're going to get the full file path。

 have a little output stamp and letting us know what's happening。

Create the knowledge graph builder and then run the knowledge graph builder。



![](img/7479beb84ff34a83faf6d4c678d9097c_85.png)

Now this will take a couple of minutes， we have， I think about 10 files that it's actually going to process。

 each one of those will take， depending on how much responsiveness we get out of open AI。

 it'll take up to maybe a minute to actually do all the natural language processing of the document doing the extraction and along the way well be also doing the chunking。

Okay， once this loop is finished， you will end up with a complete lexical graph that's the parts of the graph that's going to contain the chunks connected to each other and connected to a document node as well。

 and then also the subject graph that's going to have all the extracted entities and also how they're related to each other。



![](img/7479beb84ff34a83faf6d4c678d9097c_87.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_88.png)

Now that we have all files processed， this has been completed， you now have a lexical graph。

 a subject graph and a domain graph， however， the null graph isn't complete because the subject graph and the domain graph are not connected。

 and if you recall the domain graph was created from the CSV files and we just created the subject graph as extracting data from markdown files。

The next step is to connect the entities that we extracted from the markdown files into the subject graph。

 We want to be able to connect those with the domain graph。

 So if there are products in the domain graph that refer to the same product as the extracted entities in the subject graph。

 we want to connect those。 So we're going to define a couple of tools in order to do that。 Now。

 for each type of entity in the subject graph， you're going to devise a strategy for correlating with the right node in the domain graph。

 for example， you should expect that the products with the product names exist in the subject graph。

 and that these should correlate with the products in the domain graph。So in order to do this。

 you will do a couple of things。 First， you're going to find all the unique entities。

 labels in the subject graph。Similarly， you'll find all the unique node labels in the domain graph。

And then you'll attempt to correlate the property keys between those two different sets of labels。

 so you can figure out if there is a product with a couple of different properties in the subject graph。

 How does that correlate with a product with a couple of different properties in the domain graph。

 So that's the very final step is performing entity resolution by analyzing the similarity of property values。

Okay， the first step is to find unique entity labels in the subject graph。Now。

 let's take a look at the subject graph to see what the nodes look like After the Neuvaj Graphraag library has done its work。

 the resulting nodes that are part of the subject graph will have an extra label identifying them。

 They're going be labeled with this underscore underscore entity underscored label。

 So you'll see that plus additional labels to identifying what type of entity it is。

 So if we run this query matching any nodes。 And we have a predicate looking for where that node has this label。

 We can then return the distinct sets of labels and call that the entity labels。

 So let's take a look at that result。And you can see there's a couple of special labels that have been added here。

 there's the underscore entity one， there's also the underscore KG builder indicating that KG builder is the one responsible for creating those nodes。

 but what we really care about is that we see the product， location， issue and feature。Now。

 we do know this because that's what you're expecting from the previous steps。

But what's important is some of those steps might have intended to try to find things like location。

 but those might have failed to actually occur inside of the graph because the L M fail to actually find them。

 So what we'll do instead is we're going to query the graph for what actually happened。

 Then based on the labels that we find inside of the graph。

 We'll call those the unique entity labels that are part of the subject graph。

So let's walk through a couple elaborations of this query。



![](img/7479beb84ff34a83faf6d4c678d9097c_90.png)

The first thing is， if you take that what you realize each of these rows。

 it's really a list of labels。 So for each row， if we go ahead and just use that unwind clause。

 So for you say you here， unwind the entity labels， which are going to be the labels for every node。

 And we're going to call that individual rows as entity label。

 we can then return the distinct entity labels。 We should see all the same values。 But now。

 rather than as a bunch of lists， we'll see a single list with all the values。



![](img/7479beb84ff34a83faf6d4c678d9097c_92.png)

Okay， so now the list is really just a couple of rows where each row has a single label。

 the K G builder， the product entity。 you can see it right there。



![](img/7479beb84ff34a83faf6d4c678d9097c_94.png)

So let's elaborate a little bit further on this query。We want to filter out these underscore labels。

 So we're simply going to do that by having exactly the same query。

 We're going to start with the match， have a predicate for just the ones that actually are entities。

 Unwind all of those。 So they're just entity labels individually。

 And then with those who are going to have another predicate says， okay。

 now get rid of end of the entities that start with underscore。

 That should get rid of K G builder and underscore entity。



![](img/7479beb84ff34a83faf6d4c678d9097c_96.png)

So that's the list that we're looking for， just product location， issue and feature。



![](img/7479beb84ff34a83faf6d4c678d9097c_98.png)

You can then define a utility function that just wraps that call to Ne for day。



![](img/7479beb84ff34a83faf6d4c678d9097c_100.png)

If you try out the utility function。

![](img/7479beb84ff34a83faf6d4c678d9097c_102.png)

You should see， of course， just that list， it's exactly what you want。Now。

 for each of those unique entity labels， we also want to find the unique keys that each of those labels have。

 So for every one of those， we're going to do a similar thing。

 We're going to define a utility function that's going to look for all nodes that have that particular label。

 But instead， once we found some sample set of those。

 we're going to find just a unique keys that occur on those。

 Let's take a look at what that utility function looks like。



![](img/7479beb84ff34a83faf6d4c678d9097c_104.png)

Here it's going to get an argument， which is what's the entity label that we're looking for。

And now the match， rather than finding all nodes， we're only going to find nodes that have that particular entity label。

 And here we're going to kind of turn things around a little bit。 We actually want to look。

 of course， only where that label co occurs with the underscore entity label。

And then rather than finding the distinct set of labels。

 we're going to find the distinct set of keys on those nodes and return those。

 And similar to what we did before， we're going to unwind those lists of keys into just a couple of rows of keys。

 So that's what the unwind is doing here。 And then we're going to collect those all back into a list。

 and then return that as the single result。 So let's define that function and then give it a run。

 looking just for the unique keys related to product within the subject graph。



![](img/7479beb84ff34a83faf6d4c678d9097c_106.png)

Okay， and it looks like we didn't really constrain that too much when we were doing the entity extraction。

 So this time around the LM， it actually found lots of different keys when it created those entities。

 So across the different products。 Here's all the different kinds of properties that it actually derived from the reviews。

 It figured out things like the material， different features about， I don't know。

 the shelf depth apparently appears somewhere。 you'd have to look at the text of the markdown to actually see why the LM discovered these different properties。

 Depending on the particular review that was being used for doing the extraction。

 Some of the reviews probably have some of these properties being mentioned， others will not。

 And so this is not going to be consistent across all properties。

 But some of these things probably are， particularly Im thinking the name was going to cooccur。

 And you'll see later how we actually try to take this list of keys and correlate them with keys that are available on the domain graph。

 and that's how we're actually going to sync everything up。



![](img/7479beb84ff34a83faf6d4c678d9097c_108.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_109.png)

The next utility function that you will define is very similar。

 but now we're going to turn attention to the domain graph。 and on the domain graph。

 we already know how to find the labels that are part of the domain graph。

 we know that their labels where there is not an entity extra label on it。

 So if we match for a particular label， let's say for product。

 if we're going to find the unique domain keys for product。

 we're going to ahead match for that and then filter out any of the ones that have entity because those are part of the subject graph。

 And then same as we did for the previous function that were then going to go ahead and get the unique keys on those domain nodes and then collect those up into a list。

 And so if we look for the unique property keys on the domain labels。

 this should be consistent because these were， of course， imported from a single Cv file。

 It's a much smaller list， it probably correlates exactly with what the Cv file had the product name。

 the price or description product I D。

![](img/7479beb84ff34a83faf6d4c678d9097c_111.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_112.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_113.png)

To help that process along， we're going to define a helper function called normalizedize key。

 You can just pass in for a particular label what is the key that you want to normalize here。

 And what this function is going to do， it's going to go ahead and lowercase the key。

 It's going to remove extra whitespace that's not very helpful。

 And if the prefix is actually present there where the prefix is the label itself。

 go ahead and remove that。 that would do things like this product name would end up being just name。

 Then you could obviously make it very easy to correlate with the name key from the subject graph。



![](img/7479beb84ff34a83faf6d4c678d9097c_115.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_116.png)

So product renders score name would end up to being just name， product space name would be just name。

 and of course， a property key like price would still just be price。 I wouldn't get changed at all。



![](img/7479beb84ff34a83faf6d4c678d9097c_118.png)

So again， the implementation is pretty straightforward。

 but the purpose of this is actually just to kind of make the property keys themselves easy to compare。

And then you can look at some of the examples just for a sanity checking， that looks good。



![](img/7479beb84ff34a83faf6d4c678d9097c_120.png)

The next utility function that you'll put together is for correlating keys for a given label。 Now。

 this is going to take advantage of some of the utility functions we already had and let's take a look at the implementation。



![](img/7479beb84ff34a83faf6d4c678d9097c_122.png)

We're going to import a new library here in Python called rapidpiid fuzz。

 It's really just used for doing text similarity scoring。 And this is a simple edit based scoring。

 There's a couple different ways for actually trying to figure out whether text strings are very similar to each other。

 Rapi fuzz is a pretty good library for that inside of the function itself， given a particular label。

 some keys from the entity node and some keys from the domain node。

 We're then going to look at a similarity score that is a threshold We like how do these keys correlate with each other according to the scoring from rapid fuzzes fuzz function。

 And then for the keys that correlate very highly， we're going to pair those up as saying these keys are probably worth comparing the values of。



![](img/7479beb84ff34a83faf6d4c678d9097c_124.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_125.png)

Okay， let's look at this in detail。The correlated keys so the keys that we want to pair up start off as being empty。

 and we're going to iterate through all of the keys in the entity keys collection in kind of classic style。

 we're going to have a for loop inside of a for loop。

 we'll loop through all the entity keys and then inside of that we'll loop through all the domain keys and for each pairing there we're going to consider how closely they correlate。



![](img/7479beb84ff34a83faf6d4c678d9097c_127.png)

We're going to go ahead and just normalize each of those keys。

 And because the rapid f similarity score goes from 0 up to 100。

 we're going actually going to flip that around so that it looks more like a similarity score。



![](img/7479beb84ff34a83faf6d4c678d9097c_129.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_130.png)

And we're going to go ahead and calculate the ratio of this normalized domain key and the entity key。



![](img/7479beb84ff34a83faf6d4c678d9097c_132.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_133.png)

And that should be the fuzzy similarity。Now， we want that fuzzy similarity to be greater than the similarity threshold that was passed into the function up here。



![](img/7479beb84ff34a83faf6d4c678d9097c_135.png)

Which is currently set at 0。9 as a default。 And so if it surpasses that threshold。

 we're going to go ahead and add that to the correlated keys as a pair that we think is valid。



![](img/7479beb84ff34a83faf6d4c678d9097c_137.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_138.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_139.png)

We'll go ahead and just sort those keys， then。Just so it's easier to take a look at the ones that are the most highly correlated verse less correlated。

 And we're going to take the top correlated one later on to actually use。

 So after defining that function， we're going to go ahead and this part here is just to be trying it out。



![](img/7479beb84ff34a83faf6d4c678d9097c_141.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_142.png)

So as's to find the function for a product， it's going to go ahead and find all the unique entity keys。

 find the domain keys， pass it into this function， and see the results。



![](img/7479beb84ff34a83faf6d4c678d9097c_144.png)

So for product， we can see that name and product name correlate perfectly。

 price and price correlate perfectly。 De description correlate perfectly。But design a description。

 that's pre low correlation， dimensions and description， low correlation。 Those aren't super great。

What was the threshold that we passed in。 Yeah， we asked for a similarity of 0。5。

 You can try different values here to see what kind of different results you get。

 The default value of 0。9 is one of those classic kind of high thresholds you want to set。 Okay。

 one more bit of background here。 And then we're going to actually put all this stuff together。

 We've now been able to correlate for a given label in the subject graph and in the domain graph and the keys on those labels。

 What the good pairings are for actually trying to decide whether two nodes happen to be the same node。

 Now， this is all by way of having what's called entity resolution。

 This is a technique for achieving that。 There's many different techniques。

 This is a pretty good baseline and it works perfectly for this current data set that we have probably for different data sets you're going to want to have multiple techniques。

 And， of course， you could imagine an entire agent built around just trying to figure out for the data that you have。

 What's the right technique for actually doing the resolution。



![](img/7479beb84ff34a83faf6d4c678d9097c_146.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_147.png)

But for what we're doing today， we're going to make some assumptions。

The next function that we actually want to use is actually when we're going through processing all the data inside of Ne4j with some cpher calls。

 Cypher has some support for doing string comparison methods as well。

 One of the value similarity functions that's available It's called Gerro Winkler distance。

 and that is really just a string comparison method similar to you might use vector similarity where you actually have to calculate the vector beddings。

 Instead you can figure out text distance in lots of different ways。

 Jro Winkler does that by calculating what's called the edit distance between two strings。

 And it really looks at how many small edits have to be made to take some string A and some string B。

 How many edits you have to make to actually make them be the same string。

So the values end up being between0 and 1， where kind of in inverse way。

0 ends up meaning that it's an exact match and one means that there's no match whatsoever between these two strings。

Now， near for J's library of tech similarity scores include this Jro Winkler calculation。

 you can also use hamming distance， the Leevenstein distance， there Sorenen diceimity。

 and also fuzzy matching。 And of course， if you want to。

 you can also do a cosine similarity using vector beddings All those have different features and like everything else we've been doing so far with this part of the logra construction you could probably pick and choose which one is better given a particular data set for the data set that we have this Jaro Winkler distance is going to be just fine So you can take a look at what Jaro Winkler would look like in action using just pure cipher If you look at the cipher query that's happening here in the match clause。

 we're actually going be matching a pair of both entities and domains for a particular label here we're going to be looking for the entity label that is the same on both and of course。

 the entity node also has the extra label of underscoreco entity and then with the entity and the domain and then calculating this Jaro Winkler distance score We're going to pass that on with a filter where the score has to be less than0 point。



![](img/7479beb84ff34a83faf6d4c678d9097c_149.png)

if you remember the score of0 means it's the perfect match。

 And so we're going to have kind of the opposite way of scoring here。 we're looking for low values。

 So filter on that and then return those values to take a look。 So in this example。

 we're going to be passing some query parameters， we're going to be looking for the entity label of product。

 both on the subject graph notes on the domain graph on the subject graph。

 we're going to look for the entity key name and the domain key is going to be product underscoreco name。



![](img/7479beb84ff34a83faf6d4c678d9097c_151.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_152.png)

Okay， you can see that these are perfect scores。 Gothenburg table and Gothenburg table。

 These all look exactly the same， of course。 So you would expect them to have a very low score。

 You can try this with different values to try to see what it would be like if you maybe had a little bit less strict threshold at0。

5。 You can see that the Gothenburg cable and Vaster's bookshelf， apparently。



![](img/7479beb84ff34a83faf6d4c678d9097c_154.png)

Are not terrible。 Gothenburg table and Stockholm chair。

 I don't know how those are actually very similar。 T wise， but I guess the distance gives you that。

 This is why usually one end up with in practice having a very low threshold like 0。

1 so that there is closest as possible to being the actual same thing。



![](img/7479beb84ff34a83faf6d4c678d9097c_156.png)

So let's elaborate on that query a little bit。 This is exactly the same query。

 but we've added one extra part。 whenever we find two entities that have a very low threshold。

 So here we repackaged things a little bit。 now in the where clause in this pairing of entities and domain nodes。

 we're going to have the where clause actually just having a predicate on the Jwinkler distance。

 We're setting the threshold to be 0。1。 And for any pairs that pass that correspondence。

 we're actually going to go ahead and create a relationship from the entity to the domain node。

 And so we're going to use the fixed type here， it's not going to be parameterized of corresponds to。

 So the relationship will be this entity node corresponds with this domain node。

 Now there's two sub clauses that we're going to use here in case you decide to run this multiple times。

 This can be very useful when you do a merge。 merge side of Ne forj is kind of like an up。

 and it actually has two sub clauseuses based on the behavior of the uper。

 So if the merge ends up finding a match for actually what you've described。

 Then there's the sub clauseuse。

![](img/7479beb84ff34a83faf6d4c678d9097c_158.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_159.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_160.png)

For on match and then whatever follows that will be executed。

 or if you're doing the first time and it's being created， the clause on create is being called。

 So after you do the merge， if the very first time you run it on create will be called and we're going to set this value。

 create a time with a timestamp， the other one， if you already have created it and you're just matching again。

 we're going to say that updated it ad also gets a timestamp and that'll be updated every time you run this again。



![](img/7479beb84ff34a83faf6d4c678d9097c_162.png)

Okay， and that runs across all of the corresponding products。That looks pretty good。



![](img/7479beb84ff34a83faf6d4c678d9097c_164.png)

That Cypher query is doing exactly what you want。 So go ahead and wrap that inside of a function call。

 passing in the label entity key and the domain key。

 and also the similarimary score that you want to have as a threshold。

 The query is pretty much the same here。 And you can see that the parameters are being passed in as query parameters from the arguments to a function。



![](img/7479beb84ff34a83faf6d4c678d9097c_166.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_167.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_168.png)

And again， we can just go ahead and run that。 We're trying that out on product name and product name。

 These are the two different keys from the entity and also from the domain graph。



![](img/7479beb84ff34a83faf6d4c678d9097c_170.png)

Great， so that found 10 relationships that made sense between the subject graph and the domain graph。



![](img/7479beb84ff34a83faf6d4c678d9097c_172.png)

So for completeness。While we know that we can connect to products。

 we want to do this for all of the entities that are available。

 so to correlate and connect all of the subject nodes to the corresponding domain nodes。

 we'll just put in a forward loop that's going to go through all of the unique entity labels and then try to correlate them from the entity side over to the domain side。

 so the subject nodes and the domain nodes will be connected。



![](img/7479beb84ff34a83faf6d4c678d9097c_174.png)

![](img/7479beb84ff34a83faf6d4c678d9097c_175.png)

So you can see that product was connected， of course， location actually doesn't have any correlation。

 neither does issue or neither does feature， but that's what we expected。What has happened now。

 as a result of doing all this work， you finally have a complete domain graph that was constructed out of C as V files。

 You also have a lexical graph and a subject graph that was created from markdown files。

 And with this final step， you've connected the entities in the subject graph with the entities in the domain node。

 Now， you have a completely connected knowledge graph。 Well done。



![](img/7479beb84ff34a83faf6d4c678d9097c_177.png)