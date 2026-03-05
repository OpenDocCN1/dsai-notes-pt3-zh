# 【Databricks】Llm模型底层基础 ｜ Llm： Foundation Models From The Ground Up p02 P02_模块_1-Transformer-1.1_介绍 -BV1LZp9zXEab_p2-

![](img/368e35c382dd50383335abcc22862c3d_0.png)

Welcome to our first module of the course， which is about Transers。

 the main neural network architecture used in virtually all large language models today。

 so if you only pay attention to one thing in this course。

 this is a good one to look at transformers in their current form were first published in 2017 with the BRT paper and since then most large language models have been some kind of variation on them including GPT the pre-trained transformer model from openaiI that's had a lot of impact in the current of chatbased language models so one of the really interesting things about transformers is that before this point there was really rapid experimentation with many deep learning model designs。

 it was sort of like a Cammbian explosion of all these different layers you could combine all these functions。

 all these modules。After Transers actually at least for natural language。

 many models design have followed the same basic building blocks。

 so we focused more on the different training techniques。

 the way to generate data for these and so on， and no one's really made massive changes to the underlying architecture so it's a pretty powerful architecture as you'll see it allows the model to learn many different kinds of interactions between different aspects of its input and it's something that you can also stack with itself to different depths so you can get different qualities of models and even though there are variations today that make certain things faster or cheaper and so on。

 the basic building blocks are the same so it's important to really understand this in detail and be able to to both interpret kind of what the models are doing and evaluate kind of new changes to this architecture。

