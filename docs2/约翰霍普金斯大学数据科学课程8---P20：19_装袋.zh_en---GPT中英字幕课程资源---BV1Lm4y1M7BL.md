# 约翰霍普金斯大学数据科学课程8：《实际机器学习课程（约翰霍普金斯大学）》｜practical-machine-learning｜ - P20：19_装袋.zh_en - GPT中英字幕课程资源 - BV1Lm4y1M7BL

![](img/95a50204d20243034e521f58eb1fcdf2_0.png)

This lecture is about bagging which is short for bootstrap aggregating。

 The basic idea is that when you fit complicated models。

 sometimes if you average those models together， you get a smoother model fit that gives you a better balance between potential bias in your fit and variance in your fit。



![](img/95a50204d20243034e521f58eb1fcdf2_2.png)

![](img/95a50204d20243034e521f58eb1fcdf2_3.png)

![](img/95a50204d20243034e521f58eb1fcdf2_4.png)

So Boottrappa aggregating has a very simple idea， the basic idea is take your data and take resamples of the data set。



![](img/95a50204d20243034e521f58eb1fcdf2_6.png)

![](img/95a50204d20243034e521f58eb1fcdf2_7.png)

So this is similar to the idea of bootstrapping， which you would have learned about in the inference class that is part of the data science specialization。

 after you resample the cases with replacement， then you recalculate your prediction function on that resampled data。

 and then you either average the predictions from all these repeated predictors that you've built or you majority vote or something like that when you're doing classification。



![](img/95a50204d20243034e521f58eb1fcdf2_9.png)

![](img/95a50204d20243034e521f58eb1fcdf2_10.png)

![](img/95a50204d20243034e521f58eb1fcdf2_11.png)

![](img/95a50204d20243034e521f58eb1fcdf2_12.png)

![](img/95a50204d20243034e521f58eb1fcdf2_13.png)

The thing is， is that you get a similar bias that you would get from fitting any one of those models individually。

 but a reduced variability because you've averaged a bunch of different predictors together。

 This is most useful for nonlinear functions， so we'll show an example with smoothing。

 but it's also very useful for things like predicting with trees。



![](img/95a50204d20243034e521f58eb1fcdf2_15.png)

![](img/95a50204d20243034e521f58eb1fcdf2_16.png)

![](img/95a50204d20243034e521f58eb1fcdf2_17.png)

So I'm going to go back to the Ozone data， so it's in the LMtt learn package and I load the Ozone data set。



![](img/95a50204d20243034e521f58eb1fcdf2_19.png)

![](img/95a50204d20243034e521f58eb1fcdf2_20.png)

I then order for the purposes of showing you how this works。

 so I'm going to order the data set by the outcome， the ozone variable here。



![](img/95a50204d20243034e521f58eb1fcdf2_22.png)

And then I look at the data set and I can see it has four variables， ozone， radiation， temperature。

 and wind。

![](img/95a50204d20243034e521f58eb1fcdf2_24.png)

![](img/95a50204d20243034e521f58eb1fcdf2_25.png)

So the idea is that I'm going to try to predict temperature as a function of ozone。



![](img/95a50204d20243034e521f58eb1fcdf2_27.png)

So the first thing that we can do is just show you an example of how this works。

 so the basic idea is I'm going to create a matrix here and it's going to have 10 rows and 155 columns。

😊。

![](img/95a50204d20243034e521f58eb1fcdf2_29.png)

![](img/95a50204d20243034e521f58eb1fcdf2_30.png)

Then what I'm going to do is I'm going to resample the data set if for 10 different times。

 so I'm going to loop over 10 different samples of the data each time I'm going to sample with replacement from the entire data。



![](img/95a50204d20243034e521f58eb1fcdf2_32.png)

![](img/95a50204d20243034e521f58eb1fcdf2_33.png)

![](img/95a50204d20243034e521f58eb1fcdf2_34.png)

