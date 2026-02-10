# 约翰霍普金斯大学数据科学课程7：《回归模型》｜regression-models｜ - P32：31_模型选择第2部分.zh_en - GPT中英字幕课程资源 - BV1Xw411m7We

Okay， so we've talked a little bit about the impact of excluding important regressors right that results in bias and now let's dig down a little bit further in this other phenomenon that if we include unimportant regressors that causes so-called variance inflation。

 so I'm going to show this with a little simulation。Okay。

 so in this case I have a sample of size 100， and I'm going to do  a thousand simulations。

 so let me define those。We get some space down here so。

I'm just we're just looking at this new set of code， okay。

 so I'm going to define those and then I'm going to define three regressors。

 they're all just three independent random normal vectors。

And then what I'm going to do is I'm going to simulate data。

Where the outcome Y only depends on x1 and error， and then doesn't depend on the other two variables。

 And then I'm going to look at the standard error for the x1 variable。

For the model that just includes x1， the model that includes， that's this one。

The model that includes x1 and x2。 That's this one and the model that includes x1 and x3。

 and I'm going to do that over and over again， and I'm going to look at the standard deviation of the simulated estimated coefficients。

 Now the reason I'm doing this by simulation is because the variance inflation occurs on the actual standard errors。

 not the estimated standard errors， it's actually a little complicated in that if I put another variable into a regression model。

 it doesn't necessarily inflate the observed standard error。

 and the reason is because the variance is estimated rather than the actual variance。

 and that has a kind of conflicting property， So you don't necessarily see the variance go up when you include a regressionor in a regression model。

 an unnecessary regressionor into a regression model。

And so you have to look at it through simulation， so let's go ahead and do this。

And this is sort of the ideal setting where the three regressors don't have anything to do with one another。

 Now， what you see is， in fact， so the first model this is the standard error。

 the standard deviation of the beta coefficients I got across all simulations。 Here's the second one。

 It actually went down a little bit for the second one。 Now we know theoretically that can't happen。

 but there's some Monte Carlo error when I do my simulations。

 So let's just say these two are about the same。 And the third one is also about the same0032 as opposed to 0。

031。 So nothing that bad。 the variance inflation by including the extra variables did almost not was was negligible。

 and the reason that is the case is because these other two variables。

 x 2 and x3 have nothing to do with x1。 I simulated them independently。

Let's look at a case now where I've simulated them。In such a way that they depend heavily on X1。

 So I'm going to generate my X1 as。As I did the last time just as a random normal vector。

 but my x2 depends on x1， but also some noise。And my x3 is heavily dependent on x1。

 very dependent on x1， so now let's repeat the simulation。

And see what happens to the variability in the estimated coefficients。

Now we see huge amounts of variance inflation， especially for this third model where we include x2 and x3。

 we see the standard error has gone up by a factor of5 and that goes to the general rule。

If the variable that you include is highly correlated to the thing that you're interested in。

You are going to inflate the variance more。And so you need to concern yourself with putting highly correlated variables into your regression model unnecessarily okay so if I have diastolic blood pressure in my model and I put systolic blood pressure in my model。

 which is basically the same you know relatively the same thing， they're very correlated。

 if I did that unnecessarily that's going to make my diastolic blood pressure standard error。

 it's going to increase it。So yeah， so imagine， for example。

 another example is if you had height in a model and then you also included weight or something like that。

 something that's highly related， height and weight tend to track pretty well with one another and so。

If that was necessary to include， then you just have to bite the bullet and deal with the deviation the extra standard error that you get。

 however， if it's unnecessary， then you don't want to include it。Again。

 the main point is is the more correlated thegressors are to the the covarits are to the regressors that you're interested in。

 the worse off you're going to be in terms of paying a penalty for increased standards deviation。

So that goes to show there's no free lunch， if we omit variables that are important， we get bias。

 if we include variables that are unnecessary， we inflate standard errors。

 especially if we include variables that are unnecessary that are uncorrelated with。

Are variable of interest。 And this， again， reiterates why randomization is so important， right。

 So it randomizes across these other variables the。

The known and unknown knowns that we would otherwise need to include in the model so that we can only include the treatment effect of interest。

And things that we include even if if we feel like we have to。

 they should be relatively balanced or relatively uncorrelated with the treatment effect because it's been randomized and so we won't get this kind of variance inflation that we would get otherwise so again that's why randomization is such an important quality。

