# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p42 13_关联性分析.zh_en -BV1L9Fde5EXS_p42-

This lecture gives an example of an associational analysis and how to use formal modeling to challenge your findings。



![](img/c7ea35b4922bc4f630212228ab05c211_1.png)

![](img/c7ea35b4922bc4f630212228ab05c211_2.png)

The basic form of a model in an associational analysis will something looks something like this。

 you'll have an outcome y and you'll have a key predictor X。

 and then you'll have maybe some potential confounder that well call z。

 and then you have some independent random error that we call epsilon in addition to those factors we have a number of parameters that we want to estimate so alpha here is the intercept。

 it's the value of y when x and z are 0 we have beta which is the change in y associated with a one unit increase in x adjusted for Z and then gamma is the change in y associated with a one unit increase in z adjusting for x。



![](img/c7ea35b4922bc4f630212228ab05c211_4.png)

![](img/c7ea35b4922bc4f630212228ab05c211_5.png)

So this is a linear model and the parameter that we're trying to estimate here is beta。

 that's what tells us how our outcome changes along with our key predictor。

 Now there are other parameters， gamma and alpha that are in the model and we need to have them in the model for the model to work。

 but we're actually not interested in those parameters。

 So we sometimes call them nuisance parameters because we have to estimate them but we don't actually care about their value。

 So this is what I might consider to be a primary model it's very simple。

 there's a key predictor and there's only one confounder And so you may need to consider other things later on。

 but this is sometimes good as a primary model。 On the other hand。

 sometimes we'll use a primary model that doesn't have any confounders and then slowly add things to the model to see how our results change。

 So the example I'm going to use here is going to be an advertising campaign for a new product。

 So imagine you're selling something and you're thinking of buying ads on Facebook to sell this product and you want to know how effective those ads are going to be。

 So ultimately what you want to do is sell more products and make more money from。

And so one thing you might do is try to pilot a one week experiment where you buy Facebook ads for a week and see how it does。

 Okay so this is a very simple design。 you might say look at the one week before the ad campaign。

 the one week during the ad campaign and then the one week after the ad campaign just to see how the sales numbers change while you're running the ads and then you could compare the total sales for the three weeks during the three weeks before and three weeks after and see if there's any reasonable increase in the total sales So using this type of design in this kind of experiment know what would you expect to see。



![](img/c7ea35b4922bc4f630212228ab05c211_7.png)

So here's a data that's not real， but it kind of represents the ideal scenario for what you might see in an experiment like this。

 So in the first seven days how can I have an average about $200 per day in the next seven days is during the campaign you have an average about $300 and then after the campaign finishes you have an average again of about $200 So it's possible to tell just from this graph without any doing anything fancyed that the ad campaign seems to add about $100 per day to the total daily sales。

So in this case， your primary model might be very simple。

 might look something like this where you have Y is the outcome that would be the daily sales。

 And then x is just an indicator of whether a given day fell during the ad campaign or not。

 And then still your primary interests is on the coefficientient beta。

 which tells you how your total daily sales increases with the ad campaign in place。 So for example。

 the data for this might look something like this in this table here where you have 21 days and you have seven days without the campaign seven days with the campaign in seven days without。

 you can see the daily sales change as you go in and out of the campaign。 So it's a very basic setup。

 very simple and this is kind of what you would love to see in your data if you in an ideal world。

 Of course in reality， you'll never see data like this。 therell always be something more complicated。

 So here's something here's a picture of what kind of more realistic data might look like from an experiment like this。

 typicallyy， real worldorl data are more noisy。 There are other trends in the background that are kind。



![](img/c7ea35b4922bc4f630212228ab05c211_9.png)

![](img/c7ea35b4922bc4f630212228ab05c211_10.png)

up your relationship so it makes it harder to analyze the data So you'll notice that in this picture。

 there does appear to be an increase in sales during the campaign period。

 but the problem is that it seems like there was the increase started actually before the campaign even started the sales were kind of going up and so you might want to ask are there background trends that for some reason increased sales over a threewe period So it's possible that we would have seen higher sales in the product even without the ad campaign just because of these background trends And so the question you really want to know is did the ads cause an increase in sales over and above whatever background trends that might have been going on that you're not aware of。

So let's take our primary model， which is just going to be a simple model with the outcome and indicator of the campaign。

 If we use that model， what you'll see is that we'll estimate beta the increase in the daily sales due to the ad campaign to be $44。

