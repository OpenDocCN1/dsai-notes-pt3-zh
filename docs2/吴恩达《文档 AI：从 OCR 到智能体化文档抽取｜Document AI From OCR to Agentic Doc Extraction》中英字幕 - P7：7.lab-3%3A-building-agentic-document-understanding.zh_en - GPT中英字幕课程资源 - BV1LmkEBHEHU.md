# 吴恩达《文档 AI：从 OCR 到智能体化文档抽取｜Document AI From OCR to Agentic Doc Extraction》中英字幕 - P7：7.lab-3%3A-building-agentic-document-understanding.zh_en - GPT中英字幕课程资源 - BV1LmkEBHEHU

![](img/5f85a464d3154908d335dc92bcdd3f82_0.png)

Welcome to La 3。 We're now ready to build an intelligent document analysis agent that combines OCR layout detection and VLM tools。

 You'll follow an agentic approach， which allows you to recognize different content types automatically apply the right tools for each content type and combine insights into coherent answers。

 This is similar to how a human analysis will approach a complex report。

 scanning the structure first， then diving deep into specific sections as needed。

 The overall pipeline will have three components。 First text extraction will use Pa OcrR for text extraction and lay a Le for reading order。

 Second layout detection。 Pa OcrR layout detection to detect tables， charts and regions。

 Third agentic processing will use a la chain agent with two specialized tools。 analyze chart。

 a VLM based chart figure analysis analyze table， a VLM table extraction。 Let's begin by。

Loading the environment variables from a dot environment file。

 this file contains the API key for Open AI， which we will need later when we define the agent。Next。

 we import the essential libraries for our pipeline。Pillow for loading and manipulating images。

 C2 from Open CV for image processing and drawing bonding boxes。

 mapplotlib for visualizing the result。 Numpy for numerical operations on image arrays。

 data class Pythons built in decorator for creating clean data structures。

Typing for type hints that make our code more readable with our environment setup up。

 let's dive into the first stage of our pipeline， extracting text from the document and determining the correct reading order using layouty LM。

First， we create a PaOCR instance configured for English text。Then we load our sample document。

 which is the same economics report you've seen in the previous lab。 Now。

 let's run the OCR engine on our document。

![](img/5f85a464d3154908d335dc92bcdd3f82_2.png)

As you've already seen in the previous lab， the OCR engine returns three key pieces of information for each detected region。

 the recognized text strings， the confidence score， and bounding box coordinates。



![](img/5f85a464d3154908d335dc92bcdd3f82_4.png)

Visual verification is important。Here we draw green bounding boxes around each detected text region。

 This helps us confirm that OCR is correctly identifying all text areas in the document。

 notice how each line of text， table cell and label gets its own bonding box。



![](img/5f85a464d3154908d335dc92bcdd3f82_6.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_7.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_8.png)

Ral OCR output is just list of values to make our code cleaner and more maintainable。

 we create an OCR region data class。 This gives us a clean type structure for each text region and a convenient bouning box X Y XY property that converts the4 corner polygon to a simple X1。

 Y1， X2， Y2 format。The structure format will be used throughout the rest of our pipeline。

Now that we have the raw OCR output， we need to determine the correct reading order。

Let's use layouty readerer based on layouty LMV3 for this task。

 let's load the pretrain layout reader model from Hing face。

This model takes bounding box coordinates as input and predicts the reading order position for each box。

The model has been trained to understand common document layouts， including single column。

 multi column， tables， and mixed layouts。

![](img/5f85a464d3154908d335dc92bcdd3f82_10.png)

With the model loaded， let's define the core function for reading order detection。



![](img/5f85a464d3154908d335dc92bcdd3f82_12.png)

Here is what it does step by step。 First， we calculate the image dimensions。

 We estimate the image size from the bonding boxes with 10% padding。 Second。

 we normalize the coordinates。 layouty L M expects coordinates in a 0 to 1000 range。

 so we scale our bounding boxes。

![](img/5f85a464d3154908d335dc92bcdd3f82_14.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_15.png)

Third， we prepare the inputs。 We convert it to the format that the transformer expects。Fourth。

 werun inference and get the model's prediction。Last but not least， we parse the results。

 We extract the reading order from the model's output los。



![](img/5f85a464d3154908d335dc92bcdd3f82_17.png)

The result is a list that tells us the reading order for each OCR text region。

 Let's see the reading order in action。

