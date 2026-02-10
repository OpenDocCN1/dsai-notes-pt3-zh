# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P33：32_模型选择第3部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_0.png)

So up to this point， all that we've talked about is the impact of。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_2.png)

Unnecessary or necessary included variables on our regression coefficients。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_4.png)

But there's one other parameter that we estimate in a regression model。

 the residual variance sigma squared。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_6.png)

So what happens？

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_8.png)

If we have assuming IID errors that our linear model is additive that that part of the model is correct。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_10.png)

Then we can mathematically describe the impact of omitting unnecessary variables or including unnecessary variables。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_12.png)

And it follows along the same lines as what we discussed before， if we underfi the model。

 in other words we omit important variables， then the variance estimate is biased。

 why is that because we've attributed to variation things that are actually systematically explained by these covariates that we've omitted。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_14.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_15.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_16.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_17.png)

On the other hand， if we either correctly fit the model， we include all the right。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_19.png)

Terms or if we overfit the model。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_21.png)

Then the variance estimate is unbiased， however。The variance of the variance estimate gets inflated if we include unnecessary variables。

 so it's actually kind of the same rule if we om as we discussed before with coefficients。

 if we omit variables。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_23.png)

Then we get bias， if we include variables， then we get a less reliable estimate。

 so it's roughly the same impact going on。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_25.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_26.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_27.png)

So let's talk about model selection in general， automated model selection。

 and I just want to briefly mention again that automated model selection is something that we cover in the machine learning class。

 and really， I think at one point it was a statistical topic but it's really moved into the realm of machine learning for the most part。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_29.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_30.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_31.png)

And I would say， though， even for relatively simple linear regression models。

 the space of model terms that you have to search among explodes really quickly when you start including interactions and polynomial terms like the square of a regressiongressor and so on。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_33.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_34.png)

If you have a lot of lot of regressors and you're interested in how do I reduce this space。

 then there's a lot of factor analytic and things like principal components。

 those kinds of techniques that are available to you to reduce your covariate space down to side now however those come with consequences your principal components or factors that you obtain might be less interpretable than the original data that you're interested in again。

 again， this is probably a better served in a multivariable class。

 a multivariate class or a class on machine learning。

 but for us we're going to mostly consider the case where we have a relatively small number of regressors and we're going to pick through them with highly interactive process between the analyst。

 the data and the scientific context。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_36.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_37.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_38.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_39.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_40.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_41.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_42.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_43.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_44.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_45.png)

Another thing I would mention is that good design can often eliminate the need for a lot of this model discussion。

 we've talked a lot about how randomization can really prevent a lot of the。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_47.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_48.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_49.png)

Problems that we're talking about with making our variable of interest unrelated to nuisance variables that we're not interested in or nuisance variables that we don't even know about。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_51.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_52.png)

However， there's other aspects of design that can serve the same purpose， for example。

 if we stratify and randomize within strata， the classic example of this when this was developed was artificial is working in field crop experiments and they needed let's say you're trying a different kind of seed you might block on different you block on different areas of the field that you' were going to plant in and randomize the different seeds to those areas。

 so you might have two different kinds of seeds but they will have been distributed in a systematic way that is fair across the field but also then within that design there will also be some randomization this topic of experimental design is a pretty broad topic another great example is in biostatistics the field that I work in the most a very common kind of design is a crossover design。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_54.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_55.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_56.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_57.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_58.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_59.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_60.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_61.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_62.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_63.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_64.png)

And in that case， you try to use every subject as their own control， so let's say for example。

 you're interested in looking at an as two different kinds of aspirin。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_66.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_67.png)

And you might give the aspirin to one group of people and then the aspirin to another group of people。

 the other aspirin to a different group of people。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_69.png)

Let's say they have different gels or whatever that determine how it gets absorbed in your stomach。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_71.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_72.png)

So。If those two groups aren't the same either。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_74.png)

The randomization wasn't very good and there was some sort of imbalance that you just got unlucky about。

 or if the study was just observational。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_76.png)

Then the comparison of those two groups might be biased by whatever differentiates the groups rather than group one receiving one kind of aspirin and group two receiving different kind of aspirin。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_78.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_79.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_80.png)

On the other hand， if you can give a person one kind of aspirin and then later on give them a different kind of aspirin when they have another headache that would compare each person to themselves right control block on the person so to speak so that's a design strategy now there's some nuance with this design strategy as well。

 what happens if there's some residual effect of the first aspirin when you give the second one right so maybe you could handle that with some sort of washout period a long washout period or something like that。

 but anyway the point of that design is to make it so that you're comparing people with themselves to control and everything that's intrinsic to the person。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_82.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_83.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_84.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_85.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_86.png)

