# 约翰霍普金斯大学《高管数据科学（5课全）｜Executive Data Science》中英字幕（deepseek p39 10_人群有多种形式.zh_en -BV1L9Fde5EXS_p39-

![](img/76550b8ed5bcf1afbb7b1c8b51b7ddd2_0.png)

I I want to talk a little bit more about populations and the kind of the forms in which they can come because populations can come in a variety of different forms that you may not necessarily expect。

 And so two common ones are kind of that I want to talk about for data that vary over time or data that vary over space。

 So for example， suppose you're looking at time series data you might be looking at like the closing value of Apples stock every day for a year so you've got this data it's daily data for a year of Apple's closing price。

 And so if you suppose you make an inference about you want to make an inference from this data。

 Well where is that what is the population there that you're trying to make an inference too so there's a couple of different candidate you can think about the first is like so this data came from a single years worth of data。

 Apples been around for many years So you might think that this data represents a sample from all the future years or feature or past years for example of data that might exist and so this data is a random sample from all the different years that you might look at。



![](img/76550b8ed5bcf1afbb7b1c8b51b7ddd2_2.png)

![](img/76550b8ed5bcf1afbb7b1c8b51b7ddd2_3.png)

Another possibility is that of course， Apple is on a stock market and there's other stocks that trade on a stock market。

 and so you might think of Apple as being a random sample draw from those other stocks in the stock market okay so there for example。

 if you're trying to approximate an index of stocks， Apple would be a random element of that index。

 you might sample different stocks to approximate the index。

So the other kind of phenomenon that often is a little bit can be where the population can be difficult to define is when you're looking at natural phenomena。

 So if things like earthquakes， hurricanes or wildfires。

 things that kind of occur in space you often collect data on that and analyze that music models or whatnot But then if you want to make an inference。

 you have to think a little bit carefully about well what exactly are you inferring making the inference about And so often with natural process it's useful to think of an unobserved stochastic process that kind of lies in the background and drops these events on the ground。

 So if you imagine there's a stochastic process of earthquakes that randomly drops earthquakes into our world or wildfires or hurricanes。

 whatever it may be。 And so when when you fit a model and you make an inference from that model。

 what you're inferring our properties of this unobserved stochastic process okay。



![](img/76550b8ed5bcf1afbb7b1c8b51b7ddd2_5.png)

![](img/76550b8ed5bcf1afbb7b1c8b51b7ddd2_6.png)

So the last thing that I'll talk about when it comes to inference is actually not about inference at all。

 it's actually a special case of using the data as a population so the underlying question here really that you want to ask yourself is do you actually need to make an inference at all sometimes you can think of the data as a population so there may be cases where you actually have all the data that you'll ever want to see and then you actually don't care about things that are outside the data which is really fundamentally what inference is about you're talking about things outside the data so if the data are the population one of the features of your analysis is that it will have no uncertainty because there's no sampling process that generates the uncertainty and you won't have to worry about competent interval or standard errors or P values because you'll have all of a certainty in the world that you'll need assuming that you don't have any problems with that data and so there are many cases where for example。

 if you have data collecting on your organization that you won't have to worry about things that are outside the data。

You may not be worried about things that are outside your organization so try to always think carefully about whether or not you actually have to make an inference because in many cases you may not。

 and then your analysis will be greatly simplified because you won't have to worry about things that are about making statements about things that you don't actually observe because you actually observe everything so just to summarize inferences the process of making statements from data about things that you can observe and there are many different kind of populations that you can think about or construct when when you're making inference from data。

 Of course and then there's the special case of using the data as the population in which case you're not making any inferences at all。

 but you actually have all the information you need So it's useful to figure out what situation you're in and for any given question and to always define the population coherently so that you know what you're making inferences about。



![](img/76550b8ed5bcf1afbb7b1c8b51b7ddd2_8.png)

![](img/76550b8ed5bcf1afbb7b1c8b51b7ddd2_9.png)