# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p04 3_机器学习基础.zh_en -BV1L9Fde5EXS_p4-

Hi， my name is Brian Kaho， and this is the lecture on machine learning。

So I'm going to define machine learning as a set of algorithms and take a set of inputs and return a prediction。

And I would classify the way in which it returns a prediction。

 at least in the two ways that are most useful for data science as two broad categories。

And this is not exhaustive， there's other aspects of machine learning。

 but the two I want to focus on are unsupervised and supervised versions of machine learning。

In an unsupervised case， you're trying to build a prediction but where you don't actually have the outcome to train the algorithm。

 so I would define unsupervised learning as trying to uncover unobserved factors and some examples of this would be clustering mixture models and principal components。

To give you an example， I will go back to one of the first examples of clustering and that is for the famous G factor in psychometrics。

 so people like Spearman of famous psychometrician and statistician used factor analysis to combine collections of questionnaire data to find that people who took these tests。

 these psychometric tests tended to cluster。They hypothesized that these clusters represented some outcome。

 some unmeasured outcome that represents some kind of intrinsic intellectual ability。

 so this was one of the first examples of unsupervised clustering done well before the advent of computers I might add。

If that's unsupervised clustering， let's talk about what's supervised。Learning is。

So supervised learning is using a collection of predictors and some observed outcomes to build an algorithm。

 to predict this outcome when it's not observed， so some examples of supervised learning algorithms include random forest boosting support vector machines。

So let me I'll try and give you a similarly old， maybe in fact older version of supervised learning。

 regression， and I give a picture of my regression book which is free on Le pub。

 which you're more than welcome to download but the reason I actually put the book up here is because of the picture on the cover and I like this picture quite a bit because it was taken from Francis Galton's original paper where he developed regression in this paper he was trying to predict the height of sons from the height of the parents in some cases some mid midpoint between the father and the mother's height and other cases just from the father's height。

 but this is an example where we have an observed outcome， the son's height。

 and then we have the predictor the father's height and Francis Galalton wanted to build up an algorithm so that when you just knew the father's height and say the mother was still pregnant。

Then you could try and predict what the sun's height was。

So this led him to the development of what we think of now as linear regression。However。

 modern prediction algorithms can take thousands and tens of thousands of potential predictors to predict outcomes now you need a lot of data to train up your algorithm。

 but that's been some of the real advances in this area so in these cases you would use a collection of outcomes。

AndLo of collection of a large collection of predictors， you would build up this algorithm。

And then you would then be able to predict the outcome in instances where you didn't have it。

 so you might want to predict stock prices in the future。

 but doing that you're going to use historic stock pricing data with a lot of predictors to try and build up your algorithm so that's machine learning in a nutshell I'd like to contrast it because it seems very different many people are familiar with traditional statistics。

 but there may be a little less familiar with machine learning。

 so I'd like to contrast traditional statistics with machine learning So in my mind traditional machine learning。

 the main emphasis at least let's focus on supervised learning it emphasizes predictions。

And then it tries to evaluate performance via the prediction performance。So unlike。

 and we'll talk a little bit about statistics， traditional statistics， how it evaluates performance。

So there's a lot of concern for overfitting in machine learning。

 but there's not as much concern for model complexity。

 so if you have a highly complex model that's not overfitting and yielding good predictions。

 then there's more of a tolerance for that in the field of machine learning than there is in the field of traditional statistics and so there's an emphasis in machine learning on performance and in less of an emphasis on superpopulation models and generalizability that occurs a lot in statistics。

So generalizability in machine learning tends to be obtained by applying the algorithm on novel data sets where you know the outcome and checking to see how good your predictions are。

 rather than on modeling and sampling assumptions that often occur in traditional statistics。😡。

And there's， of course， in machine learning， a concern over performance and robustness。

So in traditional statistical analysis， let's contrast that now。

 this tends to emphasize not so much predictions， even if it's doing prediction。

 but emphasizes predictions or models as they relate to some superpop。

 you have a sample and you want to generalize it to some superpop。That the sample was drawn from。

 so there's less of an emphasis on sampling of assumptions and machine learning。

Traditional statistics tends to focus on a priori hypotheses where things like unsupervised learning tend to try to generate the hypotheses right the G factor generated this idea that there was intrinsic variability in intelligence。

It traditional statistics tends to focus on simpler models。

Over complex ones ands to put a higher penalty on complexity than a machine learning algorithm does。

 in fact， the idea of a model seems already simpler than the idea of an algorithm， right？

Just the words themselves， they seem like when I give you the word algorithm it conjures up an image of something that's far more complex than the idea of a model。

 the idea of a model is a simplifies version of something that's complicated。

