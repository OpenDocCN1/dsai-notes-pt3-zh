# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p44 15_推断与预测.zh_en -BV1L9Fde5EXS_p44-

Recognizing whether you're asking an inferential question or a prediction question is really important because the type of question that you're asking can greatly influence the modeling strategy that you pursue in any data analysis。

😊。

![](img/094c5bd1c889e98c895cfae0523cb5ad_1.png)

So just to recap with inferential questions， the goal is to estimate the association between an outcome and a key predictor while potentially trying to adjust for all these confounding factors。

 there's usually a very small number or even a single key predictor that we're interested in and its relationship with the outcome and then there may be all these other variables and the key goals for the modeling is to estimate this association and to make sure that you probably adjust for any other kind kind of factors you often do sensitivity analyses to see how the association might change in the presence of other factors but the prediction question the goal is to develop a model that best predicts the outcome using whatever information you have available to you so typically you don't put any a priori weight on one predictor over another and so there's no notion of say a key predictor and a confounder all the predictors might be equally important before you look at the data and any good prediction algorithm will tell you which predictors are which。

are more or less important for predicting the outcome， but beforehand。

 we don't necessarily divide them into different groups based on importance。Finally。

 we usually don't care about the mechanism or the specific details of the relationship between the various predictors or variables。

 we just want to find kind of a form， a model form that predicts the outcome with a high accuracy and low error。

So I wanted to give a brief example of how these different types of questions can lead to different conclusions。

 even on the same data set okay and so I'll start first with having an inferential question。

 So suppose I want to know how is air pollution in New York City related to mortality in New York City so the data I'm going to use comes from this national morbidity mortality and air pollution study and here's a picture of daily mortality in New York from 2001 to 2005 and you can see that it has highly seasonal component the mortality tends to be higher in the winter and lower in the summer and it's a very specific kind of pattern across every year。

Here is what particulate matter data looks like and so for the same time period you can see this has also a seasonal structure to it in particular a particulate matter is high in the summer。

 and tends to be low in the winter in New York City and that's a very that pattern is kind of repeated across the years。



![](img/094c5bd1c889e98c895cfae0523cb5ad_3.png)

So the first step I'm going to do is just to try the easy solution。

 the easy solution is just a scatter plot of mortality and PM10 on the X axis and here you can see what the relationship looks like。

 there's quite a bit of noise because we wouldn't necessarily expect particulate matter to explain all the variability in mortality and so we may need to resort to some modeling。

 some formal modeling to see if there's any sort of association here。



![](img/094c5bd1c889e98c895cfae0523cb5ad_5.png)

So the first thing we're going to do is to take that scatter plot and just fit a simple linear regression to the data in that scatter plot。

 so this is basically regressing mortality as the outcome and PM10 as our key predictor without any other factors。

 just is kind of a baseline model。And here are the results that we get from a regression model of that nature and you can see that the coefficient for PM10 here is 0。

00004， etc cetera， and so basically is close to 0， you can tell by the size of the standard error which is much bigger than the estimate that there's a lot of variability around this estimate and so it's effectively zero so the association between the two variables is0 okay so that's kind of what our basic first cut analysis tells us。

Now one thing we know about pollution and mortality just from the pictures that we just saw of the data is that they're highly seasonal。

 so season plays a big role in explaining variability in both mortality and in air pollution remember mortality was high in the winter and low in the summer and pollution was high in the summer and low in the winter so it seems like season is clearly related to both mortality in pollution so it might be a reasonable thing to include as a potential confounding factor so we can fit a secondary model to the data which includes PM10 as our key predictor and then maybe will include the season of the year as a potential confounding factor so the season will just be there'll be four seasons and we'll have a categorical variable for a category for each season。

So here's the results of fitting that models of the data and you can see that I highlighted the coefficient for PM10 here is actually quite a bit larger now it's 。

00149 and you can see that the standard error is quite a bit smaller relative to the estimate and so this suggests that that the coefficient for PM10 is quite a bit bigger than zero maybe statistically significant so the addition of this confounding vguard factor and dramatically changed the association that we estimate between PM10 and mortality and so part of this is because season is very strongly related to both。

 but it's kind of positive it's correlated in one with mortality but it's correlated in a different way with pollution and so that's part of why we saw when we didn't include season we saw no relationship but when we do include it we see this kind of quite a bit stronger relationship。

Now there are other potential factors that we might want to consider in terms of things that might be both related to mortality and to air pollution。

 so another one is the weather right so weather is associated with mortality and it's also highly associated with various air pollutants and so we can characterize the weather with something like temperature or dew point temperature to think to just capture a piece of kind of what weather is and so we can include that into our models so here's the results of including temperature which is this TmpDD variable and dew point temperature which is this DPTP variable and you can see now actually I've highlighted the coefficient for PM10 is even bigger than it was before and and the standard error is similar so it's actually more statistically significant in some sense than in the previous models again。

 temperature in dew point are strong kind of factors that are related to both mortality and pollution。

