# 约翰霍普金斯大学《数据科学R语言基础｜Data Science： Foundations using R》中英字幕（deepseek - P16：15_数据科学问题的类型.zh_en - GPT中英字幕课程资源 - BV1tsFQemEts

In this lesson， we're going to be a little more conceptual and look at some of the types of analyses data scientists employ to answer questions in data science。



![](img/691202e86966f8c706f10ee111976c4f_1.png)

There are broadly speaking six categories in which data analyzes fall in the approximate order of difficulty。

 they are descriptive， exploratory， inferential， predictive， causal。

 and mechanistic let's explore the goals of each of these types and look at some examples of each analysis to start。

 let's look at descriptive data analysis the goal of descriptive analysis is to describe or summarize a set of data whenever you get a new data set to examine this is usually the first kind of analysis you will perform descriptive analysis will generate simple summaries about the samples and their measurements you may be familiar with common descriptive statistics including measures of central tendency EG mean median mode or measures of variability EG range standard deviations or variance this type of analysis is aimed at summarizing your sample。

 not for generalizing the results of the analysis to a larger population or trying to make conclusions。



![](img/691202e86966f8c706f10ee111976c4f_3.png)

Of data is separated from making interpretations， generalizations and interpretations require additional statistical steps。

 Some examples of purely descriptive analysis can be seen in censuses Here the government collects a series of measurements on all of the country's citizens which can then be summarized here you are being shown the age distribution in the U。

 stratified by sex The goal of this is just to describe the distribution There is no inferences about what this means or predictions on how the data might trend in the future It is just to show you a summary of the data collected The goal of exploratory analysis is to examine or explore the data and find relationships that weren't previously known Exploratory analysis。

 explore how different measures might be related to each other but do not confirm that relationship is causative You've probably heard the phrase correlation does not imply causation and exploratory analysis lie at the root of this same just because you observe a relationship between two variables during exploratory analysis。



![](img/691202e86966f8c706f10ee111976c4f_5.png)

![](img/691202e86966f8c706f10ee111976c4f_6.png)

It does not mean that one necessarily causes the other because of this。

 Exploratory analysis while useful for discovering new connections should not be the final say in answering a question it can allow you to formulate hypotheses and drive the design of future studies and data collection but exploratory analysis alone should never be used as the final say on why or how data might be related to each other。

 going back to the census example from above rather than just summarizing the data points within a single variable we can look at how to or more variables might be related to each other in this plot。

 we can see the percent of the workforce that is made up of women in various sectors and how that has changed between 2000 and 2016 Exp this data。

 we can see quite a few relationships looking just at the top pro of the data。

 we can see that women make up a vast majority of nurses and that it has slightly decreased in 16 years while these are interesting relationships to note the causes of these relationships is not apparent from this analysis。



![](img/691202e86966f8c706f10ee111976c4f_8.png)

Exploratory analysis can tell us is that a relationship exists not the cause The goal of inferential analysis is to use a relatively small sample of data to infer or say something about the population at large Inferential analysis is commonly the goal of statistical modeling where you have a small amount of information to extrapolate and generalize that information to a larger group Inferential analysis typically involves using the data you have to estimate that value in the population and then give a measure of your uncertainty about your estimate Since you are moving from a small amount of data and trying to generalize to a larger population your ability to accurately infer information about the larger population depends heavily on your sampling scheme if the data you collect is not from a representative sample of the population the generalizations you infer won't be accurate for the population。



![](img/691202e86966f8c706f10ee111976c4f_10.png)

![](img/691202e86966f8c706f10ee111976c4f_11.png)

Unlike in our previous examples， we shouldn't be using census data in inferential analysis。

 a census already collects information on functionally， the entire population。

 there is nobody left to infer to and inferring data from the U。

S census to another country would not be a good idea because the U。

S isn't necessarily representative of another country that we are trying to infer knowledge about Instead。

 a better example of inferential analysis is a study in which a subset of the U。

S population was a save for their life expectancy given the level of air pollution they experienced This study uses the data they collected from a sample of the U。