OkayNow let's talk about variance inflation factors。We don't know the actual sigmas。

 when we include so we can't actually calculate the exact variance inflation。

 that depends on the actual true residual variance， however， if we can compare ratios of them。

 the sigma would drop out and then we can create things like ratios of variance inflation that accurately represent how much the standard deviation is inflated or not。

So there's a particular。Measure that is very commonly used in regression called the variance inflation factor of VIF。

And all this is is the comparison， this ratio， the variance inflation that occurs from what you actually have。

So looking at the standard error for the data that you have versus the ideal setting where all the other covariates that you were interested in are orthogonal。

To the covarit that you're interested or uncoral， let's just say uncorrelated。 Okay。

 so remember that was the ideal case， right， So if the everything else was uncorrelated to what you're interested in。

 we didn't see much variance inflation。So this looks at the case that you're in versus the ideal case where what you're interested in。

Is uncorrelated with all the other variables， that's a so called variance inflation factor。

And here I give a little simulation。 I'm not going to show it where I just show you that that the ratios can get estimated。

 I show you a little simulation that they can get estimated pretty well。

 So let's actually look with the Swiss data。 Let's look at the variance inflation。

 You So what I'm going to do。Is。Fit the model。Oh。Sorry， this here it is。 I'm going to fit the model。



![](img/849e472ba79624ded97b40e4795fbbf3_1.png)

With all of the variables included so when you do a tilde dot。

 it includes all of the variables and then I'm going to do VIF of fit that gives me my variance inflation factor oh but you have to remember to load this library CrR okay。

 let's load that。

![](img/849e472ba79624ded97b40e4795fbbf3_3.png)

![](img/849e472ba79624ded97b40e4795fbbf3_4.png)

And then now let's try it again， and I would rather than the variance inflation factors。

 I would look at the inflation factors for the standard deviations， which is just the square root。



![](img/849e472ba79624ded97b40e4795fbbf3_6.png)

![](img/849e472ba79624ded97b40e4795fbbf3_7.png)

![](img/849e472ba79624ded97b40e4795fbbf3_8.png)

So let's look down here So on the first line I have the variance inflation factor by itself and then in the line below it I have the square root of it which I tend to prefer So let's look at the first line just because it's the more normal thing the variance inflation so the agriculture one is two what does that mean it means the standard error for the agriculture effect is double of what it would be if it were orthogonal to all the other regressors okay and we see that some of them are quite high examination is quite high 3。

67 so almost four times then the instance when if it were。

Orthgonal to all the other regressors and we know that that education I'm sorry examination and education are highly related。

 so that's why these two have very high variance inflation factors relative to some of the other ones and you can see take a variable like infant mortality right which has a very low variance inflation factor。

 infant mortality is largely going to be unrelated to any of these other variables by and large and so you can see that it doesn't have a large variance inflation factor because it is pretty much unrelated to the other variables anyway。



![](img/849e472ba79624ded97b40e4795fbbf3_10.png)

Okay。So that gets you a little bit of a headway into the world of。

Looking at what happens when you include unnecessary variables and the one of the ways to look at that is so called variance inflation factors and they're incredibly useful little tools and I hope you get a chance to use them。



![](img/849e472ba79624ded97b40e4795fbbf3_12.png)

So up to this point， all that we've talked about is the impact of。



![](img/849e472ba79624ded97b40e4795fbbf3_14.png)

Unnecessary or necessary included variables on our regression coefficients。



![](img/849e472ba79624ded97b40e4795fbbf3_16.png)

But there's one other parameter that we estimate in a regression model。

 the residual variance sigma squared。

![](img/849e472ba79624ded97b40e4795fbbf3_18.png)

So what happens？If we have assuming IID area errors that our linear model is additive that that part of the model is correct。



![](img/849e472ba79624ded97b40e4795fbbf3_20.png)

That we can mathematically describe the impact of omitting unnecessary variables or including unnecessary variables。



![](img/849e472ba79624ded97b40e4795fbbf3_22.png)

![](img/849e472ba79624ded97b40e4795fbbf3_23.png)

And it follows along the same lines as what weve discussed before， if we underfi the model。

 in other words we omit important variables， then the variance estimate is biased。

 why is that because we've attributed to variation things that are actually systematically explained by these covariates that we've omitted。



![](img/849e472ba79624ded97b40e4795fbbf3_25.png)

![](img/849e472ba79624ded97b40e4795fbbf3_26.png)

![](img/849e472ba79624ded97b40e4795fbbf3_27.png)

![](img/849e472ba79624ded97b40e4795fbbf3_28.png)

