# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p45 16_解释你的结果.zh_en -BV1L9Fde5EXS_p45-

This lecture is about interpreting your results because data analysis is an iterative process。

 interpretation is actually something that happens continuously throughout the whole process。

 but because it's so important， it deserves a separate discussion。



![](img/b90f8566deea870ff201c84e77d7f237_1.png)

Interpretation in a data analysis is a continuous part of the entire data analysis process。

 and just like with other aspects of data analysis。

 everything you do is based on setting expectations and kind of matching matching the data that you collect or the information that you collect to those expectations Now the expectations for your interpretation will be based on things like exploratory data analysis and formal modeling。

Now when the interpretation does not match your expectations you're going to have to figure out whether it's because your expectations were incorrect or because your interpretation is incorrect and so figuring that out as part of the iterative nature of interpretation。

 and even though this is one of the last steps of any data analysis。

 you may need to go back to the exploratory data analysis or the formal modeling stages if the things that you've discovered in your interpretation challenge what you found previously。

So there are a couple of basic principles to keep in mind when interpreting results。

 particularly in the later stages of a data analysis the first thing you're probably going to want to do is to revisit your question and just to kind of make sure that you haven't gone off course from your original question the second thing you want to think about is your primary result so typically in a formal model and you'll have primary model and maybe some secondary models particularly in an inferential or causal type of question and so the primary results will be kind of initially what you focus on it may not be the last thing that you focus on but it'll be what you initially focus on and there are three things that you want to think about with your primary result that's the directionality the magnitude and the uncertainty and we'll talk more about this in a second but those are the kind of the three properties of any result that you're going to want to think about then there's the context the context is important because it really takes into account the totality of the evidence that you've developed through both primary and secondary models okay and when you look at the kind of。

ality of the evidence you want to look separately at the direction。

 magnitude uncertainty of all the different models that you fit and of course you want to join this with everything that's already known about the question you're asking。

 read it from literature or from other colleagues in your organization。😊。

The last thing you want to think about is the implications because so you want to consider the implications of your analysis and how they might determine what actions to take and so and it should be any actions that might be taken that are a result of the answer to your question。

 so the implications is kind of the last step of interpretation。

So revisiting the question is really important because often in a long and complicated data analysis。

 it's easy to go off course or kind of go off on a tangent while you're looking at interesting things of your data and this can happen either in the exploratory data analysis process or in the formal modeling phase and so it's important to kind of either get back on to track with your original question or if you divertted onto a different or perhaps more interesting question to recognize that fact that you're looking at something different so you may pursue other important findings that's okay but it's important to just realize what question you're actually asking so because if your formal modeling ends up answering a different question and perhaps and the modeling approach doesn't exactly match what the question was than you might have a problem with interpretation later on so revisiting the question is really important for just setting your expectations for what you will find in your results。

It's also useful to kind of remind yourself of what type of question you were trying to ask。

 whether it was descriptive， exploratory， inferential， predictive， causal or mechanistic。

 just to remind yourself of what of the kind of nature of the question and to make sure that the analysis that you did matched the question that you were asking so most of what I'm going to talk about in this lecture really pertains to inferential or kind of causal questions where the interpretation can be kind of very challenging。

😊，So the other thing you want to think about as you reconsider your question is to check for potential bias in your results so given a certain type of question you will have a population that the question applies to。

 you'll have a sampling process that you should be able to describe as part of your kind of data analysis process and it's useful to think about whether or not that sampling process accurately represents the population or whether there may be some bias in terms of who you select it into your data set and who exactly they represent。