S population to infer how air pollution might be impacting life expectancy in the entire US。S。

 the goal of predictive analysis is to use current data to make predictions about future dataEssential。

 you are using current and historical data to find patterns and predict the likelihood of future outcomes like an inferential analysis。

 your accuracy in predictions is dependent on measuring the right variables If you aren't measuring the right。



![](img/691202e86966f8c706f10ee111976c4f_13.png)

to predict an outcome your predictions aren't going to be accurate。 Additionally。

 there are many ways to build up prediction models with some being better or worse for specific cases。

 but in general， having more data and a simple model generally performs well at predicting future outcomes All this being said。

 much like an exploratory analysis just because one variable may predict another。

 it does not mean that one causes the other。 you are just capitalizing on this observed relationship to predict the second variable。

 a common saying is that prediction is hard， especially about the future。

 there aren't easy ways to gauge how well you are going to predict an event until that event has come to pass so evaluating different approaches or models is a challenge We spend a lot of time trying to predict things。

 the upcoming weather the outcomes of sports events and in the example we'll explore here the outcomes of elections We've previously mentionednateate Silver of 538 where they try and predict the outcomes of U elections and sports matches too。



![](img/691202e86966f8c706f10ee111976c4f_15.png)

Hisstorical polling data and trends and current polling538 builds models to predict the outcomes in the next US presidential vote and has been fairly accurate at doing so538 models accurately predicted the 2008 and 2012 elections and was widely considered an outlier in the 2016 U elections as it was one of the few models to suggest Donald Trump at having a chance of winning the caveat to a lot of the analysis we've looked at so far as that we can only see correlations and can't get at the cause of the relationships we observe causal analysis fills that gap。

 the goal of causal analysis is to see what happens to one variable when we manipulate another variable。

 looking at the cause and effect of the relationship General。

 causal analysis are fairly complicated to do with observed data alone there will always be questions as to whether it is correlation driving your conclusions or that the assumptions underlying your analysis are valid more often。

 causal analysis are applied to the results of randomized studies that were designed to identify causation。



![](img/691202e86966f8c706f10ee111976c4f_17.png)

Casal analysis is often considered the gold standard in data analysis and is seen frequently in scientific studies where scientists are trying to identify the cause of a phenomenon。

 but often getting appropriate data for doing a causal analysis is a challenge one thing to note about causal analysis is that the data is usually analyzed in aggregate and observed relationships are usually average effects。

 so while on average giving a certain population a drug may alleviate the symptoms of a disease。

 this causal relationship may not hold true for every single affected individual as we've said。

 many scientific studies allow for causal analysis。

 randomized control trials for drugs are a prime example of this For example。

 one randomized control trial examined the effects of a new drug on treating infants with spinal muscular atrophy comparing a sample of infants receiving the drug versus a sample receiving a mock control。

 they measure various clinical outcomes and the babies and look at how the drug effects the outcomes。



![](img/691202e86966f8c706f10ee111976c4f_19.png)

![](img/691202e86966f8c706f10ee111976c4f_20.png)

Mechanistic analysis are not nearly as commonly used as the previous analysis。

 the goal of mechanistic analysis is to understand the exact changes in variables that lead to exact changes in other variables。

 these analyses are exceedingly hard to use to infer much。

 except in simple situations or in those that are nicely modeled by deterministic equations。

 given this description， it might be clear to see how mechanistic analyses are most commonly applied to physical or engineering sciences。

 biological sciences， for example， are far too noisy of data sets to use mechanistic analysis； often。

 when these analyses are applied， the only noise in the data is measurement error。

 which can be accounted for。

![](img/691202e86966f8c706f10ee111976c4f_22.png)

You can generally find examples of mechanistic analysis and material science experiments here we have a study on biocomposites。

 essentially making biodegradable plastics that was examining how biocarbon particle size。

 functional polymer type and concentration affected mechanical properties of the resulting plastic they are able to do mechanistic analysis through a careful balance of controlling and manipulating variables with very accurate measures of both those variables and the desired outcome in this lesson we've covered the various types of data analysis。

 their goals， and looked at a few examples of each to demonstrate what each analysis is capable of。

 and importantly， what it is not。

![](img/691202e86966f8c706f10ee111976c4f_24.png)