# 约翰霍普金斯大学《数据科学：统计和机器学习｜Data Science： Statistics and Machine Learning》中英字幕 - P98：17_使用回归进行预测：多个协变量.zh_en - GPT中英字幕课程资源 - BV1jsAAeNE3k

This lecture is about two things， first it's about predicting with regression using multiple covariates。

 but more importantly it's about exploring a data set and trying to identify which predictors are most important to include in a prediction model。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_1.png)

So we're again going to be using the wages data to try to predict the wages of a group of men that come from the Mid Atlantic。

 this data set is available in the ISLR package which you can find here and it comes from the book Introduction to Statistical Learning。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_3.png)

So the first thing that we do is that we load the dataset in and so here is the ISLR data。

 we're also loading the GGplot2 package for some exploratory analysis and we're loading the CAt package for doing prediction and we're going to subset the data for our exploration purposes to just the part of the data that isn't the variable we're trying to predict。

 so we select out the log wage variable which is the variable that we're going to be predicting in this analysis。

Then we can look at a summary of the data and so we can already see some features， for example。

 we saw before that this data has only males included in the data and that， for example。

 the region is entirely people from the mid Atlantic。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_5.png)

So to do a little bit more exploration， we first need to subset things into the training and test sets。

 so we use that with the createreate data partition function and we subset into a training and test set and so we're going to do all of our exploration again on the training set because when we're building models were not going to use any of the test set we're only going to apply at once。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_7.png)

So the first thing that you can do is a feature plot。

 so this feature plot shows a little bit about how the variables are related to each other。

 sometimes this plot is useful and sometimes it isn't in this particular plot it's a little bit hard to see because everything is so squish together but if you make it on your own using this function。

 you'll see that it's a little bit easier to see。So for example。

 you can see that there appears for the job class， there appears to be this group。

 appears to be a little bit higher than that group for the job class in terms of the outcome。

 and you can see that there's at least for this age variable， the relationship to the outcome， again。

 there seems to be some outlier group two separate groups here。

 that gives us some indication that we might be able to use that variable to predict。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_9.png)

So the first thing that we can do is plot the variables versus age。

 so this is plotting the wage variable versus the。Age variable and you can see that there appears to be some kind of trend which we saw in the previous lectures。

 but there also is this set of points that's outlying up here and so the idea is that that set of points that's outlying up there might be something we can predict。

 but we would have to figure out what variable it is that is representing that chunk。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_11.png)

So one way that you can do that is you plot one variable， one predictor age versus the outcome wage。

 and then you color the points by another variable in this case job class and so you can see for example。

 that it appears that most of these points up here are blue instead of pink and so that means they come from the information group so this gives us some indication that the information variable might be able to predict at least some fraction of the variability that's in that top class up at the top of the plot。

You can also color it by education， so here I'm just doing Q plot again。

 so I'm plotting age versus wage and I'm telling it to color the plot by education and again I'm only using the training set because we're trying to only look at the training set for our。

Development of our model and you can see that the advanced degree also explains a lot of the variation up here in the top group。

 and so some combination of degree and class of job could explain why the relationship between age and wage isn't just a perfect relationship down here in one big cloud。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_13.png)

So the next thing that we can do is fit a linear model with multiple variables in it and so the idea here is again we're just fitting lines but now we're fitting more than one line and so the idea is we have some intercept terms so that's just the baseline level of wage that we might have and then we might have a relationship with the age of the person and then we might have a relationship with what job class you're in so one way that we typically do that is by fitting an indicator variable。

 so an indicator variable is variable that's denoted like this in mathematical notation it just says if the job class for the I person is equal to information。

 this variable is equal to one， if the job class for the I person is not equal to information then this variable is equal to zero and so this represents the difference in the wages between the people with job class equal to information versus job class equal to not information。

 when you fix all the other variables in the regression model。You can also do this for education。

 it's a little bit more complicated right because there are multiple education levels so we create an indicator variable for each of the different education levels and so here this is a sum of four indicator variables and so the variable is equal to one。

 if the education for person I is equal to level K that variable is equal to1 and zero otherwise。😊。