On the other hand， if we either correctly fit the model， we include all the right。



![](img/849e472ba79624ded97b40e4795fbbf3_30.png)

Terms or if we overfit the model。Then the variance estimate is unbiased， however。



![](img/849e472ba79624ded97b40e4795fbbf3_32.png)

The variance of the variance estimate gets inflated if we include unnecessary variables。

 so it's actually kind of the same rule if we omit as we discussed before with coefficients。

 if we omit variables。

![](img/849e472ba79624ded97b40e4795fbbf3_34.png)

![](img/849e472ba79624ded97b40e4795fbbf3_35.png)

Then we get bias， if we include variables， then we get a less reliable estimate。

 so it's roughly the same impact going on。

![](img/849e472ba79624ded97b40e4795fbbf3_37.png)

![](img/849e472ba79624ded97b40e4795fbbf3_38.png)

So let's talk about model selection in general， automated model selection。

 and I just want to briefly mention again that automated model selection is something that we cover in the machine learning class。

 and really， I think at one point it was a statistical topic but it's really moved into the realm of machine learning for the most part。



![](img/849e472ba79624ded97b40e4795fbbf3_40.png)

![](img/849e472ba79624ded97b40e4795fbbf3_41.png)

![](img/849e472ba79624ded97b40e4795fbbf3_42.png)

![](img/849e472ba79624ded97b40e4795fbbf3_43.png)

And I would say， though， even for relatively simple linear regression models。

 the space of model terms that you have to search among explodes really quickly when you start including interactions and polynomial terms like the square of a regressiongressor and so on。



![](img/849e472ba79624ded97b40e4795fbbf3_45.png)

![](img/849e472ba79624ded97b40e4795fbbf3_46.png)

![](img/849e472ba79624ded97b40e4795fbbf3_47.png)

If you have a lot of lot of regressors and you're interested in how do I reduce this space。

 then there's a lot of factor analytic and things like principal components。

 those kinds of techniques that are available to you to reduce your covariate space down to side Now however those come with consequences your principal components or factors that you obtain might be less interpretable than the original data that you're interested again。

 again this is probably better served in a multivariable class。

 a multivariate class or a class on machine learning。

 but for us we're going to mostly consider the case where we have a relatively small number of regressors and we're going to pick through them with highly interactive process between the analyst。

 the data and the scientific context。

![](img/849e472ba79624ded97b40e4795fbbf3_49.png)

![](img/849e472ba79624ded97b40e4795fbbf3_50.png)

![](img/849e472ba79624ded97b40e4795fbbf3_51.png)

![](img/849e472ba79624ded97b40e4795fbbf3_52.png)

![](img/849e472ba79624ded97b40e4795fbbf3_53.png)

![](img/849e472ba79624ded97b40e4795fbbf3_54.png)

Another thing I would mention is that good design can often eliminate the need for a lot of this model discussion。

 We've talked a lot about how randomization can really prevent a lot of the。



![](img/849e472ba79624ded97b40e4795fbbf3_56.png)

![](img/849e472ba79624ded97b40e4795fbbf3_57.png)

Problems that we're talking about with making our variable of interest unrelated to nuisance variables that we're not interested in or nuisance variables that we don't even know about。



![](img/849e472ba79624ded97b40e4795fbbf3_59.png)

![](img/849e472ba79624ded97b40e4795fbbf3_60.png)

However， there's other aspects of design that can serve the same purpose， for example。

 if we stratify and randomize within strata， the classic example of this when this was developed was artificial is working in field crop experiments and they needed let's say you're trying a different kind of seed you might block on different you know block on different areas of the field that you're going to plant in and randomize the different seeds to those areas so you might have two different kinds of seeds but they will have been distributed in a systematic way that is fair across the field but also then within that design there will also be some randomization this topic of experimental design is a pretty broad topic another great example is in biostatistics。

 the field that I work in the most a very common kind of design is a crossover design and in that case you try to use every subject is their own。



![](img/849e472ba79624ded97b40e4795fbbf3_62.png)

![](img/849e472ba79624ded97b40e4795fbbf3_63.png)

![](img/849e472ba79624ded97b40e4795fbbf3_64.png)

![](img/849e472ba79624ded97b40e4795fbbf3_65.png)

![](img/849e472ba79624ded97b40e4795fbbf3_66.png)

![](img/849e472ba79624ded97b40e4795fbbf3_67.png)

![](img/849e472ba79624ded97b40e4795fbbf3_68.png)

