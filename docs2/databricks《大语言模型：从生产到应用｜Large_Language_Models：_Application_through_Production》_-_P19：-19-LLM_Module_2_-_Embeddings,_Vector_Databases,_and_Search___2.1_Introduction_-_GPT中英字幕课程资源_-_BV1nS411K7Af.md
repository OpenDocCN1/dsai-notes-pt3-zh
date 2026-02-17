# databricks《大语言模型：从生产到应用｜Large Language Models： Application through Production》 - P19：-19-LLM Module 2 - Embeddings, Vector Databases, and Search _ 2.1 Introduction - GPT中英字幕课程资源 - BV1nS411K7Af

![](img/35af43ea178b0dd2de0443962a187369_0.png)

Welcome to our second module， embedding vector databases and search this is actually an areaA that I've been doing a lot of research in with my research group at Stanford so very excited to talk about about this and it's one of the things that really increases the capabilities of LLMs dramatically so in the previous model we saw some simple applications of LLMs at a high level and in this module we want to dive into detail into one of the more common applications which is called knowledgebased question answering basically getting an LLM to use information in a bunch of documents and knowledge base to answer questions and do task related to a specific areaEA and at databases this is definitely the most common applications we see in practice lots of organizations have custom data sets custom knowledge things internal to their company and they want an LLM to help them do things related to that。

So knowledgegebased QA makes a lot of sense as a very common application because it really helps people be more productive。

 you can use that for internal processes inside your company。

 you can use that for you user- facing stuff， things like customer support you can also update the knowledge very quickly you can just plop in some new documents and your application begin answering questions about them and it works around many of the fundamental challenges that just a language model alone has。

 for example， a language model alone may not accurately remember all knowledge but if you put it into an application that you looks up some documents and cites them and returns a source for everything and generates。

 suddenly you've got something more reliable and something where the user can look at it and judge and say yeah。

 this is accurate or it isn't so this is the kind of thing that we're going to do and so at the high level we're using an LLM to understand and process information in our knowledge base。

But where do embeddings vector databases and search come in。

 where these are the tools that we use to help the LLM find the appropriate knowledge for a particular task and then use it。

 so embeddings are a powerful kind of feature you can get out of the way language models work where you can map documents and questions to mathematical vectors and find related things very easily。

 vector databases are a type of search technology really you can use classical keywordbased search as well。

 that help you search for relevant documents given a task or an input that you have and you can actually train them to be good at that and basically will take our LLM take some input to it。

 you search for relevant knowledge and then feed that knowledge plus the original question into it and try to get it to answer things and we'll talk about these foundational technologies are that are required to do this and some of the algorithms in this space。

This space is fast evolving， but we think it is one of the most common things you'll want to do when putting LLMs into practice。

 especially in a custom domain。

![](img/35af43ea178b0dd2de0443962a187369_2.png)