Then I'm going to create a new data set ozone zero。

 which is the resampled data set for that particular element of the loop。



![](img/95a50204d20243034e521f58eb1fcdf2_36.png)

And that's just the subset of the data set corresponding to our random sample。



![](img/95a50204d20243034e521f58eb1fcdf2_38.png)

Then I'm going to reorder the data set every time by the ozone variable。

 and you'll see why in just a minute。

![](img/95a50204d20243034e521f58eb1fcdf2_40.png)

Then I fit a low S curve each time， so a low S is a kind of a smooth curve that you can fit through the data。

 It's very similar to the sp model fits that we saw in a previous example with modeling with linear regression and so the basic idea is we're fitting a smooth curve relating temperature to the ozone variable so temperature is the outcome and ozone is the predictor and each time I use the resampled data set as the data I'm building that predictor on and I use a common span for each time。

 the span being a measure of how smooth that fit will be。



![](img/95a50204d20243034e521f58eb1fcdf2_42.png)

![](img/95a50204d20243034e521f58eb1fcdf2_43.png)

![](img/95a50204d20243034e521f58eb1fcdf2_44.png)

![](img/95a50204d20243034e521f58eb1fcdf2_45.png)

![](img/95a50204d20243034e521f58eb1fcdf2_46.png)

![](img/95a50204d20243034e521f58eb1fcdf2_47.png)

![](img/95a50204d20243034e521f58eb1fcdf2_48.png)

I then predict for every single low S curve， the outcome for a new data set for the exact same values。

 I always predict for ozone values 1 to 155。

![](img/95a50204d20243034e521f58eb1fcdf2_50.png)

![](img/95a50204d20243034e521f58eb1fcdf2_51.png)

So the Ithe row of this LL object is now the prediction from the low S curve from the Ith resample of the data ozone。



![](img/95a50204d20243034e521f58eb1fcdf2_53.png)

![](img/95a50204d20243034e521f58eb1fcdf2_54.png)

So what have I done here， I've resampled my data set 10 different times。

 fit a smooth curve through it those 10 different times。

 and then what I'm going to do is I'm going to average those values。



![](img/95a50204d20243034e521f58eb1fcdf2_56.png)

![](img/95a50204d20243034e521f58eb1fcdf2_57.png)

So here's what it looks like in this plot， so here I've plotted ozone on the X axis。

 these are the observed ozone values versus temperature on the Y axis。

 those are the observed temperature values and each black dot represents an observation。



![](img/95a50204d20243034e521f58eb1fcdf2_59.png)

![](img/95a50204d20243034e521f58eb1fcdf2_60.png)

![](img/95a50204d20243034e521f58eb1fcdf2_61.png)

Each gray line here represents the fit with one resampled data set。

 so you can see the gray lines have a lot of curvyness to them。

 They capture a lot of the variability in the data set。

 but they also maybe over captureture some of the variability。 They're a little bit too curvy。

 Once I've averaged those lines together， I get something that's a little bit smoother and is closer to the middle of the dataset。

 that's the red line。

![](img/95a50204d20243034e521f58eb1fcdf2_63.png)

![](img/95a50204d20243034e521f58eb1fcdf2_64.png)

![](img/95a50204d20243034e521f58eb1fcdf2_65.png)

![](img/95a50204d20243034e521f58eb1fcdf2_66.png)

So the red line is the bagged low S curve， it's basically the average of multiple fitted low S curves to the same data set where I've resampled it every time。



![](img/95a50204d20243034e521f58eb1fcdf2_68.png)

![](img/95a50204d20243034e521f58eb1fcdf2_69.png)

There's a proof that shows that the bagging estimate will always have lower variability。

 but similar bias to the individual model fits that you do。



![](img/95a50204d20243034e521f58eb1fcdf2_71.png)

![](img/95a50204d20243034e521f58eb1fcdf2_72.png)