![](img/5f85a464d3154908d335dc92bcdd3f82_19.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_20.png)

This visualization overlays numbers on each text region showing the sequence in which they should be read。

 The numbers in red indicate the reading position。 Not the logical flow。 Ti first。

 then the content Following the natural way a human would read the document。 Of course。

 is not perfect。 with some jumping around。 And this shows some of the limitation you may face with this approach。

 And depending on the complexity。 you may have to fine tune your own layout model for chunking and reading order。

 which can be hard to develop， scale and maintain。 Finally。

 let's combine our O CR text with the reading order to produce properly sequence text。

 This function pairs each O CR region with the corresponding reading position。

 Then it sorts all regions by their position。 and returns a list of dictionaries with position， text。

 confidence and bonding box info。

![](img/5f85a464d3154908d335dc92bcdd3f82_22.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_23.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_24.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_25.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_26.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_27.png)

This order text will become part of our agent's context。

 allowing we to understand the document content without needing to call a VLM for basic text questions。



![](img/5f85a464d3154908d335dc92bcdd3f82_29.png)

Now that we can extract and order text， we need to understand what types of content exist in the document。

 This is where layout detection comes in。 As you've seen in the previous lab。

 Pado OCR provides a separate layout detection class specifically for identifying document structure。

 let's initialize it Now， Next， we define the process document function to run layout detection and return a list of detection regions。

 Each region includes the label， the type of content like text， table， chart， figure， etc cetera。

 The score， confidence score for the detection。

![](img/5f85a464d3154908d335dc92bcdd3f82_31.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_32.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_33.png)

B box， Bny box coordinates and X， Y， X， Y format。 Let's take a closer look at the top five detector regions。

 Notice the different content types。 You have text blocks， chart and paragraph title。



![](img/5f85a464d3154908d335dc92bcdd3f82_35.png)

Similar to our OCR results， let's create a layout region data class for clean data handling。

Each region will get a unique ID that our tools need to reference specific regions。



![](img/5f85a464d3154908d335dc92bcdd3f82_37.png)

Then we'll loop through each result and store it in a structured format。 Now。

 let's visualize all the layout regions with color coded boxes。 Each region type gets a unique color。

 and we display the region I D type and confidence score。 As you can see， we identified titles。

 tables， charts and bodies of text。 with our layout regions identified。

 We need to prepare them for the agent for our agent to analyze a chart or table。

 We need to send a crop region to the VLM。 This approach has several benefits。

 First is focused analysis。 The VLM only sees the relevant content。 Second is reduce noise。

 Sur text does not interfere。 Third is lower cost。 Small images mean lower API cost。 Now。

 let's crop each region using the crop region function。 We also convert images to base 64 encoding。

 which is the format vision APIs expect。 then let's load the image。



![](img/5f85a464d3154908d335dc92bcdd3f82_39.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_40.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_41.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_42.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_43.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_44.png)

And use these two functions to create a dictionary containing information for each cropped region。

Keep in mind that even though VLMs are powerful， they're not great at localization。

This approach may help improve accuracy， but you'll need to find two new prompts for various edge cases to deal with greater complexities and variants。

 Let's display all the crop regions to see what content the agent will have access to Each region is labeled with its ID and type Now that we have the text extracted and ordered and a layout detected we can start building our agent starting with the tools。

 will create two specialized tools。 Each design for a specific type of content analysis。

 Analy chart uses a vision language model to interpret charts and figures。

 Analy table also uses a VLM to extract structure data from tables by creating specialized tools。

 we can use optimized prompts for each content type and return structure Json that is easy to process for VLM。

 we will use G for mini from openaiI。 Next， let's define the prompts for each tool。



![](img/5f85a464d3154908d335dc92bcdd3f82_46.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_47.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_48.png)

we use are critical for getting useful structure output from the VLM。

 Each prompt will have three components。 First will define the role。 In this case。

 you are a chart analysis specialist。 Second， will define what to extract specific fields like chart type axes and data points。

 then we'll provide a Json template to ensure consistent output format。

 While define prompts will help ensure the VLM returns data。

 our agent can reliably use we'll use the same logic for the second prompt。

 before creating our tools， let's define a utility function that handles the mechanics of calling the VLM with an image。

 It creates a multimodal message containing both the text prompt and the base 64 encoded image then returns the models response。

 The a tool decorator from link chain transforms our function into an agent usable tool it takes in the region I checks if the region exists using the dictionary。



