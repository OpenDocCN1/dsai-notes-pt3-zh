# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p07 6_数据科学项目的结构.zh_en -BV1L9Fde5EXS_p7-

This lecture discusses the basic structure of a data science project。



![](img/2797732a00b98ae0037b9f0105642f46_1.png)

A typical data science project will be structured in a few different phases that I'll talk about in separately in this lecture so there's roughly five different phases that we can think about in a data science project the first phase is the most important phase and that's the phase where you ask the question and you specify you know what is it that you're interested in learning from data now specifying the question and kind of refining it over time is really important because it will ultimately guide the data that you obtain and the type of analysis that you do part of specifying the question is also determining the type of question that you're going to be asking and so there are roughly six types of questions that you can ask going from kind of descriptive to exploratory to inferential to causal to predictive and mechanistic and so figuring out what type of question you're asking and what exactly the question is is really influential and so you should spend a lot of time thinking about this once you've kind of figured out。

What your question is typically you'll get some data now either you'll already have the data or you'll have to go out and get it somewhere or maybe someone will provide it to you but the data will come to you and then the next phase will be exploratory data analysis so this is the second part and there are two main goals to exploratory data analysis the first is you want to know if the data that you have is suitable for answering the question that you have and so this will depend on a variety of factors depending on very basic things like are there is there enough data are there too many missing values things like that to more fundamental ones like are you missing certain variables or do you need to collect more data to get those variables etc the second goal of exploratory data analysis is to start to develop a sketch of the solution and so if the data are appropriate for answering your question you can start using it to kind of sketch out what the answer might be to get a sense of kind of what what it will look like this can be done without any formal modeling or any kind of statistical testing or things like that just to get a good picture。

What it might be the next stage， the third stage is formal modeling。

 So if your sketch kind of works out， you've got the right data and it seems appropriate to move on。

 the formal modeling phase is a way to kind of specifically write down what questions you're asking what parameters you're trying to estimate and it also provides a framework for challenging your results so just because you've come up with an answer in the exploratory data analysis phase doesn't mean that it's necessarily going to be the right answer and you need to be able to challenge that your results through a variety of approaches sensitivity analysis or other types of analysis So challenging your model and developing a formal framework is really important to making sure that you can develop robust evidence for answering your question the next phase is interpretation So once you've done your analysis your formal modeling you want to think about how to interpret your results and there are variety of things to think about in the interpretation phase of a data science project the first。

To kind of think about how your results jive with kind what you expected to find when you were first asking the question and also you want to think about the kind of the totality of the evidence that you developed at this point。

 you've probably done many different analyses you've probably fit in many different models and so you have many different bits of information to think about and part of the interpretation face is to kind of assemble all that information to weigh the different pieces of evidence so that you know of which are more reliable or which are more important than others and to get a sense of the totality of the evidence with respect to kind of answering the question。

The last phase is the communication phase and so any data science project that is successful will want to communicate its findings to some sort of audience now that audience may be internal to your organization and may be external it may to a large audience or even just a few people but communicating your findings is an essential part of data science because it informs a data analysis process and it translates your findings into action so and that's kind of the last part which is not a formal part of a data science project necessarily。

 but often there will be some decision that needs to be made or some action that needs to be taken and the data science project will have been conducted in support of making decision or taking an action so that last phase will depend on more than just the results of the data science or the data analysis but require inputs from many other different parts of an organization or from other stakeholders so ultimately if the decision is made the data analysis that was done inform that decision and will support。

😊，And the evidence that was collected will support that decision So these are roughly the five phases of a data science project。

 there's the question there's exploratory data analysis， there's formal modeling。

 there's interpretation and there's communication Now there is another approach that can be taken it's very often taken in data science project and that is to really start with the data and to start with exploratory data analysis so often there there will be a data available but it won't maybe be immediately clear kind of what the data will be useful for so it can be useful to kind of do some exploratory data analysis to look at the data to summarize it a little bit make some plots and see what's there and to generate some interesting questions based on the data so this is sometimes called hypothesis generating because it kind of produces questions that were not already there once you produce the questions that you want to ask based on your initial kind of exploratory data analysis it may be useful to kind of get more data or other data to kind of do an exploratory data analysis that。

spececific to your question now and then continue with the formal modeling。

 interpretation and communication。 One thing that you have to be wary of is to do the exploratory data analysis in one data。

 develop the question and then go back to the same data set and pretend like you hadn't done the exploratory data analysis before and and then and come at it with say a fresh question that goes on to the rest of the stages this often be a recipe for kind of for bias in your analysis because the question and the results were derived from the same data so it's important to be careful about doing that and to try to obtain other data when you're using the data to generate the questions in the first place so this is the kind of secondary approach to data science that that can be very useful and can be often result in many interesting questions that are kind generated from the data data science projects have a variety of phases and its important kind understand which phase you're in so that you can know how to progress。



![](img/2797732a00b98ae0037b9f0105642f46_3.png)

How to move forward with any data science project。

![](img/2797732a00b98ae0037b9f0105642f46_5.png)