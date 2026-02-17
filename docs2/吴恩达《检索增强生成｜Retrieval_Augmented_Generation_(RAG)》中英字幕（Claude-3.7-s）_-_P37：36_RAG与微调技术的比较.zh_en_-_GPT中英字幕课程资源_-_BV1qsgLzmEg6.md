# 吴恩达《检索增强生成｜Retrieval Augmented Generation (RAG)》中英字幕（Claude-3.7-s） - P37：36_RAG与微调技术的比较.zh_en - GPT中英字幕课程资源 - BV1qsgLzmEg6

While RaG is a popular and powerful approach for improving the performance of an LM。

 another technique called fine tuning is also frequently used。

 rather than just augmenting the prompt。 fine tuning retrains and off the shelf LLM to improve performance in a specific context。

 Let's look more closely at fine tuning and what role it can play in your ragg system。

 The core idea of fine tuning is to retrain a language model with your own data to update its internal parameters。

😊。

![](img/b9ca8215d658172779f56c7c01e33418_1.png)

Typically， this is done through supervised fine tuning or SFT。

It's supervised because the model is retrained using a labeled data set from the domain the model is being adapted to。

Instruction， fine tuning in particular， refers to an approach in which the dataset set includes both a set of instructions to the language model。

 typicallyyically a prompt or a question， as well as an expected ground truth best answer。

To fine tune the model， you feed it the input instructions and see how close the output is to the correct answers from your dataset。

 you then use these results to adjust the model's internal parameters to better align with the correct answer。

This process is very similar to the way language models are initially trained。

 but the dataset set used is taken from a specific domain。

 The model is being fine tuned to specialize in。Suppose you want to fine tune in a model to work in the healthcare domain to start。

You would choose a general purpose language model。 If you ask this model about a specific set of symptoms。

 say joint pain， skin rash， Sun sensitivity。 the language model might give you a generic answer in a generic tone。

This is because the off the shelf model hasn't been specialized on medical data。

 If you use instruction tuning on that same model， training it on a lot of medical domain instructions and responses。

 the model essentially becomes much more of an expert at answering that kind of question。 Now。

 if you gave it that same prompt， it'd be able to respond with more accuracy detail and in a style that's more appropriate for the medical domain。

Fine tuning can work well in instances like this one where you want the model to specialize in a particular domain。

 like providing an initial medical diagnosis or summarizing legal briefs。

While the model's performance will improve in that domain。

 fine tuning can actually decrease performance in other domains。

The fine tuning process is only optimizing the model's performance in the target domain。

 which means that sometimes adjustments made to the model's internal parameters will lead to lower performance with other kinds of requests。

So long as the model will only be used within the domain it's being specialized for。 However。

 this trade off is usually worth it。 a particular place。 this is true。

 If for small models used inside agent systems。 If you know ahead of time。

 a model's only job will be to determine whether a prompt requires retrieval from vector database。

 Youre more than happy to use a small lightweight model and heavily fine tune that model to only perform well at that single task。

 It's worth noting， fine tuning is usually not a great way to teach an an am new information。😊。

The way a model is adapted by fine tuning tends to have a greater impact on how the model responds to prompts。

 like the words it uses， style or structure， and less pronounced impact on what information the model knows。

This last point hits at some of the pros and cons of rag versus fine tuning。

 so let's talk about when it makes sense to use each。In short。

 the current consensus is that RaG is best at knowledge injection and fine tuning is best at domain adaption。

 If you need the LLM to have access to new information。

 retrieval augmented generation is the best solution。You can inject that information into the prompt。

And an off the shelf LLM will be able to incorporate that new information in its response。 If。

 on the other hand， you want your LLM to specialize in a certain task or domain。

 fine tuning is the way to go。Especially if your LM will be handling one discrete task like routing prompts in your rag system or responding to only a certain type of prompt。

 fine tuning makes a lot more sense。 fine tuning a rag can also be used together In particular。

 you might fine tune a model specifically to incorporate retrieved information into its final responses。

In other words， you're helping the model specialize in its role within the RAG system。

When deciding whether to use fine tuning or rag。The best choice might be both。

Each approach improves the model's performance in different ways。

 and there are benefits to using both of them together。

 If you want to incorporate fine tuning into your own rag system。

 I recommend you take a separate course on fine tuning and explore how to fine tune your own language model。

 fine tuning is a complex topic， and itd be impossible to adequately cover it within this course。

 That said， often you can find models that have already been fine tuned for you and adapt it to a particular task or domain。

 If you think your system needs a fine tune model， Many online repositories of previously fine tune models are available。

 and you might be able to use one of those without doing the fine tuning yourself。



![](img/b9ca8215d658172779f56c7c01e33418_3.png)

Fine tuning and RaG are sometimes described as competing alternatives。

 but they're more accurately viewed as complementary tools。

 adding fine tune models into your RAG pipeline or even fine tuning the core LLM that generates your final response can help improve your system's performance。

While you won't dive and fine tuning techniques in this course。

 it's definitely worth exploring as you continue to build your generative AI skills and look for ways to optimize your RAG systems。



![](img/b9ca8215d658172779f56c7c01e33418_5.png)