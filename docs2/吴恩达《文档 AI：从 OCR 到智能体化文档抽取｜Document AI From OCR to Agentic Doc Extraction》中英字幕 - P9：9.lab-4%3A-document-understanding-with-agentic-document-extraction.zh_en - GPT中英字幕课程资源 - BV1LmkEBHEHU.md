# 吴恩达《文档 AI：从 OCR 到智能体化文档抽取｜Document AI From OCR to Agentic Doc Extraction》中英字幕 - P9：9.lab-4%3A-document-understanding-with-agentic-document-extraction.zh_en - GPT中英字幕课程资源 - BV1LmkEBHEHU

Welcome to Lab4 document understandinging with Age Gentic document extraction in this lab you're going to be using the API based version of Age Gentic document extraction from landing AI so let's get started。

Al right， at the top of our notebook， a couple cells to do setup。

 Most of these should be familiar data science libraries or things that we used in previous lessons。

 New in this lesson are the imports here from landing AI。

 So we're gonna to be importing landing AI underscore AdeE and then importing specific types that we'll use for parsing and extractioning。

 Next， you'll load the API key from the environment。

 Note that if you'd like to create your own API key to work with agent document extraction outside of this lesson。

 there will be instructions provided in the notebook。

 Let's initialize the client and now our setup is ready。

So in a continuation of the setup we're going to import a variety of helper functions。

 you have the ability to inspect the contents of all of these。

 it's going to keep the notebook a bit cleaner， most of these are really for the purposes of drawing and displaying things on screen。

In this lesson， there are three exercises， and each of them are broken into component parts。

 So the first exercise will be extracting verifiable key value pairs from a utility bill。 and。

 of course， the first step is to just preview the document。 Here。

 we use one of the helper functions to view the document。

 This is a combined gas and electric bill from a utility in San Diego。

 few things to notice its for a particular monthly period。

 It does have both the gas and the electric charges separate。

 and it also has a usage history for both of those services。 All right。

 in this section we'll be parsing the document。 We'll be using the document pretrain transformer that we introduced in the slide section。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_1.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_2.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_3.png)

Since we've already imported parse response， actually calling the API is just a matter of saying parse。

 specifying the document path and the model type we'll be using DPT2 latest。

 We release updates to DP T2 roughly once per month， so your results may vary from mine。

After we send the utility bill to the parse API， we'll print a few details from the response。

 All right， our parsing is complete。 We have a job I D we can refer back to。

 It was indeed just one page resulted in about 6000 characters and 24 chunks。

 So now we can continue to work with that parse result and inspect it。

 As you explore the output from parse。 You'll see that it's very easy to overlay the results on the original。

 print some of the chunks and chunk summaries and also print some of the markdown。

 Let's go ahead and do that now。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_5.png)

Alright， here is the annotated version of the document。

 And you'll notice bounding boxes of different colors for the different chunk types。

 So logo here in light green， text in the medium green。

 And notice also that each chunk has a unique identifier。 In addition to the type。

 Here we see a table chunk。 And notably inside the table chunk。

 there are individual table cells that have their own unique identifiers in purple。

 a margin chunk and， of course， two figure chunks in the Json response chunks is one of the top level elements。

 And here we're printing the first five so you can see the structure。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_7.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_8.png)

Recall from the original that in the top left corner， there is a logo。

 and that happens to be chunk 0。 So here we're looking at the identifier， the type。

 the page and the coordinates corresponding all to chunk0。 The JO output is well structured。

 allowing you to do simple aggregations such as this one where you may count the chunks of each type。

 Another top level element is the markdown。 And here we're displaying the first 500 characters of the markdown。

 conveniently， the identifier is included along with the markdown content for each one of these chunks。

 In this cell， we're not looking at the top level markdown element。

 We're actually looking at chunks again and chunk number 9。

 So what's important to learn here is that within the chunks element。

 Each of the individual markdowns are available separately。 This one happens to be a table。

 which renders nicely as HTML。Recall when we looked at the overlays that I drew your attention to the fact that each table cell has its own identifier。

 Here's the raw mark down for that same chunk。 And here you can really see each of those table identifiers。

 This is going to be helpful later for visual grounding because we can refer back to a specific table cell by its identifier once we extract a value。

 Having completed parsing， It's time to extract those key value pairs。

 If you remember from the slides， the extraction step combines the mark down from the parse step together with a schema。

 So we'll need to define a schema that corresponds to the utility bill。

 This schema has 10 properties。 and is defined using Json。

 The important things to note are that you can have nested schemas here under account summary。

 we have nested underneath the current charges and the total amount due under gas summary。

 notice that we can also have。Boleions and strings and numerous other types。

 and notice that each field has a fairly robust description。 the more descriptive you are。

 the more likely you are to get what you want when you go to extract these fields。

 The last line here convert the dictionary into a formatted string to use with the API Now you're ready to call the extract API using extract response。