![](img/849e472ba79624ded97b40e4795fbbf3_69.png)

![](img/849e472ba79624ded97b40e4795fbbf3_70.png)

So let's say， for example， you're interested in looking at an two different kinds of aspirin。



![](img/849e472ba79624ded97b40e4795fbbf3_72.png)

And you might give the aspirin to one group of people and then the aspirin to another group of people。



![](img/849e472ba79624ded97b40e4795fbbf3_74.png)

It's the other aspirin to a different group of people。



![](img/849e472ba79624ded97b40e4795fbbf3_76.png)

Let's say they have different gels or whatever that determine how it gets absorbed in your stomach。



![](img/849e472ba79624ded97b40e4795fbbf3_78.png)

So。If those two groups aren't the same either。The randomization wasn't very good and there was some sort of imbalance that you just got unlucky about。

 or if the study was just observational。

![](img/849e472ba79624ded97b40e4795fbbf3_80.png)

![](img/849e472ba79624ded97b40e4795fbbf3_81.png)

Then the comparison of those two groups might be biased by whatever differentiates the groups rather than group one receiving one kind of aspirin and group two receiving a different kind of aspirin。



![](img/849e472ba79624ded97b40e4795fbbf3_83.png)

![](img/849e472ba79624ded97b40e4795fbbf3_84.png)

On the other hand， if you can give a person one kind of aspirin and then later on give them a different kind of aspirin when they have another headache that would compare each person to themselves control block on the person so to speak so that's a design strategy now there's some nuance with this design strategy as well。

 what happens if there's some residual effect of the first aspirin when you give the second one right so maybe you could handle that with some sort of washout period。

 a long washout period or something like that， but anyway the point of that design is to make it so that you're comparing people with themselves to control and everything that's intrinsic to the person。



![](img/849e472ba79624ded97b40e4795fbbf3_86.png)

![](img/849e472ba79624ded97b40e4795fbbf3_87.png)

![](img/849e472ba79624ded97b40e4795fbbf3_88.png)

![](img/849e472ba79624ded97b40e4795fbbf3_89.png)

![](img/849e472ba79624ded97b40e4795fbbf3_90.png)

![](img/849e472ba79624ded97b40e4795fbbf3_91.png)

At least across time periods control for that by giving both aspirs to each person maybe you would randomize the order in which they receive them and that's called a crossover design at any rate the broader point that I'm trying to make is it's often the case that good thoughtful experimental design can really eliminate the need for some of the main considerations that you'd have to go through in model building if you were to just collect data in an observational fashion。



![](img/849e472ba79624ded97b40e4795fbbf3_93.png)

![](img/849e472ba79624ded97b40e4795fbbf3_94.png)

![](img/849e472ba79624ded97b40e4795fbbf3_95.png)

![](img/849e472ba79624ded97b40e4795fbbf3_96.png)

![](img/849e472ba79624ded97b40e4795fbbf3_97.png)

![](img/849e472ba79624ded97b40e4795fbbf3_98.png)

The last thing I would say is there's one automated model search technique that I like quite a bit and I find it very useful and it's the idea of looking at nested models。

 so I'm often interested in a particular variable。

![](img/849e472ba79624ded97b40e4795fbbf3_100.png)

![](img/849e472ba79624ded97b40e4795fbbf3_101.png)

![](img/849e472ba79624ded97b40e4795fbbf3_102.png)

And I'm very interested in how the other variables that I've collected will impact it。

 so I'm interested in a treatment or something like that， some important variable。

 but I'm worried that my treatment groups are imbalanced or with respect to potentially some of these other variables so I might look what I'd like to look at is the model that just includes the treatment by itself then the model that includes the treatment and let's say age if the ages weren't really balanced between the two treatment groups and then one that looks at age and gender。

 if maybe the genders between the two groups weren't really balanced and then so on and this idea of creating models that are nested。

 every successive model contains all the terms of the previous model leads to a very easy way of testing each successive model okay and these nested model examples are very easy to do so I'm just going to show you some code right here。



![](img/849e472ba79624ded97b40e4795fbbf3_104.png)

![](img/849e472ba79624ded97b40e4795fbbf3_105.png)

![](img/849e472ba79624ded97b40e4795fbbf3_106.png)

![](img/849e472ba79624ded97b40e4795fbbf3_107.png)

![](img/849e472ba79624ded97b40e4795fbbf3_108.png)

![](img/849e472ba79624ded97b40e4795fbbf3_109.png)

![](img/849e472ba79624ded97b40e4795fbbf3_110.png)

