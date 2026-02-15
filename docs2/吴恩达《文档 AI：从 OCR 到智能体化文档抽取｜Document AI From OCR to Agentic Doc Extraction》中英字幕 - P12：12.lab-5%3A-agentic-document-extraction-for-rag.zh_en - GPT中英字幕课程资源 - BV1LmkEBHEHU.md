# 吴恩达《文档 AI：从 OCR 到智能体化文档抽取｜Document AI From OCR to Agentic Doc Extraction》中英字幕 - P12：12.lab-5%3A-agentic-document-extraction-for-rag.zh_en - GPT中英字幕课程资源 - BV1LmkEBHEHU

![](img/268f58d45f206bfc91e4083b9625939c_0.png)

In this lab， you apply your experience parsing and extracting information from documents for a rag By the end of the lab。

 youll have implemented a workflow for answering questions about a document。



![](img/268f58d45f206bfc91e4083b9625939c_2.png)

We'll use some of the same libraries from the previous lessons， including Open AI。

 Langchain and pillow。 We'll use two models from OpenaiI Tex embedding 3 small for our embedding model to convert parse chunks and to vectors and G5 mini for our language model to provide answers to questions。

 We'll use Chroma Db for vector database and Lcha to connect retrieved chunks from the database to our prompt for the language model。

 We've also provided a utility to visualized chunks that were used to generate the answer。

 Let's take a look at the document we're working on in this lab。 is the Apple's 10k report。

 a publicly available report that US companies must file to regulatory agencies like Se for audit。

 It provides detailed information about their business throughout the fiscal year。

 We've already run landing AI AE on the document for you。



![](img/268f58d45f206bfc91e4083b9625939c_4.png)

![](img/268f58d45f206bfc91e4083b9625939c_5.png)

![](img/268f58d45f206bfc91e4083b9625939c_6.png)

You can find ADdeE parse results MD and JSson under ADde outputs in the lessons folder。

 remember from the previous lesson that parsing yields a markdown file containing all the data from the document along with a JSsonN file containing is metadata Let's load the markdown content and display a preview for the first page As you've seen in the previous lab。

 the markdown file contains snippets of HTML call anchor tag which indicate the unique identifier of each chunk we can use the ID to link each chunk in the markdown file to its metadata in the JSsonN file Now let's load the chunks and examine the structure of the first chunk Each chunk has five key fields chunk ID which is the unique identifier chunk type what kind of content this is text table figure etc the text which is the actual content including the HTML anchor tags with unique ID for that chunk B。



![](img/268f58d45f206bfc91e4083b9625939c_8.png)

Bounding box coordinates for the chunk page which page this chunk came from The Boing box is critical。

 This is what makes landing AI different。 Every chunk traces back to its exact location in the original document When we retrieve a chunk later。

 we can show where it came from。

![](img/268f58d45f206bfc91e4083b9625939c_10.png)

Let's set up our vector database As you can see here we've already defined where we want to store our data。

 This path points to a folder called chromroma Db right here in our lessons directory and we're naming our collection Ade underscore documents。

 This is where we'll store all our document embeddings。 Next。

 we specify which embedding model to use here we're using open AIs text embedding three small model to convert text into embeddings Now this line instants our Cha Db client noticeice we're using persistent client here。

 which is important。 This means our data will be saved to our disk。 Finally。

 this line creates our collection。 We're using get or create collection， which is really convenient。

 If this collection already exists it will load if not it creates a new one and that's the setup。

 we're not ready to start populating the database with chunks。

 we've already loaded the chunks into the vector database for you。

 So if you check for existing chunks。 you'll see that there are already for。

53 existing in the collection。 But let's say this is your first time loading ADE chunks into the vector database。

 our collection Next， we extract the text and skip any empty chunks and then generate embeddings using open as API Now to prepare the metadata we extract the chunk type page number and the bounding boxes。

 Once we add everything to our Cha collection， you have the text the chunk ID metadata and the embedding。

 we just generated in the collection。 As you can see since the chunks were already preloaded。

 we added zero new chunks to the collection。 Now that we have data and metadata in our database。

 we can queryrry the vectors to retrieve relevant chunks。

 we write a function call rag core to help us with this the function takes four parameters The question the user' input question in natural language top K how many results to return from the vector search default is equal to3 the threshold minimum similar。



![](img/268f58d45f206bfc91e4083b9625939c_12.png)

![](img/268f58d45f206bfc91e4083b9625939c_13.png)

![](img/268f58d45f206bfc91e4083b9625939c_14.png)

![](img/268f58d45f206bfc91e4083b9625939c_15.png)