75 okay Now now let's suppose we add a background trend into our model。

 So instead of the primary model we we just have the key predictor in the outcome。

 we fit the following model， which has a quadratic trend for time。

 So this allows for kind little curvature and allows for kind of rising and falling of the daily total sales Okay。

So if we use this model and we still try to estimate beta。

 what we get is that our estimate of beta is $39。86。

 so that's somewhat less than the beta that we estimated from the primary model and recall that this is the increase in sales due to the ad campaign。

So just for comparison， we can fit actually an even even more complex model。

 we could have a fourth order polynomial to model the trend just in case there might be something more complicated going on in the background。

 and then if we were to fit that model， this gives us a beta of $49。

10 per day so under this model the ad campaign added an extra $49。10 per day to our sales。

So we have three models， a one primary model and two secondary models。

 and so Model1 tells us that our estimate of beta is $44。75， Model 2 tells us it's $39。

86 and Model 3 tells us it's 49。10， so what do we do with this？



![](img/c7ea35b4922bc4f630212228ab05c211_12.png)

So there are a number of ways to evaluate your formal modeling and your kind of your examination of primary and secondary models。

 Now the first thing that you want to look at is the effect size。

 So the effect size essentially what is the value of beta that you estimate and is it big or is it small or how do they compare to each other from the different models So the three different models represent a range of going from roughly $39 to $49 And so you might want to ask yourself is that a big range do you care about those differences it's a little hard to answer that question without knowing what the context is and what your situation is For example。

 if the cost of the ad campaign were really low and it didn't really matter how much how much you made as long as you made something。

 then maybe you don't care whether it's $39 or $49 as long as you make something back then the ad campaigns worth it。

 On the other end， if the ad campaign were really expensive so maybe it's 20 a day to run these ads then you might care which which end of the range you fall on when you run this ad。

Because maybe $39 is not worth it， but $49 would be worth it so ultimately the question you're asking is you know is it worth the risk of buying these ads given the evidence that you've seen from these different models showing you that there might be a range of say $39 a $49 increase in total sales during the period of the ad campaign。

The second factor you want to think about is plausibility。

 so even though we fit many different models not all of them are equally plausible okay so the primary model may not be plausible because it didn't incorporate the possibility of any sort of background trend and likely with real worldorld data there's going to be lots of things going on in the background and you don't want to just forget about them because they could affect how your sales go and you may think that your campaign is having a big effect when actually there's something just going on in the background that's moving your sales numbers。

Now the third model that we did which had this kind of fourth third or polynomial was a relatively complex model to capture a trend and it may be too complex or more than we need to capture a very simple。

 smooth trend in the background and so Model2 seems kind of reasonable we allow for this background trend it's a polynomial model but it's not very complicated or at least not overly complicated to try to capture this trend。

 so whether a model could be considered more or less plausible will depend on your knowledge of the subject and your ability to map real- world events to the mathematical formulation of the model。

The last concept to think of is parsimony so when different models tell the same story， for example。

 if you don't care about the range of $39 or $49 then it's sometimes better to just choose the simpler model or the model with fewer parameters and the reason is it's usually easier to tell a story about the data when you have fewer parameters and so this makes the model more useful and then finally a simpler model will be more efficient because you're using more data to estimate fewer parameters and so that's generally good from a statistical standpoint and that will afford you to have less uncertainty about those estimates about those parameter estimates because you're able to use more data for each of the parameters。

So in this example， this was an associational analysis and it focused on kind of estimating the association between two features。

 total sales and the ad campaign while adjusting for other confounding factors like this potential background trend the primary models capture the basic relationship and while the secondary models are used to kind adjust for different factors in different ways So we had two different models kind adjusting for the background trends。

 So what conclusion you make ultimately may depend on outside factors like cost or kind timing issues and so you have to factor all this in when you kind ultimately make draw your conclusions about what to do or what decisions to make and also you may have to think about the plausibility of the various models that you've chosen to determine what evidence you're going to wait more heavily than other evidence。

 So this is the basic kind of outline in associational analysis obviously there often be many more things that you're going to want to do but they will generally follow this framework and you're going to want to iterate between kind fitting primary models and secondary models until you get。

To an answer that you can use or can make a decision on。



![](img/c7ea35b4922bc4f630212228ab05c211_14.png)