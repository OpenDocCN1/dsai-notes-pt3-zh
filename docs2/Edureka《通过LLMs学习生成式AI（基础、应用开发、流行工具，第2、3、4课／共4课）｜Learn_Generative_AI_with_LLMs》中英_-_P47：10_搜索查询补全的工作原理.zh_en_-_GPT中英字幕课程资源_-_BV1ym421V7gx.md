# Edureka《通过LLMs学习生成式AI（基础、应用开发、流行工具，第2、3、4课／共4课）｜Learn Generative AI with LLMs》中英 - P47：10_搜索查询补全的工作原理.zh_en - GPT中英字幕课程资源 - BV1ym421V7gx

![](img/5a080daf1727e13695ff5e3a765ed7ab_0.png)

So let's now explore the progression from our previous discussion so now let's understand the stepby step working of search query completion。

 The very first step is that encoding and representation So what happens here It's like giving your words a secret code we transform plain text into something fancy that are supersmart language can understand think of it as turning words into numbers we have techniques like word embeddings or sentence encoders that convert everyday words into numerical vectors a special language for our computers It's like turning recipe into a set of step by step instructions for a robot chef we convert raw text into a format that are language models can digest so now here is a cool part word embeddings it's like giving each word a unique fingerprint capturing not just word it is but also the。

😊。

![](img/5a080daf1727e13695ff5e3a765ed7ab_2.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_3.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_4.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_5.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_6.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_7.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_8.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_9.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_10.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_11.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_12.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_13.png)

Flavor it adds to the sentence This helps the computer understand the meaning and context behind the words。

😊。

![](img/5a080daf1727e13695ff5e3a765ed7ab_15.png)

So in simple terms we are turning words into the secret codes。

 transforming the text into a language computer's love and giving each word a special fingerprint。

 That's step1 encoding entry representation So now let's understand the step two that is encoder decor architecture Imagine the encoder as the detective processing your incomplete search query and the context around it。

 It's like the brain that captures the key information。

 This is where the computer does its heavy lifting to understand what you are looking for。

 so now here is a secret source attention mechanism within the encoder think of them as Chinese spotlights that help the computer to focus on the important bits they highlight the essential words or the phrases just like underlining the key points in the text This helps the computer really get the context of what you are asking in simpler terms。

😊。

![](img/5a080daf1727e13695ff5e3a765ed7ab_17.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_18.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_19.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_20.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_21.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_22.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_23.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_24.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_25.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_26.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_27.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_28.png)

It's like your computer paying extra attention to the words that matter。

 making sure it understands the context around your search。

 the encoder does the job of capturing the main details and the attention mechanism ensure it does not must a bit。

 That's about encoded decoder architecture。 Then the next step is decoder for production。😊。



![](img/5a080daf1727e13695ff5e3a765ed7ab_30.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_31.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_32.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_33.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_34.png)

The decoder is a smart cookie。 It's conditioned on the information。 the encoder gathered。

 Think of it like having all the clues of detective phase。

 the incomplete search query and its context。 The decoder uses this information to generate the prediction。

 Now， here is the real trick。 the decoder predicts a probability distribution over your vocabulary of words or phrases。

 It's like the computer playing a guessing game considering all the possible words that could complete your search。

 this makes into account the context and the intent represented in the encoding means in simpler terms the decoder is making educated guesses about what words or phrases might complete your search query。

 It's like the final touch of magic to ensure your search engine knows exactly what you are looking for。

 That's what decoder prediction。 Then the next one。😊。



![](img/5a080daf1727e13695ff5e3a765ed7ab_36.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_37.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_38.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_39.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_40.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_41.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_42.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_43.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_44.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_45.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_46.png)

Is advanced technical completion generation so now instead of just settling for one completion its simultaneously explore let's explore multiple potential completions it's like having a multiple search parties looking for the treasure but only the best one will make it back now the cool part is that here the search selects the most promising options。

😊。

![](img/5a080daf1727e13695ff5e3a765ed7ab_48.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_49.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_50.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_51.png)

Based on various criteria， it's not about being relevant to your incomplete query。

 It's also about creating a coherrenent and valid search query。

 The computer is like a judge scoring each completion on how well it balances all these factors in simpler terms it's like having a search engine that does not just guess by guess。

 but carefully selects the most likely and sensible options for completing your search。

 It's about finding the switch spot between the relevance coherence and the probability of creating a search query that makes sense。

 So now let's understand the last step that is fine tuning Okay so we have a prediction are advanced techniquess。

 but we are not done at enter into the fine tuning。

 It's like the final polish that transforms good into great。

 This step ensures that our LLMs are perfectly in tune with what you。😊。



![](img/5a080daf1727e13695ff5e3a765ed7ab_53.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_54.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_55.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_56.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_57.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_58.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_59.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_60.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_61.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_62.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_63.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_64.png)

are looking for so to fine tune these elements we use the large data sets filled with search logs and user interactions。

 It's like giving their models a crash course in understanding the unique language and behaviors of the searches the more to see the better they get at predicting what you want fine tuning is about refining the model to align with your unique search behaviors it's like tailoring a suit to fit perfectly making sure the model understands your language shades preferences and the way you interact with the technology as a result。

 fine tuning enhances the accuracy of the prediction and the relevance of the completions it's like having a search engine that truly gets you anticipating your needs even before you finish typing so that's what the fine tuning so in summary so we have traveled through the five steps of our journey in this lesson。



![](img/5a080daf1727e13695ff5e3a765ed7ab_66.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_67.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_68.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_69.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_70.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_71.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_72.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_73.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_74.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_75.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_76.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_77.png)

We have covered the magic of search query completion where AI predicts and completes your search queries enhancing information retrieval system so will delvet into encoding decoding advanced techniques and fine tuning unveiling the seamless synergy of technology and user experience Thank you。

😊。

![](img/5a080daf1727e13695ff5e3a765ed7ab_79.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_80.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_81.png)

![](img/5a080daf1727e13695ff5e3a765ed7ab_82.png)