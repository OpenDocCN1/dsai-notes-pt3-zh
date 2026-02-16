# 杜克大学《本地大语言模型的基础｜Foundations of Local Large Language models》中英字幕 - P6：06_01_05_减轻LLM的风险.zh_en - GPT中英字幕课程资源 - BV19M4m1m72W

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_0.png)

To mitigate and have a good understanding on how to actually mitigate some of the risks of LLMs。

 this graphic is very useful。

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_2.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_3.png)

So let's start here right at the very top with the prompt engineering so prompt engineering is the way we can actually provide an input。

 an accurate input an accurate prompt description of a problem or thing that we want to a machine learning model specializes in language generation so when we are crafting a very good prompt we're going to get well better results now these at the very top represents a very a very easy thing to do so our difficulty right here。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_5.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_6.png)

It's going to be the easiest this is going to be the easiest thing that you're going to do right at this level now as we are going to go ahead that way were going to hit more difficulty and more costs so these is the cost for these prompt engineering is essentially zero and the difficulty well it's very reduced so that means we are only tasked with being able to describe input a good input for the machine learning model on the other side on the quality side right here。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_8.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_9.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_10.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_11.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_12.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_13.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_14.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_15.png)

We are going to get well a lesser quality so we can have like a very good prompt。

 but if the model is not very good at the task at hand。

 so say give you an example if the model you're trying to get accurately responses accurate responses for say for example。

 something that is related to a legal proceeding or some legal problem that you're having in a specific country then this is going to probably not going to help you much if you if the model is not trained or doesn't have any knowledge for that all right so next up we have the retrieval or search or retrieval augmented that we can actually combine this with search and what this means is that。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_17.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_18.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_19.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_20.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_21.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_22.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_23.png)

You can actually do a combination of things where you're doing a search first on something that is coming from the prompt and then combine that as part of your prompt going to the model。

 So this is going to essentially be a little bit more difficult here and it's going to involve more cost So let's just say this is going to be a little bit more costly than just prompt engineering for retrieval augmented guidance or rag or search which is essentially that's what it is What you're doing is you're going to have some sort of storage and some sort of。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_25.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_26.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_27.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_28.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_29.png)

Search that is going search engine is going to allow you to do that and the quality well the quality is going to be improved from that of prompt engineering you can have actual new events。

 for example certain models are trained on events that happen a while ago well you can have retrieval search and mitigate those problems because you can keep updating the search with data that is more relevant and more new essentially moving on we're going to get into fine tuning and fine tuning well it's way more complex you will need tons more data and that requires a continuous。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_31.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_32.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_33.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_34.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_35.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_36.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_37.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_38.png)

A continuous set of processes that will allow you to have data train the model with that extra data and do the fine tuning this is going to be way way more difficult than just retrieval augmented guidance or prompt engineering and of course is going to be more costly for fine tuning to be done quickly you will probably require some GPUus the quality however if you have something that is done very well with fine tuning you will have a little bit more quality Now my preference still is a little bit here within within retrieval augmented guidance and prompt engineering the difficulties with fine tuning and the last one。

 the last piece and I'll put in number four right here which is the train the model well this is training a model from scratch。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_40.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_41.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_42.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_43.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_44.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_45.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_46.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_47.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_48.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_49.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_50.png)

And again， this is what most large language models have to do anyway because they have to produce an actual model。

 and this is going to be the pinnacle of difficulty and the most costly operation that you will see here and the quality。

 well it can， depending on what you want to do might be going higher know better， better quality。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_52.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_53.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_54.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_55.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_56.png)

So understanding how to mitigate some of the risks。

 well here you get like a good understanding of all the different steps that you have and all the different options that you have and what does it mean to compare prompt engineering into training the model from scratch？



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_58.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_59.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_60.png)

And what does that mean to cost and difficulty and of course how it relates to quality so some things might be more problematic for mitigating some risks and you have to use some guardrails anyway these these sections。

 these sections like say for example prompt engineering engineering here。

 that doesn't mean that if you're training a model you can you can be using prompt engineering you 100% can be using prompt engineering as well as fine tune in as well re search。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_62.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_63.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_64.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_65.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_66.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_67.png)

Rtruual augment a guidance or search and put all of these things to good use。

 so the more you have a good understanding with this。

 the more tools and the more things that you can have at your disposal to try to mitigate some of these problems that you might get when you're dealing with large language models。



![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_69.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_70.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_71.png)

![](img/aaa752330f2f6b4c0c736a0c7a2e0bff_72.png)