The Json schema has been defined， and the parse result is still available in memory。 Again。

 we'll be using the latest version of the extraction model。

 So your results might differ slightly with the extraction complete。

 It's time to explore the result and expecting 10 total values with a mixture of numerics。

 Booleions and strings。And this appears to be exactly what I wanted at the top level account summary。

 current charges are $155。15， which also equals the amount due。

 The Booles are telling us that a usage chart is available。

 and the max month is actually interpreting a value from the usage chart。

 saying that in the last 12 months。 January was the highest gas consumption。

 and August was the highest electric consumption。You can go back to the original and verify that based on the peaks in the bar chart。

Then in the extraction metadata， we see the references for where that information was obtained。

 This 0 dash A is one of the table cells from chunk 9， and as is 0 dash D。

 So these values are coming from a table。Typically， when you see a longer chunk reference like this。

 it's coming from a figure， a text block or something that's not a table。These two responses。

 combined with the parse result， give me all the information I would need to actually build a user interface to display back to the user the fields that they wanted and exactly the portion of the document that that came from。

So to wrap up exercise one， you've used two APIs， parse and extract。

It's really parse that is analogous to what we did in lessons 1，2 and3。

 but here the agenttic Do extraction API has abstracted away all of the model training。

 configuration and custom coding that was previously required and a single API call is all that's required to understand the entire document。

And the output is better， that quality difference will become more apparent as you test more difficult documents in exercise2。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_10.png)

We're in Section 4， Ex 2， and we'll look at the agentic document extraction performance on some more difficult documents。

 We've selected6 for you that are difficult in various ways。

 But the same API using the same underlying document pretrain transformer can understand all of them。

 I'll be moving through this section fairly quickly。

 But feel free to take your time and explore these examples。 There's one long function here。

 which is going to call the parse API for each document and print a variety of outputs。

 That's going allow us to quickly run all six of them using this function repeatedly。

 This section is really about looking at a wide variety of examples。

 feel free to substitute some of your own。 for each one。 after I execute the cell。

 I'll just draw your attention to one or two key differentiators。

 Let's start with some charts and flow charts。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_12.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_13.png)

This is what the original looks like， it's an interior page of an investor presentation。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_15.png)

And A D E has found 9 total chunks and has correctly detected all of the figures。

 Let's select this figure down in the lower right and see if it's understanding this horizontal line as the average at 4。

3 x。 And indeed， there it is within the bar chart type average revenue multiple of 4。3 x。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_17.png)

Let's take a look at this flow chart original。Here's an example of a document that a human understands intuitively。

 but has a lot of spatial and relationship based information with the arrows and pointing in all sorts of different directions。

 A D E detects all of this as one large figure， which is correct。 It is one large visual unit。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_19.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_20.png)

And let's see if we can find where good reference follows the yes to select candidate。

 This would be very difficult in traditional O C R。

 because select candidate is actually higher on the page than good reference。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_22.png)

And here it is。 Good reference。 If yes， it proceeds to select candidates。 Well done。

 Let's look at some tables。 The world is full of tables， but in many cases。

 some of the lines are missing。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_24.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_25.png)

This table has no column dividers and no row dividers。

 And because of the large amount of blank space， it's very difficult as an OcrR problem。

 In the response， you can see that the entire section was detected as a table。

 And you can see that all of the blank cells have been understood because of the regular array of cells that we see here。

 Priing the markdown as HTML to the note shows all of those blanks。 What about something like this。

 You could even call this a mega table。 There are over 1000 individual cells here。

 In addition to the total quantity of cells， Notice also that the rows have merged cells and the columns have merged cells。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_27.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_28.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_29.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_30.png)

