# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p41 12_一般框架.zh_en -BV1L9Fde5EXS_p41-

Formal modeling is the process of precisely specifying statistical models for your data and for providing a rigorous framework for challenging and testing those models。



![](img/b9bee1b293b179f9160d05232c6e098e_1.png)

![](img/b9bee1b293b179f9160d05232c6e098e_2.png)

So at this point， you've done a lot of exploratory data analysis and you probably have a reasonable sketch of the solution that you're looking for for your question。

 but you may not be so sure about whether that solution will hold up to kind of challenges or will be sensitive to various change to little changes either in the data or the model and so formal modeling is is the process of of specifying your model very precisely so that you know what you're trying to estimate and you know how you can challenge your findings in a rigorous framework and so usually the way that we write down these models is with mathematical notation or with computer code so we can get very specific about what we're trying to do and's often difficult to achieve that kind of precision using just words alone to describe a model so that's why we usually have to resort to mathematics or computer code。

Now when we talk about formal models very often we'll talk about parameters and parameters play an important role in statistical modeling parameters usually represent characteristics of the population they might describe relationships between variables or certain features like means or standard deviations and because they are characteristics of the population they are generally considered to be unknown and so we try we have to estimate them from the data and often the goal of an analysis is to estimate given types of parameters and the nice thing about formal modeling is that allows you to specify which types of parameters you're interested in and are trying to estimate so for example in a linear regression the coefficients of the linear regression models are parameters and very often your goal is to estimate them so the general framework for doing formal modeling is very similar to what we've been talking about all along in this course the three basic steps are setting expectations collecting information and then revising those expectations based on what you see so for setting expectations。



![](img/b9bee1b293b179f9160d05232c6e098e_4.png)

ically you want to have a primary model which is your best sense of kind of what the solution should be and what is the answer to your question This is the leading candidate based on all the current information that you have and based on any kind of exploratory data analysis that you've done Now it's not necessarily going to be the final model it's just the model that you start with to kind of structure your formal analysis you may update it later based on any information that you collect and and you may change your primary model to be something different so that's okay and so you don't have you don't have to worry too much about kind what your primary model is going to be from the get- go just pick one that seems reasonable from the data and provides a kind of sensible solution and then you'll be testing it in various different ways to see how it's going to work。



![](img/b9bee1b293b179f9160d05232c6e098e_6.png)

![](img/b9bee1b293b179f9160d05232c6e098e_7.png)

So the next stage is collecting information So given that you have a primary model。

 you want to develop a series of what I call secondary models to test and challenge your solution。

 So the basic idea of a secondary model is that it's slightly different from your primary model it may add variables。

 it may subtract variables and you may add different functional forms so it looks kind of like your primary model but it has various variations to it those are all the secondary model that you want to look at and the goal is to generate evidence against your primary model so if you can generate evidence that suggests that your primary model is incorrect then you can kind of update your thinking and try to come up with a different primary model。

Another word for this is sensitivity analysis so you want to think about how sensitive your primary model is to various changes that are introduced via the secondary models so we'll talk a little bit more specifically about what this means when we talk about our examples the last step of course is revising your expectations and so if the secondary models are largely consistent with your primary model and exactly what consistent means depends on the context and your application and the question that you're asking then that's great and then you can either move on to the next phase or maybe you're finished and you can just kind of report your results however。

 if your secondary model successfully challenge your primary model and maybe put some of your initial conclusions in doubt then you may need to adjust or modify the primary model to better reflect all this additional evidence that you've generated via all the secondary models and then you can start the process again with the new primary model and then perhaps a new set of secondary models to challenge that primary model and。



![](img/b9bee1b293b179f9160d05232c6e098e_9.png)

![](img/b9bee1b293b179f9160d05232c6e098e_10.png)

And then you can iterate through this process until you arrive at a model that you think reasonably summarizes your data and answers the questions that you were looking to ask。



![](img/b9bee1b293b179f9160d05232c6e098e_12.png)

So there's two basic types of situations in which we often use formal modeling and I'm going to categorize them into what I call associational analyses and prediction analysis so associational analyses there the aim is to look at the association between two or maybe more features well in the presence of many other potentially confounding factors okay and so for the most part we're interested in looking at the association between two things but there may be other things that we have to adjust for or account for and that we want to make sure that we're accounting for properly so there's three classes of variables in an associational type of analysis the first is the outcome so the outcome is the factor or the feature that we think varies along with what I call a key predictor now actually it may not actually respond to the key predictor and in a causal sense but the idea is that when the key predictor changes the outcome changes along with it。



![](img/b9bee1b293b179f9160d05232c6e098e_14.png)

It's causal or not okay so the next class of variable is is what I call the key predictor and this is usually the predictor of interest that we want to know how does it vary。

 how does the outcome vary with the key predictor there may be one or two or even three key predictors that you're primarily interested in but usually the number will be small and very often the number is actually just one and so the key predictor explain some variation in the outcome and it's something that you're interested in the last set is a very large class of variables and it's all the potential confounders so these are things that tend to be they're associated with your key predictor and they're also associated with their outcome and they generally serve to kind of confuse the association between your key predictor and your outcome so these are things that often maybe may need to be accounted for in some way or included in a formal model to properly examine the relationship between your key predictor and your outcome。



![](img/b9bee1b293b179f9160d05232c6e098e_16.png)

The next set of analyses that you might do is a prediction analysis so a prediction analysis differs from an associational type of analysis because the goal here is to really to use all available information to predict an outcome so you usually don't care about the mechanism or how things work when you're trying when you're trying to do a prediction analysis so you don't necessarily care about how to explaining how a variable can predict a given outcome you just want to be able to generate a good prediction from a set of variables and you're not developing some detailed understanding of the relationships between all the features now for most prediction analysis there really isn't a distinction between the key predictor and a bunch of other potential confounders usually all predictors are considered equally and because they may contribute information to predicting the outcome and before we do the analysis we may not weight them any differently we may weight them all equally because we don't have any a priori information about what might be more or less important now any good prediction algorithm。



![](img/b9bee1b293b179f9160d05232c6e098e_18.png)

Help you to determine which variables are useful for predicting the outcome and which aren't。

 and so they will help you sort that out。Another feature of prediction analyses is that usually the model that you use cannot be written down in a convenient mathematical notation。

 often the only way that the procedure can be specified is through through computer code or through some algorithm and so often there's no parameters of interest so you're not trying to estimate any parameters you're just trying to make a prediction using any combination of features and using any functional form in any type of model and so that's kind of a hall prediction analyses and finally most prediction analyses often are what you might call classification problems。

 so the outcome really is something that takes two different values and you're trying to predict one of those two different values。



![](img/b9bee1b293b179f9160d05232c6e098e_20.png)

So that's the kind of summary of what formal modeling is useful in what context it may be used。

 whether it's associational or prediction types of analyses。

 in the next lectures I'll give examples of associational and prediction analyses and how the formal modeling framework can be used to work through these different kinds of analyses。



![](img/b9bee1b293b179f9160d05232c6e098e_22.png)

![](img/b9bee1b293b179f9160d05232c6e098e_23.png)