![](img/268f58d45f206bfc91e4083b9625939c_16.png)

score to include in the results defaultult is 0。25 and show images whether to show visual grounding from the original Pdf defaultult equals true。

 Let's break down what the function does。 First， we embed the question。

 which cons your question to a vector using the same embedding model we use for the chunks。 Second。

 we query chroma Db to find the top K nearest vector to your question。 Third。

 parse results to extract documents， metadata， distances and Is from the response。



![](img/268f58d45f206bfc91e4083b9625939c_18.png)

![](img/268f58d45f206bfc91e4083b9625939c_19.png)

![](img/268f58d45f206bfc91e4083b9625939c_20.png)

![](img/268f58d45f206bfc91e4083b9625939c_21.png)

Fourth， we filter by the threshold。 So we only show results above the minimum similarity score。

 and fifth， we visualize using our helper utilities。

 We extract and highlight the chunk from the original Pdf to show exactly where the information came from。

 Let's test our query function。 We'll ask about Apple's net sales in 2023。

 The same question we tried with reexx earlier。 Not how we're seeing top K equals 5 to get more results and thresholds 0。

32 to filter out weaker matches。 Let's look at the five results。 The question was。

 what was Apple's net sales in 2023。 Keep in mind， these are semanically similar answers So they may not be perfect。

 The first response gives you a clear breakdown of net sales for the previous three years by products and services。

 second， third and  fifth are giving you tangential information about net sales in 2023。

 which doesn't directly answer the question。 The fourth result。



![](img/268f58d45f206bfc91e4083b9625939c_23.png)

![](img/268f58d45f206bfc91e4083b9625939c_24.png)

![](img/268f58d45f206bfc91e4083b9625939c_25.png)

![](img/268f58d45f206bfc91e4083b9625939c_26.png)

![](img/268f58d45f206bfc91e4083b9625939c_27.png)

![](img/268f58d45f206bfc91e4083b9625939c_28.png)

![](img/268f58d45f206bfc91e4083b9625939c_29.png)

the same answer as the first one。 So in production。

 you can tweak the parameters to get the answers you actually need。

 What if you want to ask questions about a table， It is common that financial data is found in a lot of tables。

 This is where hybrid search can help us First， we vectorized a question or the user input What was Apple's total revenue in 2023。

 We'll still use semantic similarity So we'll match total revenue to net sales by meaning。 Second。

 we'll use metadata for filtering。 So in this case。

 we're only looking at chunks where the chunk type is table。 As you can see from the result。

 you can see the table tag in the markdown。 which means that we're pulling information from tables。

 feel free to use the helper methods to visualize this chunk。

 and feel free to use other filters like page number and chunk types Now that we can retrieve a11 chunks we can incorporate this into a full rack pipeline。

 we can create a retriever object from our Cha Db database。



![](img/268f58d45f206bfc91e4083b9625939c_31.png)

![](img/268f58d45f206bfc91e4083b9625939c_32.png)

![](img/268f58d45f206bfc91e4083b9625939c_33.png)

Wwhich slots into a length chain chain then we can build the actual rag chain and we need three components first is the prompt template。

 we define a system prompt then instructs the LLM to use the retrieve context to answer questions the context placeholder is where length chain will inject the retrieve chunks and the input is where the user's question goes second is the language model We will initialize the LLM GT5 mini that will generate answers based on the retrieve context。

 third is the rag chain。 we use length chains create retrieval chain to connect the retrieval to our prompt and LLM。

 This chain automatically handles the flow Take the user's question retrieve 11 chunks。

 then inject them into the prompt to generate anans We could answer that question by inspecting the retrieve chunks directly but what about questions that require comparing multiple chunks of information For example。

 comparing total revenue across multiple years。

![](img/268f58d45f206bfc91e4083b9625939c_35.png)

How the total revenue trend between 2022 and 2023 for iPhone sales This is where the language model can reason through multiple chunks of retrieved data so beyond simple lookups。

 you can also use this approach to look for discrepancies across multiple documents get the latest version of an amendment and illegal documents。

 lists not all versions of that amendment or get a summary on a specific topic with grounded sources。

 you can do things like analyzing research papers， reports and regulatory documents for commercializing a drug in summary by combining embeddings。

 vector databases and RaG you can transform raw extracted data into accurate insights from multiple documents and files。

 delivering faster， smarter document understanding in our next lesson we'll review how to deploy ADE in the cloud。

 scaling our RaG application through an event-dven architecture that automatically triggers ADE for document processing whenever new documents appear。



![](img/268f58d45f206bfc91e4083b9625939c_37.png)

I will see you there。