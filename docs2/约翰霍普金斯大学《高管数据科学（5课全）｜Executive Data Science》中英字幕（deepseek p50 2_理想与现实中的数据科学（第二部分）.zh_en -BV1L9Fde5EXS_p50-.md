# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p50 2_理想与现实中的数据科学（第二部分）.zh_en -BV1L9Fde5EXS_p50-

![](img/7523d0f51829192965d9fe993bf7b4dc_0.png)

Hi， my name is Brian Caho， and this is lecture 1 in week4 of the executiveive data Science series。



![](img/7523d0f51829192965d9fe993bf7b4dc_2.png)

In this lecture， we're going to talk about the perfect data science experience and contrast with what actually happens in real life。



![](img/7523d0f51829192965d9fe993bf7b4dc_4.png)

So in the perfect data science experience， what happens where you have clearly defined hypotheses of interest that you've specified our priori？

Experimental design is at your disposal， so you have a lot of control over what you do prior to collecting data。

 So for example， you might be able to conduct an AB test and do randomization across a treatment of interest。

 or if you have some nuisance variables that you're not interested in。

 you might be able to stratify across those。And randomization isn't enough by itself。

 you actually have a random sample from a population that you're interested in。

 so when you draw your conclusions from your sample。

 you know that they will hopefully be representative to the population that you're really interested in。

The data that you measure is actually able to interrogate the hypotheses that you're interested in。

 that's an important other aspect that we'll talk a little bit more about later。

And then your data creation， creating your database， whatever merging you have to do。

 all of that goes smoothly， there's no missing data， there's no failed entries。

 there's no nonun matches， so all of that goes perfectly。

Analysis is robust without the need for some sort of advanced modeling。

 so you can get by with a simple T test or something like that。 And then your conclusions are clear。

 You gain parsimonious knowledge from the experiment and your decision is obvious given the data。

 So that's the perfect scenario。

![](img/7523d0f51829192965d9fe993bf7b4dc_6.png)

What actually happens？So what typically happens is you don't have strongly specified ari hypothesis and your data is actually needed to inform your hypotheses before you start to interrogate them and usually you're having to use the same data set to come up with the hypothesis as you are to decide between the hypotheses。



![](img/7523d0f51829192965d9fe993bf7b4dc_8.png)

And because of that and because you're often looking at multiple hypotheses。

 multiple comparisons are an issue。Your access to experimental design is often limited。

 or the data is just completely observational， so randomization isn't available or even in a setting that comes up commonly in biostatistics。

 your data is retrospective， so you just look at the outcomes and look backwards to see what covariates they had。

Often the population being studied isn't the population of interest。

 so if you're Google and you happen to be analyzing search data from Yahoo， then that's not ideal。

 but if that's an instance where that's the only data you happen to have。

 then that's the data that you happen to have。Another problem is that you don't have the exact measurements you need to evaluate the hypotheses。

 and that's a very common problem in my experience。The data is problematic。

 you have some issue with merging where you have non unique matches or multiple matches。

 you have data entry errors， you have missing data。

And then because of all these errors and intricacies and the observational nature of the data。

Advanced modeling winds up being required， and because advanced modeling is required。

 advanced computing is needed to fit your advanced models， and because of that。

 there's issues of both computational robustness， how fragile the model is to the assumptions that you've made and so on。

And then your conclusions might be indeterminate， and then your decision space might not be substantially more informed by the data than if you had done nothing at all。



![](img/7523d0f51829192965d9fe993bf7b4dc_10.png)