![](img/5f85a464d3154908d335dc92bcdd3f82_50.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_51.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_52.png)

Regions we just created get the region data and then passes the cropped image in base 64 and the corresponding prompt to the VLM。

 Following the same pattern， let's create our second tool for table extraction。

 it uses the table specific prompt to guide the VLM in extracting structured data with proper headers and row organization。

 before integrating our tools into the agent， less test them individually。

 This verifies that the VLM connection works and our prompts produce useful output。

 We'll find the first chart region and analyze it。 notice that the data points are close。

 but not 100% accurate。 This is due to a lack of visual reasoning and localization capabilities I mentioned earlier。

 Similarlyly， let's test the table tool。 This tool does a decent job of extracting the information from this simple table。

 However， as complexity grows。 the agent may have a harder time localizing extracting and may be prone to hallucination。



![](img/5f85a464d3154908d335dc92bcdd3f82_54.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_55.png)

With our tools tested and working， we're ready to build the agent that will orchestrate everything。

 So how does the agent work。 First， the agent will receive a question about the document。 Second。

 it reads the system prompt containing all O CR text and the layout info。 Third。

 it will decide whether or not it can answer from text alone or need to use a tool。

4 for visual content like charts and tables。 It will call the appropriate tool。

 And last but not least， it will combine all the information into a coherent response。

 before building the agent， lets verify that our data structures are ready。

 We need both the order text from the O CR plus the layout Lm and the layout regions from layout detection。

 Now， let's prepare the context for our agent。 The agent needs a well formatted system prompt。

 So these helper functions convert our data structures into readable text as strings。

 the formatted context。

![](img/5f85a464d3154908d335dc92bcdd3f82_57.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_58.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_59.png)

As the agent's memory of the document。 Now we construct the system prompt。

 which is the foundation of our agent's behavior。 It contains the role definition。 In this case。

 you are a document intelligence agent， the document context， all OCR text in reading order。

 the layout information， region types and Is， tool descriptions。

 when to use each tool and the instructions。 how to handle different content types。 Finally。

 let's put it all together。 We'll use length chains， create tool calling agent to build our agent。

 This involves tools list， our analyze chart and analyze table functions。

 the LLM GT40 mini for cost efficiency。 The prompt template， which combines system prompt。

 user input and scratch pad。 Then we'll create an agent that can call tools。



![](img/5f85a464d3154908d335dc92bcdd3f82_61.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_62.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_63.png)

Last but not least， we'll set up the agent executor to run the tool in a bold loop。

 We'll set verbos equal true， which is a setting that lets us see the agent's reasoning process with our agent assembled。

 let's put it to the test。 First， we'll ask a general question about the document。

 They should be answerable from the O C R text alone without calling any tools。



![](img/5f85a464d3154908d335dc92bcdd3f82_65.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_66.png)

Watch how the agent uses its context to respond。

![](img/5f85a464d3154908d335dc92bcdd3f82_68.png)

Now let's ask the agent to extract table data， Watch how it identifies the table region and calls the analyze table tool to get these structure data。

 the verbo output shows the agent's reasoning or quote unquote thinking process。



![](img/5f85a464d3154908d335dc92bcdd3f82_70.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_71.png)

For our final test， let's ask about the chart。 This agent will use the analyze chart tool to extract visual information about the trends and data points that cannot be determined from OCR text alone。



![](img/5f85a464d3154908d335dc92bcdd3f82_73.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_74.png)

![](img/5f85a464d3154908d335dc92bcdd3f82_75.png)

And that's it in this lab， we built a complete agenttic document intelligence pipeline that combines multiple AI technologies to understand complex documents。

 Together， these components form a hybrid system that can deeply understand more complex reports。

 tables， figures， multi columnlum layouts， captions and narrative flow。 however。

 as documents become more diverse and more variable。

 These multiagent pipeline can begin to break down。 It becomes hard to maintain。

 Bririttle across edge cases and difficult to scale because each component must be tuned。

 monitored and orchestrated manually， and the next lesson。

 Andrea will introduce landing AI's agenttic document extraction。

 which unifies all the essential steps for document understanding。 layout analysis， text extraction。

 region segmentation， reading order reconstruction。

 multimodal reasoning and schemabased field extraction into a single。



![](img/5f85a464d3154908d335dc92bcdd3f82_77.png)

Coordinated agent workflow。 See you all there。