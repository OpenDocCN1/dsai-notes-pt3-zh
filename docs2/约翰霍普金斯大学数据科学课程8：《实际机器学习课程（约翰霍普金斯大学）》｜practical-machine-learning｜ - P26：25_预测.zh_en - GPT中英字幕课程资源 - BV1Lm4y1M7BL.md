# 约翰霍普金斯大学数据科学课程8：《实际机器学习课程（约翰霍普金斯大学）》｜practical-machine-learning｜ - P26：25_预测.zh_en - GPT中英字幕课程资源 - BV1Lm4y1M7BL

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_0.png)

This lecture is about forecasting， which is a very specific kind of prediction problem and it's typically applied to things like time series data so for example。

 this is the stock information for Google on the NasdaAq and so it's the symbol GOOG and you can see over time that there's a price for this stock and it goes up and down so this introduces some very specific kinds of dependent structure and some additional challenges that must be taken into account when performing prediction。

And so first of all the data are dependent over time and so that alone makes prediction a little bit more challenging than it is when you have independent examples。

 there are some also some specific pattern types that should be paid attention to trends such as longterm increases or decreases。

 seasonal patterns are very common in this kind of data， for example， seasonal patterns over weeks。

 months， years， etc， cycles， patterns that rise and fall periodically over a period that's longer than a year。

 for example。

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_2.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_3.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_4.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_5.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_6.png)

Here the subsampling into training and test can be a little bit more complicated because you can't just randomly assign samples into training and test。

 you have to take advantage of the fact that there's actually specific times that are being sampled and that points are dependent in time。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_8.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_9.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_10.png)

Similar issues arise in prediction of spatial data， for example。

 there's dependency between nearby observations and there may be location specific effects that have to be modeled with doing prediction。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_12.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_13.png)

Typically the goal here is to predict one or more observations into the future。

 and all standard prediction algorithms can be used。

 but you have to be a little bit cautious about how you use them。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_15.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_16.png)

So one thing to be aware of is that you have to be careful of spurious correlations so time series can often be correlated for reasons that do not make them good for predicting one from the other。

 so if you look at you can go to Google correlate to correlate different words over time the frequency of different words over time and so for example here you can see a correlation between the Google stock price shown in blue and Solitaire network which is in red and so those don't necessarily have anything to do with each other at all。

 but they have a very high correlation you might think you might be able to predict one from the other even though in the future they might diverge substantially because they aren't necessarily related to each other at all。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_18.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_19.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_20.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_21.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_22.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_23.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_24.png)

It's also very common in geographic analysis， this is actually a cartoon from XKCD that shows that heat maps。

 particularly population-based heat maps， have very similar shapes because of the place where many people live so for example the users of a particular site or the subscribers to a particular magazine or the consumers of a particular type of website may all appear in the very similar places because the highest density of population in the United States is over here on the Eastern seaboard and so you see very similar heat maps of a large number of individuals at all of those different places。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_26.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_27.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_28.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_29.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_30.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_31.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_32.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_33.png)

You should also be aware of extrapolation so this is a kind of a funny example that shows what happens if you extrapolate time series out without being careful about what could happen。

 so this shows on a log scale the winning time of a large number of sorry of races that occurred at the Olympics。

 the blue times are men and the red times are women and these authors of this paper extrapolated out into the future and said that in 2156 that would be when women would run faster than men in this sprint and while we don't know when that win or when that may or may not occur。

 one thing that was pointed out is that this kind of extrapolation is very dangerous eventually at some time in the future。

 both men and women would be predicted to run negative times for the 100 meters and so you have to be very careful about how far out you extrapolate from your data。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_35.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_36.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_37.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_38.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_39.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_40.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_41.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_42.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_43.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_44.png)

So I'm going to show a quick example of some forecasting using the Qua mod package and some Google data。

 so if I load this Qua mod package and I can load in a bunch of data from the Google stock symbol and I can get it from the Google Finance dataset and so if I look at this Google variable。

 I get the open， high low close and volume information for a particular Google stock from the first of January 2008 to December 31st 2013。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_46.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_47.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_48.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_49.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_50.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_51.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_52.png)

So I can summarize this monthly and store it as a time series so I can use the two monthly variable or function to convert that to a monthly time series and I can just take the opening information and then I can create a time series object using the TS function in R then if I plot that I can see here's the monthly opening prices for Google over a period of seven years。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_54.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_55.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_56.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_57.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_58.png)

So an example time series decomposition would decompose this time series into a trend。

 any kind of consistent pattern， a seasonal pattern over time。

 and cyclic patterns where the data rises and falls over nonfied periods。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_60.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_61.png)

And so one way that we can do this is with the decompose function in R so if I decompose this in an additive way。

 then I can see that there's a trend variable that appears to be an upward trend of the Google stock price。

 there also appears to be a seasonal pattern as well as a more random cyclical pattern in the data so this is decomposing this series here into a series of different types of patterns in the data。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_63.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_64.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_65.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_66.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_67.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_68.png)

So here for training and test sets I have to build training and test sets that have consecutive time points。

 so here I'm building a training set that starts at time。1 and ends at  time。

5 and then a test set that is the next consecutive set of points after that so that way I can always build a training set and apply it to a test set that have consecutive time points that show the same sort of trends that I observe in my data。

So there's a couple of different ways for doing forecasting， one is to do a simple moving average。

 which in other words it basically averages up all of the values for a particular time point。

 the prediction will be the average of the previous time points up to a particular time。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_70.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_71.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_72.png)

You can also do exponential smoothing in other words。

 basically we weight nearby time points as higher values or more heavily than time points that are farther away。

 so there's a large number of different classes of smoothing models that you can choose。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_74.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_75.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_76.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_77.png)

And for exponential smoothing， get you can fit a model where you have different choices for the different types of trends that you might want to fit。

 and then when you forecast， you can get a prediction that comes out of your forecasting model and you can also get sort of prediction bounds for what are the possible values that you could get from that prediction。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_79.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_80.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_81.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_82.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_83.png)

And you can get the accuracy using this accuracy function so you can basically get the accuracy of your forecast using your test set。

 and it'll give you root mean squared error and other metrics that are more appropriate for forecasting。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_85.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_86.png)

I've obviously gone through this very fast and so if you want more information。

 there's actually an entire field dedicated of forecasting and time series prediction。

 and I would highly recommend Rob Hinman's forecasting principles and practice this is a free book that's online and it's really。

 really good and has a lot of information about how to get started in forecasting so the cautions are to be wary of spurious correlations be very careful about how far you predict out into the future with extrapolation and be wary of dependencies like seasonal effects over time。

😊。

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_88.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_89.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_90.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_91.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_92.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_93.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_94.png)

If you would like information on form financial prediction and financial forecasting。

 the quant mod and Quao packages are also very useful in that area。



![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_96.png)

![](img/ea32c1e1785f3b53a7c081ab7fcd88c4_97.png)