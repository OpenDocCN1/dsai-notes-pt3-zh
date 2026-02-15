# 吴恩达《检索增强生成｜Retrieval Augmented Generation (RAG)》中英字幕（Claude-3.7-s） - P1：0_与吴恩达的对话.zh_en - GPT中英字幕课程资源 - BV1qsgLzmEg6

Welcome to Retrieval augmentmented Generation from De AI。

Retval augmented generation or RaG is the most widely used technique for improving the quality and accuracy of a large language model's response。

 An OM starts off knowing only information from maybe the public internet data it was trained on。

 So if we needed to answer questions using facts drawn from proprietaryriety data。

 Sa your own documents。 RaG lets the model do this by providing the model access to that additional data。

Just doesn an LM answer questions with facts that it was not already trained on。 For example。

 you may also have seen a chatbot like Cha G P or Cla Gemin I tell you is searching the web to help answer your question。

 This LM is accessing additional information to try to make sure the responses up to date and accurateate。

 I'm excited to introduce your instructor thiscourse Z Hasan。

 Z has experienced AI and machine learning engineer and researcher and educator。

 He spent much the last decade working at a handful of exciting AI companies like Reviate。

 which is a leading vector database company providing one of the key components Ra as well as to get AI。

 which is a provider ofM services。😊，Thank you， Andrew。 I'm super excited to be here。😊。

What I love about RaG is the fact that it provides a simple and practical way to focus the power of large language models。

The core idea of Ra is pairing classical search systems with the reasoning abilities of large language models。

 With this course， we've tried to balance covering foundational concepts underlying both search and LLMs and the practical tips for applying these concepts to architect a high performing rag system。

Even though the concept of RA is not complex， there is a zillion waste to implement it and the design choices make a huge difference in accuracy and speed of your system。

You'll learn how to prepare your data to be used in this system。

 prompt your language model to get the most out of that data。

 and evaluate actual user traffic to ensure you're providing high quality responses。

So you're going to leave this course with a lot of practical skills to build and tune your rag system and have the foundational understanding of why these techniques work。

 It's an incredibly useful skill set and has applications to a huge variety of industries。

I think RAG may be the most commonly built type of OM based application in the world today。

 large companies are using it to help their customers get answers to questions about their products or help their own employees get answers to the company's internal policies or other matters starts are also building RAC applications in many verticals like healthcare。

 such as answering medical questions or in education to help to the students on a range of subjects and so on。

 One interesting thing about RaG is that as Om technology improves。

 RaC systems are also rapidly incorporating these technologies So for example。

 the recent generation of models have been much better than those from one or two years ago at getting RAC systems to be more grounded in the documents or context as given so that over the last year or so it feels like the hallucination rates of rack systems have been steadily trending downward。

And reason models also let them tackle much more complex questions and can reason on top of the provided context and one interesting change over the last couple of years is as the input context window of elementss has gone up the hyperpara tune what exactly do you insert into the Ra how do you cut documents that pieces a signal input context。

 the best practices which then is really exp on has been evolving as well because now you don't need to squeeze so much information into tiny little context window and as agent document extraction and related technologies improve you can now also more easily build rag systems on top of PDF files or slides other types of documents so you can build rag systems to more easy ingest and reason over and answer questions relating to broader sense of materials that you may have and more broadly as teams are building more complex multistep agent workflows。

 Ra is often than one component in a complex。😊，Aent workflow where maybe on you know step five or step seven of some internal enterprise workload。

 Ra gives the agent the information that needs in order to process the doctrine or reason about the customer request oh。

 I completely agree。Even as the AI field continues to evolve rapidly。

 I don't think rag's going anywhere。LLMs will continue to benefit from access to high quality relevant data I also think this course gives a really strong foundation to work with all these cutting edge advances。

We've included a huge variety of advanced techniques in this course。

 from multimodal or reasoning models， like you mentioned， to balancing approaches like rag。

 fine tuning and newer long context models。 One technique that I'm personally quite excited about is agentic rag or building systems that use multiple large language models where each one handles a single part of a large workflow and has the agency to decide what data to retrieve。

This is right at the frontier of where companies are pushing the performance of LLM based applications。

 I think the earlier generation rack systems was a human engineer they would write a bunch of code but write a bunch of rules to decide。

 give the query， this is how we take a long document， how we cut the pieces。

 how we retrieve it and we're going to take you know seven pieces or something to put into own context。

 So as read the human engineer deciding what to give as context So they own to answer a question。

 and the thing that's really interesting about agenttic rack is you can give a AI agent tools to retrieve information and it let it decide。

 doesn't want to do a web search next。 And if so what keywords is want to use for the web search or maybe query a specific specialized database And after retrieve in the first round of information I it good enough or do you want to do a second round of retrieval。

 So these highly agentic systems can then decifi themselves what information to retrieve to serve a specific information need。

 And I find that to。😊，Be important way to make systems much more flexible and powerful。

 It gives them a way to deal with the messiness of the real world。 They mess up。 They can。

 can route back and fix the approach that they're going with。

So going all the way from basic RA to advanced agent Ra in this course you learn about this range of techniques。

 both from the core principles and the mental frameworks of how to build these systems to the practicalities of how to actually tune the hyperparameter of what the appropriate chunk size to cut a very long document into and how to manage context and if you are just sorting out on the earlier phases of building out GenI applications。

 I think that this course will give you a good overview of not just RAG but many of the components that go into RA but could be useful for other things you may build in the future as well。

 so I think that this course will set you up absolutely to do RAG but more broadly to have a good foundation to think about how to assemble many of the tools that we now have in GenI to build an application and to evaluate it and to drive continued improvements。

So far Zen and I have chatted about RaG and why we think is' important and why we think you benefit from learning about it and in the next video。

 Zan will present a high levell overview of what are the most important components of rag so that whether you're building a standardal low rag system or building less one component of a more complex agent auto type system。

 you have that mental map for what are the things you need to do to get an effective rag system going so let's take a look at the next video to dive into the details a rag。

😊。