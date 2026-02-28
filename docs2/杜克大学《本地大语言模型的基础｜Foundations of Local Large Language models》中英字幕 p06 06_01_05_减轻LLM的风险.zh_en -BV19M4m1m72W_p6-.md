# 杜克大学《本地大语言模型的基础｜Foundations of Local Large Language models》中英字幕 p06 06_01_05_减轻LLM的风险.zh_en -BV19M4m1m72W_p6-

![](img/684b122cc05b7e7fec2c76528e5ce0fd_0.png)

To mitigate and have a good understanding on how to actually mitigate some of the risks of LLMs。

 this graphic is very useful。

![](img/684b122cc05b7e7fec2c76528e5ce0fd_2.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_3.png)

So let's start here right at the very top with the prompt engineering so prompt engineering is the way we can actually provide an input an accurate input an accurate prompt description of a problem or the thing that we want to a machine learning model specializes in language generation so when we are crafting a very good prompt we're going to get well better results now these at the very top represents a very a very easy thing to do so our difficulty right here。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_5.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_6.png)

It's going to be the easiest this is going to be the easiest thing that you're going to do right at this level now as we are going to go head that way were going to hit more difficulty and more costs so these is the cost for these prompt engineering is essentially zero and the difficulty well it's very reduced so that means we are only tasked with being able to describe input a good input for the machine learning model on the other side on the quality side right here。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_8.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_9.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_10.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_11.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_12.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_13.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_14.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_15.png)

We are going to get well a lesser quality so we can have like a very good prompt。

 but if the model is not very good at the task at hand。

 so say give you an example if the model you're trying to get accurately responses accurate responses for say for example。

 something that is related to a legal proceeding or some legal problem that you're having in a specific country then this is going to probably not going to help you much if you if the model is not trained or doesn't have any knowledge for that all right so next up we have the retrieval or search or retrieval augmented that we can actually combine this with search and what this means is that。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_17.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_18.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_19.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_20.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_21.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_22.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_23.png)

You can actually do a combination of things where you're doing a search first on something that is coming from the prompt and then combine that as part of your prompt going to the model。

 So this is going to essentially be a little bit more difficult here and it's going to involve more cost So let's just say this is going to be a little bit more costly than just prompt engineering for retrieval augmented guidance or rag or search which is essentially that's what it is What you're doing is you're going to have some sort of storage and some sort of。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_25.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_26.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_27.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_28.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_29.png)

Search that is going search engine is going to allow you to do that and the quality well the quality is going to be improved from that of prompt engineering you can have actual new events。

 for example certain models are trained on events that happen a while ago well you can have retrieval search and mitigate those problems because you can keep updating the search with data that is more relevant and more new essentially moving on we're going to get into fine tuning and fine tuning well it's way more complex you will need tons more data and that requires a continuous。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_31.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_32.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_33.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_34.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_35.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_36.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_37.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_38.png)

A continuous set of processes that will allow you to have data train the model with that extra data and do the fine tuning this is going to be way way more difficult than just retrieval augmented guidance or prompt engineering and of course is going to be more costly for fine tuning to be done quickly you will probably require some GPUs the quality however。

 if you have something that is done very well with fine tuning you will have a little bit more quality now my preference still is a little bit here within within retrieval augmented guidance and prompt engineering the difficulties with fine tuning and the last one。

 the last piece and I'll put number four right here which is the train the model well this is training a model from scratch。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_40.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_41.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_42.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_43.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_44.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_45.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_46.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_47.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_48.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_49.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_50.png)

And again， this is what most large language models have to do anyway because they have to produce an actual model。

 and this is going to be the pinnacle of difficulty and the most costly operation that you will see here and the quality。

 well it can， depending on what you want to do might be going higher you know better， better quality。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_52.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_53.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_54.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_55.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_56.png)

So understanding how to mitigate some of the risks。

 well here you get like a good understanding of all the different steps that you have and all the different options that you have and what does it mean to compare prompt engineering to training the model from scratch？



![](img/684b122cc05b7e7fec2c76528e5ce0fd_58.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_59.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_60.png)

And what does that mean to cost and difficulty and of course how it relates to quality so some things might be more problematic for mitigating some risks and you have to use some guardrails anyway these these sections。

 these sections like say for example prompt engineering engineering here。

 that doesn't mean that if you're training a model you can you can be using prompt engineering you 100% can be using prompt engineering as well as fine tune as well rerie search。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_62.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_63.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_64.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_65.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_66.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_67.png)

Retruual augmented guidance or search and put all these things to good use。

 so the more you have a good understanding with this。

 the more tools and the more things that you can have at your disposal to try to mitigate some of these problems that you might get when you're dealing with large language models。



![](img/684b122cc05b7e7fec2c76528e5ce0fd_69.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_70.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_71.png)

![](img/684b122cc05b7e7fec2c76528e5ce0fd_72.png)