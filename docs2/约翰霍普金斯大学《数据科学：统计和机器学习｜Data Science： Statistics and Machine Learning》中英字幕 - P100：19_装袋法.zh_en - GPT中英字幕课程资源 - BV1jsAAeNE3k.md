# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P100：19_装袋法.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

This lecture is about bagging， which is short for bootstrap aggregating。

 The basic idea is that when you fit complicated models。

 Sometimes if you average those models together， you get a smoother model fit that gives you a better balance between potential bias in your fit and variance in your fit。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_1.png)

So Bootttrarappa aggregating has a very simple idea。

 the basic idea is take your data and take resamples of the data set。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_3.png)

So this is similar to the idea of bootstrapping， which you would have learned about in the inference class that is part of the data science specialization。

 after you resample the cases with replacement， then you recalculate your prediction function on that resampled data。

 and then you either average the predictions from all these repeated predictors that you've built or you majority vote or something like that when you're doing classification。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_5.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_6.png)

The thing is， that you get a similar bias that you would get from fitting any one of those models individually。

 but a reduced variability， because you've averaged a bunch of different predictors together。

 This is most useful for nonlinear functions。 So we'll show an example with smoothing。

 but it's also very useful for things like predicting with trees。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_8.png)

So I'm going to go back to the Ozone data， so it's in the LMtt learn package and I load the Ozone data set。

I then order for the purposes of showing you how this works。

 so I'm going to order the data set by the outcome， the ozone variable here。

And then I look at the data set and I can see it has four variables， ozone， radiation， temperature。

 and wind。

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_10.png)

So the idea is that I'm going to try to predict temperature as a function of ozone。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_12.png)

So the first thing that we can do is just show you an example of how this works。

 so the basic idea is I'm going to create a matrix here and it's going to have 10 rows and 155 columns。

😊，Then what I'm going to do is I'm going to resample the data if for 10 different times。

 so I'm going to loop over 10 different samples of the data each time I'm going to sample width replacement from the entire data。

Then I'm going to create a new data set Ozone zero。

 which is the resampled data set for that particular element of the loop。

And that's just the subset of the data set corresponding to our random sample。

Then I'm going to reorder the data set every time by the ozone variable。

 and you'll see why in just a minute。Then I fit a low S curve each time。

 so a low S is a kind of a smooth curve that you can fit through the data。

 It's very similar to the sp model fits that we saw in a previous example with modeling with linear regression and so the basic idea is we're fitting a smooth curve relating temperature to the ozone variable so temperature is the outcome and ozone is the predictor and each time I use the resampled data set as the data set I'm building that predictor on and I use a common span for each time。

 the span being a measure of how smooth that fit will be。I then predict for every single low S curve。

 the outcome for a new data set for the exact same values。

 I always predict for ozone values 1 to 155。So the Ithe row of this LL object is now the prediction from the low S curve from the Ith resample of the data ozone。

So what have I done here， I've resampled my data set 10 different times。

 fit a smooth curve through it those 10 different times。

 and then what I'm going to do is I'm going to average those values。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_14.png)

So here's what it looks like in this plot， so here I've plotted ozone on the X axis。

 these are the observed ozone values versus temperature on the Y axis。

 those are the observed temperature values and each black dot represents an observation。

Each gray line here represents the fit with one resampled data set。

 So you can see the gray lines have a lot of curvyness to them。

 They capture a lot of the variability in the data set。

 but they also maybe over captureture some of the variability。 They're a little bit too curvy。

 Once I've averaged those lines together， I get something that's a little bit smoother and is closer to the middle of the dataset。

 that's the red line。So the red line is the bagged low S curve。

 it's basically the average of multiple fitted low S curves to the same data set where I've resampled it every time。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_16.png)

There's a proof that shows that the bagging estimate will always have lower variability。

 but similar bias to the individual model fits that you do。In the carrot package。

 there are some models that already perform bagging for you， so if you're using the train function。

 you can set method to be bag Earth， tree bag， or bag FDA。

 and those are specific bagged models that the carrot package will fit for you。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_18.png)

Alternatively， you can actually build your own bagging function and carrot。

 this is a bit of an advanced use， and so I recommend that you read the documentation carefully if you're going to be trying to do that yourself。

The idea here though is you basically are going to take your predictor variable and put it into one data frame。

 so I'm going to make the predictors be a data frame that contains the ozone data。

 then you have your outcome variable here it's going to be just the temperature variable from the data。

And I pass this to the bag function in Carrot package。

 so I tell it that I want to use the predictors from that data frame， this is my outcome。

 this is the number of replications or the number of subamples I'd like to take from the data。

And then bag control tells me something about how I'm going to fit the model。

 so fit is the function that's going to be applied to fit the model every time this could be a call to the train function in the cart package。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_20.png)

Predict is the way that given a particular model fit that we'll be able to predict new values。

 so this could be， for example， a call to the predict function from a trained model。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_22.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_23.png)

And then aggregate is the way that we'll put the predictions together， so for example。

 it could average the predictions across all of the different replicated samples。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_25.png)

You can see that if you look at this custombaged version of the conditional regression trees。

 you can see that it gets some of the benefit that I was showing you in the previous slide with bagged lows so the idea here is I'm plotting ozone again on the x axis versus temperature on the y axis。

 the little gray dots represent actual observed values the red dots represent the fit from a single conditional regression tree and so you can see that for example capture it doesn't capture the trend that's going on down here very well the red line is just flat even though there appears to be a trend upward in the data points here。

 but when I average over 10 different bagged model model fits with these conditional regression trees I see that there's an increase here in the values in the blue fit which is the fit from the bagged regression。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_27.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_28.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_29.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_30.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_31.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_32.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_33.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_34.png)

So I'm going to look a little bit at those different parts of the bagging function。

 so in this particular case I'm using this C treee bag function。

 which you can look at in if you've loaded the cart package in R so for the fit part。

 it takes the data frame that we've passed and in the outcome that we've passed and it basically uses the C tree function to train conditional regression tree on the dataset。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_36.png)

This is the last command that's called the C treee command。

 so it returns this model fit from the C tree function。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_38.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_39.png)

The prediction takes in the object， so this is going to be an object from the C tree model fit and a new data set X and it's going to get a new prediction so what you can see here is it basically calculates each time the tree response or the outcome from the object and the new data。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_41.png)

It then calculates this probability matrix and returns either the actually of the observed levels that it predicts。

 or it actually just returns the response， the predicted response from the variable。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_43.png)

The aggregation then takes those values and averages them together or puts them together in some way。

 so here what this is doing is it's basically getting the prediction from every single one of these model fits so that's across a large number of observations and then it binds them together into one data matrix by with each row being equal to the prediction from one of the model predictions。

And then it takes the median and every value， so in other words。

 it takes the median prediction from each of the different model fits across all the bootstrap samples。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_45.png)

So bagging is very useful for nonlinear models and it's widely used， it's often used with trees。

 and you can think of an extension to this as being random forests。

 which we'll talk about in a future lecture。

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_47.png)

Several models use bagging and Cart's main train function， like I told you about in previous slides。

 and you could also build your own specific bagging functions for any classification or prediction algorithm that you'd like to take a look at。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_49.png)

For further resources， I've linked to a couple of different tutorials on bagging and boosting。

 as well as the elements of statistical learning which has a lot more details about how bagging works。

 but remember that the basic idea is to basically resample your data， refit your nonlinear model。

 then average those model fits together over resamples to get a smoother model fit than you would have got from any individual fit on its own。



![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_51.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_52.png)

![](img/8d1d14a46c8b1bb5eba9b2e93c933bd3_53.png)