So then we can fit the model just like we did before。

 so we have we're using the train function in the carrot package and we again use wage as the outcome and then Tilde represents the formula on the right is going to be used to predict the variable on the left。

And so we use age， job class and education so job class and education are both factor variables and R and so by default it does。

 you know， it creates these indicator variables like I've shown here so that when it fits the model it takes that into account by automatically。

Again， we're fitting the model in the training set and we can look at the final model and you can see now that the final model has 10 predictors。

 even though we only put three variable names into the formula。

 and the reason is because this variable right here actually received more than one predictor in the data because of the way that we had to create these indicator functions。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_15.png)

So then we can look at some diagnostic plots so this is very typical for when you're building these regression models so the idea here is you could plot the fitted values so this is the predictions from our model on the training set versus the residuals that's the amount of variation that's left over after you fit your model and so what you'd like to see is that this line would be centered at zero on this axis because the residuals is the difference between our model prediction and our actual real values that we're trying to predict and here you can see there's still a couple of outliers up here that have been labeled for you in this plot。

And so those variables might be variables that we want to try to explore a little bit further and see if we can identify any other predictors in our data that might be able to explain them。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_17.png)

The other thing that we can do is color by variables not just used in the model。

 so for example here I'm plotting again the fitted values from our model versus the residuals。

And so again we'd like to see this land on the zero line because it's the difference between our fitted values and our real values and so what we can do is plot on this plot we can again plot it by different variables in this case we can plot it by for example。

 race and so you can see that it seems like some of these outliers up here may be explained by the race variable and the data and so these is another exploratory technique。

 plotting the fitted model versus the residuals and then coloring it by different variables to identify potential trends。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_19.png)

Another thing that can be really useful is plotting the fitted residuals versus the index and what do I mean by the index so the data set comes in a set of rows that you got in a particular order and so the index is just which row of the data you're looking at。

And the y axis here is the residuals and so you can see that all the residuals seem to be happening。

 high residuals seem to be happening down here at the right end。

 the highest row numbers and you can also see a trend with respect to row numbers and so whenever you can see a trend or a outlier like that with respect to the row numbers。

 it suggests that there's a variable missing from your model because you're plotting the residuals here so that's the difference between the true values in the fitted and that shouldn't have any relationship to the order in which the variables appear in your data。

 unless and this is what's typically you discover when you see a trend like this or outliers like this at one end of this plot that there's a relationship with respect to time or age or some other continuous variable that the rows are ordered by。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_21.png)

So the other thing that you can do is plot the wage variable。

 so this is the wage variable in the test set versus the predicted values in the test set so ideally these two things would be very close to each other ideally you'd have essentially a straight line on the 45 degree line where wage was exactly equal to our predictions of course that isn't how it always works out and then in the test set you can explore and try to identify trends that you might have missed so for example here we're looking at the year that the data was collected in the test set as a way of exploring how our model might have broken down。

Now， something to keep in mind is that if you do this sort of exploration in the test set。

 you can't then go back and reupate your model in the training set because that would be using the test set to rebuild your predictors。

 this is more like post a postmortem on your analysis or a way to try to determine whether your analysis worked or not。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_23.png)

If you want all of the covariates in your model building。

 one thing that you can do is use this again in the train function。

 you can pass it on outcome and then tilde and then if you put a dot here instead of putting a set of variables separated by plus signs it says predict with all of the variables in the data so this is a model fit with all of the variables and so this is the wage variable and the predictions here and so you can actually see that it does a little bit better when you include all of the variables in the data this is by default if you don't want to try to do some sort of model selection in advance。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_25.png)

So linear regression is often useful in combination with other models。

 it's quite a simple model in the sense that it always fits lines through the data and so it can capture a lot of variability if the relationship between the predictors and the outcome is linear if it's not linear than you often miss things and it can be better blended with other models we' talk about model blending later in the class。

Exploratory data analysis can be very useful with regression models because like the plots we made with residuals and so forth colored by different features。

 you can try to identify the patterns in the data。There's more information in these three books if you want to go and find a lot more about regression modeling for prediction。



![](img/5f85d2bc687de5ef6ebb5d4960648f1a_27.png)