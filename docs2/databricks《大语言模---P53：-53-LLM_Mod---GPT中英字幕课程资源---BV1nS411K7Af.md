# databricks《大语言模型：从生产到应用｜Large Language Models： Application through Production》 - P53：-53-LLM Module 5_ Society and LLMs _ 5.1 Introduction.zh_en - GPT中英字幕课程资源 - BV1nS411K7Af

![](img/f08f2fdf86a126dc526c8ec979a2ba24_0.png)

Welcome to module5 which is about society and LLMs and some of the risks that you using LLMs can have and various ways to mitigate them so so far in the course we've seen a lot of you know pretty cool examples of how we can build and use LLMs for a bunch of applications and they often make for like really good initial demo there are ways to make it even better over time but there are some risk with it and in this module we want to talk about some of the largest risks with LLMs to increase awareness of them and make sure people understand the limitations and also some ways available to mitigate some of these so LLMs can can produce various kinds of unreliable behaviors I'll just mention two of them really quickly and we'll talk about what to do about them one of the first sources of bad behavior has to do with the language modeling itself right if you train your LLM on a whole bunch of data especially。

From the web the data might have biases in some fashion that you don't want your application to have maybe so that's bad because it learns the bias because it just learns the language that's out there。

 the data might also be about certain things you you don't want a language model that's asked the medical question and it turns the popular wisdom from the web when you you're building an application where it has to be something approved by by the government or it has to be the latest scientific knowledge or something like that there's just a lot of junk on the web there's offensive text there's like search engine optimization so it's not necessarily great so that's like one problem your language modeling and you're just getting you're modeling the facts that you don't want to learn second example is what's called hallucination where the model when it doesn't really know what to say it will still make something up and it can sound very confident about it and beyond so these are like some of the risk。

There are other things as well， and we'll talk about some ways to mitigate some of these risks and to design applications where users aren't fooled into intotaking these risks。

 including things like basic generations and retrieval from a knowledge base that's been reviewed。

 different ways to evaluate how well the model is doing and just the kind of things to watch out for in this space。



![](img/f08f2fdf86a126dc526c8ec979a2ba24_2.png)