All right， We're certainly not going to go through and verify every cell here。

 But if you've ever tried to extract a mega table like this with an LL M。

 you'll know that it's very susceptible to hallucinations。

 The L L M simply cannot hold this many numbers in its context window。

 and this is really where the agentic approach becomes crucially important。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_32.png)

And of course， if you needed your mega table actually rendered in Excel or HTML。

 we could now quickly save this as CSV。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_34.png)

Continuing with the theme of handwriting， but taking it to another level。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_36.png)

Here's a document with handwriting， it also has a checkbox。

 it also has six or seven instances of the word no being circled。

 and it has four preexisting conditions， asthma， circulation。

 eye infection and urinary tract infection。 Let's take a look at how this gets parsed。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_38.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_39.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_40.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_41.png)

For this example， it's not the chunk identification。 that is the impressive part。

 It's the markdown itself and how it detects the check boxes and the circles。

 So let's scroll down to that area。 Here's the one。 Yes， no checkbox。 Do you have a pacemaker。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_43.png)

Here we see the seven instances of no having been circled。

And here we see the section where the patient is instructed to circle the preexisting conditions。

 and we do see asthma， circulation， eye infection， and urinary infection as marked。

This is the type of output that combined with an L L M can now accurately extract medical information in a very reliable way。

 Let's push the boundaries on handwriting with some integral calculus。

 Let me draw your attention to this portion of the handwritten response。

 This is the square root of root 2 over2。 has a lot of visual information encoded here。

 So let's look for this in the response。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_45.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_46.png)

All right。 The bounding boxes look good。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_48.png)

Each of the individual questions has its own box。 You can already see in the markdown that we're able to display functions and square root symbols and skipping down to the very end。

 Indeed， we have the square root of route 2 over to。 Well done。

 This next example has no writing whatsoever。 It's the classic second page inside most Ikea instruction manuals。

 So far， we've been sending all of our documents to DP T 2 latest。

 I'm going to send this one to DP T 1 latest。 This document is exclusively illustrations and figures。

 So indeed， we have three chunks that are all figures。

 Let's focus on this middle figure and take a look at the markdown。😊。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_50.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_51.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_52.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_53.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_54.png)

Allright。 The final analysis here is that the figure instructs users to avoid assembling or placing the object directly on hard surfaces to prevent damage。

 recommends using a protective mat or rug underneath during assembly。

 That is basically a picture perfect description of that picture。

 You can also see that the response for each figure is quite a bit longer than from DP2。

 For those of you analyzing things like marketing materials or magazines。

 You're going to encounter documents such as this， which are fundamentally infographics。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_56.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_57.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_58.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_59.png)

This is really putting the layout detection through its paces。

 but the figure and text and logo and table chunks here actually look pretty solid。

 The only chunk type that we haven't seen so far is the attestation type。

 which is used for stamps and signatures。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_61.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_62.png)

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_63.png)

This document which is a certificate of origin， actually has stamps and signatures。

 so let's take a look at how it's parsed。

![](img/a9e1707fd9a9854f8195cb7dd87a39b8_65.png)

So here， the turquoise is an attestation chunk type， and these are really difficult examples。

 Here we have curved text inside of the stamp with other text in the background and a separate signature off to the side。

 Let's take a look at the parse result for this chunk。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_67.png)

So the content begins here with this attestation。 So we're told that it's an official company stamp and signature。

 The signature itself is legible and is provided back to us in the markdown。

As is the text from the stamp itself。There were two of these。

 and you can see that the counterparty signature is also legible， as is the second stamp。

That wraps up exercise2。In this section， you saw how the agent Genic approach to document extraction is able to handle complexity within a document and across documents without any additional actions or inputs from the users。

 this means that agenttic document extraction can be used reliably in document processing pipelines that encounter such real world complexity and variability。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_69.png)

We'll be back in a separate video to tackle exercisese 3。



![](img/a9e1707fd9a9854f8195cb7dd87a39b8_71.png)