In the carrot package there are some models that already perform bagging for you so if you're using the train function。

 you can set method to be bag Earth， tree bag， or bag FDA。

 and those are specific bagged models that the cart package will fit for you。



![](img/95a50204d20243034e521f58eb1fcdf2_74.png)

![](img/95a50204d20243034e521f58eb1fcdf2_75.png)

![](img/95a50204d20243034e521f58eb1fcdf2_76.png)

Alternatively， you can actually build your own bagging function and carrot。

 this is a bit of an advanced use， and so I recommend that you read the documentation carefully if you're going to be trying to do that yourself。



![](img/95a50204d20243034e521f58eb1fcdf2_78.png)

![](img/95a50204d20243034e521f58eb1fcdf2_79.png)

![](img/95a50204d20243034e521f58eb1fcdf2_80.png)

The idea here though is you basically are going to take your predictor variable and put it into one data frame。

 so I'm going to make the predictors be a data frame that contains the ozone data。

 then you have your outcome variable here it's going to be just the temperature variable from the data。



![](img/95a50204d20243034e521f58eb1fcdf2_82.png)

![](img/95a50204d20243034e521f58eb1fcdf2_83.png)

![](img/95a50204d20243034e521f58eb1fcdf2_84.png)

And I pass this to the bag function in carrot package。

 so I tell it that I want to use the predictors from that data frame， this is my outcome。

 this is the number of replications or the number of subamples I'd like to take from the data。



![](img/95a50204d20243034e521f58eb1fcdf2_86.png)

![](img/95a50204d20243034e521f58eb1fcdf2_87.png)

![](img/95a50204d20243034e521f58eb1fcdf2_88.png)

And then bag control tells me something about how I'm going to fit the model。

 so fit is the function that's going to be applied to fit the model every time this could be a call to the train function in the cart package。



![](img/95a50204d20243034e521f58eb1fcdf2_90.png)

![](img/95a50204d20243034e521f58eb1fcdf2_91.png)

Predict is the way that given a particular model fit that we'll be able to predict new values。

 so this could be， for example， a call to the predict function from a trained model。



![](img/95a50204d20243034e521f58eb1fcdf2_93.png)

![](img/95a50204d20243034e521f58eb1fcdf2_94.png)

![](img/95a50204d20243034e521f58eb1fcdf2_95.png)

And then aggregate is the way that we'll put the predictions together， so for example。

 it could average the predictions across all of the different replicated samples。



![](img/95a50204d20243034e521f58eb1fcdf2_97.png)

You can see that if you look at this custombaged version of the conditional regression trees。

 you can see that it gets some of the benefit that I was showing you in the previous slide with bagged lowS so the idea here is I'm plotting ozone again on the x axis versus temperature on the y axis。

 the little gray dots represent actual observed values the red dots represent the fit from a single conditional regression tree and so you can see that for example capture it doesn't capture the trend that's going on down here very well the red line is just flat even though there appears to be a trend upward in the data points here but when I average over 10 different bagged model model fits with these conditional regression trees I see that there's an increase here in the values in the blue fit which is the fit from the bagged regression。



![](img/95a50204d20243034e521f58eb1fcdf2_99.png)

![](img/95a50204d20243034e521f58eb1fcdf2_100.png)

![](img/95a50204d20243034e521f58eb1fcdf2_101.png)

![](img/95a50204d20243034e521f58eb1fcdf2_102.png)

![](img/95a50204d20243034e521f58eb1fcdf2_103.png)

![](img/95a50204d20243034e521f58eb1fcdf2_104.png)

![](img/95a50204d20243034e521f58eb1fcdf2_105.png)

![](img/95a50204d20243034e521f58eb1fcdf2_106.png)

![](img/95a50204d20243034e521f58eb1fcdf2_107.png)

![](img/95a50204d20243034e521f58eb1fcdf2_108.png)

![](img/95a50204d20243034e521f58eb1fcdf2_109.png)