Finally another type of factor that may be related to both mortality and PM particulate matter is other pollutants right so there are other pollutants that may affect health and they may be correlated with with particulate matter because they may share common sources so one common source in a city like New York is going to be traffic traffic tends can produce particles and can also produce other pollutants so one of the pollutants that we'll look at as nitrogen dioxide and so nitrogen dioxide tends to be correlated with particles so if you are interested in association between particles and mortality。

 you might want to you might wonder well is what we're seeing actually the association between nitrogen dioxide and mortality and PM10 is kind of getting mixed up in the two and so we can include nitrogen dioxide in our model as a potential confounding factor and see how the estimate for particulate matter changes when we do that。

So here are the results from that model， you can see that compared to the previous model。

 the coefficient for PM10 drops a little bit， it goes down a little bit。

 so the effect weakens a little bit when we include nitrogen dioxide in the model now it's still quite a strong effect relative to the standard error that we estimate。

 but it' not an estimate that is not as strong as it was before we entered we included N02 in the model and so NoO2 and PM10 might be sharing a lot of the same effect on mortality and it may be difficult to completely disentangle them however。

 even with NO2 in the model we still see a reasonably strong association between PM10 and mortality and New York City。



![](img/094c5bd1c889e98c895cfae0523cb5ad_7.png)

So when we put all these results together from the primary model which just had PM10 and mortality and then the various secondary models we've shown。

 you can see that the primary model had zero association effectively and then the other three models had quite a relatively strong positive association with the outcome and here I've plotted the 95% confidence intervals for each of these associations so this is the kind of analysis that we're interested in we're looking at PM10 is our key predictor and mortality is are outcome and we want to see how that association changes under different scenarios under different sets of models including different sets of confounding factors now what we do with this information will depend on what the goal the analysis is who the stakeholders are and kind of what we might do with this information afterwards but we want to talk about that now the point I want to make is kind of the analysis that you do for an associational type of analysis is very much along these lines。

So another question that we could ask is what best predicts mortality in New York City using the data that we have available Okay。

 so now I've changed the question to a prediction type of question and we want to know what predicts the outcome best。

So one of the things that we can do is fit a complex prediction algorithm right we don't need know we don't need to worry about estimating associations or adjusting for confounding factors。

 we're just going to put all the data that we have available to us and see how well that predicts the outcome mortality so I'm here I'm going to use a random force algorithm to make predictions of mortality in New York City and one of the aspects of the random forest algorithm is that it allows for a summary statistical called variable importance and this gives you a sense of how important a variable is an increasing the skill of the algorithm in predicting the outcome so I've plotted here the variable importance plot that rank orders all the variables in terms of how important they are to kind improving the prediction skill of the algorithm。

And you can see at the very top here is temperature which is kind of ranked as the most important variable。

 followed by dew point temperature， followed by the date and then N02 ozone。

 which is03 season and then finally PM10 and then DOW which is the day of the week so you can see that from this prediction model。

 particulate matter actually is second from the bottom in terms of improving the prediction skill of the algorithm so if you were to look at this analysis and say and then ask the original question of say you how is PM10 related to mortality。

 you might think， well it's not related to mortality， it's not important for predicting。

But that's true， but it doesn't necessarily mean that PM10 is not not is associated with mortality in from an associational standpoint。

 it may have an important association with mortality but that the association is inherently weak and so it's not necessarily going to be good for predicting the outcome but it may nevertheless have an important association with the outcome and so separating these kinds of questions out and the goals of these questions is very important because if you were to ask an inferential question。

 but then do an analysis that's really tuned for prediction。

 you might be led to come to the wrong conclusion that oh PM10 is not important and it doesn't have an important association with the outcome and particularly if you think about something like pollution。

 it may have an inherently very small association with the outcome but because everyone in New York City ostensibly breeze and is exposed to this polluted error the effect the ultimate effect of such an association could be quite large given the large population of a city like New York so you can't。



![](img/094c5bd1c889e98c895cfae0523cb5ad_9.png)

It's important to not kind of conflate the magnitude of the association with the kind of effect。

 the ultimate effect on the population or that you're interested in。

 so using prediction algorithms for prediction questions and associational analyses for associational questions is really important so that you can draw the right conclusions from your data and not mistake the results of one question for another。

So framing the question correctly is really important for developing an appropriate modeling strategy and for kind of drawing the right conclusions。



![](img/094c5bd1c889e98c895cfae0523cb5ad_11.png)