![](img/849e472ba79624ded97b40e4795fbbf3_111.png)

![](img/849e472ba79624ded97b40e4795fbbf3_112.png)

![](img/849e472ba79624ded97b40e4795fbbf3_113.png)

On how you do nested model testing in R so hit I fit three linear models to our Swiss data set the first one just includes agriculture。

 let's pretend that that's the variable that we're interested in okay and then the next one includes agriculture and examination in education I put both those in because I'm thinking they're kind of measuring the same thing but now after this lecture I'm concerned open the possibility that they're too much so measuring the same thing but let's put that aside for this time being and then the third model includes examination education plus cat plus infant mortality so all the terms so now I have three nested models and I'm interested in seeing what happens to my effect as I go through those three models。



![](img/849e472ba79624ded97b40e4795fbbf3_115.png)

![](img/849e472ba79624ded97b40e4795fbbf3_116.png)

![](img/849e472ba79624ded97b40e4795fbbf3_117.png)

![](img/849e472ba79624ded97b40e4795fbbf3_118.png)

![](img/849e472ba79624ded97b40e4795fbbf3_119.png)

![](img/849e472ba79624ded97b40e4795fbbf3_120.png)

![](img/849e472ba79624ded97b40e4795fbbf3_121.png)

![](img/849e472ba79624ded97b40e4795fbbf3_122.png)

![](img/849e472ba79624ded97b40e4795fbbf3_123.png)

The point being in this case， you can test。

![](img/849e472ba79624ded97b40e4795fbbf3_125.png)

TheWhether or not the inclusion of the additional set of extra terms is necessary with the A No function so I do AO fit one fit3 and fit5 okay that's what I name them 135 and then you see down here what you get is the listing of the models Model1 Model2 Model3 and then it gives you the degrees of freedom okay that's the number of data points minus the number of parameters that had to fit the。



![](img/849e472ba79624ded97b40e4795fbbf3_127.png)

![](img/849e472ba79624ded97b40e4795fbbf3_128.png)

![](img/849e472ba79624ded97b40e4795fbbf3_129.png)

Sums of squares， the residual sums of squares， and then the excess degrees of freedom of going DF is the excess degrees of freedom of going from。

Model 1 to model2 and then Model2 to Model3 so we added two parameters and going from model1 to Model2 that's why that Df is2 and then we added two additional parameters going from Model 2 to Model3 so the two parameters we added from going from model one Model1 to model2 is we added examination and education there two regression coefficients going from model2 to model3 we added cat and infant mortality there two regression coefficients okay so with this residual sum of squares and the degrees of freedom you can calculate so-called f statistic and let's get a P value this gives you the s statistic and the P value associated with each of them and then here it shows that yes the inclusion of education examination appears to be necessary over just looking at agriculture by itself and then when I look at the next one it says yes the inclusion of Catholic and infant mortality appears to be necessary beyond。

Just including examination， education and agriculture。Okay。

 so if the way in which you're interested in looking at your data naturally falls into a nested model search as it often does。

 I think， when you're interested in one variable in specific， as in this case。

 I think this would be a pretty natural way of thinking about the series of analyses。

 then some kind of nested model search is a reasonable thing to do。

 it doesn't work if the models that you're looking at aren't nested。For example。

 if I had the first model or model2 had examination but not education and the third model had education but not examination this wouldn't necessarily this wouldn't apply you'd have to do something else and there I think you get into the harder world of automated model selection with things like information criteria so I would put all that stuff off to our prediction class and then just leave you this one technique that's useful in the one specific instance where you've decided to kind of。

Look along a series of models each getting increasingly more and complicated。

 but including the previous one。Okay， so I hope in this lecture that you've gotten a couple of model selection techniques that you can use。

 I hope you've also learned that there's some basic consequences that occur if you include variables that you shouldn't have or exclude variables that you should have。

 these has consequences to your coefficients that you're interested in they have consequences to your residual variance estimate。

 we didn't even touch on some other aspects of poor model that can occur such as absence of linearity and other things like that nonnormalality and so on。

So again， it's generally necessary to take your model fits with a grain of salt because more than likely one aspect of your model is wrong。

And I'll leave you then with this famous quote by George Box， who's very famously said。

All models are wrong， some models are useful， and I think that's a very good credo to go along with that。

 yes， for sure your model is wrong， but it might be useful in the sense of being a lens to teach you something useful and true about your data set。

Okay， so that ends today's lecture and I look forward to seeing you for the next one。

