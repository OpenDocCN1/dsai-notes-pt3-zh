# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p32 3_六种问题类型.zh_en -BV1L9Fde5EXS_p32-

There are six types of questions you can ask in a data analysis。

 and in this lecture we'll talk about each of them and what they mean for interpreting your results。

The six types of questions that you can ask in a data analysis are descriptive， exploratory。

Inferential， predictive， causal and mechanistic。 Now。

 each one of these questions has very different characteristics and imply different ways that you can interpret findings from any data analysis。

 So we're going talk about the characteristics of each of these types of questions and how they can be used or misused in any data analysis。

The first type of question you can ask is a descriptive question Now the fundamental feature of a descriptive question is that you're often looking to summarize a characteristic of a data set。

 so often this involves taking the average or taking the proportion of some feature in your data So for example you might ask how many people visited this website in the last 24 hours or what's the average level of air pollution in the city of Baltimore Si you you're summarizing kind of features of a data and you're focusing on the data that you have on hand and you're not really worried about things that are outside the data yet。

 you really just want to summarize the numbers that you have。😊。

The second type of question you can ask is an exploratory question and the basic goal here is you want to look at trends or relationships between variables in your data and sometimes these are called hypothesis generating types of analysis because you're you're looking at the data you have in hand and looking for relationships that might be of interest again like a descriptive question。

 typically with an exploratory question， you're not interested in things that are outside the data。

 but rather in summarizing and characterizing relationships within a dataset。😊。

The third type of data analysis question is an inferential question and an inferential question can often be the result of lots of exploratory and descriptive types of analyses and the fundamental property of an inferential question is that you want to make a statement about something outside the data and so you often for example。

 you want to know whether a relationship that you observe in the data holds somewhere else。

 either in another data or in a different population of kind of data points and so the key to an inferential question is that you want to make a statement about something that you don't observe and so this is a much more difficult type of question because now you're concerned about things that are outside the data so you have to be careful about what types of methods and what types of approaches you use there。

😊，The fourth type of question in a data analysis is a predictive question Now with a predictive question。

 you want to know whether you can take a set of features and use them to predict another feature on a given person or in a given unit of analysis right So this is at a large scale about essentially looking at correlations between lots of features in a data set Now often with predictive types of questions。

 they lead you to solutions that don't necessarily tell you how things work or explain the mechanism of what's going on inside any given system because the goal is to really produce a very good prediction of a given feature。

 given a set of other features and the goal is not really to explain how things are working Now on occasion。

 a predictive question can lead you to an explanation about what's going on。

 but the key point there is that it's not the ultimate goal。😊。



![](img/91e156e525e9e9711614f0592489b96a_1.png)

Yeah。The fifth type of question that we're interested in is a causal question Now with a causal question we're often looking to determine how average changes in a set of features or in a given feature will change when we modify another feature and so if we take a variable and deliberately make changes to it on average what how will another feature or another characteristic be affected these types of questions can often be directly addressed via experiments such as randomized controlled trials or directly control the kind of laboratory experiments however in many other situations causal questions can really only be answered indirectly using observational data so in situations where we can't control what the settings are or what the experiment or design a specific experiment to kind to collect data directly on this question and so there in situations like that we need to accumulate evidence through many different types of studies。

😊，And to develop a pattern that would suggest that a causal relationship exists。

The six type of question that we are interested in is a mechanistic type of question and the goal here is essentially to uncover a deterministic link between a set two sets of features okay and so we want to know if we if we change one measurement on one hand。

 can we does it always result in a specific outcome on a different measurement okay now this type of relationship is often very difficult to identify outside of highly controlled environments。

 for example， in engineering processes so we're often not we're not often going to be looking at mechanistic types of questions。

 but it is an important area to think about。Now why are we talking about these six types of questions The reason is because knowing what type of question you're asking is really important to interpreting the results of a data analysis。

 it's often very common to mistake one type of question for another and that will often result in problems in your interpretation and on improperly waiting the evidence from one kind of analysis versus another kind of analysis in fact it's so common to mistake one type of question for another that we actually have little nicknames for when this type of mistake occurs。

For example， we often think we're asking a causal question。

 but the way that we've done the analysis or collected the data is really results in us asking an inferential question and that is the class correlation does not imply causation type of problem another good example is when we think we're doing an inial we're asking an inferential type of question but in reality we're doing something more exploratory and so that's sometimes called data dredging Another mistake that's commonly made is when were trying we think we're trying to do prediction but that we build our prediction models inroperly and so it ends up being more of an exploratory type of analysis and that's sometimes called overfitting the data and lastly we sometimes think that we're doing an inferential type of analysis but it's really more descriptive particularly if you very small sample sizes so that's sometimes called an n of one analysis so make sure you know what type of question you're asking and interpret your data analysis appropriately。



![](img/91e156e525e9e9711614f0592489b96a_3.png)