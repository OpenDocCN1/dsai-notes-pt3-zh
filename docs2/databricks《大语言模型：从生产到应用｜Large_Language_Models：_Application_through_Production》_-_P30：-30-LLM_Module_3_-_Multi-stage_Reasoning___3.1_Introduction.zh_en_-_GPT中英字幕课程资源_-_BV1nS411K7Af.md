# databricks《大语言模型：从生产到应用｜Large Language Models： Application through Production》 - P30：-30-LLM Module 3 - Multi-stage Reasoning _ 3.1 Introduction.zh_en - GPT中英字幕课程资源 - BV1nS411K7Af

![](img/5d593ac017ded24480f84d0a9370d329_0.png)

Welcome to our third module on multistage reasoning this is a really exciting capability that people are developing with LLMs。

 basically building more complicated applications out of individual calls to language models so in this module we're going to start off by talking more about prompting and how to build more sophisticated pumps that get a model to reason in some way to produce better answers one of the common tools that will'll talk about this is palmM templates and there are various techniques like chain of thought that can guide the model into producing the kind of output you want using statistical capabilities and next we'll move to the concept of chaining pumps which allows you to create steps in your LLM application that are good at a particular subtask and put them together into something bigger that overall works well for a complicated task。

T about how this helps break down the problem， make it easier than just having a single giant pump and hoping it gets everything right and we'll talk about open source frameworks in this space like Langchain and basically this idea of chaining and of modularizing an application。

 much like in software engineering is allowing people to build applications using language models that can do sophisticated things and are still maintainable and controllable and high quality we'll also touch a little bit on the area of LLM agents so this is an LLM application that can use external tools know much of the way that a model can generate text as an answer。

 it could generate text that's actually an API call to some kind of tool and then you can sort of get a model to use these tools to do things that it couldn't do using using knowledge alone。

And so that also fits very well into this training paradigm and we'll also talk about sort of autonomous LLM systems that kind of discover which tools to use and how to do things as the this area of multistage reasoning is also near and dear to my heart as a researcher。

 we actually have a project at Stanford called demonstraterate search and Pre or DSP which is looking at a way to build pipelines of multiple LLM calls that are highly reliable and can also automatically be improved using data to make them better and again this is one of the fastest moving areas and LLMs but also really powerful really important to get your LLM to plug into other systems and do cool things with other software。



![](img/5d593ac017ded24480f84d0a9370d329_2.png)