So there's a lot of emphasis in traditional statistics on parameter interpretability。

And then an emphasis on the modeling and assumptions that go in to connect your data to the population you're trying to draw inferences on。

And just like machine learning， there's concern over assumptions or robustness。

 so those are some broad distinctions between machine learning and statistics。

 though of course there's a lot of overlap。Let's just give you some examples。

Problems that occur where you could both approach them from a statistics perspective and machine learning perspective and talk about them。

 one of the most famous recent machine learning exercises was the Netflix Prize。

And here the goal was to predict movie choices。From a large collection of instances where users rated movies。

 so you had the outcome data and you had a lot of data on their viewing history and other things that might help you perform that prediction。

 so machine learning would build an automated movie recommender system and success would be defined as anything that produces reliable predictions。

Statistical analysis on the other hand， would try to build a parsimonious and interpretable model to better understand why people choose the movies that they do。

 so you'd want something that was interpretable， you'd want to understand aha。

 this is the reason why this prediction works is because because of this psychology。

 people have a tendency to like this kind of movie if they like this kind of movie。

 whereas an algorithm can tend to have a lot more complexity built in and may sacrifice some interpretability。

Another example that I was engaged in was the Heritage Health Prize in the Heritage Health Prize we wanted to identify the number of days that patients would spend in the hospital in subsequent years。

 given their prior year' hospitalization rates and。

A large collection of their insurance claims data that led to their hospitalization and whatever other insurance claims they had。

And in this case， if you're doing a machine learning exercise， which is how we approach the problem。

 we wanted to build an automated system for predicting hospital stays from previous claims and all we want success is anything that yields reliable predictions for the next year。

 so when we predict for a person the next year，How long that we think they're going to be in the hospital。

 if that's a number greater than zero， we might want to do some sort of intervention。

Statistical analysis， the goal would be to build a parsimonious and interpretable model to better understand why people stay in the hospital longer。

 so success would be anything true that's learned about hospital stays。

 whether or not it gives good predictions。Statistical analysis can you can have a great example of a statistical effect that would yield no significant prediction is take。

 for example， if a drug is shown to have a very small but positive effect for reducing the symptoms of Alzheimer's disease that would be actually a huge success for the medical field。

But knowledge of whether the effect is very minor， but statistically significant。

 that would be a huge effect that would be a landmark study in the field of Alzheimer's disease。

 but if it was a really minor effect， knowledge of whether or not someone was taking that drug wouldn't lead to a good prediction of their Alzheimer's disease symptoms。

That may something like their age and other factors。

 their age and their family history of Alzheimer's disease and other things may be a better predictor of the severity of the likely severity of their disease than whether or not they're taking this drug。

 so that is an instance where。Statistical significance in a statistical model that's important may not lead to。

And important。That important predictor being something that would be important in a machine learning algorithm。

 so I just want to emphasize that there's a big difference between these two approaches even though there's a lot of overlap。

 and I think the biggest difference is just in how you're thinking about the problem and what you're concerned with。

The last example I'd like to give is kind of a relatively famous one which is Google flu trends in this。

 the very clever people at Google tried to come up with a way to predict flu cases based on people's search history and try to predict outbreaks so in a particular area where a lot of ISPs traffic is relating to searches on TaMAFlu that might suggest an outbreak in that area。

 so success for an algorithm in this case would be anything that produces reliable predictions and they had。

 for example the CDC data， the historical CDC data to build up the predictions to try and predict flu outbreaks in the future。

 I'm not so sure how this is held up but nonetheless that's how you would approach this as a machine learning algorithm is a very clever ID I think。

Statistical analysis， on the other hand， would instead try to approach the problem of trying to learn what predicts flu outbreaks and anything true that was learned about that would count。

 regardless of whether or not it dramatically improved our ability to predict。

So the goal would be to build a parsimonious and interpretable model to better understand the outbreaks rather than to just get prediction performance。

 so if you build a model， if you built a model that was simpler。

And led to better understanding of what was going on， but it didn't lead to good predictions。

 that would be a beneficial outcome in statistical analysis。

So some lessons learned are that both approaches are extremely valuable and they have their replaced。

And the amount of tolerable model and algorithm complexity changes dramatically between the approaches and their goals are often very different。

 however I would say this caveat that there's a fair amount of work in making machine learning more interpretable and a fair amount of work in making traditional statistical approaches have better prediction so it does seem like both fields are working towards some common areas in the middle in the next lecture I'm just going to give you some examples of further reading that you can go into for contrasting traditional statistics versus machine learning so thank you for listening and I'll see in the next lecture。

