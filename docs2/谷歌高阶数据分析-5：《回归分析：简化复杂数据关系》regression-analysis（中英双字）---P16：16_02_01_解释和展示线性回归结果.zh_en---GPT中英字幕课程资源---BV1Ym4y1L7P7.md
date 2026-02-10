# 谷歌高阶数据分析 5：《回归分析：简化复杂数据关系》regression-analysis（中英双字） - P16：16_02_01_解释和展示线性回归结果.zh_en - GPT中英字幕课程资源 - BV1Ym4y1L7P7

![](img/f84eab22ffd4db5bd1b428a409455264_0.png)

Earlier in the course， you built a regression model that passed all four of the assumptions for simple。

 linear regression。 residualual plots confirmed a linear relationship。

 and you were able to successfully evaluate the performance of the model using a few common metrics。

 Next， it's on the execute phase of the pace framework。 How exciting。😊。

This is the point of the pace framework when your ability to communicate is crucial together we're going to review interpreting the results of our regression model。

 exploring ways in which those insights can be translated into formal visualizations and communicating a meaningful narrative with stakeholders。

In one of my previous positions， I was brought on to help a newly launched mobile phone service provider reduce the amount of fraudulent orders they were receiving。

 After building out a model， it was time to present the model。

 insights and recommendations to my stakeholders。😊，These folks were non technical business partners。

 so I knew that data specific terminology wouldn't interest them。As a matter of fact。

 it would be too technical and they would probably lose interest very quickly。

 which would cause lack of buy in。What was important to my business partners was stopping fraudulent orders。

 So telling the story in a way where I succinctly articulated how many fraudulent orders the model would detect and how that translated to the bottom line。

 resulted in the model being implemented immediately。

 I remember feeling so accomplished in that moment。

 because after all the hard work of building the model， I was able to get the model into production。

 Once the model was in production， fraudulent orders dropped drastically。😊。

Telling the right story to the right people takes time and practice。

 This is a skill that we'll continue to work on throughout our careers。

 It's super important to know your audience and tailor your delivery and story in order to have the most impact。

😊，Enough about me。 Let's return to the example that we've been exploring where you were working at a local zoo。

 You were trying to understand the relationship between penguin structural measurements and their body mass。

In the regression model you created， you observed a positive correlation between bill length and body mass of a group of penguins。

Let's use the results of that model to translate the statistical findings for stakeholders regression model interpretation depends on coefficients and P values coefficients will determine how changes in the independent variable are associated with changes in the dependent variable。

P values demonstrate whether coefficients are statistically significant。

Recall that the slope is used to determine the amount you expect y to increase or decrease per one unit increase of x。

Let's go through the numbers yielded in the O L S summary table to gain a better understanding。

 Bo mass equals intercept plus slope times Bill length。 The slope is positive，141。19。

 and the intercept is negative 1707。29。Next， let's review the P value The coefficient for bill length has a P value of 0。

000。 this P value tests the null hypothesis that the coefficient is0。If we observe a small P value。

 the null hypothesis is likely false。So we reject the null hypothesis and conclude that the coefficient is not0。

 meaning that there is a strong relationship between x and Y。

 It's important to understand that the positive correlation between bill length and body mass you've observed does not necessarily reflect causation。

 Remember， causation describes a cause and effect relationship。

 where one variable directly causes the other to change in a particular way。

 The positive correlation between bill size and mass could be the result of a variety of factors。

 So even though we cannot speak to causation， we can still provide valuable insights about the penguins。

Based on our regressiongress analysis， we can say that for penguins with1 millm more in billing。

 their body masses 141。19 gm more。These results are statistically significant with a P value of 0。

000， a confidence interval of 131。79 to 150。59， and in R squared of 0。

77 by providing measures of uncertainty around our estimates we're responsibly reporting our results based on the interpretation of the numbers you can contribute to the zoo community around you。

Each person on the team at untrue zoo brings a variety of experiences and knowledge。

 The input from your colleagues adds richer detail to the story the model tells Without the informed perspectives of the other bird caretakers。

 the Avian department would not be able to make a sound argument for an increase in food to maintain an adequate inventory that supports the penguins and other birds at the zoo。

😊，When sharing insights as a data analytics professional。

 you need to make sure that your findings can be quickly understood and correctly interpreted。

Communicating the context of your data is one way you can report it responsibly。 For example。

 if your results only apply to a specific penguin population。

 make it clear that people should be cautious about extrapolating to larger or different groups of penguins。

Data visualizations are excellent ways of making statistics relatable for others。

 use caution when presenting terms like coefficients and P values in your visualizations。

Consider that not everyone will fully grasp the significance of these terms immediately。

There are many useful libraries like Maplloot Lib and Seaborn that can help create visualizations programs like Tableau。

 PowerPoint or Google Slides allow for creation of high quality presentations to help you provide context that's relevant to the business problem。

 regardless of your visualization tool of choice， communicating with those around you is critical to your success at all points of the pace process。



![](img/f84eab22ffd4db5bd1b428a409455264_2.png)

As a data analytics professional， clear communication allows you and your work to have impact throughout your team and organization。