At least across time periods control for that by giving both aspirants to each person maybe you would randomize the order in which they receive them that's called a crossover design at any rate the broader point that I'm trying to make is it's often the case that good thoughtful experimental design can really eliminate the need for some of the main considerations that you'd have to go through in model building if you were to just collect data in an observational fashion。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_88.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_89.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_90.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_91.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_92.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_93.png)

The last thing I would say is there's one automated model search technique that I like quite a bit and I find it very useful and it's the idea of looking at nested models。

 so I'm often interested in a particular variable。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_95.png)

And I'm very interested in how the other variables that I've collected will impact it。

 so I'm interested in a treatment or something like that， some important variable。

 but I'm worried that my treatment groups are imbalanced or with respect to potentially some of these other variables so I might look what I'd like to look at is the model that just includes the treatment by itself then the model that includes the treatment and let's say age。

 if the ages weren't really balanced between the two treatment groups and then one that looks at age and gender。

 if maybe the genders between the two groups weren't really balanced and then so on。

 and this idea of creating models that are nested， every successive model contains all the terms of the previous model leads to a very easy way of testing each successive model okay and these nested model examples are very easy to do。

 so I'm just going to show you some code right here。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_97.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_98.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_99.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_100.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_101.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_102.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_103.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_104.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_105.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_106.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_107.png)

On how you do nested model testing in R so I fit three linear models to our Swiss data set the first one just includes agriculture。

 let's pretend that that's the variable that we're interested in okay and then the next one includes agriculture and examination in education I put both those in because I'm thinking they're kind of measuring the same thing but now after this lecture I'm concerned over the possibility that they're too much so measuring the same thing but let's put that aside for this time being and then the third model includes examination education plus cat plus infant mortality so all the terms so now I have three nested models and I'm interested in seeing what happens to my effect as I go through those three models。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_109.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_110.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_111.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_112.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_113.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_114.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_115.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_116.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_117.png)

The point being in this case you can test。

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_119.png)

Whether or not the inclusion of the additional set of extra terms is necessary with the I No function。

 so I do AO fit one fit3 and fit5 okay that's what I name them 135 and then you see down here what you get is listing of the models Model1 Model2 Model3 and then it gives you the degrees of freedom okay that's the number of data points minus the number of parameters that had to fit the。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_121.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_122.png)

![](img/443ef12ddaca7b7d4661a06bab6aa2bc_123.png)

Sums of squares， the residual sums of squares， and then the excess degrees of freedom of going DF is the excess degrees of freedom of going from。

Model1 to model 2 and then Model2 to Model3 so we added two parameters and going from model1 to Model2 that's why that Df is2 and then we added two additional parameters going from model2 to Model3 so the two parameters we added from going from model1 Model1 to model2 is we added examination and education there two regression coefficients going from model2 to model3 we added cat and infant mortality。

 there two regression coefficients okay so with this residual sum of squares and the degrees of freedom you can calculate so-called f statistic and that's get a P value this gives you the s statistic and the P value associated with each of them and then here it shows that yes the inclusion of education examination appears to be necessary over just looking at agriculture by itself and then when I look at the next one it says yes the inclusion of Catholic and infant mortality appears to be necessary beyond。

Just including examination， education and agriculture。Okay。

 so if the way in which you're interested in looking at your data naturally falls into a nested model search as it often does。

 I think when you're interested in one variable in specific。

 as in this case I think this would be a pretty natural way of thinking about the series of analyses。

 then some kind of nested model search is a reasonable thing to do。

 it doesn't work if the models that you're looking at aren't nested。For example。

 if I had the first model or model two had examination but not education and a third model had education but not examination this wouldn't necessarily this wouldn't apply you'd have to do something else and there I think you get into the harder world of automated model selection with things like information criteria so I would put all that stuff off to our prediction class and then just leave you this one technique that's useful in the one specific instance where you've decided to kind of。

Look along a series of models each getting increasingly more and complicated。

 but including the previous one。Okay， so I hope in this lecture that you've gotten a couple of model selection techniques that you can use。

 I hope you've also learned that there's some basic consequences that occur if you include variables that you shouldn't have or exclude variables that you should have。

 these has consequences to your coefficients that you're interested in they have consequences to your residual variance estimate。

 we didn't even touch on some other aspects of poor model that can occur such as absence of linearity and other things like that non-normalality and so on。

So again， it's generally necessary to take your model fits with a grain of salt because more than likely one aspect of your model is wrong。

And I'll leave you then with this famous quote by George Box， who's very famously said。

All models are wrong， some models are useful， and I think that's a very good credo to go along with that。

 yes， for sure your model is wrong， but it might be useful in the sense of being a lens to teach you something useful and true about your data set。

Okay， so that ends today's lecture and I look forward to seeing you for the next one。



![](img/443ef12ddaca7b7d4661a06bab6aa2bc_125.png)