So I'm going to look a little bit at those different parts of the bagging function。

 so in this particular case I'm using this C treee bag function。

 which you can look at in if you've loaded the cart package in R so for the fit part。

 it takes the data frame that we've passed and in the outcome that we've passed and it basically uses the C tree function to train a conditional regression tree on the dataset。



![](img/95a50204d20243034e521f58eb1fcdf2_111.png)

![](img/95a50204d20243034e521f58eb1fcdf2_112.png)

![](img/95a50204d20243034e521f58eb1fcdf2_113.png)

![](img/95a50204d20243034e521f58eb1fcdf2_114.png)

This is the last command that's called the C treee command。

 so it returns this model fit from the C tree function。



![](img/95a50204d20243034e521f58eb1fcdf2_116.png)

![](img/95a50204d20243034e521f58eb1fcdf2_117.png)

The prediction takes in the object， so this is going to be an object from the C tree model fit and a new data set X and it's going to get a new prediction so what you can see here is it basically calculates each time the tree response or the outcome from the object and the new data。



![](img/95a50204d20243034e521f58eb1fcdf2_119.png)

![](img/95a50204d20243034e521f58eb1fcdf2_120.png)

![](img/95a50204d20243034e521f58eb1fcdf2_121.png)

![](img/95a50204d20243034e521f58eb1fcdf2_122.png)

It then calculates this probability matrix and returns either the actually the observed levels that it predicts。

 or it actually just returns the response， the predicted response from the variable。



![](img/95a50204d20243034e521f58eb1fcdf2_124.png)

![](img/95a50204d20243034e521f58eb1fcdf2_125.png)

![](img/95a50204d20243034e521f58eb1fcdf2_126.png)

The aggregation then takes those values and averages them together or puts them together in some way。

 so here what this is doing is it's basically getting the prediction from every single one of these model fits so that's across a large number of observations and then it binds them together into one data matrix by with each row being equal to the prediction from one of the model predictions。



![](img/95a50204d20243034e521f58eb1fcdf2_128.png)

![](img/95a50204d20243034e521f58eb1fcdf2_129.png)

![](img/95a50204d20243034e521f58eb1fcdf2_130.png)

![](img/95a50204d20243034e521f58eb1fcdf2_131.png)

![](img/95a50204d20243034e521f58eb1fcdf2_132.png)

And then it takes the median and every value， so in other words。

 it takes the median prediction from each of the different model fits across all the bootstrap samples。



![](img/95a50204d20243034e521f58eb1fcdf2_134.png)

![](img/95a50204d20243034e521f58eb1fcdf2_135.png)

So bagging is very useful for nonlinear models and it's widely used， it's often used with trees。

 and you can think of an extension to this as being random forests。

 which we'll talk about in a future lecture。

![](img/95a50204d20243034e521f58eb1fcdf2_137.png)

![](img/95a50204d20243034e521f58eb1fcdf2_138.png)

![](img/95a50204d20243034e521f58eb1fcdf2_139.png)

Several models use bagging and Cart's main train function， like I told you about in previous slides。

 and you could also build your own specific bagging functions for any classification or prediction algorithm that you'd like to take a look at。



![](img/95a50204d20243034e521f58eb1fcdf2_141.png)

![](img/95a50204d20243034e521f58eb1fcdf2_142.png)

For further resources， I've linked to a couple of different tutorials on bagging and boosting。

 as well as the elements of statistical learning which has a lot more details about how bagging works。

 but remember that the basic idea is to basically resample your data， refit your nonlinear model。

 then average those model fits together over resamples to get a smoother model fit than you would have got from any individual fit on its own。



![](img/95a50204d20243034e521f58eb1fcdf2_144.png)

![](img/95a50204d20243034e521f58eb1fcdf2_145.png)

![](img/95a50204d20243034e521f58eb1fcdf2_146.png)

![](img/95a50204d20243034e521f58eb1fcdf2_147.png)

![](img/95a50204d20243034e521f58eb1fcdf2_148.png)