So once you've got your primary model， this is based on exploratory data analysis and kind of formal modeling。

 you're going to have a primary result and the three things that you want to think about are the directionality of the result。

 the magnitude and the uncertainty So directionality really pertains to think to inferential and causal types of questions where you're trying to estimate some association and the association can either be positive negative or zero now so positive or negative is really is what we're talking about when we talking about directionality and that's a very easy thing to check if you were expecting a positive association then you can see whether the result is positive and likewise if you were expecting something negative you can see whether the result was negative So that quick check on directionality is useful kind of quick check for see whether your results kind of match your expectations the next thing what you' settled the directionality issue is the magnitude so the magnitude is really the size of the association or the size of the effect that you estimate and the question you want to ask is does does that magnitude make sense is it。

Meaningful to you and and you know what would be the impact on the population of having an effect of this side or if of the association was of this size。

 so who would be affected is an important question when you kind of think about the magnitude and whether it's meaningful to you or not。

The last thing of course you want to think about is the uncertainty and at this phase it's important that you focus on continuous measures of uncertainty and not kind of binary measures of yes no or statistical significance or not。

 things like confidence intervals and other measures that can give you a sense of the range of possibilities and kind of the magnitude of the uncertainty in your estimate are useful at this phase before you start making decisions about know what to do or what not to do so the directionality。

 magnitude and uncertainty are the key things to look at when you've got your primary model results。

😊，Now in addition to primary model results you'll have a lot of secondary model。

 sensitivity analyses， other things that you tried and this will kind of make up the totality of the evidence for your analysis and so you're going to want to think about each of these primary and secondary models in the context of the three factors that we just talked about which are directionality magnitude and uncertainty kind of roughly in that order so when you look across all of the evidence that you generated does how is the directionality preserved or not。

 how is the magnitude of the effect or the association preserved or not and how does the uncertainty about your estimate preserved or not how does those change from from model to model if the directionality changes then that may call into question whether you've got a reasonable modeling strategy or if even that's such an association actually exists in the population if the magnitude changes maybe that they indicate you've got a potential confounding going on or maybe you've got to think about what type of model is the best model for this type of estimate。

this type of association and similarly， if the uncertainty kind of blows up between when you add certain factors into your model。

 then that will indicate to you that maybe you don't have a very good estimate of an association or an effect in the population so and finally。

 of course， included with the totality of the evidence is the kind of any results that may already be existing that people have research before people either in the literature or in your organization that people already know about and you want to know how your results along with kind of the evidence that you've generated are consistent or not with existing results。

Finally is important to think about the implications of your analysis so many analyses are done to ultimately inform a decision and and any kind of positive findings that you find that match expectations may require some follow up before an ultimate decision is made so sometimes with inferential questions where you're just looking for an association if the association is of interest that may evolve into kind of asking a more causal question where you may need to design a different kind of study and maybe an intervention or a controlled trial so that may be the decision that results from your analysis but the ultimate decision and how much evidence is needed to inform that decision will depend on the stakeholders of the analysis so who ask for the analysis who is being informed by it and kind of what their cost benefits and what their kind of values are and so different groups of people will interpret evidence differently not because of they're interpreting it incorrectly。

 but rather their decision。

![](img/b90f8566deea870ff201c84e77d7f237_3.png)

To act on evidence will be based on a variety of factors that are really outside the data set and are not really part of the analysis so it's important to always keep in mind the ultimate goal of the analysis。

 the decision that might need to be made and the stakeholders who are involved in making those decisions and what kinds of factors they need to consider。

So just to summarize when it comes to interpreting results， you want to always revisit the question。

 make sure you know what question you're asking and what type of question it is so that you can figure out whether the analysis match the question。

 think about your primary result and for that result you want to consider the direction。

 the magnitude and the uncertainty there's going be many results that you generate so you want to think about the totality of the evidence so this is the context that we're talking about and for each of the kind of results that you generate you similarly want to think about the direction。

 magnitude and uncertainty of those results and you want to combine this evidence that you generate with existing knowledge Finally the implications of analysis are always important to consider and you want to think about how the evidence that you generate will inform the next steps or any decisions that might be made afterwards。



![](img/b90f8566deea870ff201c84e77d7f237_5.png)